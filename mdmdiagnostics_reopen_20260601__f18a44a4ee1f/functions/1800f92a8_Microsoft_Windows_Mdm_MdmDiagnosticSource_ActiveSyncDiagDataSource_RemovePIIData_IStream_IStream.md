# Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(IStream *,IStream * *)

- ea: `0x1800f92a8`
- end: `0x1800f9518`
- name: `?RemovePIIData@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIStream@@PEAPEAU6@@Z`
- size: `624`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f8f50`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f92a8`
- `0x1800f9520`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x1800f931a`
- `XmlLite!CreateXmlWriter` at `0x1800f931a`
- `XmlLite!CreateXmlReader` at `0x1800f93ee`
- `XmlLite!CreateXmlReader` at `0x1800f93ee`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f92cc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f92cc`

## string_xrefs

- `0x1800f92e5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`
- `0x1800f9351`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`
- `0x1800f940c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\activesyncdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RemovePIIData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource *this,
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
                    XmlReader = Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RetrieveActiveSyncDataWithoutPII(
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
                        v11 = 182;
                      }
                      else
                      {
                        v11 = 181;
                      }
                    }
                    else
                    {
                      v11 = 178;
                    }
                  }
                  else
                  {
                    v11 = 175;
                  }
                }
                else
                {
                  v11 = 174;
                }
              }
              else
              {
                v11 = 173;
              }
            }
            else
            {
              v11 = 172;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v11,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
              (const char *)(unsigned int)XmlReader,
              v13);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v16);
LABEL_28:
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(ppvObject);
            return v7;
          }
          v9 = 164;
        }
        else
        {
          v9 = 163;
        }
      }
      else
      {
        v9 = 162;
      }
    }
    else
    {
      v9 = 161;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v13);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\activesyncdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v13);
  return v7;
}

