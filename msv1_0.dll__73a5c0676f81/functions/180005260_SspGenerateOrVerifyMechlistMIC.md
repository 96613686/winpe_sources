# SspGenerateOrVerifyMechlistMIC

- ea: `0x180005260`
- end: `0x180005d25`
- name: `SspGenerateOrVerifyMechlistMIC`
- size: `2757`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014dc0`
- `0x180025ff0`

## callees

- `0x1800038e0`
- `0x180004630`
- `0x180005020`
- `0x180005260`
- `0x180005d30`
- `0x1800069d0`
- `0x18002ed58`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18004aca4`
- `0x18004c608`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d5`
- `ntdll!RtlReleaseResource` at `0x180005609`
- `ntdll!RtlReleaseResource` at `0x18000573c`
- `ntdll!RtlReleaseResource` at `0x180005609`
- `ntdll!RtlReleaseResource` at `0x18000573c`
- `ntdll!RtlAcquireResourceShared` at `0x1800055d0`
- `ntdll!RtlAcquireResourceShared` at `0x1800056fe`
- `ntdll!RtlAcquireResourceShared` at `0x1800055d0`
- `ntdll!RtlAcquireResourceShared` at `0x1800056fe`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800059a9`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800059a9`
- `SspiCli!FreeContextBuffer` at `0x1800059bd`
- `SspiCli!FreeContextBuffer` at `0x1800059bd`

## pseudocode

```c
__int64 __fastcall SspGenerateOrVerifyMechlistMIC(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  int inited; // edi
  unsigned int *v9; // r15
  __int64 v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  _DWORD *v14; // r14
  unsigned int i; // ebx
  int v16; // eax
  _DWORD *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rbx
  void *v20; // rax
  __int64 v21; // r12
  __int64 v22; // rax
  _QWORD *v23; // rcx
  unsigned int v24; // ecx
  unsigned int v25; // ebx
  struct _RTL_RESOURCE *v26; // rdi
  struct _LIST_ENTRY near **v27; // rcx
  struct _LIST_ENTRY near *k; // rax
  struct _NTLM_CLIENT_CONTEXT *v29; // rbx
  int v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // ebx
  struct _RTL_RESOURCE *v33; // r14
  struct _LIST_ENTRY near **v34; // rcx
  struct _LIST_ENTRY near *j; // rax
  struct _LIST_ENTRY near *v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rbx
  int v40; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  char v44; // [rsp+30h] [rbp-79h]
  __int64 v45; // [rsp+38h] [rbp-71h] BYREF
  int v46; // [rsp+40h] [rbp-69h] BYREF
  __int64 v47; // [rsp+48h] [rbp-61h] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+50h] [rbp-59h] BYREF
  int v49; // [rsp+58h] [rbp-51h] BYREF
  int v50; // [rsp+5Ch] [rbp-4Dh]
  __int64 v51; // [rsp+60h] [rbp-49h]
  int v52; // [rsp+68h] [rbp-41h]
  int v53; // [rsp+6Ch] [rbp-3Dh]
  __int64 v54; // [rsp+70h] [rbp-39h]
  __int128 v55; // [rsp+78h] [rbp-31h] BYREF
  _BYTE *v56; // [rsp+88h] [rbp-21h]
  __int128 v57; // [rsp+90h] [rbp-19h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-9h] BYREF

  v46 = a3;
  inited = 0;
  v56 = a6;
  v47 = 0;
  *a6 = 0;
  v9 = a2;
  v45 = 0;
  v10 = 0;
  ppPackageInfo = 0;
  v55 = 0;
  v44 = 0;
  v11 = 0;
  v57 = 0;
  while ( v11 < *(_DWORD *)(a4 + 4) )
  {
    v12 = *(_QWORD *)(a4 + 8) + 16LL * v11;
    v13 = *(_DWORD *)(v12 + 4) & 0xFFFFFFF;
    switch ( v13 )
    {
      case 11:
        v47 = *(_QWORD *)(a4 + 8) + 16LL * v11;
LABEL_5:
        inited = ((__int64 (__fastcall *)(__int64, __int64))LsaFunctions->MapBuffer)(v12, v12);
        break;
      case 12:
        v10 = *(_QWORD *)(a4 + 8) + 16LL * v11;
        goto LABEL_5;
      case 2:
        ppPackageInfo = (PSecPkgInfoW)(*(_QWORD *)(a4 + 8) + 16LL * v11);
        goto LABEL_5;
    }
    if ( inited < 0 )
      goto LABEL_80;
    ++v11;
  }
  v14 = 0;
  for ( i = 0; i < *(_DWORD *)(a5 + 4); ++i )
  {
    a3 = *(_QWORD *)(a5 + 8) + 16LL * i;
    v16 = *(_DWORD *)(a3 + 4) & 0xFFFFFFF;
    if ( v16 == 12 )
    {
      v45 = *(_QWORD *)(a5 + 8) + 16LL * i;
      inited = ((__int64 (__fastcall *)(__int64, __int64))LsaFunctions->MapBuffer)(v45, v45);
      if ( inited < 0 )
        goto LABEL_80;
    }
    else if ( v16 == 2 )
    {
      v14 = (_DWORD *)(*(_QWORD *)(a5 + 8) + 16LL * i);
    }
  }
  if ( v10 && *(_DWORD *)v10 > 0x10u )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
      v17 = WPP_GLOBAL_Control;
    }
    v18 = 0;
    v10 = 0;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    v18 = 0;
  }
  if ( !v46 || (a2 = (unsigned int *)*(unsigned int *)(a1 + 72), (unsigned int)((_DWORD)a2 - 3) <= 1) )
  {
    if ( v10 )
    {
      a3 = v45;
    }
    else
    {
      if ( (*(_BYTE *)(a1 + 288) & 1) == 0 )
      {
        if ( v17 == (_DWORD *)&WPP_GLOBAL_Control || (v17[7] & 0x20000) == 0 )
          goto LABEL_120;
        v42 = 141;
        goto LABEL_126;
      }
      a3 = v45;
      if ( !v45 )
      {
        if ( v17 == (_DWORD *)&WPP_GLOBAL_Control || (v17[7] & 0x20000) == 0 )
          goto LABEL_120;
        v42 = 142;
        goto LABEL_126;
      }
    }
    v19 = v47;
    if ( !v47 )
    {
      if ( v17 == (_DWORD *)&WPP_GLOBAL_Control || (v17[7] & 1) == 0 )
        goto LABEL_97;
      WPP_SF_(*((_QWORD *)v17 + 2), 143, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
      inited = -2146893048;
      goto LABEL_80;
    }
    if ( ppPackageInfo && ppPackageInfo->fCapabilities && v14 && !*v14 && !v10 && !a3 )
    {
      if ( v17 != (_DWORD *)&WPP_GLOBAL_Control && (v17[7] & 0x20000) != 0 )
      {
        WPP_SF_q(*((_QWORD *)v17 + 2), 144, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
        v21 = v45;
LABEL_73:
        v18 = 0;
LABEL_74:
        v38 = *(_QWORD *)(a1 + 80);
        if ( !v38 )
        {
LABEL_79:
          *v56 = 1;
          goto LABEL_84;
        }
        v39 = *((_QWORD *)v9 + 1);
        v45 = 0;
        if ( !v39 )
        {
LABEL_78:
          CloseHandle(*(HANDLE *)(a1 + 80));
          *(_QWORD *)(a1 + 80) = 0;
          goto LABEL_79;
        }
        v40 = ((__int64 (__fastcall *)(__int64, __int64 *, __int64, _QWORD))LsaFunctions->DuplicateTokenHandle)(
                v38,
                &v45,
                a3,
                0);
        inited = v40;
        if ( v40 >= 0 )
        {
          *(_DWORD *)(v39 + 8) = v45;
          goto LABEL_78;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            149,
            WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
            (unsigned int)v40);
          v17 = WPP_GLOBAL_Control;
          v18 = 0;
          goto LABEL_82;
        }
LABEL_112:
        v18 = 0;
        goto LABEL_82;
      }
LABEL_121:
      v21 = v45;
      goto LABEL_74;
    }
    if ( !dword_180089CF0 )
    {
      ppPackageInfo = 0;
      inited = QuerySecurityPackageInfoW((LPWSTR)L"NTLM", &ppPackageInfo);
      if ( inited < 0 )
        goto LABEL_80;
      FreeContextBuffer(ppPackageInfo);
      v17 = WPP_GLOBAL_Control;
      v18 = 0;
      dword_180089CF0 = 1;
    }
    if ( (*(_BYTE *)(a1 + 48) & 0x30) != 0 )
    {
      v20 = (void *)((__int64 (__fastcall *)(_QWORD, unsigned int *, __int64, _QWORD))LsaFunctions->AllocateLsaHeap)(
                      *v9,
                      a2,
                      a3,
                      0);
      *((_QWORD *)&v57 + 1) = v20;
      if ( v20 )
      {
        memcpy_0(v20, *((const void **)v9 + 1), *v9);
        *(_QWORD *)&v57 = *(_QWORD *)v9;
        inited = SpInitUserModeContext((struct _LIST_ENTRY *)a1, (__int64)&v57);
        if ( inited >= 0 )
        {
          v44 = 1;
          if ( !v10 )
            goto LABEL_33;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
          }
          *(_QWORD *)&v55 = 0x200000000LL;
          *((_QWORD *)&v55 + 1) = &v49;
          v49 = *(_DWORD *)v47;
          v50 = *(_DWORD *)(v47 + 4);
          v51 = *(_QWORD *)(v47 + 8);
          v52 = *(_DWORD *)v10;
          v53 = *(_DWORD *)(v10 + 4);
          v54 = *(_QWORD *)(v10 + 8);
          v50 = 1;
          v53 = 2;
          inited = SpVerifySignature(a1, &v55, 0, &v46);
          if ( inited >= 0 )
          {
            *(_DWORD *)(a1 + 288) |= 2u;
LABEL_33:
            v21 = v45;
            if ( !v45 )
            {
LABEL_58:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
              }
              v31 = ((unsigned int)a1 >> 4) + WORD1(a1) + BYTE3(a1) + a1 + ((unsigned int)a1 >> 8);
              v32 = (unsigned __int8)(v31 + (v31 >> 4));
              v33 = (struct _RTL_RESOURCE *)&(&NtLmUserContextLock)[12 * (v32 & (NtLmUserContextLockCount - 1))];
              RtlAcquireResourceShared(v33, 1u);
              v34 = &(&NtLmUserContextList)[2 * v32];
              for ( j = *v34; ; j = j->Flink )
              {
                v36 = 0;
                if ( j == (struct _LIST_ENTRY near *)v34 )
                  break;
                v36 = j;
                if ( j[2].Blink == (struct _LIST_ENTRY *)a1 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)&j[10].Blink);
                  break;
                }
              }
              RtlReleaseResource(v33);
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                WPP_SF_qq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
                  a1,
                  v36);
                v17 = WPP_GLOBAL_Control;
              }
              if ( v36 )
              {
                v37 = *((_QWORD *)v9 + 1);
                if ( v37 )
                {
                  *(_DWORD *)(v37 + 12) = v36[7].Blink;
                  *(_DWORD *)(v37 + 16) = HIDWORD(v36[7].Blink);
                }
                DereferenceUserContext((struct _NTLM_CLIENT_CONTEXT *)v36);
                v17 = WPP_GLOBAL_Control;
              }
              if ( (*(_BYTE *)(a1 + 288) & 2) == 0 )
              {
                inited = 590610;
                v18 = 0;
                goto LABEL_82;
              }
              goto LABEL_73;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
            {
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
            }
            v22 = ((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(16);
            *(_QWORD *)(v45 + 8) = v22;
            if ( !v22 )
            {
              v17 = WPP_GLOBAL_Control;
              inited = -1073741801;
              goto LABEL_112;
            }
            *(_DWORD *)v21 = 16;
            *((_QWORD *)&v55 + 1) = &v49;
            *(_QWORD *)&v55 = 0x200000000LL;
            v49 = *(_DWORD *)v19;
            v50 = *(_DWORD *)(v19 + 4);
            v51 = *(_QWORD *)(v19 + 8);
            v52 = *(_DWORD *)v21;
            v53 = *(_DWORD *)(v21 + 4);
            v54 = *(_QWORD *)(v21 + 8);
            v50 = 1;
            v53 = 2;
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
              v23 = WPP_GLOBAL_Control;
            }
            v47 = 0;
            v58 = 0;
            if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x200) != 0 )
              WPP_SF_q(v23[2], 10, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
            v24 = ((unsigned int)a1 >> 4) + WORD1(a1) + BYTE3(a1) + a1 + ((unsigned int)a1 >> 8);
            v25 = (unsigned __int8)(v24 + (v24 >> 4));
            v26 = (struct _RTL_RESOURCE *)&(&NtLmUserContextLock)[12 * (v25 & (NtLmUserContextLockCount - 1))];
            RtlAcquireResourceShared(v26, 1u);
            v27 = &(&NtLmUserContextList)[2 * v25];
            for ( k = *v27; ; k = k->Flink )
            {
              v29 = 0;
              if ( k == (struct _LIST_ENTRY near *)v27 )
                break;
              v29 = (struct _NTLM_CLIENT_CONTEXT *)k;
              if ( k[2].Blink == (struct _LIST_ENTRY *)a1 )
              {
                _InterlockedIncrement((volatile signed __int32 *)&k[10].Blink);
                break;
              }
            }
            RtlReleaseResource(v26);
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              WPP_SF_qq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                12,
                WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
                a1,
                v29);
              v17 = WPP_GLOBAL_Control;
            }
            if ( v29 )
            {
              v30 = SspSignSealHelper((__int64)v29, 0, (__int64)&v55, 0, &v58, &v47);
              inited = v30;
              if ( v30 < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    58,
                    WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
                    (unsigned int)v30);
                }
                DereferenceUserContext(v29);
              }
              else
              {
                *(_OWORD *)v47 = v58;
                inited = DereferenceUserContext(v29);
              }
            }
            else
            {
              inited = -1073741816;
              if ( v17 == (_DWORD *)&WPP_GLOBAL_Control )
              {
LABEL_56:
                v21 = v45;
                if ( inited < 0 )
                  goto LABEL_112;
                *(_DWORD *)v45 = v52;
                goto LABEL_58;
              }
              if ( (v17[7] & 1) == 0 )
              {
LABEL_55:
                if ( v17 != (_DWORD *)&WPP_GLOBAL_Control && (v17[7] & 0x100) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)v17 + 2),
                    59,
                    WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
                    (unsigned int)inited);
                  v17 = WPP_GLOBAL_Control;
                }
                goto LABEL_56;
              }
              WPP_SF_(*((_QWORD *)v17 + 2), 57, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
            }
            v17 = WPP_GLOBAL_Control;
            goto LABEL_55;
          }
        }
      }
      else
      {
        inited = -1073741801;
      }
