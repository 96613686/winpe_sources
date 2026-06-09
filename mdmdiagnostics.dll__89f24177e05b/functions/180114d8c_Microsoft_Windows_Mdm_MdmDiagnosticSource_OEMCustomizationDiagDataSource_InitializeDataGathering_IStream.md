# Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::InitializeDataGathering(IStream * *)

- ea: `0x180114d8c`
- end: `0x180114e56`
- name: `?InitializeDataGathering@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `202`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180114750`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180114d8c`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180114db7`
- `XmlLite!CreateXmlWriter` at `0x180114db7`

## string_xrefs

- `0x180114dcd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`

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
0x180114d8c  mov     [rsp+arg_0], rbx
0x180114d91  mov     [rsp+arg_8], rsi
0x180114d96  push    rdi; int
0x180114d97  sub     rsp, 20h
0x180114d9b  lea     rdi, [rcx+8]
0x180114d9f  mov     rsi, rdx
0x180114da2  mov     rcx, rdi
0x180114da5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180114daa  xor     r8d, r8d; pMalloc
0x180114dad  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180114db4  mov     rdx, rdi; ppvObject
0x180114db7  call    cs:__imp_CreateXmlWriter
0x180114dbd  mov     ebx, eax
0x180114dbf  test    eax, eax
0x180114dc1  jns     short loc_180114DE0
0x180114dc3  mov     edx, 64h ; 'd'; void *
0x180114dc8  mov     rcx, [rsp+28h]; this
0x180114dcd  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114dd4  mov     r9d, ebx; char *
0x180114dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114ddc  mov     eax, ebx
0x180114dde  jmp     short loc_180114E46
0x180114de0  mov     rcx, [rdi]
0x180114de3  mov     rdx, [rsi]
0x180114de6  mov     rax, [rcx]
0x180114de9  mov     rax, [rax+18h]
0x180114ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114df2  mov     ebx, eax
0x180114df4  test    eax, eax
0x180114df6  jns     short loc_180114DFF
0x180114df8  mov     edx, 65h ; 'e'
0x180114dfd  jmp     short loc_180114DC8
0x180114dff  mov     rcx, [rdi]
0x180114e02  mov     edx, 1
0x180114e07  mov     r8d, edx
0x180114e0a  mov     rax, [rcx]
0x180114e0d  mov     rax, [rax+28h]
0x180114e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e16  mov     ebx, eax
0x180114e18  test    eax, eax
0x180114e1a  jns     short loc_180114E23
0x180114e1c  mov     edx, 66h ; 'f'
0x180114e21  jmp     short loc_180114DC8
0x180114e23  mov     rcx, [rdi]
0x180114e26  xor     edx, edx
0x180114e28  mov     rax, [rcx]
0x180114e2b  mov     rax, [rax+0D0h]
0x180114e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e37  mov     ebx, eax
0x180114e39  test    eax, eax
0x180114e3b  jns     short loc_180114E44
0x180114e3d  mov     edx, 67h ; 'g'
0x180114e42  jmp     short loc_180114DC8
0x180114e44  xor     eax, eax
0x180114e46  mov     rbx, [rsp+28h+arg_0]
0x180114e4b  mov     rsi, [rsp+28h+arg_8]
0x180114e50  add     rsp, 20h
0x180114e54  pop     rdi
0x180114e55  retn
```
