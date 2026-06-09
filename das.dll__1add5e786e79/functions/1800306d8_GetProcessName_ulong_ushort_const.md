# GetProcessName(ulong,ushort * const)

- ea: `0x1800306d8`
- end: `0x180030744`
- name: `?GetProcessName@@YAJKQEAG@Z`
- size: `108`
- prototype: `__int64 __fastcall(DWORD dwProcessId, LPWSTR lpFilename)`
- caller_count: `15`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002e494`
- `0x18002ed00`
- `0x18002eee0`
- `0x18002f4e0`
- `0x180030300`
- `0x1800304f0`
- `0x180030750`
- `0x180030960`
- `0x180030dac`
- `0x180031258`
- `0x180031658`
- `0x1800320e0`
- `0x180032484`
- `0x180046ad0`
- `0x180046ce0`

## callees

- `0x180019cbc`
- `0x18002aa34`
- `0x1800306d8`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003070e`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003070e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800306eb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800306eb`

## string_xrefs

- `0x180030720`: `onecore\base\devices\association\service\lib\misc.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessName(DWORD dwProcessId, LPWSTR lpFilename)
{
  HANDLE v3; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v9; // [rsp+40h] [rbp+18h] BYREF

  v3 = OpenProcess(0x400u, 0, dwProcessId);
  v9 = v3;
  if ( v3 )
  {
    if ( K32GetModuleFileNameExW(v3, 0, lpFilename, 0x104u) )
    {
      LastError = 0;
      goto LABEL_7;
    }
    v5 = 122;
  }
  else
  {
    v5 = 117;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\misc.cpp",
                v4);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x1800306d8  push    rbx
0x1800306da  sub     rsp, 20h
0x1800306de  mov     rbx, rdx
0x1800306e1  mov     r8d, ecx; dwProcessId
0x1800306e4  xor     edx, edx; bInheritHandle
0x1800306e6  mov     ecx, 400h; dwDesiredAccess
0x1800306eb  call    cs:__imp_OpenProcess
0x1800306f1  mov     [rsp+28h+arg_10], rax
0x1800306f6  test    rax, rax
0x1800306f9  jnz     short loc_180030700
0x1800306fb  lea     edx, [rax+75h]
0x1800306fe  jmp     short loc_18003071B
0x180030700  mov     r9d, 104h; nSize
0x180030706  mov     r8, rbx; lpFilename
0x180030709  xor     edx, edx; hModule
0x18003070b  mov     rcx, rax; hProcess
0x18003070e  call    cs:__imp_K32GetModuleFileNameExW
0x180030714  test    eax, eax
0x180030716  jnz     short loc_180030730
0x180030718  lea     edx, [rax+7Ah]; void *
0x18003071b  mov     rcx, [rsp+28h]; this
0x180030720  lea     r8, aOnecoreBaseDev_19; "onecore\\base\\devices\\association\\se"...
0x180030727  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003072c  mov     ebx, eax
0x18003072e  jmp     short loc_180030732
0x180030730  xor     ebx, ebx
0x180030732  lea     rcx, [rsp+28h+arg_10]
0x180030737  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003073c  mov     eax, ebx
0x18003073e  add     rsp, 20h
0x180030742  pop     rbx
0x180030743  retn
```
