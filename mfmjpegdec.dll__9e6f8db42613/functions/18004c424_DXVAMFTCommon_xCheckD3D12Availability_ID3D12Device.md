# DXVAMFTCommon::xCheckD3D12Availability(ID3D12Device *)

- ea: `0x18004c424`
- end: `0x18004ca70`
- name: `?xCheckD3D12Availability@DXVAMFTCommon@@AEAAJPEAUID3D12Device@@@Z`
- size: `1612`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, struct ID3D12Device *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004d23c`

## callees

- `0x180020598`
- `0x180024220`
- `0x1800245f0`
- `0x18003a54c`
- `0x1800431f4`
- `0x180044d78`
- `0x18004aa94`
- `0x18004acfc`
- `0x18004aed8`
- `0x18004b128`
- `0x18004b30c`
- `0x18004b56c`
- `0x18004b9d0`
- `0x18004bcd4`
- `0x18004c424`
- `0x18004dad4`
- `0x180055bec`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DXVAMFTCommon::xCheckD3D12Availability(DXVAMFTCommon *this, struct ID3D12Device *a2)
{
  unsigned int v4; // r13d
  void *v5; // r14
  void *v6; // r15
  HRESULT (__stdcall *QueryInterface)(ID3D12Device *, const IID *const, void **); // rbx
  const struct std::nothrow_t *v8; // rdx
  unsigned int v9; // ebx
  _OWORD *v10; // rax
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rbx
  void *v15; // rcx
  __int64 i; // r14
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  void *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  void *v25; // [rsp+98h] [rbp-68h]
  void *v26; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+A8h] [rbp-58h] BYREF
  void *v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[24]; // [rsp+B8h] [rbp-48h] BYREF
  char v30[16]; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+E4h] [rbp-1Ch]
  __int64 v33; // [rsp+F4h] [rbp-Ch]
  _BYTE v34[12]; // [rsp+FCh] [rbp-4h] BYREF
  __int128 v35; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v36[2]; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v37[76]; // [rsp+140h] [rbp+40h] BYREF
  char v38; // [rsp+270h] [rbp+170h]
  char v39[4]; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int128 v40; // [rsp+3ACh] [rbp+2ACh]
  int v41; // [rsp+3BCh] [rbp+2BCh]
  int v42; // [rsp+3C4h] [rbp+2C4h]
  int v43; // [rsp+3C8h] [rbp+2C8h]
  int v44; // [rsp+3CCh] [rbp+2CCh]
  char v45; // [rsp+3DCh] [rbp+2DCh]
  int v46; // [rsp+3E4h] [rbp+2E4h]
  _BYTE v47[24]; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v48; // [rsp+400h] [rbp+300h]

  v4 = 0;
  v23 = 0;
  v27 = 0;
  v24 = 0;
  v25 = 0;
  v32 = 0;
  memset(v34, 0, sizeof(v34));
  memset(v36, 0, sizeof(v36));
  v35 = 0;
  v5 = 0;
  v22 = 0;
  v6 = 0;
  v28 = 0;
  v31 = 0;
  v33 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v9 = ((__int64 (__fastcall *)(struct ID3D12Device *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_1f052807_0b46_4acc_8a89_364f793718a4,
         &v23);
  if ( !v9 )
  {
    if ( g_wppLevels >= 4u )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, 0, this);
    dxva_utils::GetAdapaterDescription((__int64)v37, (__int64)a2);
    if ( v38 )
    {
      v10 = (_OWORD *)((char *)this + 24);
      v11 = v37;
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
    }
    else if ( g_wppLevels )
    {
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, v37[0], this);
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, 10, &v27);
    if ( !v9 )
    {
      HIDWORD(v24) = HIDWORD(v27);
      LODWORD(v24) = 0;
      v26 = operator new[](saturated_mul(HIDWORD(v27), 0x10u));
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v28, &v26);
      if ( v26 )
        operator delete(v26, v8);
      v6 = v28;
      v25 = v28;
      if ( v28 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64))(*(_QWORD *)v23 + 24LL))(v23, 1, &v24, 16);
        if ( !v9 )
        {
          utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::clear((char *)this + 352);
          if ( g_wppLevels >= 4u )
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
              HIDWORD(v24),
              this);
          while ( (*(unsigned __int8 (__fastcall **)(DXVAMFTCommon *, _QWORD, _QWORD, void *, __int128 *))(*(_QWORD *)this + 16LL))(
                    this,
                    v4,
                    HIDWORD(v24),
                    v25,
                    &v35) )
          {
            DXVAConfiguration::DXVAConfiguration((DXVAConfiguration *)v37);
            LODWORD(v36[0]) = 0;
            *(_QWORD *)((char *)&v36[1] + 4) = 0;
            *(_OWORD *)((char *)v36 + 4) = v35;
            if ( g_wppLevels )
              WPP_SF_LHHHHHHHHHHq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                BYTE13(v35),
                BYTE12(v35),
                v35,
                SBYTE4(v35),
                SBYTE6(v35),
                SBYTE8(v35),
                SBYTE9(v35),
                SBYTE10(v35),
                SBYTE11(v35),
                SBYTE12(v35),
                SBYTE13(v35),
                SBYTE14(v35),
                SHIBYTE(v35),
                (char)this);
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)v23 + 24LL))(v23, 11, v36);
            if ( v9 )
              goto LABEL_39;
            v32 = *(_OWORD *)((char *)v36 + 4);
            v33 = *(_QWORD *)((char *)&v36[1] + 4);
            *(_DWORD *)v34 = HIDWORD(v36[1]);
            v14 = operator new[](saturated_mul(HIDWORD(v36[1]), 4u));
            v15 = v22;
            v22 = v14;
            if ( v15 )
              operator delete(v15, v13);
            *(_QWORD *)&v34[4] = v14;
            if ( !v14 )
            {
              v9 = -2147024882;
LABEL_39:
              utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::clear(v47);
              goto LABEL_46;
            }
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v23 + 24LL))(v23, 2, &v31);
            if ( v9 )
              goto LABEL_39;
            for ( i = 0; (unsigned int)i < *(_DWORD *)v34; i = (unsigned int)(i + 1) )
            {
              v17 = 4 * i;
              if ( g_wppLevels >= 4u )
                WPP_SF_dq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids,
                  *(unsigned int *)(v17 + *(_QWORD *)&v34[4]),
                  this);
              v44 = *(_DWORD *)(v17 + *(_QWORD *)&v34[4]);
              v40 = v35;
              v41 = 0;
              v42 = 144;
              v43 = 144;
              v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v23 + 24LL))(
                     v23,
                     0,
                     v39,
                     64);
              if ( v9 )
                break;
              if ( (v45 & 1) != 0 && v46 )
                utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::_InsertImpl<enum DXGI_FORMAT const &>(
                  v47,
                  v30,
                  0,
                  v17 + *(_QWORD *)&v34[4]);
            }
            if ( v48 )
            {
              utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(
                (char *)this + 352,
                v29,
                &v35);
              if ( !v29[16] )
              {
                v20 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_NewNodeConstruct<utl::_PairMapTag,_GUID const &,DXVAConfiguration>(
                        v19,
                        v18,
                        &v35,
                        v37);
                if ( v20 )
                  utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(
                    (char *)this + 352,
                    &v26,
                    v29,
                    v20);
              }
            }
            utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::clear(v47);
            ++v4;
          }
          if ( !v9 && !*((_QWORD *)this + 47) )
          {
            if ( g_wppLevels >= 4u )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, this);
            v9 = -1072875818;
          }
LABEL_46:
          v5 = v22;
        }
      }
      else
      {
        v9 = -2147024882;
      }
    }
  }
  if ( g_wppLevels >= 4u )
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, v9, this);
  if ( v6 )
    operator delete(v6, v8);
  if ( v5 )
    operator delete(v5, v8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  return v9;
}

```

