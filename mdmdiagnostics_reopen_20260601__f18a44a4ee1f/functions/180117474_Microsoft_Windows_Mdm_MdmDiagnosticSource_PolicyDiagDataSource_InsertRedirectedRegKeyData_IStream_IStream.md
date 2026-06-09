# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(IStream *,IStream * *)

- ea: `0x180117474`
- end: `0x1801176e4`
- name: `?InsertRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z`
- size: `624`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801172e0`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180117474`
- `0x180117c54`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1801174e6`
- `XmlLite!CreateXmlWriter` at `0x1801174e6`
- `XmlLite!CreateXmlReader` at `0x1801175ba`
- `XmlLite!CreateXmlReader` at `0x1801175ba`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117498`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180117498`

## string_xrefs

- `0x1801174b1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x18011751d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x1801175d8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::InsertRedirectedRegKeyData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *this,
        struct IStream *a2,
        struct IStream **a3)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned int v7; // ebx
  HRESULT XmlWriter; // eax
  __int64 v9; // rdx
  HRESULT XmlReader; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  void *ppvObject[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  struct IXmlReader *v16; // [rsp+98h] [rbp+50h] BYREF

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  v7 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    ppvObject[0] = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
    XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
    v7 = XmlWriter;
    if ( XmlWriter >= 0 )
    {
      XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject[0] + 24LL))(ppvObject[0], *a3);
      v7 = XmlWriter;
      if ( XmlWriter >= 0 )
      {
        XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject[0] + 40LL))(
                      ppvObject[0],
                      1,
                      1);
        v7 = XmlWriter;
        if ( XmlWriter >= 0 )
        {
          XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject[0] + 208LL))(ppvObject[0], 0);
          v7 = XmlWriter;
          if ( XmlWriter >= 0 )
          {
            ppvObject[1] = 0;
            (*(void (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, 0, 0, 0);
            v16 = 0;
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
            XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)&v16, 0);
            v7 = XmlReader;
            if ( XmlReader >= 0 )
            {
              XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64))v16->lpVtbl->SetProperty)(v16, 4);
              v7 = XmlReader;
              if ( XmlReader >= 0 )
              {
                XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64, __int64))v16->lpVtbl->SetProperty)(
                              v16,
                              1,
                              1);
                v7 = XmlReader;
                if ( XmlReader >= 0 )
                {
                  XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, struct IStream *))v16->lpVtbl->SetInput)(
                                v16,
                                a2);
                  v7 = XmlReader;
                  if ( XmlReader >= 0 )
                  {
                    XmlReader = Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::RetrieveRedirectedRegKeyData(
                                  this,
                                  v16,
                                  (struct IXmlWriter *)ppvObject[0]);
                    v7 = XmlReader;
                    if ( XmlReader >= 0 )
                    {
                      XmlReader = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject[0] + 112LL))(ppvObject[0]);
                      v7 = XmlReader;
                      if ( XmlReader >= 0 )
                      {
                        XmlReader = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject[0] + 248LL))(ppvObject[0]);
                        v7 = XmlReader;
                        if ( XmlReader >= 0 )
                        {
                          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
                          v7 = 0;
                          goto LABEL_28;
                        }
                        v11 = 495;
                      }
                      else
                      {
                        v11 = 494;
                      }
                    }
                    else
                    {
                      v11 = 491;
                    }
                  }
                  else
                  {
                    v11 = 488;
                  }
                }
                else
                {
                  v11 = 487;
                }
              }
              else
              {
                v11 = 486;
              }
            }
            else
            {
              v11 = 485;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v11,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
              (const char *)(unsigned int)XmlReader,
              v13);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
LABEL_28:
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
            return v7;
          }
          v9 = 477;
        }
        else
        {
          v9 = 476;
        }
      }
      else
      {
        v9 = 475;
      }
    }
    else
    {
      v9 = 474;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v13);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v13);
  return v7;
}

