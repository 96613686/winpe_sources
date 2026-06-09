# CFileAccessor::OplockBrokenCallback(void)

- ea: `0x180021f70`
- end: `0x180022006`
- name: `?OplockBrokenCallback@CFileAccessor@@AEAAXXZ`
- size: `150`
- prototype: `void __fastcall(CFileAccessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800223b0`

## callees

- `0x180002d00`
- `0x180004e60`
- `0x180005a50`
- `0x180020aac`
- `0x180021f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021f95`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021f95`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180021fdc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180021fdc`

## pseudocode

```c
void __fastcall CFileAccessor::OplockBrokenCallback(CFileAccessor *this)
{
  __int64 v2; // rcx
  LPWSTR ExtensionW; // rax
  LPWSTR v4; // [rsp+38h] [rbp+10h] BYREF

  if ( (unsigned int)CFileAccessor::IsOplockBroken(this)
    && WaitForSingleObjectEx(*((HANDLE *)this + 25), 0x15F90u, 0) == 258 )
  {
    v2 = *((_QWORD *)this + 27);
    if ( v2 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v2 + 24,
        -1);
      TComPointer<CFileStream>::operator=((_QWORD *)this + 27, 0);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 104,
      -1);
    ExtensionW = PathFindExtensionW(*((LPCWSTR *)this + 88));
    if ( *ExtensionW == 46 )
    {
      v4 = ExtensionW + 1;
      SearchIndexerDiagnosticTelemetry::IndexerOplockBreakTime<wchar_t const *>(&v4);
    }
  }
}

```

## disassembly

```asm
0x180021f70  mov     [rsp+arg_0], rbx
0x180021f75  push    rdi
0x180021f76  sub     rsp, 20h
0x180021f7a  mov     rbx, rcx
0x180021f7d  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x180021f82  test    eax, eax
0x180021f84  jz      short loc_180021FFB
0x180021f86  mov     rcx, [rbx+0C8h]; hHandle
0x180021f8d  xor     r8d, r8d; bAlertable
0x180021f90  mov     edx, 15F90h; dwMilliseconds
0x180021f95  call    cs:__imp_WaitForSingleObjectEx
0x180021f9b  cmp     eax, 102h
0x180021fa0  jnz     short loc_180021FFB
0x180021fa2  lea     rdi, [rbx+0D8h]
0x180021fa9  mov     rcx, [rdi]
0x180021fac  test    rcx, rcx
0x180021faf  jz      short loc_180021FC8
0x180021fb1  add     rcx, 18h
0x180021fb5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180021fb9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021fbe  xor     edx, edx
0x180021fc0  mov     rcx, rdi
0x180021fc3  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x180021fc8  lea     rcx, [rbx+68h]
0x180021fcc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180021fd0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021fd5  mov     rcx, [rbx+2C0h]; pszPath
0x180021fdc  call    cs:__imp_PathFindExtensionW
0x180021fe2  cmp     word ptr [rax], 2Eh ; '.'
0x180021fe6  jnz     short loc_180021FFB
0x180021fe8  add     rax, 2
0x180021fec  lea     rcx, [rsp+28h+arg_8]
0x180021ff1  mov     [rsp+28h+arg_8], rax
0x180021ff6  call    ??$IndexerOplockBreakTime@PEB_W@SearchIndexerDiagnosticTelemetry@@SAX$$QEAPEB_W@Z; SearchIndexerDiagnosticTelemetry::IndexerOplockBreakTime<wchar_t const *>(wchar_t const * &&)
0x180021ffb  mov     rbx, [rsp+28h+arg_0]
0x180022000  add     rsp, 20h
0x180022004  pop     rdi
0x180022005  retn
```
