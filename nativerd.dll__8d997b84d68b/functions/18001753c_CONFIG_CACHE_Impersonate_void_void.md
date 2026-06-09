# CONFIG_CACHE::Impersonate(void *,void * *)

- ea: `0x18001753c`
- end: `0x1800175bc`
- name: `?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(HANDLE hToken, PHANDLE TokenHandle)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027888`
- `0x18004d674`
- `0x18004dfb8`
- `0x18004e580`
- `0x18004f07c`
- `0x18004f1a0`
- `0x18004f92c`
- `0x180050238`

## callees

- `0x18001753c`
- `0x18001a814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001759a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001759a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017590`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001757b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001757b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800175aa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800175aa`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::Impersonate(HANDLE hToken, PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax

  *TokenHandle = 0;
  if ( !hToken
    || ((CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 6u, 1, TokenHandle))
     || GetLastError() == 1008)
    && ImpersonateLoggedOnUser(hToken) )
  {
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
      McTemplateU0pp_EtwEventWriteTransfer(hToken, TokenHandle, hToken);
  }
  else
  {
    GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x18001753c  mov     [rsp+arg_0], rbx
0x180017541  push    rdi
0x180017542  sub     rsp, 20h
0x180017546  mov     qword ptr [rdx], 0
0x18001754d  mov     rdi, rdx
0x180017550  mov     rbx, rcx
0x180017553  test    rcx, rcx
0x180017556  jnz     short loc_18001757B
0x180017558  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x18001755f  jnz     short loc_18001756E
0x180017561  mov     rbx, [rsp+28h+arg_0]
0x180017566  xor     eax, eax
0x180017568  add     rsp, 20h
0x18001756c  pop     rdi
0x18001756d  retn
0x18001756e  mov     r9, [rdi]
0x180017571  mov     r8, rbx
0x180017574  call    McTemplateU0pp_EtwEventWriteTransfer
0x180017579  jmp     short loc_180017561
0x18001757b  call    cs:__imp_GetCurrentThread
0x180017581  mov     edx, 6; DesiredAccess
0x180017586  mov     r9, rdi; TokenHandle
0x180017589  mov     rcx, rax; ThreadHandle
0x18001758c  lea     r8d, [rdx-5]; OpenAsSelf
0x180017590  call    cs:__imp_OpenThreadToken
0x180017596  test    eax, eax
0x180017598  jnz     short loc_1800175A7
0x18001759a  call    cs:__imp_GetLastError
0x1800175a0  cmp     eax, 3F0h
0x1800175a5  jnz     short loc_1800175B4
0x1800175a7  mov     rcx, rbx; hToken
0x1800175aa  call    cs:__imp_ImpersonateLoggedOnUser
0x1800175b0  test    eax, eax
0x1800175b2  jnz     short loc_180017558
0x1800175b4  call    cs:__imp_GetLastError
0x1800175ba  jmp     short loc_180017561
```
