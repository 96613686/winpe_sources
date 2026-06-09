# NDXGI::CDevice::PresentMultiplaneOverlay1CBImpl<DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO>(void *,DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO * *,uint,void *)

- ea: `0x18005d440`
- end: `0x18005d9a6`
- name: `??$PresentMultiplaneOverlay1CBImpl@UDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO@@@CDevice@NDXGI@@KAJPEAXPEAPEAUDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO@@I0@Z`
- size: `1382`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005d420`

## callees

- `0x180021b90`
- `0x180022630`
- `0x1800349cc`
- `0x180035e3c`
- `0x180053c88`
- `0x18005d440`
- `0x180070520`
- `0x180074d78`
- `0x1800a9d20`
- `0x1800dd664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d87e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d87e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d52f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d4d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d4d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d878`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d8f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d8f1`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTPresentMultiPlaneOverlay3` at `0x18005d7b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NDXGI::CDevice::PresentMultiplaneOverlay1CBImpl<DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO>(
        NDXGI::CDevice *this,
        __int64 a2,
        int a3,
        ULONG_PTR a4)
{
  ULONG_PTR v4; // r14
  __int64 v6; // r10
  unsigned int v8; // r8d
  __int64 v9; // rdx
  ULONG_PTR v10; // rsi
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  struct IErrorInfo *v12; // r8
  bool v13; // r9
  __int64 *v14; // rdx
  __int64 *v15; // rax
  __int64 *i; // rcx
  int v17; // eax
  __int64 v18; // rcx
  char v20; // dl
  char v21; // r9
  unsigned int v22; // r12d
  __int64 v23; // rcx
  __int64 v24; // r15
  unsigned int *v25; // rbx
  unsigned int v26; // eax
  int v27; // r14d
  char v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // esi
  _QWORD *v33; // rcx
  __int64 *v34; // rax
  int v35; // r10d
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  char v40; // [rsp+30h] [rbp-1C8h]
  char v41; // [rsp+31h] [rbp-1C7h]
  bool v42; // [rsp+32h] [rbp-1C6h] BYREF
  bool v43; // [rsp+33h] [rbp-1C5h] BYREF
  char v44; // [rsp+34h] [rbp-1C4h]
  __int64 v45; // [rsp+38h] [rbp-1C0h]
  ULONG_PTR v46; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v47; // [rsp+48h] [rbp-1B0h]
  _QWORD v48[3]; // [rsp+50h] [rbp-1A8h] BYREF
  _com_error *v49; // [rsp+68h] [rbp-190h] BYREF
  _BYTE pExceptionObject[44]; // [rsp+70h] [rbp-188h] BYREF
  int v51; // [rsp+9Ch] [rbp-15Ch]
  _DWORD v52[64]; // [rsp+B0h] [rbp-148h] BYREF

  v4 = a4;
  v46 = a4;
  v6 = a2;
  v47 = a2;
  v8 = 0;
  v45 = 0;
  v48[0] = this;
  v48[1] = a4;
  v9 = *((_QWORD *)this + 9);
  if ( *(_BYTE *)(v9 + 1112) > 9u
    || *(_BYTE *)(v9 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 1232) + 96LL) + 912LL)) >= 4u )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1920);
    v48[2] = (char *)this + 1920;
    EnterCriticalSection((LPCRITICAL_SECTION)this + 48);
    v14 = (__int64 *)*((_QWORD *)this + 245);
    v15 = (__int64 *)v14[1];
    v51 = 0;
    for ( i = v14; !*((_BYTE *)v15 + 25); v15 = (__int64 *)*v15 )
    {
      if ( v15[4] >= v4 )
        i = v15;
      else
        v15 += 2;
    }
    if ( *((_BYTE *)i + 25) )
      goto LABEL_97;
    while ( v4 < i[4] || i == v14 )
    {
LABEL_97:
      try
      {
        _com_error::_com_error((_com_error *)pExceptionObject, -2147024809, v12, v13);
        throw (_com_error *)pExceptionObject;
      }
      catch ( _com_error *v49 )
      {
        LODWORD(v46) = *((_DWORD *)v49 + 2);
        ScopeExit<_lambda_9f297a07735dab95dc135be842567443_>::~ScopeExit<_lambda_9f297a07735dab95dc135be842567443_>(v48);
        return (unsigned int)v46;
      }
      catch ( std::bad_alloc )
      {
        ScopeExit<_lambda_9f297a07735dab95dc135be842567443_>::~ScopeExit<_lambda_9f297a07735dab95dc135be842567443_>(v48);
        return 2147942414LL;
      }
    }
    v10 = i[5];
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 48);
    v6 = v47;
    v8 = 0;
  }
  else
  {
    v10 = a4;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1920);
  }
  v17 = *(_DWORD *)(v10 + 28);
  if ( a3 != v17 )
  {
    v18 = *((_QWORD *)this + 9);
    if ( *(_BYTE *)(v18 + 1112) <= 9u
      && (*(_BYTE *)(v18 + 1112) != 9 || HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 1232) + 96LL) + 912LL)) < 4u) )
    {
      return 2147942487LL;
    }
    NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v11, v4);
    return 2147942487LL;
  }
  *(_QWORD *)(v10 + 8) = v52;
  *(_DWORD *)(v10 + 4) = 0;
  v20 = 1;
  v44 = 1;
  v40 = 0;
  v21 = 0;
  v41 = 0;
  v22 = 0;
  if ( !v17 )
  {
LABEL_52:
    if ( !*(_DWORD *)(v10 + 4) )
    {
      *(_DWORD *)(v10 + 4) = 1;
      v52[0] = *(_DWORD *)(**(_QWORD **)(*(_QWORD *)v6 + 8LL) + 8LL);
    }
    v31 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
            D3DKMTPresentMultiPlaneOverlay3,
            "PresentMultiplaneOverlay3",
            v10);
    HIDWORD(v45) = v31;
    if ( v31 <= -1071775733 )
    {
      if ( v31 != -1071775733 )
      {
        if ( (unsigned int)(v31 + 1071775739) > 2 && v31 != -1071775744 )
          goto LABEL_58;
        goto LABEL_66;
      }
LABEL_59:
      v32 = 0;
LABEL_67:
      LODWORD(v45) = v32;
      goto LABEL_68;
    }
    if ( v31 == -1071775731 )
    {
      HIDWORD(v45) = 0;
    }
    else if ( (unsigned int)(v31 + 1071775720) > 1 && v31 != -1071774910 )
    {
      if ( v31 != 259 )
      {
LABEL_58:
        v32 = NDXGI::CDevice::NTStatusToHResult(this, v31);
        LODWORD(v45) = v32;
LABEL_68:
        if ( *((_BYTE *)this + 898) )
        {
          v33 = (_QWORD *)*((_QWORD *)this + 176);
          if ( v33 )
            *v33 = v45;
        }
        else
        {
          AcquireSRWLockShared((PSRWLOCK)this + 167);
          LODWORD(v46) = GetCurrentThreadId();
          v34 = (__int64 *)(*((_QWORD *)this + 171)
                          + 16 * (*((_QWORD *)this + 174) & std::_Hash_representation<unsigned long>(&v46)));
          v36 = v34[1];
          v37 = *((_QWORD *)this + 169);
          if ( v36 == v37 )
          {
LABEL_76:
            v36 = 0;
          }
          else
          {
            v38 = *v34;
            while ( v35 != *(_DWORD *)(v36 + 16) )
            {
              if ( v36 == v38 )
                goto LABEL_76;
              v36 = *(_QWORD *)(v36 + 8);
            }
          }
          if ( v36 && v36 != v37 )
            **(_QWORD **)(v36 + 24) = v45;
          if ( this != (NDXGI::CDevice *)-1336LL )
            ReleaseSRWLockShared((PSRWLOCK)this + 167);
        }
        if ( v32 == -2005532132 || v32 == -2005530512 )
          v32 = 0;
        v39 = *((_QWORD *)this + 9);
        if ( *(_BYTE *)(v39 + 1112) > 9u
          || *(_BYTE *)(v39 + 1112) == 9
          && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v39 + 1232) + 96LL) + 912LL)) >= 4u )
        {
          NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v11, v4);
        }
        return v32;
      }
      goto LABEL_59;
    }
