# CertTypeRetrieveClientToken(void * *)

- ea: `0x18002cddc`
- end: `0x18002cf4a`
- name: `?CertTypeRetrieveClientToken@@YAHPEAPEAX@Z`
- size: `366`
- prototype: `_BOOL8 __fastcall(void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3f0`
- `0x18001246c`
- `0x18002d1c0`

## callees

- `0x180008400`
- `0x180012450`
- `0x18002cddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cdf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cdf7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ce2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ce2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ce71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ce71`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cead`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cead`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002cee6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002cee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf2d`

## pseudocode

```c
_BOOL8 __fastcall CertTypeRetrieveClientToken(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  int v4; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE ExistingTokenHandle; // [rsp+38h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = CurrentThread;
  if ( CurrentThread )
  {
    v4 = 0;
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_14;
    v4 = myHLastError();
    CSPrintErrorLineFile(0x55A0324u, v4);
    if ( v4 != -2147023888 )
    {
      CSPrintErrorLineFile(0x55D0324u, v4);
      goto LABEL_16;
    }
    CloseHandle(v3);
    CurrentProcess = GetCurrentProcess();
    v3 = CurrentProcess;
    if ( CurrentProcess )
    {
      ExistingTokenHandle = 0;
      if ( OpenProcessToken(CurrentProcess, 2u, &ExistingTokenHandle) )
      {
        v4 = 0;
        if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
        {
          v4 = myHLastError();
          CSPrintErrorLineFile(0x5810324u, v4);
          CloseHandle(v3);
          v3 = 0;
        }
        CloseHandle(ExistingTokenHandle);
      }
      else
      {
        v4 = myHLastError();
        CSPrintErrorLineFile(0x5760324u, v4);
        CloseHandle(v3);
        v3 = 0;
      }
    }
    else
    {
      v4 = myHLastError();
      CSPrintErrorLineFile(0x56A0324u, v4);
    }
    if ( !v4 )
LABEL_14:
      *a1 = TokenHandle;
    if ( !v3 )
      return v4 == 0;
LABEL_16:
    CloseHandle(v3);
    return v4 == 0;
  }
  v4 = myHLastError();
  CSPrintErrorLineFile(0x5520324u, v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x18002cddc  mov     [rsp+arg_0], rbx
0x18002cde1  mov     [rsp+arg_18], rsi
0x18002cde6  push    rdi
0x18002cde7  sub     rsp, 20h
0x18002cdeb  mov     rsi, rcx
0x18002cdee  mov     [rsp+28h+TokenHandle], 0
0x18002cdf7  call    cs:__imp_GetCurrentThread
0x18002cdfd  mov     rdi, rax
0x18002ce00  test    rax, rax
0x18002ce03  jnz     short loc_18002CE1D
0x18002ce05  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002ce0a  mov     edx, eax; int
0x18002ce0c  mov     ecx, 5520324h; unsigned int
0x18002ce11  mov     ebx, eax
0x18002ce13  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ce18  jmp     loc_18002CF33
0x18002ce1d  xor     ebx, ebx
0x18002ce1f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002ce24  mov     rcx, rdi; ThreadHandle
0x18002ce27  lea     edx, [rbx+8]; DesiredAccess
0x18002ce2a  lea     r8d, [rbx+1]; OpenAsSelf
0x18002ce2e  call    cs:__imp_OpenThreadToken
0x18002ce34  test    eax, eax
0x18002ce36  jnz     loc_18002CF1D
0x18002ce3c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002ce41  mov     edx, eax; int
0x18002ce43  mov     ecx, 55A0324h; unsigned int
0x18002ce48  mov     ebx, eax
0x18002ce4a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ce4f  cmp     ebx, 800703F0h
0x18002ce55  jz      short loc_18002CE68
0x18002ce57  mov     edx, ebx; int
0x18002ce59  mov     ecx, 55D0324h; unsigned int
0x18002ce5e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ce63  jmp     loc_18002CF2A
0x18002ce68  mov     rcx, rdi; hObject
0x18002ce6b  call    cs:__imp_CloseHandle
0x18002ce71  call    cs:__imp_GetCurrentProcess
0x18002ce77  mov     rdi, rax
0x18002ce7a  test    rax, rax
0x18002ce7d  jnz     short loc_18002CE97
0x18002ce7f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002ce84  mov     edx, eax; int
0x18002ce86  mov     ecx, 56A0324h; unsigned int
0x18002ce8b  mov     ebx, eax
0x18002ce8d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ce92  jmp     loc_18002CF19
0x18002ce97  lea     r8, [rsp+28h+ExistingTokenHandle]; TokenHandle
0x18002ce9c  mov     [rsp+28h+ExistingTokenHandle], 0
0x18002cea5  mov     edx, 2; DesiredAccess
0x18002ceaa  mov     rcx, rdi; ProcessHandle
0x18002cead  call    cs:__imp_OpenProcessToken
0x18002ceb3  test    eax, eax
0x18002ceb5  jnz     short loc_18002CED7
0x18002ceb7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002cebc  mov     edx, eax; int
0x18002cebe  mov     ecx, 5760324h; unsigned int
0x18002cec3  mov     ebx, eax
0x18002cec5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ceca  mov     rcx, rdi; hObject
0x18002cecd  call    cs:__imp_CloseHandle
0x18002ced3  xor     edi, edi
0x18002ced5  jmp     short loc_18002CF19
0x18002ced7  mov     rcx, [rsp+28h+ExistingTokenHandle]; ExistingTokenHandle
0x18002cedc  lea     r8, [rsp+28h+TokenHandle]; DuplicateTokenHandle
0x18002cee1  xor     ebx, ebx
0x18002cee3  lea     edx, [rbx+2]; ImpersonationLevel
0x18002cee6  call    cs:__imp_DuplicateToken
0x18002ceec  test    eax, eax
0x18002ceee  jnz     short loc_18002CF0E
0x18002cef0  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002cef5  mov     edx, eax; int
0x18002cef7  mov     ecx, 5810324h; unsigned int
0x18002cefc  mov     ebx, eax
0x18002cefe  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002cf03  mov     rcx, rdi; hObject
0x18002cf06  call    cs:__imp_CloseHandle
0x18002cf0c  xor     edi, edi
0x18002cf0e  mov     rcx, [rsp+28h+ExistingTokenHandle]; hObject
0x18002cf13  call    cs:__imp_CloseHandle
0x18002cf19  test    ebx, ebx
0x18002cf1b  jnz     short loc_18002CF25
0x18002cf1d  mov     rax, [rsp+28h+TokenHandle]
0x18002cf22  mov     [rsi], rax
0x18002cf25  test    rdi, rdi
0x18002cf28  jz      short loc_18002CF33
0x18002cf2a  mov     rcx, rdi; hObject
0x18002cf2d  call    cs:__imp_CloseHandle
0x18002cf33  mov     rsi, [rsp+28h+arg_18]
0x18002cf38  xor     eax, eax
0x18002cf3a  test    ebx, ebx
0x18002cf3c  mov     rbx, [rsp+28h+arg_0]
0x18002cf41  setz    al
0x18002cf44  add     rsp, 20h
0x18002cf48  pop     rdi
0x18002cf49  retn
```
