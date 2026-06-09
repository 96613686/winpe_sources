# CResource<ID3D11Buffer>::CLS::FinalConstruct(CContext *,D3D11DDIARG_CREATERESOURCE const *,SD3D11SharedResourceCreationArgs *,SD3D11CrossLayerData *,D3D10DDI_HRTRESOURCE)

- ea: `0x18003ce70`
- end: `0x18003d704`
- name: `?FinalConstruct@CLS@?$CResource@UID3D11Buffer@@@@QEAAXPEAVCContext@@PEBUD3D11DDIARG_CREATERESOURCE@@PEAUSD3D11SharedResourceCreationArgs@@PEAUSD3D11CrossLayerData@@UD3D10DDI_HRTRESOURCE@@@Z`
- size: `2196`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x18003ce20`

## callees

- `0x18001a130`
- `0x18001e2a0`
- `0x180022400`
- `0x18002bd20`
- `0x18002cb9c`
- `0x18003a3b0`
- `0x18003b420`
- `0x18003b720`
- `0x18003ce70`
- `0x18003d70c`
- `0x18003d814`
- `0x18003dcd4`
- `0x18006055c`
- `0x18006081c`
- `0x1800608b4`
- `0x1800608c4`
- `0x180092724`
- `0x1800a48cc`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cf70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cf70`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CResource<ID3D11Buffer>::CLS::FinalConstruct(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6)
{
  __int64 v7; // r13
  __int64 v10; // rbx
  __int64 v11; // r15
  _OWORD *v12; // rcx
  __int64 v13; // rdi
  int v14; // r15d
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdi
  unsigned int v18; // r14d
  struct CDevice *v19; // rdi
  __int64 v20; // rcx
  bool v21; // al
  __int64 v22; // rcx
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  char v28; // bl
  __int64 v29; // rdx
  __int64 v30; // r9
  int v31; // eax
  _QWORD *v32; // rbx
  unsigned __int64 v33; // rdx
  __int64 v34; // r8
  unsigned __int64 v35; // rcx
  CDevice *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  _BYTE *v42; // rdx
  _BYTE *v43; // rcx
  char *v44; // rdx
  char *v45; // rcx
  signed __int32 v46[8]; // [rsp+0h] [rbp-C9h] BYREF
  bool v47; // [rsp+40h] [rbp-89h]
  char v48; // [rsp+41h] [rbp-88h]
  int v49; // [rsp+44h] [rbp-85h] BYREF
  __int64 v50; // [rsp+48h] [rbp-81h] BYREF
  __int64 v51; // [rsp+50h] [rbp-79h]
  _QWORD v52[5]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v53; // [rsp+80h] [rbp-49h]
  __int64 v54; // [rsp+90h] [rbp-39h]
  int v55; // [rsp+98h] [rbp-31h]
  __int64 v56; // [rsp+9Ch] [rbp-2Dh]
  _BYTE v57[28]; // [rsp+A8h] [rbp-21h] BYREF
  char v58; // [rsp+C4h] [rbp-5h] BYREF

  v7 = a3;
  v10 = a6;
  v11 = *a1;
  if ( a2 )
  {
    if ( (*(_DWORD *)(v11 + 284) & 0x100) == 0 && (*(_WORD *)(v11 + 272) & 1) == 0 )
    {
      if ( *(_BYTE *)(v11 + 250) != 2 )
      {
LABEL_4:
        if ( (*(_BYTE *)(v11 + 272) & 8) != 0 )
        {
          *((_BYTE *)a1 + 11) |= 4u;
          *((_DWORD *)a1 + 13) = *(_DWORD *)(v11 + 444);
          _InterlockedOr(v46, 0);
          v12 = (_OWORD *)((char *)a1 + 36);
          *((_DWORD *)a1 + 9) = *(_DWORD *)(v11 + 428);
          *((_DWORD *)a1 + 10) = *(_DWORD *)(v11 + 432);
          *((_DWORD *)a1 + 11) = *(_DWORD *)(v11 + 436);
          *((_DWORD *)a1 + 12) = *(_DWORD *)(v11 + 440);
          if ( *((_DWORD *)a1 + 9) >= *((_DWORD *)a1 + 11) || *((_DWORD *)a1 + 10) >= *((_DWORD *)a1 + 12) )
          {
            *v12 = c_DefaultD3D11JpegOptions;
            *((_BYTE *)a1 + 17) &= ~2u;
            *((_BYTE *)a1 + 16) |= 4u;
          }
          else if ( (unsigned __int8)operator!=() )
          {
            *((_BYTE *)a1 + 17) |= 2u;
            *((_BYTE *)a1 + 16) &= ~4u;
          }
        }
        v13 = v11 + 448;
        v54 = a2;
        v14 = *(_DWORD *)(a2 + 3688);
        v55 = v14;
        v15 = *(_QWORD *)(a2 + 3692);
        v56 = v15;
        *(_DWORD *)(a2 + 3688) = GetCurrentThreadId();
        *(_BYTE *)(a2 + 3692) = 2;
        *(_WORD *)(a2 + 3693) = *(_WORD *)((char *)&v51 + 1);
        *(_BYTE *)(a2 + 3695) = BYTE3(v51);
        *(_DWORD *)(a2 + 3696) = 0;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD *, __int64))(a2 + 1944))(a2 + 40768, 0, a1 + 7, v13);
        if ( *(int *)(a2 + 3696) >= 0 )
          *((_BYTE *)a1 + 11) |= 1u;
        *(_DWORD *)(a2 + 3688) = v14;
        *(_QWORD *)(a2 + 3692) = v15;
        return;
      }
    }
    else if ( *(_BYTE *)(v11 + 250) != 2 )
    {
LABEL_46:
      ++*(_QWORD *)(a2 + 39488);
      *((_BYTE *)a1 + 11) |= 4u;
      goto LABEL_4;
    }
    *((_BYTE *)a1 + 10) = 0;
    goto LABEL_46;
  }
  v16 = *(_QWORD *)(v11 + 160);
  v17 = *(_QWORD *)(v16 + 1080);
  v50 = v17;
  if ( !a6 )
    v10 = *(_QWORD *)(v11 + 168);
  if ( *(int *)(*(_QWORD *)(v16 + 1232) + 1248LL) >= 0 )
  {
    if ( a5 && (v47 = 0, *a5) )
    {
      v18 = 3;
    }
    else
    {
      v18 = 1;
      v47 = 0;
    }
LABEL_17:
    v19 = *(struct CDevice **)(*a1 + 160LL);
    if ( v19 && *((_BYTE *)v19 + 1352) )
    {
      v51 = *(_QWORD *)(*a1 + 160LL);
      CLockOwnerChild<CDevice,0>::UCAddUse((char *)v19 + 248);
      CDDISync::CFreeThreadedLock::Enter(v19);
    }
    else
    {
      v19 = 0;
      v51 = 0;
    }
    if ( a4 && *(_QWORD *)(a4 + 8) )
    {
      LOBYTE(a3) = 2;
      DDIImmCtxMT::DDIImmCtxMT(v52, v50, a3);
      if ( *(_DWORD *)(a4 + 44) )
      {
        v48 = 1;
        v38 = *(_QWORD *)(*(_QWORD *)(*a1 + 160LL) + 1232LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 256LL))(v38);
      }
      else
      {
        v48 = 0;
      }
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD *, __int64))(v52[0] + 1952LL))(
        v50 + 40768,
        *(_QWORD *)(a4 + 8),
        a1 + 7,
        v10);
      v49 = *(_DWORD *)(v53 + 4);
      if ( v49 < 0 )
      {
        if ( v48 )
        {
          v40 = *(_QWORD *)(*(_QWORD *)(*a1 + 160LL) + 1232LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 264LL))(v40);
        }
        v28 = v47;
      }
      else
      {
        v39 = *(_QWORD *)(*(_QWORD *)(*a1 + 160LL) + 1232LL);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 248LL))(v39, v10);
        v28 = 1;
        CResource<ID3D11Buffer>::CLS::QueryMipTiling(a1, v18);
      }
      DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v52);
    }
    else
    {
      v20 = *(_QWORD *)(*a1 + 160LL);
      v21 = *(int *)(v20 + 1284) <= 37632
         && (int)CDevice::GetDriverDDIVersion(v20 + 48) >= 3
         && (*(_DWORD *)(v7 + 24) & 0xFFFFFBFF) == 0x800
         && !*(_DWORD *)(v7 + 32);
      if ( *(_QWORD *)(v7 + 56) )
      {
        LOBYTE(a3) = 8;
      }
      else
      {
        a3 = 2;
        if ( v21 )
          a3 = 10;
      }
      DDIImmCtxMT::DDIImmCtxMT(v52, v50, a3);
      v22 = *(_QWORD *)(*(_QWORD *)(*a1 + 160LL) + 1232LL);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 240LL))(v22, a4);
      v23 = *(_BYTE *)(*(_QWORD *)(*a1 + 160LL) + 1112LL);
      if ( (v23 & 0xFC) != 0 || v23 == 1 )
      {
        v24 = v52[0];
        if ( v18 == 1 )
          v25 = v52[0] + 1480LL;
        else
          v25 = *(_QWORD *)(v52[0] + 39672LL);
      }
      else
      {
        v24 = v52[0];
        if ( v18 == 1 )
          v25 = v52[0] + 1480LL;
        else
          v25 = *(_QWORD *)(v52[0] + 39672LL);
      }
      v47 = *(_QWORD *)(v25 + 464) != (_QWORD)&CContext::DDI_CreateResource11_DR;
      if ( v18 == 1 )
        v26 = v24 + 1480;
      else
        v26 = *(_QWORD *)(v24 + 39672);
      (*(void (__fastcall **)(__int64, __int64, _QWORD *, __int64))(v26 + 464))(v50 + 40768, v7, a1 + 7, v10);
      v27 = *(_QWORD *)(*(_QWORD *)(*a1 + 160LL) + 1232LL);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 240LL))(v27, 0);
      v49 = *(_DWORD *)(v53 + 4);
      if ( v49 >= 0 )
        CResource<ID3D11Buffer>::CLS::QueryMipTiling(a1, v18);
      DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v52);
      v28 = v47;
    }
    if ( v19 )
    {
      CDDISync::CFreeThreadedLock::Leave(v19);
      CLockOwnerChild<CDevice,0>::UCReleaseUse((char *)v19 + 248);
    }
    v17 = v50;
    goto LABEL_37;
  }
  v47 = 0;
  v18 = 3;
  v49 = -2005270523;
  if ( a5 && *a5 && (!a4 || !*(_QWORD *)(a4 + 8)) )
    goto LABEL_17;
  v28 = v47;
