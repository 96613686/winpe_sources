# Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData::InitializeReportGeneration(void)

- ea: `0x180122690`
- end: `0x180122771`
- name: `?InitializeReportGeneration@RegistryDiagnosticData@MDMDiagnostics@MDM@Windows@Microsoft@@UEAAJXZ`
- size: `225`
- prototype: `int(Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180122690`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1801226bb`
- `XmlLite!CreateXmlWriter` at `0x1801226bb`

## string_xrefs

- `0x1801226d1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\registrydiagnosticdata.cpp`
- `0x180122747`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\registrydiagnosticdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData::InitializeReportGeneration(
        Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData *this)
{
  void **v1; // rbx
  HRESULT XmlWriter; // edi
  __int64 v4; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void **)((char *)this + 48);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 48);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, v1, 0);
  if ( XmlWriter < 0 )
  {
    v4 = 55;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\registrydiagnosticdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v8);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v1 + 24LL))(*v1, *((_QWORD *)this + 5));
  if ( XmlWriter < 0 )
  {
    v4 = 56;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v1 + 40LL))(*v1, 1, 1);
  if ( XmlWriter < 0 )
  {
    v4 = 57;
    goto LABEL_3;
  }
  v6 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v1 + 208LL))(*v1, 0);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\registrydiagnosticdata.cpp",
    (const char *)(unsigned int)v6,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180122690  mov     [rsp+arg_0], rbx
0x180122695  mov     [rsp+arg_8], rsi
0x18012269a  push    rdi; int
0x18012269b  sub     rsp, 20h
0x18012269f  lea     rbx, [rcx+30h]
0x1801226a3  mov     rsi, rcx
0x1801226a6  mov     rcx, rbx
0x1801226a9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801226ae  xor     r8d, r8d; pMalloc
0x1801226b1  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1801226b8  mov     rdx, rbx; ppvObject
0x1801226bb  call    cs:__imp_CreateXmlWriter
0x1801226c1  mov     edi, eax
0x1801226c3  test    eax, eax
0x1801226c5  jns     short loc_1801226E4
0x1801226c7  mov     edx, 37h ; '7'; void *
0x1801226cc  mov     rcx, [rsp+28h]; this
0x1801226d1  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801226d8  mov     r9d, edi; char *
0x1801226db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801226e0  mov     eax, edi
0x1801226e2  jmp     short loc_180122761
0x1801226e4  mov     rcx, [rbx]
0x1801226e7  mov     rdx, [rsi+28h]
0x1801226eb  mov     rax, [rcx]
0x1801226ee  mov     rax, [rax+18h]
0x1801226f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801226f7  mov     edi, eax
0x1801226f9  test    eax, eax
0x1801226fb  jns     short loc_180122704
0x1801226fd  mov     edx, 38h ; '8'
0x180122702  jmp     short loc_1801226CC
0x180122704  mov     rcx, [rbx]
0x180122707  mov     edx, 1
0x18012270c  mov     r8d, edx
0x18012270f  mov     rax, [rcx]
0x180122712  mov     rax, [rax+28h]
0x180122716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012271b  mov     edi, eax
0x18012271d  test    eax, eax
0x18012271f  jns     short loc_180122728
0x180122721  mov     edx, 39h ; '9'
0x180122726  jmp     short loc_1801226CC
0x180122728  mov     rcx, [rbx]
0x18012272b  xor     edx, edx
0x18012272d  mov     rax, [rcx]
0x180122730  mov     rax, [rax+0D0h]
0x180122737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012273c  mov     ebx, eax
0x18012273e  test    eax, eax
0x180122740  jns     short loc_18012275F
0x180122742  mov     rcx, [rsp+28h]; this
0x180122747  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012274e  mov     r9d, eax; char *
0x180122751  mov     edx, 3Ah ; ':'; void *
0x180122756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012275b  mov     eax, ebx
0x18012275d  jmp     short loc_180122761
0x18012275f  xor     eax, eax
0x180122761  mov     rbx, [rsp+28h+arg_0]
0x180122766  mov     rsi, [rsp+28h+arg_8]
0x18012276b  add     rsp, 20h
0x18012276f  pop     rdi
0x180122770  retn
```
