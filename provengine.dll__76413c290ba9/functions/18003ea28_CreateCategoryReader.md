# CreateCategoryReader

- ea: `0x18003ea28`
- end: `0x18003eb8b`
- name: `CreateCategoryReader`
- size: `355`
- prototype: `__int64 __fastcall(void **ppvObject, LPCWSTR pszFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003f334`

## callees

- `0x1800011ac`
- `0x180021cf4`
- `0x18003ea28`
- `0x180047010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18003ea60`
- `XmlLite!CreateXmlReader` at `0x18003ea60`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18003ead9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18003ead9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall CreateCategoryReader(void **ppvObject, __int64 *pszFile)
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
  __int64 *v14; // [rsp+68h] [rbp+20h] BYREF

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
  if ( (unsigned int)dword_18005A000 > 5 )
  {
    v14 = pszFile;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)byte_18005059B,
      0,
      v6,
      &v14);
  }
  ppstm = 0;
  v7 = SHCreateStreamOnFileW((LPCWSTR)pszFile, 0, &ppstm);
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
0x18003ea28  mov     rax, rsp
0x18003ea2b  mov     [rax+10h], rbx
0x18003ea2f  mov     [rax+8], rcx
0x18003ea33  push    rdi
0x18003ea34  sub     rsp, 40h
0x18003ea38  mov     rdi, rdx
0x18003ea3b  mov     rbx, rcx
0x18003ea3e  mov     dword ptr [rax-18h], 0
0x18003ea45  mov     qword ptr [rcx], 0
0x18003ea4c  mov     dword ptr [rax-18h], 1
0x18003ea53  xor     r8d, r8d; pMalloc
0x18003ea56  mov     rdx, rcx; ppvObject
0x18003ea59  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18003ea60  call    cs:__imp_CreateXmlReader
0x18003ea66  mov     rcx, [rsp+48h]; this
0x18003ea6b  test    eax, eax
0x18003ea6d  js      loc_18003EB4C
0x18003ea73  mov     rcx, [rbx]
0x18003ea76  mov     rax, [rcx]
0x18003ea79  xor     r8d, r8d
0x18003ea7c  lea     edx, [r8+4]
0x18003ea80  mov     rax, [rax+28h]
0x18003ea84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea89  mov     rcx, [rsp+48h]; this
0x18003ea8e  test    eax, eax
0x18003ea90  js      loc_18003EB61
0x18003ea96  mov     eax, cs:dword_18005A000
0x18003ea9c  cmp     eax, 5
0x18003ea9f  jbe     short loc_18003EAC6
0x18003eaa1  mov     [rsp+48h+arg_18], rdi
0x18003eaa6  lea     rax, [rsp+48h+arg_18]
0x18003eaab  mov     qword ptr [rsp+48h+var_28], rax; int
0x18003eab0  xor     r8d, r8d
0x18003eab3  lea     rdx, byte_18005059B
0x18003eaba  lea     rcx, dword_18005A000
0x18003eac1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003eac6  mov     [rsp+48h+ppstm], 0
0x18003eacf  lea     r8, [rsp+48h+ppstm]; ppstm
0x18003ead4  xor     edx, edx; grfMode
0x18003ead6  mov     rcx, rdi; pszFile
0x18003ead9  call    cs:__imp_SHCreateStreamOnFileW
0x18003eadf  mov     rcx, [rsp+48h]; this
0x18003eae4  test    eax, eax
0x18003eae6  js      loc_18003EB76
0x18003eaec  mov     rcx, [rbx]
0x18003eaef  mov     rax, [rcx]
0x18003eaf2  mov     rdx, [rsp+48h+ppstm]
0x18003eaf7  mov     rax, [rax+18h]
0x18003eafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb00  mov     rcx, [rsp+48h]; this
0x18003eb05  test    eax, eax
0x18003eb07  js      short loc_18003EB37
0x18003eb09  mov     rcx, [rsp+48h+ppstm]
0x18003eb0e  test    rcx, rcx
0x18003eb11  jz      short loc_18003EB29
0x18003eb13  mov     [rsp+48h+ppstm], 0
0x18003eb1c  mov     rax, [rcx]
0x18003eb1f  mov     rax, [rax+10h]
0x18003eb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb28  nop
0x18003eb29  mov     rax, rbx
0x18003eb2c  mov     rbx, [rsp+48h+arg_8]
0x18003eb31  add     rsp, 40h
0x18003eb35  pop     rdi
0x18003eb36  retn
0x18003eb37  mov     r9d, eax; char *
0x18003eb3a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003eb41  mov     edx, 2Fh ; '/'; void *
0x18003eb46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003eb4c  mov     r9d, eax; char *
0x18003eb4f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003eb56  mov     edx, 23h ; '#'; void *
0x18003eb5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003eb61  mov     r9d, eax; char *
0x18003eb64  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003eb6b  mov     edx, 24h ; '$'; void *
0x18003eb70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003eb76  mov     r9d, eax; char *
0x18003eb79  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003eb80  mov     edx, 2Eh ; '.'; void *
0x18003eb85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
