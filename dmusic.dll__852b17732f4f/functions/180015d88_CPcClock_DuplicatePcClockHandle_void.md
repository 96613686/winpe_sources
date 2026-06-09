# CPcClock::DuplicatePcClockHandle(void)

- ea: `0x180015d88`
- end: `0x180015eb3`
- name: `?DuplicatePcClockHandle@CPcClock@@AEAAJXZ`
- size: `299`
- prototype: `__int64 __fastcall(CPcClock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180015b50`

## callees

- `0x180015d88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015e45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015e45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015e0f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015e7a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180015e7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e85`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015ddd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015ddd`

## pseudocode

```c
__int64 __fastcall CPcClock::DuplicatePcClockHandle(CPcClock *this)
{
  HANDLE v1; // rcx
  int v2; // ebp
  unsigned int v3; // esi
  DWORD v4; // r8d
  HANDLE v5; // r14
  _QWORD *v6; // rax
  DWORD CurrentProcessId; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HANDLE CurrentProcess; // rax
  BOOL v12; // ebx
  _QWORD *v13; // rax
  HANDLE TargetHandle; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = -1;
  TargetHandle = 0;
  v3 = 0;
  while ( v2 == -1 || !v1 )
  {
    v4 = *((_DWORD *)CPcClock::m_pShared + 4 * v3 + 4);
    if ( v4 || v2 != -1 )
    {
      if ( !v1 )
      {
        v5 = OpenProcess(0x40u, 0, v4);
        if ( v5 )
        {
          CurrentProcess = GetCurrentProcess();
          v12 = DuplicateHandle(
                  v5,
                  *((HANDLE *)CPcClock::m_pShared + 2 * v3 + 1),
                  CurrentProcess,
                  &TargetHandle,
                  0xC0000000,
                  0,
                  0);
          CloseHandle(v5);
          if ( !v12 )
          {
            v13 = CPcClock::m_pShared;
            v1 = 0;
            *((_DWORD *)CPcClock::m_pShared + 4 * v3 + 4) = 0;
            v13[2 * v3 + 1] = 0;
            TargetHandle = 0;
            goto LABEL_11;
          }
        }
        else
        {
          v6 = CPcClock::m_pShared;
          *((_DWORD *)CPcClock::m_pShared + 4 * v3 + 4) = 0;
          v6[2 * v3 + 1] = 0;
        }
        v1 = TargetHandle;
      }
    }
    else
    {
      v2 = v3;
    }
LABEL_11:
    if ( (int)++v3 >= 64 )
      break;
  }
  CPcClock::m_hClock = v1;
  CurrentProcessId = GetCurrentProcessId();
  v8 = CPcClock::m_pShared;
  v9 = 2LL * v2;
  *((_DWORD *)CPcClock::m_pShared + 2 * v9 + 4) = CurrentProcessId;
  v8[v9 + 1] = TargetHandle;
  return 0;
}

```

## disassembly

```asm
0x180015d88  mov     rax, rsp
0x180015d8b  mov     [rax+10h], rbx
0x180015d8f  mov     [rax+18h], rbp
0x180015d93  mov     [rax+8], rcx
0x180015d97  push    rsi
0x180015d98  push    rdi
0x180015d99  push    r14
0x180015d9b  sub     rsp, 40h
0x180015d9f  xor     ecx, ecx
0x180015da1  or      ebp, 0FFFFFFFFh
0x180015da4  mov     [rax+8], rcx
0x180015da8  xor     esi, esi
0x180015daa  cmp     ebp, 0FFFFFFFFh
0x180015dad  jz      short loc_180015DB4
0x180015daf  test    rcx, rcx
0x180015db2  jnz     short loc_180015E08
0x180015db4  mov     rax, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015dbb  mov     edi, esi
0x180015dbd  add     rdi, rdi
0x180015dc0  mov     r8d, [rax+rdi*8+10h]; dwProcessId
0x180015dc5  test    r8d, r8d
0x180015dc8  jnz     short loc_180015DD3
0x180015dca  cmp     ebp, 0FFFFFFFFh
0x180015dcd  jnz     short loc_180015DD3
0x180015dcf  mov     ebp, esi
0x180015dd1  jmp     short loc_180015E01
0x180015dd3  test    rcx, rcx
0x180015dd6  jnz     short loc_180015E01
0x180015dd8  xor     edx, edx; bInheritHandle
0x180015dda  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180015ddd  call    cs:__imp_OpenProcess
0x180015de3  mov     r14, rax
0x180015de6  test    rax, rax
0x180015de9  jnz     short loc_180015E45
0x180015deb  mov     rax, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015df2  mov     [rax+rdi*8+10h], r14d
0x180015df7  mov     [rax+rdi*8+8], r14
0x180015dfc  mov     rcx, [rsp+58h+TargetHandle]
0x180015e01  inc     esi
0x180015e03  cmp     esi, 40h ; '@'
0x180015e06  jl      short loc_180015DAA
0x180015e08  mov     cs:?m_hClock@CPcClock@@0PEAXEA, rcx; void * CPcClock::m_hClock
0x180015e0f  call    cs:__imp_GetCurrentProcessId
0x180015e15  mov     rcx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015e1c  mov     rbx, [rsp+58h+arg_8]
0x180015e21  movsxd  rdx, ebp
0x180015e24  mov     rbp, [rsp+58h+arg_10]
0x180015e29  add     rdx, rdx
0x180015e2c  mov     [rcx+rdx*8+10h], eax
0x180015e30  mov     rax, [rsp+58h+TargetHandle]
0x180015e35  mov     [rcx+rdx*8+8], rax
0x180015e3a  xor     eax, eax
0x180015e3c  add     rsp, 40h
0x180015e40  pop     r14
0x180015e42  pop     rdi
0x180015e43  pop     rsi
0x180015e44  retn
0x180015e45  call    cs:__imp_GetCurrentProcess
0x180015e4b  mov     rdx, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015e52  lea     r9, [rsp+58h+TargetHandle]; lpTargetHandle
0x180015e57  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180015e5f  mov     r8, rax; hTargetProcessHandle
0x180015e62  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x180015e6a  mov     rcx, r14; hSourceProcessHandle
0x180015e6d  mov     [rsp+58h+dwDesiredAccess], 0C0000000h; dwDesiredAccess
0x180015e75  mov     rdx, [rdx+rdi*8+8]; hSourceHandle
0x180015e7a  call    cs:__imp_DuplicateHandle
0x180015e80  mov     rcx, r14; hObject
0x180015e83  mov     ebx, eax
0x180015e85  call    cs:__imp_CloseHandle
0x180015e8b  test    ebx, ebx
0x180015e8d  jnz     loc_180015DFC
0x180015e93  mov     rax, cs:?m_pShared@CPcClock@@0PEAUPCCLOCKSHARE@@EA; PCCLOCKSHARE * CPcClock::m_pShared
0x180015e9a  xor     ecx, ecx
0x180015e9c  mov     [rax+rdi*8+10h], ebx
0x180015ea0  mov     qword ptr [rax+rdi*8+8], 0
0x180015ea9  mov     [rsp+58h+TargetHandle], rcx
0x180015eae  jmp     loc_180015E01
```
