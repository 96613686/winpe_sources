# CDX11DecodeCore::D3DDeviceOpen(DXVAVideoDesc const &,DXVAParams_tag const *,D3D11_VIDEO_DECODER_CONFIG const &,bool,bool,bool,bool,DXVAVideoDesc &,CDXVABufferTracker * *)

- ea: `0x180050aa0`
- end: `0x180051089`
- name: `?D3DDeviceOpen@CDX11DecodeCore@@UEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@AEBUD3D11_VIDEO_DECODER_CONFIG@@_N333AEAU2@PEAPEAVCDXVABufferTracker@@@Z`
- size: `1513`
- prototype: `__int64 __usercall@<rax>(CDX11DecodeCore *__hidden this@<rcx>, const struct DXVAVideoDesc *@<rdx>, const struct DXVAParams_tag *@<r8>, const struct D3D11_VIDEO_DECODER_CONFIG *@<r9>, bool, bool, bool, bool, struct DXVAVideoDesc *, struct CDXVABufferTracker **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800434f0`

## callees

- `0x180014eec`
- `0x180014f4c`
- `0x180024220`
- `0x180024bf4`
- `0x180044d78`
- `0x180048a84`
- `0x18004a11c`
- `0x18004e33c`
- `0x18004ee8c`
- `0x180050aa0`
- `0x180051520`
- `0x1800519f4`
- `0x18005253c`
- `0x180052644`
- `0x180055f44`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDX11DecodeCore::D3DDeviceOpen(
        CDX11DecodeCore *this,
        const struct DXVAVideoDesc *a2,
        const struct DXVAParams_tag *a3,
        const struct D3D11_VIDEO_DECODER_CONFIG *a4,
        bool a5,
        bool a6,
        bool a7,
        bool a8,
        struct DXVAVideoDesc *a9,
        struct CDXVABufferTracker **a10)
{
  unsigned __int8 v13; // r15
  struct DXGI_ADAPTER_DESC *v14; // rdx
  char *v15; // rdi
  __int64 v16; // rdx
  int Resources; // ebx
  __int64 v18; // r8
  int (__fastcall ***v19)(_QWORD, GUID *, struct ID3D11VideoDevice1 **); // rdi
  int (__fastcall *v20)(_QWORD, GUID *, struct ID3D11VideoDevice1 **); // rbx
  CDXVABufferTracker **v21; // r13
  int v23; // ecx
  int v24; // edx
  int v25; // r8d
  __int64 v26; // r8
  int v27; // r9d
  _DWORD *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  _DWORD *v31; // rcx
  __int64 v32; // rdi
  void (__fastcall *v33)(__int64, struct CDXVABufferTracker ***); // rbx
  struct CDXVABufferTracker **v34; // [rsp+40h] [rbp-C0h] BYREF
  struct ID3D11VideoDevice1 *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  char *v37; // [rsp+58h] [rbp-A8h]
  __int128 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v39; // [rsp+70h] [rbp-90h]
  __int128 v40; // [rsp+80h] [rbp-80h]
  int v41; // [rsp+90h] [rbp-70h]
  __int128 v42; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v43[7]; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+120h] [rbp+20h]
  _BYTE v45[500]; // [rsp+124h] [rbp+24h] BYREF
  _BYTE v46[72]; // [rsp+318h] [rbp+218h] BYREF

  v34 = a10;
  v42 = 0;
  *a10 = 0;
  *((_BYTE *)this + 432) = 0;
  *((_BYTE *)this + 394) = 0;
  v13 = 0;
  CDX11DecodeCore::ReleaseSurfaces(this);
  v15 = (char *)this + 48;
  v37 = (char *)this + 48;
  if ( !a6 && *(_QWORD *)v15
    || (Resources = CDX11DecodeCore::OpenDevice(this, v14), v37 = (char *)this + 48, !Resources) )
  {
    *((_OWORD *)this + 4) = a4->guidConfigBitstreamEncryption;
    *((_OWORD *)this + 5) = a4->guidConfigMBcontrolEncryption;
    *((_OWORD *)this + 6) = a4->guidConfigResidDiffEncryption;
    *((_OWORD *)this + 7) = *(_OWORD *)&a4->ConfigBitstreamRaw;
    *((_OWORD *)this + 8) = *(_OWORD *)&a4->ConfigResid8Subtraction;
    *((_OWORD *)this + 9) = *(_OWORD *)&a4->ConfigResidDiffAccelerator;
    *((_DWORD *)this + 40) = *(_DWORD *)&a4->ConfigMinRenderTargetBuffCount;
    if ( _TestMockIsDXVAProfileInEnableList((const struct _GUID *)((char *)a2 + 12)) )
      *((_BYTE *)this + 432) = 1;
    v35 = 0;
    v19 = *(int (__fastcall ****)(_QWORD, GUID *, struct ID3D11VideoDevice1 **))v15;
    v20 = **v19;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
    if ( v20(v19, &IID_ID3D11VideoDevice1, &v35) >= 0 )
    {
      if ( a8 )
      {
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v43[0] = *(_OWORD *)((char *)a2 + 12);
        v43[1] = a4->guidConfigBitstreamEncryption;
        v43[2] = a4->guidConfigMBcontrolEncryption;
        v43[3] = a4->guidConfigResidDiffEncryption;
        v43[4] = *(_OWORD *)&a4->ConfigBitstreamRaw;
        v43[5] = *(_OWORD *)&a4->ConfigResid8Subtraction;
        v43[6] = *(_OWORD *)&a4->ConfigResidDiffAccelerator;
        v44 = *(_DWORD *)&a4->ConfigMinRenderTargetBuffCount;
        memset_0(v45, 0, sizeof(v45));
        memset_0(v46, 0, 0x40u);
        if ( !(unsigned int)GetRecommendedDownsampleConfigDevice(
                              a2,
                              (const struct DXVAConfigurationBase *)v43,
                              v35,
                              (struct DXVAVideoDesc *)&v38) )
        {
          v23 = v38;
          *(_QWORD *)&v42 = v38;
          v24 = DWORD1(v38);
          v25 = DWORD2(v38);
          *((_QWORD *)&v42 + 1) = __PAIR64__(HIDWORD(v39), DWORD2(v38));
          v13 = 1;
          goto LABEL_17;
        }
      }
      else if ( *((_DWORD *)a2 + 12) )
      {
        v23 = *(_DWORD *)a2;
        LODWORD(v42) = *(_DWORD *)a2;
        v24 = *((_DWORD *)a2 + 1);
        DWORD1(v42) = v24;
        v25 = *((_DWORD *)a2 + 2);
        DWORD2(v42) = v25;
        HIDWORD(v42) = *((_DWORD *)a2 + 7);
        goto LABEL_22;
      }
    }
    else if ( *((_DWORD *)a2 + 12) )
    {
      Resources = -1072875829;
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
      *((_BYTE *)this + 394) = 0;
      v21 = v34;
      goto LABEL_9;
    }
    v25 = DWORD2(v42);
    v24 = DWORD1(v42);
    v23 = v42;
LABEL_22:
    if ( !*((_DWORD *)a2 + 12) )
    {
      v21 = v34;
      Resources = CDX11DecodeCore::AllocateResources(this, a2, v34);
      if ( !Resources )
      {
        if ( g_wppLevels >= 4u )
          WPP_SF_ddddq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            v26,
            *((unsigned int *)a2 + 8),
            *(_DWORD *)a2,
            *((_DWORD *)a2 + 1),
            *((_DWORD *)a2 + 2),
            this);
LABEL_28:
        if ( a7 && (!*((_QWORD *)this + 7) || *((__int16 *)this + 81) >= 0) )
        {
          v28 = (_DWORD *)*((_QWORD *)this + 1);
          if ( v28 && *v28 > 5u )
          {
            v34 = (struct CDXVABufferTracker **)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
              (_DWORD)v28,
              (unsigned int)byte_1800949A5,
              v26,
              v27,
              (__int64)&v34);
          }
          Resources = (*(__int64 (__fastcall **)(CDX11DecodeCore *, const struct DXVAVideoDesc *, char *))(*(_QWORD *)this + 280LL))(
                        this,
                        a2,
                        (char *)this + 64);
          v31 = (_DWORD *)*((_QWORD *)this + 1);
          if ( v31 && *v31 > 5u )
          {
            LODWORD(v36) = Resources;
            v34 = (struct CDXVABufferTracker **)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (_DWORD)v31,
              (unsigned int)byte_180094841,
              v29,
              v30,
              (__int64)&v34,
              (__int64)&v36);
          }
          if ( Resources < 0 )
          {
            if ( g_wppLevels >= 4u )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, this);
            Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
            *((_BYTE *)this + 394) = v13;
            goto LABEL_9;
          }
          if ( a5
            && (*(unsigned int (__fastcall **)(CDX11DecodeCore *, const struct DXVAVideoDesc *))(*(_QWORD *)this + 8LL))(
                 this,
                 a2) )
          {
            *((_DWORD *)this + 99) = 1;
          }
        }
        if ( v13 || *((_DWORD *)a2 + 12) )
        {
          v34 = 0;
          v36 = 0;
          v32 = *(_QWORD *)v37;
          v33 = *(void (__fastcall **)(__int64, struct CDXVABufferTracker ***))(**(_QWORD **)v37 + 320LL);
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v34);
          v33(v32, &v34);
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v36);
          Resources = (*(__int64 (__fastcall **)(struct CDXVABufferTracker **, GUID *, __int64 *))*v34)(
                        v34,
                        &IID_ID3D11VideoContext1,
                        &v36);
          if ( Resources < 0 || *((_BYTE *)this + 432) )
          {
            v13 = 0;
          }
          else
          {
            Resources = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, _DWORD))(*(_QWORD *)v36 + 544LL))(
                          v36,
                          *((_QWORD *)this + 7),
                          8,
                          &v42,
                          *((_DWORD *)a2 + 9));
            if ( Resources < 0 )
              v13 = 0;
            *((_DWORD *)a9 + 2) = DWORD2(v42);
            *(_OWORD *)((char *)this + 216) = *(_OWORD *)a9;
            *(_OWORD *)((char *)this + 232) = *((_OWORD *)a9 + 1);
            *(_OWORD *)((char *)this + 248) = *((_OWORD *)a9 + 2);
            *((_DWORD *)this + 66) = *((_DWORD *)a9 + 12);
          }
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v36);
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v34);
        }
        goto LABEL_18;
      }
      goto LABEL_18;
    }
