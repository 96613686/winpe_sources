# Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource::InitializeDataGathering(IStream * *)

- ea: `0x180114180`
- end: `0x18011424a`
- name: `?InitializeDataGathering@MultivariantDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `202`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180112340`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180114180`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1801141ab`
- `XmlLite!CreateXmlWriter` at `0x1801141ab`

## string_xrefs

- `0x1801141c1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource::InitializeDataGathering(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource *this,
        struct IStream **a2)
{
  void **v2; // rdi
  HRESULT XmlWriter; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void **)((char *)this + 8);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 8);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 182;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v7);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, *a2);
  if ( XmlWriter < 0 )
  {
    v5 = 183;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v2 + 40LL))(*v2, 1, 1);
  if ( XmlWriter < 0 )
  {
    v5 = 184;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 208LL))(*v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 185;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180114180  mov     [rsp+arg_0], rbx
0x180114185  mov     [rsp+arg_8], rsi
0x18011418a  push    rdi; int
0x18011418b  sub     rsp, 20h
0x18011418f  lea     rdi, [rcx+8]
0x180114193  mov     rsi, rdx
0x180114196  mov     rcx, rdi
0x180114199  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011419e  xor     r8d, r8d; pMalloc
0x1801141a1  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1801141a8  mov     rdx, rdi; ppvObject
0x1801141ab  call    cs:__imp_CreateXmlWriter
0x1801141b1  mov     ebx, eax
0x1801141b3  test    eax, eax
0x1801141b5  jns     short loc_1801141D4
0x1801141b7  mov     edx, 0B6h; void *
0x1801141bc  mov     rcx, [rsp+28h]; this
0x1801141c1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801141c8  mov     r9d, ebx; char *
0x1801141cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801141d0  mov     eax, ebx
0x1801141d2  jmp     short loc_18011423A
0x1801141d4  mov     rcx, [rdi]
0x1801141d7  mov     rdx, [rsi]
0x1801141da  mov     rax, [rcx]
0x1801141dd  mov     rax, [rax+18h]
0x1801141e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801141e6  mov     ebx, eax
0x1801141e8  test    eax, eax
0x1801141ea  jns     short loc_1801141F3
0x1801141ec  mov     edx, 0B7h
0x1801141f1  jmp     short loc_1801141BC
0x1801141f3  mov     rcx, [rdi]
0x1801141f6  mov     edx, 1
0x1801141fb  mov     r8d, edx
0x1801141fe  mov     rax, [rcx]
0x180114201  mov     rax, [rax+28h]
0x180114205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011420a  mov     ebx, eax
0x18011420c  test    eax, eax
0x18011420e  jns     short loc_180114217
0x180114210  mov     edx, 0B8h
0x180114215  jmp     short loc_1801141BC
0x180114217  mov     rcx, [rdi]
0x18011421a  xor     edx, edx
0x18011421c  mov     rax, [rcx]
0x18011421f  mov     rax, [rax+0D0h]
0x180114226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011422b  mov     ebx, eax
0x18011422d  test    eax, eax
0x18011422f  jns     short loc_180114238
0x180114231  mov     edx, 0B9h
0x180114236  jmp     short loc_1801141BC
0x180114238  xor     eax, eax
0x18011423a  mov     rbx, [rsp+28h+arg_0]
0x18011423f  mov     rsi, [rsp+28h+arg_8]
0x180114244  add     rsp, 20h
0x180114248  pop     rdi
0x180114249  retn
```
