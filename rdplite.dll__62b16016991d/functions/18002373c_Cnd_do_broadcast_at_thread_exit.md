# _Cnd_do_broadcast_at_thread_exit

- ea: `0x18002373c`
- end: `0x1800237ea`
- name: `_Cnd_do_broadcast_at_thread_exit`
- size: `174`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ef20`

## callees

- `0x1800081d0`
- `0x180008c30`
- `0x18002373c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002374c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002374c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800237a9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800237a9`

## pseudocode

```c
void __cdecl Cnd_do_broadcast_at_thread_exit()
{
  __int64 *v0; // rbx
  DWORD CurrentThreadId; // ebp
  int v2; // ecx
  int v3; // esi
  _DWORD *v4; // rax

  v0 = qword_18003CA60;
  CurrentThreadId = GetCurrentThreadId();
  std::_Mutex_base::lock((std::_Mutex_base *)qword_18003C5C0);
  do
  {
    v2 = *((_DWORD *)v0 + 200);
    if ( v2 )
    {
      v3 = 0;
      do
      {
        if ( v3 >= 20 )
          break;
        if ( v0[5 * v3 + 2] && LODWORD(v0[5 * v3 + 1]) == CurrentThreadId )
        {
          v4 = (_DWORD *)v0[5 * v3 + 4];
          if ( v4 )
            *v4 = 1;
          Mtx_unlock((_Mtx_t)v0[5 * v3 + 2]);
          WakeAllConditionVariable((PCONDITION_VARIABLE)(v0[5 * v3 + 3] + 8));
          v0[5 * v3 + 2] = 0;
          v2 = --*((_DWORD *)v0 + 200);
        }
        ++v3;
      }
      while ( v2 );
    }
    v0 = (__int64 *)v0[101];
  }
  while ( v0 );
  Mtx_unlock((_Mtx_t)qword_18003C5C0);
}

```

## disassembly

```asm
0x18002373c  push    rbx
0x18002373e  push    rbp
0x18002373f  push    rsi
0x180023740  push    rdi
0x180023741  sub     rsp, 28h
0x180023745  lea     rbx, qword_18003CA60
0x18002374c  call    cs:__imp_GetCurrentThreadId
0x180023752  mov     ebp, eax
0x180023754  lea     rcx, qword_18003C5C0; this
0x18002375b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180023760  mov     ecx, [rbx+320h]
0x180023766  test    ecx, ecx
0x180023768  jz      short loc_1800237CA
0x18002376a  xor     esi, esi
0x18002376c  cmp     esi, 14h
0x18002376f  jge     short loc_1800237CA
0x180023771  movsxd  rax, esi
0x180023774  lea     rdi, [rax+rax*4]
0x180023778  cmp     qword ptr [rbx+rdi*8+10h], 0
0x18002377e  jz      short loc_1800237C4
0x180023780  cmp     [rbx+rdi*8+8], ebp
0x180023784  jnz     short loc_1800237C4
0x180023786  mov     rax, [rbx+rdi*8+20h]
0x18002378b  test    rax, rax
0x18002378e  jz      short loc_180023796
0x180023790  mov     dword ptr [rax], 1
0x180023796  mov     rcx, [rbx+rdi*8+10h]; _Mtx_t
0x18002379b  call    _Mtx_unlock
0x1800237a0  mov     rcx, [rbx+rdi*8+18h]
0x1800237a5  add     rcx, 8; ConditionVariable
0x1800237a9  call    cs:__imp_WakeAllConditionVariable
0x1800237af  mov     qword ptr [rbx+rdi*8+10h], 0
0x1800237b8  dec     dword ptr [rbx+320h]
0x1800237be  mov     ecx, [rbx+320h]
0x1800237c4  inc     esi
0x1800237c6  test    ecx, ecx
0x1800237c8  jnz     short loc_18002376C
0x1800237ca  mov     rbx, [rbx+328h]
0x1800237d1  test    rbx, rbx
0x1800237d4  jnz     short loc_180023760
0x1800237d6  lea     rcx, qword_18003C5C0
0x1800237dd  add     rsp, 28h
0x1800237e1  pop     rdi
0x1800237e2  pop     rsi
0x1800237e3  pop     rbp
0x1800237e4  pop     rbx
0x1800237e5  jmp     _Mtx_unlock
```