LABEL_80:
      v17 = WPP_GLOBAL_Control;
      v18 = 0;
      goto LABEL_81;
    }
    if ( v17 == (_DWORD *)&WPP_GLOBAL_Control || (v17[7] & 0x20000) == 0 )
    {
LABEL_120:
      inited = 0;
      goto LABEL_121;
    }
    v42 = 145;
LABEL_126:
    WPP_SF_q(*((_QWORD *)v17 + 2), v42, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
    v18 = 0;
    goto LABEL_120;
  }
  if ( v17 != (_DWORD *)&WPP_GLOBAL_Control && (v17[7] & 1) != 0 )
  {
    WPP_SF_qd(*((_QWORD *)v17 + 2), a2, a3, a1, *(_DWORD *)(a1 + 72));
    v17 = WPP_GLOBAL_Control;
    v18 = 0;
  }
LABEL_97:
  inited = -2146893048;
LABEL_81:
  v21 = v45;
LABEL_82:
  if ( *v56 )
    goto LABEL_85;
  *(_OWORD *)(a1 + 272) = *(_OWORD *)v9;
  *v9 = 0;
  *((_QWORD *)v9 + 1) = 0;
LABEL_84:
  v17 = WPP_GLOBAL_Control;
LABEL_85:
  if ( v44 )
  {
    SpDeleteUserModeContext(a1, a2, a3, v18);
    v17 = WPP_GLOBAL_Control;
  }
  if ( inited < 0 )
  {
    if ( v17 != (_DWORD *)&WPP_GLOBAL_Control && (v17[7] & 1) != 0 )
      WPP_SF_qD(*((_QWORD *)v17 + 2), 148, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1, inited);
    if ( v21 )
    {
      v43 = *(_QWORD *)(v21 + 8);
      if ( v43 )
      {
        ((void (__fastcall *)(__int64, unsigned int *, __int64, __int64))LsaFunctions->FreeLsaHeap)(v43, a2, a3, v18);
        *(_QWORD *)(v21 + 8) = 0;
        *(_DWORD *)v21 = 0;
      }
    }
  }
  if ( *((_QWORD *)&v57 + 1) )
    ((void (__fastcall *)(_QWORD, unsigned int *, __int64, __int64))LsaFunctions->FreeLsaHeap)(
      *((_QWORD *)&v57 + 1),
      a2,
      a3,
      v18);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180005260  mov     [rsp-8+arg_10], rbx
