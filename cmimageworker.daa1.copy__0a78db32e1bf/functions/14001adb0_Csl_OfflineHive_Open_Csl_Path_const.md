# Csl::OfflineHive::Open(Csl::Path const &)

- ea: `0x14001adb0`
- end: `0x14001ae42`
- name: `?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z`
- size: `146`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const struct Path *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140019e40`
- `0x14001b938`
- `0x14001d310`

## callees

- `0x140006fc4`
- `0x14001adb0`
- `0x140022834`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ae28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ae28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001ade6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001ade6`

## string_xrefs

- `0x14001ae00`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::Open(Csl::OfflineHive *this, LPCWSTR *a2)
{
  HANDLE FileW; // rax
  bool v4; // r8
  const char *v5; // r9
  void *v6; // rbx
  unsigned int v7; // edi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = CreateFileW(*a2, 1u, 0, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x6E,
                           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                           v5);
  }
  else
  {
    v7 = Csl::OfflineHive::Open(this, FileW, v4);
    if ( v6 )
      CloseHandle(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x14001adb0  mov     [rsp+arg_0], rbx
0x14001adb5  push    rdi
0x14001adb6  sub     rsp, 40h
0x14001adba  mov     rax, rdx
0x14001adbd  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14001adc6  xor     r9d, r9d; lpSecurityAttributes
0x14001adc9  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14001add1  mov     rdi, rcx
0x14001add4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14001addc  xor     r8d, r8d; dwShareMode
0x14001addf  mov     rcx, [rax]; lpFileName
0x14001ade2  lea     edx, [r9+1]; dwDesiredAccess
0x14001ade6  call    cs:__imp_CreateFileW
0x14001aded  nop     dword ptr [rax+rax+00h]
0x14001adf2  mov     rbx, rax
0x14001adf5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001adf9  jnz     short loc_14001AE13
0x14001adfb  mov     rcx, [rsp+48h]; this
0x14001ae00  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14001ae07  lea     edx, [rax+6Fh]; void *
0x14001ae0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001ae0f  mov     edi, eax
0x14001ae11  jmp     short loc_14001AE34
0x14001ae13  mov     rdx, rbx; void *
0x14001ae16  mov     rcx, rdi; this
0x14001ae19  call    ?Open@OfflineHive@Csl@@QEAAJPEAX_N@Z; Csl::OfflineHive::Open(void *,bool)
0x14001ae1e  mov     edi, eax
0x14001ae20  test    rbx, rbx
0x14001ae23  jz      short loc_14001AE34
0x14001ae25  mov     rcx, rbx; hObject
0x14001ae28  call    cs:__imp_CloseHandle
0x14001ae2f  nop     dword ptr [rax+rax+00h]
0x14001ae34  mov     rbx, [rsp+48h+arg_0]
0x14001ae39  mov     eax, edi
0x14001ae3b  add     rsp, 40h
0x14001ae3f  pop     rdi
0x14001ae40  retn
```
