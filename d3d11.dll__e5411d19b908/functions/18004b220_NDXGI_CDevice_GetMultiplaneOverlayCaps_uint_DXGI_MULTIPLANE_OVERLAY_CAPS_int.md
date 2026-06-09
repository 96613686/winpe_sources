# NDXGI::CDevice::GetMultiplaneOverlayCaps(uint,DXGI_MULTIPLANE_OVERLAY_CAPS *,int *)

- ea: `0x18004b220`
- end: `0x18004b5aa`
- name: `?GetMultiplaneOverlayCaps@CDevice@NDXGI@@UEAAJIPEAUDXGI_MULTIPLANE_OVERLAY_CAPS@@PEAH@Z`
- size: `906`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, unsigned int, struct DXGI_MULTIPLANE_OVERLAY_CAPS *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800bd440`

## callees

- `0x180022630`
- `0x18004b220`
- `0x18004ba20`
- `0x18004ba94`
- `0x18004bb50`
- `0x18004bbc4`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTGetMultiPlaneOverlayCaps` at `0x18004b2b7`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTGetMultiPlaneOverlayCaps` at `0x18004b2b7`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTGetPostCompositionCaps` at `0x18004b439`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTGetPostCompositionCaps` at `0x18004b439`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::GetMultiplaneOverlayCaps(
        NDXGI::CDevice *this,
        unsigned int a2,
        struct DXGI_MULTIPLANE_OVERLAY_CAPS *a3,
        int *a4)
{
  NDXGI::CDevice *v4; // rsi
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int InternalMultiplaneOverlayCaps; // edi
  int v13; // eax
  unsigned int v15; // r13d
  unsigned int v16; // r15d
  __int64 v17; // rax
  char v18; // dl
  char *v19; // rax
  int v20; // ecx
  float v21; // xmm0_4
  int v22; // r8d
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edx
  unsigned int v27; // ecx
  int v28; // xmm0_4
  int v29; // xmm1_4
  int v30; // r9d
  int v31; // r8d
  int v32; // eax
  __int64 v33; // rcx
  bool v34; // [rsp+30h] [rbp-39h]
  __int128 v35; // [rsp+38h] [rbp-31h] BYREF
  __int128 v36; // [rsp+48h] [rbp-21h] BYREF
  __int128 v37; // [rsp+58h] [rbp-11h]

  v4 = (NDXGI::CDevice *)((char *)this - 16);
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *(_OWORD *)((char *)a3 + 28) = 0;
  *(_DWORD *)a3 = 1;
  *((_DWORD *)a3 + 4) = 1065353216;
  *((_DWORD *)a3 + 5) = 1065353216;
  *a4 = 0;
  if ( !NDXGI::CDevice::DriverSupportsKernelOverlayCaps((NDXGI::CDevice *)((char *)this - 16)) )
  {
    v34 = NDXGI::CDevice::PanelFitterEnabled(v4);
    *(_QWORD *)&v35 = 0;
    InternalMultiplaneOverlayCaps = NDXGI::CDevice::GetInternalMultiplaneOverlayCaps(
                                      v4,
                                      a2,
                                      (struct DXGI_INTERNAL_MULTIPLANE_OVERLAY_CAPS *)&v35,
                                      a4);
    if ( InternalMultiplaneOverlayCaps < 0 )
      goto LABEL_4;
    v15 = DWORD1(v35);
    v16 = 0;
    *(_DWORD *)a3 = v35;
    if ( !v15 )
      goto LABEL_4;
    while ( 1 )
    {
      v17 = *(_QWORD *)this;
      v35 = 0;
      if ( (*(int (__fastcall **)(NDXGI::CDevice *, _QWORD, _QWORD, __int128 *))(v17 + 224))(this, a2, v16, &v35) >= 0 )
      {
        v18 = BYTE12(v35);
        if ( (WORD6(v35) & 0x800) == 0 )
        {
          v19 = (char *)a3 + 4;
          goto LABEL_14;
        }
        if ( v34 )
        {
          v19 = (char *)a3 + 24;
LABEL_14:
          *((_DWORD *)v19 + 2) |= HIDWORD(v35);
          v20 = *((_DWORD *)v19 + 2);
          v21 = *((float *)&v35 + 1);
          v22 = v35;
          if ( (v18 & 0x20) != 0 )
          {
            *(_DWORD *)v19 += v35;
            if ( v21 > 1.0 )
            {
              v20 |= 0x400u;
              *((_DWORD *)v19 + 2) = v20;
            }
          }
          if ( (v18 & 0x40) != 0 )
          {
            *((_DWORD *)v19 + 1) += v22;
            if ( v21 > 1.0 )
              *((_DWORD *)v19 + 2) = v20 | 0x200;
          }
          if ( v21 > *((float *)v19 + 3) )
            *((float *)v19 + 3) = v21;
          if ( *((float *)v19 + 4) > *((float *)&v35 + 2) )
            *((_DWORD *)v19 + 4) = DWORD2(v35);
        }
      }
      if ( ++v16 >= v15 )
      {
        v4 = (NDXGI::CDevice *)((char *)this - 16);
        goto LABEL_4;
      }
    }
  }
  v9 = *((_QWORD *)v4 + 12);
  v36 = 0;
  v37 = 0;
  LODWORD(v36) = *(_DWORD *)(v9 + 96);
  DWORD1(v36) = a2;
  v10 = D3DKMTGetMultiPlaneOverlayCaps(&v36);
  v11 = NDXGI::CDevice::NTStatusToHResult(v4, v10);
  InternalMultiplaneOverlayCaps = v11;
  if ( v11 == -2005530512 )
    goto LABEL_3;
  if ( v11 < 0 )
    goto LABEL_4;
  v23 = *((_QWORD *)this + 10);
  v35 = 0;
  LODWORD(v35) = *(_DWORD *)(v23 + 96);
  DWORD1(v35) = a2;
  v24 = D3DKMTGetPostCompositionCaps(&v35);
  v25 = NDXGI::CDevice::NTStatusToHResult(v4, v24);
  InternalMultiplaneOverlayCaps = v25;
  if ( v25 == -2005530512 )
  {
LABEL_3:
    InternalMultiplaneOverlayCaps = -2005270523;
  }
  else if ( v25 >= 0 )
  {
    v26 = DWORD1(v37);
    v27 = HIDWORD(v36);
    v28 = DWORD2(v37);
    v29 = HIDWORD(v37);
    v30 = v37;
    *(_DWORD *)a3 = DWORD2(v36);
    *((_DWORD *)a3 + 4) = v28;
    *((_DWORD *)a3 + 5) = v29;
    *((_DWORD *)a3 + 1) = v27;
    *((_DWORD *)a3 + 2) = v30;
    v31 = v26 & 1
        | (((v26 >> 1) & 1) << 15)
        | (2 * ((v26 >> 2) & 1))
        | (4 * ((v26 >> 3) & 1))
        | (((v26 >> 9) & 1) << 16)
        | (((v26 >> 10) & 1) << 17)
        | (((v26 >> 6) & 1) << 7)
        | (((v26 >> 7) & 1) << 8)
        | (((v26 >> 8) & 1) << 13);
    *((_DWORD *)a3 + 3) = v31;
    if ( v27 > 1 )
    {
      v32 = v31 | (((v26 >> 4) & 1) << 10) | 0x20;
      *((_DWORD *)a3 + 3) = v32;
    }
    else
    {
      v32 = v26 & 1
          | (((v26 >> 1) & 1) << 15)
          | (2 * ((v26 >> 2) & 1))
          | (4 * ((v26 >> 3) & 1))
          | (((v26 >> 9) & 1) << 16)
          | (((v26 >> 10) & 1) << 17)
          | (((v26 >> 6) & 1) << 7)
          | (((v26 >> 7) & 1) << 8)
          | (((v26 >> 8) & 1) << 13);
    }
    if ( v30 )
      *((_DWORD *)a3 + 3) = v32 | (((v26 >> 5) & 1) << 9) | 0x40;
    if ( *((float *)&v35 + 2) > 1.0 )
    {
      *(_QWORD *)((char *)a3 + 36) = *((_QWORD *)&v35 + 1);
      *((_DWORD *)a3 + 6) = 1;
      *((_DWORD *)a3 + 8) = 1024;
    }
    *a4 = 1;
  }
LABEL_4:
  if ( NDXGI::CDevice::MPO3DDIsEnabled(v4) && *((_QWORD *)this + 103) )
    *((_DWORD *)a3 + 3) |= 0x40000u;
  v13 = *((_DWORD *)a3 + 3);
  if ( (v13 & 0x8000) != 0 )
  {
    v33 = *((_QWORD *)this + 10);
    if ( *(_DWORD *)(v33 + 940) == 32902 && *(_DWORD *)(v33 + 944) == 3889 )
      *((_DWORD *)a3 + 3) = v13 & 0xFFFF7FFF;
  }
  return (unsigned int)InternalMultiplaneOverlayCaps;
}

```