LABEL_37:
  ThrowFailure(v49);
  *((_BYTE *)a1 + 11) ^= (v28 ^ *((_BYTE *)a1 + 11)) & 1;
  if ( *(_DWORD *)(v7 + 28)
    && !*(_DWORD *)(v7 + 72)
    && !*(_BYTE *)(v11 + 250)
    && (unsigned int)(*(_DWORD *)(v7 + 16) - 2) <= 3 )
  {
    v32 = (_QWORD *)(v11 + 304);
    v33 = *(unsigned int *)(v11 + 256);
    v34 = *(_QWORD *)(v11 + 304);
    v35 = (*(_QWORD *)(v11 + 312) - v34) >> 5;
    if ( v33 < v35 )
    {
      *(_QWORD *)(v11 + 312) = v34 + 32 * v33;
    }
    else if ( v33 > v35 )
    {
      if ( v33 <= (*(_QWORD *)(v11 + 320) - v34) >> 5 )
        *(_QWORD *)(v11 + 312) = std::_Uninitialized_value_construct_n<std::allocator<D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT>>(
                                   *(_QWORD *)(v11 + 312),
                                   v33 - v35,
                                   v11 + 304);
      else
        std::vector<D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT>::_Resize_reallocate<std::_Value_init_tag>(v11 + 304);
    }
    DDIImmCtxMT::DDIImmCtxMT(v52, v17, 0);
    v49 = 0;
    v36 = *(CDevice **)(*a1 + 160LL);
    if ( *((_BYTE *)v36 + 1136) )
    {
      if ( !*(_DWORD *)(v11 + 288) )
        *(_DWORD *)(v11 + 292) = 256;
    }
    else if ( CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(v36) )
    {
      if ( v18 == 1 )
        v37 = v52[0] + 1480LL;
      else
        v37 = *(_QWORD *)(v52[0] + 39672LL);
      (*(void (__fastcall **)(__int64, _QWORD *, _QWORD, int *, __int64, _QWORD))(v37 + 1392))(
        v17 + 40768,
        a1 + 7,
        *(unsigned int *)(v11 + 256),
        &v49,
        v11 + 292,
        *v32);
    }
    else
    {
      memset(v57, 0, sizeof(v57));
      LODWORD(v50) = -1;
      if ( (unsigned __int8)std::_Is_all_bits_zero<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN>(&v50) )
        std::_Fill_zero_memset<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN *>(v57, 7);
      else
        memset(v57, 255, sizeof(v57));
      if ( v18 == 1 )
        v41 = v52[0] + 1480LL;
      else
        v41 = *(_QWORD *)(v52[0] + 39672LL);
      (*(void (__fastcall **)(__int64, _QWORD *, _QWORD, int *, __int64, _BYTE *, _QWORD))(v41 + 1320))(
        v17 + 40768,
        a1 + 7,
        *(unsigned int *)(v11 + 256),
        &v49,
        v11 + 292,
        v57,
        *v32);
      v42 = (_BYTE *)(v11 + 296);
      v43 = v57;
      do
      {
        *v42++ = *v43;
        v43 += 4;
      }
      while ( v43 != &v57[20] );
      v44 = (char *)(v11 + 301);
      v45 = &v57[20];
      do
      {
        *v44++ = *v45;
        v45 += 4;
      }
      while ( v45 != &v58 );
    }
    DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v52);
  }
  CDeviceChild<ID3D11Texture1D>::AllocateCLSOffset(v11, v29, a1 + 7);
  if ( a4 && *(_DWORD *)(a4 + 44) )
    HazardTracking::SetAcquired(a1 + 2, 0, *a1);
  v30 = *(_QWORD *)(v7 + 56);
  if ( v30 && (*(_DWORD *)(v30 + 40) & 1) == 0 )
  {
    v31 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v11 + 40LL))(
            v11,
            &GUID_DXGI_PRIMARY_DESC,
            44);
    ThrowFailure(v31);
  }
}

