# CXMLFile::Open(ushort const *,_GUID const &)

- ea: `0x18006a9b8`
- end: `0x18006aa85`
- name: `?Open@CXMLFile@@QEAAJPEBGAEBU_GUID@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(struct IUnknown **this, STRSAFE_PCNZWCH pszSrc, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057510`

## callees

- `0x180007de0`
- `0x18000b098`
- `0x18006a748`
- `0x18006a80c`
- `0x18006a9b8`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18006aa08`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18006aa08`

## string_xrefs

- `0x18006aa2c`: `onecoreuap\shell\lib\stockatl\xml.cpp`
- `0x18006aa64`: `onecoreuap\shell\lib\stockatl\xml.cpp`

## pseudocode

```c
__int64 __fastcall CXMLFile::Open(struct IUnknown **this, STRSAFE_PCNZWCH pszSrc, struct _GUID *a3)
{
  HRESULT v5; // ebx
  const struct _GUID *v6; // r8
  int v7; // eax
  size_t v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  IStream *ppstm; // [rsp+50h] [rbp+18h] BYREF

  ppstm = (IStream *)a3;
  if ( !pszSrc )
    return 2147942487LL;
  v5 = StringCopyWorkerW((STRSAFE_LPWSTR)this + 12, 0x104u, (size_t *)&a3->Data1, pszSrc, v8);
  if ( v5 >= 0 )
  {
    ppstm = 0;
    v5 = SHCreateStreamOnFileW((LPCWSTR)this + 12, 0, &ppstm);
    if ( v5 >= 0 )
    {
      v7 = CXMLDOMNode::CreateFromStream(this, ppstm, v6);
      v5 = v7;
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D9,
          (unsigned int)"onecoreuap\\shell\\lib\\stockatl\\xml.cpp",
          (const char *)(unsigned int)v7,
          v9);
    }
    ATL::CComQIPtr<IPersistStream,&__s_GUID const _GUID_00000109_0000_0000_c000_000000000046>::~CComQIPtr<IPersistStream,&__s_GUID const _GUID_00000109_0000_0000_c000_000000000046>(&ppstm);
    if ( v5 <= -2147024895 || (unsigned int)(v5 + 2147024892) <= 0x7FF8FFFB )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3DB,
        (unsigned int)"onecoreuap\\shell\\lib\\stockatl\\xml.cpp",
        (const char *)(unsigned int)v5,
        v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006a9b8  mov     [rsp+arg_0], rbx
0x18006a9bd  mov     [rsp+ppstm], r8
0x18006a9c2  push    rdi
0x18006a9c3  sub     rsp, 30h
0x18006a9c7  mov     rdi, rcx
0x18006a9ca  test    rdx, rdx
0x18006a9cd  jnz     short loc_18006A9D9
0x18006a9cf  mov     eax, 80070057h
0x18006a9d4  jmp     loc_18006AA7A
0x18006a9d9  mov     r9, rdx; pszSrc
0x18006a9dc  add     rcx, 18h; pszDest
0x18006a9e0  mov     edx, 104h; cchDest
0x18006a9e5  call    StringCopyWorkerW
0x18006a9ea  mov     ebx, eax
0x18006a9ec  test    eax, eax
0x18006a9ee  js      loc_18006AA78
0x18006a9f4  lea     r8, [rsp+38h+ppstm]; ppstm
0x18006a9f9  mov     [rsp+38h+ppstm], 0
0x18006aa02  xor     edx, edx; grfMode
0x18006aa04  lea     rcx, [rdi+18h]; pszFile
0x18006aa08  call    cs:__imp_SHCreateStreamOnFileW
0x18006aa0e  mov     ebx, eax
0x18006aa10  test    eax, eax
0x18006aa12  js      short loc_18006AA40
0x18006aa14  mov     rdx, [rsp+38h+ppstm]; struct IStream *
0x18006aa19  mov     rcx, rdi; this
0x18006aa1c  call    ?CreateFromStream@CXMLDOMNode@@QEAAJPEAUIStream@@AEBU_GUID@@@Z; CXMLDOMNode::CreateFromStream(IStream *,_GUID const &)
0x18006aa21  mov     ebx, eax
0x18006aa23  test    eax, eax
0x18006aa25  jns     short loc_18006AA40
0x18006aa27  mov     rcx, [rsp+38h]; this
0x18006aa2c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\stockatl\\xml.c"...
0x18006aa33  mov     r9d, eax; char *
0x18006aa36  mov     edx, 2D9h; void *
0x18006aa3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006aa40  lea     rcx, [rsp+38h+ppstm]
0x18006aa45  call    ??1?$CComQIPtr@UIPersistStream@@$1?_GUID_00000109_0000_0000_c000_000000000046@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IPersistStream,&__s_GUID const _GUID_00000109_0000_0000_c000_000000000046>::~CComQIPtr<IPersistStream,&__s_GUID const _GUID_00000109_0000_0000_c000_000000000046>(void)
0x18006aa4a  cmp     ebx, 80070001h
0x18006aa50  jle     short loc_18006AA5F
0x18006aa52  lea     eax, [rbx+7FF8FFFCh]
0x18006aa58  cmp     eax, 7FF8FFFBh
0x18006aa5d  ja      short loc_18006AA78
0x18006aa5f  mov     rcx, [rsp+38h]; this
0x18006aa64  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\stockatl\\xml.c"...
0x18006aa6b  mov     r9d, ebx; char *
0x18006aa6e  mov     edx, 3DBh; void *
0x18006aa73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006aa78  mov     eax, ebx
0x18006aa7a  mov     rbx, [rsp+38h+arg_0]
0x18006aa7f  add     rsp, 30h
0x18006aa83  pop     rdi
0x18006aa84  retn
```
