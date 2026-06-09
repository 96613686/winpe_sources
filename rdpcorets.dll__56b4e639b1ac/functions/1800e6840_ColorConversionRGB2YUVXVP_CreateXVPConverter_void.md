# ColorConversionRGB2YUVXVP::CreateXVPConverter(void)

- ea: `0x1800e6840`
- end: `0x1800e6e51`
- name: `?CreateXVPConverter@ColorConversionRGB2YUVXVP@@QEAAJXZ`
- size: `1553`
- prototype: `__int64 __fastcall(ColorConversionRGB2YUVXVP *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e5560`
- `0x1800e6e60`
- `0x1800e6fa0`

## callees

- `0x18002e600`
- `0x180033da0`
- `0x1800598d0`
- `0x1800e6840`
- `0x1800e7b10`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e687f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e687f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e68b6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6917`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e69a4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6a61`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6b0e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6bba`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6c73`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6d27`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6df6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e68b6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6917`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e69a4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6a61`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6b0e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6bba`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6c73`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6d27`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e6df6`

## string_xrefs

- `0x1800e68bc`: `CoCreateInstance ColorConverter failed`

## pseudocode

```c
__int64 __fastcall ColorConversionRGB2YUVXVP::CreateXVPConverter(LPVOID *this)
{
  _QWORD *v1; // rdi
  HRESULT Instance; // ebx
  int ActivityIdPrefix; // eax
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  HRESULT v24; // [rsp+28h] [rbp-38h]
  HRESULT v25; // [rsp+28h] [rbp-38h]
  HRESULT v26; // [rsp+28h] [rbp-38h]
  HRESULT v27; // [rsp+28h] [rbp-38h]
  HRESULT v28; // [rsp+28h] [rbp-38h]
  HRESULT v29; // [rsp+28h] [rbp-38h]
  HRESULT v30; // [rsp+28h] [rbp-38h]
  HRESULT v31; // [rsp+28h] [rbp-38h]
  __int64 v32; // [rsp+30h] [rbp-30h] BYREF
  __int64 v33; // [rsp+38h] [rbp-28h] BYREF
  __int64 v34; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+48h] [rbp-18h]
  int v36; // [rsp+4Ch] [rbp-14h]

  v1 = this + 4;
  Instance = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, this + 4);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      v24 = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
        ActivityIdPrefix,
        (__int64)"CoCreateInstance ColorConverter failed",
        v24);
    }
    return (unsigned int)Instance;
  }
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v1;
  if ( !*v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
        v6,
        (__int64)"m_spXVPConverter");
    }
    return (unsigned int)-2147467261;
  }
  v33 = 0;
  v32 = 0;
  Instance = (**v5)(v5, &IID_IMFVideoProcessorControl, &v32);
  if ( Instance >= 0 )
  {
    v35 = *((_DWORD *)this + 2);
    v36 = *((_DWORD *)this + 3);
    v34 = 0;
    Instance = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 32LL))(v32, &v34);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v34);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v1 + 64LL))(*v1, &v33);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v33 + 168LL))(
                       v33,
                       &MF_XVP_DISABLE_FRC,
                       1);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID))(*(_QWORD *)*v1 + 184LL))(*v1, 2, this[9]);
            if ( Instance >= 0 )
            {
              v20 = v32;
              if ( v32 )
              {
                v32 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              v21 = v33;
              if ( v33 )
              {
                v33 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
              Instance = ColorConversionRGB2YUVXVP::SetInOutType((ColorConversionRGB2YUVXVP *)this);
              if ( Instance < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v22 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                v31 = Instance;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  28,
                  (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
                  v22,
                  (__int64)"SetInOutType() Failed",
                  v31);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v18 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                v30 = Instance;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
                  v18,
                  (__int64)"MFT_MESSAGE_SET_D3D_MANAGER failed",
                  v30);
              }
              v19 = v32;
              if ( v32 )
              {
                v32 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              v9 = v33;
              if ( v33 )
                goto LABEL_65;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
              v29 = Instance;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
                v16,
                (__int64)"Set MF_XVP_DISABLE_FRC failed",
                v29);
            }
            v17 = v32;
            if ( v32 )
            {
              v32 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            v9 = v33;
            if ( v33 )
              goto LABEL_65;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
            v28 = Instance;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
              v14,
              (__int64)"GetAttributes failed",
              v28);
          }
          v15 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          v9 = v33;
          if ( v33 )
            goto LABEL_65;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
          v27 = Instance;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
            v12,
            (__int64)"SetDestinationRectangle failed",
            v27);
        }
        v13 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v9 = v33;
        if ( v33 )
          goto LABEL_65;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
        v26 = Instance;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
          v10,
          (__int64)"SetSourceRectangle failed",
          v26);
      }
      v11 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v9 = v33;
      if ( v33 )
        goto LABEL_65;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      v25 = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids,
        v7,
        (__int64)"QueryInterface IID_IMFVideoProcessorControl failed",
        v25);
    }
    v8 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v33;
    if ( v33 )
    {
LABEL_65:
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e6840  mov     [rsp-18h+arg_10], rbx
0x1800e6845  push    rbp
0x1800e6846  push    rsi
0x1800e6847  push    rdi
0x1800e6848  mov     rbp, rsp
0x1800e684b  sub     rsp, 60h
0x1800e684f  mov     rax, cs:__security_cookie
0x1800e6856  xor     rax, rsp
0x1800e6859  mov     [rbp+var_10], rax
0x1800e685d  lea     rdi, [rcx+20h]
0x1800e6861  mov     rsi, rcx
0x1800e6864  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800e686b  mov     [rsp+60h+ppv], rdi; ppv
0x1800e6870  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800e6877  xor     edx, edx; pUnkOuter
0x1800e6879  mov     r8d, 1; dwClsContext
0x1800e687f  call    cs:__imp_CoCreateInstance
0x1800e6885  mov     ebx, eax
0x1800e6887  test    eax, eax
0x1800e6889  jns     short loc_1800E68F0
0x1800e688b  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6892  lea     rcx, WPP_GLOBAL_Control
0x1800e6899  cmp     rax, rcx
0x1800e689c  jz      loc_1800E6E33
0x1800e68a2  test    byte ptr [rax+1Ch], 8
0x1800e68a6  jz      loc_1800E6E33
0x1800e68ac  cmp     byte ptr [rax+19h], 2
0x1800e68b0  jb      loc_1800E6E33
0x1800e68b6  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e68bc  lea     rcx, aCocreateinstan_4; "CoCreateInstance ColorConverter failed"
0x1800e68c3  mov     [rsp+60h+var_38], ebx
0x1800e68c7  mov     [rsp+60h+ppv], rcx
0x1800e68cc  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e68d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e68da  mov     edx, 14h
0x1800e68df  mov     r9d, eax
0x1800e68e2  mov     rcx, [rcx+10h]
0x1800e68e6  call    WPP_SF_DsD
0x1800e68eb  jmp     loc_1800E6E33
0x1800e68f0  mov     rcx, [rdi]
0x1800e68f3  test    rcx, rcx
0x1800e68f6  jnz     short loc_1800E6952
0x1800e68f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800e68ff  lea     rcx, WPP_GLOBAL_Control
0x1800e6906  cmp     rax, rcx
0x1800e6909  jz      short loc_1800E6948
0x1800e690b  test    byte ptr [rax+1Ch], 8
0x1800e690f  jz      short loc_1800E6948
0x1800e6911  cmp     byte ptr [rax+19h], 2
0x1800e6915  jb      short loc_1800E6948
0x1800e6917  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e691d  lea     rcx, aMSpxvpconverte_1; "m_spXVPConverter"
0x1800e6924  mov     edx, 15h
0x1800e6929  mov     [rsp+60h+ppv], rcx
0x1800e692e  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6935  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e693c  mov     r9d, eax
0x1800e693f  mov     rcx, [rcx+10h]
0x1800e6943  call    WPP_SF_Ds
0x1800e6948  mov     ebx, 80004003h
0x1800e694d  jmp     loc_1800E6E33
0x1800e6952  mov     [rsp+60h+arg_8], r14
0x1800e695a  lea     r8, [rbp+var_30]
0x1800e695e  xor     r14d, r14d
0x1800e6961  lea     rdx, IID_IMFVideoProcessorControl
0x1800e6968  mov     [rbp+var_28], r14
0x1800e696c  mov     [rbp+var_30], r14
0x1800e6970  mov     rax, [rcx]
0x1800e6973  mov     rax, [rax]
0x1800e6976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e697b  mov     ebx, eax
0x1800e697d  test    eax, eax
0x1800e697f  jns     loc_1800E6A14
0x1800e6985  mov     rax, cs:WPP_GLOBAL_Control
0x1800e698c  lea     rcx, WPP_GLOBAL_Control
0x1800e6993  cmp     rax, rcx
0x1800e6996  jz      short loc_1800E69D9
0x1800e6998  test    byte ptr [rax+1Ch], 8
0x1800e699c  jz      short loc_1800E69D9
0x1800e699e  cmp     byte ptr [rax+19h], 2
0x1800e69a2  jb      short loc_1800E69D9
0x1800e69a4  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e69aa  lea     rcx, aQueryinterface_0; "QueryInterface IID_IMFVideoProcessorCon"...
0x1800e69b1  mov     [rsp+60h+var_38], ebx
0x1800e69b5  mov     [rsp+60h+ppv], rcx
0x1800e69ba  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e69c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e69c8  mov     edx, 16h
0x1800e69cd  mov     r9d, eax
0x1800e69d0  mov     rcx, [rcx+10h]
0x1800e69d4  call    WPP_SF_DsD
0x1800e69d9  mov     rcx, [rbp+var_30]
0x1800e69dd  test    rcx, rcx
0x1800e69e0  jz      short loc_1800E69F2
0x1800e69e2  mov     [rbp+var_30], r14
0x1800e69e6  mov     rax, [rcx]
0x1800e69e9  mov     rax, [rax+10h]
0x1800e69ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e69f2  mov     rcx, [rbp+var_28]
0x1800e69f6  test    rcx, rcx
0x1800e69f9  jz      loc_1800E6E2B
0x1800e69ff  mov     [rbp+var_28], r14
0x1800e6a03  mov     rax, [rcx]
0x1800e6a06  mov     rax, [rax+10h]
0x1800e6a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a0f  jmp     loc_1800E6E2B
0x1800e6a14  mov     eax, [rsi+8]
0x1800e6a17  lea     rdx, [rbp+var_20]
0x1800e6a1b  mov     rcx, [rbp+var_30]
0x1800e6a1f  mov     [rbp+var_18], eax
0x1800e6a22  mov     eax, [rsi+0Ch]
0x1800e6a25  mov     [rbp+var_14], eax
0x1800e6a28  mov     [rbp+var_20], r14
0x1800e6a2c  mov     rax, [rcx]
0x1800e6a2f  mov     rax, [rax+20h]
0x1800e6a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a38  mov     ebx, eax
0x1800e6a3a  test    eax, eax
0x1800e6a3c  jns     loc_1800E6AD1
0x1800e6a42  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6a49  lea     rcx, WPP_GLOBAL_Control
0x1800e6a50  cmp     rax, rcx
0x1800e6a53  jz      short loc_1800E6A96
0x1800e6a55  test    byte ptr [rax+1Ch], 8
0x1800e6a59  jz      short loc_1800E6A96
0x1800e6a5b  cmp     byte ptr [rax+19h], 2
0x1800e6a5f  jb      short loc_1800E6A96
0x1800e6a61  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e6a67  lea     rcx, aSetsourcerecta; "SetSourceRectangle failed"
0x1800e6a6e  mov     [rsp+60h+var_38], ebx
0x1800e6a72  mov     [rsp+60h+ppv], rcx
0x1800e6a77  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6a85  mov     edx, 17h
0x1800e6a8a  mov     r9d, eax
0x1800e6a8d  mov     rcx, [rcx+10h]
0x1800e6a91  call    WPP_SF_DsD
0x1800e6a96  mov     rcx, [rbp+var_30]
0x1800e6a9a  test    rcx, rcx
0x1800e6a9d  jz      short loc_1800E6AAF
0x1800e6a9f  mov     [rbp+var_30], r14
0x1800e6aa3  mov     rax, [rcx]
0x1800e6aa6  mov     rax, [rax+10h]
0x1800e6aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6aaf  mov     rcx, [rbp+var_28]
0x1800e6ab3  test    rcx, rcx
0x1800e6ab6  jz      loc_1800E6E2B
0x1800e6abc  mov     [rbp+var_28], r14
0x1800e6ac0  mov     rax, [rcx]
0x1800e6ac3  mov     rax, [rax+10h]
0x1800e6ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6acc  jmp     loc_1800E6E2B
0x1800e6ad1  mov     rcx, [rbp+var_30]
0x1800e6ad5  lea     rdx, [rbp+var_20]
0x1800e6ad9  mov     rax, [rcx]
0x1800e6adc  mov     rax, [rax+28h]
0x1800e6ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6ae5  mov     ebx, eax
0x1800e6ae7  test    eax, eax
0x1800e6ae9  jns     loc_1800E6B7E
0x1800e6aef  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6af6  lea     rcx, WPP_GLOBAL_Control
0x1800e6afd  cmp     rax, rcx
0x1800e6b00  jz      short loc_1800E6B43
0x1800e6b02  test    byte ptr [rax+1Ch], 8
0x1800e6b06  jz      short loc_1800E6B43
0x1800e6b08  cmp     byte ptr [rax+19h], 2
0x1800e6b0c  jb      short loc_1800E6B43
0x1800e6b0e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e6b14  lea     rcx, aSetdestination; "SetDestinationRectangle failed"
0x1800e6b1b  mov     [rsp+60h+var_38], ebx
0x1800e6b1f  mov     [rsp+60h+ppv], rcx
0x1800e6b24  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6b32  mov     edx, 18h
0x1800e6b37  mov     r9d, eax
0x1800e6b3a  mov     rcx, [rcx+10h]
0x1800e6b3e  call    WPP_SF_DsD
0x1800e6b43  mov     rcx, [rbp+var_30]
0x1800e6b47  test    rcx, rcx
0x1800e6b4a  jz      short loc_1800E6B5C
0x1800e6b4c  mov     [rbp+var_30], r14
0x1800e6b50  mov     rax, [rcx]
0x1800e6b53  mov     rax, [rax+10h]
0x1800e6b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6b5c  mov     rcx, [rbp+var_28]
0x1800e6b60  test    rcx, rcx
0x1800e6b63  jz      loc_1800E6E2B
0x1800e6b69  mov     [rbp+var_28], r14
0x1800e6b6d  mov     rax, [rcx]
0x1800e6b70  mov     rax, [rax+10h]
0x1800e6b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6b79  jmp     loc_1800E6E2B
0x1800e6b7e  mov     rcx, [rdi]
0x1800e6b81  lea     rdx, [rbp+var_28]
0x1800e6b85  mov     rax, [rcx]
0x1800e6b88  mov     rax, [rax+40h]
0x1800e6b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6b91  mov     ebx, eax
0x1800e6b93  test    eax, eax
0x1800e6b95  jns     loc_1800E6C2A
0x1800e6b9b  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6ba2  lea     rcx, WPP_GLOBAL_Control
0x1800e6ba9  cmp     rax, rcx
0x1800e6bac  jz      short loc_1800E6BEF
0x1800e6bae  test    byte ptr [rax+1Ch], 8
0x1800e6bb2  jz      short loc_1800E6BEF
0x1800e6bb4  cmp     byte ptr [rax+19h], 2
0x1800e6bb8  jb      short loc_1800E6BEF
0x1800e6bba  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e6bc0  lea     rcx, aGetattributesF; "GetAttributes failed"
0x1800e6bc7  mov     [rsp+60h+var_38], ebx
0x1800e6bcb  mov     [rsp+60h+ppv], rcx
0x1800e6bd0  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6bde  mov     edx, 19h
0x1800e6be3  mov     r9d, eax
0x1800e6be6  mov     rcx, [rcx+10h]
0x1800e6bea  call    WPP_SF_DsD
0x1800e6bef  mov     rcx, [rbp+var_30]
0x1800e6bf3  test    rcx, rcx
0x1800e6bf6  jz      short loc_1800E6C08
0x1800e6bf8  mov     [rbp+var_30], r14
0x1800e6bfc  mov     rax, [rcx]
0x1800e6bff  mov     rax, [rax+10h]
0x1800e6c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6c08  mov     rcx, [rbp+var_28]
0x1800e6c0c  test    rcx, rcx
0x1800e6c0f  jz      loc_1800E6E2B
0x1800e6c15  mov     [rbp+var_28], r14
0x1800e6c19  mov     rax, [rcx]
0x1800e6c1c  mov     rax, [rax+10h]
0x1800e6c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6c25  jmp     loc_1800E6E2B
0x1800e6c2a  mov     rcx, [rbp+var_28]
0x1800e6c2e  lea     rdx, MF_XVP_DISABLE_FRC
0x1800e6c35  mov     r8d, 1
0x1800e6c3b  mov     rax, [rcx]
0x1800e6c3e  mov     rax, [rax+0A8h]
0x1800e6c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6c4a  mov     ebx, eax
0x1800e6c4c  test    eax, eax
0x1800e6c4e  jns     loc_1800E6CE3
0x1800e6c54  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6c5b  lea     rcx, WPP_GLOBAL_Control
0x1800e6c62  cmp     rax, rcx
0x1800e6c65  jz      short loc_1800E6CA8
0x1800e6c67  test    byte ptr [rax+1Ch], 8
0x1800e6c6b  jz      short loc_1800E6CA8
0x1800e6c6d  cmp     byte ptr [rax+19h], 2
0x1800e6c71  jb      short loc_1800E6CA8
0x1800e6c73  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e6c79  lea     rcx, aSetMfXvpDisabl; "Set MF_XVP_DISABLE_FRC failed"
0x1800e6c80  mov     [rsp+60h+var_38], ebx
0x1800e6c84  mov     [rsp+60h+ppv], rcx
0x1800e6c89  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6c90  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6c97  mov     edx, 1Ah
0x1800e6c9c  mov     r9d, eax
0x1800e6c9f  mov     rcx, [rcx+10h]
0x1800e6ca3  call    WPP_SF_DsD
0x1800e6ca8  mov     rcx, [rbp+var_30]
0x1800e6cac  test    rcx, rcx
0x1800e6caf  jz      short loc_1800E6CC1
0x1800e6cb1  mov     [rbp+var_30], r14
0x1800e6cb5  mov     rax, [rcx]
0x1800e6cb8  mov     rax, [rax+10h]
0x1800e6cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6cc1  mov     rcx, [rbp+var_28]
0x1800e6cc5  test    rcx, rcx
0x1800e6cc8  jz      loc_1800E6E2B
0x1800e6cce  mov     [rbp+var_28], r14
0x1800e6cd2  mov     rax, [rcx]
0x1800e6cd5  mov     rax, [rax+10h]
0x1800e6cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6cde  jmp     loc_1800E6E2B
0x1800e6ce3  mov     rcx, [rdi]
0x1800e6ce6  mov     edx, 2
0x1800e6ceb  mov     r8, [rsi+48h]
0x1800e6cef  mov     rax, [rcx]
0x1800e6cf2  mov     rax, [rax+0B8h]
0x1800e6cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6cfe  mov     ebx, eax
0x1800e6d00  test    eax, eax
0x1800e6d02  jns     loc_1800E6D97
0x1800e6d08  mov     rax, cs:WPP_GLOBAL_Control
0x1800e6d0f  lea     rcx, WPP_GLOBAL_Control
0x1800e6d16  cmp     rax, rcx
0x1800e6d19  jz      short loc_1800E6D5C
0x1800e6d1b  test    byte ptr [rax+1Ch], 8
0x1800e6d1f  jz      short loc_1800E6D5C
0x1800e6d21  cmp     byte ptr [rax+19h], 2
0x1800e6d25  jb      short loc_1800E6D5C
0x1800e6d27  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e6d2d  lea     rcx, aMftMessageSetD; "MFT_MESSAGE_SET_D3D_MANAGER failed"
0x1800e6d34  mov     [rsp+60h+var_38], ebx
0x1800e6d38  mov     [rsp+60h+ppv], rcx
0x1800e6d3d  lea     r8, WPP_844ba8de81fe3ffc73d6c7268d2d6f32_Traceguids
0x1800e6d44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6d4b  mov     edx, 1Bh
  ... truncated ...
```
