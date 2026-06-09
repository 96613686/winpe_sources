# Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource::InitializeReportGeneration(void)

- ea: `0x1800f7a5c`
- end: `0x1800f7bb6`
- name: `?InitializeReportGeneration@FirstSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAXXZ`
- size: `346`
- prototype: `void __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::FirstSyncDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f7a00`

## callees

- `0x1800ead14`
- `0x1800f7a5c`
- `0x1800f7bdc`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1800f7aaf`
- `XmlLite!CreateXmlWriter` at `0x1800f7aaf`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f7a74`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f7a74`

## string_xrefs

- `0x1800f7a83`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f7abe`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f7af0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f7b26`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f7b59`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`
- `0x1800f7b96`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\firstsynctrackingdata.cpp`

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
0x1800f7a5c  mov     [rsp+arg_0], rbx
0x1800f7a61  push    rdi
0x1800f7a62  sub     rsp, 30h
0x1800f7a66  mov     rbx, rcx
0x1800f7a69  lea     r8, [rcx+8]; ppstm
0x1800f7a6d  xor     ecx, ecx; hGlobal
0x1800f7a6f  mov     edx, 1; fDeleteOnRelease
0x1800f7a74  call    cs:__imp_CreateStreamOnHGlobal
0x1800f7a7a  test    eax, eax
0x1800f7a7c  jns     short loc_1800F7A98
0x1800f7a7e  mov     rcx, [rsp+38h]; this
0x1800f7a83  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7a8a  mov     r9d, eax; char *
0x1800f7a8d  mov     edx, 68h ; 'h'; void *
0x1800f7a92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7a98  lea     rcx, [rbx+10h]
0x1800f7a9c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f7aa1  xor     r8d, r8d; pMalloc
0x1800f7aa4  lea     rdx, [rbx+10h]; ppvObject
0x1800f7aa8  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800f7aaf  call    cs:__imp_CreateXmlWriter
0x1800f7ab5  test    eax, eax
0x1800f7ab7  jns     short loc_1800F7AD3
0x1800f7ab9  mov     rcx, [rsp+38h]; this
0x1800f7abe  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7ac5  mov     r9d, eax; char *
0x1800f7ac8  mov     edx, 69h ; 'i'; void *
0x1800f7acd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7ad3  mov     rcx, [rbx+10h]
0x1800f7ad7  mov     rdx, [rbx+8]
0x1800f7adb  mov     rax, [rcx]
0x1800f7ade  mov     rax, [rax+18h]
0x1800f7ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7ae7  test    eax, eax
0x1800f7ae9  jns     short loc_1800F7B05
0x1800f7aeb  mov     rcx, [rsp+38h]; this
0x1800f7af0  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7af7  mov     r9d, eax; char *
0x1800f7afa  mov     edx, 6Ah ; 'j'; void *
0x1800f7aff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7b05  mov     rcx, [rbx+10h]
0x1800f7b09  mov     edx, 1
0x1800f7b0e  mov     r8d, edx
0x1800f7b11  mov     rax, [rcx]
0x1800f7b14  mov     rax, [rax+28h]
0x1800f7b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b1d  test    eax, eax
0x1800f7b1f  jns     short loc_1800F7B3B
0x1800f7b21  mov     rcx, [rsp+38h]; this
0x1800f7b26  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7b2d  mov     r9d, eax; char *
0x1800f7b30  mov     edx, 6Bh ; 'k'; void *
0x1800f7b35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7b3b  mov     rcx, [rbx+10h]
0x1800f7b3f  xor     edx, edx
0x1800f7b41  mov     rax, [rcx]
0x1800f7b44  mov     rax, [rax+0D0h]
0x1800f7b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b50  test    eax, eax
0x1800f7b52  jns     short loc_1800F7B6E
0x1800f7b54  mov     rcx, [rsp+38h]; this
0x1800f7b59  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7b60  mov     r9d, eax; char *
0x1800f7b63  mov     edx, 6Ch ; 'l'; void *
0x1800f7b68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7b6e  mov     rcx, [rbx+10h]
0x1800f7b72  lea     r8, aFirstsyncdata; "FirstSyncData"
0x1800f7b79  xor     r9d, r9d
0x1800f7b7c  xor     edx, edx
0x1800f7b7e  mov     rax, [rcx]
0x1800f7b81  mov     rax, [rax+0D8h]
0x1800f7b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b8d  test    eax, eax
0x1800f7b8f  jns     short loc_1800F7BAB
0x1800f7b91  mov     rcx, [rsp+38h]; this
0x1800f7b96  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f7b9d  mov     r9d, eax; char *
0x1800f7ba0  mov     edx, 6Dh ; 'm'; void *
0x1800f7ba5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f7bab  mov     rbx, [rsp+38h+arg_0]
0x1800f7bb0  add     rsp, 30h
0x1800f7bb4  pop     rdi
0x1800f7bb5  retn
```
