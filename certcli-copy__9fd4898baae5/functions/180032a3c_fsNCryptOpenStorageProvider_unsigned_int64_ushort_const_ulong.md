# fsNCryptOpenStorageProvider(unsigned __int64 *,ushort const *,ulong)

- ea: `0x180032a3c`
- end: `0x180032a9a`
- name: `?fsNCryptOpenStorageProvider@@YAJPEA_KPEBGK@Z`
- size: `94`
- prototype: `__int64 __fastcall(unsigned __int64 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800318cc`

## callees

- `0x180032a3c`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180032a61`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180032a61`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032a87`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032a87`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180032a7a`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180032a7a`
- `ncrypt!NCryptOpenStorageProvider` at `0x180032a50`
- `ncrypt!NCryptOpenStorageProvider` at `0x180032a50`

## pseudocode

```c
__int64 __fastcall fsNCryptOpenStorageProvider(unsigned __int64 *a1, const unsigned __int16 *a2, DWORD a3)
{
  unsigned int v4; // ebx

  v4 = NCryptOpenStorageProvider(a1, L"Microsoft Software Key Storage Provider", a3);
  if ( v4 || DbgIsSSActive(0x404u) )
  {
    CSPrintErrorLineFileData(L"Microsoft Software Key Storage Provider", 0x5AF0C25u, v4);
    CSPrintErrorLineFile(0x5B00C25u, a3);
  }
  return v4;
}

```

## disassembly

```asm
0x180032a3c  mov     [rsp+arg_0], rbx
0x180032a41  push    rdi
0x180032a42  sub     rsp, 20h
0x180032a46  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180032a4d  mov     edi, r8d
0x180032a50  call    cs:__imp_NCryptOpenStorageProvider
0x180032a56  mov     ebx, eax
0x180032a58  test    eax, eax
0x180032a5a  jnz     short loc_180032A6B
0x180032a5c  mov     ecx, 404h
0x180032a61  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180032a67  test    eax, eax
0x180032a69  jz      short loc_180032A8D
0x180032a6b  mov     r8d, ebx
0x180032a6e  lea     rcx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180032a75  mov     edx, 5AF0C25h
0x180032a7a  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180032a80  mov     edx, edi
0x180032a82  mov     ecx, 5B00C25h
0x180032a87  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032a8d  mov     eax, ebx
0x180032a8f  mov     rbx, [rsp+28h+arg_0]
0x180032a94  add     rsp, 20h
0x180032a98  pop     rdi
0x180032a99  retn
```
