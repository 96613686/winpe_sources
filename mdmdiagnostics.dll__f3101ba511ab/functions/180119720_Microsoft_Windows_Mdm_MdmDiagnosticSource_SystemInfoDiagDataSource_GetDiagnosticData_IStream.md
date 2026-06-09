# Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180119720`
- end: `0x180119881`
- name: `?GetDiagnosticData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *__hidden this, LPSTREAM *ppstm)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180119720`
- `0x180119888`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180119785`
- `XmlLite!CreateXmlWriter` at `0x180119785`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011973a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011973a`

## string_xrefs

- `0x180119756`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`
- `0x1801197a1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetDiagnosticData(
        void **this,
        LPSTREAM *ppstm)
{
  HRESULT StreamOnHGlobal; // ebx
  __int64 v5; // rdx
  _QWORD *v7; // rbx
  HRESULT XmlWriter; // edi
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\systeminfodiagdata.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v10);
    return (unsigned int)StreamOnHGlobal;
  }
  v7 = this + 1;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(this + 1);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, this + 1, 0);
  if ( XmlWriter < 0 )
  {
    v9 = 115;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\systeminfodiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v10);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 24LL))(*v7, *ppstm);
  if ( XmlWriter < 0 )
  {
    v9 = 116;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v7 + 40LL))(*v7, 1, 1);
  if ( XmlWriter < 0 )
  {
    v9 = 117;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 208LL))(*v7, 0);
  if ( XmlWriter < 0 )
  {
    v9 = 118;
    goto LABEL_6;
  }
  XmlWriter = Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData((Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *)this);
  if ( XmlWriter < 0 )
  {
    v9 = 120;
    goto LABEL_6;
  }
  XmlWriter = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 112LL))(*v7);
  if ( XmlWriter < 0 )
  {
    v9 = 122;
    goto LABEL_6;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 248LL))(*v7);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 123;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180119720  push    rbx
0x180119722  push    rsi
0x180119723  push    rdi
0x180119724  push    r14
0x180119726  sub     rsp, 28h
0x18011972a  mov     r14, rdx
0x18011972d  mov     rsi, rcx
0x180119730  mov     r8, rdx; ppstm
0x180119733  xor     ecx, ecx; hGlobal
0x180119735  mov     edx, 1; fDeleteOnRelease
0x18011973a  call    cs:__imp_CreateStreamOnHGlobal
0x180119741  nop     dword ptr [rax+rax+00h]
0x180119746  mov     ebx, eax
0x180119748  test    eax, eax
0x18011974a  jns     short loc_18011976C
0x18011974c  mov     edx, 72h ; 'r'; void *
0x180119751  mov     rcx, [rsp+48h]; this
0x180119756  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011975d  mov     r9d, ebx; char *
0x180119760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119765  mov     eax, ebx
0x180119767  jmp     loc_180119876
0x18011976c  lea     rbx, [rsi+8]
0x180119770  mov     rcx, rbx
0x180119773  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119778  xor     r8d, r8d; pMalloc
0x18011977b  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180119782  mov     rdx, rbx; ppvObject
0x180119785  call    cs:__imp_CreateXmlWriter
0x18011978c  nop     dword ptr [rax+rax+00h]
0x180119791  mov     edi, eax
0x180119793  test    eax, eax
0x180119795  jns     short loc_1801197B7
0x180119797  mov     edx, 73h ; 's'; void *
0x18011979c  mov     rcx, [rsp+48h]; this
0x1801197a1  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801197a8  mov     r9d, edi; char *
0x1801197ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801197b0  mov     eax, edi
0x1801197b2  jmp     loc_180119876
0x1801197b7  mov     rcx, [rbx]
0x1801197ba  mov     rdx, [r14]
0x1801197bd  mov     rax, [rcx]
0x1801197c0  mov     rax, [rax+18h]
0x1801197c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801197c9  mov     edi, eax
0x1801197cb  test    eax, eax
0x1801197cd  jns     short loc_1801197D6
0x1801197cf  mov     edx, 74h ; 't'
0x1801197d4  jmp     short loc_18011979C
0x1801197d6  mov     rcx, [rbx]
0x1801197d9  mov     edx, 1
0x1801197de  mov     r8d, edx
0x1801197e1  mov     rax, [rcx]
0x1801197e4  mov     rax, [rax+28h]
0x1801197e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801197ed  mov     edi, eax
0x1801197ef  test    eax, eax
0x1801197f1  jns     short loc_1801197FA
0x1801197f3  mov     edx, 75h ; 'u'
0x1801197f8  jmp     short loc_18011979C
0x1801197fa  mov     rcx, [rbx]
0x1801197fd  xor     edx, edx
0x1801197ff  mov     rax, [rcx]
0x180119802  mov     rax, [rax+0D0h]
0x180119809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011980e  mov     edi, eax
0x180119810  test    eax, eax
0x180119812  jns     short loc_18011981B
0x180119814  mov     edx, 76h ; 'v'
0x180119819  jmp     short loc_18011979C
0x18011981b  mov     rcx, rsi; this
0x18011981e  call    ?GetSystemInformationData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData(void)
0x180119823  mov     edi, eax
0x180119825  test    eax, eax
0x180119827  jns     short loc_180119833
0x180119829  mov     edx, 78h ; 'x'
0x18011982e  jmp     loc_18011979C
0x180119833  mov     rcx, [rbx]
0x180119836  mov     rax, [rcx]
0x180119839  mov     rax, [rax+70h]
0x18011983d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119842  mov     edi, eax
0x180119844  test    eax, eax
0x180119846  jns     short loc_180119852
0x180119848  mov     edx, 7Ah ; 'z'
0x18011984d  jmp     loc_18011979C
0x180119852  mov     rcx, [rbx]
0x180119855  mov     rax, [rcx]
0x180119858  mov     rax, [rax+0F8h]
0x18011985f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119864  mov     ebx, eax
0x180119866  test    eax, eax
0x180119868  jns     short loc_180119874
0x18011986a  mov     edx, 7Bh ; '{'
0x18011986f  jmp     loc_180119751
0x180119874  xor     eax, eax
0x180119876  add     rsp, 28h
0x18011987a  pop     r14
0x18011987c  pop     rdi
0x18011987d  pop     rsi
0x18011987e  pop     rbx
0x18011987f  retn
```
