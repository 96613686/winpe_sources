# CEnhancedStorageSilo::GetPortableDevice(IPortableDevice * *)

- ea: `0x180007290`
- end: `0x180007427`
- name: `?GetPortableDevice@CEnhancedStorageSilo@@UEAAJPEAPEAUIPortableDevice@@@Z`
- size: `407`
- prototype: `int(CEnhancedStorageSilo *__hidden this, struct IPortableDevice **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003c54`
- `0x180003ce0`
- `0x180003df0`
- `0x180003ed0`
- `0x1800061c8`
- `0x1800063dc`
- `0x18000664c`
- `0x180007290`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000736a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000736a`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::GetPortableDevice(CEnhancedStorageSilo *this, LPVOID *a2)
{
  unsigned int v4; // ebx
  HRESULT Instance; // eax
  CEnhancedStorageSilo *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  struct IPortableDeviceValues *v11; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[272]; // [rsp+40h] [rbp-C0h] BYREF

  v10 = -2147418113;
  v11 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, a2);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v12, "CEnhancedStorageSilo::GetPortableDevice", &v10);
  if ( a2 )
  {
    Instance = CoCreateInstance(&CLSID_PortableDevice, 0, 1u, &IID_IPortableDevice, a2);
    v10 = Instance;
    v4 = Instance;
    if ( Instance >= 0 )
    {
      CEnhancedStorageSilo::CreateClientInformation(v6, (LPVOID *)&v11);
      Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPortableDeviceValues *))(*(_QWORD *)*a2 + 24LL))(
                   *a2,
                   *((_QWORD *)this + 8),
                   v11);
      v10 = Instance;
      v4 = Instance;
      if ( Instance >= 0 )
        goto LABEL_18;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_18;
      v8 = 54;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_18;
      v8 = 53;
    }
    WPP_SF_d(v7[2], v8, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, (unsigned int)Instance);
    v4 = v10;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
      "ppIPortableDevice != NULL");
  v4 = -2147024809;
LABEL_18:
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v12);
  ATL::CComPtrBase<IPortableDeviceValues>::~CComPtrBase<IPortableDeviceValues>(&v11);
  return v4;
}

```

## disassembly

```asm
0x180007290  mov     [rsp-8+arg_10], rbx
0x180007295  mov     [rsp-8+arg_18], rsi
0x18000729a  push    rbp
0x18000729b  push    rdi
0x18000729c  push    r14
0x18000729e  lea     rbp, [rsp-60h]
0x1800072a3  sub     rsp, 160h
0x1800072aa  mov     rax, cs:__security_cookie
0x1800072b1  xor     rax, rsp
0x1800072b4  mov     [rbp+70h+var_20], rax
0x1800072b8  mov     rdi, rdx
0x1800072bb  mov     [rsp+170h+var_140], 8000FFFFh
0x1800072c3  mov     rsi, rcx
0x1800072c6  mov     [rsp+170h+var_138], 0
0x1800072cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072d6  lea     r14, WPP_GLOBAL_Control
0x1800072dd  cmp     rcx, r14
0x1800072e0  jz      short loc_180007300
0x1800072e2  test    byte ptr [rcx+1Ch], 10h
0x1800072e6  jz      short loc_180007300
0x1800072e8  mov     rcx, [rcx+10h]
0x1800072ec  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800072f3  mov     edx, 33h ; '3'
0x1800072f8  mov     r9, rdi
0x1800072fb  call    WPP_SF_q
0x180007300  lea     r8, [rsp+170h+var_140]; int *
0x180007305  lea     rdx, aCenhancedstora_11; "CEnhancedStorageSilo::GetPortableDevice"
0x18000730c  lea     rcx, [rsp+170h+var_130]; this
0x180007311  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x180007316  test    rdi, rdi
0x180007319  jnz     short loc_180007351
0x18000731b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007322  cmp     rcx, r14
0x180007325  jz      short loc_180007347
0x180007327  test    byte ptr [rcx+1Ch], 2
0x18000732b  jz      short loc_180007347
0x18000732d  mov     rcx, [rcx+10h]
0x180007331  lea     edx, [rdi+34h]
0x180007334  lea     r9, aPpiportabledev; "ppIPortableDevice != NULL"
0x18000733b  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007342  call    WPP_SF_s
0x180007347  mov     ebx, 80070057h
0x18000734c  jmp     loc_1800073ED
0x180007351  xor     edx, edx; pUnkOuter
0x180007353  mov     [rsp+170h+ppv], rdi; ppv
0x180007358  lea     r9, IID_IPortableDevice; riid
0x18000735f  lea     rcx, CLSID_PortableDevice; rclsid
0x180007366  lea     r8d, [rdx+1]; dwClsContext
0x18000736a  call    cs:__imp_CoCreateInstance
0x180007370  mov     [rsp+170h+var_140], eax
0x180007374  mov     ebx, eax
0x180007376  test    eax, eax
0x180007378  jns     short loc_180007393
0x18000737a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007381  cmp     rcx, r14
0x180007384  jz      short loc_1800073ED
0x180007386  test    byte ptr [rcx+1Ch], 2
0x18000738a  jz      short loc_1800073ED
0x18000738c  mov     edx, 35h ; '5'
0x180007391  jmp     short loc_1800073D6
0x180007393  lea     rdx, [rsp+170h+var_138]; struct IPortableDeviceValues **
0x180007398  call    ?CreateClientInformation@CEnhancedStorageSilo@@AEAAXPEAPEAUIPortableDeviceValues@@@Z; CEnhancedStorageSilo::CreateClientInformation(IPortableDeviceValues * *)
0x18000739d  mov     rcx, [rdi]
0x1800073a0  mov     r8, [rsp+170h+var_138]
0x1800073a5  mov     rdx, [rsi+40h]
0x1800073a9  mov     rax, [rcx]
0x1800073ac  mov     rax, [rax+18h]
0x1800073b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b5  mov     [rsp+170h+var_140], eax
0x1800073b9  mov     ebx, eax
0x1800073bb  test    eax, eax
0x1800073bd  jns     short loc_1800073ED
0x1800073bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073c6  cmp     rcx, r14
0x1800073c9  jz      short loc_1800073ED
0x1800073cb  test    byte ptr [rcx+1Ch], 2
0x1800073cf  jz      short loc_1800073ED
0x1800073d1  mov     edx, 36h ; '6'
0x1800073d6  mov     rcx, [rcx+10h]
0x1800073da  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800073e1  mov     r9d, eax
0x1800073e4  call    WPP_SF_d
0x1800073e9  mov     ebx, [rsp+170h+var_140]
0x1800073ed  lea     rcx, [rsp+170h+var_130]; this
0x1800073f2  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x1800073f7  lea     rcx, [rsp+170h+var_138]
0x1800073fc  call    ??1?$CComPtrBase@UIPortableDeviceValues@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IPortableDeviceValues>::~CComPtrBase<IPortableDeviceValues>(void)
0x180007401  mov     eax, ebx
0x180007403  mov     rcx, [rbp+70h+var_20]
0x180007407  xor     rcx, rsp; StackCookie
0x18000740a  call    __security_check_cookie
0x18000740f  lea     r11, [rsp+170h+var_10]
0x180007417  mov     rbx, [r11+30h]
0x18000741b  mov     rsi, [r11+38h]
0x18000741f  mov     rsp, r11
0x180007422  pop     r14
0x180007424  pop     rdi
0x180007425  pop     rbp
0x180007426  retn
```