LABEL_17:
    *((_WORD *)this + 81) |= 0x2000u;
    *(_OWORD *)a9 = *(_OWORD *)a2;
    *((_OWORD *)a9 + 1) = *((_OWORD *)a2 + 1);
    *((_OWORD *)a9 + 2) = *((_OWORD *)a2 + 2);
    *((_DWORD *)a9 + 12) = *((_DWORD *)a2 + 12);
    *(_DWORD *)a9 = v23;
    *((_DWORD *)a9 + 1) = v24;
    *((_DWORD *)a9 + 2) = v25;
    v21 = v34;
    Resources = CDX11DecodeCore::AllocateResources(this, a9, v34);
    if ( !Resources )
    {
      if ( g_wppLevels >= 4u )
        WPP_SF_ddddq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          v26,
          *((unsigned int *)a2 + 8),
          v42,
          DWORD1(v42),
          DWORD2(v42),
          this);
      goto LABEL_28;
    }
LABEL_18:
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
    goto LABEL_54;
  }
  v21 = v34;
LABEL_54:
  *((_BYTE *)this + 394) = v13;
  if ( Resources >= 0 )
  {
    *((_DWORD *)this + 107) = 0;
    goto LABEL_11;
  }
LABEL_9:
  if ( *v21 )
  {
    CDXVABufferTracker::`vector deleting destructor'(*v21, v16);
    *v21 = 0;
  }
LABEL_11:
  if ( g_wppLevels >= 8u )
    WPP_SF_dddDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      v18,
      v13,
      *((_DWORD *)a2 + 8),
      *((_DWORD *)a2 + 9),
      Resources,
      this);
  return (unsigned int)Resources;
}

```

## disassembly

```asm
0x180050aa0  mov     [rsp-8+arg_10], rbx
0x180050aa5  push    rbp
0x180050aa6  push    rsi
0x180050aa7  push    rdi
0x180050aa8  push    r12
0x180050aaa  push    r13
0x180050aac  push    r14
0x180050aae  push    r15
0x180050ab0  lea     rbp, [rsp-270h]
0x180050ab8  sub     rsp, 370h
0x180050abf  mov     rax, cs:__security_cookie
0x180050ac6  xor     rax, rsp
0x180050ac9  mov     [rbp+2A0h+var_40], rax
0x180050ad0  mov     r13, r9
0x180050ad3  mov     r14, rdx
0x180050ad6  mov     rsi, rcx
0x180050ad9  mov     r12, [rbp+2A0h+arg_40]
0x180050ae0  mov     rax, [rbp+2A0h+arg_48]
0x180050ae7  mov     [rsp+3A0h+var_360], rax
0x180050aec  xorps   xmm0, xmm0
0x180050aef  movups  [rbp+2A0h+var_308], xmm0
0x180050af3  xor     ebx, ebx
0x180050af5  mov     [rax], rbx
0x180050af8  mov     [rcx+1B0h], bl
0x180050afe  mov     [rcx+18Ah], bl
0x180050b04  mov     r15b, bl
0x180050b07  call    ?ReleaseSurfaces@CDX11DecodeCore@@IEAAJXZ; CDX11DecodeCore::ReleaseSurfaces(void)
0x180050b0c  lea     rdi, [rsi+30h]
0x180050b10  mov     [rsp+3A0h+var_348], rdi
0x180050b15  cmp     [rbp+2A0h+arg_28], bl
0x180050b1b  jnz     short loc_180050B22
0x180050b1d  cmp     [rdi], rbx
0x180050b20  jnz     short loc_180050B3B
0x180050b22  mov     rcx, rsi; this
0x180050b25  call    ?OpenDevice@CDX11DecodeCore@@IEAAJPEAUDXGI_ADAPTER_DESC@@@Z; CDX11DecodeCore::OpenDevice(DXGI_ADAPTER_DESC *)
0x180050b2a  mov     ebx, eax
0x180050b2c  mov     [rsp+3A0h+var_348], rdi
0x180050b31  test    eax, eax
0x180050b33  jnz     loc_180051068
0x180050b39  xor     ebx, ebx
0x180050b3b  movups  xmm0, xmmword ptr [r13+0]
0x180050b40  movups  xmmword ptr [rsi+40h], xmm0
0x180050b44  movups  xmm1, xmmword ptr [r13+10h]
0x180050b49  movups  xmmword ptr [rsi+50h], xmm1
0x180050b4d  movups  xmm0, xmmword ptr [r13+20h]
0x180050b52  movups  xmmword ptr [rsi+60h], xmm0
0x180050b56  movups  xmm1, xmmword ptr [r13+30h]
0x180050b5b  movups  xmmword ptr [rsi+70h], xmm1
0x180050b5f  movups  xmm0, xmmword ptr [r13+40h]
0x180050b64  movups  xmmword ptr [rsi+80h], xmm0
0x180050b6b  movups  xmm1, xmmword ptr [r13+50h]
0x180050b70  movups  xmmword ptr [rsi+90h], xmm1
0x180050b77  mov     eax, [r13+60h]
0x180050b7b  mov     [rsi+0A0h], eax
0x180050b81  lea     rcx, [r14+0Ch]; struct _GUID *
0x180050b85  call    ?_TestMockIsDXVAProfileInEnableList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInEnableList(_GUID const &)
0x180050b8a  test    al, al
0x180050b8c  jz      short loc_180050B95
0x180050b8e  mov     byte ptr [rsi+1B0h], 1
0x180050b95  mov     [rsp+3A0h+var_358], rbx
0x180050b9a  mov     rdi, [rdi]
0x180050b9d  mov     rax, [rdi]
0x180050ba0  mov     rbx, [rax]
0x180050ba3  lea     rcx, [rsp+3A0h+var_358]
0x180050ba8  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050bad  lea     r8, [rsp+3A0h+var_358]
0x180050bb2  lea     rdx, IID_ID3D11VideoDevice1
0x180050bb9  mov     rcx, rdi
0x180050bbc  mov     rax, rbx
0x180050bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bc4  xor     edi, edi
0x180050bc6  test    eax, eax
0x180050bc8  jns     loc_180050C67
0x180050bce  cmp     [r14+30h], edi
0x180050bd2  jz      loc_180050DC5
0x180050bd8  mov     ebx, 0C00D36CBh
0x180050bdd  lea     rcx, [rsp+3A0h+var_358]
0x180050be2  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050be7  mov     [rsi+18Ah], dil
0x180050bee  mov     r13, [rsp+3A0h+var_360]
0x180050bf3  mov     rcx, [r13+0]; this
0x180050bf7  test    rcx, rcx
0x180050bfa  jz      short loc_180050C05
0x180050bfc  call    ??_ECDXVABufferTracker@@QEAAPEAXI@Z; CDXVABufferTracker::`vector deleting destructor'(uint)
0x180050c01  mov     [r13+0], rdi
0x180050c05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180050c0c  jb      short loc_180050C3B
0x180050c0e  movzx   r9d, r15b
0x180050c12  mov     [rsp+3A0h+var_368], rsi
0x180050c17  mov     [rsp+3A0h+var_370], ebx
0x180050c1b  mov     eax, [r14+24h]
0x180050c1f  mov     dword ptr [rsp+3A0h+var_378], eax
0x180050c23  mov     eax, [r14+20h]
0x180050c27  mov     dword ptr [rsp+3A0h+var_380], eax
0x180050c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c32  mov     rcx, [rcx+10h]
0x180050c36  call    WPP_SF_dddDq
0x180050c3b  mov     eax, ebx
0x180050c3d  mov     rcx, [rbp+2A0h+var_40]
0x180050c44  xor     rcx, rsp; StackCookie
0x180050c47  call    __security_check_cookie
0x180050c4c  mov     rbx, [rsp+3A0h+arg_10]
0x180050c54  add     rsp, 370h
0x180050c5b  pop     r15
0x180050c5d  pop     r14
0x180050c5f  pop     r13
0x180050c61  pop     r12
0x180050c63  pop     rdi
0x180050c64  pop     rsi
0x180050c65  pop     rbp
0x180050c66  retn
0x180050c67  cmp     [rbp+2A0h+arg_38], dil
0x180050c6e  jz      loc_180050DA1
0x180050c74  xorps   xmm0, xmm0
0x180050c77  xor     eax, eax
0x180050c79  movups  [rsp+3A0h+var_340], xmm0
0x180050c7e  movups  [rsp+3A0h+var_330], xmm0
0x180050c83  movups  [rbp+2A0h+var_320], xmm0
0x180050c87  mov     [rbp+2A0h+var_310], eax
0x180050c8a  movups  xmm0, xmmword ptr [r14+0Ch]
0x180050c8f  movdqu  [rbp+2A0h+var_2F0], xmm0
0x180050c94  movups  xmm1, xmmword ptr [r13+0]
0x180050c99  movaps  [rbp+2A0h+var_2E0], xmm1
0x180050c9d  movups  xmm0, xmmword ptr [r13+10h]
0x180050ca2  movaps  [rbp+2A0h+var_2D0], xmm0
0x180050ca6  movups  xmm1, xmmword ptr [r13+20h]
0x180050cab  movaps  [rbp+2A0h+var_2C0], xmm1
0x180050caf  movups  xmm0, xmmword ptr [r13+30h]
0x180050cb4  movaps  [rbp+2A0h+var_2B0], xmm0
0x180050cb8  movups  xmm1, xmmword ptr [r13+40h]
0x180050cbd  movaps  [rbp+2A0h+var_2A0], xmm1
0x180050cc1  movups  xmm0, xmmword ptr [r13+50h]
0x180050cc6  movaps  [rbp+2A0h+var_290], xmm0
0x180050cca  mov     eax, [r13+60h]
0x180050cce  mov     [rbp+2A0h+var_280], eax
0x180050cd1  xor     edx, edx; Val
0x180050cd3  mov     r8d, 1F4h; Size
0x180050cd9  lea     rcx, [rbp+2A0h+var_27C]; void *
0x180050cdd  call    memset_0
0x180050ce2  xor     edx, edx; Val
0x180050ce4  lea     r8d, [rdx+40h]; Size
0x180050ce8  lea     rcx, [rbp+2A0h+var_88]; void *
0x180050cef  call    memset_0
0x180050cf4  lea     r9, [rsp+3A0h+var_340]; struct DXVAVideoDesc *
0x180050cf9  mov     r8, [rsp+3A0h+var_358]; struct ID3D11VideoDevice1 *
0x180050cfe  lea     rdx, [rbp+2A0h+var_2F0]; struct DXVAConfigurationBase *
0x180050d02  mov     rcx, r14; struct DXVAVideoDesc *
0x180050d05  call    ?GetRecommendedDownsampleConfigDevice@@YAJAEBUDXVAVideoDesc@@AEBUDXVAConfigurationBase@@PEAUID3D11VideoDevice1@@AEAU1@@Z; GetRecommendedDownsampleConfigDevice(DXVAVideoDesc const &,DXVAConfigurationBase const &,ID3D11VideoDevice1 *,DXVAVideoDesc &)
0x180050d0a  test    eax, eax
0x180050d0c  jnz     loc_180050DC5
0x180050d12  mov     ecx, dword ptr [rsp+3A0h+var_340]
0x180050d16  mov     dword ptr [rbp+2A0h+var_308], ecx
0x180050d19  mov     edx, dword ptr [rsp+3A0h+var_340+4]
0x180050d1d  mov     dword ptr [rbp+2A0h+var_308+4], edx
0x180050d20  mov     r8d, dword ptr [rsp+3A0h+var_340+8]
0x180050d25  mov     dword ptr [rbp+2A0h+var_308+8], r8d
0x180050d29  mov     eax, dword ptr [rsp+3A0h+var_330+0Ch]
0x180050d2d  mov     dword ptr [rbp+2A0h+var_308+0Ch], eax
0x180050d30  mov     r15b, 1
0x180050d33  mov     eax, 2000h
0x180050d38  or      [rsi+0A2h], ax
0x180050d3f  movups  xmm0, xmmword ptr [r14]
0x180050d43  movups  xmmword ptr [r12], xmm0
0x180050d48  movups  xmm1, xmmword ptr [r14+10h]
0x180050d4d  movups  xmmword ptr [r12+10h], xmm1
0x180050d53  movups  xmm0, xmmword ptr [r14+20h]
0x180050d58  movups  xmmword ptr [r12+20h], xmm0
0x180050d5e  mov     eax, [r14+30h]
0x180050d62  mov     [r12+30h], eax
0x180050d67  mov     [r12], ecx
0x180050d6b  mov     [r12+4], edx
0x180050d70  mov     [r12+8], r8d
0x180050d75  mov     r13, [rsp+3A0h+var_360]
0x180050d7a  mov     r8, r13; struct CDXVABufferTracker **
0x180050d7d  mov     rdx, r12; struct DXVAVideoDesc *
0x180050d80  mov     rcx, rsi; this
0x180050d83  call    ?AllocateResources@CDX11DecodeCore@@IEAAJAEBUDXVAVideoDesc@@PEAPEAVCDXVABufferTracker@@@Z; CDX11DecodeCore::AllocateResources(DXVAVideoDesc const &,CDXVABufferTracker * *)
0x180050d88  mov     ebx, eax
0x180050d8a  test    eax, eax
0x180050d8c  jz      loc_180050E18
0x180050d92  lea     rcx, [rsp+3A0h+var_358]
0x180050d97  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050d9c  jmp     loc_18005106F
0x180050da1  cmp     [r14+30h], edi
0x180050da5  jz      short loc_180050DC5
0x180050da7  mov     ecx, [r14]
0x180050daa  mov     dword ptr [rbp+2A0h+var_308], ecx
0x180050dad  mov     edx, [r14+4]
0x180050db1  mov     dword ptr [rbp+2A0h+var_308+4], edx
0x180050db4  mov     r8d, [r14+8]
0x180050db8  mov     dword ptr [rbp+2A0h+var_308+8], r8d
0x180050dbc  mov     eax, [r14+1Ch]
0x180050dc0  mov     dword ptr [rbp+2A0h+var_308+0Ch], eax
0x180050dc3  jmp     short loc_180050DCF
0x180050dc5  mov     r8d, dword ptr [rbp+2A0h+var_308+8]
0x180050dc9  mov     edx, dword ptr [rbp+2A0h+var_308+4]
0x180050dcc  mov     ecx, dword ptr [rbp+2A0h+var_308]
0x180050dcf  cmp     [r14+30h], edi
0x180050dd3  jnz     loc_180050D33
0x180050dd9  mov     r13, [rsp+3A0h+var_360]
0x180050dde  mov     r8, r13; struct CDXVABufferTracker **
0x180050de1  mov     rdx, r14; struct DXVAVideoDesc *
0x180050de4  mov     rcx, rsi; this
0x180050de7  call    ?AllocateResources@CDX11DecodeCore@@IEAAJAEBUDXVAVideoDesc@@PEAPEAVCDXVABufferTracker@@@Z; CDX11DecodeCore::AllocateResources(DXVAVideoDesc const &,CDXVABufferTracker * *)
0x180050dec  mov     ebx, eax
0x180050dee  test    eax, eax
0x180050df0  jnz     short loc_180050D92
0x180050df2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180050df9  jb      short loc_180050E54
0x180050dfb  lea     edx, [rax+11h]
0x180050dfe  mov     [rsp+3A0h+var_368], rsi
0x180050e03  mov     eax, [r14+8]
0x180050e07  mov     [rsp+3A0h+var_370], eax
0x180050e0b  mov     eax, [r14+4]
0x180050e0f  mov     dword ptr [rsp+3A0h+var_378], eax
0x180050e13  mov     eax, [r14]
0x180050e16  jmp     short loc_180050E3C
0x180050e18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180050e1f  jb      short loc_180050E54
0x180050e21  mov     edx, 10h
0x180050e26  mov     [rsp+3A0h+var_368], rsi
0x180050e2b  mov     eax, dword ptr [rbp+2A0h+var_308+8]
0x180050e2e  mov     [rsp+3A0h+var_370], eax
0x180050e32  mov     eax, dword ptr [rbp+2A0h+var_308+4]
0x180050e35  mov     dword ptr [rsp+3A0h+var_378], eax
0x180050e39  mov     eax, dword ptr [rbp+2A0h+var_308]
0x180050e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050e43  mov     dword ptr [rsp+3A0h+var_380], eax
0x180050e47  mov     r9d, [r14+20h]
0x180050e4b  mov     rcx, [rcx+10h]
0x180050e4f  call    WPP_SF_ddddq
0x180050e54  cmp     [rbp+2A0h+arg_30], dil
0x180050e5b  jz      loc_180050F5F
0x180050e61  cmp     [rsi+38h], rdi
0x180050e65  jz      short loc_180050E74
0x180050e67  cmp     [rsi+0A2h], di
0x180050e6e  jl      loc_180050F5F
0x180050e74  mov     rcx, [rsi+8]
0x180050e78  test    rcx, rcx
0x180050e7b  jz      short loc_180050E9F
0x180050e7d  mov     eax, [rcx]
0x180050e7f  cmp     eax, 5
0x180050e82  jbe     short loc_180050E9F
0x180050e84  mov     [rsp+3A0h+var_360], rsi
0x180050e89  lea     rax, [rsp+3A0h+var_360]
0x180050e8e  mov     [rsp+3A0h+var_380], rax
0x180050e93  lea     rdx, byte_1800949A5
0x180050e9a  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180050e9f  mov     rax, [rsi]
0x180050ea2  lea     r8, [rsi+40h]
0x180050ea6  mov     rdx, r14
0x180050ea9  mov     rcx, rsi
0x180050eac  mov     rax, [rax+118h]
0x180050eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eb8  mov     ebx, eax
0x180050eba  mov     rcx, [rsi+8]
0x180050ebe  test    rcx, rcx
0x180050ec1  jz      short loc_180050EF3
0x180050ec3  mov     eax, [rcx]
0x180050ec5  cmp     eax, 5
0x180050ec8  jbe     short loc_180050EF3
0x180050eca  mov     dword ptr [rsp+3A0h+var_350], ebx
0x180050ece  mov     [rsp+3A0h+var_360], rsi
0x180050ed3  lea     rax, [rsp+3A0h+var_350]
0x180050ed8  mov     [rsp+3A0h+var_378], rax
0x180050edd  lea     rax, [rsp+3A0h+var_360]
0x180050ee2  mov     [rsp+3A0h+var_380], rax
0x180050ee7  lea     rdx, byte_180094841
0x180050eee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180050ef3  test    ebx, ebx
0x180050ef5  jns     short loc_180050F36
0x180050ef7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180050efe  jb      short loc_180050F20
0x180050f00  mov     edx, 12h
0x180050f05  mov     r9, rsi
0x180050f08  lea     r8, WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids
0x180050f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f16  mov     rcx, [rcx+10h]
0x180050f1a  call    WPP_SF_q
0x180050f1f  nop
0x180050f20  lea     rcx, [rsp+3A0h+var_358]
0x180050f25  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050f2a  mov     [rsi+18Ah], r15b
0x180050f31  jmp     loc_180050BF3
0x180050f36  cmp     [rbp+2A0h+arg_20], dil
0x180050f3d  jz      short loc_180050F5F
0x180050f3f  mov     rax, [rsi]
0x180050f42  mov     rdx, r14
0x180050f45  mov     rcx, rsi
0x180050f48  mov     rax, [rax+8]
0x180050f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f51  test    eax, eax
0x180050f53  jz      short loc_180050F5F
0x180050f55  mov     dword ptr [rsi+18Ch], 1
0x180050f5f  test    r15b, r15b
0x180050f62  jnz     short loc_180050F6E
0x180050f64  cmp     [r14+30h], edi
0x180050f68  jz      loc_180050D92
0x180050f6e  mov     [rsp+3A0h+var_360], rdi
0x180050f73  mov     [rsp+3A0h+var_350], rdi
  ... truncated ...
```