```

## disassembly

```asm
0x1800f92a8  push    rbp
0x1800f92aa  push    rbx
0x1800f92ab  push    rsi
0x1800f92ac  push    rdi
0x1800f92ad  push    r12
0x1800f92af  push    r14
0x1800f92b1  mov     rbp, rsp
0x1800f92b4  sub     rsp, 48h
0x1800f92b8  mov     rdi, r8
0x1800f92bb  mov     rsi, rdx
0x1800f92be  mov     r14, rcx
0x1800f92c1  mov     r12d, 1
0x1800f92c7  mov     edx, r12d; fDeleteOnRelease
0x1800f92ca  xor     ecx, ecx; hGlobal
0x1800f92cc  call    cs:__imp_CreateStreamOnHGlobal
0x1800f92d3  nop     dword ptr [rax+rax+00h]
0x1800f92d8  mov     ebx, eax
0x1800f92da  test    eax, eax
0x1800f92dc  jns     short loc_1800F92FB
0x1800f92de  mov     rcx, [rbp+30h]; this
0x1800f92e2  mov     r9d, eax; char *
0x1800f92e5  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f92ec  mov     edx, 9Dh; void *
0x1800f92f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f92f6  jmp     loc_1800F9508
0x1800f92fb  mov     [rbp+ppvObject], 0
0x1800f9303  lea     rcx, [rbp+ppvObject]
0x1800f9307  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f930c  xor     r8d, r8d; pMalloc
0x1800f930f  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800f9313  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800f931a  call    cs:__imp_CreateXmlWriter
0x1800f9321  nop     dword ptr [rax+rax+00h]
0x1800f9326  mov     ebx, eax
0x1800f9328  test    eax, eax
0x1800f932a  jns     short loc_1800F9333
0x1800f932c  mov     edx, 0A1h
0x1800f9331  jmp     short loc_1800F9351
0x1800f9333  mov     rcx, [rbp+ppvObject]
0x1800f9337  mov     rax, [rcx]
0x1800f933a  mov     rdx, [rdi]
0x1800f933d  mov     rax, [rax+18h]
0x1800f9341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9346  mov     ebx, eax
0x1800f9348  test    eax, eax
0x1800f934a  jns     short loc_1800F9369
0x1800f934c  mov     edx, 0A2h; void *
0x1800f9351  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9358  mov     r9d, eax; char *
0x1800f935b  mov     rcx, [rbp+30h]; this
0x1800f935f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9364  jmp     loc_1800F94FF
0x1800f9369  mov     rcx, [rbp+ppvObject]
0x1800f936d  mov     rax, [rcx]
0x1800f9370  mov     r8, r12
0x1800f9373  mov     edx, r12d
0x1800f9376  mov     rax, [rax+28h]
0x1800f937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f937f  mov     ebx, eax
0x1800f9381  test    eax, eax
0x1800f9383  jns     short loc_1800F938C
0x1800f9385  mov     edx, 0A3h
0x1800f938a  jmp     short loc_1800F9351
0x1800f938c  mov     rcx, [rbp+ppvObject]
0x1800f9390  mov     rax, [rcx]
0x1800f9393  xor     edx, edx
0x1800f9395  mov     rax, [rax+0D0h]
0x1800f939c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f93a1  mov     ebx, eax
0x1800f93a3  test    eax, eax
0x1800f93a5  jns     short loc_1800F93AE
0x1800f93a7  mov     edx, 0A4h
0x1800f93ac  jmp     short loc_1800F9351
0x1800f93ae  mov     [rbp+var_10], 0
0x1800f93b6  mov     rax, [rsi]
0x1800f93b9  xor     r9d, r9d
0x1800f93bc  xor     r8d, r8d
0x1800f93bf  mov     rdx, [rbp+var_10]
0x1800f93c3  mov     rcx, rsi
0x1800f93c6  mov     rax, [rax+28h]
0x1800f93ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f93cf  mov     [rbp+arg_18], 0
0x1800f93d7  lea     rcx, [rbp+arg_18]
0x1800f93db  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f93e0  xor     r8d, r8d; pMalloc
0x1800f93e3  lea     rdx, [rbp+arg_18]; ppvObject
0x1800f93e7  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800f93ee  call    cs:__imp_CreateXmlReader
0x1800f93f5  nop     dword ptr [rax+rax+00h]
0x1800f93fa  mov     ebx, eax
0x1800f93fc  test    eax, eax
0x1800f93fe  jns     short loc_1800F9427
0x1800f9400  mov     edx, 0ACh; void *
0x1800f9405  mov     rcx, [rbp+30h]; this
0x1800f9409  mov     r9d, eax; char *
0x1800f940c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9418  nop
0x1800f9419  lea     rcx, [rbp+arg_18]
0x1800f941d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f9422  jmp     loc_1800F94FF
0x1800f9427  mov     rcx, [rbp+arg_18]
0x1800f942b  mov     rax, [rcx]
0x1800f942e  xor     r8d, r8d
0x1800f9431  lea     edx, [r8+4]
0x1800f9435  mov     rax, [rax+28h]
0x1800f9439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f943e  mov     ebx, eax
0x1800f9440  test    eax, eax
0x1800f9442  jns     short loc_1800F944B
0x1800f9444  mov     edx, 0ADh
0x1800f9449  jmp     short loc_1800F9405
0x1800f944b  mov     rcx, [rbp+arg_18]
0x1800f944f  mov     rax, [rcx]
0x1800f9452  mov     r8, r12
0x1800f9455  mov     edx, r12d
0x1800f9458  mov     rax, [rax+28h]
0x1800f945c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9461  mov     ebx, eax
0x1800f9463  test    eax, eax
0x1800f9465  jns     short loc_1800F946E
0x1800f9467  mov     edx, 0AEh
0x1800f946c  jmp     short loc_1800F9405
0x1800f946e  mov     rcx, [rbp+arg_18]
0x1800f9472  mov     rax, [rcx]
0x1800f9475  mov     rdx, rsi
0x1800f9478  mov     rax, [rax+18h]
0x1800f947c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9481  mov     ebx, eax
0x1800f9483  test    eax, eax
0x1800f9485  jns     short loc_1800F9491
0x1800f9487  mov     edx, 0AFh
0x1800f948c  jmp     loc_1800F9405
0x1800f9491  mov     r8, [rbp+ppvObject]; struct IXmlWriter *
0x1800f9495  mov     rdx, [rbp+arg_18]; struct IXmlReader *
0x1800f9499  mov     rcx, r14; this
0x1800f949c  call    ?RetrieveActiveSyncDataWithoutPII@ActiveSyncDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ActiveSyncDiagDataSource::RetrieveActiveSyncDataWithoutPII(IXmlReader *,IXmlWriter *)
0x1800f94a1  mov     ebx, eax
0x1800f94a3  test    eax, eax
0x1800f94a5  jns     short loc_1800F94B1
0x1800f94a7  mov     edx, 0B2h
0x1800f94ac  jmp     loc_1800F9405
0x1800f94b1  mov     rcx, [rbp+ppvObject]
0x1800f94b5  mov     rax, [rcx]
0x1800f94b8  mov     rax, [rax+70h]
0x1800f94bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f94c1  mov     ebx, eax
0x1800f94c3  test    eax, eax
0x1800f94c5  jns     short loc_1800F94D1
0x1800f94c7  mov     edx, 0B5h
0x1800f94cc  jmp     loc_1800F9405
0x1800f94d1  mov     rcx, [rbp+ppvObject]
0x1800f94d5  mov     rax, [rcx]
0x1800f94d8  mov     rax, [rax+0F8h]
0x1800f94df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f94e4  mov     ebx, eax
0x1800f94e6  test    eax, eax
0x1800f94e8  jns     short loc_1800F94F4
0x1800f94ea  mov     edx, 0B6h
0x1800f94ef  jmp     loc_1800F9405
0x1800f94f4  lea     rcx, [rbp+arg_18]
0x1800f94f8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f94fd  xor     ebx, ebx
0x1800f94ff  lea     rcx, [rbp+ppvObject]
0x1800f9503  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f9508  mov     eax, ebx
0x1800f950a  add     rsp, 48h
0x1800f950e  pop     r14
0x1800f9510  pop     r12
0x1800f9512  pop     rdi
0x1800f9513  pop     rsi
0x1800f9514  pop     rbx
0x1800f9515  pop     rbp
0x1800f9516  retn
```
