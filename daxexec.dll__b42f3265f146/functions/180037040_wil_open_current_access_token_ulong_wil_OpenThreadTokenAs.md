# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x180037040`
- end: `0x180037116`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180031534`
- `0x180032218`
- `0x180033100`
- `0x1800bb650`

## callees

- `0x1800125f4`
- `0x180037040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800370a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800370a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037058`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800370b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800370b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180037074`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180037074`

## string_xrefs

- `0x180037101`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1, DWORD a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  bool v7; // sf
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, 1, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a2, &TokenHandle) )
      goto LABEL_10;
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v7 = LastError < 0;
LABEL_9:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)(unsigned int)LastError,
      v9);
LABEL_10:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x180037040  mov     [rsp+arg_0], rbx
0x180037045  push    rdi
0x180037046  sub     rsp, 30h
0x18003704a  mov     edi, edx
0x18003704c  mov     [rsp+38h+TokenHandle], 0
0x180037055  mov     rbx, rcx
0x180037058  call    cs:__imp_GetCurrentThread
0x18003705f  nop     dword ptr [rax+rax+00h]
0x180037064  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180037069  mov     r8d, 1; OpenAsSelf
0x18003706f  mov     rcx, rax; ThreadHandle
0x180037072  mov     edx, edi; DesiredAccess
0x180037074  call    cs:__imp_OpenThreadToken
0x18003707b  nop     dword ptr [rax+rax+00h]
0x180037080  test    eax, eax
0x180037082  jnz     short loc_1800370E5
0x180037084  call    cs:__imp_GetLastError
0x18003708b  nop     dword ptr [rax+rax+00h]
0x180037090  test    eax, eax
0x180037092  jle     short loc_18003709C
0x180037094  movzx   eax, ax
0x180037097  or      eax, 80070000h
0x18003709c  cmp     eax, 800703F0h
0x1800370a1  jnz     short loc_1800370E1
0x1800370a3  call    cs:__imp_GetCurrentProcess
0x1800370aa  nop     dword ptr [rax+rax+00h]
0x1800370af  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800370b4  mov     edx, edi; DesiredAccess
0x1800370b6  mov     rcx, rax; ProcessHandle
0x1800370b9  call    cs:__imp_OpenProcessToken
0x1800370c0  nop     dword ptr [rax+rax+00h]
0x1800370c5  test    eax, eax
0x1800370c7  jnz     short loc_1800370E5
0x1800370c9  call    cs:__imp_GetLastError
0x1800370d0  nop     dword ptr [rax+rax+00h]
0x1800370d5  test    eax, eax
0x1800370d7  jle     short loc_1800370E3
0x1800370d9  movzx   eax, ax
0x1800370dc  or      eax, 80070000h
0x1800370e1  test    eax, eax
0x1800370e3  js      short loc_1800370FC
0x1800370e5  mov     rax, [rsp+38h+TokenHandle]
0x1800370ea  mov     [rbx], rax
0x1800370ed  mov     rax, rbx
0x1800370f0  mov     rbx, [rsp+38h+arg_0]
0x1800370f5  add     rsp, 30h
0x1800370f9  pop     rdi
0x1800370fa  retn
0x1800370fc  mov     rcx, [rsp+38h]; this
0x180037101  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037108  mov     r9d, eax; char *
0x18003710b  mov     edx, 0E1h; void *
0x180037110  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
