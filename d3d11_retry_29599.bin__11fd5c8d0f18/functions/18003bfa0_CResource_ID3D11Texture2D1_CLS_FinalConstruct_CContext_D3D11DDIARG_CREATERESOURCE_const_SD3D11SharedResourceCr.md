# CResource<ID3D11Texture2D1>::CLS::FinalConstruct(CContext *,D3D11DDIARG_CREATERESOURCE const *,SD3D11SharedResourceCreationArgs *,SD3D11CrossLayerData *,D3D10DDI_HRTRESOURCE)

- ea: `0x18003bfa0`
- end: `0x18003c75d`
- name: `?FinalConstruct@CLS@?$CResource@UID3D11Texture2D1@@@@QEAAXPEAVCContext@@PEBUD3D11DDIARG_CREATERESOURCE@@PEAUSD3D11SharedResourceCreationArgs@@PEAUSD3D11CrossLayerData@@UD3D10DDI_HRTRESOURCE@@@Z`
- size: `1981`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18003bf50`

## callees

- `0x18001a130`
- `0x18001e2a0`
- `0x180022400`
- `0x18002bd20`
- `0x18002cb9c`
- `0x18003a3b0`
- `0x18003b420`
- `0x18003b720`
- `0x18003bfa0`
- `0x18003c764`
- `0x18003c7d8`
- `0x18003c8e0`
- `0x18003dcd4`
- `0x18005f4f4`
- `0x18006081c`
- `0x1800608b4`
- `0x1800608c4`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c058`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CResource<ID3D11Texture2D1>::CLS::FinalConstruct(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6)
{
  __int64 v7; // r13
  __int64 v10; // rdi
  __int64 v11; // r15
  __int64 v12; // rdi
  int v13; // r15d
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // r14d
  struct CDevice *v18; // rbx
  __int64 v19; // rcx
  bool v20; // al
  __int64 v21; // rcx
  char v22; // al
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // r9
  int v30; // eax
  __int64 v31; // rdi
  CDevice *v32; // rcx
  __int64 v33; // rax
  _BYTE *v34; // rdx
  _BYTE *v35; // rcx
  char *v36; // rdx
  char *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  bool v42; // [rsp+40h] [rbp-89h]
  char v43; // [rsp+41h] [rbp-88h]
  int v44; // [rsp+44h] [rbp-85h] BYREF
  __int64 v45; // [rsp+48h] [rbp-81h] BYREF
  __int64 v46; // [rsp+50h] [rbp-79h]
  _QWORD v47[5]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v48; // [rsp+80h] [rbp-49h]
  __int64 v49; // [rsp+90h] [rbp-39h]
  int v50; // [rsp+98h] [rbp-31h]
  __int64 v51; // [rsp+9Ch] [rbp-2Dh]
  _BYTE v52[28]; // [rsp+A8h] [rbp-21h] BYREF
  char v53; // [rsp+C4h] [rbp-5h] BYREF

  v7 = a3;
  v10 = a6;
  v11 = *(_QWORD *)a1;
  if ( a2 )
  {
    if ( (*(_DWORD *)(v11 + 284) & 0x100) == 0 && (*(_WORD *)(v11 + 272) & 1) == 0 )
    {
      if ( *(_BYTE *)(v11 + 250) != 2 )
      {
LABEL_4:
        if ( (*(_BYTE *)(v11 + 272) & 8) != 0 )
        {
          a1[11] |= 4u;
          CResource<ID3D11Texture1D>::CLS::GuardReadHelper(a1, v11 + 392);
        }
        v12 = v11 + 448;
        v49 = a2;
        v13 = *(_DWORD *)(a2 + 3688);
        v50 = v13;
        v14 = *(_QWORD *)(a2 + 3692);
        v51 = v14;
        *(_DWORD *)(a2 + 3688) = GetCurrentThreadId();
        *(_BYTE *)(a2 + 3692) = 2;
        *(_WORD *)(a2 + 3693) = *(_WORD *)((char *)&v46 + 1);
        *(_BYTE *)(a2 + 3695) = BYTE3(v46);
        *(_DWORD *)(a2 + 3696) = 0;
        (*(void (__fastcall **)(__int64, _QWORD, _BYTE *, __int64))(a2 + 1944))(a2 + 40768, 0, a1 + 56, v12);
        if ( *(int *)(a2 + 3696) >= 0 )
          a1[11] |= 1u;
        *(_DWORD *)(a2 + 3688) = v13;
        *(_QWORD *)(a2 + 3692) = v14;
        return;
      }
    }
    else if ( *(_BYTE *)(v11 + 250) != 2 )
    {
LABEL_78:
      ++*(_QWORD *)(a2 + 39488);
      a1[11] |= 4u;
      goto LABEL_4;
    }
    a1[10] = 0;
    goto LABEL_78;
  }
  v15 = *(_QWORD *)(v11 + 160);
  v16 = *(_QWORD *)(v15 + 1080);
  v45 = v16;
  if ( !a6 )
    v10 = *(_QWORD *)(v11 + 168);
  if ( *(int *)(*(_QWORD *)(v15 + 1232) + 1248LL) >= 0 )
  {
    if ( a5 && (v42 = 0, *a5) )
    {
      v17 = 3;
    }
    else
    {
      v17 = 1;
      v42 = 0;
    }
LABEL_16:
    v18 = *(struct CDevice **)(*(_QWORD *)a1 + 160LL);
    if ( v18 && *((_BYTE *)v18 + 1352) )
    {
      v46 = *(_QWORD *)(*(_QWORD *)a1 + 160LL);
      CLockOwnerChild<CDevice,0>::UCAddUse((char *)v18 + 248);
      CDDISync::CFreeThreadedLock::Enter(v18);
      v16 = v45;
    }
    else
    {
      v18 = 0;
      v46 = 0;
    }
    if ( a4 && *(_QWORD *)(a4 + 8) )
    {
      LOBYTE(a3) = 2;
      DDIImmCtxMT::DDIImmCtxMT(v47, v16, a3);
      if ( *(_DWORD *)(a4 + 44) )
      {
        v43 = 1;
        v39 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1232LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 256LL))(v39);
      }
      else
      {
        v43 = 0;
      }
      (*(void (__fastcall **)(__int64, _QWORD, _BYTE *, __int64))(v47[0] + 1952LL))(
        v45 + 40768,
        *(_QWORD *)(a4 + 8),
        a1 + 56,
        v10);
      v44 = *(_DWORD *)(v48 + 4);
      if ( v44 < 0 )
      {
        if ( v43 )
        {
          v41 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1232LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 264LL))(v41);
        }
      }
      else
      {
        v38 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1232LL);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 248LL))(v38, v10);
        v42 = 1;
        CResource<ID3D11Texture2D1>::CLS::QueryMipTiling(a1, v17);
      }
    }
    else
    {
      v19 = *(_QWORD *)(*(_QWORD *)a1 + 160LL);
      v20 = *(int *)(v19 + 1284) <= 37632
         && (int)CDevice::GetDriverDDIVersion(v19 + 48) >= 3
         && (*(_DWORD *)(v7 + 24) & 0xFFFFFBFF) == 0x800
         && !*(_DWORD *)(v7 + 32);
      if ( *(_QWORD *)(v7 + 56) )
      {
        LOBYTE(a3) = 8;
      }
      else
      {
        a3 = 2;
        if ( v20 )
          a3 = 10;
      }
      DDIImmCtxMT::DDIImmCtxMT(v47, v45, a3);
      v21 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1232LL);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 240LL))(v21, a4);
      v22 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1112LL);
      if ( (v22 & 0xFC) != 0 || v22 == 1 )
      {
        v23 = v47[0];
        if ( v17 == 1 )
          v24 = v47[0] + 1480LL;
        else
          v24 = *(_QWORD *)(v47[0] + 39672LL);
      }
      else
      {
        v23 = v47[0];
        if ( v17 == 1 )
          v24 = v47[0] + 1480LL;
        else
          v24 = *(_QWORD *)(v47[0] + 39672LL);
      }
      v42 = *(_QWORD *)(v24 + 464) != (_QWORD)&CContext::DDI_CreateResource11_DR;
      if ( v17 == 1 )
        v25 = v23 + 1480;
      else
        v25 = *(_QWORD *)(v23 + 39672);
      (*(void (__fastcall **)(__int64, __int64, _BYTE *, __int64))(v25 + 464))(v45 + 40768, v7, a1 + 56, v10);
      v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 160LL) + 1232LL);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 240LL))(v26, 0);
      v44 = *(_DWORD *)(v48 + 4);
      if ( v44 >= 0 )
        CResource<ID3D11Texture2D1>::CLS::QueryMipTiling(a1, v17);
    }
    DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v47);
    if ( v18 )
    {
      CDDISync::CFreeThreadedLock::Leave(v18);
      CLockOwnerChild<CDevice,0>::UCReleaseUse((char *)v18 + 248);
    }
    v27 = v44;
    goto LABEL_35;
  }
  v42 = 0;
  v17 = 3;
  v27 = -2005270523;
  if ( a5 && *a5 && (!a4 || !*(_QWORD *)(a4 + 8)) )
    goto LABEL_16;
