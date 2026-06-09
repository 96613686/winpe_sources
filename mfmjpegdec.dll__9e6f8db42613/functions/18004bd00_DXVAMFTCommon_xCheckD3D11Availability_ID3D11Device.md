# DXVAMFTCommon::xCheckD3D11Availability(ID3D11Device *)

- ea: `0x18004bd00`
- end: `0x18004c41b`
- name: `?xCheckD3D11Availability@DXVAMFTCommon@@AEAAJPEAUID3D11Device@@@Z`
- size: `1819`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, struct ID3D11Device *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004d23c`

## callees

- `0x180023934`
- `0x180024220`
- `0x1800245f0`
- `0x180024bf4`
- `0x18003a54c`
- `0x180041620`
- `0x1800431f4`
- `0x180044d78`
- `0x18004a11c`
- `0x18004aa94`
- `0x18004acfc`
- `0x18004aed8`
- `0x18004af48`
- `0x18004b128`
- `0x18004b30c`
- `0x18004b56c`
- `0x18004b9d0`
- `0x18004bca8`
- `0x18004bcd4`
- `0x18004bd00`
- `0x18004e33c`
- `0x180055688`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DXVAMFTCommon::xCheckD3D11Availability(DXVAMFTCommon *this, struct ID3D11Device *a2)
{
  void *v4; // r15
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rbx
  unsigned int v6; // edi
  HRESULT (__stdcall *v7)(ID3D11Device *, const IID *const, void **); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, void **); // rbx
  _OWORD *v10; // rax
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // r12d
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  __int64 v17; // rsi
  unsigned int i; // ebx
  int v19; // eax
  unsigned int j; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // r12d
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx
  const struct std::nothrow_t *v28; // rdx
  void *v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v34; // [rsp+5Ch] [rbp-A4h]
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  void *v36; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  char v39[8]; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v41; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[24]; // [rsp+B0h] [rbp-50h] BYREF
  char v43[16]; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v44; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int Data1; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v46; // [rsp+ECh] [rbp-14h]
  __int64 v47; // [rsp+FCh] [rbp-4h]
  struct _GUID v48; // [rsp+110h] [rbp+10h] BYREF
  __int128 v49; // [rsp+120h] [rbp+20h]
  __int128 v50; // [rsp+130h] [rbp+30h]
  __int128 v51; // [rsp+140h] [rbp+40h]
  __int128 v52; // [rsp+150h] [rbp+50h]
  __int128 v53; // [rsp+160h] [rbp+60h]
  int v54; // [rsp+170h] [rbp+70h]
  _BYTE v55[16]; // [rsp+180h] [rbp+80h] BYREF
  struct _GUID v56; // [rsp+190h] [rbp+90h]
  __int128 v57; // [rsp+1A0h] [rbp+A0h]
  __int128 v58; // [rsp+1B0h] [rbp+B0h]
  __int128 v59; // [rsp+1C0h] [rbp+C0h]
  __int128 v60; // [rsp+1D0h] [rbp+D0h]
  __int128 v61; // [rsp+1E0h] [rbp+E0h]
  int v62; // [rsp+1F0h] [rbp+F0h]
  _OWORD v63[35]; // [rsp+1F4h] [rbp+F4h]
  _BYTE v64[16]; // [rsp+428h] [rbp+328h] BYREF
  __int64 v65; // [rsp+438h] [rbp+338h]
  _BYTE v66[304]; // [rsp+450h] [rbp+350h] BYREF

  v32 = 0;
  v4 = 0;
  v36 = 0;
  v31 = 0;
  Data1 = 0;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  v35 = 0;
  memset_0(v66, 0, sizeof(v66));
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v38 = -1;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v32);
  v6 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333,
         &v32);
  if ( !v6 )
  {
    v30 = 0;
    v7 = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
    v6 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))v7)(
           a2,
           &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
           &v35);
    if ( v6
      || (v8 = v35,
          v9 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v35 + 56LL),
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v30),
          (v6 = v9(v8, &v30)) != 0)
      || (v6 = (*(__int64 (__fastcall **)(void *, _BYTE *))(*(_QWORD *)v30 + 64LL))(v30, v66)) != 0 )
    {
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v30);
      goto LABEL_58;
    }
    v10 = (_OWORD *)((char *)this + 24);
    v11 = v66;
    v12 = 2;
    do
    {
      *v10 = *v11;
      v10[1] = v11[1];
      v10[2] = v11[2];
      v10[3] = v11[3];
      v10[4] = v11[4];
      v10[5] = v11[5];
      v10[6] = v11[6];
      v10[7] = v11[7];
      v10 += 8;
      v11 += 8;
      --v12;
    }
    while ( v12 );
    *v10 = *v11;
    v10[1] = v11[1];
    v10[2] = v11[2];
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v30);
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 88LL))(v32);
    v34 = v13;
    v30 = operator new[](saturated_mul(v13, 0x10u));
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v36, &v30);
    if ( v30 )
      operator delete(v30, v14);
    v4 = v36;
    if ( v36 )
    {
      memset_0(v36, 0, 16LL * v13);
      v15 = 0;
      if ( !v13 )
      {
LABEL_14:
        utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::clear((char *)this + 352);
        v16 = 0;
        v17 = si128.m128i_i64[1];
        while ( 1 )
        {
          LODWORD(v30) = v16;
          if ( !(*(unsigned __int8 (__fastcall **)(DXVAMFTCommon *, _QWORD, _QWORD, void *, struct _GUID *))(*(_QWORD *)this + 16LL))(
                  this,
                  v16,
                  v13,
                  v4,
                  &v44) )
            break;
          DXVAConfiguration::DXVAConfiguration((DXVAConfiguration *)v55);
          for ( i = 0; i < 0xB; ++i )
          {
            v33 = 0;
            (*(void (__fastcall **)(__int64, struct _GUID *, _QWORD, int *))(*(_QWORD *)v32 + 104LL))(
              v32,
              &v44,
              *((unsigned int *)qword_1800923D0 + (int)i),
              &v33);
            if ( _TestMockIsDXVAProfileInEnableList(&v44) )
            {
              v19 = 1;
              v33 = 1;
            }
            else
            {
              v19 = v33;
            }
            if ( v19 )
              utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::_InsertImpl<enum DXGI_FORMAT const &>(
                v64,
                v43,
                0,
                (char *)qword_1800923D0 + 4 * (int)i);
          }
          Data1 = v44.Data1;
          *(_QWORD *)&v46 = *(_QWORD *)&v44.Data2;
          *((_QWORD *)&v46 + 1) = *(unsigned int *)&v44.Data4[4] | 0x9000000000LL;
          LODWORD(v47) = 144;
          HIDWORD(v47) = *(_DWORD *)(v65 + 24);
          if ( !_TestMockIsDXVAProfileInEnableList(&v44) )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v32 + 112LL))(
                   v32,
                   &Data1,
                   &v31);
            if ( v6 )
              goto LABEL_50;
          }
          if ( g_wppLevels )
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
              v31,
              this);
          v48.Data1 = 0;
          memset_0(&v48.Data2, 0, 0x60u);
          for ( j = 0; j < v31; ++j )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, struct _GUID *))(*(_QWORD *)v32 + 120LL))(
                   v32,
                   &Data1,
                   j,
                   &v48);
            if ( v6 )
              break;
            if ( (_DWORD)v51 == 1 )
            {
              Buf1 = v48;
              if ( !IsValidEncryptionScheme(&Buf1) )
              {
                v56 = v48;
                v57 = v49;
                v58 = v50;
                v59 = v51;
                v60 = v52;
                v61 = v53;
                v62 = v54;
                break;
              }
            }
          }
          v21 = 0;
          if ( v31 )
          {
            while ( 1 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, struct _GUID *))(*(_QWORD *)v32 + 120LL))(
                     v32,
                     &Data1,
                     v21,
                     &v48);
              if ( v6 )
                break;
              v22 = v48.Data1;
              v41 = v48;
              if ( IsValidEncryptionScheme(&v41) )
              {
                if ( v21 >= 5 )
                {
                  if ( g_wppLevels )
                    WPP_SF_dq(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
                      5,
                      this);
                  goto LABEL_46;
                }
                v23 = 100LL * v21;
                *(struct _GUID *)((char *)v63 + v23) = v48;
                *(_OWORD *)((char *)&v63[1] + v23) = v49;
                *(_OWORD *)((char *)&v63[2] + v23) = v50;
                *(_OWORD *)((char *)&v63[3] + v23) = v51;
                *(_OWORD *)((char *)&v63[4] + v23) = v52;
                *(_OWORD *)((char *)&v63[5] + v23) = v53;
                *(_DWORD *)((char *)&v63[6] + v23) = v54;
                if ( v17 == v38 )
                {
                  utl::vector<_GUID,utl::allocator<_GUID>>::_PushBackOne2<_GUID const &>(&si128, &v48);
                  v17 = si128.m128i_i64[1];
                }
                else
                {
                  *(_DWORD *)v17 = v22;
                  *(_QWORD *)(v17 + 4) = *(_QWORD *)&v48.Data2;
                  *(_DWORD *)(v17 + 12) = *(_DWORD *)&v48.Data4[4];
                  v17 += 16;
                  si128.m128i_i64[1] = v17;
                }
              }
              if ( ++v21 >= v31 )
                goto LABEL_46;
            }
LABEL_50:
            utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::clear(v64);
            v13 = v34;
            break;
          }
          if ( v6 )
            goto LABEL_50;
LABEL_46:
          utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(
            (char *)this + 352,
            v42,
            &v44);
          if ( !v42[16] )
          {
            v26 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::_PairMapTag,_GUID const &,DXVAConfiguration>(
                    v25,
                    v24,
                    &v44,
                    v55);
            if ( v26 )
              utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(
                (char *)this + 352,
                v39,
                v42,
                v26);
          }
          utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::clear(v64);
          v16 = (_DWORD)v30 + 1;
          v13 = v34;
        }
        if ( *((_QWORD *)this + 47) )
        {
          v27 = *((_QWORD *)this + 56);
          v30 = (void *)*((_QWORD *)this + 55);
          Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(&v30);
          if ( !(unsigned __int8)xIsDeviceInHWExlusionList(
                                   v35,
                                   v13,
                                   (_DWORD)v4,
                                   (v17 - si128.m128i_i64[0]) >> 4,
                                   si128.m128i_i64[0],
                                   (__int64)this + 424,
                                   (__int64)&v30,
                                   v27) )
            goto LABEL_58;
        }
        else if ( g_wppLevels )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, this);
        }
        v6 = -1072875818;
        goto LABEL_58;
      }
      while ( 1 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v32 + 96LL))(
               v32,
               v15,
               (__int64)v4 + 16 * v15);
        if ( v6 )
          break;
        if ( ++v15 >= v13 )
          goto LABEL_14;
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
LABEL_58:
  utl::vector<_GUID,utl::allocator<_GUID>>::_Uninit(&si128);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v35);
  if ( v4 )
    operator delete(v4, v28);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v32);
  return v6;
}

```

