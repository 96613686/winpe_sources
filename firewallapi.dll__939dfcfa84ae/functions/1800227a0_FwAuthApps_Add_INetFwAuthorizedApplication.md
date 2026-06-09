# FwAuthApps::Add(INetFwAuthorizedApplication *)

- ea: `0x1800227a0`
- end: `0x1800228e5`
- name: `?Add@FwAuthApps@@UEAAJPEAUINetFwAuthorizedApplication@@@Z`
- size: `325`
- prototype: `int(FwAuthApps *__hidden this, struct INetFwAuthorizedApplication *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800227a0`
- `0x1800256f4`
- `0x180026b58`
- `0x1800294b0`
- `0x18002c02c`
- `0x18003071c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022844`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022844`
- `fwbase!FwReportReturnError` at `0x1800227e0`
- `fwbase!FwReportReturnError` at `0x18002288c`
- `fwbase!FwReportReturnError` at `0x1800228ab`
- `fwbase!FwReportReturnError` at `0x1800227e0`
- `fwbase!FwReportReturnError` at `0x18002288c`
- `fwbase!FwReportReturnError` at `0x1800228ab`

## pseudocode

```c
__int64 __fastcall FwAuthApps::Add(FwAuthApps *this, struct INetFwAuthorizedApplication *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  HRESULT Instance; // eax
  struct FwAuthApp *v9; // [rsp+30h] [rbp-28h] BYREF
  struct INetFwAuthorizedApplication *ppv; // [rsp+38h] [rbp-20h] BYREF

  v9 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwAuthApps::Add", v5);
    return (unsigned int)FwReportReturnError("FwAuthApps::Add", v4);
  }
  if ( (int)FwAuthApp::Narrow(a2, &v9) < 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &GUID_ec9846b3_2762_4a6b_a214_6acb603462d2,
                 0,
                 1u,
                 &GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050,
                 (LPVOID *)&ppv);
    v4 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CopyINetFwAuthorizedApplication(a2, ppv);
      v4 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(FwAuthApps *, struct INetFwAuthorizedApplication *))(*(_QWORD *)this + 64LL))(
                     this,
                     ppv);
        v4 = Instance;
        if ( Instance >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          return v4;
        }
      }
    }
    FwReportReturnError("FwAuthApps::Add", (unsigned int)Instance);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)FwReportReturnError("FwAuthApps::Add", v4);
  }
  v6 = FwAuthApp::Add(v9, *((unsigned int *)this + 6));
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = (unsigned int)v6;
    goto LABEL_3;
  }
  return v4;
}

```

## disassembly

```asm
0x1800227a0  mov     [rsp+arg_10], rbx
0x1800227a5  mov     [rsp+arg_18], rsi
0x1800227aa  push    rdi
0x1800227ab  sub     rsp, 50h
0x1800227af  mov     rax, cs:__security_cookie
0x1800227b6  xor     rax, rsp
0x1800227b9  mov     [rsp+58h+var_18], rax
0x1800227be  mov     [rsp+58h+var_28], 0
0x1800227c7  mov     rdi, rdx
0x1800227ca  mov     rsi, rcx
0x1800227cd  test    rdx, rdx
0x1800227d0  jnz     short loc_1800227F1
0x1800227d2  mov     ebx, 80004003h
0x1800227d7  mov     edx, ebx
0x1800227d9  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x1800227e0  call    cs:__imp_FwReportReturnError
0x1800227e7  nop     dword ptr [rax+rax+00h]
0x1800227ec  jmp     loc_1800228A2
0x1800227f1  lea     rdx, [rsp+58h+var_28]; struct FwAuthApp **
0x1800227f6  mov     rcx, rdi; struct INetFwAuthorizedApplication *
0x1800227f9  call    ?Narrow@FwAuthApp@@SAJPEAUINetFwAuthorizedApplication@@PEAPEAV1@@Z; FwAuthApp::Narrow(INetFwAuthorizedApplication *,FwAuthApp * *)
0x1800227fe  test    eax, eax
0x180022800  js      short loc_18002281D
0x180022802  mov     edx, [rsi+18h]
0x180022805  mov     rcx, [rsp+58h+var_28]
0x18002280a  call    ?Add@FwAuthApp@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z; FwAuthApp::Add(_tag_FW_PROFILE_TYPE)
0x18002280f  mov     ebx, eax
0x180022811  test    eax, eax
0x180022813  jns     loc_1800228C5
0x180022819  mov     edx, eax
0x18002281b  jmp     short loc_1800227D9
0x18002281d  xor     edx, edx; pUnkOuter
0x18002281f  mov     [rsp+58h+var_20], 0
0x180022828  lea     rax, [rsp+58h+var_20]
0x18002282d  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x180022834  mov     [rsp+58h+ppv], rax; ppv
0x180022839  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x180022840  lea     r8d, [rdx+1]; dwClsContext
0x180022844  call    cs:__imp_CoCreateInstance
0x18002284b  nop     dword ptr [rax+rax+00h]
0x180022850  mov     ebx, eax
0x180022852  test    eax, eax
0x180022854  js      short loc_180022883
0x180022856  mov     rdx, [rsp+58h+var_20]; struct INetFwAuthorizedApplication *
0x18002285b  mov     rcx, rdi; struct INetFwAuthorizedApplication *
0x18002285e  call    ?CopyINetFwAuthorizedApplication@@YAJPEAUINetFwAuthorizedApplication@@0@Z; CopyINetFwAuthorizedApplication(INetFwAuthorizedApplication *,INetFwAuthorizedApplication *)
0x180022863  mov     ebx, eax
0x180022865  test    eax, eax
0x180022867  js      short loc_180022883
0x180022869  mov     rax, [rsi]
0x18002286c  mov     rcx, rsi
0x18002286f  mov     rdx, [rsp+58h+var_20]
0x180022874  mov     rax, [rax+40h]
0x180022878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002287d  mov     ebx, eax
0x18002287f  test    eax, eax
0x180022881  jns     short loc_1800228BB
0x180022883  mov     edx, eax
0x180022885  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x18002288c  call    cs:__imp_FwReportReturnError
0x180022893  nop     dword ptr [rax+rax+00h]
0x180022898  lea     rcx, [rsp+58h+var_20]
0x18002289d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800228a2  mov     edx, ebx
0x1800228a4  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x1800228ab  call    cs:__imp_FwReportReturnError
0x1800228b2  nop     dword ptr [rax+rax+00h]
0x1800228b7  mov     ebx, eax
0x1800228b9  jmp     short loc_1800228C5
0x1800228bb  lea     rcx, [rsp+58h+var_20]
0x1800228c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800228c5  mov     eax, ebx
0x1800228c7  mov     rcx, [rsp+58h+var_18]
0x1800228cc  xor     rcx, rsp; StackCookie
0x1800228cf  call    __security_check_cookie
0x1800228d4  mov     rbx, [rsp+58h+arg_10]
0x1800228d9  mov     rsi, [rsp+58h+arg_18]
0x1800228de  add     rsp, 50h
0x1800228e2  pop     rdi
0x1800228e3  retn
```
