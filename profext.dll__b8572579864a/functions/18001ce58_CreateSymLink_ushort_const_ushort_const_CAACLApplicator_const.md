# CreateSymLink(ushort const *,ushort const *,CAACLApplicator const &)

- ea: `0x18001ce58`
- end: `0x18001cf66`
- name: `?CreateSymLink@@YAJPEBG0AEBVCAACLApplicator@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, const struct CAACLApplicator *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000feb0`

## callees

- `0x180001854`
- `0x180004594`
- `0x18000f864`
- `0x18001ce58`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cec0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cec0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001cf22`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001cf22`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001ce6e`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001ce6e`

## string_xrefs

- `0x18001ce83`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18001cefe`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18001cf37`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`

## pseudocode

```c
__int64 __fastcall CreateSymLink(LPCWSTR lpFileName, const unsigned __int16 *a2, const struct CAACLApplicator *a3)
{
  const char *v5; // r9
  HANDLE FileW; // rdx
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  unsigned int LastError; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v14; // [rsp+68h] [rbp+20h] BYREF

  if ( !CreateSymbolicLinkW(lpFileName, a2, 1u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA1,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
             v5);
  FileW = CreateFileW(lpFileName, 0x40040000u, 0, 0, 3u, 0x2200000u, 0);
  v14 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v9 = 167;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
                  v8);
    goto LABEL_11;
  }
  v10 = (*(__int64 (__fastcall **)(const struct CAACLApplicator *, HANDLE))(*(_QWORD *)a3 + 8LL))(a3, FileW);
  LastError = v10;
  if ( v10 >= 0 )
  {
    v14 = -1;
    if ( SetFileAttributesW(lpFileName, 0x2006u) )
    {
      LastError = 0;
      goto LABEL_11;
    }
    v9 = 178;
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
    (const char *)(unsigned int)v10,
    dwCreationDisposition);
LABEL_11:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x18001ce58  mov     [rsp+arg_0], rbx
0x18001ce5d  push    rdi
0x18001ce5e  sub     rsp, 40h
0x18001ce62  mov     rbx, r8
0x18001ce65  mov     rdi, rcx
0x18001ce68  mov     r8d, 1; dwFlags
0x18001ce6e  call    cs:__imp_CreateSymbolicLinkW
0x18001ce75  nop     dword ptr [rax+rax+00h]
0x18001ce7a  test    al, al
0x18001ce7c  jnz     short loc_18001CE99
0x18001ce7e  mov     rcx, [rsp+48h]; this
0x18001ce83  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ce8a  mov     edx, 0A1h; void *
0x18001ce8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ce94  jmp     loc_18001CF5A
0x18001ce99  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001cea2  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001ceaa  mov     [rsp+48h+dwCreationDisposition], 3; int
0x18001ceb2  xor     r9d, r9d; lpSecurityAttributes
0x18001ceb5  xor     r8d, r8d; dwShareMode
0x18001ceb8  mov     edx, 40040000h; dwDesiredAccess
0x18001cebd  mov     rcx, rdi; lpFileName
0x18001cec0  call    cs:__imp_CreateFileW
0x18001cec7  nop     dword ptr [rax+rax+00h]
0x18001cecc  mov     rdx, rax
0x18001cecf  mov     [rsp+48h+arg_18], rax
0x18001ced4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ced8  jnz     short loc_18001CEE1
0x18001ceda  mov     edx, 0A7h
0x18001cedf  jmp     short loc_18001CF37
0x18001cee1  mov     rax, [rbx]
0x18001cee4  mov     rcx, rbx
0x18001cee7  mov     rax, [rax+8]
0x18001ceeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef0  mov     ebx, eax
0x18001cef2  test    eax, eax
0x18001cef4  jns     short loc_18001CF11
0x18001cef6  mov     rcx, [rsp+48h]; this
0x18001cefb  mov     r9d, eax; char *
0x18001cefe  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001cf05  mov     edx, 0A9h; void *
0x18001cf0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf0f  jmp     short loc_18001CF4E
0x18001cf11  mov     [rsp+48h+arg_18], 0FFFFFFFFFFFFFFFFh
0x18001cf1a  mov     edx, 2006h; dwFileAttributes
0x18001cf1f  mov     rcx, rdi; lpFileName
0x18001cf22  call    cs:__imp_SetFileAttributesW
0x18001cf29  nop     dword ptr [rax+rax+00h]
0x18001cf2e  test    eax, eax
0x18001cf30  jnz     short loc_18001CF4C
0x18001cf32  mov     edx, 0B2h; void *
0x18001cf37  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001cf3e  mov     rcx, [rsp+48h]; this
0x18001cf43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cf48  mov     ebx, eax
0x18001cf4a  jmp     short loc_18001CF4E
0x18001cf4c  xor     ebx, ebx
0x18001cf4e  lea     rcx, [rsp+48h+arg_18]
0x18001cf53  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001cf58  mov     eax, ebx
0x18001cf5a  mov     rbx, [rsp+48h+arg_0]
0x18001cf5f  add     rsp, 40h
0x18001cf63  pop     rdi
0x18001cf64  retn
```