```

## disassembly

```asm
0x180117474  push    rbp
0x180117476  push    rbx
0x180117477  push    rsi
0x180117478  push    rdi
0x180117479  push    r12
0x18011747b  push    r14
0x18011747d  mov     rbp, rsp
0x180117480  sub     rsp, 48h
0x180117484  mov     rdi, r8
0x180117487  mov     rsi, rdx
0x18011748a  mov     r14, rcx
0x18011748d  mov     r12d, 1
0x180117493  mov     edx, r12d; fDeleteOnRelease
0x180117496  xor     ecx, ecx; hGlobal
0x180117498  call    cs:__imp_CreateStreamOnHGlobal
0x18011749f  nop     dword ptr [rax+rax+00h]
0x1801174a4  mov     ebx, eax
0x1801174a6  test    eax, eax
0x1801174a8  jns     short loc_1801174C7
0x1801174aa  mov     rcx, [rbp+30h]; this
0x1801174ae  mov     r9d, eax; char *
0x1801174b1  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801174b8  mov     edx, 1D6h; void *
0x1801174bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801174c2  jmp     loc_1801176D4
0x1801174c7  mov     [rbp+ppvObject], 0
0x1801174cf  lea     rcx, [rbp+ppvObject]
0x1801174d3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801174d8  xor     r8d, r8d; pMalloc
0x1801174db  lea     rdx, [rbp+ppvObject]; ppvObject
0x1801174df  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1801174e6  call    cs:__imp_CreateXmlWriter
0x1801174ed  nop     dword ptr [rax+rax+00h]
0x1801174f2  mov     ebx, eax
0x1801174f4  test    eax, eax
0x1801174f6  jns     short loc_1801174FF
0x1801174f8  mov     edx, 1DAh
0x1801174fd  jmp     short loc_18011751D
0x1801174ff  mov     rcx, [rbp+ppvObject]
0x180117503  mov     rax, [rcx]
0x180117506  mov     rdx, [rdi]
0x180117509  mov     rax, [rax+18h]
0x18011750d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117512  mov     ebx, eax
0x180117514  test    eax, eax
0x180117516  jns     short loc_180117535
0x180117518  mov     edx, 1DBh; void *
0x18011751d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117524  mov     r9d, eax; char *
0x180117527  mov     rcx, [rbp+30h]; this
0x18011752b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117530  jmp     loc_1801176CB
0x180117535  mov     rcx, [rbp+ppvObject]
0x180117539  mov     rax, [rcx]
0x18011753c  mov     r8, r12
0x18011753f  mov     edx, r12d
0x180117542  mov     rax, [rax+28h]
0x180117546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011754b  mov     ebx, eax
0x18011754d  test    eax, eax
0x18011754f  jns     short loc_180117558
0x180117551  mov     edx, 1DCh
0x180117556  jmp     short loc_18011751D
0x180117558  mov     rcx, [rbp+ppvObject]
0x18011755c  mov     rax, [rcx]
0x18011755f  xor     edx, edx
0x180117561  mov     rax, [rax+0D0h]
0x180117568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011756d  mov     ebx, eax
0x18011756f  test    eax, eax
0x180117571  jns     short loc_18011757A
0x180117573  mov     edx, 1DDh
0x180117578  jmp     short loc_18011751D
0x18011757a  mov     [rbp+var_10], 0
0x180117582  mov     rax, [rsi]
0x180117585  xor     r9d, r9d
0x180117588  xor     r8d, r8d
0x18011758b  mov     rdx, [rbp+var_10]
0x18011758f  mov     rcx, rsi
0x180117592  mov     rax, [rax+28h]
0x180117596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011759b  mov     [rbp+arg_18], 0
0x1801175a3  lea     rcx, [rbp+arg_18]
0x1801175a7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801175ac  xor     r8d, r8d; pMalloc
0x1801175af  lea     rdx, [rbp+arg_18]; ppvObject
0x1801175b3  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1801175ba  call    cs:__imp_CreateXmlReader
0x1801175c1  nop     dword ptr [rax+rax+00h]
0x1801175c6  mov     ebx, eax
0x1801175c8  test    eax, eax
0x1801175ca  jns     short loc_1801175F3
0x1801175cc  mov     edx, 1E5h; void *
0x1801175d1  mov     rcx, [rbp+30h]; this
0x1801175d5  mov     r9d, eax; char *
0x1801175d8  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801175df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801175e4  nop
0x1801175e5  lea     rcx, [rbp+arg_18]
0x1801175e9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801175ee  jmp     loc_1801176CB
0x1801175f3  mov     rcx, [rbp+arg_18]
0x1801175f7  mov     rax, [rcx]
0x1801175fa  xor     r8d, r8d
0x1801175fd  lea     edx, [r8+4]
0x180117601  mov     rax, [rax+28h]
0x180117605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011760a  mov     ebx, eax
0x18011760c  test    eax, eax
0x18011760e  jns     short loc_180117617
0x180117610  mov     edx, 1E6h
0x180117615  jmp     short loc_1801175D1
0x180117617  mov     rcx, [rbp+arg_18]
0x18011761b  mov     rax, [rcx]
0x18011761e  mov     r8, r12
0x180117621  mov     edx, r12d
0x180117624  mov     rax, [rax+28h]
0x180117628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011762d  mov     ebx, eax
0x18011762f  test    eax, eax
0x180117631  jns     short loc_18011763A
0x180117633  mov     edx, 1E7h
0x180117638  jmp     short loc_1801175D1
0x18011763a  mov     rcx, [rbp+arg_18]
0x18011763e  mov     rax, [rcx]
0x180117641  mov     rdx, rsi
0x180117644  mov     rax, [rax+18h]
0x180117648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011764d  mov     ebx, eax
0x18011764f  test    eax, eax
0x180117651  jns     short loc_18011765D
0x180117653  mov     edx, 1E8h
0x180117658  jmp     loc_1801175D1
0x18011765d  mov     r8, [rbp+ppvObject]; struct IXmlWriter *
0x180117661  mov     rdx, [rbp+arg_18]; struct IXmlReader *
0x180117665  mov     rcx, r14; this
0x180117668  call    ?RetrieveRedirectedRegKeyData@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::RetrieveRedirectedRegKeyData(IXmlReader *,IXmlWriter *)
0x18011766d  mov     ebx, eax
0x18011766f  test    eax, eax
0x180117671  jns     short loc_18011767D
0x180117673  mov     edx, 1EBh
0x180117678  jmp     loc_1801175D1
0x18011767d  mov     rcx, [rbp+ppvObject]
0x180117681  mov     rax, [rcx]
0x180117684  mov     rax, [rax+70h]
0x180117688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011768d  mov     ebx, eax
0x18011768f  test    eax, eax
0x180117691  jns     short loc_18011769D
0x180117693  mov     edx, 1EEh
0x180117698  jmp     loc_1801175D1
0x18011769d  mov     rcx, [rbp+ppvObject]
0x1801176a1  mov     rax, [rcx]
0x1801176a4  mov     rax, [rax+0F8h]
0x1801176ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801176b0  mov     ebx, eax
0x1801176b2  test    eax, eax
0x1801176b4  jns     short loc_1801176C0
0x1801176b6  mov     edx, 1EFh
0x1801176bb  jmp     loc_1801175D1
0x1801176c0  lea     rcx, [rbp+arg_18]
0x1801176c4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801176c9  xor     ebx, ebx
0x1801176cb  lea     rcx, [rbp+ppvObject]
0x1801176cf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801176d4  mov     eax, ebx
0x1801176d6  add     rsp, 48h
0x1801176da  pop     r14
0x1801176dc  pop     r12
0x1801176de  pop     rdi
0x1801176df  pop     rsi
0x1801176e0  pop     rbx
0x1801176e1  pop     rbp
0x1801176e2  retn
```
