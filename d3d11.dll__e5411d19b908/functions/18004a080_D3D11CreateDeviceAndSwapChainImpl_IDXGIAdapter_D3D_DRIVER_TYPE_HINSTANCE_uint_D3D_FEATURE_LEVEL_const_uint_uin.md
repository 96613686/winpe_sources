# D3D11CreateDeviceAndSwapChainImpl(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)

- ea: `0x18004a080`
- end: `0x18004a745`
- name: `?D3D11CreateDeviceAndSwapChainImpl@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEBUDXGI_SWAP_CHAIN_DESC@@PEAPEAUIDXGISwapChain@@PEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z`
- size: `1733`
- prototype: `int(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, const struct DXGI_SWAP_CHAIN_DESC *, struct IDXGISwapChain **, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180034550`
- `0x180047a80`
- `0x18004948c`
- `0x18004a080`
- `0x18004a74c`
- `0x18004a7d4`
- `0x18004ac20`
- `0x18004b04c`
- `0x18009cdc4`
- `0x1800a2e84`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800af02c`
- `0x1800af820`
- `0x1801cb010`

## string_xrefs

- `0x18004a49a`: `D3D11CreateDevice: The D3D11_CREATE_DEVICE_ENABLE_INCREASED_PRIORITY flag may only be used if the calling process possesses the SeIncBasePriority privilege.`
- `0x18004a594`: `D3D11CreateDevice: The output parameter pFeatureLevel must not overlap with the input paramteter array pFeatureLevels.`
- `0x18004a5b6`: `D3D11CreateDevice: There's no reason to pass in an array larger than %d elements, as it implies that either certain D3D_FEATURE_LEVELs will be tried multiple times or never succeed. FeatureLevels was set to %d. Only D3D_FEATURE_LEVEL_9_1, D3D_FEATURE_LEVEL_9_2, D3D_FEATURE_LEVEL_9_3, D3D_FEATURE_LEVEL_10_0, D3D_FEATURE_LEVEL_10_1, D3D_FEATURE_LEVEL_11_0, D3D_FEATURE_LEVEL_11_1, D3D_FEATURE_LEVEL_12_0,  D3D_FEATURE_LEVEL_12_1 and D3D_FEATURE_LEVEL_12_2 are recognized.`
- `0x18004a654`: `D3D11CreateDevice: The adapter obtained via IDXGIDevice::GetAdapter from a D3D_FEATURE_LEVEL_9_* device can only be used to create other feature level 9 devices.  Because this device creation call only requests feature level 10 or higher it will fail.`
- `0x1800eab54`: `D3D11CreateDevice: The adapter obtained via IDXGIDevice::GetAdapter from a D3D_FEATURE_LEVEL_9_* device can only be used to create other feature level 9 devices.  Higher feature levels are being ignored.`
- `0x18004a671`: `D3D11CreateDevice: When creating a device from an existing adapter (i.e. pAdapter is non-NULL), DriverType must be D3D_DRIVER_TYPE_UNKNOWN.`
- `0x18004a686`: `D3D11CreateDevice: When creating a device without an adapter (i.e. pAdapter is NULL), the DriverType designates the type of adapter to use; and must not be D3D_DRIVER_TYPE_UNKNOWN.`
- `0x18004a540`: `D3D11CreateDevice: When creating a D3D_DRIVER_TYPE_SOFTWARE device, Software handle must be non-NULL.`
- `0x18004a59d`: `D3D11CreateDevice: When creating a non-D3D_DRIVER_TYPE_SOFTWARE device, Software handle must be NULL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall D3D11CreateDeviceAndSwapChainImpl(
        struct IUnknown *a1,
        enum D3D_DRIVER_TYPE a2,
        HINSTANCE a3,
        unsigned int a4,
        enum D3D_FEATURE_LEVEL *a5,
        unsigned int a6,
        unsigned int a7,
        const struct DXGI_SWAP_CHAIN_DESC *a8,
        struct IDXGISwapChain **a9,
        struct ID3D11Device **a10,
        enum D3D_FEATURE_LEVEL *a11,
        struct ID3D11DeviceContext **a12)
{
  enum D3D_DRIVER_TYPE v13; // r13d
  enum D3D_FEATURE_LEVEL *v14; // r14
  unsigned int v15; // edi
  struct ID3D11Device **v16; // rsi
  enum D3D_FEATURE_LEVEL *v17; // r15
  __int64 v18; // r8
  char v19; // r15
  bool v20; // cl
  int v21; // eax
  int v22; // ecx
  int Device; // ebx
  bool v24; // bl
  HINSTANCE v25; // r9
  int v27; // ecx
  __int64 i; // r13
  enum D3D_FEATURE_LEVEL v29; // r9d
  struct ID3D11Device **v30; // rax
  struct IDXGISwapChain **v31; // rdi
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  enum D3D_DRIVER_TYPE v33; // [rsp+5Ch] [rbp-A4h]
  _BYTE v34[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v42; // [rsp+9Ch] [rbp-64h]
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  struct IDXGISwapChain **v44; // [rsp+A8h] [rbp-58h]
  HINSTANCE v45; // [rsp+B0h] [rbp-50h]
  const struct DXGI_SWAP_CHAIN_DESC *v46; // [rsp+B8h] [rbp-48h]
  _BYTE v47[320]; // [rsp+C0h] [rbp-40h] BYREF
  enum D3D_FEATURE_LEVEL v48[3]; // [rsp+200h] [rbp+100h] BYREF

  v45 = a3;
  v13 = a2;
  v33 = a2;
  v37 = a1;
  v14 = a5;
  v15 = a6;
  v46 = a8;
  v44 = a9;
  v16 = a10;
  v17 = a11;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a12 )
    *a12 = 0;
  DebugPrintF::DebugPrintF((DebugPrintF *)v34, a4);
  v43 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  if ( (a4 & 0x1000) != 0 && !CurrentProcessHasIncreasedPriorityPrivileges() )
  {
    DebugPrintF::operator()(
      v34,
      0,
      "D3D11CreateDevice: The D3D11_CREATE_DEVICE_ENABLE_INCREASED_PRIORITY flag may only be used if the calling process "
      "possesses the SeIncBasePriority privilege.");
    Device = -2147024809;
    goto LABEL_49;
  }
  v18 = (unsigned int)IsProcessDWM();
  v19 = 1;
  v20 = (v13 & 0xFFFFFFFA) == 0 && v13 != D3D_DRIVER_TYPE_SOFTWARE;
  if ( (a4 & 0x8000000) != 0 )
  {
    v21 = 2;
    dword_18022B860 = 2;
    if ( !v20 || (_DWORD)v18 )
      goto LABEL_83;
  }
  else
  {
    v21 = 0;
    dword_18022B860 = 0;
    if ( v20 )
    {
      v21 = CheckConfigsForForcingD3D11on12Usage(v37, (unsigned int)v13, v18);
      dword_18022B860 = v21;
    }
  }
  v22 = a4 | 0x8000000;
  if ( !v21 )
    v22 = a4;
  v42 = v22;
  if ( !v37 )
  {
LABEL_25:
    if ( a11 )
    {
      if ( a5 && a5 <= a11 && a11 < &a5[a6] )
      {
        DebugPrintF::operator()(
          v34,
          0,
          "D3D11CreateDevice: The output parameter pFeatureLevel must not overlap with the input paramteter array pFeatureLevels.");
        goto LABEL_83;
      }
      *a11 = 0;
    }
    if ( !ValidSDKVersion(a7) )
      goto LABEL_83;
    v24 = 0;
    if ( v37 )
    {
      v32 = 0;
      v41 = 4;
      v24 = ((int (__fastcall *)(struct IUnknown *, GUID *, int *, int *))v37->lpVtbl[1].Release)(
              v37,
              &GUID_DDILevel,
              &v41,
              &v32) >= 0;
    }
    if ( a5 )
    {
      if ( a6 > 0xA )
        DebugPrintF::operator()(
          v34,
          1,
          "D3D11CreateDevice: There's no reason to pass in an array larger than %d elements, as it implies that either ce"
          "rtain D3D_FEATURE_LEVELs will be tried multiple times or never succeed. FeatureLevels was set to %d. Only D3D_"
          "FEATURE_LEVEL_9_1, D3D_FEATURE_LEVEL_9_2, D3D_FEATURE_LEVEL_9_3, D3D_FEATURE_LEVEL_10_0, D3D_FEATURE_LEVEL_10_"
          "1, D3D_FEATURE_LEVEL_11_0, D3D_FEATURE_LEVEL_11_1, D3D_FEATURE_LEVEL_12_0,  D3D_FEATURE_LEVEL_12_1 and D3D_FEA"
          "TURE_LEVEL_12_2 are recognized.",
          10,
          a6);
      v27 = 0;
      v32 = 0;
      for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
      {
        v29 = a5[i];
        if ( v29 <= D3D_FEATURE_LEVEL_11_0 )
        {
          if ( v29 != D3D_FEATURE_LEVEL_11_0 )
          {
            if ( v29 == D3D_FEATURE_LEVEL_9_3 || v29 == D3D_FEATURE_LEVEL_9_1 || v29 == D3D_FEATURE_LEVEL_9_2 )
            {
              v32 = ++v27;
            }
            else if ( v29 != D3D_FEATURE_LEVEL_10_0 && v29 != D3D_FEATURE_LEVEL_10_1 )
            {
LABEL_82:
              DebugPrintF::operator()(v34, 0, "Unrecognized D3D_FEATURE_LEVEL (%#x) in pFeatureLevels[ %d ].", v29, i);
              goto LABEL_83;
            }
          }
        }
        else if ( v29 != D3D_FEATURE_LEVEL_12_1 && v29 != D3D_FEATURE_LEVEL_11_1 && v29 != D3D_FEATURE_LEVEL_12_0 )
        {
          if ( v29 != (D3D_FEATURE_LEVEL_12_0|0x200) )
            goto LABEL_82;
          DebugPrintF::operator()(
            v34,
            1,
            "pFeatureLevels includes FEATURE_LEVEL_12_2, which is not supported with Direct3D 11.");
          v27 = v32;
        }
      }
      if ( v24 )
      {
        if ( !v27 )
        {
          DebugPrintF::operator()(
            v34,
            0,
            "D3D11CreateDevice: The adapter obtained via IDXGIDevice::GetAdapter from a D3D_FEATURE_LEVEL_9_* device can "
            "only be used to create other feature level 9 devices.  Because this device creation call only requests featu"
            "re level 10 or higher it will fail.");
          Device = -2005270524;
          goto LABEL_48;
        }
        if ( v27 != a6 )
        {
          DebugPrintF::operator()(
            v34,
            0,
            "D3D11CreateDevice: The adapter obtained via IDXGIDevice::GetAdapter from a D3D_FEATURE_LEVEL_9_* device can "
            "only be used to create other feature level 9 devices.  Higher feature levels are being ignored.");
          v15 = FilterNon9FeatureLevels(a5, a6, (enum D3D_FEATURE_LEVEL (*)[3])v48);
          v14 = v48;
        }
      }
      v13 = v33;
      goto LABEL_38;
    }
    if ( a6 )
      goto LABEL_83;
    v14 = (enum D3D_FEATURE_LEVEL *)qword_1801F4B60;
    if ( !v24 )
      v14 = (enum D3D_FEATURE_LEVEL *)&qword_1801F4B70;
    v15 = v24 ? 3 : 6;
LABEL_38:
    if ( v37 )
    {
      if ( v13 == D3D_DRIVER_TYPE_UNKNOWN )
      {
LABEL_40:
        v25 = v45;
        if ( !v45 )
        {
LABEL_41:
          if ( v46 && v44 || (v19 = 0, a12) )
          {
            v30 = (struct ID3D11Device **)&v43;
            if ( a10 )
              v30 = a10;
            v16 = v30;
          }
          Device = D3D11CoreCreateDevice(0, v37, v13, v25, v42, v14, v15, a7, v16, a11);
          if ( Device >= 0 )
          {
            if ( !v19
              || (((void (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))(*v16)->lpVtbl->QueryInterface)(
                    *v16,
                    &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
                    &v40),
                  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 56LL))(v40, &v39),
                  (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v39 + 48LL))(
                    v39,
                    &GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369,
                    &v38),
                  Device = (*(__int64 (__fastcall **)(__int64, struct ID3D11Device *, const struct DXGI_SWAP_CHAIN_DESC *, struct IDXGISwapChain **))(*(_QWORD *)v38 + 80LL))(
                             v38,
                             *v16,
                             v46,
                             v44),
                  Device >= 0) )
            {
              if ( a12 )
                ((void (__fastcall *)(struct ID3D11Device *, struct ID3D11DeviceContext **))(*v16)->lpVtbl->GetImmediateContext)(
                  *v16,
                  a12);
              LogCreatedDeviceTelemetry(v16, v13, v14, v15);
            }
          }
          goto LABEL_48;
        }
        DebugPrintF::operator()(
          v34,
          0,
          "D3D11CreateDevice: When creating a non-D3D_DRIVER_TYPE_SOFTWARE device, Software handle must be NULL.");
        goto LABEL_83;
      }
      DebugPrintF::operator()(
        v34,
        0,
        "D3D11CreateDevice: When creating a device from an existing adapter (i.e. pAdapter is non-NULL), DriverType must "
        "be D3D_DRIVER_TYPE_UNKNOWN.");
    }
    else
    {
      if ( v13 )
      {
        if ( v13 == D3D_DRIVER_TYPE_SOFTWARE )
        {
          v25 = v45;
          if ( !v45 )
          {
            DebugPrintF::operator()(
              v34,
              0,
              "D3D11CreateDevice: When creating a D3D_DRIVER_TYPE_SOFTWARE device, Software handle must be non-NULL.");
            goto LABEL_83;
          }
          goto LABEL_41;
        }
        goto LABEL_40;
      }
      DebugPrintF::operator()(
        v34,
        0,
        "D3D11CreateDevice: When creating a device without an adapter (i.e. pAdapter is NULL), the DriverType designates "
        "the type of adapter to use; and must not be D3D_DRIVER_TYPE_UNKNOWN.");
    }
LABEL_83:
    Device = -2147024809;
LABEL_48:
    v17 = a11;
LABEL_49:
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
    }
    if ( v39 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v39 = 0;
    }
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v40 = 0;
    }
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
    if ( Device < 0 )
    {
      v31 = v44;
      if ( v44 && *v44 )
      {
        ((void (__fastcall *)(struct IDXGISwapChain *))(*v44)->lpVtbl->Release)(*v44);
        *v31 = 0;
      }
      if ( v16 && *v16 )
      {
        ((void (__fastcall *)(struct ID3D11Device *))(*v16)->lpVtbl->Release)(*v16);
        *v16 = 0;
      }
      if ( v17 )
        *v17 = 0;
      if ( a12 && *a12 )
      {
        ((void (__fastcall *)(_QWORD))(*a12)->lpVtbl->Release)(*a12);
        *a12 = 0;
      }
    }
    goto LABEL_58;
  }
  v36 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v37->lpVtbl->QueryInterface)(
         v37,
         &GUID_29038f61_3839_4626_91fd_086879011a05,
         &v36) < 0
    || (memset_0(v47, 0, 0x138u), (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v36 + 80LL))(v36, v47) < 0)
    || (v47[304] & 1) == 0 )
  {
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    goto LABEL_25;
  }
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  Device = -2005270524;
LABEL_58:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v35);
  SafeHMODULE::~SafeHMODULE((SafeHMODULE *)v34);
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x18004a080  push    rbp
0x18004a082  push    rbx
0x18004a083  push    rsi
0x18004a084  push    rdi
0x18004a085  push    r12
0x18004a087  push    r13
0x18004a089  push    r14
0x18004a08b  push    r15
0x18004a08d  lea     rbp, [rsp-128h]
0x18004a095  sub     rsp, 228h
0x18004a09c  mov     rax, cs:__security_cookie
0x18004a0a3  xor     rax, rsp
0x18004a0a6  mov     [rbp+160h+var_50], rax
0x18004a0ad  mov     ebx, r9d
0x18004a0b0  mov     [rbp+160h+var_1B0], r8
0x18004a0b4  mov     r13d, edx
0x18004a0b7  mov     [rsp+260h+var_204], edx
0x18004a0bb  mov     [rsp+260h+var_1E8], rcx
0x18004a0c0  mov     r14, [rbp+160h+arg_20]
0x18004a0c7  mov     edi, [rbp+160h+arg_28]
0x18004a0cd  mov     rax, [rbp+160h+arg_38]
0x18004a0d4  mov     [rbp+160h+var_1A8], rax
0x18004a0d8  mov     rax, [rbp+160h+arg_40]
0x18004a0df  mov     [rbp+160h+var_1B8], rax
0x18004a0e3  mov     rsi, [rbp+160h+arg_48]
0x18004a0ea  mov     r15, [rbp+160h+arg_50]
0x18004a0f1  mov     [rsp+260h+var_210], r15
0x18004a0f6  mov     r12, [rbp+160h+arg_58]
0x18004a0fd  xor     ecx, ecx
0x18004a0ff  test    rax, rax
0x18004a102  jnz     loc_18004A549
0x18004a108  test    rsi, rsi
0x18004a10b  jnz     loc_18004A443
0x18004a111  test    r12, r12
0x18004a114  jnz     loc_18004A44B
0x18004a11a  mov     edx, ebx; unsigned int
0x18004a11c  lea     rcx, [rsp+260h+var_200]; this
0x18004a121  call    ??0DebugPrintF@@QEAA@I@Z; DebugPrintF::DebugPrintF(uint)
0x18004a126  nop
0x18004a127  xor     eax, eax
0x18004a129  mov     [rbp+160h+var_1C0], rax
0x18004a12d  mov     [rbp+160h+var_1D0], rax
0x18004a131  mov     [rbp+160h+var_1D8], rax
0x18004a135  mov     [rbp+160h+var_1E0], rax
0x18004a139  bt      ebx, 0Ch
0x18004a13d  jb      loc_18004A48D
0x18004a143  call    ?IsProcessDWM@@YAHXZ; IsProcessDWM(void)
0x18004a148  mov     r8d, eax
0x18004a14b  mov     r15d, 1
0x18004a151  test    r13d, 0FFFFFFFAh
0x18004a158  jnz     loc_18004A551
0x18004a15e  cmp     r13d, 4
0x18004a162  jz      loc_18004A551
0x18004a168  mov     cl, r15b
0x18004a16b  bt      ebx, 1Bh
0x18004a16f  jb      loc_18004A558
0x18004a175  xor     eax, eax
0x18004a177  mov     cs:dword_18022B860, eax
0x18004a17d  test    cl, cl
0x18004a17f  jz      short loc_18004A194
0x18004a181  mov     edx, r13d
0x18004a184  mov     rcx, [rsp+260h+var_1E8]
0x18004a189  call    ?CheckConfigsForForcingD3D11on12Usage@@YA?AW4D3D11On12Reason@@PEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@H@Z; CheckConfigsForForcingD3D11on12Usage(IDXGIAdapter *,D3D_DRIVER_TYPE,int)
0x18004a18e  mov     cs:dword_18022B860, eax
0x18004a194  mov     ecx, ebx
0x18004a196  bts     ecx, 1Bh
0x18004a19a  test    eax, eax
0x18004a19c  cmovz   ecx, ebx
0x18004a19f  mov     [rbp+160h+var_1C4], ecx
0x18004a1a2  mov     rcx, [rsp+260h+var_1E8]
0x18004a1a7  test    rcx, rcx
0x18004a1aa  jz      loc_18004A23F
0x18004a1b0  mov     [rsp+260h+var_1F0], 0
0x18004a1b9  mov     rax, [rcx]
0x18004a1bc  lea     r8, [rsp+260h+var_1F0]
0x18004a1c1  lea     rdx, _GUID_29038f61_3839_4626_91fd_086879011a05
0x18004a1c8  mov     rax, [rax]
0x18004a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1d0  test    eax, eax
0x18004a1d2  js      short loc_18004A228
0x18004a1d4  xor     edx, edx; Val
0x18004a1d6  mov     r8d, 138h; Size
0x18004a1dc  lea     rcx, [rbp+160h+var_1A0]; void *
0x18004a1e0  call    memset_0
0x18004a1e5  mov     rcx, [rsp+260h+var_1F0]
0x18004a1ea  mov     rax, [rcx]
0x18004a1ed  lea     rdx, [rbp+160h+var_1A0]
0x18004a1f1  mov     rax, [rax+50h]
0x18004a1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1fa  test    eax, eax
0x18004a1fc  js      short loc_18004A228
0x18004a1fe  test    [rbp+160h+var_70], r15b
0x18004a205  jz      short loc_18004A228
0x18004a207  mov     rcx, [rsp+260h+var_1F0]
0x18004a20c  test    rcx, rcx
0x18004a20f  jz      short loc_18004A21E
0x18004a211  mov     rax, [rcx]
0x18004a214  mov     rax, [rax+10h]
0x18004a218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a21d  nop
0x18004a21e  mov     ebx, 887A0004h
0x18004a223  jmp     loc_18004A3A4
0x18004a228  mov     rcx, [rsp+260h+var_1F0]
0x18004a22d  test    rcx, rcx
0x18004a230  jz      short loc_18004A23F
0x18004a232  mov     rax, [rcx]
0x18004a235  mov     rax, [rax+10h]
0x18004a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a23e  nop
0x18004a23f  mov     rdx, [rsp+260h+var_210]
0x18004a244  test    rdx, rdx
0x18004a247  jz      short loc_18004A266
0x18004a249  test    r14, r14
0x18004a24c  jz      short loc_18004A260
0x18004a24e  cmp     r14, rdx
0x18004a251  ja      short loc_18004A260
0x18004a253  lea     rcx, [r14+rdi*4]
0x18004a257  cmp     rdx, rcx
0x18004a25a  jb      loc_18004A594
0x18004a260  mov     dword ptr [rdx], 0
0x18004a266  mov     ecx, [rbp+160h+arg_30]; unsigned int
0x18004a26c  call    ?ValidSDKVersion@@YA_NI@Z; ValidSDKVersion(uint)
0x18004a271  test    al, al
0x18004a273  jz      loc_18004A58A
0x18004a279  xor     bl, bl
0x18004a27b  mov     rcx, [rsp+260h+var_1E8]
0x18004a280  test    rcx, rcx
0x18004a283  jnz     loc_18004A454
0x18004a289  test    r14, r14
0x18004a28c  jnz     loc_18004A3DD
0x18004a292  test    edi, edi
0x18004a294  jnz     loc_18004A58A
0x18004a29a  lea     rax, qword_1801F4B70
0x18004a2a1  lea     r14, qword_1801F4B60
0x18004a2a8  test    bl, bl
0x18004a2aa  cmovz   r14, rax
0x18004a2ae  neg     bl
0x18004a2b0  sbb     edi, edi
0x18004a2b2  and     edi, 0FFFFFFFDh
0x18004a2b5  add     edi, 6
0x18004a2b8  mov     rcx, [rsp+260h+var_1E8]
0x18004a2bd  test    rcx, rcx
0x18004a2c0  jz      loc_18004A67D
0x18004a2c6  test    r13d, r13d
0x18004a2c9  jnz     loc_18004A671
0x18004a2cf  mov     r9, [rbp+160h+var_1B0]
0x18004a2d3  test    r9, r9
0x18004a2d6  jnz     loc_18004A59D
0x18004a2dc  cmp     [rbp+160h+var_1A8], 0
0x18004a2e1  jnz     loc_18004A692
0x18004a2e7  xor     r15b, r15b
0x18004a2ea  test    r12, r12
0x18004a2ed  jnz     loc_18004A69D
0x18004a2f3  mov     rax, [rsp+260h+var_210]
0x18004a2f8  mov     [rsp+260h+var_218], rax
0x18004a2fd  mov     [rsp+260h+var_220], rsi
0x18004a302  mov     eax, [rbp+160h+arg_30]
0x18004a308  mov     [rsp+260h+var_228], eax
0x18004a30c  mov     [rsp+260h+var_230], edi
0x18004a310  mov     [rsp+260h+var_238], r14
0x18004a315  mov     eax, [rbp+160h+var_1C4]
0x18004a318  mov     [rsp+260h+var_240], eax
0x18004a31c  mov     r8d, r13d
0x18004a31f  mov     rdx, rcx
0x18004a322  xor     ecx, ecx
0x18004a324  call    D3D11CoreCreateDevice
0x18004a329  mov     ebx, eax
0x18004a32b  test    eax, eax
0x18004a32d  js      short loc_18004A363
0x18004a32f  test    r15b, r15b
0x18004a332  jnz     loc_18004A4B7
0x18004a338  test    r12, r12
0x18004a33b  jz      short loc_18004A352
0x18004a33d  mov     rcx, [rsi]
0x18004a340  mov     rax, [rcx]
0x18004a343  mov     rdx, r12
0x18004a346  mov     rax, [rax+140h]
0x18004a34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a352  mov     r9d, edi; unsigned int
0x18004a355  mov     r8, r14; enum D3D_FEATURE_LEVEL *
0x18004a358  mov     edx, r13d; enum D3D_DRIVER_TYPE
0x18004a35b  mov     rcx, rsi; struct ID3D11Device **
0x18004a35e  call    ?LogCreatedDeviceTelemetry@@YAXPEAPEAUID3D11Device@@W4D3D_DRIVER_TYPE@@PEBW4D3D_FEATURE_LEVEL@@I@Z; LogCreatedDeviceTelemetry(ID3D11Device * *,D3D_DRIVER_TYPE,D3D_FEATURE_LEVEL const *,uint)
0x18004a363  mov     r15, [rsp+260h+var_210]
0x18004a368  mov     rcx, [rbp+160h+var_1E0]
0x18004a36c  test    rcx, rcx
0x18004a36f  jnz     loc_18004A6B0
0x18004a375  mov     rcx, [rbp+160h+var_1D8]
0x18004a379  test    rcx, rcx
0x18004a37c  jnz     loc_18004A6C9
0x18004a382  mov     rcx, [rbp+160h+var_1D0]
0x18004a386  test    rcx, rcx
0x18004a389  jnz     loc_18004A6E2
0x18004a38f  mov     rcx, [rbp+160h+var_1C0]
0x18004a393  test    rcx, rcx
0x18004a396  jnz     loc_18004A6FB
0x18004a39c  test    ebx, ebx
0x18004a39e  js      loc_18004A714
0x18004a3a4  lea     rcx, [rsp+260h+var_1F8]
0x18004a3a9  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18004a3ae  lea     rcx, [rsp+260h+var_200]; this
0x18004a3b3  call    ??1SafeHMODULE@@QEAA@XZ; SafeHMODULE::~SafeHMODULE(void)
0x18004a3b8  mov     eax, ebx
0x18004a3ba  mov     rcx, [rbp+160h+var_50]
0x18004a3c1  xor     rcx, rsp; StackCookie
0x18004a3c4  call    __security_check_cookie
0x18004a3c9  add     rsp, 228h
0x18004a3d0  pop     r15
0x18004a3d2  pop     r14
0x18004a3d4  pop     r13
0x18004a3d6  pop     r12
0x18004a3d8  pop     rdi
0x18004a3d9  pop     rsi
0x18004a3da  pop     rbx
0x18004a3db  pop     rbp
0x18004a3dc  retn
0x18004a3dd  mov     r9d, 0Ah
0x18004a3e3  cmp     edi, r9d
0x18004a3e6  ja      loc_18004A5B2
0x18004a3ec  xor     ecx, ecx
0x18004a3ee  mov     [rsp+260h+var_208], ecx
0x18004a3f2  xor     r13d, r13d
0x18004a3f5  cmp     r13d, edi
0x18004a3f8  jnb     short loc_18004A419
0x18004a3fa  mov     r9d, [r14+r13*4]
0x18004a3fe  cmp     r9d, 0B000h
0x18004a405  jle     short loc_18004A42B
0x18004a407  cmp     r9d, 0C100h
0x18004a40e  jnz     loc_18004A608
0x18004a414  add     r13d, r15d
0x18004a417  jmp     short loc_18004A3F5
0x18004a419  test    bl, bl
0x18004a41b  jnz     loc_18004A64C
0x18004a421  mov     r13d, [rsp+260h+var_204]
0x18004a426  jmp     loc_18004A2B8
0x18004a42b  jz      short loc_18004A414
0x18004a42d  cmp     r9d, 9300h
0x18004a434  jnz     loc_18004A5CF
0x18004a43a  add     ecx, r15d
0x18004a43d  mov     [rsp+260h+var_208], ecx
0x18004a441  jmp     short loc_18004A414
0x18004a443  mov     [rsi], rcx
0x18004a446  jmp     loc_18004A111
0x18004a44b  mov     [r12], rcx
0x18004a44f  jmp     loc_18004A11A
0x18004a454  mov     [rsp+260h+var_208], 0
0x18004a45c  mov     [rbp+160h+var_1C8], 4
0x18004a463  mov     rax, [rcx]
0x18004a466  lea     r9, [rsp+260h+var_208]
0x18004a46b  lea     r8, [rbp+160h+var_1C8]
0x18004a46f  lea     rdx, GUID_DDILevel
0x18004a476  mov     rax, [rax+28h]
0x18004a47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a47f  movzx   ebx, bl
0x18004a482  test    eax, eax
0x18004a484  cmovns  ebx, r15d
0x18004a488  jmp     loc_18004A289
0x18004a48d  call    ?CurrentProcessHasIncreasedPriorityPrivileges@@YA_NXZ; CurrentProcessHasIncreasedPriorityPrivileges(void)
0x18004a492  test    al, al
0x18004a494  jnz     loc_18004A143
0x18004a49a  lea     r8, aD3d11createdev_12; "D3D11CreateDevice: The D3D11_CREATE_DEV"...
0x18004a4a1  xor     edx, edx
0x18004a4a3  lea     rcx, [rsp+260h+var_200]
0x18004a4a8  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x18004a4ad  mov     ebx, 80070057h
0x18004a4b2  jmp     loc_18004A368
0x18004a4b7  mov     rcx, [rsi]
0x18004a4ba  mov     rax, [rcx]
0x18004a4bd  lea     r8, [rbp+160h+var_1D0]
0x18004a4c1  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18004a4c8  mov     rax, [rax]
0x18004a4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4d0  mov     rcx, [rbp+160h+var_1D0]
0x18004a4d4  mov     rax, [rcx]
0x18004a4d7  lea     rdx, [rbp+160h+var_1D8]
0x18004a4db  mov     rax, [rax+38h]
0x18004a4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4e4  mov     rcx, [rbp+160h+var_1D8]
0x18004a4e8  mov     rax, [rcx]
0x18004a4eb  lea     r8, [rbp+160h+var_1E0]
0x18004a4ef  lea     rdx, _GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369
0x18004a4f6  mov     rax, [rax+30h]
0x18004a4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4ff  mov     rcx, [rbp+160h+var_1E0]
0x18004a503  mov     rax, [rcx]
0x18004a506  mov     r9, [rbp+160h+var_1B8]
0x18004a50a  mov     r8, [rbp+160h+var_1A8]
0x18004a50e  mov     rdx, [rsi]
0x18004a511  mov     rax, [rax+50h]
0x18004a515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a51a  mov     ebx, eax
0x18004a51c  test    eax, eax
0x18004a51e  jns     loc_18004A338
0x18004a524  jmp     loc_18004A363
0x18004a529  cmp     r13d, 4
0x18004a52d  jnz     loc_18004A2CF
0x18004a533  mov     r9, [rbp+160h+var_1B0]
0x18004a537  test    r9, r9
0x18004a53a  jnz     loc_18004A2DC
0x18004a540  lea     r8, aD3d11createdev_2; "D3D11CreateDevice: When creating a D3D_"...
  ... truncated ...
```
