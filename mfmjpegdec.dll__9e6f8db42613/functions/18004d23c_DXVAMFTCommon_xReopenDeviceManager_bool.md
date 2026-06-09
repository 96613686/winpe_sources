# DXVAMFTCommon::xReopenDeviceManager(bool)

- ea: `0x18004d23c`
- end: `0x18004d693`
- name: `?xReopenDeviceManager@DXVAMFTCommon@@AEAAJ_N@Z`
- size: `1111`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004ccc0`
- `0x18004d134`

## callees

- `0x180020598`
- `0x180041668`
- `0x180043324`
- `0x180044d78`
- `0x18004a11c`
- `0x18004aa94`
- `0x18004bd00`
- `0x18004c424`
- `0x18004d23c`
- `0x18006ed38`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DXVAMFTCommon::xReopenDeviceManager(DXVAMFTCommon *this, char a2)
{
  char v2; // di
  int v4; // r14d
  _QWORD *v5; // r12
  _QWORD *v6; // r15
  _QWORD *v7; // r13
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, GUID *, struct ID3D12Device **); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, GUID *, struct ID3D11Device **); // rbx
  int v13; // r14d
  struct ID3D11Device *v14; // rbx
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rdi
  struct IDXGIAdapter4 *v16; // rdi
  HRESULT (__stdcall *EnumOutputs)(IDXGIAdapter4 *, UINT, IDXGIOutput **); // rbx
  void (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v19)(_QWORD, GUID *, struct IDXGIAdapter4 **); // rdi
  bool v20; // al
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  unsigned int v26; // ebx
  struct ID3D12Device *v28[3]; // [rsp+30h] [rbp-18h] BYREF
  struct ID3D11Device *v29; // [rsp+90h] [rbp+48h] BYREF
  char v30; // [rsp+98h] [rbp+50h]
  struct IDXGIAdapter4 *v31; // [rsp+A0h] [rbp+58h] BYREF
  void (__fastcall ***v32)(_QWORD, GUID *, struct IDXGIAdapter4 **); // [rsp+A8h] [rbp+60h] BYREF

  v30 = a2;
  v2 = a2;
  v4 = 0;
  v5 = (_QWORD *)((char *)this + 416);
  v6 = (_QWORD *)((char *)this + 400);
  if ( *((_QWORD *)this + 52) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 24LL))(*v6);
    *v5 = 0;
    v7 = (_QWORD *)((char *)this + 416);
  }
  else
  {
    v7 = (_QWORD *)((char *)this + 416);
  }
  *(_QWORD *)((char *)this + 340) = 0;
  if ( !*v6 || (*(int (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v6 + 48LL))(*v6, v5) < 0 )
    goto LABEL_29;
  v29 = 0;
  v28[0] = 0;
  v32 = 0;
  v8 = *v6;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct ID3D12Device **))(*(_QWORD *)*v6 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)v28);
  v10 = v9(v8, *v5, &IID_ID3D12Device, v28);
  if ( v10 < 0 )
  {
    v11 = *v6;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct ID3D11Device **))(*(_QWORD *)*v6 + 32LL);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v29);
    v13 = v12(v11, *v7, &IID_ID3D11Device, &v29);
    if ( v13 >= 0 )
    {
      v31 = 0;
      v14 = v29;
      QueryInterface = v29->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v31);
      if ( ((int (__fastcall *)(struct ID3D11Device *, GUID *, struct IDXGIAdapter4 **))QueryInterface)(
             v14,
             &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
             &v31) >= 0 )
      {
        v16 = v31;
        EnumOutputs = v31->lpVtbl->EnumOutputs;
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v32);
        ((void (__fastcall *)(struct IDXGIAdapter4 *, void (__fastcall ****)(_QWORD, GUID *, struct IDXGIAdapter4 **)))EnumOutputs)(
          v16,
          &v32);
      }
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v31);
      if ( g_wppLevels >= 8u )
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
          (unsigned int)v13,
          this);
      if ( (int)DXVAMFTCommon::xCheckD3D11Availability(this, v29) >= 0 )
      {
        *((_DWORD *)this + 86) = 1;
        goto LABEL_18;
      }
    }
LABEL_19:
    v4 = -1072875818;
    goto LABEL_20;
  }
  if ( g_wppLevels >= 8u )
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
      (unsigned int)v10,
      this);
  if ( (int)DXVAMFTCommon::xCheckD3D12Availability(this, v28[0]) < 0 )
    goto LABEL_19;
  *((_DWORD *)this + 85) = 1;
LABEL_18:
  v4 = 0;
LABEL_20:
  v18 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v32;
  if ( v32 )
  {
    v31 = 0;
    v19 = **v32;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v31);
    v19(v18, &GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e, &v31);
    if ( v31 )
    {
      v20 = IsP010BlockedOnDevice(v31, (DXVAMFTCommon *)((char *)this + 428));
      *((_BYTE *)this + 16) = v20;
      if ( v20 )
      {
        if ( g_wppLevels )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, this);
      }
    }
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v31);
  }
  if ( v4 < 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 50) + 24LL))(
      *((_QWORD *)this + 50),
      *((_QWORD *)this + 52));
    *((_QWORD *)this + 52) = 0;
  }
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)v28);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v29);
  v6 = (_QWORD *)((char *)this + 400);
  v2 = v30;
LABEL_29:
  if ( g_wppLevels >= 8u )
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
      (unsigned int)v4,
      this);
  if ( v4 < 0 )
    goto LABEL_40;
  (*(void (__fastcall **)(DXVAMFTCommon *))(*(_QWORD *)this + 24LL))(this);
  v22 = *(_QWORD *)this;
  if ( *v6 )
  {
    LOBYTE(v21) = v2;
    v23 = (*(__int64 (__fastcall **)(DXVAMFTCommon *, __int64))(v22 + 32))(this, v21);
    v4 = v23;
    if ( g_wppLevels >= 8u )
    {
      v24 = 28;
LABEL_37:
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, v23, this);
    }
  }
  else
  {
    LOBYTE(v21) = 1;
    v23 = (*(__int64 (__fastcall **)(DXVAMFTCommon *, __int64))(v22 + 40))(this, v21);
    v4 = v23;
    *(_QWORD *)((char *)this + 340) = 0;
    if ( g_wppLevels >= 8u )
    {
      v24 = 29;
      goto LABEL_37;
    }
  }
  if ( v4 >= 0 )
  {
    *((_DWORD *)this + 83) = 0;
    return (unsigned int)v4;
  }
  v6 = (_QWORD *)((char *)this + 400);
LABEL_40:
  if ( *((_DWORD *)this + 82) )
  {
    (*(void (__fastcall **)(DXVAMFTCommon *))(*(_QWORD *)this + 24LL))(this);
    LOBYTE(v25) = *v6 == 0;
    v26 = (*(__int64 (__fastcall **)(DXVAMFTCommon *, __int64))(*(_QWORD *)this + 40LL))(this, v25);
    *(_QWORD *)((char *)this + 340) = 0;
    if ( !*v6 )
    {
      wistd::unique_ptr<CGenericDXVAAllocatorDecode,wistd::default_delete<CGenericDXVAAllocatorDecode>>::reset(
        (char *)this + 8,
        0);
      Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease((char *)this + 392);
    }
    if ( g_wppLevels >= 8u )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, v26, this);
    if ( *((_DWORD *)this + 84) && v2 )
      return v26;
  }
  else
  {
    *((_DWORD *)this + 83) = 1;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004d23c  mov     [rsp-40h+arg_8], dl
0x18004d240  push    rbp
0x18004d241  push    rbx
0x18004d242  push    rsi
0x18004d243  push    rdi
0x18004d244  push    r12
0x18004d246  push    r13
0x18004d248  push    r14
0x18004d24a  push    r15
0x18004d24c  mov     rbp, rsp
0x18004d24f  sub     rsp, 48h
0x18004d253  mov     dil, dl
0x18004d256  mov     rsi, rcx
0x18004d259  xor     ebx, ebx
0x18004d25b  mov     r14d, ebx
0x18004d25e  lea     r12, [rcx+1A0h]
0x18004d265  mov     rdx, [r12]
0x18004d269  lea     r15, [rcx+190h]
0x18004d270  test    rdx, rdx
0x18004d273  jz      short loc_18004D291
0x18004d275  mov     rcx, [r15]
0x18004d278  mov     rax, [rcx]
0x18004d27b  mov     rax, [rax+18h]
0x18004d27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d284  mov     [r12], rbx
0x18004d288  lea     r13, [rsi+1A0h]
0x18004d28f  jmp     short loc_18004D294
0x18004d291  mov     r13, r12
0x18004d294  mov     [rsi+154h], rbx
0x18004d29b  mov     rcx, [r15]
0x18004d29e  test    rcx, rcx
0x18004d2a1  jz      loc_18004D508
0x18004d2a7  mov     rax, [rcx]
0x18004d2aa  mov     rdx, r12
0x18004d2ad  mov     rax, [rax+30h]
0x18004d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2b6  test    eax, eax
0x18004d2b8  js      loc_18004D508
0x18004d2be  mov     [rbp+arg_0], rbx
0x18004d2c2  mov     [rbp+var_18], rbx
0x18004d2c6  mov     [rbp+arg_18], rbx
0x18004d2ca  mov     rdi, [r15]
0x18004d2cd  mov     rax, [rdi]
0x18004d2d0  mov     rbx, [rax+20h]
0x18004d2d4  lea     rcx, [rbp+var_18]
0x18004d2d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d2dd  lea     r9, [rbp+var_18]
0x18004d2e1  lea     r8, IID_ID3D12Device
0x18004d2e8  mov     rdx, [r12]
0x18004d2ec  mov     rcx, rdi
0x18004d2ef  mov     rax, rbx
0x18004d2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2f7  xor     r12d, r12d
0x18004d2fa  test    eax, eax
0x18004d2fc  js      short loc_18004D34E
0x18004d2fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18004d305  jb      short loc_18004D32B
0x18004d307  lea     edx, [r12+18h]
0x18004d30c  mov     [rsp+48h+var_28], rsi
0x18004d311  mov     r9d, eax
0x18004d314  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d322  mov     rcx, [rcx+10h]
0x18004d326  call    WPP_SF_dq
0x18004d32b  mov     rdx, [rbp+var_18]; struct ID3D12Device *
0x18004d32f  mov     rcx, rsi; this
0x18004d332  call    ?xCheckD3D12Availability@DXVAMFTCommon@@AEAAJPEAUID3D12Device@@@Z; DXVAMFTCommon::xCheckD3D12Availability(ID3D12Device *)
0x18004d337  test    eax, eax
0x18004d339  js      loc_18004D431
0x18004d33f  mov     dword ptr [rsi+154h], 1
0x18004d349  jmp     loc_18004D42C
0x18004d34e  mov     rdi, [r15]
0x18004d351  mov     rax, [rdi]
0x18004d354  mov     rbx, [rax+20h]
0x18004d358  lea     rcx, [rbp+arg_0]
0x18004d35c  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d361  lea     r9, [rbp+arg_0]
0x18004d365  lea     r8, IID_ID3D11Device
0x18004d36c  mov     rdx, [r13+0]
0x18004d370  mov     rcx, rdi
0x18004d373  mov     rax, rbx
0x18004d376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d37b  mov     r14d, eax
0x18004d37e  test    eax, eax
0x18004d380  js      loc_18004D431
0x18004d386  mov     [rbp+arg_10], r12
0x18004d38a  mov     rbx, [rbp+arg_0]
0x18004d38e  mov     rax, [rbx]
0x18004d391  mov     rdi, [rax]
0x18004d394  lea     rcx, [rbp+arg_10]
0x18004d398  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d39d  lea     r8, [rbp+arg_10]
0x18004d3a1  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18004d3a8  mov     rcx, rbx
0x18004d3ab  mov     rax, rdi
0x18004d3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3b3  nop
0x18004d3b4  test    eax, eax
0x18004d3b6  js      short loc_18004D3DC
0x18004d3b8  mov     rdi, [rbp+arg_10]
0x18004d3bc  mov     rax, [rdi]
0x18004d3bf  mov     rbx, [rax+38h]
0x18004d3c3  lea     rcx, [rbp+arg_18]
0x18004d3c7  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d3cc  lea     rdx, [rbp+arg_18]
0x18004d3d0  mov     rcx, rdi
0x18004d3d3  mov     rax, rbx
0x18004d3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3db  nop
0x18004d3dc  lea     rcx, [rbp+arg_10]
0x18004d3e0  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d3e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18004d3ec  jb      short loc_18004D412
0x18004d3ee  mov     edx, 19h
0x18004d3f3  mov     [rsp+48h+var_28], rsi
0x18004d3f8  mov     r9d, r14d
0x18004d3fb  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d402  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d409  mov     rcx, [rcx+10h]
0x18004d40d  call    WPP_SF_dq
0x18004d412  mov     rdx, [rbp+arg_0]; struct ID3D11Device *
0x18004d416  mov     rcx, rsi; this
0x18004d419  call    ?xCheckD3D11Availability@DXVAMFTCommon@@AEAAJPEAUID3D11Device@@@Z; DXVAMFTCommon::xCheckD3D11Availability(ID3D11Device *)
0x18004d41e  test    eax, eax
0x18004d420  js      short loc_18004D431
0x18004d422  mov     dword ptr [rsi+158h], 1
0x18004d42c  mov     r14d, r12d
0x18004d42f  jmp     short loc_18004D437
0x18004d431  mov     r14d, 0C00D36D6h
0x18004d437  mov     rbx, [rbp+arg_18]
0x18004d43b  test    rbx, rbx
0x18004d43e  jz      short loc_18004D4B8
0x18004d440  mov     [rbp+arg_10], r12
0x18004d444  mov     rax, [rbx]
0x18004d447  mov     rdi, [rax]
0x18004d44a  lea     rcx, [rbp+arg_10]
0x18004d44e  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d453  lea     r8, [rbp+arg_10]
0x18004d457  lea     rdx, _GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e
0x18004d45e  mov     rcx, rbx
0x18004d461  mov     rax, rdi
0x18004d464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d469  nop
0x18004d46a  mov     rcx, [rbp+arg_10]; struct IDXGIAdapter4 *
0x18004d46e  test    rcx, rcx
0x18004d471  jz      short loc_18004D4AF
0x18004d473  lea     rdx, [rsi+1ACh]; this
0x18004d47a  call    ?IsP010BlockedOnDevice@@YA_NPEAUIDXGIAdapter4@@AEAVWDDMVersionHelper@@@Z; IsP010BlockedOnDevice(IDXGIAdapter4 *,WDDMVersionHelper &)
0x18004d47f  mov     [rsi+10h], al
0x18004d482  test    al, al
0x18004d484  jz      short loc_18004D4AF
0x18004d486  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d48d  jb      short loc_18004D4AF
0x18004d48f  mov     edx, 1Ah
0x18004d494  mov     r9, rsi
0x18004d497  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d49e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d4a5  mov     rcx, [rcx+10h]
0x18004d4a9  call    WPP_SF_q
0x18004d4ae  nop
0x18004d4af  lea     rcx, [rbp+arg_10]
0x18004d4b3  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d4b8  test    r14d, r14d
0x18004d4bb  jns     short loc_18004D4DE
0x18004d4bd  mov     rcx, [rsi+190h]
0x18004d4c4  mov     rax, [rcx]
0x18004d4c7  mov     rdx, [rsi+1A0h]
0x18004d4ce  mov     rax, [rax+18h]
0x18004d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4d7  mov     [rsi+1A0h], r12
0x18004d4de  lea     rcx, [rbp+arg_18]
0x18004d4e2  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d4e7  nop
0x18004d4e8  lea     rcx, [rbp+var_18]
0x18004d4ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d4f1  nop
0x18004d4f2  lea     rcx, [rbp+arg_0]
0x18004d4f6  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004d4fb  lea     r15, [rsi+190h]
0x18004d502  mov     dil, [rbp+arg_8]
0x18004d506  jmp     short loc_18004D50B
0x18004d508  xor     r12d, r12d
0x18004d50b  mov     r13b, 8
0x18004d50e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004d515  jb      short loc_18004D53B
0x18004d517  mov     edx, 1Bh
0x18004d51c  mov     [rsp+48h+var_28], rsi
0x18004d521  mov     r9d, r14d
0x18004d524  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d52b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d532  mov     rcx, [rcx+10h]
0x18004d536  call    WPP_SF_dq
0x18004d53b  test    r14d, r14d
0x18004d53e  js      loc_18004D5D3
0x18004d544  mov     rax, [rsi]
0x18004d547  mov     rcx, rsi
0x18004d54a  mov     rax, [rax+18h]
0x18004d54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d553  mov     rax, [rsi]
0x18004d556  mov     rcx, rsi
0x18004d559  cmp     [r15], r12
0x18004d55c  jz      short loc_18004D57D
0x18004d55e  mov     dl, dil
0x18004d561  mov     rax, [rax+20h]
0x18004d565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d56a  mov     r14d, eax
0x18004d56d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004d574  jb      short loc_18004D5C3
0x18004d576  mov     edx, 1Ch
0x18004d57b  jmp     short loc_18004D5A4
0x18004d57d  mov     dl, 1
0x18004d57f  mov     rax, [rax+28h]
0x18004d583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d588  mov     r14d, eax
0x18004d58b  mov     qword ptr [rsi+154h], 0
0x18004d596  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004d59d  jb      short loc_18004D5C3
0x18004d59f  mov     edx, 1Dh
0x18004d5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5ab  mov     [rsp+48h+var_28], rsi
0x18004d5b0  mov     r9d, eax
0x18004d5b3  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d5ba  mov     rcx, [rcx+10h]
0x18004d5be  call    WPP_SF_dq
0x18004d5c3  test    r14d, r14d
0x18004d5c6  jns     loc_18004D66C
0x18004d5cc  lea     r15, [rsi+190h]
0x18004d5d3  cmp     [rsi+148h], r12d
0x18004d5da  jz      loc_18004D675
0x18004d5e0  mov     rax, [rsi]
0x18004d5e3  mov     rcx, rsi
0x18004d5e6  mov     rax, [rax+18h]
0x18004d5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5ef  mov     rax, [rsi]
0x18004d5f2  cmp     [r15], r12
0x18004d5f5  setz    dl
0x18004d5f8  mov     rcx, rsi
0x18004d5fb  mov     rax, [rax+28h]
0x18004d5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d604  mov     ebx, eax
0x18004d606  mov     qword ptr [rsi+154h], 0
0x18004d611  cmp     [r15], r12
0x18004d614  jnz     short loc_18004D62D
0x18004d616  lea     rcx, [rsi+8]
0x18004d61a  xor     edx, edx
0x18004d61c  call    ?reset@?$unique_ptr@VCGenericDXVAAllocatorDecode@@U?$default_delete@VCGenericDXVAAllocatorDecode@@@wistd@@@wistd@@QEAAXPEAVCGenericDXVAAllocatorDecode@@@Z; wistd::unique_ptr<CGenericDXVAAllocatorDecode,wistd::default_delete<CGenericDXVAAllocatorDecode>>::reset(CGenericDXVAAllocatorDecode *)
0x18004d621  lea     rcx, [rsi+188h]
0x18004d628  call    ?InternalRelease@?$ComPtr@VCDXVAFrameManagerGenericDecode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease(void)
0x18004d62d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004d634  jb      short loc_18004D65A
0x18004d636  mov     edx, 1Eh
0x18004d63b  mov     [rsp+48h+var_28], rsi
0x18004d640  mov     r9d, ebx
0x18004d643  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d651  mov     rcx, [rcx+10h]
0x18004d655  call    WPP_SF_dq
0x18004d65a  cmp     [rsi+150h], r12d
0x18004d661  jz      short loc_18004D67F
0x18004d663  test    dil, dil
0x18004d666  jz      short loc_18004D67F
0x18004d668  mov     eax, ebx
0x18004d66a  jmp     short loc_18004D682
0x18004d66c  mov     [rsi+14Ch], r12d
0x18004d673  jmp     short loc_18004D67F
0x18004d675  mov     dword ptr [rsi+14Ch], 1
0x18004d67f  mov     eax, r14d
0x18004d682  add     rsp, 48h
0x18004d686  pop     r15
0x18004d688  pop     r14
0x18004d68a  pop     r13
0x18004d68c  pop     r12
0x18004d68e  pop     rdi
0x18004d68f  pop     rsi
0x18004d690  pop     rbx
0x18004d691  pop     rbp
0x18004d692  retn
```