0x180005265  push    rbp
0x180005266  push    rsi
0x180005267  push    rdi
0x180005268  push    r12
0x18000526a  push    r13
0x18000526c  push    r14
0x18000526e  push    r15
0x180005270  lea     rbp, [rsp-17h]
0x180005275  sub     rsp, 0C0h
0x18000527c  mov     rax, cs:__security_cookie
0x180005283  xor     rax, rsp
0x180005286  mov     [rbp+47h+var_40], rax
0x18000528a  mov     r13, [rbp+47h+arg_20]
0x18000528e  mov     rsi, rcx
0x180005291  mov     rcx, [rbp+47h+arg_28]
0x180005295  mov     r14, r9
0x180005298  xor     r9d, r9d
0x18000529b  mov     [rbp+47h+var_B0], r8d
0x18000529f  mov     edi, r9d
0x1800052a2  mov     [rbp+47h+var_68], rcx
0x1800052a6  xorps   xmm0, xmm0
0x1800052a9  mov     [rbp+47h+var_A8], r9
0x1800052ad  xorps   xmm1, xmm1
0x1800052b0  mov     [rcx], dil
0x1800052b3  mov     r15, rdx
0x1800052b6  mov     [rbp+47h+var_B8], r9
0x1800052ba  mov     r12d, r9d
0x1800052bd  mov     [rbp+47h+ppPackageInfo], r9
0x1800052c1  movups  [rbp+47h+var_78], xmm0
0x1800052c5  mov     [rbp+47h+var_C0], dil
0x1800052c9  mov     ebx, r9d
0x1800052cc  movups  [rbp+47h+var_60], xmm1
0x1800052d0  cmp     ebx, [r14+4]
0x1800052d4  jnb     short loc_180005323
0x1800052d6  mov     ecx, ebx
0x1800052d8  shl     rcx, 4
0x1800052dc  add     rcx, [r14+8]
0x1800052e0  mov     eax, [rcx+4]
0x1800052e3  and     eax, 0FFFFFFFh
0x1800052e8  cmp     eax, 0Bh
0x1800052eb  jnz     short loc_180005315
0x1800052ed  mov     [rbp+47h+var_A8], rcx
0x1800052f1  mov     rax, cs:LsaFunctions
0x1800052f8  mov     rdx, rcx
0x1800052fb  mov     rax, [rax+98h]
0x180005302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005307  mov     edi, eax
0x180005309  test    edi, edi
0x18000530b  js      loc_1800057EC
0x180005311  inc     ebx
0x180005313  jmp     short loc_1800052D0
0x180005315  cmp     eax, 0Ch
0x180005318  jnz     loc_180005876
0x18000531e  mov     r12, rcx
0x180005321  jmp     short loc_1800052F1
0x180005323  xor     r14d, r14d
0x180005326  xor     ebx, ebx
0x180005328  cmp     ebx, [r13+4]
0x18000532c  jnb     short loc_180005356
0x18000532e  mov     r8d, ebx
0x180005331  shl     r8, 4
0x180005335  add     r8, [r13+8]
0x180005339  mov     eax, [r8+4]
0x18000533d  and     eax, 0FFFFFFFh
0x180005342  cmp     eax, 0Ch
0x180005345  jz      loc_180005888
0x18000534b  cmp     eax, 2
0x18000534e  cmovz   r14, r8
0x180005352  inc     ebx
0x180005354  jmp     short loc_180005328
0x180005356  lea     r13, WPP_GLOBAL_Control
0x18000535d  test    r12, r12
0x180005360  jnz     loc_1800058D6
0x180005366  mov     rcx, cs:WPP_GLOBAL_Control
0x18000536d  xor     r9d, r9d
0x180005370  cmp     [rbp+47h+var_B0], 0
0x180005374  jnz     loc_1800058B4
0x18000537a  test    r12, r12
0x18000537d  jz      loc_180005A0D
0x180005383  mov     r8, [rbp+47h+var_B8]
0x180005387  mov     rbx, [rbp+47h+var_A8]
0x18000538b  test    rbx, rbx
0x18000538e  jz      loc_180005B68
0x180005394  mov     rax, [rbp+47h+ppPackageInfo]
0x180005398  test    rax, rax
0x18000539b  jnz     loc_18000591D
0x1800053a1  cmp     cs:dword_180089CF0, 0
0x1800053a8  jz      loc_18000599A
0x1800053ae  test    byte ptr [rsi+30h], 30h
0x1800053b2  jz      loc_180005A49
0x1800053b8  mov     rax, cs:LsaFunctions
0x1800053bf  mov     ecx, [r15]
0x1800053c2  mov     rax, [rax+28h]
0x1800053c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cb  mov     qword ptr [rbp+47h+var_60+8], rax
0x1800053cf  test    rax, rax
0x1800053d2  jz      loc_180005B9A
0x1800053d8  mov     r8d, [r15]; Size
0x1800053db  mov     rcx, rax; void *
0x1800053de  mov     rdx, [r15+8]; Src
0x1800053e2  call    memcpy_0
0x1800053e7  mov     eax, [r15]
0x1800053ea  lea     rdx, [rbp+47h+var_60]
0x1800053ee  mov     dword ptr [rbp+47h+var_60], eax
0x1800053f1  mov     rcx, rsi
0x1800053f4  mov     eax, [r15+4]
0x1800053f8  mov     dword ptr [rbp+47h+var_60+4], eax
0x1800053fb  call    SpInitUserModeContext
0x180005400  mov     edi, eax
0x180005402  test    eax, eax
0x180005404  js      loc_1800057F3
0x18000540a  mov     [rbp+47h+var_C0], 1
0x18000540e  test    r12, r12
0x180005411  jz      loc_1800054A3
0x180005417  mov     rcx, cs:WPP_GLOBAL_Control
0x18000541e  cmp     rcx, r13
0x180005421  jz      short loc_180005430
0x180005423  test    dword ptr [rcx+1Ch], 20000h
0x18000542a  jnz     loc_180005BA4
0x180005430  mov     dword ptr [rbp+47h+var_78], 0
0x180005437  lea     rax, [rbp+47h+var_98]
0x18000543b  mov     qword ptr [rbp+47h+var_78+8], rax
0x18000543f  lea     r9, [rbp+47h+var_B0]
0x180005443  mov     dword ptr [rbp+47h+var_78+4], 2
0x18000544a  lea     rdx, [rbp+47h+var_78]
0x18000544e  mov     eax, [rbx]
0x180005450  xor     r8d, r8d
0x180005453  mov     [rbp+47h+var_98], eax
0x180005456  mov     rcx, rsi
0x180005459  mov     eax, [rbx+4]
0x18000545c  mov     [rbp+47h+var_94], eax
0x18000545f  mov     rax, [rbx+8]
0x180005463  mov     [rbp+47h+var_90], rax
0x180005467  mov     eax, [r12]
0x18000546b  mov     [rbp+47h+var_88], eax
0x18000546e  mov     eax, [r12+4]
0x180005473  mov     [rbp+47h+var_84], eax
0x180005476  mov     rax, [r12+8]
0x18000547b  mov     [rbp+47h+var_80], rax
0x18000547f  mov     [rbp+47h+var_94], 1
0x180005486  mov     [rbp+47h+var_84], 2
0x18000548d  call    SpVerifySignature
0x180005492  mov     edi, eax
0x180005494  test    eax, eax
0x180005496  js      loc_1800057F3
0x18000549c  or      dword ptr [rsi+120h], 2
0x1800054a3  mov     r12, [rbp+47h+var_B8]
0x1800054a7  lea     r14, __ImageBase
0x1800054ae  test    r12, r12
0x1800054b1  jz      loc_18000569D
0x1800054b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054be  cmp     rcx, r13
0x1800054c1  jz      short loc_1800054D0
0x1800054c3  test    dword ptr [rcx+1Ch], 20000h
0x1800054ca  jnz     loc_180005BC1
0x1800054d0  mov     rax, cs:LsaFunctions
0x1800054d7  mov     ecx, 10h
0x1800054dc  mov     rax, [rax+28h]
0x1800054e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e5  mov     [r12+8], rax
0x1800054ea  test    rax, rax
0x1800054ed  jz      loc_180005BDE
0x1800054f3  mov     dword ptr [r12], 10h
0x1800054fb  lea     rax, [rbp+47h+var_98]
0x1800054ff  mov     qword ptr [rbp+47h+var_78+8], rax
0x180005503  xor     r14d, r14d
0x180005506  mov     dword ptr [rbp+47h+var_78], r14d
0x18000550a  mov     dword ptr [rbp+47h+var_78+4], 2
0x180005511  mov     eax, [rbx]
0x180005513  mov     [rbp+47h+var_98], eax
0x180005516  mov     eax, [rbx+4]
0x180005519  mov     [rbp+47h+var_94], eax
0x18000551c  mov     rax, [rbx+8]
0x180005520  mov     [rbp+47h+var_90], rax
0x180005524  mov     eax, [r12]
0x180005528  mov     [rbp+47h+var_88], eax
0x18000552b  mov     eax, [r12+4]
0x180005530  mov     [rbp+47h+var_84], eax
0x180005533  mov     rax, [r12+8]
0x180005538  mov     [rbp+47h+var_80], rax
0x18000553c  mov     [rbp+47h+var_94], 1
0x180005543  mov     [rbp+47h+var_84], 2
0x18000554a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005551  cmp     rcx, r13
0x180005554  jz      short loc_180005563
0x180005556  test    dword ptr [rcx+1Ch], 100h
0x18000555d  jnz     loc_180005BEF
0x180005563  xorps   xmm0, xmm0
0x180005566  mov     [rbp+47h+var_A8], r14
0x18000556a  movups  [rbp+47h+var_50], xmm0
0x18000556e  cmp     rcx, r13
0x180005571  jz      short loc_180005580
0x180005573  test    dword ptr [rcx+1Ch], 200h
0x18000557a  jnz     loc_180005C10
0x180005580  mov     edx, esi
0x180005582  lea     r12, __ImageBase
0x180005589  shr     edx, 18h
0x18000558c  lea     rdi, rva ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A[r12]; _RTL_RESOURCE near * NtLmUserContextLock ...
0x180005594  mov     eax, esi
0x180005596  mov     ecx, esi
0x180005598  shr     eax, 10h
0x18000559b  add     edx, eax
0x18000559d  shr     ecx, 8
0x1800055a0  add     ecx, esi
0x1800055a2  mov     eax, esi
0x1800055a4  shr     eax, 4
0x1800055a7  add     ecx, edx
0x1800055a9  add     ecx, eax
0x1800055ab  mov     dl, 1; Wait
0x1800055ad  mov     eax, ecx
0x1800055af  shr     eax, 4
0x1800055b2  add     eax, ecx
0x1800055b4  mov     ecx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x1800055ba  movzx   ebx, al
0x1800055bd  dec     ecx
0x1800055bf  and     rcx, rbx
0x1800055c2  lea     rax, [rcx+rcx*2]
0x1800055c6  shl     rax, 5
0x1800055ca  add     rdi, rax
0x1800055cd  mov     rcx, rdi; Resource
0x1800055d0  call    cs:__imp_RtlAcquireResourceShared
0x1800055d6  mov     eax, ebx
0x1800055d8  lea     rcx, rva ?NtLmUserContextList@@3PAU_LIST_ENTRY@@A[r12]; _LIST_ENTRY near * NtLmUserContextList ...
0x1800055e0  shl     rax, 4
0x1800055e4  add     rcx, rax
0x1800055e7  mov     rax, [rcx]
0x1800055ea  mov     rbx, r14
0x1800055ed  cmp     rax, rcx
0x1800055f0  jz      short loc_180005606
0x1800055f2  mov     rbx, rax
0x1800055f5  cmp     [rax+28h], rsi
0x1800055f9  jnz     loc_180005AF8
0x1800055ff  lock inc dword ptr [rax+0A8h]
0x180005606  mov     rcx, rdi; Resource
0x180005609  call    cs:__imp_RtlReleaseResource
0x18000560f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005616  cmp     rcx, r13
0x180005619  jz      short loc_180005628
0x18000561b  test    dword ptr [rcx+1Ch], 200h
0x180005622  jnz     loc_180005AA6
0x180005628  test    rbx, rbx
0x18000562b  jz      loc_180005A74
0x180005631  lea     rax, [rbp+47h+var_A8]
0x180005635  xor     r9d, r9d
0x180005638  mov     [rsp+0F0h+var_C8], rax
0x18000563d  lea     r8, [rbp+47h+var_78]
0x180005641  lea     rax, [rbp+47h+var_50]
0x180005645  xor     edx, edx
0x180005647  mov     rcx, rbx
0x18000564a  mov     [rsp+0F0h+var_D0], rax
0x18000564f  call    ?SspSignSealHelper@@YAJPEAU_NTLM_CLIENT_CONTEXT@@W4_eSignSealOp@@PEAU_SecBufferDesc@@KPEAU_NTLMSSP_MESSAGE_SIGNATURE@@PEAPEAU4@@Z; SspSignSealHelper(_NTLM_CLIENT_CONTEXT *,_eSignSealOp,_SecBufferDesc *,ulong,_NTLMSSP_MESSAGE_SIGNATURE *,_NTLMSSP_MESSAGE_SIGNATURE * *)
0x180005654  mov     edi, eax
0x180005656  test    eax, eax
0x180005658  js      loc_180005C2D
0x18000565e  mov     rax, [rbp+47h+var_A8]
0x180005662  mov     rcx, rbx; struct _NTLM_CLIENT_CONTEXT *
0x180005665  movups  xmm0, [rbp+47h+var_50]
0x180005669  movups  xmmword ptr [rax], xmm0
0x18000566c  call    ?DereferenceUserContext@@YAJPEAU_NTLM_CLIENT_CONTEXT@@@Z; DereferenceUserContext(_NTLM_CLIENT_CONTEXT *)
0x180005671  mov     edi, eax
0x180005673  mov     rcx, cs:WPP_GLOBAL_Control
0x18000567a  cmp     rcx, r13
0x18000567d  jnz     loc_1800059DC
0x180005683  mov     r12, [rbp+47h+var_B8]
0x180005687  test    edi, edi
0x180005689  js      loc_180005992
0x18000568f  mov     eax, [rbp+47h+var_88]
0x180005692  lea     r14, __ImageBase
0x180005699  mov     [r12], eax
0x18000569d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056a4  cmp     rcx, r13
0x1800056a7  jz      short loc_1800056B6
0x1800056a9  test    dword ptr [rcx+1Ch], 200h
0x1800056b0  jnz     loc_180005C64
0x1800056b6  mov     edx, esi
0x1800056b8  lea     r14, rva ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A[r14]; _RTL_RESOURCE near * NtLmUserContextLock ...
0x1800056bf  shr     edx, 18h
0x1800056c2  mov     eax, esi
0x1800056c4  shr     eax, 10h
0x1800056c7  mov     ecx, esi
0x1800056c9  add     edx, eax
0x1800056cb  shr     ecx, 8
0x1800056ce  add     ecx, esi
0x1800056d0  mov     eax, esi
0x1800056d2  shr     eax, 4
0x1800056d5  add     ecx, edx
0x1800056d7  add     ecx, eax
0x1800056d9  mov     dl, 1; Wait
0x1800056db  mov     eax, ecx
0x1800056dd  shr     eax, 4
0x1800056e0  add     eax, ecx
0x1800056e2  mov     ecx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x1800056e8  movzx   ebx, al
0x1800056eb  dec     ecx
0x1800056ed  and     rcx, rbx
0x1800056f0  lea     rax, [rcx+rcx*2]
0x1800056f4  shl     rax, 5
0x1800056f8  add     r14, rax
0x1800056fb  mov     rcx, r14; Resource
  ... truncated ...
```
