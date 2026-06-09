# ImpersonationReverter::Revert(void)

- ea: `0x180096894`
- end: `0x180096962`
- name: `?Revert@ImpersonationReverter@@SA?AU1@XZ`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800240f0`
- `0x180096618`
- `0x1800967b0`

## callees

- `0x180013100`
- `0x180015314`
- `0x18002031c`
- `0x180096894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180096912`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180096912`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800968dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800968dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800968c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800968c0`

## string_xrefs

- `0x180096936`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`
- `0x180096950`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonationReverter::Revert(__int64 a1)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // ebx
  DWORD LastError; // eax
  const char *v5; // r9
  unsigned int v7; // [rsp+20h] [rbp-28h]
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-18h] BYREF
  char v10; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_BYTE *)a1 = 1;
  *(_QWORD *)(a1 + 8) = 0;
  v8 = a1 + 8;
  TokenHandle = 0;
  v10 = 1;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v8);
  if ( v3 )
  {
    if ( !SetThreadToken(0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
        v5);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
        (const char *)LastError,
        v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180096894  mov     r11, rsp
0x180096897  mov     [r11+10h], rbx
0x18009689b  mov     [r11+8], rcx
0x18009689f  push    rdi
0x1800968a0  sub     rsp, 40h
0x1800968a4  mov     rdi, rcx
0x1800968a7  mov     byte ptr [rcx], 1
0x1800968aa  lea     rax, [rcx+8]
0x1800968ae  and     qword ptr [rax], 0
0x1800968b2  mov     [r11-20h], rax
0x1800968b6  and     qword ptr [r11-18h], 0
0x1800968bb  mov     [rsp+48h+var_10], 1
0x1800968c0  call    cs:__imp_GetCurrentThread
0x1800968c7  nop     dword ptr [rax+rax+00h]
0x1800968cc  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800968d1  mov     edx, 0Ch; DesiredAccess
0x1800968d6  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800968da  mov     rcx, rax; ThreadHandle
0x1800968dd  call    cs:__imp_OpenThreadToken
0x1800968e4  nop     dword ptr [rax+rax+00h]
0x1800968e9  mov     ebx, eax
0x1800968eb  lea     rcx, [rsp+48h+var_20]
0x1800968f0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800968f5  test    ebx, ebx
0x1800968f7  jnz     short loc_18009690E
0x1800968f9  call    cs:__imp_GetLastError
0x180096900  nop     dword ptr [rax+rax+00h]
0x180096905  cmp     eax, 3F0h
0x18009690a  jnz     short loc_180096948
0x18009690c  jmp     short loc_180096927
0x18009690e  xor     edx, edx; Token
0x180096910  xor     ecx, ecx; Thread
0x180096912  call    cs:__imp_SetThreadToken
0x180096919  nop     dword ptr [rax+rax+00h]
0x18009691e  mov     rcx, [rsp+48h]; this
0x180096923  test    eax, eax
0x180096925  jz      short loc_180096936
0x180096927  mov     rax, rdi
0x18009692a  mov     rbx, [rsp+48h+arg_8]
0x18009692f  add     rsp, 40h
0x180096933  pop     rdi
0x180096934  retn
0x180096936  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009693d  mov     edx, 3Eh ; '>'; void *
0x180096942  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180096948  mov     rcx, [rsp+48h]; this
0x18009694d  mov     r9d, eax; char *
0x180096950  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\execmodel\\des"...
0x180096957  mov     edx, 3Ah ; ':'; void *
0x18009695c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