```

## disassembly

```asm
0x18003ce70  push    rbp
0x18003ce72  push    rbx
0x18003ce73  push    rsi
0x18003ce74  push    rdi
0x18003ce75  push    r12
0x18003ce77  push    r13
0x18003ce79  push    r14
0x18003ce7b  push    r15
0x18003ce7d  lea     rbp, [rsp-0Fh]
0x18003ce82  sub     rsp, 0D8h
0x18003ce89  mov     rax, cs:__security_cookie
0x18003ce90  xor     rax, rsp
0x18003ce93  mov     [rbp+47h+var_48], rax
0x18003ce97  mov     r12, r9
0x18003ce9a  mov     r13, r8
0x18003ce9d  mov     r14, rdx
0x18003cea0  mov     rsi, rcx
0x18003cea3  mov     rbx, [rbp+47h+arg_28]
0x18003cea7  mov     r15, [rcx]
0x18003ceaa  test    rdx, rdx
0x18003cead  jz      loc_18003D00C
0x18003ceb3  test    dword ptr [r15+11Ch], 100h
0x18003cebe  setz    cl
0x18003cec1  xor     r12d, r12d
0x18003cec4  movzx   eax, word ptr [r15+110h]
0x18003cecc  bt      ax, r12w
0x18003ced1  setnb   al
0x18003ced4  test    al, cl
0x18003ced6  jz      loc_18003D26C
0x18003cedc  cmp     byte ptr [r15+0FAh], 2
0x18003cee4  jz      loc_18003D276
0x18003ceea  test    byte ptr [r15+110h], 8
0x18003cef2  jz      short loc_18003CF4F
0x18003cef4  or      byte ptr [rsi+0Bh], 4
0x18003cef8  mov     eax, [r15+1BCh]
0x18003ceff  mov     [rsi+34h], eax
0x18003cf02  lock or [rsp+110h+var_110], r12d
0x18003cf07  lea     rcx, [rsi+24h]
0x18003cf0b  mov     eax, [r15+1ACh]
0x18003cf12  mov     [rcx], eax
0x18003cf14  mov     eax, [r15+1B0h]
0x18003cf1b  mov     [rsi+28h], eax
0x18003cf1e  mov     eax, [r15+1B4h]
0x18003cf25  mov     [rsi+2Ch], eax
0x18003cf28  mov     eax, [r15+1B8h]
0x18003cf2f  mov     [rsi+30h], eax
0x18003cf32  mov     eax, [rcx+8]
0x18003cf35  cmp     [rcx], eax
0x18003cf37  jl      loc_18003D6DF
0x18003cf3d  movups  xmm0, cs:?c_DefaultD3D11JpegOptions@@3UD3DWDDM2_0DDI_D3D11_JPEG_OPTIONS_DATA@@B; D3DWDDM2_0DDI_D3D11_JPEG_OPTIONS_DATA const c_DefaultD3D11JpegOptions
0x18003cf44  movups  xmmword ptr [rcx], xmm0
0x18003cf47  and     byte ptr [rsi+11h], 0FDh
0x18003cf4b  or      byte ptr [rsi+10h], 4
0x18003cf4f  lea     rdi, [r15+1C0h]
0x18003cf56  mov     [rbp+47h+var_80], r14
0x18003cf5a  mov     r15d, [rdx+0E68h]
0x18003cf61  mov     [rbp+47h+var_78], r15d
0x18003cf65  mov     rbx, [rdx+0E6Ch]
0x18003cf6c  mov     [rbp+47h+var_74], rbx
0x18003cf70  call    cs:__imp_GetCurrentThreadId
0x18003cf76  mov     [r14+0E68h], eax
0x18003cf7d  mov     byte ptr [r14+0E6Ch], 2
0x18003cf85  movzx   eax, [rbp+47h+var_BF]
0x18003cf89  mov     [r14+0E6Dh], ax
0x18003cf91  movzx   eax, [rbp+47h+var_BD]
0x18003cf95  mov     [r14+0E6Fh], al
0x18003cf9c  mov     [r14+0E70h], r12d
0x18003cfa3  mov     rax, [rsi]
0x18003cfa6  mov     rcx, [rax+0A0h]
0x18003cfad  movzx   eax, byte ptr [rcx+458h]
0x18003cfb4  mov     r9, rdi
0x18003cfb7  lea     r8, [rsi+38h]
0x18003cfbb  xor     edx, edx
0x18003cfbd  lea     rcx, [r14+9F40h]
0x18003cfc4  mov     rax, [r14+798h]
0x18003cfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfd0  cmp     dword ptr [r14+0E70h], 0
0x18003cfd8  jl      short loc_18003CFDE
0x18003cfda  or      byte ptr [rsi+0Bh], 1
0x18003cfde  mov     [r14+0E68h], r15d
0x18003cfe5  mov     [r14+0E6Ch], rbx
0x18003cfec  mov     rcx, [rbp+47h+var_48]
0x18003cff0  xor     rcx, rsp; StackCookie
0x18003cff3  call    __security_check_cookie
0x18003cff8  add     rsp, 0D8h
0x18003cfff  pop     r15
0x18003d001  pop     r14
0x18003d003  pop     r13
0x18003d005  pop     r12
0x18003d007  pop     rdi
0x18003d008  pop     rsi
0x18003d009  pop     rbx
0x18003d00a  pop     rbp
0x18003d00b  retn
0x18003d00c  mov     rax, [r15+0A0h]
0x18003d013  mov     rdi, [rax+438h]
0x18003d01a  mov     [rsp+110h+var_C8], rdi
0x18003d01f  test    rbx, rbx
0x18003d022  jz      loc_18003D2A7
0x18003d028  mov     rax, [rax+4D0h]
0x18003d02f  mov     ecx, [rax+4E0h]
0x18003d035  mov     rax, [rbp+47h+arg_20]
0x18003d039  test    ecx, ecx
0x18003d03b  js      loc_18003D246
0x18003d041  test    rax, rax
0x18003d044  jz      short loc_18003D054
0x18003d046  mov     [rsp+110h+var_D0], 0
0x18003d04b  cmp     byte ptr [rax], 0
0x18003d04e  jnz     loc_18003D423
0x18003d054  mov     r14d, 1
0x18003d05a  mov     [rsp+110h+var_D0], 0
0x18003d05f  mov     rdi, [rsi]
0x18003d062  mov     rdi, [rdi+0A0h]
0x18003d069  test    rdi, rdi
0x18003d06c  jz      short loc_18003D07B
0x18003d06e  cmp     byte ptr [rdi+548h], 0
0x18003d075  jnz     loc_18003D28A
0x18003d07b  xor     edi, edi
0x18003d07d  mov     [rbp-79h], rdi
0x18003d081  test    r12, r12
0x18003d084  jnz     loc_18003D43E
0x18003d08a  mov     rax, [rsi]
0x18003d08d  mov     rcx, [rax+0A0h]
0x18003d094  cmp     dword ptr [rcx+504h], 9300h
0x18003d09e  jle     loc_18003D547
0x18003d0a4  xor     al, al
0x18003d0a6  cmp     qword ptr [r13+38h], 0
0x18003d0ab  jnz     loc_18003D3F9
0x18003d0b1  mov     ecx, 0Ah
0x18003d0b6  mov     r8d, 2
0x18003d0bc  test    al, al
0x18003d0be  cmovnz  r8d, ecx
0x18003d0c2  mov     rdx, [rsp+110h+var_C8]
0x18003d0c7  lea     rcx, [rbp+47h+var_B8]
0x18003d0cb  call    ??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z; DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)
0x18003d0d0  nop
0x18003d0d1  mov     rax, [rsi]
0x18003d0d4  mov     rcx, [rax+0A0h]
0x18003d0db  mov     rcx, [rcx+4D0h]
0x18003d0e2  mov     rax, [rcx]
0x18003d0e5  mov     rdx, r12
0x18003d0e8  mov     rax, [rax+0F0h]
0x18003d0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0f4  mov     rax, [rsi]
0x18003d0f7  mov     rcx, [rax+0A0h]
0x18003d0fe  movzx   eax, byte ptr [rcx+458h]
0x18003d105  test    al, 0FCh
0x18003d107  jz      loc_18003D2B3
0x18003d10d  mov     rax, [rbp+47h+var_B8]
0x18003d111  cmp     r14d, 1
0x18003d115  jnz     loc_18003D3ED
0x18003d11b  lea     rcx, [rax+5C8h]
0x18003d122  lea     rdx, ?DDI_CreateResource11_DR@CContext@@SAXUD3D10DDI_HDEVICE@@PEBUD3D11DDIARG_CREATERESOURCE@@UD3D10DDI_HRESOURCE@@UD3D10DDI_HRTRESOURCE@@@Z; CContext::DDI_CreateResource11_DR(D3D10DDI_HDEVICE,D3D11DDIARG_CREATERESOURCE const *,D3D10DDI_HRESOURCE,D3D10DDI_HRTRESOURCE)
0x18003d129  cmp     [rcx+1D0h], rdx
0x18003d130  setnz   [rsp+110h+var_D0]
0x18003d135  cmp     r14d, 1
0x18003d139  jnz     loc_18003D3E1
0x18003d13f  add     rax, 5C8h
0x18003d145  mov     rcx, [rsp+110h+var_C8]
0x18003d14a  mov     r9, rbx
0x18003d14d  lea     r8, [rsi+38h]
0x18003d151  mov     rdx, r13
0x18003d154  add     rcx, 9F40h
0x18003d15b  mov     rax, [rax+1D0h]
0x18003d162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d167  mov     rax, [rsi]
0x18003d16a  mov     rcx, [rax+0A0h]
0x18003d171  mov     rcx, [rcx+4D0h]
0x18003d178  mov     rax, [rcx]
0x18003d17b  xor     edx, edx
0x18003d17d  mov     rax, [rax+0F0h]
0x18003d184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d189  mov     rax, [rbp+47h+var_90]
0x18003d18d  mov     eax, [rax+4]
0x18003d190  mov     [rsp+110h+var_CC], eax
0x18003d194  test    eax, eax
0x18003d196  js      short loc_18003D1A4
0x18003d198  mov     edx, r14d
0x18003d19b  mov     rcx, rsi
0x18003d19e  call    ?QueryMipTiling@CLS@?$CResource@UID3D11Buffer@@@@AEAAXW4EDDI@@@Z; CResource<ID3D11Buffer>::CLS::QueryMipTiling(EDDI)
0x18003d1a3  nop
0x18003d1a4  lea     rcx, [rbp+47h+var_B8]; this
0x18003d1a8  call    ??1DDIImmCtxMT@@QEAA@XZ; DDIImmCtxMT::~DDIImmCtxMT(void)
0x18003d1ad  movzx   ebx, [rsp+110h+var_D0]
0x18003d1b2  test    rdi, rdi
0x18003d1b5  jz      short loc_18003D1CB
0x18003d1b7  mov     rcx, rdi; struct CDevice *
0x18003d1ba  call    ?Leave@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Leave(CDevice *)
0x18003d1bf  lea     rcx, [rdi+0F8h]
0x18003d1c6  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18003d1cb  mov     rdi, [rsp+110h+var_C8]
0x18003d1d0  mov     ecx, [rsp+110h+var_CC]; int
0x18003d1d4  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18003d1d9  movzx   ecx, byte ptr [rsi+0Bh]
0x18003d1dd  xor     cl, bl
0x18003d1df  and     cl, 1
0x18003d1e2  xor     [rsi+0Bh], cl
0x18003d1e5  cmp     dword ptr [r13+1Ch], 0
0x18003d1ea  jnz     loc_18003D2DC
0x18003d1f0  lea     r8, [rsi+38h]
0x18003d1f4  mov     rcx, r15
0x18003d1f7  call    ?AllocateCLSOffset@?$CDeviceChild@UID3D11Texture1D@@@@QEAAXW4D3D11DDI_HANDLETYPE@@PEAX_K@Z; CDeviceChild<ID3D11Texture1D>::AllocateCLSOffset(D3D11DDI_HANDLETYPE,void *,unsigned __int64)
0x18003d1fc  test    r12, r12
0x18003d1ff  jnz     loc_18003D66A
0x18003d205  mov     r9, [r13+38h]
0x18003d209  test    r9, r9
0x18003d20c  jz      loc_18003CFEC
0x18003d212  mov     eax, [r9+28h]
0x18003d216  test    al, 1
0x18003d218  jnz     loc_18003CFEC
0x18003d21e  mov     rax, [r15]
0x18003d221  mov     r8d, 2Ch ; ','
0x18003d227  lea     rdx, GUID_DXGI_PRIMARY_DESC
0x18003d22e  mov     rcx, r15
0x18003d231  mov     rax, [rax+28h]
0x18003d235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d23a  mov     ecx, eax; int
0x18003d23c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18003d241  jmp     loc_18003CFEC
0x18003d246  mov     [rsp+110h+var_D0], 0
0x18003d24b  mov     r14d, 3
0x18003d251  mov     [rsp+110h+var_CC], 887A0005h
0x18003d259  test    rax, rax
0x18003d25c  jnz     loc_18003D401
0x18003d262  movzx   ebx, [rsp+110h+var_D0]
0x18003d267  jmp     loc_18003D1D0
0x18003d26c  cmp     byte ptr [r15+0FAh], 2
0x18003d274  jnz     short loc_18003D27A
0x18003d276  mov     [rsi+0Ah], r12b
0x18003d27a  inc     qword ptr [rdx+9A40h]
0x18003d281  or      byte ptr [rsi+0Bh], 4
0x18003d285  jmp     loc_18003CEEA
0x18003d28a  mov     [rbp-79h], rdi
0x18003d28e  lea     rcx, [rdi+0F8h]
0x18003d295  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18003d29a  mov     rcx, rdi; struct CDevice *
0x18003d29d  call    ?Enter@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Enter(CDevice *)
0x18003d2a2  jmp     loc_18003D081
0x18003d2a7  mov     rbx, [r15+0A8h]
0x18003d2ae  jmp     loc_18003D028
0x18003d2b3  cmp     al, 1
0x18003d2b5  jz      loc_18003D10D
0x18003d2bb  mov     rax, [rbp+47h+var_B8]
0x18003d2bf  cmp     r14d, 1
0x18003d2c3  jnz     loc_18003D689
0x18003d2c9  lea     rcx, [rax+5C8h]
0x18003d2d0  lea     rdx, ?DDI_CreateResource11_DR@CContext@@SAXUD3D10DDI_HDEVICE@@PEBUD3D11DDIARG_CREATERESOURCE@@UD3D10DDI_HRESOURCE@@UD3D10DDI_HRTRESOURCE@@@Z; CContext::DDI_CreateResource11_DR(D3D10DDI_HDEVICE,D3D11DDIARG_CREATERESOURCE const *,D3D10DDI_HRESOURCE,D3D10DDI_HRTRESOURCE)
0x18003d2d7  jmp     loc_18003D129
0x18003d2dc  cmp     dword ptr [r13+48h], 0
0x18003d2e1  jnz     loc_18003D1F0
0x18003d2e7  cmp     byte ptr [r15+0FAh], 0
0x18003d2ef  jnz     loc_18003D1F0
0x18003d2f5  mov     eax, [r13+10h]
0x18003d2f9  sub     eax, 2
0x18003d2fc  cmp     eax, 3
0x18003d2ff  ja      loc_18003D1F0
0x18003d305  lea     rbx, [r15+130h]
0x18003d30c  mov     edx, [r15+100h]
0x18003d313  mov     r9, [rbx+8]
0x18003d317  mov     r8, [rbx]
0x18003d31a  mov     rcx, r9
0x18003d31d  sub     rcx, r8
0x18003d320  sar     rcx, 5
0x18003d324  cmp     rdx, rcx
0x18003d327  jb      loc_18003D42E
0x18003d32d  jbe     short loc_18003D34B
0x18003d32f  mov     rax, [rbx+10h]
0x18003d333  sub     rax, r8
0x18003d336  sar     rax, 5
0x18003d33a  cmp     rdx, rax
0x18003d33d  jbe     loc_18003D6ED
0x18003d343  mov     rcx, rbx
0x18003d346  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UD3DWDDM2_0DDI_SUBRESOURCE_LAYOUT@@V?$allocator@UD3DWDDM2_0DDI_SUBRESOURCE_LAYOUT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<D3DWDDM2_0DDI_SUBRESOURCE_LAYOUT>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003d34b  xor     r8d, r8d
0x18003d34e  mov     rdx, rdi
0x18003d351  lea     rcx, [rbp+47h+var_B8]
0x18003d355  call    ??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z; DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)
0x18003d35a  nop
0x18003d35b  mov     [rsp+110h+var_CC], 0
0x18003d363  mov     rax, [rsi]
0x18003d366  mov     rcx, [rax+0A0h]; this
0x18003d36d  cmp     byte ptr [rcx+470h], 0
0x18003d374  jnz     loc_18003D57E
0x18003d37a  call    ?IsDDIWDDM2_0BuildVersion5OrEarlier@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(void)
0x18003d37f  test    al, al
0x18003d381  jz      loc_18003D59C
0x18003d387  mov     rax, [rbp+47h+var_B8]
0x18003d38b  cmp     r14d, 1
0x18003d38f  jnz     loc_18003D503
0x18003d395  add     rax, 5C8h
0x18003d39b  lea     rdx, [rsi+38h]
0x18003d39f  lea     rcx, [rdi+9F40h]
0x18003d3a6  lea     r9, [r15+124h]
0x18003d3ad  mov     r8, [rbx]
0x18003d3b0  mov     [rsp+110h+var_E8], r8
0x18003d3b5  mov     [rsp+110h+var_F0], r9
0x18003d3ba  lea     r9, [rsp+110h+var_CC]
0x18003d3bf  mov     r8d, [r15+100h]
0x18003d3c6  mov     rax, [rax+570h]
0x18003d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
