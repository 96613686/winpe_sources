# GetCurrentToken

- ea: `0x180009b28`
- end: `0x180009c02`
- name: `GetCurrentToken`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800094f0`
- `0x180009740`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180009b28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180009b83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180009b83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009b3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009b3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b61`

## string_xrefs

- `0x180009b77`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall GetCurrentToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  void *v4; // rax
  HMODULE ModuleHandleA; // rax
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 0, &TokenHandle) )
  {
    v4 = TokenHandle;
    goto LABEL_8;
  }
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    v4 = 0;
LABEL_8:
    *a1 = v4;
    return 0;
  }
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2026, (unsigned int)LastError);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  MI_ReportErrorDetails_ForCustomError(LastError, (int)L"HRESULT", 0, 0);
  return 2;
}

```

## disassembly

```asm
0x180009b28  mov     [rsp+arg_0], rbx
0x180009b2d  push    rdi
0x180009b2e  sub     rsp, 40h
0x180009b32  mov     rdi, rcx
0x180009b35  mov     [rsp+48h+TokenHandle], 0
0x180009b3e  call    cs:__imp_GetCurrentThread
0x180009b44  xor     r8d, r8d; OpenAsSelf
0x180009b47  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180009b4c  mov     rcx, rax; ThreadHandle
0x180009b4f  lea     edx, [r8+0Eh]; DesiredAccess
0x180009b53  call    cs:__imp_OpenThreadToken
0x180009b59  test    eax, eax
0x180009b5b  jnz     loc_180009BED
0x180009b61  call    cs:__imp_GetLastError
0x180009b67  mov     ebx, eax
0x180009b69  cmp     eax, 3F0h
0x180009b6e  jnz     short loc_180009B74
0x180009b70  xor     eax, eax
0x180009b72  jmp     short loc_180009BF2
0x180009b74  xorps   xmm0, xmm0
0x180009b77  lea     rcx, ModuleName; "mpunits.dll"
0x180009b7e  movups  [rsp+48h+var_18], xmm0
0x180009b83  call    cs:__imp_GetModuleHandleA
0x180009b89  mov     r8d, ebx
0x180009b8c  mov     edx, 7EAh
0x180009b91  mov     rcx, rax
0x180009b94  call    _Intlstr_FormatString_FormatMessage
0x180009b99  mov     qword ptr [rsp+48h+var_18], rax
0x180009b9e  mov     byte ptr [rsp+48h+var_18+8], 1
0x180009ba3  test    ebx, ebx
0x180009ba5  jle     short loc_180009BB0
0x180009ba7  movzx   ebx, bx
0x180009baa  or      ebx, 80070000h
0x180009bb0  movaps  xmm0, [rsp+48h+var_18]
0x180009bb5  lea     r9, [rsp+48h+var_18]
0x180009bba  mov     [rsp+48h+var_20], 0; __int64
0x180009bc3  lea     rdx, aHresult; "HRESULT"
0x180009bca  mov     r8d, 12h
0x180009bd0  movdqa  [rsp+48h+var_18], xmm0
0x180009bd6  mov     ecx, ebx; int
0x180009bd8  mov     [rsp+48h+var_28], 0; __int64
0x180009be1  call    MI_ReportErrorDetails_ForCustomError
0x180009be6  mov     eax, 2
0x180009beb  jmp     short loc_180009BF7
0x180009bed  mov     rax, [rsp+48h+TokenHandle]
0x180009bf2  mov     [rdi], rax
0x180009bf5  xor     eax, eax
0x180009bf7  mov     rbx, [rsp+48h+arg_0]
0x180009bfc  add     rsp, 40h
0x180009c00  pop     rdi
0x180009c01  retn
```
