# CSetThreadPriority::CSetThreadPriority(bool)

- ea: `0x18005bfe0`
- end: `0x18005c093`
- name: `??0CSetThreadPriority@@QEAA@_N@Z`
- size: `179`
- prototype: `CSetThreadPriority *__fastcall(CSetThreadPriority *this, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ddbe4`

## callees

- `0x18005bfe0`
- `0x18009e9c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bffe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005c00c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005c00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c062`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bff5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005c019`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bff5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005c019`

## pseudocode

```c
CSetThreadPriority *__fastcall CSetThreadPriority::CSetThreadPriority(CSetThreadPriority *this, char a2)
{
  int TickCount64; // edi
  HANDLE CurrentThread; // rax
  int v5; // r9d
  EVENT_LOG *v6; // rcx
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r9

  *(_BYTE *)this = 0;
  if ( a2 )
  {
    TickCount64 = GetTickCount64();
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      *(_BYTE *)this = 1;
      v5 = GetTickCount64();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return this;
      v10 = (unsigned int)(v5 - TickCount64);
      v9 = 51;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v6 + 2), v9, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v10);
      return this;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      v6 = WPP_GLOBAL_Control;
      v9 = 50;
      v10 = LastError;
      goto LABEL_10;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18005bfe0  push    rbx
0x18005bfe2  sub     rsp, 20h
0x18005bfe6  mov     byte ptr [rcx], 0
0x18005bfe9  mov     rbx, rcx
0x18005bfec  test    dl, dl
0x18005bfee  jz      short loc_18005C040
0x18005bff0  mov     [rsp+28h+arg_0], rdi
0x18005bff5  call    cs:__imp_GetTickCount64
0x18005bffb  mov     rdi, rax
0x18005bffe  call    cs:__imp_GetCurrentThread
0x18005c004  mov     rcx, rax; hThread
0x18005c007  mov     edx, 10000h; nPriority
0x18005c00c  call    cs:__imp_SetThreadPriority
0x18005c012  test    eax, eax
0x18005c014  jz      short loc_18005C049
0x18005c016  mov     byte ptr [rbx], 1
0x18005c019  call    cs:__imp_GetTickCount64
0x18005c01f  mov     r9, rax
0x18005c022  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c029  lea     rax, WPP_GLOBAL_Control
0x18005c030  cmp     rcx, rax
0x18005c033  jz      short loc_18005C03B
0x18005c035  test    byte ptr [rcx+1Ch], 1
0x18005c039  jnz     short loc_18005C079
0x18005c03b  mov     rdi, [rsp+28h+arg_0]
0x18005c040  mov     rax, rbx
0x18005c043  add     rsp, 20h
0x18005c047  pop     rbx
0x18005c048  retn
0x18005c049  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c050  lea     rax, WPP_GLOBAL_Control
0x18005c057  cmp     rcx, rax
0x18005c05a  jz      short loc_18005C03B
0x18005c05c  test    byte ptr [rcx+1Ch], 2
0x18005c060  jz      short loc_18005C03B
0x18005c062  call    cs:__imp_GetLastError
0x18005c068  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c06f  mov     edx, 32h ; '2'
0x18005c074  mov     r9d, eax
0x18005c077  jmp     short loc_18005C081
0x18005c079  sub     r9d, edi
0x18005c07c  mov     edx, 33h ; '3'
0x18005c081  mov     rcx, [rcx+10h]
0x18005c085  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x18005c08c  call    WPP_SF_d
0x18005c091  jmp     short loc_18005C03B
```