## disassembly

```asm
0x18004bd00  mov     [rsp-8+arg_10], rbx
0x18004bd05  push    rbp
0x18004bd06  push    rsi
0x18004bd07  push    rdi
0x18004bd08  push    r12
0x18004bd0a  push    r13
0x18004bd0c  push    r14
0x18004bd0e  push    r15
0x18004bd10  lea     rbp, [rsp-490h]
0x18004bd18  sub     rsp, 590h
0x18004bd1f  mov     rax, cs:__security_cookie
0x18004bd26  xor     rax, rsp
0x18004bd29  mov     [rbp+4C0h+var_40], rax
0x18004bd30  mov     rsi, rdx
0x18004bd33  mov     r14, rcx
0x18004bd36  mov     [rsp+5C0h+var_570], 0
0x18004bd3f  xor     r15d, r15d
0x18004bd42  mov     [rsp+5C0h+var_558], r15
0x18004bd47  mov     [rsp+5C0h+var_578], r15d
0x18004bd4c  mov     [rbp+4C0h+var_4D8], r15d
0x18004bd50  xorps   xmm0, xmm0
0x18004bd53  xor     eax, eax
0x18004bd55  movups  [rbp+4C0h+var_4D4], xmm0
0x18004bd59  mov     [rbp+4C0h+var_4C4], rax
0x18004bd5d  movups  xmmword ptr [rbp+4C0h+var_4E8.Data1], xmm0
0x18004bd61  mov     [rsp+5C0h+var_560], rax
0x18004bd66  xor     edx, edx; Val
0x18004bd68  mov     r8d, 130h; Size
0x18004bd6e  lea     rcx, [rbp+4C0h+var_170]; void *
0x18004bd75  call    memset_0
0x18004bd7a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004bd82  movdqu  [rsp+5C0h+var_550], xmm0
0x18004bd88  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004bd8c  mov     [rbp+4C0h+var_540], r13
0x18004bd90  mov     rax, [rsi]
0x18004bd93  mov     rbx, [rax]
0x18004bd96  lea     rcx, [rsp+5C0h+var_570]
0x18004bd9b  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004bda0  lea     r8, [rsp+5C0h+var_570]
0x18004bda5  lea     rdx, _GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333
0x18004bdac  mov     rcx, rsi
0x18004bdaf  mov     rax, rbx
0x18004bdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdb7  mov     edi, eax
0x18004bdb9  test    eax, eax
0x18004bdbb  jnz     loc_18004C3C1
0x18004bdc1  mov     [rsp+5C0h+var_580], r15
0x18004bdc6  mov     rax, [rsi]
0x18004bdc9  mov     rbx, [rax]
0x18004bdcc  lea     rcx, [rsp+5C0h+var_560]
0x18004bdd1  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004bdd6  lea     r8, [rsp+5C0h+var_560]
0x18004bddb  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18004bde2  mov     rcx, rsi
0x18004bde5  mov     rax, rbx
0x18004bde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bded  mov     edi, eax
0x18004bdef  test    eax, eax
0x18004bdf1  jz      short loc_18004BE02
0x18004bdf3  lea     rcx, [rsp+5C0h+var_580]
0x18004bdf8  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004bdfd  jmp     loc_18004C3C1
0x18004be02  mov     rdi, [rsp+5C0h+var_560]
0x18004be07  mov     rax, [rdi]
0x18004be0a  mov     rbx, [rax+38h]
0x18004be0e  lea     rcx, [rsp+5C0h+var_580]
0x18004be13  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004be18  lea     rdx, [rsp+5C0h+var_580]
0x18004be1d  mov     rcx, rdi
0x18004be20  mov     rax, rbx
0x18004be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be28  mov     edi, eax
0x18004be2a  test    eax, eax
0x18004be2c  jnz     short loc_18004BDF3
0x18004be2e  mov     rcx, [rsp+5C0h+var_580]
0x18004be33  mov     rax, [rcx]
0x18004be36  lea     rdx, [rbp+4C0h+var_170]
0x18004be3d  mov     rax, [rax+40h]
0x18004be41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be46  mov     edi, eax
0x18004be48  test    eax, eax
0x18004be4a  jnz     short loc_18004BDF3
0x18004be4c  lea     rax, [r14+18h]
0x18004be50  lea     rcx, [rbp+4C0h+var_170]
0x18004be57  lea     edx, [rdi+2]
0x18004be5a  lea     r8d, [rdx+7Eh]
0x18004be5e  movups  xmm0, xmmword ptr [rcx]
0x18004be61  movups  xmmword ptr [rax], xmm0
0x18004be64  movups  xmm1, xmmword ptr [rcx+10h]
0x18004be68  movups  xmmword ptr [rax+10h], xmm1
0x18004be6c  movups  xmm0, xmmword ptr [rcx+20h]
0x18004be70  movups  xmmword ptr [rax+20h], xmm0
0x18004be74  movups  xmm1, xmmword ptr [rcx+30h]
0x18004be78  movups  xmmword ptr [rax+30h], xmm1
0x18004be7c  movups  xmm0, xmmword ptr [rcx+40h]
0x18004be80  movups  xmmword ptr [rax+40h], xmm0
0x18004be84  movups  xmm1, xmmword ptr [rcx+50h]
0x18004be88  movups  xmmword ptr [rax+50h], xmm1
0x18004be8c  movups  xmm0, xmmword ptr [rcx+60h]
0x18004be90  movups  xmmword ptr [rax+60h], xmm0
0x18004be94  movups  xmm1, xmmword ptr [rcx+70h]
0x18004be98  movups  xmmword ptr [rax+70h], xmm1
0x18004be9c  add     rax, r8
0x18004be9f  add     rcx, r8
0x18004bea2  sub     rdx, 1
0x18004bea6  jnz     short loc_18004BE5E
0x18004bea8  movups  xmm0, xmmword ptr [rcx]
0x18004beab  movups  xmmword ptr [rax], xmm0
0x18004beae  movups  xmm1, xmmword ptr [rcx+10h]
0x18004beb2  movups  xmmword ptr [rax+10h], xmm1
0x18004beb6  movups  xmm0, xmmword ptr [rcx+20h]
0x18004beba  movups  xmmword ptr [rax+20h], xmm0
0x18004bebe  lea     rcx, [rsp+5C0h+var_580]
0x18004bec3  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004bec8  mov     rcx, [rsp+5C0h+var_570]
0x18004becd  mov     rax, [rcx]
0x18004bed0  mov     rax, [rax+58h]
0x18004bed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bed9  mov     r12d, eax
0x18004bedc  mov     [rsp+5C0h+var_564], r12d
0x18004bee1  mov     ebx, eax
0x18004bee3  mov     eax, 10h
0x18004bee8  mul     r12
0x18004beeb  cmovb   rax, r13
0x18004beef  mov     rcx, rax; unsigned __int64
0x18004bef2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004bef7  mov     [rsp+5C0h+var_580], rax
0x18004befc  lea     rdx, [rsp+5C0h+var_580]
0x18004bf01  lea     rcx, [rsp+5C0h+var_558]
0x18004bf06  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18004bf0b  mov     rcx, [rsp+5C0h+var_580]; void *
0x18004bf10  test    rcx, rcx
0x18004bf13  jz      short loc_18004BF1A
0x18004bf15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004bf1a  mov     r15, [rsp+5C0h+var_558]
0x18004bf1f  test    r15, r15
0x18004bf22  jz      loc_18004C3BC
0x18004bf28  shl     rbx, 4
0x18004bf2c  mov     r8, rbx; Size
0x18004bf2f  xor     edx, edx; Val
0x18004bf31  mov     rcx, r15; void *
0x18004bf34  call    memset_0
0x18004bf39  xor     ebx, ebx
0x18004bf3b  test    r12d, r12d
0x18004bf3e  jz      short loc_18004BF6E
0x18004bf40  mov     rcx, [rsp+5C0h+var_570]
0x18004bf45  mov     rax, [rcx]
0x18004bf48  mov     r8d, ebx
0x18004bf4b  shl     r8, 4
0x18004bf4f  add     r8, r15
0x18004bf52  mov     edx, ebx
0x18004bf54  mov     rax, [rax+60h]
0x18004bf58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf5d  mov     edi, eax
0x18004bf5f  test    eax, eax
0x18004bf61  jnz     loc_18004C3C1
0x18004bf67  inc     ebx
0x18004bf69  cmp     ebx, r12d
0x18004bf6c  jb      short loc_18004BF40
0x18004bf6e  lea     r13, [r14+160h]
0x18004bf75  mov     rcx, r13
0x18004bf78  call    ?clear@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::clear(void)
0x18004bf7d  xor     ecx, ecx
0x18004bf7f  mov     rsi, qword ptr [rsp+5C0h+var_550+8]
0x18004bf84  mov     dword ptr [rsp+5C0h+var_580], ecx
0x18004bf88  mov     rax, [r14]
0x18004bf8b  lea     rdx, [rbp+4C0h+var_4E8]
0x18004bf8f  mov     [rsp+5C0h+var_5A0], rdx
0x18004bf94  mov     r9, r15
0x18004bf97  mov     r8d, r12d
0x18004bf9a  mov     edx, ecx
0x18004bf9c  mov     rcx, r14
0x18004bf9f  mov     rax, [rax+10h]
0x18004bfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfa8  test    al, al
0x18004bfaa  jz      loc_18004C321
0x18004bfb0  lea     rcx, [rbp+4C0h+var_440]; this
0x18004bfb7  call    ??0DXVAConfiguration@@QEAA@XZ; DXVAConfiguration::DXVAConfiguration(void)
0x18004bfbc  nop
0x18004bfbd  xor     ebx, ebx
0x18004bfbf  mov     [rsp+5C0h+var_568], 0
0x18004bfc7  mov     rcx, [rsp+5C0h+var_570]
0x18004bfcc  movsxd  rax, ebx
0x18004bfcf  lea     rdx, qword_1800923D0
0x18004bfd6  lea     r12, [rdx+rax*4]
0x18004bfda  mov     rax, [rcx]
0x18004bfdd  lea     r9, [rsp+5C0h+var_568]
0x18004bfe2  mov     r8d, [r12]
0x18004bfe6  lea     rdx, [rbp+4C0h+var_4E8]
0x18004bfea  mov     rax, [rax+68h]
0x18004bfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bff3  lea     rcx, [rbp+4C0h+var_4E8]; struct _GUID *
0x18004bff7  call    ?_TestMockIsDXVAProfileInEnableList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInEnableList(_GUID const &)
0x18004bffc  test    al, al
0x18004bffe  jz      short loc_18004C00B
0x18004c000  mov     eax, 1
0x18004c005  mov     [rsp+5C0h+var_568], eax
0x18004c009  jmp     short loc_18004C00F
0x18004c00b  mov     eax, [rsp+5C0h+var_568]
0x18004c00f  test    eax, eax
0x18004c011  jz      short loc_18004C029
0x18004c013  mov     r9, r12
0x18004c016  xor     r8d, r8d
0x18004c019  lea     rdx, [rbp+4C0h+var_4F8]
0x18004c01d  lea     rcx, [rbp+4C0h+var_198]
0x18004c024  call    ??$_InsertImpl@AEBW4DXGI_FORMAT@@@?$_Tree@W4DXGI_FORMAT@@W41@U?$less@W4DXGI_FORMAT@@@utl@@V?$allocator@W4DXGI_FORMAT@@@3@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@W4DXGI_FORMAT@@@utl@@_N@1@PEAU?$_TreeNode@W4DXGI_FORMAT@@@1@AEBW4DXGI_FORMAT@@@Z; utl::_Tree<DXGI_FORMAT,DXGI_FORMAT,utl::less<DXGI_FORMAT>,utl::allocator<DXGI_FORMAT>,0>::_InsertImpl<DXGI_FORMAT const &>(utl::_TreeNode<DXGI_FORMAT> *,DXGI_FORMAT const &)
0x18004c029  inc     ebx
0x18004c02b  cmp     ebx, 0Bh
0x18004c02e  jb      short loc_18004BFBF
0x18004c030  mov     eax, [rbp+4C0h+var_4E8.Data1]
0x18004c033  mov     [rbp+4C0h+var_4D8], eax
0x18004c036  movsd   xmm0, qword ptr [rbp+4C0h+var_4E8.Data2]
0x18004c03b  movsd   qword ptr [rbp+4C0h+var_4D4], xmm0
0x18004c040  mov     eax, dword ptr [rbp+4C0h+var_4E8.Data4+4]
0x18004c043  mov     dword ptr [rbp+4C0h+var_4D4+8], eax
0x18004c046  mov     eax, 90h
0x18004c04b  mov     dword ptr [rbp+4C0h+var_4D4+0Ch], eax
0x18004c04e  mov     dword ptr [rbp+4C0h+var_4C4], eax
0x18004c051  mov     rax, [rbp+4C0h+var_188]
0x18004c058  mov     ecx, [rax+18h]
0x18004c05b  mov     dword ptr [rbp+4C0h+var_4C4+4], ecx
0x18004c05e  lea     rcx, [rbp+4C0h+var_4E8]; struct _GUID *
0x18004c062  call    ?_TestMockIsDXVAProfileInEnableList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInEnableList(_GUID const &)
0x18004c067  test    al, al
0x18004c069  jnz     short loc_18004C08F
0x18004c06b  mov     rcx, [rsp+5C0h+var_570]
0x18004c070  mov     rax, [rcx]
0x18004c073  lea     r8, [rsp+5C0h+var_578]
0x18004c078  lea     rdx, [rbp+4C0h+var_4D8]
0x18004c07c  mov     rax, [rax+70h]
0x18004c080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c085  mov     edi, eax
0x18004c087  test    eax, eax
0x18004c089  jnz     loc_18004C310
0x18004c08f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c096  jb      short loc_18004C0BE
0x18004c098  mov     edx, 15h
0x18004c09d  mov     [rsp+5C0h+var_5A0], r14
0x18004c0a2  mov     r9d, [rsp+5C0h+var_578]
0x18004c0a7  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004c0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0b5  mov     rcx, [rcx+10h]
0x18004c0b9  call    WPP_SF_dq
0x18004c0be  mov     dword ptr [rbp+4C0h+var_4B0], 0
0x18004c0c5  xor     edx, edx; Val
0x18004c0c7  lea     r8d, [rdx+60h]; Size
0x18004c0cb  lea     rcx, [rbp+4C0h+var_4B0+4]; void *
0x18004c0cf  call    memset_0
0x18004c0d4  xor     ebx, ebx
0x18004c0d6  cmp     [rsp+5C0h+var_578], ebx
0x18004c0da  jbe     loc_18004C180
0x18004c0e0  mov     rcx, [rsp+5C0h+var_570]
0x18004c0e5  mov     rax, [rcx]
0x18004c0e8  lea     r9, [rbp+4C0h+var_4B0]
0x18004c0ec  mov     r8d, ebx
0x18004c0ef  lea     rdx, [rbp+4C0h+var_4D8]
0x18004c0f3  mov     rax, [rax+78h]
0x18004c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0fc  mov     edi, eax
0x18004c0fe  test    eax, eax
0x18004c100  jnz     short loc_18004C180
0x18004c102  cmp     dword ptr [rbp+4C0h+var_480], 1
0x18004c106  jnz     short loc_18004C12B
0x18004c108  mov     eax, dword ptr [rbp+4C0h+var_4B0]
0x18004c10b  mov     [rbp+4C0h+Buf1.Data1], eax
0x18004c10e  movsd   xmm0, qword ptr [rbp+4C0h+var_4B0+4]
0x18004c113  movsd   qword ptr [rbp+4C0h+Buf1.Data2], xmm0
0x18004c118  mov     eax, dword ptr [rbp+4C0h+var_4B0+0Ch]
0x18004c11b  mov     dword ptr [rbp+4C0h+Buf1.Data4+4], eax
0x18004c11e  lea     rcx, [rbp+4C0h+Buf1]; Buf1
0x18004c122  call    ?IsValidEncryptionScheme@@YA_NU_GUID@@@Z; IsValidEncryptionScheme(_GUID)
0x18004c127  test    al, al
0x18004c129  jz      short loc_18004C135
0x18004c12b  inc     ebx
0x18004c12d  cmp     ebx, [rsp+5C0h+var_578]
0x18004c131  jb      short loc_18004C0E0
0x18004c133  jmp     short loc_18004C180
0x18004c135  movaps  xmm0, [rbp+4C0h+var_4B0]
0x18004c139  movaps  [rbp+4C0h+var_430], xmm0
0x18004c140  movaps  xmm1, [rbp+4C0h+var_4A0]
0x18004c144  movaps  [rbp+4C0h+var_420], xmm1
0x18004c14b  movaps  xmm0, [rbp+4C0h+var_490]
0x18004c14f  movaps  [rbp+4C0h+var_410], xmm0
0x18004c156  movaps  xmm1, [rbp+4C0h+var_480]
0x18004c15a  movaps  [rbp+4C0h+var_400], xmm1
0x18004c161  movaps  xmm0, [rbp+4C0h+var_470]
0x18004c165  movaps  [rbp+4C0h+var_3F0], xmm0
0x18004c16c  movaps  xmm1, [rbp+4C0h+var_460]
0x18004c170  movaps  [rbp+4C0h+var_3E0], xmm1
0x18004c177  mov     eax, [rbp+4C0h+var_450]
0x18004c17a  mov     [rbp+4C0h+var_3D0], eax
0x18004c180  xor     ebx, ebx
0x18004c182  cmp     [rsp+5C0h+var_578], ebx
0x18004c186  jbe     loc_18004C2B1
0x18004c18c  mov     rcx, [rsp+5C0h+var_570]
0x18004c191  mov     rax, [rcx]
0x18004c194  lea     r9, [rbp+4C0h+var_4B0]
0x18004c198  mov     r8d, ebx
0x18004c19b  lea     rdx, [rbp+4C0h+var_4D8]
0x18004c19f  mov     rax, [rax+78h]
  ... truncated ...
```
