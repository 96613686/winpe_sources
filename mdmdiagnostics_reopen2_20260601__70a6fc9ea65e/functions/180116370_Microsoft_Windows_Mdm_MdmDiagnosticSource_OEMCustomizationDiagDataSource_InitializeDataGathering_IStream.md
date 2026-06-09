# Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::InitializeDataGathering(IStream * *)

- ea: `0x180116370`
- end: `0x180116441`
- name: `?InitializeDataGathering@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `209`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180115d00`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180116370`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18011639b`
- `XmlLite!CreateXmlWriter` at `0x18011639b`

## string_xrefs

- `0x1801163b7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::InitializeDataGathering(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *this,
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
    v5 = 100;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v7);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, *a2);
  if ( XmlWriter < 0 )
  {
    v5 = 101;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v2 + 40LL))(*v2, 1, 1);
  if ( XmlWriter < 0 )
  {
    v5 = 102;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 208LL))(*v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 103;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180116370  mov     [rsp+arg_0], rbx
0x180116375  mov     [rsp+arg_8], rsi
0x18011637a  push    rdi; int
0x18011637b  sub     rsp, 20h
0x18011637f  lea     rdi, [rcx+8]
0x180116383  mov     rsi, rdx
0x180116386  mov     rcx, rdi
0x180116389  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011638e  xor     r8d, r8d; pMalloc
0x180116391  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180116398  mov     rdx, rdi; ppvObject
0x18011639b  call    cs:__imp_CreateXmlWriter
0x1801163a2  nop     dword ptr [rax+rax+00h]
0x1801163a7  mov     ebx, eax
0x1801163a9  test    eax, eax
0x1801163ab  jns     short loc_1801163CA
0x1801163ad  mov     edx, 64h ; 'd'; void *
0x1801163b2  mov     rcx, [rsp+28h]; this
0x1801163b7  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801163be  mov     r9d, ebx; char *
0x1801163c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801163c6  mov     eax, ebx
0x1801163c8  jmp     short loc_180116430
0x1801163ca  mov     rcx, [rdi]
0x1801163cd  mov     rdx, [rsi]
0x1801163d0  mov     rax, [rcx]
0x1801163d3  mov     rax, [rax+18h]
0x1801163d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801163dc  mov     ebx, eax
0x1801163de  test    eax, eax
0x1801163e0  jns     short loc_1801163E9
0x1801163e2  mov     edx, 65h ; 'e'
0x1801163e7  jmp     short loc_1801163B2
0x1801163e9  mov     rcx, [rdi]
0x1801163ec  mov     edx, 1
0x1801163f1  mov     r8d, edx
0x1801163f4  mov     rax, [rcx]
0x1801163f7  mov     rax, [rax+28h]
0x1801163fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116400  mov     ebx, eax
0x180116402  test    eax, eax
0x180116404  jns     short loc_18011640D
0x180116406  mov     edx, 66h ; 'f'
0x18011640b  jmp     short loc_1801163B2
0x18011640d  mov     rcx, [rdi]
0x180116410  xor     edx, edx
0x180116412  mov     rax, [rcx]
0x180116415  mov     rax, [rax+0D0h]
0x18011641c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116421  mov     ebx, eax
0x180116423  test    eax, eax
0x180116425  jns     short loc_18011642E
0x180116427  mov     edx, 67h ; 'g'
0x18011642c  jmp     short loc_1801163B2
0x18011642e  xor     eax, eax
0x180116430  mov     rbx, [rsp+28h+arg_0]
0x180116435  mov     rsi, [rsp+28h+arg_8]
0x18011643a  add     rsp, 20h
0x18011643e  pop     rdi
0x18011643f  retn
```