LABEL_35:
  ThrowFailure(v27);
  a1[11] ^= (v42 ^ a1[11]) & 1;
  if ( *(_DWORD *)(v7 + 28)
    && !*(_DWORD *)(v7 + 72)
    && !*(_BYTE *)(v11 + 250)
    && (unsigned int)(*(_DWORD *)(v7 + 16) - 2) <= 3 )
  {
    std::vector<D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT>::_Resize<std::_Value_init_tag>(
      v11 + 304,
      *(unsigned int *)(v11 + 256));
    v31 = v45;
    DDIImmCtxMT::DDIImmCtxMT(v47, v45, 0);
    v44 = 0;
    v32 = *(CDevice **)(*(_QWORD *)a1 + 160LL);
    if ( *((_BYTE *)v32 + 1136) )
    {
      if ( !*(_DWORD *)(v11 + 288) )
        *(_DWORD *)(v11 + 292) = 256;
    }
    else if ( CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(v32) )
    {
      if ( v17 == 1 )
        v40 = v47[0] + 1480LL;
      else
        v40 = *(_QWORD *)(v47[0] + 39672LL);
      (*(void (__fastcall **)(__int64, _BYTE *, _QWORD, int *, __int64, _QWORD))(v40 + 1392))(
        v45 + 40768,
        a1 + 56,
        *(unsigned int *)(v11 + 256),
        &v44,
        v11 + 292,
        *(_QWORD *)(v11 + 304));
    }
    else
    {
      memset(v52, 0, sizeof(v52));
      LODWORD(v45) = -1;
      if ( (unsigned __int8)std::_Is_all_bits_zero<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN>(&v45) )
        std::_Fill_zero_memset<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN *>(v52, 7);
      else
        memset(v52, 255, sizeof(v52));
      if ( v17 == 1 )
        v33 = v47[0] + 1480LL;
      else
        v33 = *(_QWORD *)(v47[0] + 39672LL);
      (*(void (__fastcall **)(__int64, _BYTE *, _QWORD, int *, __int64, _BYTE *, _QWORD))(v33 + 1320))(
        v31 + 40768,
        a1 + 56,
        *(unsigned int *)(v11 + 256),
        &v44,
        v11 + 292,
        v52,
        *(_QWORD *)(v11 + 304));
      v34 = (_BYTE *)(v11 + 296);
      v35 = v52;
      do
      {
        *v34++ = *v35;
        v35 += 4;
      }
      while ( v35 != &v52[20] );
      v36 = (char *)(v11 + 301);
      v37 = &v52[20];
      do
      {
        *v36++ = *v37;
        v37 += 4;
      }
      while ( v37 != &v53 );
    }
    DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v47);
  }
  CDeviceChild<ID3D11Texture2D1>::AllocateCLSOffset(v11, v28, a1 + 56);
  if ( a4 && *(_DWORD *)(a4 + 44) )
    HazardTracking::SetAcquired(a1 + 16, 0, *(_QWORD *)a1);
  v29 = *(_QWORD *)(v7 + 56);
  if ( v29 && (*(_DWORD *)(v29 + 40) & 1) == 0 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v11 + 40LL))(
            v11,
            &GUID_DXGI_PRIMARY_DESC,
            44);
    ThrowFailure(v30);
  }
}

