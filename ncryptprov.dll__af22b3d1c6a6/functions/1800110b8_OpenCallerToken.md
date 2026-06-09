# OpenCallerToken

- ea: `0x1800110b8`
- end: `0x180011200`
- name: `OpenCallerToken`
- size: `328`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800107a4`
- `0x180010fac`
- `0x1800121e4`
- `0x1800253b4`
- `0x180051e8c`
- `0x18006128c`

## callees

- `0x18000b250`
- `0x1800110b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001116c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001116c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011146`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011146`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001115c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001115c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111ef`

## string_xrefs

- `0x1800111ce`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(DWORD DesiredAccess, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  int v7; // edx
  int v8; // r8d
  HANDLE CurrentProcess; // rax
  int v10; // edx
  int v11; // r8d
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, DesiredAccess, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, DesiredAccess, &TokenHandle) )
    {
LABEL_2:
      LastError = 0;
      *a2 = TokenHandle;
      TokenHandle = 0;
      goto LABEL_3;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        45);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v8,
      (unsigned int)"dwReturn",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
      37);
  }
LABEL_3:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800110b8  mov     [rsp+arg_0], rbx
0x1800110bd  mov     [rsp+arg_8], rsi
0x1800110c2  push    rdi
0x1800110c3  sub     rsp, 40h
0x1800110c7  mov     rdi, rdx
0x1800110ca  mov     [rsp+48h+TokenHandle], 0
0x1800110d3  mov     esi, ecx
0x1800110d5  call    cs:__imp_GetCurrentThread
0x1800110dc  nop     dword ptr [rax+rax+00h]
0x1800110e1  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800110e6  mov     r8d, 1; OpenAsSelf
0x1800110ec  mov     rcx, rax; ThreadHandle
0x1800110ef  mov     edx, esi; DesiredAccess
0x1800110f1  call    cs:__imp_OpenThreadToken
0x1800110f8  nop     dword ptr [rax+rax+00h]
0x1800110fd  test    eax, eax
0x1800110ff  jz      short loc_180011131
0x180011101  mov     rax, [rsp+48h+TokenHandle]
0x180011106  xor     ebx, ebx
0x180011108  mov     [rdi], rax
0x18001110b  mov     [rsp+48h+TokenHandle], rbx
0x180011110  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180011115  test    rcx, rcx
0x180011118  jnz     loc_1800111EF
0x18001111e  mov     rsi, [rsp+48h+arg_8]
0x180011123  mov     eax, ebx
0x180011125  mov     rbx, [rsp+48h+arg_0]
0x18001112a  add     rsp, 40h
0x18001112e  pop     rdi
0x18001112f  retn
0x180011131  call    cs:__imp_GetLastError
0x180011138  nop     dword ptr [rax+rax+00h]
0x18001113d  mov     ebx, eax
0x18001113f  cmp     eax, 3F0h
0x180011144  jnz     short loc_1800111A1
0x180011146  call    cs:__imp_GetCurrentProcess
0x18001114d  nop     dword ptr [rax+rax+00h]
0x180011152  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180011157  mov     edx, esi; DesiredAccess
0x180011159  mov     rcx, rax; ProcessHandle
0x18001115c  call    cs:__imp_OpenProcessToken
0x180011163  nop     dword ptr [rax+rax+00h]
0x180011168  test    eax, eax
0x18001116a  jnz     short loc_180011101
0x18001116c  call    cs:__imp_GetLastError
0x180011173  nop     dword ptr [rax+rax+00h]
0x180011178  mov     ebx, eax
0x18001117a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011181  lea     rax, WPP_GLOBAL_Control
0x180011188  cmp     rcx, rax
0x18001118b  jz      short loc_180011110
0x18001118d  test    byte ptr [rcx+1Ch], 1
0x180011191  jz      loc_180011110
0x180011197  mov     [rsp+48h+var_18], 12Dh
0x18001119f  jmp     short loc_1800111CA
0x1800111a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111a8  lea     rax, WPP_GLOBAL_Control
0x1800111af  cmp     rcx, rax
0x1800111b2  jz      loc_180011110
0x1800111b8  test    byte ptr [rcx+1Ch], 1
0x1800111bc  jz      loc_180011110
0x1800111c2  mov     [rsp+48h+var_18], 125h
0x1800111ca  mov     rcx, [rcx+10h]
0x1800111ce  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800111d5  mov     [rsp+48h+var_20], rax
0x1800111da  lea     r9, aDwreturn; "dwReturn"
0x1800111e1  mov     [rsp+48h+var_28], ebx
0x1800111e5  call    WPP_SF_sDsd
0x1800111ea  jmp     loc_180011110
0x1800111ef  call    cs:__imp_CloseHandle
0x1800111f6  nop     dword ptr [rax+rax+00h]
0x1800111fb  jmp     loc_18001111E
```
