# _Cnd_do_broadcast_at_thread_exit

- ea: `0x18002ace0`
- end: `0x18002adfb`
- name: `_Cnd_do_broadcast_at_thread_exit`
- size: `283`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029260`

## callees

- `0x18002ab98`
- `0x18002ace0`
- `0x18002ae04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ad71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002adcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ad71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002adcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002acf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002acf2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002ad80`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002ad80`

## pseudocode

```c
void __cdecl Cnd_do_broadcast_at_thread_exit()
{
  DWORD CurrentThreadId; // ebp
  __int64 *v1; // rbx
  int v2; // ecx
  int v3; // esi
  _DWORD *v4; // rax
  __int64 v5; // rcx

  CurrentThreadId = GetCurrentThreadId();
  if ( (unsigned int)mtx_do_lock(qword_18003C460) )
    std::_Throw_Cpp_error(5);
  if ( dword_18003C4AC == 0x7FFFFFFF )
  {
    dword_18003C4AC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v1 = qword_18003C7C0;
  do
  {
    v2 = *((_DWORD *)v1 + 200);
    if ( v2 )
    {
      v3 = 0;
      do
      {
        if ( v3 >= 20 )
          break;
        if ( v1[5 * v3 + 2] && LODWORD(v1[5 * v3 + 1]) == CurrentThreadId )
        {
          v4 = (_DWORD *)v1[5 * v3 + 4];
          if ( v4 )
            *v4 = 1;
          v5 = v1[5 * v3 + 2];
          if ( (*(_DWORD *)(v5 + 76))-- == 1 )
          {
            *(_DWORD *)(v5 + 72) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 16));
          }
          WakeAllConditionVariable((PCONDITION_VARIABLE)(v1[5 * v3 + 3] + 8));
          v1[5 * v3 + 2] = 0;
          v2 = --*((_DWORD *)v1 + 200);
        }
        ++v3;
      }
      while ( v2 );
    }
    v1 = (__int64 *)v1[101];
  }
  while ( v1 );
  if ( !--dword_18003C4AC )
  {
    dword_18003C4A8 = -1;
    ReleaseSRWLockExclusive(&stru_18003C470);
  }
}

```

## disassembly

```asm
0x18002ace0  push    rbx
0x18002ace2  push    rbp
0x18002ace3  push    rsi
0x18002ace4  push    rdi
0x18002ace5  sub     rsp, 38h
0x18002ace9  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18002acf2  call    cs:__imp_GetCurrentThreadId
0x18002acf8  mov     ebp, eax
0x18002acfa  lea     rcx, qword_18003C460
0x18002ad01  call    mtx_do_lock
0x18002ad06  test    eax, eax
0x18002ad08  jnz     loc_18002ADF0
0x18002ad0e  cmp     cs:dword_18003C4AC, 7FFFFFFFh
0x18002ad18  jz      loc_18002ADDB
0x18002ad1e  lea     rbx, qword_18003C7C0
0x18002ad25  mov     ecx, [rbx+320h]
0x18002ad2b  test    ecx, ecx
0x18002ad2d  jz      short loc_18002ADA1
0x18002ad2f  xor     esi, esi
0x18002ad31  cmp     esi, 14h
0x18002ad34  jge     short loc_18002ADA1
0x18002ad36  movsxd  rax, esi
0x18002ad39  lea     rdi, [rax+rax*4]
0x18002ad3d  cmp     qword ptr [rbx+rdi*8+10h], 0
0x18002ad43  jz      short loc_18002AD9B
0x18002ad45  cmp     [rbx+rdi*8+8], ebp
0x18002ad49  jnz     short loc_18002AD9B
0x18002ad4b  mov     rax, [rbx+rdi*8+20h]
0x18002ad50  test    rax, rax
0x18002ad53  jz      short loc_18002AD5B
0x18002ad55  mov     dword ptr [rax], 1
0x18002ad5b  mov     rcx, [rbx+rdi*8+10h]
0x18002ad60  sub     dword ptr [rcx+4Ch], 1
0x18002ad64  jnz     short loc_18002AD77
0x18002ad66  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x18002ad6d  add     rcx, 10h; SRWLock
0x18002ad71  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ad77  mov     rcx, [rbx+rdi*8+18h]
0x18002ad7c  add     rcx, 8; ConditionVariable
0x18002ad80  call    cs:__imp_WakeAllConditionVariable
0x18002ad86  mov     qword ptr [rbx+rdi*8+10h], 0
0x18002ad8f  dec     dword ptr [rbx+320h]
0x18002ad95  mov     ecx, [rbx+320h]
0x18002ad9b  inc     esi
0x18002ad9d  test    ecx, ecx
0x18002ad9f  jnz     short loc_18002AD31
0x18002ada1  mov     rbx, [rbx+328h]
0x18002ada8  test    rbx, rbx
0x18002adab  jnz     loc_18002AD25
0x18002adb1  sub     cs:dword_18003C4AC, 1
0x18002adb8  jnz     short loc_18002ADD2
0x18002adba  mov     cs:dword_18003C4A8, 0FFFFFFFFh
0x18002adc4  lea     rcx, stru_18003C470; SRWLock
0x18002adcb  call    cs:__imp_ReleaseSRWLockExclusive
0x18002add1  nop
0x18002add2  add     rsp, 38h
0x18002add6  pop     rdi
0x18002add7  pop     rsi
0x18002add8  pop     rbp
0x18002add9  pop     rbx
0x18002adda  retn
0x18002addb  mov     cs:dword_18003C4AC, 7FFFFFFEh
0x18002ade5  mov     ecx, 6; int
0x18002adea  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002adf0  mov     ecx, 5; int
0x18002adf5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