## disassembly

```asm
0x18004b220  push    rbp
0x18004b222  push    rbx
0x18004b223  push    rsi
0x18004b224  push    rdi
0x18004b225  push    r12
0x18004b227  push    r13
0x18004b229  push    r14
0x18004b22b  push    r15
0x18004b22d  lea     rbp, [rsp-1Fh]
0x18004b232  sub     rsp, 88h
0x18004b239  movaps  [rsp+0C0h+var_50], xmm6
0x18004b23e  mov     rax, cs:__security_cookie
0x18004b245  xor     rax, rsp
0x18004b248  mov     [rbp+57h+var_58], rax
0x18004b24c  xorps   xmm0, xmm0
0x18004b24f  lea     rsi, [rcx-10h]
0x18004b253  movups  xmmword ptr [r8], xmm0
0x18004b257  mov     eax, 3F800000h
0x18004b25c  mov     r14, rcx
0x18004b25f  movups  xmmword ptr [r8+10h], xmm0
0x18004b264  mov     r13d, 1
0x18004b26a  mov     rcx, rsi; this
0x18004b26d  movups  xmmword ptr [r8+1Ch], xmm0
0x18004b272  mov     [r8], r13d
0x18004b275  mov     r15, r9
0x18004b278  mov     [r8+10h], eax
0x18004b27c  mov     rbx, r8
0x18004b27f  mov     [r8+14h], eax
0x18004b283  mov     r12d, edx
0x18004b286  mov     dword ptr [r9], 0
0x18004b28d  call    ?DriverSupportsKernelOverlayCaps@CDevice@NDXGI@@QEAA_NXZ; NDXGI::CDevice::DriverSupportsKernelOverlayCaps(void)
0x18004b292  test    al, al
0x18004b294  jz      loc_18004B328
0x18004b29a  mov     rax, [rsi+60h]
0x18004b29e  xorps   xmm0, xmm0
0x18004b2a1  movups  [rbp+57h+var_78], xmm0
0x18004b2a5  movups  [rbp+57h+var_68], xmm0
0x18004b2a9  mov     ecx, [rax+60h]
0x18004b2ac  mov     dword ptr [rbp+57h+var_78], ecx
0x18004b2af  lea     rcx, [rbp+57h+var_78]
0x18004b2b3  mov     dword ptr [rbp+57h+var_78+4], r12d
0x18004b2b7  call    cs:__imp_D3DKMTGetMultiPlaneOverlayCaps
0x18004b2bd  mov     edx, eax; int
0x18004b2bf  mov     rcx, rsi; this
0x18004b2c2  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18004b2c7  mov     edi, eax
0x18004b2c9  cmp     eax, 88760870h
0x18004b2ce  jnz     loc_18004B418
0x18004b2d4  mov     edi, 887A0005h
0x18004b2d9  mov     rcx, rsi; this
0x18004b2dc  call    ?MPO3DDIsEnabled@CDevice@NDXGI@@QEAA_NXZ; NDXGI::CDevice::MPO3DDIsEnabled(void)
0x18004b2e1  test    al, al
0x18004b2e3  jz      short loc_18004B2F4
0x18004b2e5  cmp     qword ptr [r14+338h], 0
0x18004b2ed  jz      short loc_18004B2F4
0x18004b2ef  bts     dword ptr [rbx+0Ch], 12h
0x18004b2f4  mov     eax, [rbx+0Ch]
0x18004b2f7  bt      eax, 0Fh
0x18004b2fb  jb      loc_18004B57A
0x18004b301  mov     eax, edi
0x18004b303  mov     rcx, [rbp+57h+var_58]
0x18004b307  xor     rcx, rsp; StackCookie
0x18004b30a  call    __security_check_cookie
0x18004b30f  movaps  xmm6, [rsp+0C0h+var_50]
0x18004b314  add     rsp, 88h
0x18004b31b  pop     r15
0x18004b31d  pop     r14
0x18004b31f  pop     r13
0x18004b321  pop     r12
0x18004b323  pop     rdi
0x18004b324  pop     rsi
0x18004b325  pop     rbx
0x18004b326  pop     rbp
0x18004b327  retn
0x18004b328  mov     rcx, rsi; this
0x18004b32b  call    ?PanelFitterEnabled@CDevice@NDXGI@@QEAA_NXZ; NDXGI::CDevice::PanelFitterEnabled(void)
0x18004b330  mov     r9, r15; int *
0x18004b333  mov     [rbp+57h+var_90], al
0x18004b336  lea     r8, [rbp+57h+var_88]; struct DXGI_INTERNAL_MULTIPLANE_OVERLAY_CAPS *
0x18004b33a  mov     qword ptr [rbp+57h+var_88], 0
0x18004b342  mov     edx, r12d; unsigned int
0x18004b345  mov     rcx, rsi; this
0x18004b348  call    ?GetInternalMultiplaneOverlayCaps@CDevice@NDXGI@@QEAAJIPEAUDXGI_INTERNAL_MULTIPLANE_OVERLAY_CAPS@@PEAH@Z; NDXGI::CDevice::GetInternalMultiplaneOverlayCaps(uint,DXGI_INTERNAL_MULTIPLANE_OVERLAY_CAPS *,int *)
0x18004b34d  mov     edi, eax
0x18004b34f  test    eax, eax
0x18004b351  js      short loc_18004B2D9
0x18004b353  mov     r13d, dword ptr [rbp+57h+var_88+4]
0x18004b357  xor     r15d, r15d
0x18004b35a  mov     ecx, dword ptr [rbp+57h+var_88]
0x18004b35d  mov     [rbx], ecx
0x18004b35f  test    r13d, r13d
0x18004b362  jz      loc_18004B2D9
0x18004b368  movss   xmm6, cs:__real@3f800000
0x18004b370  mov     sil, [rbp+57h+var_90]
0x18004b374  mov     rax, [r14]
0x18004b377  lea     r9, [rbp+57h+var_88]
0x18004b37b  xorps   xmm0, xmm0
0x18004b37e  mov     r8d, r15d
0x18004b381  mov     edx, r12d
0x18004b384  mov     rcx, r14
0x18004b387  movups  [rbp+57h+var_88], xmm0
0x18004b38b  mov     rax, [rax+0E0h]
0x18004b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b397  test    eax, eax
0x18004b399  js      short loc_18004B403
0x18004b39b  mov     edx, dword ptr [rbp+57h+var_88+0Ch]
0x18004b39e  bt      edx, 0Bh
0x18004b3a2  jb      loc_18004B568
0x18004b3a8  lea     rax, [rbx+4]
0x18004b3ac  or      [rax+8], edx
0x18004b3af  mov     ecx, [rax+8]
0x18004b3b2  movss   xmm0, dword ptr [rbp+57h+var_88+4]
0x18004b3b7  mov     r8d, dword ptr [rbp+57h+var_88]
0x18004b3bb  test    dl, 20h
0x18004b3be  jz      short loc_18004B3CF
0x18004b3c0  add     [rax], r8d
0x18004b3c3  comiss  xmm0, xmm6
0x18004b3c6  jbe     short loc_18004B3CF
0x18004b3c8  bts     ecx, 0Ah
0x18004b3cc  mov     [rax+8], ecx
0x18004b3cf  test    dl, 40h
0x18004b3d2  jz      short loc_18004B3E4
0x18004b3d4  add     [rax+4], r8d
0x18004b3d8  comiss  xmm0, xmm6
0x18004b3db  jbe     short loc_18004B3E4
0x18004b3dd  bts     ecx, 9
0x18004b3e1  mov     [rax+8], ecx
0x18004b3e4  comiss  xmm0, dword ptr [rax+0Ch]
0x18004b3e8  jbe     short loc_18004B3EF
0x18004b3ea  movss   dword ptr [rax+0Ch], xmm0
0x18004b3ef  movss   xmm0, dword ptr [rax+10h]
0x18004b3f4  movss   xmm1, dword ptr [rbp+57h+var_88+8]
0x18004b3f9  comiss  xmm0, xmm1
0x18004b3fc  jbe     short loc_18004B403
0x18004b3fe  movss   dword ptr [rax+10h], xmm1
0x18004b403  inc     r15d
0x18004b406  cmp     r15d, r13d
0x18004b409  jb      loc_18004B374
0x18004b40f  lea     rsi, [r14-10h]
0x18004b413  jmp     loc_18004B2D9
0x18004b418  test    eax, eax
0x18004b41a  js      loc_18004B2D9
0x18004b420  mov     rax, [r14+50h]
0x18004b424  xorps   xmm0, xmm0
0x18004b427  movups  [rbp+57h+var_88], xmm0
0x18004b42b  mov     ecx, [rax+60h]
0x18004b42e  mov     dword ptr [rbp+57h+var_88], ecx
0x18004b431  lea     rcx, [rbp+57h+var_88]
0x18004b435  mov     dword ptr [rbp+57h+var_88+4], r12d
0x18004b439  call    cs:__imp_D3DKMTGetPostCompositionCaps
0x18004b43f  mov     edx, eax; int
0x18004b441  mov     rcx, rsi; this
0x18004b444  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18004b449  mov     edi, eax
0x18004b44b  cmp     eax, 88760870h
0x18004b450  jz      loc_18004B2D4
0x18004b456  test    eax, eax
0x18004b458  js      loc_18004B2D9
0x18004b45e  mov     edx, dword ptr [rbp+57h+var_68+4]
0x18004b461  mov     r8d, edx
0x18004b464  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18004b467  mov     ecx, dword ptr [rbp+57h+var_78+0Ch]
0x18004b46a  movss   xmm0, dword ptr [rbp+57h+var_68+8]
0x18004b46f  movss   xmm1, dword ptr [rbp+57h+var_68+0Ch]
0x18004b474  mov     r9d, dword ptr [rbp+57h+var_68]
0x18004b478  mov     [rbx], eax
0x18004b47a  mov     eax, edx
0x18004b47c  shr     eax, 7
0x18004b47f  and     eax, r13d
0x18004b482  shr     r8d, 8
0x18004b486  shl     eax, 8
0x18004b489  and     r8d, r13d
0x18004b48c  shl     r8d, 0Dh
0x18004b490  or      r8d, eax
0x18004b493  movss   dword ptr [rbx+10h], xmm0
0x18004b498  mov     eax, edx
0x18004b49a  movss   dword ptr [rbx+14h], xmm1
0x18004b49f  shr     eax, 6
0x18004b4a2  and     eax, r13d
0x18004b4a5  mov     [rbx+4], ecx
0x18004b4a8  shl     eax, 7
0x18004b4ab  or      r8d, eax
0x18004b4ae  mov     [rbx+8], r9d
0x18004b4b2  mov     eax, edx
0x18004b4b4  shr     eax, 0Ah
0x18004b4b7  and     eax, r13d
0x18004b4ba  shl     eax, 11h
0x18004b4bd  or      r8d, eax
0x18004b4c0  mov     eax, edx
0x18004b4c2  shr     eax, 9
0x18004b4c5  and     eax, r13d
0x18004b4c8  shl     eax, 10h
0x18004b4cb  or      r8d, eax
0x18004b4ce  mov     eax, edx
0x18004b4d0  shr     eax, 3
0x18004b4d3  and     eax, r13d
0x18004b4d6  shl     eax, 2
0x18004b4d9  or      r8d, eax
0x18004b4dc  mov     eax, edx
0x18004b4de  shr     eax, 2
0x18004b4e1  and     eax, r13d
0x18004b4e4  add     eax, eax
0x18004b4e6  or      r8d, eax
0x18004b4e9  mov     eax, edx
0x18004b4eb  shr     eax, 1
0x18004b4ed  and     eax, r13d
0x18004b4f0  shl     eax, 0Fh
0x18004b4f3  or      r8d, eax
0x18004b4f6  mov     eax, edx
0x18004b4f8  and     eax, r13d
0x18004b4fb  or      r8d, eax
0x18004b4fe  mov     [rbx+0Ch], r8d
0x18004b502  cmp     ecx, r13d
0x18004b505  ja      short loc_18004B53F
0x18004b507  mov     eax, r8d
0x18004b50a  test    r9d, r9d
0x18004b50d  jnz     short loc_18004B555
0x18004b50f  movss   xmm0, dword ptr [rbp+57h+var_88+8]
0x18004b514  comiss  xmm0, cs:__real@3f800000
0x18004b51b  jbe     short loc_18004B537
0x18004b51d  movss   dword ptr [rbx+24h], xmm0
0x18004b522  movss   xmm0, dword ptr [rbp+57h+var_88+0Ch]
0x18004b527  movss   dword ptr [rbx+28h], xmm0
0x18004b52c  mov     [rbx+18h], r13d
0x18004b530  mov     dword ptr [rbx+20h], 400h
0x18004b537  mov     [r15], r13d
0x18004b53a  jmp     loc_18004B2D9
0x18004b53f  mov     eax, edx
0x18004b541  shr     eax, 4
0x18004b544  and     eax, r13d
0x18004b547  shl     eax, 0Ah
0x18004b54a  or      eax, r8d
0x18004b54d  or      eax, 20h
0x18004b550  mov     [rbx+0Ch], eax
0x18004b553  jmp     short loc_18004B50A
0x18004b555  shr     edx, 5
0x18004b558  and     edx, r13d
0x18004b55b  shl     edx, 9
0x18004b55e  or      edx, eax
0x18004b560  or      edx, 40h
0x18004b563  mov     [rbx+0Ch], edx
0x18004b566  jmp     short loc_18004B50F
0x18004b568  test    sil, sil
0x18004b56b  jz      loc_18004B403
0x18004b571  lea     rax, [rbx+18h]
0x18004b575  jmp     loc_18004B3AC
0x18004b57a  mov     rcx, [r14+50h]
0x18004b57e  cmp     dword ptr [rcx+3ACh], 8086h
0x18004b588  jnz     loc_18004B301
0x18004b58e  cmp     dword ptr [rcx+3B0h], 0F31h
0x18004b598  jnz     loc_18004B301
0x18004b59e  btr     eax, 0Fh
0x18004b5a2  mov     [rbx+0Ch], eax
0x18004b5a5  jmp     loc_18004B301
```