## disassembly

```asm
0x18004c424  mov     [rsp-8+arg_10], rbx
0x18004c429  push    rbp
0x18004c42a  push    rsi
0x18004c42b  push    rdi
0x18004c42c  push    r12
0x18004c42e  push    r13
0x18004c430  push    r14
0x18004c432  push    r15
0x18004c434  lea     rbp, [rsp-320h]
0x18004c43c  sub     rsp, 420h
0x18004c443  mov     rax, cs:__security_cookie
0x18004c44a  xor     rax, rsp
0x18004c44d  mov     [rbp+350h+var_40], rax
0x18004c454  mov     rdi, rdx
0x18004c457  mov     rsi, rcx
0x18004c45a  xor     r13d, r13d
0x18004c45d  mov     [rbp+350h+var_3C8], r13
0x18004c461  mov     [rbp+350h+var_3A8], r13
0x18004c465  mov     [rbp+350h+var_3C0], r13
0x18004c469  mov     [rbp+350h+var_3B8], r13
0x18004c46d  xorps   xmm0, xmm0
0x18004c470  movdqu  [rbp+350h+var_36C], xmm0
0x18004c475  mov     [rbp+350h+var_354], r13
0x18004c479  mov     [rbp+350h+var_34C], r13d
0x18004c47d  movups  [rbp+350h+var_338], xmm0
0x18004c481  movups  [rbp+350h+var_328], xmm0
0x18004c485  movups  [rbp+350h+var_348], xmm0
0x18004c489  mov     r14d, r13d
0x18004c48c  mov     [rbp+350h+var_3D0], r13
0x18004c490  mov     r15d, r13d
0x18004c493  mov     [rbp+350h+var_3A0], r13
0x18004c497  mov     [rbp+350h+var_370], r13d
0x18004c49b  mov     [rbp+350h+var_35C], r13
0x18004c49f  mov     rax, [rdx]
0x18004c4a2  mov     rbx, [rax]
0x18004c4a5  lea     rcx, [rbp+350h+var_3C8]
0x18004c4a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c4ae  lea     r8, [rbp+350h+var_3C8]
0x18004c4b2  lea     rdx, _GUID_1f052807_0b46_4acc_8a89_364f793718a4
0x18004c4b9  mov     rcx, rdi
0x18004c4bc  mov     rax, rbx
0x18004c4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4c4  mov     ebx, eax
0x18004c4c6  test    eax, eax
0x18004c4c8  jnz     loc_18004C9F1
0x18004c4ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18004c4d5  jb      short loc_18004C4F9
0x18004c4d7  lea     edx, [rax+0Eh]
0x18004c4da  mov     [rsp+450h+var_430], rsi
0x18004c4df  xor     r9d, r9d
0x18004c4e2  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004c4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4f0  mov     rcx, [rcx+10h]
0x18004c4f4  call    WPP_SF_dq
0x18004c4f9  mov     rdx, rdi
0x18004c4fc  lea     rcx, [rbp+350h+var_310]
0x18004c500  call    ?GetAdapaterDescription@dxva_utils@@YA?AV?$expected@UDXGI_ADAPTER_DESC@@J@std@@AEAUID3D12Device@@@Z; dxva_utils::GetAdapaterDescription(ID3D12Device &)
0x18004c505  cmp     [rbp+350h+var_1E0], r13b
0x18004c50c  jz      short loc_18004C581
0x18004c50e  lea     rax, [rsi+18h]
0x18004c512  lea     rcx, [rbp+350h+var_310]
0x18004c516  mov     edx, 2
0x18004c51b  lea     r8d, [rdx+7Eh]
0x18004c51f  movups  xmm0, xmmword ptr [rcx]
0x18004c522  movups  xmmword ptr [rax], xmm0
0x18004c525  movups  xmm1, xmmword ptr [rcx+10h]
0x18004c529  movups  xmmword ptr [rax+10h], xmm1
0x18004c52d  movups  xmm0, xmmword ptr [rcx+20h]
0x18004c531  movups  xmmword ptr [rax+20h], xmm0
0x18004c535  movups  xmm1, xmmword ptr [rcx+30h]
0x18004c539  movups  xmmword ptr [rax+30h], xmm1
0x18004c53d  movups  xmm0, xmmword ptr [rcx+40h]
0x18004c541  movups  xmmword ptr [rax+40h], xmm0
0x18004c545  movups  xmm1, xmmword ptr [rcx+50h]
0x18004c549  movups  xmmword ptr [rax+50h], xmm1
0x18004c54d  movups  xmm0, xmmword ptr [rcx+60h]
0x18004c551  movups  xmmword ptr [rax+60h], xmm0
0x18004c555  movups  xmm1, xmmword ptr [rcx+70h]
0x18004c559  movups  xmmword ptr [rax+70h], xmm1
0x18004c55d  add     rax, r8
0x18004c560  add     rcx, r8
0x18004c563  sub     rdx, 1
0x18004c567  jnz     short loc_18004C51F
0x18004c569  movups  xmm0, xmmword ptr [rcx]
0x18004c56c  movups  xmmword ptr [rax], xmm0
0x18004c56f  movups  xmm1, xmmword ptr [rcx+10h]
0x18004c573  movups  xmmword ptr [rax+10h], xmm1
0x18004c577  movups  xmm0, xmmword ptr [rcx+20h]
0x18004c57b  movups  xmmword ptr [rax+20h], xmm0
0x18004c57f  jmp     short loc_18004C5AF
0x18004c581  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c588  jb      short loc_18004C5AF
0x18004c58a  mov     edx, 0Fh
0x18004c58f  mov     [rsp+450h+var_430], rsi
0x18004c594  mov     r9d, [rbp+350h+var_310]
0x18004c598  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004c59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c5a6  mov     rcx, [rcx+10h]
0x18004c5aa  call    WPP_SF_dq
0x18004c5af  mov     rcx, [rbp+350h+var_3C8]
0x18004c5b3  mov     rax, [rcx]
0x18004c5b6  mov     r9d, 8
0x18004c5bc  lea     r8, [rbp+350h+var_3A8]
0x18004c5c0  lea     edx, [r9+2]
0x18004c5c4  mov     rax, [rax+18h]
0x18004c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5cd  mov     ebx, eax
0x18004c5cf  test    eax, eax
0x18004c5d1  jnz     loc_18004C9F1
0x18004c5d7  mov     eax, dword ptr [rbp+350h+var_3A8+4]
0x18004c5da  mov     dword ptr [rbp+350h+var_3C0+4], eax
0x18004c5dd  mov     dword ptr [rbp+350h+var_3C0], r13d
0x18004c5e1  mov     ecx, eax
0x18004c5e3  lea     edi, [rbx+10h]
0x18004c5e6  mov     eax, edi
0x18004c5e8  mul     rcx
0x18004c5eb  lea     rcx, [rdi-11h]
0x18004c5ef  cmovb   rax, rcx
0x18004c5f3  mov     rcx, rax; unsigned __int64
0x18004c5f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004c5fb  mov     [rbp+350h+var_3B0], rax
0x18004c5ff  lea     rdx, [rbp+350h+var_3B0]
0x18004c603  lea     rcx, [rbp+350h+var_3A0]
0x18004c607  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18004c60c  mov     rcx, [rbp+350h+var_3B0]; void *
0x18004c610  test    rcx, rcx
0x18004c613  jz      short loc_18004C61A
0x18004c615  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004c61a  mov     r15, [rbp+350h+var_3A0]
0x18004c61e  mov     [rbp+350h+var_3B8], r15
0x18004c622  test    r15, r15
0x18004c625  jnz     short loc_18004C631
0x18004c627  mov     ebx, 8007000Eh
0x18004c62c  jmp     loc_18004C9F1
0x18004c631  mov     rcx, [rbp+350h+var_3C8]
0x18004c635  mov     rax, [rcx]
0x18004c638  mov     r9d, edi
0x18004c63b  lea     r8, [rbp+350h+var_3C0]
0x18004c63f  mov     edx, 1
0x18004c644  mov     rax, [rax+18h]
0x18004c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c64d  mov     ebx, eax
0x18004c64f  test    eax, eax
0x18004c651  jnz     loc_18004C9F1
0x18004c657  lea     r12, [rsi+160h]
0x18004c65e  mov     rcx, r12
0x18004c661  call    ?clear@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::clear(void)
0x18004c666  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18004c66d  jb      short loc_18004C691
0x18004c66f  mov     edx, edi
0x18004c671  mov     [rsp+450h+var_430], rsi
0x18004c676  mov     r9d, dword ptr [rbp+350h+var_3C0+4]
0x18004c67a  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004c681  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c688  mov     rcx, [rcx+10h]
0x18004c68c  call    WPP_SF_dq
0x18004c691  mov     rax, [rsi]
0x18004c694  lea     rcx, [rbp+350h+var_348]
0x18004c698  mov     [rsp+450h+var_430], rcx
0x18004c69d  mov     r9, [rbp+350h+var_3B8]
0x18004c6a1  mov     r8d, dword ptr [rbp+350h+var_3C0+4]
0x18004c6a5  mov     edx, r13d
0x18004c6a8  mov     rcx, rsi
0x18004c6ab  mov     rax, [rax+10h]
0x18004c6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6b4  test    al, al
0x18004c6b6  jz      loc_18004C9B2
0x18004c6bc  lea     rcx, [rbp+350h+var_310]; this
0x18004c6c0  call    ??0DXVAConfiguration@@QEAA@XZ; DXVAConfiguration::DXVAConfiguration(void)
0x18004c6c5  nop
0x18004c6c6  mov     dword ptr [rbp+350h+var_338], 0
0x18004c6cd  mov     qword ptr [rbp+350h+var_328+4], 0
0x18004c6d5  mov     r9d, dword ptr [rbp+350h+var_348]
0x18004c6d9  mov     dword ptr [rbp+350h+var_338+4], r9d
0x18004c6dd  movzx   r14d, word ptr [rbp+350h+var_348+4]
0x18004c6e2  mov     word ptr [rbp+350h+var_338+8], r14w
0x18004c6e7  movzx   eax, word ptr [rbp+350h+var_348+6]
0x18004c6eb  mov     word ptr [rbp+350h+var_338+0Ah], ax
0x18004c6ef  movzx   edi, byte ptr [rbp+350h+var_348+8]
0x18004c6f3  mov     byte ptr [rbp+350h+var_338+0Ch], dil
0x18004c6f7  movzx   ebx, byte ptr [rbp+350h+var_348+9]
0x18004c6fb  mov     byte ptr [rbp+350h+var_338+0Dh], bl
0x18004c6fe  movzx   r11d, byte ptr [rbp+350h+var_348+0Ah]
0x18004c703  mov     byte ptr [rbp+350h+var_338+0Eh], r11b
0x18004c707  movzx   r10d, byte ptr [rbp+350h+var_348+0Bh]
0x18004c70c  mov     byte ptr [rbp+350h+var_338+0Fh], r10b
0x18004c710  movzx   r8d, byte ptr [rbp+350h+var_348+0Ch]
0x18004c715  mov     byte ptr [rbp+350h+var_328], r8b
0x18004c719  movzx   edx, byte ptr [rbp+350h+var_348+0Dh]
0x18004c71d  mov     byte ptr [rbp+350h+var_328+1], dl
0x18004c720  movzx   ecx, byte ptr [rbp+350h+var_348+0Eh]
0x18004c724  mov     byte ptr [rbp+350h+var_328+2], cl
0x18004c727  movzx   eax, byte ptr [rbp+350h+var_348+0Fh]
0x18004c72b  mov     byte ptr [rbp+350h+var_328+3], al
0x18004c72e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c735  jb      short loc_18004C786
0x18004c737  mov     [rsp+450h+var_3E0], rsi
0x18004c73c  mov     [rsp+450h+var_3E8], ax
0x18004c741  mov     [rsp+450h+var_3F0], cx
0x18004c746  mov     [rsp+450h+var_3F8], dx
0x18004c74b  mov     [rsp+450h+var_400], r8w
0x18004c751  mov     [rsp+450h+var_408], r10w
0x18004c757  mov     [rsp+450h+var_410], r11w
0x18004c75d  mov     [rsp+450h+var_418], bx
0x18004c762  mov     [rsp+450h+var_420], di
0x18004c767  movzx   eax, word ptr [rbp+350h+var_348+6]
0x18004c76b  mov     [rsp+450h+var_428], ax
0x18004c770  mov     word ptr [rsp+450h+var_430], r14w
0x18004c776  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c77d  mov     rcx, [rcx+10h]
0x18004c781  call    WPP_SF_LHHHHHHHHHHq
0x18004c786  mov     rcx, [rbp+350h+var_3C8]
0x18004c78a  mov     rax, [rcx]
0x18004c78d  mov     r9d, 20h ; ' '
0x18004c793  lea     r8, [rbp+350h+var_338]
0x18004c797  lea     edx, [r9-15h]
0x18004c79b  mov     rax, [rax+18h]
0x18004c79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7a4  mov     ebx, eax
0x18004c7a6  test    eax, eax
0x18004c7a8  jnz     loc_18004C99D
0x18004c7ae  mov     eax, dword ptr [rbp+350h+var_338+4]
0x18004c7b1  mov     dword ptr [rbp+350h+var_36C], eax
0x18004c7b4  movzx   eax, word ptr [rbp+350h+var_338+8]
0x18004c7b8  mov     word ptr [rbp+350h+var_36C+4], ax
0x18004c7bc  movzx   eax, word ptr [rbp+350h+var_338+0Ah]
0x18004c7c0  mov     word ptr [rbp+350h+var_36C+6], ax
0x18004c7c4  mov     al, byte ptr [rbp+350h+var_338+0Ch]
0x18004c7c7  mov     byte ptr [rbp+350h+var_36C+8], al
0x18004c7ca  mov     al, byte ptr [rbp+350h+var_338+0Dh]
0x18004c7cd  mov     byte ptr [rbp+350h+var_36C+9], al
0x18004c7d0  mov     al, byte ptr [rbp+350h+var_338+0Eh]
0x18004c7d3  mov     byte ptr [rbp+350h+var_36C+0Ah], al
0x18004c7d6  mov     al, byte ptr [rbp+350h+var_338+0Fh]
0x18004c7d9  mov     byte ptr [rbp+350h+var_36C+0Bh], al
0x18004c7dc  mov     al, byte ptr [rbp+350h+var_328]
0x18004c7df  mov     byte ptr [rbp+350h+var_36C+0Ch], al
0x18004c7e2  mov     al, byte ptr [rbp+350h+var_328+1]
0x18004c7e5  mov     byte ptr [rbp+350h+var_36C+0Dh], al
0x18004c7e8  mov     al, byte ptr [rbp+350h+var_328+2]
0x18004c7eb  mov     byte ptr [rbp+350h+var_36C+0Eh], al
0x18004c7ee  mov     al, byte ptr [rbp+350h+var_328+3]
0x18004c7f1  mov     byte ptr [rbp+350h+var_36C+0Fh], al
0x18004c7f4  mov     eax, dword ptr [rbp+350h+var_328+4]
0x18004c7f7  mov     dword ptr [rbp+350h+var_35C], eax
0x18004c7fa  mov     eax, dword ptr [rbp+350h+var_328+8]
0x18004c7fd  mov     dword ptr [rbp+350h+var_35C+4], eax
0x18004c800  mov     eax, dword ptr [rbp+350h+var_328+0Ch]
0x18004c803  mov     dword ptr [rbp+350h+var_354], eax
0x18004c806  mov     ecx, eax
0x18004c808  lea     eax, [rbx+4]
0x18004c80b  mul     rcx
0x18004c80e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004c815  cmovb   rax, rcx
0x18004c819  mov     rcx, rax; unsigned __int64
0x18004c81c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004c821  mov     rbx, rax
0x18004c824  mov     rcx, [rbp+350h+var_3D0]; void *
0x18004c828  mov     [rbp+350h+var_3D0], rax
0x18004c82c  test    rcx, rcx
0x18004c82f  jz      short loc_18004C836
0x18004c831  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004c836  mov     [rbp+350h+var_354+4], rbx
0x18004c83a  test    rbx, rbx
0x18004c83d  jz      loc_18004C9AB
0x18004c843  mov     rcx, [rbp+350h+var_3C8]
0x18004c847  mov     rax, [rcx]
0x18004c84a  mov     r9d, 28h ; '('
0x18004c850  lea     r8, [rbp+350h+var_370]
0x18004c854  lea     edx, [r9-26h]
0x18004c858  mov     rax, [rax+18h]
0x18004c85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c861  mov     ebx, eax
0x18004c863  test    eax, eax
0x18004c865  jnz     loc_18004C99D
0x18004c86b  xor     r14d, r14d
0x18004c86e  cmp     dword ptr [rbp+350h+var_354], r14d
0x18004c872  jbe     loc_18004C943
0x18004c878  lea     rdi, ds:0[r14*4]
0x18004c880  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18004c887  jb      short loc_18004C8B2
0x18004c889  mov     edx, 12h
0x18004c88e  mov     [rsp+450h+var_430], rsi
0x18004c893  mov     r9, [rbp+350h+var_354+4]
0x18004c897  mov     r9d, [rdi+r9]
0x18004c89b  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004c8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8a9  mov     rcx, [rcx+10h]
0x18004c8ad  call    WPP_SF_dq
0x18004c8b2  mov     rax, [rbp+350h+var_354+4]
0x18004c8b6  mov     ecx, [rdi+rax]
0x18004c8b9  mov     [rbp+350h+var_84], ecx
0x18004c8bf  movups  xmm0, [rbp+350h+var_348]
0x18004c8c3  movdqu  [rbp+350h+var_A4], xmm0
0x18004c8cb  mov     [rbp+350h+var_94], 0
0x18004c8d5  mov     eax, 90h
0x18004c8da  mov     [rbp+350h+var_8C], eax
0x18004c8e0  mov     [rbp+350h+var_88], eax
0x18004c8e6  mov     rcx, [rbp+350h+var_3C8]
0x18004c8ea  mov     rax, [rcx]
  ... truncated ...
```