LABEL_66:
    v32 = *((int *)this + 312) < 0 ? 0x88760870 : 0;
    goto LABEL_67;
  }
  while ( 1 )
  {
    v23 = 8LL * v22;
    v24 = *(_QWORD *)(v23 + *(_QWORD *)(v10 + 32));
    v25 = *(unsigned int **)(v6 + v23);
    if ( (*(_BYTE *)(v24 + 4) & 1) == 0 )
    {
      *(_QWORD *)(v24 + 24) = 0;
      *(_DWORD *)(v24 + 16) = 0;
      v28 = v40;
      goto LABEL_35;
    }
    if ( *v25 > 0x40 )
      break;
    *(_QWORD *)(v24 + 24) = *((_QWORD *)v25 + 2);
    *(_DWORD *)(v24 + 16) = *v25;
    if ( v20 )
    {
      v44 = 0;
      v26 = *v25;
      if ( *v25 )
      {
        do
        {
          v23 = *(_QWORD *)(*((_QWORD *)v25 + 1) + 8LL * v8);
          v52[v8++] = *(_DWORD *)(v23 + 8);
          v26 = *v25;
        }
        while ( v8 < *v25 );
      }
      *(_DWORD *)(v10 + 4) = v26;
    }
    if ( (*(_BYTE *)(v10 + 24) & 0x40) != 0 )
      goto LABEL_32;
    v42 = 0;
    v43 = 0;
    v27 = NDXGI::CDevice::HandleMPOSyncIntervalOverride(
            (struct ID3D11Device *)v23,
            &v42,
            &v43,
            (struct _D3DKMT_MULTIPLANE_OVERLAY3 *)v24,
            (struct DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *)v25);
    LODWORD(v45) = v27;
    if ( v27 < 0 )
    {
      v29 = *((_QWORD *)this + 9);
      if ( *(_BYTE *)(v29 + 1112) > 9u
        || *(_BYTE *)(v29 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v29 + 1232) + 96LL) + 912LL)) >= 4u )
      {
        NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v11, v46);
      }
      return (unsigned int)v27;
    }
    v6 = v47;
    if ( v42 )
    {
      if ( v43 )
      {
        v28 = 1;
        v40 = 1;
        v21 = v41;
        v20 = v44;
        goto LABEL_35;
      }
      v21 = 1;
      v41 = 1;
LABEL_32:
      v28 = v40;
      v20 = v44;
      goto LABEL_35;
    }
    v28 = v40;
    v21 = v41;
    v20 = v44;
