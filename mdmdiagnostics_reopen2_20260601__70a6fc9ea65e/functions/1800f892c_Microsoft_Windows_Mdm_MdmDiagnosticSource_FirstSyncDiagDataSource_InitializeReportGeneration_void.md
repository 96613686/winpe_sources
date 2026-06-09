# Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource::InitializeReportGeneration(void)

- ea: `0x1800f892c`
- end: `0x1800f8a93`
- name: `?InitializeReportGeneration@FirstSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAXXZ`
- size: `359`
- prototype: `void __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f88d0`

## callees

- `0x1800eb1ac`
- `0x1800f892c`
- `0x1800f8abc`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1800f8985`
- `XmlLite!CreateXmlWriter` at `0x1800f8985`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8944`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f8944`

## string_xrefs

- `0x1800f8959`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f899a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f89cc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f8a02`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f8a35`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f8a72`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`

## pseudocode

```c
void __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource::InitializeReportGeneration(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource *this)
{
  HRESULT StreamOnHGlobal; // eax
  HRESULT XmlWriter; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)this + 1);
  if ( StreamOnHGlobal < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v8);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 16);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, (void **)this + 2, 0);
  if ( XmlWriter < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v8);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 24LL))(
         *((_QWORD *)this + 2),
         *((_QWORD *)this + 1));
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)v4,
      v8);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 2) + 40LL))(
         *((_QWORD *)this + 2),
         1,
         1);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)v5,
      v8);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 208LL))(*((_QWORD *)this + 2), 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)v6,
      v8);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 2) + 216LL))(
         *((_QWORD *)this + 2),
         0,
         L"FirstSyncData",
         0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\firstsynctrackingdata.cpp",
      (const char *)(unsigned int)v7,
      v8);
}

```

## disassembly

```asm
0x1800f892c  mov     [rsp+arg_0], rbx
0x1800f8931  push    rdi
0x1800f8932  sub     rsp, 30h
0x1800f8936  mov     rbx, rcx
0x1800f8939  lea     r8, [rcx+8]; ppstm
0x1800f893d  xor     ecx, ecx; hGlobal
0x1800f893f  mov     edx, 1; fDeleteOnRelease
0x1800f8944  call    cs:__imp_CreateStreamOnHGlobal
0x1800f894b  nop     dword ptr [rax+rax+00h]
0x1800f8950  test    eax, eax
0x1800f8952  jns     short loc_1800F896E
0x1800f8954  mov     rcx, [rsp+38h]; this
0x1800f8959  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8960  mov     r9d, eax; char *
0x1800f8963  mov     edx, 68h ; 'h'; void *
0x1800f8968  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f896e  lea     rcx, [rbx+10h]
0x1800f8972  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f8977  xor     r8d, r8d; pMalloc
0x1800f897a  lea     rdx, [rbx+10h]; ppvObject
0x1800f897e  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800f8985  call    cs:__imp_CreateXmlWriter
0x1800f898c  nop     dword ptr [rax+rax+00h]
0x1800f8991  test    eax, eax
0x1800f8993  jns     short loc_1800F89AF
0x1800f8995  mov     rcx, [rsp+38h]; this
0x1800f899a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f89a1  mov     r9d, eax; char *
0x1800f89a4  mov     edx, 69h ; 'i'; void *
0x1800f89a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f89af  mov     rcx, [rbx+10h]
0x1800f89b3  mov     rdx, [rbx+8]
0x1800f89b7  mov     rax, [rcx]
0x1800f89ba  mov     rax, [rax+18h]
0x1800f89be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f89c3  test    eax, eax
0x1800f89c5  jns     short loc_1800F89E1
0x1800f89c7  mov     rcx, [rsp+38h]; this
0x1800f89cc  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f89d3  mov     r9d, eax; char *
0x1800f89d6  mov     edx, 6Ah ; 'j'; void *
0x1800f89db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f89e1  mov     rcx, [rbx+10h]
0x1800f89e5  mov     edx, 1
0x1800f89ea  mov     r8d, edx
0x1800f89ed  mov     rax, [rcx]
0x1800f89f0  mov     rax, [rax+28h]
0x1800f89f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f89f9  test    eax, eax
0x1800f89fb  jns     short loc_1800F8A17
0x1800f89fd  mov     rcx, [rsp+38h]; this
0x1800f8a02  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8a09  mov     r9d, eax; char *
0x1800f8a0c  mov     edx, 6Bh ; 'k'; void *
0x1800f8a11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f8a17  mov     rcx, [rbx+10h]
0x1800f8a1b  xor     edx, edx
0x1800f8a1d  mov     rax, [rcx]
0x1800f8a20  mov     rax, [rax+0D0h]
0x1800f8a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a2c  test    eax, eax
0x1800f8a2e  jns     short loc_1800F8A4A
0x1800f8a30  mov     rcx, [rsp+38h]; this
0x1800f8a35  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8a3c  mov     r9d, eax; char *
0x1800f8a3f  mov     edx, 6Ch ; 'l'; void *
0x1800f8a44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f8a4a  mov     rcx, [rbx+10h]
0x1800f8a4e  lea     r8, aFirstsyncdata; "FirstSyncData"
0x1800f8a55  xor     r9d, r9d
0x1800f8a58  xor     edx, edx
0x1800f8a5a  mov     rax, [rcx]
0x1800f8a5d  mov     rax, [rax+0D8h]
0x1800f8a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a69  test    eax, eax
0x1800f8a6b  jns     short loc_1800F8A87
0x1800f8a6d  mov     rcx, [rsp+38h]; this
0x1800f8a72  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f8a79  mov     r9d, eax; char *
0x1800f8a7c  mov     edx, 6Dh ; 'm'; void *
0x1800f8a81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f8a87  mov     rbx, [rsp+38h+arg_0]
0x1800f8a8c  add     rsp, 30h
0x1800f8a90  pop     rdi
0x1800f8a91  retn
```
