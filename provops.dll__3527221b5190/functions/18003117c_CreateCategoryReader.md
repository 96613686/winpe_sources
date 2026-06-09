# CreateCategoryReader

- ea: `0x18003117c`
- end: `0x1800312db`
- name: `CreateCategoryReader`
- size: `351`
- prototype: `__int64 __fastcall(void **ppvObject, LPCWSTR pszFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180031a34`

## callees

- `0x1800017ec`
- `0x18001b388`
- `0x18003117c`
- `0x180037010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x1800311b4`
- `XmlLite!CreateXmlReader` at `0x1800311b4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180031229`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180031229`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall CreateCategoryReader(void **ppvObject, LPCWSTR pszFile)
{
  HRESULT XmlReader; // eax
  int v5; // eax
  __int64 v6; // r9
  HRESULT v7; // eax
  int v8; // eax
  IStream *v9; // rcx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IStream *ppstm; // [rsp+60h] [rbp+18h] BYREF
  LPCWSTR v14; // [rsp+68h] [rbp+20h] BYREF

  *ppvObject = 0;
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)XmlReader,
      v11);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v5,
      v11);
  if ( *(_DWORD *)g_hProvTraceProvider > 5u )
  {
    v14 = pszFile;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      g_hProvTraceProvider,
      (__int64)byte_180041D85,
      0,
      v6,
      &v14);
  }
  ppstm = 0;
  v7 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v7,
      v11);
  v8 = (*(__int64 (__fastcall **)(_QWORD, IStream *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppstm);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return ppvObject;
}

```

## disassembly

```asm
0x18003117c  mov     rax, rsp
0x18003117f  mov     [rax+10h], rbx
0x180031183  mov     [rax+8], rcx
0x180031187  push    rdi
0x180031188  sub     rsp, 40h
0x18003118c  mov     rdi, rdx
0x18003118f  mov     rbx, rcx
0x180031192  mov     dword ptr [rax-18h], 0
0x180031199  mov     qword ptr [rcx], 0
0x1800311a0  mov     dword ptr [rax-18h], 1
0x1800311a7  xor     r8d, r8d; pMalloc
0x1800311aa  mov     rdx, rcx; ppvObject
0x1800311ad  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800311b4  call    cs:__imp_CreateXmlReader
0x1800311ba  mov     rcx, [rsp+48h]; this
0x1800311bf  test    eax, eax
0x1800311c1  js      loc_18003129C
0x1800311c7  mov     rcx, [rbx]
0x1800311ca  mov     rax, [rcx]
0x1800311cd  xor     r8d, r8d
0x1800311d0  lea     edx, [r8+4]
0x1800311d4  mov     rax, [rax+28h]
0x1800311d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311dd  mov     rcx, [rsp+48h]; this
0x1800311e2  test    eax, eax
0x1800311e4  js      loc_1800312B1
0x1800311ea  mov     rcx, cs:g_hProvTraceProvider
0x1800311f1  mov     eax, [rcx]
0x1800311f3  cmp     eax, 5
0x1800311f6  jbe     short loc_180031216
0x1800311f8  mov     [rsp+48h+arg_18], rdi
0x1800311fd  lea     rax, [rsp+48h+arg_18]
0x180031202  mov     qword ptr [rsp+48h+var_28], rax; int
0x180031207  xor     r8d, r8d
0x18003120a  lea     rdx, byte_180041D85
0x180031211  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180031216  mov     [rsp+48h+ppstm], 0
0x18003121f  lea     r8, [rsp+48h+ppstm]; ppstm
0x180031224  xor     edx, edx; grfMode
0x180031226  mov     rcx, rdi; pszFile
0x180031229  call    cs:__imp_SHCreateStreamOnFileW
0x18003122f  mov     rcx, [rsp+48h]; this
0x180031234  test    eax, eax
0x180031236  js      loc_1800312C6
0x18003123c  mov     rcx, [rbx]
0x18003123f  mov     rax, [rcx]
0x180031242  mov     rdx, [rsp+48h+ppstm]
0x180031247  mov     rax, [rax+18h]
0x18003124b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031250  mov     rcx, [rsp+48h]; this
0x180031255  test    eax, eax
0x180031257  js      short loc_180031287
0x180031259  mov     rcx, [rsp+48h+ppstm]
0x18003125e  test    rcx, rcx
0x180031261  jz      short loc_180031279
0x180031263  mov     [rsp+48h+ppstm], 0
0x18003126c  mov     rax, [rcx]
0x18003126f  mov     rax, [rax+10h]
0x180031273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031278  nop
0x180031279  mov     rax, rbx
0x18003127c  mov     rbx, [rsp+48h+arg_8]
0x180031281  add     rsp, 40h
0x180031285  pop     rdi
0x180031286  retn
0x180031287  mov     r9d, eax; char *
0x18003128a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031291  mov     edx, 2Fh ; '/'; void *
0x180031296  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003129c  mov     r9d, eax; char *
0x18003129f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800312a6  mov     edx, 23h ; '#'; void *
0x1800312ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800312b1  mov     r9d, eax; char *
0x1800312b4  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800312bb  mov     edx, 24h ; '$'; void *
0x1800312c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800312c6  mov     r9d, eax; char *
0x1800312c9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800312d0  mov     edx, 2Eh ; '.'; void *
0x1800312d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