```

## disassembly

```asm
0x18003bfa0  push    rbp
0x18003bfa2  push    rbx
0x18003bfa3  push    rsi
0x18003bfa4  push    rdi
0x18003bfa5  push    r12
0x18003bfa7  push    r13
0x18003bfa9  push    r14
0x18003bfab  push    r15
0x18003bfad  lea     rbp, [rsp-0Fh]
0x18003bfb2  sub     rsp, 0D8h
0x18003bfb9  mov     rax, cs:__security_cookie
0x18003bfc0  xor     rax, rsp
0x18003bfc3  mov     [rbp+47h+var_48], rax
0x18003bfc7  mov     r12, r9
0x18003bfca  mov     r13, r8
0x18003bfcd  mov     r14, rdx
0x18003bfd0  mov     rsi, rcx
0x18003bfd3  mov     rdi, [rbp+47h+arg_28]
0x18003bfd7  mov     r15, [rcx]
0x18003bfda  test    rdx, rdx
0x18003bfdd  jz      loc_18003C0F4
0x18003bfe3  test    dword ptr [r15+11Ch], 100h
0x18003bfee  setz    cl
0x18003bff1  xor     r12d, r12d
0x18003bff4  movzx   eax, word ptr [r15+110h]
0x18003bffc  bt      ax, r12w
0x18003c001  setnb   al
0x18003c004  test    al, cl
0x18003c006  jz      loc_18003C60F
0x18003c00c  cmp     byte ptr [r15+0FAh], 2
0x18003c014  jz      loc_18003C619
0x18003c01a  test    byte ptr [r15+110h], 8
0x18003c022  jz      short loc_18003C037
0x18003c024  or      byte ptr [rsi+0Bh], 4
0x18003c028  lea     rdx, [r15+188h]
0x18003c02f  mov     rcx, rsi
0x18003c032  call    ?GuardReadHelper@CLS@?$CResource@UID3D11Texture1D@@@@QEAAXPEDU12@@Z; CResource<ID3D11Texture1D>::CLS::GuardReadHelper(CResource<ID3D11Texture1D>::CLS const volatile *)
0x18003c037  lea     rdi, [r15+1C0h]
0x18003c03e  mov     [rbp+47h+var_80], r14
0x18003c042  mov     r15d, [r14+0E68h]
0x18003c049  mov     [rbp+47h+var_78], r15d
0x18003c04d  mov     rbx, [r14+0E6Ch]
0x18003c054  mov     [rbp+47h+var_74], rbx
0x18003c058  call    cs:__imp_GetCurrentThreadId
0x18003c05e  mov     [r14+0E68h], eax
0x18003c065  mov     byte ptr [r14+0E6Ch], 2
0x18003c06d  movzx   eax, [rbp+47h+var_BF]
0x18003c071  mov     [r14+0E6Dh], ax
0x18003c079  movzx   eax, [rbp+47h+var_BD]
0x18003c07d  mov     [r14+0E6Fh], al
0x18003c084  mov     [r14+0E70h], r12d
0x18003c08b  mov     rax, [rsi]
0x18003c08e  mov     rcx, [rax+0A0h]
0x18003c095  movzx   eax, byte ptr [rcx+458h]
0x18003c09c  mov     r9, rdi
0x18003c09f  lea     r8, [rsi+38h]
0x18003c0a3  xor     edx, edx
0x18003c0a5  lea     rcx, [r14+9F40h]
0x18003c0ac  mov     rax, [r14+798h]
0x18003c0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0b8  cmp     dword ptr [r14+0E70h], 0
0x18003c0c0  jl      short loc_18003C0C6
0x18003c0c2  or      byte ptr [rsi+0Bh], 1
0x18003c0c6  mov     [r14+0E68h], r15d
0x18003c0cd  mov     [r14+0E6Ch], rbx
0x18003c0d4  mov     rcx, [rbp+47h+var_48]
0x18003c0d8  xor     rcx, rsp; StackCookie
0x18003c0db  call    __security_check_cookie
0x18003c0e0  add     rsp, 0D8h
0x18003c0e7  pop     r15
0x18003c0e9  pop     r14
0x18003c0eb  pop     r13
0x18003c0ed  pop     r12
0x18003c0ef  pop     rdi
0x18003c0f0  pop     rsi
0x18003c0f1  pop     rbx
0x18003c0f2  pop     rbp
0x18003c0f3  retn
0x18003c0f4  mov     rax, [r15+0A0h]
0x18003c0fb  mov     rdx, [rax+438h]
0x18003c102  mov     [rsp+110h+var_C8], rdx
0x18003c107  test    rdi, rdi
0x18003c10a  jz      loc_18003C384
0x18003c110  mov     rax, [rax+4D0h]
0x18003c117  mov     ecx, [rax+4E0h]
0x18003c11d  mov     rax, [rbp+47h+arg_20]
0x18003c121  test    ecx, ecx
0x18003c123  js      loc_18003C327
0x18003c129  test    rax, rax
0x18003c12c  jz      short loc_18003C13C
0x18003c12e  mov     [rsp+110h+var_D0], 0
0x18003c133  cmp     byte ptr [rax], 0
0x18003c136  jnz     loc_18003C62D
0x18003c13c  mov     r14d, 1
0x18003c142  mov     [rsp+110h+var_D0], 0
0x18003c147  mov     rbx, [rsi]
0x18003c14a  mov     rbx, [rbx+0A0h]
0x18003c151  test    rbx, rbx
0x18003c154  jz      short loc_18003C163
0x18003c156  cmp     byte ptr [rbx+548h], 0
0x18003c15d  jnz     loc_18003C362
0x18003c163  xor     ebx, ebx
0x18003c165  mov     [rbp-79h], rbx
0x18003c169  test    r12, r12
0x18003c16c  jnz     loc_18003C528
0x18003c172  mov     rax, [rsi]
0x18003c175  mov     rcx, [rax+0A0h]
0x18003c17c  cmp     dword ptr [rcx+504h], 9300h
0x18003c186  jle     loc_18003C6DD
0x18003c18c  xor     al, al
0x18003c18e  cmp     qword ptr [r13+38h], 0
0x18003c193  jnz     loc_18003C3B9
0x18003c199  mov     ecx, 0Ah
0x18003c19e  mov     r8d, 2
0x18003c1a4  test    al, al
0x18003c1a6  cmovnz  r8d, ecx
0x18003c1aa  mov     rdx, [rsp+110h+var_C8]
0x18003c1af  lea     rcx, [rbp+47h+var_B8]
0x18003c1b3  call    ??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z; DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)
0x18003c1b8  nop
0x18003c1b9  mov     rax, [rsi]
0x18003c1bc  mov     rcx, [rax+0A0h]
0x18003c1c3  mov     rcx, [rcx+4D0h]
0x18003c1ca  mov     rax, [rcx]
0x18003c1cd  mov     rdx, r12
0x18003c1d0  mov     rax, [rax+0F0h]
0x18003c1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1dc  mov     rax, [rsi]
0x18003c1df  mov     rcx, [rax+0A0h]
0x18003c1e6  movzx   eax, byte ptr [rcx+458h]
0x18003c1ed  test    al, 0FCh
0x18003c1ef  jz      loc_18003C390
0x18003c1f5  mov     rax, [rbp+47h+var_B8]
0x18003c1f9  cmp     r14d, 1
0x18003c1fd  jnz     loc_18003C3CD
0x18003c203  lea     rcx, [rax+5C8h]
0x18003c20a  lea     rdx, ?DDI_CreateResource11_DR@CContext@@SAXUD3D10DDI_HDEVICE@@PEBUD3D11DDIARG_CREATERESOURCE@@UD3D10DDI_HRESOURCE@@UD3D10DDI_HRTRESOURCE@@@Z; CContext::DDI_CreateResource11_DR(D3D10DDI_HDEVICE,D3D11DDIARG_CREATERESOURCE const *,D3D10DDI_HRESOURCE,D3D10DDI_HRTRESOURCE)
0x18003c211  cmp     [rcx+1D0h], rdx
0x18003c218  setnz   [rsp+110h+var_D0]
0x18003c21d  cmp     r14d, 1
0x18003c221  jnz     loc_18003C3C1
0x18003c227  add     rax, 5C8h
0x18003c22d  mov     rcx, [rsp+110h+var_C8]
0x18003c232  mov     r9, rdi
0x18003c235  lea     r8, [rsi+38h]
0x18003c239  mov     rdx, r13
0x18003c23c  add     rcx, 9F40h
0x18003c243  mov     rax, [rax+1D0h]
0x18003c24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c24f  mov     rax, [rsi]
0x18003c252  mov     rcx, [rax+0A0h]
0x18003c259  mov     rcx, [rcx+4D0h]
0x18003c260  mov     rax, [rcx]
0x18003c263  xor     edx, edx
0x18003c265  mov     rax, [rax+0F0h]
0x18003c26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c271  mov     rax, [rbp+47h+var_90]
0x18003c275  mov     eax, [rax+4]
0x18003c278  mov     [rsp+110h+var_CC], eax
0x18003c27c  test    eax, eax
0x18003c27e  js      short loc_18003C28C
0x18003c280  mov     edx, r14d
0x18003c283  mov     rcx, rsi
0x18003c286  call    ?QueryMipTiling@CLS@?$CResource@UID3D11Texture2D1@@@@AEAAXW4EDDI@@@Z; CResource<ID3D11Texture2D1>::CLS::QueryMipTiling(EDDI)
0x18003c28b  nop
0x18003c28c  lea     rcx, [rbp+47h+var_B8]; this
0x18003c290  call    ??1DDIImmCtxMT@@QEAA@XZ; DDIImmCtxMT::~DDIImmCtxMT(void)
0x18003c295  nop
0x18003c296  test    rbx, rbx
0x18003c299  jz      short loc_18003C2AF
0x18003c29b  mov     rcx, rbx; struct CDevice *
0x18003c29e  call    ?Leave@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Leave(CDevice *)
0x18003c2a3  lea     rcx, [rbx+0F8h]
0x18003c2aa  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18003c2af  mov     ecx, [rsp+110h+var_CC]; int
0x18003c2b3  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18003c2b8  movzx   ecx, byte ptr [rsi+0Bh]
0x18003c2bc  xor     cl, [rsp+110h+var_D0]
0x18003c2c0  and     cl, 1
0x18003c2c3  xor     [rsi+0Bh], cl
0x18003c2c6  cmp     dword ptr [r13+1Ch], 0
0x18003c2cb  jnz     loc_18003C3D9
0x18003c2d1  lea     r8, [rsi+38h]
0x18003c2d5  mov     rcx, r15
0x18003c2d8  call    ?AllocateCLSOffset@?$CDeviceChild@UID3D11Texture2D1@@@@QEAAXW4D3D11DDI_HANDLETYPE@@PEAX_K@Z; CDeviceChild<ID3D11Texture2D1>::AllocateCLSOffset(D3D11DDI_HANDLETYPE,void *,unsigned __int64)
0x18003c2dd  test    r12, r12
0x18003c2e0  jnz     loc_18003C5C6
0x18003c2e6  mov     r9, [r13+38h]
0x18003c2ea  test    r9, r9
0x18003c2ed  jz      loc_18003C0D4
0x18003c2f3  mov     eax, [r9+28h]
0x18003c2f7  test    al, 1
0x18003c2f9  jnz     loc_18003C0D4
0x18003c2ff  mov     rax, [r15]
0x18003c302  mov     r8d, 2Ch ; ','
0x18003c308  lea     rdx, GUID_DXGI_PRIMARY_DESC
0x18003c30f  mov     rcx, r15
0x18003c312  mov     rax, [rax+28h]
0x18003c316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c31b  mov     ecx, eax; int
0x18003c31d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18003c322  jmp     loc_18003C0D4
0x18003c327  mov     [rsp+110h+var_D0], 0
0x18003c32c  mov     r14d, 3
0x18003c332  mov     ecx, 887A0005h
0x18003c337  test    rax, rax
0x18003c33a  jz      loc_18003C2B3
0x18003c340  cmp     byte ptr [rax], 0
0x18003c343  jz      loc_18003C2B3
0x18003c349  test    r12, r12
0x18003c34c  jz      loc_18003C147
0x18003c352  cmp     qword ptr [r9+8], 0
0x18003c357  jnz     loc_18003C2B3
0x18003c35d  jmp     loc_18003C147
0x18003c362  mov     [rbp-79h], rbx
0x18003c366  lea     rcx, [rbx+0F8h]
0x18003c36d  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18003c372  mov     rcx, rbx; struct CDevice *
0x18003c375  call    ?Enter@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Enter(CDevice *)
0x18003c37a  mov     rdx, [rsp+110h+var_C8]
0x18003c37f  jmp     loc_18003C169
0x18003c384  mov     rdi, [r15+0A8h]
0x18003c38b  jmp     loc_18003C110
0x18003c390  cmp     al, 1
0x18003c392  jz      loc_18003C1F5
0x18003c398  mov     rax, [rbp+47h+var_B8]
0x18003c39c  cmp     r14d, 1
0x18003c3a0  jnz     loc_18003C72C
0x18003c3a6  lea     rcx, [rax+5C8h]
0x18003c3ad  lea     rdx, ?DDI_CreateResource11_DR@CContext@@SAXUD3D10DDI_HDEVICE@@PEBUD3D11DDIARG_CREATERESOURCE@@UD3D10DDI_HRESOURCE@@UD3D10DDI_HRTRESOURCE@@@Z; CContext::DDI_CreateResource11_DR(D3D10DDI_HDEVICE,D3D11DDIARG_CREATERESOURCE const *,D3D10DDI_HRESOURCE,D3D10DDI_HRTRESOURCE)
0x18003c3b4  jmp     loc_18003C211
0x18003c3b9  mov     r8b, 8
0x18003c3bc  jmp     loc_18003C1AA
0x18003c3c1  mov     rax, [rax+9AF8h]
0x18003c3c8  jmp     loc_18003C22D
0x18003c3cd  mov     rcx, [rax+9AF8h]
0x18003c3d4  jmp     loc_18003C20A
0x18003c3d9  cmp     dword ptr [r13+48h], 0
0x18003c3de  jnz     loc_18003C2D1
0x18003c3e4  cmp     byte ptr [r15+0FAh], 0
0x18003c3ec  jnz     loc_18003C2D1
0x18003c3f2  mov     eax, [r13+10h]
0x18003c3f6  sub     eax, 2
0x18003c3f9  cmp     eax, 3
0x18003c3fc  ja      loc_18003C2D1
0x18003c402  mov     edx, [r15+100h]
0x18003c409  lea     rcx, [r15+130h]
0x18003c410  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@UD3DWDDM2_0DDI_SUBRESOURCE_LAYOUT@@V?$allocator@UD3DWDDM2_0DDI_SUBRESOURCE_LAYOUT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003c415  xor     r8d, r8d
0x18003c418  mov     rdi, [rsp+110h+var_C8]
0x18003c41d  mov     rdx, rdi
0x18003c420  lea     rcx, [rbp+47h+var_B8]
0x18003c424  call    ??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z; DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)
0x18003c429  nop
0x18003c42a  mov     [rsp+110h+var_CC], 0
0x18003c432  mov     rax, [rsi]
0x18003c435  mov     rcx, [rax+0A0h]; this
0x18003c43c  cmp     byte ptr [rcx+470h], 0
0x18003c443  jnz     loc_18003C638
0x18003c449  call    ?IsDDIWDDM2_0BuildVersion5OrEarlier@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(void)
0x18003c44e  test    al, al
0x18003c450  jnz     loc_18003C64F
0x18003c456  xorps   xmm0, xmm0
0x18003c459  movups  [rbp+47h+var_68], xmm0
0x18003c45d  movups  [rbp+47h+var_68+0Ch], xmm0
0x18003c461  mov     dword ptr [rsp+110h+var_C8], 0FFFFFFFFh
0x18003c469  lea     rcx, [rsp+110h+var_C8]
0x18003c46e  call    ??$_Is_all_bits_zero@W4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@std@@YA_NAEBW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@Z; std::_Is_all_bits_zero<D3DWDDM2_0DDI_SWIZZLE_PATTERN>(D3DWDDM2_0DDI_SWIZZLE_PATTERN const &)
0x18003c473  test    al, al
0x18003c475  jz      loc_18003C738
0x18003c47b  mov     edx, 7
0x18003c480  lea     rcx, [rbp+47h+var_68]
0x18003c484  call    ??$_Fill_zero_memset@PEAW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@std@@YAXPEAW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@_K@Z; std::_Fill_zero_memset<D3DWDDM2_0DDI_SWIZZLE_PATTERN *>(D3DWDDM2_0DDI_SWIZZLE_PATTERN *,unsigned __int64)
0x18003c489  mov     rax, [rbp+47h+var_B8]
0x18003c48d  cmp     r14d, 1
0x18003c491  jnz     loc_18003C714
0x18003c497  add     rax, 5C8h
0x18003c49d  lea     rdx, [rsi+38h]
0x18003c4a1  lea     rcx, [rdi+9F40h]
0x18003c4a8  lea     r9, [r15+124h]
0x18003c4af  mov     r8, [r15+130h]
0x18003c4b6  mov     [rsp+110h+var_E0], r8
0x18003c4bb  lea     r8, [rbp+47h+var_68]
0x18003c4bf  mov     [rsp+110h+var_E8], r8
0x18003c4c4  mov     [rsp+110h+var_F0], r9
0x18003c4c9  lea     r9, [rsp+110h+var_CC]
0x18003c4ce  mov     r8d, [r15+100h]
0x18003c4d5  mov     rax, [rax+528h]
0x18003c4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4e1  lea     rdx, [r15+128h]
0x18003c4e8  lea     rcx, [rbp+47h+var_68]
0x18003c4ec  movzx   eax, byte ptr [rcx]
0x18003c4ef  mov     [rdx], al
0x18003c4f1  lea     rdx, [rdx+1]
0x18003c4f5  add     rcx, 4
0x18003c4f9  lea     rax, [rbp+47h+var_54]
0x18003c4fd  cmp     rcx, rax
0x18003c500  jnz     short loc_18003C4EC
0x18003c502  lea     rdx, [r15+12Dh]
0x18003c509  lea     rcx, [rbp+47h+var_54]
  ... truncated ...
```
