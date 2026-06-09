# CDX12DecodeCore::AllocateResources(DXVAVideoDesc const &,DXVAParams_tag const *)

- ea: `0x180048ac4`
- end: `0x1800492e1`
- name: `?AllocateResources@CDX12DecodeCore@@IEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@@Z`
- size: `2077`
- prototype: `__int64 __fastcall(CDX12DecodeCore *__hidden this, const struct DXVAVideoDesc *, const struct DXVAParams_tag *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800499c0`

## callees

- `0x180020598`
- `0x180024220`
- `0x1800245f0`
- `0x180024bf4`
- `0x18003a54c`
- `0x18003a628`
- `0x18003e5ec`
- `0x1800432d8`
- `0x180043300`
- `0x180048ac4`
- `0x18004a1b8`
- `0x18004a4ec`
- `0x18004aa30`
- `0x18004aa94`
- `0x18004aae4`
- `0x180054e08`
- `0x1800553c4`
- `0x180070010`

## string_xrefs

- `0x180049162`: `DXVA Command Queue`
- `0x1800491d2`: `DXVA Command List`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDX12DecodeCore::AllocateResources(
        CDX12DecodeCore *this,
        const struct DXVAVideoDesc *a2,
        const struct DXVAParams_tag *a3)
{
  unsigned int v5; // r12d
  int v6; // r13d
  int v7; // ecx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, char *); // rbx
  unsigned int Resources; // ebx
  _QWORD *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r14
  void *v15; // rax
  const struct std::nothrow_t *v16; // rdx
  void *v17; // rcx
  __int64 v18; // rax
  bool v19; // cf
  unsigned __int64 v20; // rax
  unsigned __int64 *v21; // rax
  __int64 v22; // rdx
  __int16 v23; // dx
  unsigned __int16 v24; // bx
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, char *); // rbx
  unsigned __int16 v29; // r8
  __int64 v30; // rdx
  unsigned __int16 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int16 v34; // dx
  unsigned __int16 i; // bx
  __int64 v36; // rdi
  struct DXVAParams_tag *v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD *, GUID *, char *); // rbx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64, __int64, _QWORD, GUID *, char *); // rbx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, char *); // rbx
  _QWORD *v45; // r15
  unsigned __int16 j; // r8
  __int64 v47; // rdx
  bool v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  int v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  struct DXVAParams_tag *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+90h] [rbp-70h]
  __int16 v57; // [rsp+94h] [rbp-6Ch]
  __int16 v58; // [rsp+96h] [rbp-6Ah]
  int v59; // [rsp+98h] [rbp-68h]
  __int64 v60; // [rsp+9Ch] [rbp-64h]
  int v61; // [rsp+A4h] [rbp-5Ch]
  int v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  int v64; // [rsp+B8h] [rbp-48h]
  int v65; // [rsp+BCh] [rbp-44h]
  int v66; // [rsp+C0h] [rbp-40h]
  _QWORD v67[3]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v68[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v69; // [rsp+E4h] [rbp-1Ch]
  int v70; // [rsp+F4h] [rbp-Ch]
  unsigned int v71; // [rsp+FCh] [rbp-4h]
  int v72; // [rsp+100h] [rbp+0h]
  int v73; // [rsp+104h] [rbp+4h]
  int v74; // [rsp+118h] [rbp+18h]
  int v75; // [rsp+11Ch] [rbp+1Ch]

  v52 = a3;
  memset_0(v68, 0, 0x40u);
  if ( *((_QWORD *)this + 2) )
  {
    v5 = *(_DWORD *)a2;
    v6 = *((_DWORD *)a2 + 1);
    v7 = *((_DWORD *)a2 + 2);
    v50 = v7;
    if ( (unsigned int)(v7 - 103) <= 1 || v7 == 105 )
    {
      v5 += v5 & 1;
      v6 += v6 & 1;
    }
    if ( g_wppLevels >= 8u )
      WPP_SF_ddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
        v5,
        v6,
        this);
    v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 2);
    v9 = **v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
    Resources = v9(v8, &GUID_1f052807_0b46_4acc_8a89_364f793718a4, (char *)this + 24);
    v11 = 0;
    if ( Resources )
      return Resources;
    v69 = *(_OWORD *)((char *)a2 + 12);
    v70 = 0;
    v71 = v5;
    v72 = v6;
    v73 = *((_DWORD *)a2 + 2);
    if ( !*((_BYTE *)this + 1385) )
    {
      Resources = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 3) + 24LL))(
                    *((_QWORD *)this + 3),
                    0,
                    v68,
                    Resources + 64);
      if ( Resources )
        return Resources;
      if ( g_wppLevels >= 4u )
        WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, 0, v75, this);
      if ( !v75 )
        return (unsigned int)-1072861834;
    }
    v14 = *((unsigned __int16 *)a2 + 16);
    if ( g_wppLevels >= 8u )
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
        *((unsigned __int16 *)a2 + 16),
        this);
    if ( *((_DWORD *)this + 28) )
      CDX12DecodeCore::ReleaseOutputStreamArgs(this);
    LODWORD(v49) = v74 & 4;
    v48 = v75 >= 2;
    v15 = operator new[](saturated_mul(v14, 0x30u));
    v51 = 0;
    v17 = (void *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v15;
    if ( v17 )
      operator delete(v17, v16);
    wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(&v51);
    if ( !*((_QWORD *)this + 10) )
      return (unsigned int)-2147024882;
    v18 = 8 * v14;
    if ( !is_mul_ok(v14, 8u) )
      v18 = -1;
    v19 = __CFADD__(v18, 8);
    v20 = v18 + 8;
    if ( v19 )
      v20 = -1;
    v21 = (unsigned __int64 *)operator new[](v20);
    if ( v21 )
    {
      *v21 = v14;
      v11 = v21 + 1;
      `eh vector constructor iterator'(
        v21 + 1,
        8u,
        v14,
        Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>::ComPtr<ID3D11VideoDecoderOutputView>,
        Microsoft::WRL::ComPtr<ID3D12CommandAllocator>::~ComPtr<ID3D12CommandAllocator>);
    }
    v51 = 0;
    v22 = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v11;
    if ( v22 )
      wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>();
    wistd::unique_ptr<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0],wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>>::reset(&v51);
    if ( !*((_QWORD *)this + 13) )
      return (unsigned int)-2147024882;
    memset_0(*((void **)this + 10), 0, 48 * v14);
    v63 = 1;
    v64 = 0;
    v65 = 1;
    v66 = 1;
    if ( !(_DWORD)v49 )
    {
LABEL_46:
      v34 = 1;
      if ( !v48 )
        v34 = v14;
      v53 = 3;
      v54 = 0;
      v55 = v5;
      v56 = v6;
      v57 = v34;
      v58 = 1;
      v59 = v50;
      v60 = 1;
      v61 = 0;
      v62 = 32;
      if ( v48 )
      {
        if ( !*((_BYTE *)this + 1384) )
        {
          for ( i = 0; i < (unsigned __int16)v14; ++i )
          {
            v36 = 48LL * i;
            if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, __int64))(**((_QWORD **)this + 2) + 216LL))(
                   *((_QWORD *)this + 2),
                   &v63,
                   1,
                   &v53,
                   0,
                   0,
                   &GUID_696442be_a72e_4059_bc79_5b5c98040fad,
                   v36 + *((_QWORD *)this + 10)) )
            {
              break;
            }
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**(_QWORD **)(v36 + *((_QWORD *)this + 10)) + 48LL))(
              *(_QWORD *)(v36 + *((_QWORD *)this + 10)),
              L"DXVA DPB reference buffer");
          }
        }
      }
      else
      {
        v43 = *((_QWORD *)this + 2);
        v44 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, char *))(*(_QWORD *)v43 + 216LL);
        v45 = (_QWORD *)((char *)this + 88);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
        Resources = v44(v43, &v63, 1, &v53, 0, 0, &GUID_696442be_a72e_4059_bc79_5b5c98040fad, (char *)this + 88);
        if ( Resources )
          return Resources;
        (*(void (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v45 + 48LL))(*v45, L"DXVA DPB reference array");
        for ( j = 0; j < (unsigned __int16)v14; ++j )
        {
          v47 = 6LL * j;
          *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v47) = *v45;
          *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v47 + 8) = j;
        }
      }
      *((_DWORD *)this + 28) = v14;
      v37 = v52;
      *(_OWORD *)((char *)this + 1192) = *(_OWORD *)v52;
      *(_OWORD *)((char *)this + 1208) = *((_OWORD *)v37 + 1);
      *(_OWORD *)((char *)this + 1224) = *((_OWORD *)v37 + 2);
      *(_OWORD *)((char *)this + 1240) = *((_OWORD *)v37 + 3);
      *(_OWORD *)((char *)this + 1256) = *((_OWORD *)v37 + 4);
      *(_OWORD *)((char *)this + 1272) = *((_OWORD *)v37 + 5);
      *(_OWORD *)((char *)this + 1288) = *((_OWORD *)v37 + 6);
      *(_OWORD *)((char *)this + 1304) = *((_OWORD *)v37 + 7);
      Resources = DecoderBuffersList::AllocateResources(
                    (CDX12DecodeCore *)((char *)this + 584),
                    *((struct ID3D12Device *const *)this + 2),
                    v37);
      if ( !Resources )
      {
        *((_BYTE *)this + 1320) = 0;
        v67[0] = 4;
        v67[1] = 0;
        v38 = *((_QWORD *)this + 2);
        v39 = *(__int64 (__fastcall **)(__int64, _QWORD *, GUID *, char *))(*(_QWORD *)v38 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
        Resources = v39(v38, v67, &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed, (char *)this + 56);
        if ( !Resources )
        {
          (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 7) + 48LL))(
            *((_QWORD *)this + 7),
            L"DXVA Command Queue");
          v49 = 0;
          DecoderBuffersList::GetCommandAllocator((char *)this + 584, &v49);
          v40 = *((_QWORD *)this + 2);
          v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD, GUID *, char *))(*(_QWORD *)v40 + 96LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
          Resources = v41(v40, 0, 4, v49, 0, &GUID_7116d91c_e7e4_47ce_b8c6_ec8168f437e5, (char *)this + 64);
          if ( !Resources )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"DXVA Command List");
            *((_DWORD *)this + 18) = 0;
            CDX12DecodeCore::UpdateReferenceFrameInputArguments(this);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
        }
      }
      return Resources;
    }
    v23 = 1;
    if ( !v48 )
      v23 = v14;
    v53 = 3;
    v54 = 0;
    v55 = v5;
    v56 = v6;
    v57 = v23;
    v58 = 1;
    v59 = v50;
    v60 = 1;
    v61 = 0;
    v62 = 72;
    if ( v48 )
    {
      v24 = 0;
      if ( (_WORD)v14 )
      {
        while ( 1 )
        {
          v25 = 48LL * v24;
          if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, __int64))(**((_QWORD **)this + 2) + 216LL))(
                 *((_QWORD *)this + 2),
                 &v63,
                 1,
                 &v53,
                 0,
                 0,
                 &GUID_696442be_a72e_4059_bc79_5b5c98040fad,
                 v25 + *((_QWORD *)this + 10) + 24LL) )
          {
            break;
          }
          v26 = *(_QWORD *)(v25 + *((_QWORD *)this + 10) + 24);
          (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v26 + 48LL))(v26, L"DXVA Post-proc OPB Buffer");
          if ( ++v24 >= (unsigned __int16)v14 )
            goto LABEL_42;
        }
      }
    }
    else
    {
      v27 = *((_QWORD *)this + 2);
      v28 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, int *, _DWORD, _QWORD, GUID *, char *))(*(_QWORD *)v27 + 216LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
      Resources = v28(v27, &v63, 1, &v53, 0, 0, &GUID_696442be_a72e_4059_bc79_5b5c98040fad, (char *)this + 96);
      if ( Resources )
        return Resources;
      (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 12) + 48LL))(
        *((_QWORD *)this + 12),
        L"DXVA Post-proc OPB array");
      v29 = 0;
      if ( (_WORD)v14 )
      {
        do
        {
          v30 = 6LL * v29;
          *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v30 + 24) = *((_QWORD *)this + 12);
          *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v30 + 32) = v29++;
        }
        while ( v29 < (unsigned __int16)v14 );
LABEL_42:
        v31 = 0;
LABEL_44:
        v32 = 0;
        do
        {
          v33 = 6 * v32;
          *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v33 + 16) = 1;
          *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v33 + 40) = *((_DWORD *)a2 + 7);
          *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v33 + 36) = *((_DWORD *)a2 + 7);
          ++v31;
          ++v32;
        }
        while ( v31 < (unsigned __int16)v14 );
        goto LABEL_46;
      }
    }
    v31 = 0;
    if ( !(_WORD)v14 )
      goto LABEL_46;
    goto LABEL_44;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180048ac4  mov     [rsp-8+arg_18], rbx
0x180048ac9  push    rbp
0x180048aca  push    rsi
0x180048acb  push    rdi
0x180048acc  push    r12
0x180048ace  push    r13
0x180048ad0  push    r14
0x180048ad2  push    r15
0x180048ad4  lea     rbp, [rsp-30h]
0x180048ad9  sub     rsp, 130h
0x180048ae0  mov     rax, cs:__security_cookie
0x180048ae7  xor     rax, rsp
0x180048aea  mov     [rbp+60h+var_40], rax
0x180048aee  mov     [rsp+160h+var_F0], r8
0x180048af3  mov     r15, rdx
0x180048af6  mov     rsi, rcx
0x180048af9  xor     edx, edx; Val
0x180048afb  lea     r8d, [rdx+40h]; Size
0x180048aff  lea     rcx, [rbp+60h+var_80]; void *
0x180048b03  call    memset_0
0x180048b08  cmp     qword ptr [rsi+10h], 0
0x180048b0d  jz      loc_1800492B5
0x180048b13  mov     r12d, [r15]
0x180048b16  mov     r13d, [r15+4]
0x180048b1a  mov     ecx, [r15+8]
0x180048b1e  mov     [rsp+160h+var_100], ecx
0x180048b22  lea     eax, [rcx-67h]
0x180048b25  mov     edx, 1
0x180048b2a  cmp     eax, edx
0x180048b2c  jbe     short loc_180048B33
0x180048b2e  cmp     ecx, 69h ; 'i'
0x180048b31  jnz     short loc_180048B43
0x180048b33  mov     eax, r12d
0x180048b36  and     eax, edx
0x180048b38  add     r12d, eax
0x180048b3b  mov     eax, r13d
0x180048b3e  and     eax, edx
0x180048b40  add     r13d, eax
0x180048b43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180048b4a  jb      short loc_180048B75
0x180048b4c  mov     edx, 25h ; '%'
0x180048b51  mov     [rsp+160h+var_138], rsi
0x180048b56  mov     dword ptr [rsp+160h+var_140], r13d
0x180048b5b  mov     r9d, r12d
0x180048b5e  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x180048b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b6c  mov     rcx, [rcx+10h]
0x180048b70  call    WPP_SF_ddq
0x180048b75  mov     rdi, [rsi+10h]
0x180048b79  mov     rax, [rdi]
0x180048b7c  mov     rbx, [rax]
0x180048b7f  lea     r14, [rsi+18h]
0x180048b83  mov     rcx, r14
0x180048b86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048b8b  mov     r8, r14
0x180048b8e  lea     rdx, _GUID_1f052807_0b46_4acc_8a89_364f793718a4
0x180048b95  mov     rcx, rdi
0x180048b98  mov     rax, rbx
0x180048b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ba0  mov     ebx, eax
0x180048ba2  xor     edi, edi
0x180048ba4  test    eax, eax
0x180048ba6  jnz     loc_1800491F9
0x180048bac  movups  xmm0, xmmword ptr [r15+0Ch]
0x180048bb1  movdqu  [rbp+60h+var_7C], xmm0
0x180048bb6  mov     [rbp+60h+var_6C], edi
0x180048bb9  mov     [rbp+60h+var_64], r12d
0x180048bbd  mov     [rbp+60h+var_60], r13d
0x180048bc1  mov     eax, [r15+8]
0x180048bc5  mov     [rbp+60h+var_5C], eax
0x180048bc8  cmp     [rsi+569h], dil
0x180048bcf  jnz     short loc_180048C2B
0x180048bd1  mov     rcx, [r14]
0x180048bd4  mov     rax, [rcx]
0x180048bd7  lea     r9d, [rbx+40h]
0x180048bdb  lea     r8, [rbp+60h+var_80]
0x180048bdf  xor     edx, edx
0x180048be1  mov     rax, [rax+18h]
0x180048be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bea  mov     ebx, eax
0x180048bec  test    eax, eax
0x180048bee  jnz     loc_1800491F9
0x180048bf4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180048bfb  jb      short loc_180048C1C
0x180048bfd  mov     [rsp+160h+var_138], rsi
0x180048c02  mov     eax, [rbp+60h+var_44]
0x180048c05  mov     dword ptr [rsp+160h+var_140], eax
0x180048c09  xor     r9d, r9d
0x180048c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c13  mov     rcx, [rcx+10h]
0x180048c17  call    WPP_SF_Ddq
0x180048c1c  cmp     [rbp+60h+var_44], edi
0x180048c1f  jnz     short loc_180048C2B
0x180048c21  mov     ebx, 0C00D6D76h
0x180048c26  jmp     loc_1800491F9
0x180048c2b  movzx   r14d, word ptr [r15+20h]
0x180048c30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180048c37  jb      short loc_180048C5D
0x180048c39  mov     r9d, r14d
0x180048c3c  mov     edx, 27h ; '''
0x180048c41  mov     [rsp+160h+var_140], rsi
0x180048c46  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x180048c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c54  mov     rcx, [rcx+10h]
0x180048c58  call    WPP_SF_dq
0x180048c5d  cmp     [rsi+70h], edi
0x180048c60  jz      short loc_180048C6A
0x180048c62  mov     rcx, rsi; this
0x180048c65  call    ?ReleaseOutputStreamArgs@CDX12DecodeCore@@IEAAXXZ; CDX12DecodeCore::ReleaseOutputStreamArgs(void)
0x180048c6a  mov     eax, [rbp+60h+var_48]
0x180048c6d  and     eax, 4
0x180048c70  mov     dword ptr [rsp+160h+var_108], eax
0x180048c74  cmp     [rbp+60h+var_44], 2
0x180048c78  setnl   [rsp+160h+var_110]
0x180048c7d  mov     rbx, r14
0x180048c80  mov     eax, 30h ; '0'
0x180048c85  mul     r14
0x180048c88  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180048c8f  cmovb   rax, rcx
0x180048c93  mov     rcx, rax; unsigned __int64
0x180048c96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048c9b  mov     [rsp+160h+var_F8], rdi
0x180048ca0  mov     rcx, [rsi+50h]; void *
0x180048ca4  mov     [rsi+50h], rax
0x180048ca8  test    rcx, rcx
0x180048cab  jz      short loc_180048CB2
0x180048cad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048cb2  lea     rcx, [rsp+160h+var_F8]
0x180048cb7  call    ??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)
0x180048cbc  cmp     [rsi+50h], rdi
0x180048cc0  jnz     short loc_180048CCC
0x180048cc2  mov     ebx, 8007000Eh
0x180048cc7  jmp     loc_1800491F9
0x180048ccc  mov     eax, 8
0x180048cd1  mul     rbx
0x180048cd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180048cdb  cmovb   rax, rcx
0x180048cdf  add     rax, 8
0x180048ce3  cmovb   rax, rcx
0x180048ce7  mov     rcx, rax; unsigned __int64
0x180048cea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048cef  test    rax, rax
0x180048cf2  jz      short loc_180048D1E
0x180048cf4  mov     [rax], rbx
0x180048cf7  lea     rdi, [rax+8]
0x180048cfb  lea     rax, ??1?$ComPtr@UID3D12CommandAllocator@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ID3D12CommandAllocator>::~ComPtr<ID3D12CommandAllocator>(void)
0x180048d02  mov     [rsp+160h+var_140], rax; void (*)(void *)
0x180048d07  lea     r9, ??0?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180048d0e  mov     r8, rbx; unsigned __int64
0x180048d11  mov     edx, 8; unsigned __int64
0x180048d16  mov     rcx, rdi; void *
0x180048d19  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180048d1e  mov     [rsp+160h+var_F8], 0
0x180048d27  mov     rdx, [rsi+68h]
0x180048d2b  mov     [rsi+68h], rdi
0x180048d2f  xor     edi, edi
0x180048d31  test    rdx, rdx
0x180048d34  jz      short loc_180048D3B
0x180048d36  call    ??$?RV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@Z; wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>(Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> *)
0x180048d3b  lea     rcx, [rsp+160h+var_F8]
0x180048d40  call    ?reset@?$unique_ptr@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@U?$default_delete@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0],wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>>::reset(std::nullptr_t)
0x180048d45  cmp     [rsi+68h], rdi
0x180048d49  jz      loc_180048CC2
0x180048d4f  lea     r8, [r14+r14*2]
0x180048d53  shl     r8, 4; Size
0x180048d57  xor     edx, edx; Val
0x180048d59  mov     rcx, [rsi+50h]; void *
0x180048d5d  call    memset_0
0x180048d62  mov     r10d, 1
0x180048d68  mov     [rbp+60h+var_B0], r10
0x180048d6c  mov     [rbp+60h+var_A8], edi
0x180048d6f  mov     [rbp+60h+var_A4], r10d
0x180048d73  mov     [rbp+60h+var_A0], r10d
0x180048d77  lea     r9, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x180048d7e  cmp     dword ptr [rsp+160h+var_108], edi
0x180048d82  jz      loc_180048F89
0x180048d88  mov     r8b, [rsp+160h+var_110]
0x180048d8d  test    r8b, r8b
0x180048d90  movzx   edx, r10w
0x180048d94  jnz     short loc_180048D9A
0x180048d96  movzx   edx, r14w
0x180048d9a  mov     ecx, r12d
0x180048d9d  mov     [rsp+160h+var_E8], 3
0x180048da5  mov     eax, [rsp+160h+var_E4]
0x180048da9  mov     [rsp+160h+var_E4], eax
0x180048dad  mov     [rbp+60h+var_E0], rdi
0x180048db1  mov     [rbp+60h+var_D8], rcx
0x180048db5  mov     [rbp+60h+var_D0], r13d
0x180048db9  mov     [rbp+60h+var_CC], dx
0x180048dbd  mov     [rbp+60h+var_CA], r10w
0x180048dc2  mov     eax, [rsp+160h+var_100]
0x180048dc6  mov     [rbp+60h+var_C8], eax
0x180048dc9  mov     [rbp+60h+var_C4], r10
0x180048dcd  mov     [rbp+60h+var_BC], edi
0x180048dd0  mov     [rbp+60h+var_B8], 48h ; 'H'
0x180048dd7  mov     eax, [rbp+60h+var_B4]
0x180048dda  mov     [rbp+60h+var_B4], eax
0x180048ddd  test    r8b, r8b
0x180048de0  jz      loc_180048E88
0x180048de6  mov     ebx, edi
0x180048de8  cmp     di, r14w
0x180048dec  jnb     loc_180048F48
0x180048df2  mov     rcx, [rsi+10h]
0x180048df6  movzx   eax, bx
0x180048df9  lea     rdi, [rax+rax*2]
0x180048dfd  shl     rdi, 4
0x180048e01  mov     rdx, [rcx]
0x180048e04  mov     r8, [rsi+50h]
0x180048e08  add     r8, 18h
0x180048e0c  add     r8, rdi
0x180048e0f  mov     rax, [rdx+0D8h]
0x180048e16  mov     [rsp+160h+var_128], r8
0x180048e1b  mov     [rsp+160h+var_130], r9
0x180048e20  mov     [rsp+160h+var_138], 0
0x180048e29  mov     dword ptr [rsp+160h+var_140], 0
0x180048e31  lea     r9, [rsp+160h+var_E8]
0x180048e36  mov     r8d, r10d
0x180048e39  lea     rdx, [rbp+60h+var_B0]
0x180048e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e42  test    eax, eax
0x180048e44  jnz     loc_180048F42
0x180048e4a  mov     rax, [rsi+50h]
0x180048e4e  mov     rcx, [rdi+rax+18h]
0x180048e53  mov     rax, [rcx]
0x180048e56  lea     rdx, aDxvaPostProcOp; "DXVA Post-proc OPB Buffer"
0x180048e5d  mov     rax, [rax+30h]
0x180048e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e66  mov     r10d, 1
0x180048e6c  add     bx, r10w
0x180048e70  cmp     bx, r14w
0x180048e74  lea     r9, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x180048e7b  jb      loc_180048DF2
0x180048e81  xor     edi, edi
0x180048e83  jmp     loc_180048F3D
0x180048e88  mov     rdi, [rsi+10h]
0x180048e8c  mov     rax, [rdi]
0x180048e8f  mov     rbx, [rax+0D8h]
0x180048e96  lea     rcx, [rsi+60h]
0x180048e9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e9f  lea     rax, [rsi+60h]
0x180048ea3  mov     [rsp+160h+var_128], rax
0x180048ea8  lea     rax, _GUID_696442be_a72e_4059_bc79_5b5c98040fad
0x180048eaf  mov     [rsp+160h+var_130], rax
0x180048eb4  mov     [rsp+160h+var_138], 0
0x180048ebd  mov     dword ptr [rsp+160h+var_140], 0
0x180048ec5  lea     r9, [rsp+160h+var_E8]
0x180048eca  mov     r8d, 1
0x180048ed0  lea     rdx, [rbp+60h+var_B0]
0x180048ed4  mov     rcx, rdi
0x180048ed7  mov     rax, rbx
0x180048eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048edf  mov     ebx, eax
0x180048ee1  xor     edi, edi
0x180048ee3  test    eax, eax
0x180048ee5  jnz     loc_1800491F9
0x180048eeb  mov     rcx, [rsi+60h]
0x180048eef  mov     rax, [rcx]
0x180048ef2  lea     rdx, aDxvaPostProcOp_0; "DXVA Post-proc OPB array"
0x180048ef9  mov     rax, [rax+30h]
0x180048efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f02  mov     r8d, edi
0x180048f05  lea     r10d, [rbx+1]
0x180048f09  cmp     di, r14w
0x180048f0d  jnb     short loc_180048F48
0x180048f0f  movzx   eax, r8w
0x180048f13  lea     rdx, [rax+rax*2]
0x180048f17  add     rdx, rdx
0x180048f1a  mov     rcx, [rsi+50h]
0x180048f1e  mov     rax, [rsi+60h]
0x180048f22  mov     [rcx+rdx*8+18h], rax
0x180048f27  movzx   ecx, r8w
0x180048f2b  mov     rax, [rsi+50h]
0x180048f2f  mov     [rax+rdx*8+20h], ecx
0x180048f33  add     r8w, r10w
0x180048f37  cmp     r8w, r14w
0x180048f3b  jb      short loc_180048F0F
0x180048f3d  mov     r8d, edi
0x180048f40  jmp     short loc_180048F51
0x180048f42  xor     edi, edi
0x180048f44  lea     r10d, [rdi+1]
0x180048f48  mov     r8d, edi
0x180048f4b  cmp     di, r14w
0x180048f4f  jnb     short loc_180048F89
0x180048f51  mov     r9, rdi
0x180048f54  lea     rdx, [r9+r9*2]
0x180048f58  add     rdx, rdx
0x180048f5b  mov     rax, [rsi+50h]
0x180048f5f  mov     [rax+rdx*8+10h], r10d
0x180048f64  mov     rcx, [rsi+50h]
0x180048f68  mov     eax, [r15+1Ch]
0x180048f6c  mov     [rcx+rdx*8+28h], eax
0x180048f70  mov     rcx, [rsi+50h]
0x180048f74  mov     eax, [r15+1Ch]
0x180048f78  mov     [rcx+rdx*8+24h], eax
0x180048f7c  add     r8w, r10w
0x180048f80  add     r9, r10
0x180048f83  cmp     r8w, r14w
0x180048f87  jb      short loc_180048F54
0x180048f89  mov     r8b, [rsp+160h+var_110]
0x180048f8e  test    r8b, r8b
  ... truncated ...
```