LABEL_35:
    *(_DWORD *)(v24 + 32) = v25[6];
    *(_QWORD *)(v24 + 40) = *((_QWORD *)v25 + 4);
    if ( ++v22 >= *(_DWORD *)(v10 + 28) )
    {
      if ( v28 )
      {
        *(_DWORD *)(v10 + 24) |= 0x200u;
      }
      else if ( v21 )
      {
        *(_DWORD *)(v10 + 24) &= ~0x200u;
      }
      v4 = v46;
      goto LABEL_52;
    }
    v8 = 0;
  }
  v30 = *((_QWORD *)this + 9);
  if ( *(_BYTE *)(v30 + 1112) > 9u
    || *(_BYTE *)(v30 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 1232) + 96LL) + 912LL)) >= 4u )
  {
    NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v11, v46);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18005d440  push    rbx
0x18005d442  push    rsi
0x18005d443  push    rdi
0x18005d444  push    r12
0x18005d446  push    r13
0x18005d448  push    r14
0x18005d44a  push    r15
0x18005d44c  sub     rsp, 1C0h
0x18005d453  mov     rax, cs:__security_cookie
0x18005d45a  xor     rax, rsp
0x18005d45d  mov     [rsp+1F8h+var_48], rax
0x18005d465  mov     r14, r9
0x18005d468  mov     [rsp+1F8h+var_1B8], r9
0x18005d46d  mov     ebx, r8d
0x18005d470  mov     r10, rdx
0x18005d473  mov     [rsp+1F8h+var_1B0], rdx
0x18005d478  mov     r13, rcx
0x18005d47b  xor     r8d, r8d
0x18005d47e  mov     [rsp+1F8h+var_1C0], r8
0x18005d483  mov     [rsp+1F8h+var_1A8], rcx
0x18005d488  mov     [rsp+1F8h+var_1A0], r9
0x18005d48d  mov     rdx, [rcx+48h]
0x18005d491  cmp     byte ptr [rdx+458h], 9
0x18005d498  ja      short loc_18005D4C3
0x18005d49a  jnz     short loc_18005D4B7
0x18005d49c  mov     rax, [rdx+4D0h]
0x18005d4a3  mov     rcx, [rax+60h]
0x18005d4a7  mov     eax, [rcx+390h]
0x18005d4ad  shr     rax, 10h
0x18005d4b1  cmp     ax, 4
0x18005d4b5  jnb     short loc_18005D4C3
0x18005d4b7  mov     rsi, r14
0x18005d4ba  lea     rdi, [r13+780h]
0x18005d4c1  jmp     short loc_18005D53E
0x18005d4c3  lea     rdi, [r13+780h]
0x18005d4ca  mov     [rsp+1F8h+var_198], rdi
0x18005d4cf  mov     rcx, rdi; lpCriticalSection
0x18005d4d2  call    cs:__imp_EnterCriticalSection
0x18005d4d8  nop
0x18005d4d9  mov     rdx, [rdi+28h]
0x18005d4dd  mov     rax, [rdx+8]
0x18005d4e1  xor     ecx, ecx
0x18005d4e3  mov     [rsp+1F8h+var_15C], ecx
0x18005d4ea  mov     rcx, rdx
0x18005d4ed  cmp     byte ptr [rax+19h], 0
0x18005d4f1  jnz     short loc_18005D50B
0x18005d4f3  cmp     [rax+20h], r14
0x18005d4f7  jnb     short loc_18005D4FF
0x18005d4f9  add     rax, 10h
0x18005d4fd  jmp     short loc_18005D502
0x18005d4ff  mov     rcx, rax
0x18005d502  mov     rax, [rax]
0x18005d505  cmp     byte ptr [rax+19h], 0
0x18005d509  jz      short loc_18005D4F3
0x18005d50b  cmp     byte ptr [rcx+19h], 0
0x18005d50f  jnz     loc_18005D984
0x18005d515  cmp     r14, [rcx+20h]
0x18005d519  jb      loc_18005D984
0x18005d51f  cmp     rcx, rdx
0x18005d522  jz      loc_18005D984
0x18005d528  mov     rsi, [rcx+28h]
0x18005d52c  mov     rcx, rdi; lpCriticalSection
0x18005d52f  call    cs:__imp_LeaveCriticalSection
0x18005d535  nop
0x18005d536  mov     r10, [rsp+1F8h+var_1B0]
0x18005d53b  xor     r8d, r8d
0x18005d53e  mov     eax, [rsi+1Ch]
0x18005d541  cmp     ebx, eax
0x18005d543  jz      short loc_18005D58C
0x18005d545  mov     rcx, [r13+48h]
0x18005d549  cmp     byte ptr [rcx+458h], 9
0x18005d550  ja      short loc_18005D577
0x18005d552  jnz     loc_18005D760
0x18005d558  mov     rax, [rcx+4D0h]
0x18005d55f  mov     rcx, [rax+60h]
0x18005d563  mov     eax, [rcx+390h]
0x18005d569  shr     rax, 10h
0x18005d56d  cmp     ax, 4
0x18005d571  jb      loc_18005D760
0x18005d577  mov     rdx, r14
0x18005d57a  mov     rcx, rdi
0x18005d57d  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x18005d582  mov     eax, 80070057h
0x18005d587  jmp     loc_18005D961
0x18005d58c  lea     rcx, [rsp+1F8h+var_148]
0x18005d594  mov     [rsi+8], rcx
0x18005d598  mov     [rsi+4], r8d
0x18005d59c  mov     dl, 1
0x18005d59e  mov     [rsp+1F8h+var_1C4], dl
0x18005d5a2  mov     [rsp+1F8h+var_1C8], 0
0x18005d5a7  xor     r9b, r9b
0x18005d5aa  mov     [rsp+1F8h+var_1C7], r9b
0x18005d5af  mov     r12d, r8d
0x18005d5b2  test    eax, eax
0x18005d5b4  jz      loc_18005D789
0x18005d5ba  nop     word ptr [rax+rax+00h]
0x18005d5c0  mov     eax, r12d
0x18005d5c3  lea     rcx, ds:0[rax*8]
0x18005d5cb  mov     rax, [rsi+20h]
0x18005d5cf  mov     r15, [rcx+rax]
0x18005d5d3  mov     rbx, [r10+rcx]
0x18005d5d7  test    byte ptr [r15+4], 1
0x18005d5dc  jz      loc_18005D6B8
0x18005d5e2  cmp     dword ptr [rbx], 40h ; '@'
0x18005d5e5  ja      loc_18005D729
0x18005d5eb  mov     rax, [rbx+10h]
0x18005d5ef  mov     [r15+18h], rax
0x18005d5f3  mov     eax, [rbx]
0x18005d5f5  mov     [r15+10h], eax
0x18005d5f9  test    dl, dl
0x18005d5fb  jz      short loc_18005D632
0x18005d5fd  mov     [rsp+1F8h+var_1C4], 0
0x18005d602  mov     eax, [rbx]
0x18005d604  test    eax, eax
0x18005d606  jz      short loc_18005D62F
0x18005d608  nop     dword ptr [rax+rax+00000000h]
0x18005d610  mov     edx, r8d
0x18005d613  mov     rax, [rbx+8]
0x18005d617  mov     rcx, [rax+rdx*8]; struct ID3D11Device *
0x18005d61b  mov     eax, [rcx+8]
0x18005d61e  mov     [rsp+rdx*4+1F8h+var_148], eax
0x18005d625  inc     r8d
0x18005d628  mov     eax, [rbx]
0x18005d62a  cmp     r8d, eax
0x18005d62d  jb      short loc_18005D610
0x18005d62f  mov     [rsi+4], eax
0x18005d632  test    byte ptr [rsi+18h], 40h
0x18005d636  jnz     short loc_18005D698
0x18005d638  mov     [rsp+1F8h+var_1C6], 0
0x18005d63d  mov     [rsp+1F8h+var_1C5], 0
0x18005d642  mov     [rsp+1F8h+var_1D8], rbx; struct DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *
0x18005d647  mov     r9, r15; struct _D3DKMT_MULTIPLANE_OVERLAY3 *
0x18005d64a  lea     r8, [rsp+1F8h+var_1C5]; bool *
0x18005d64f  lea     rdx, [rsp+1F8h+var_1C6]; bool *
0x18005d654  call    ?HandleMPOSyncIntervalOverride@CDevice@NDXGI@@KAJPEAUID3D11Device@@PEA_N1PEAU_D3DKMT_MULTIPLANE_OVERLAY3@@PEAUDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO@@@Z; NDXGI::CDevice::HandleMPOSyncIntervalOverride(ID3D11Device *,bool *,bool *,_D3DKMT_MULTIPLANE_OVERLAY3 *,DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO *)
0x18005d659  mov     r14d, eax
0x18005d65c  mov     dword ptr [rsp+1F8h+var_1C0], eax
0x18005d660  test    eax, eax
0x18005d662  js      loc_18005D6EA
0x18005d668  mov     r10, [rsp+1F8h+var_1B0]
0x18005d66d  cmp     [rsp+1F8h+var_1C6], 0
0x18005d672  jz      short loc_18005D6A5
0x18005d674  cmp     [rsp+1F8h+var_1C5], 0
0x18005d679  jz      short loc_18005D690
0x18005d67b  mov     r8b, 1
0x18005d67e  mov     [rsp+1F8h+var_1C8], r8b
0x18005d683  movzx   r9d, [rsp+1F8h+var_1C7]
0x18005d689  movzx   edx, [rsp+1F8h+var_1C4]
0x18005d68e  jmp     short loc_18005D6C6
0x18005d690  mov     r9b, 1
0x18005d693  mov     [rsp+1F8h+var_1C7], r9b
0x18005d698  movzx   r8d, [rsp+1F8h+var_1C8]
0x18005d69e  movzx   edx, [rsp+1F8h+var_1C4]
0x18005d6a3  jmp     short loc_18005D6C6
0x18005d6a5  movzx   r8d, [rsp+1F8h+var_1C8]
0x18005d6ab  movzx   r9d, [rsp+1F8h+var_1C7]
0x18005d6b1  movzx   edx, [rsp+1F8h+var_1C4]
0x18005d6b6  jmp     short loc_18005D6C6
0x18005d6b8  mov     [r15+18h], r8
0x18005d6bc  mov     [r15+10h], r8d
0x18005d6c0  movzx   r8d, [rsp+1F8h+var_1C8]
0x18005d6c6  mov     eax, [rbx+18h]
0x18005d6c9  mov     [r15+20h], eax
0x18005d6cd  mov     rax, [rbx+20h]
0x18005d6d1  mov     [r15+28h], rax
0x18005d6d5  inc     r12d
0x18005d6d8  cmp     r12d, [rsi+1Ch]
0x18005d6dc  jnb     loc_18005D76A
0x18005d6e2  xor     r8d, r8d
0x18005d6e5  jmp     loc_18005D5C0
0x18005d6ea  mov     rcx, [r13+48h]
0x18005d6ee  cmp     byte ptr [rcx+458h], 9
0x18005d6f5  ja      short loc_18005D714
0x18005d6f7  jnz     short loc_18005D721
0x18005d6f9  mov     rax, [rcx+4D0h]
0x18005d700  mov     rcx, [rax+60h]
0x18005d704  mov     eax, [rcx+390h]
0x18005d70a  shr     rax, 10h
0x18005d70e  cmp     ax, 4
0x18005d712  jb      short loc_18005D721
0x18005d714  mov     rdx, [rsp+1F8h+var_1B8]
0x18005d719  mov     rcx, rdi
0x18005d71c  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x18005d721  mov     eax, r14d
0x18005d724  jmp     loc_18005D961
0x18005d729  mov     rcx, [r13+48h]
0x18005d72d  cmp     byte ptr [rcx+458h], 9
0x18005d734  ja      short loc_18005D753
0x18005d736  jnz     short loc_18005D760
0x18005d738  mov     rax, [rcx+4D0h]
0x18005d73f  mov     rcx, [rax+60h]
0x18005d743  mov     eax, [rcx+390h]
0x18005d749  shr     rax, 10h
0x18005d74d  cmp     ax, 4
0x18005d751  jb      short loc_18005D760
0x18005d753  mov     rdx, [rsp+1F8h+var_1B8]
0x18005d758  mov     rcx, rdi
0x18005d75b  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x18005d760  mov     eax, 80070057h
0x18005d765  jmp     loc_18005D961
0x18005d76a  test    r8b, r8b
0x18005d76d  jz      short loc_18005D778
0x18005d76f  or      dword ptr [rsi+18h], 200h
0x18005d776  jmp     short loc_18005D784
0x18005d778  test    r9b, r9b
0x18005d77b  jz      short loc_18005D784
0x18005d77d  and     dword ptr [rsi+18h], 0FFFFFDFFh
0x18005d784  mov     r14, [rsp+1F8h+var_1B8]
0x18005d789  cmp     dword ptr [rsi+4], 0
0x18005d78d  jnz     short loc_18005D7AA
0x18005d78f  mov     dword ptr [rsi+4], 1
0x18005d796  mov     rax, [r10]
0x18005d799  mov     rcx, [rax+8]
0x18005d79d  mov     rax, [rcx]
0x18005d7a0  mov     ecx, [rax+8]
0x18005d7a3  mov     [rsp+1F8h+var_148], ecx
0x18005d7aa  mov     r8, rsi
0x18005d7ad  lea     rdx, aPresentmultipl_0; "PresentMultiplaneOverlay3"
0x18005d7b4  mov     rcx, cs:__imp_D3DKMTPresentMultiPlaneOverlay3
0x18005d7bb  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEBDPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),char const *,_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *)
0x18005d7c0  mov     edx, eax; int
0x18005d7c2  mov     dword ptr [rsp+1F8h+var_1C0+4], eax
0x18005d7c6  cmp     eax, 0C01E000Bh
0x18005d7cb  jg      short loc_18005D7F5
0x18005d7cd  jz      short loc_18005D7F1
0x18005d7cf  add     eax, 3FE1FFFBh
0x18005d7d4  cmp     eax, 2
0x18005d7d7  jbe     short loc_18005D82F
0x18005d7d9  cmp     edx, 0C01E0000h
0x18005d7df  jz      short loc_18005D82F
0x18005d7e1  mov     rcx, r13; this
0x18005d7e4  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18005d7e9  mov     esi, eax
0x18005d7eb  mov     dword ptr [rsp+1F8h+var_1C0], eax
0x18005d7ef  jmp     short loc_18005D847
0x18005d7f1  xor     esi, esi
0x18005d7f3  jmp     short loc_18005D843
0x18005d7f5  cmp     edx, 0C01E000Dh
0x18005d7fb  jz      short loc_18005D827
0x18005d7fd  add     eax, 3FE1FFE8h
0x18005d802  cmp     eax, 1
0x18005d805  jbe     short loc_18005D82F
0x18005d807  cmp     edx, 0C01E0342h
0x18005d80d  jz      short loc_18005D82F
0x18005d80f  cmp     edx, 103h
0x18005d815  jz      short loc_18005D7F1
0x18005d817  mov     rcx, r13; this
0x18005d81a  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18005d81f  mov     esi, eax
0x18005d821  mov     dword ptr [rsp+1F8h+var_1C0], eax
0x18005d825  jmp     short loc_18005D847
0x18005d827  mov     dword ptr [rsp+1F8h+var_1C0+4], 0
0x18005d82f  mov     eax, [r13+4E0h]
0x18005d836  shr     eax, 1Fh
0x18005d839  neg     al
0x18005d83b  sbb     esi, esi
0x18005d83d  and     esi, 88760870h
0x18005d843  mov     dword ptr [rsp+1F8h+var_1C0], esi
0x18005d847  cmp     byte ptr [r13+382h], 0
0x18005d84f  jz      short loc_18005D86E
0x18005d851  mov     rcx, [r13+580h]
0x18005d858  test    rcx, rcx
0x18005d85b  jz      loc_18005D8F7
0x18005d861  mov     rax, [rsp+1F8h+var_1C0]
0x18005d866  mov     [rcx], rax
0x18005d869  jmp     loc_18005D8F7
0x18005d86e  lea     rbx, [r13+538h]
0x18005d875  mov     rcx, rbx; SRWLock
0x18005d878  call    cs:__imp_AcquireSRWLockShared
0x18005d87e  call    cs:__imp_GetCurrentThreadId
0x18005d884  mov     r10d, eax
0x18005d887  mov     dword ptr [rsp+1F8h+var_1B8], eax
0x18005d88b  lea     rcx, [rsp+1F8h+var_1B8]
0x18005d890  call    ??$_Hash_representation@K@std@@YA_KAEBK@Z; std::_Hash_representation<ulong>(ulong const &)
0x18005d895  and     rax, [r13+570h]
0x18005d89c  shl     rax, 4
0x18005d8a0  add     rax, [r13+558h]
0x18005d8a7  mov     rcx, [rax+8]
0x18005d8ab  mov     rdx, [r13+548h]
0x18005d8b2  cmp     rcx, rdx
0x18005d8b5  jz      short loc_18005D8D1
0x18005d8b7  mov     rax, [rax]
0x18005d8ba  nop     word ptr [rax+rax+00h]
0x18005d8c0  cmp     r10d, [rcx+10h]
0x18005d8c4  jz      short loc_18005D8D3
0x18005d8c6  cmp     rcx, rax
0x18005d8c9  jz      short loc_18005D8D1
0x18005d8cb  mov     rcx, [rcx+8]
0x18005d8cf  jmp     short loc_18005D8C0
0x18005d8d1  xor     ecx, ecx
0x18005d8d3  test    rcx, rcx
0x18005d8d6  jz      short loc_18005D8E9
0x18005d8d8  cmp     rcx, rdx
0x18005d8db  jz      short loc_18005D8E9
0x18005d8dd  mov     rcx, [rcx+18h]
0x18005d8e1  mov     rax, [rsp+1F8h+var_1C0]
0x18005d8e6  mov     [rcx], rax
0x18005d8e9  test    rbx, rbx
0x18005d8ec  jz      short loc_18005D8F7
0x18005d8ee  mov     rcx, rbx; SRWLock
  ... truncated ...
```
