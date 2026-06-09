# LsapIdProvHostLookUpUserInfo(void *,ushort const *,void *,_LSA_IDENTITY_INFO_CLASS,void * *,ulong *)

- ea: `0x180060fa0`
- end: `0x180061c73`
- name: `?LsapIdProvHostLookUpUserInfo@@YAJPEAXPEBG0W4_LSA_IDENTITY_INFO_CLASS@@PEAPEAXPEAK@Z`
- size: `3283`
- prototype: `int __high(void *, const unsigned __int16 *, void *, enum _LSA_IDENTITY_INFO_CLASS, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003c4c`
- `0x18000c300`
- `0x18000dd90`
- `0x18000f808`
- `0x180011278`
- `0x18005fa30`
- `0x18005faf0`
- `0x18005fecc`
- `0x18006064c`
- `0x180060fa0`
- `0x180061c7c`
- `0x180061cb8`
- `0x180063c24`
- `0x1800781fc`
- `0x180078a74`
- `0x1800b1db8`
- `0x1800bbbfc`
- `0x1800bd6e0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800613d7`
- `ntdll!RtlReleaseResource` at `0x1800613d7`
- `ntdll!RtlAcquireResourceShared` at `0x18006108f`
- `ntdll!RtlAcquireResourceShared` at `0x18006108f`
- `ntdll!RtlLengthSid` at `0x1800610c2`
- `ntdll!RtlLengthSid` at `0x180061261`
- `ntdll!RtlLengthSid` at `0x1800610c2`
- `ntdll!RtlLengthSid` at `0x180061261`
- `ntdll!RtlInitUnicodeString` at `0x180061303`
- `ntdll!RtlInitUnicodeString` at `0x180061303`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSidAndAttributesList` at `0x18006144a`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSidAndAttributesList` at `0x18006144a`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x180061418`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x180061418`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetUserLogonInformation2` at `0x1800611cc`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetUserLogonInformation2` at `0x1800611cc`

## string_xrefs

- `0x180061971`: `LsapSamExtRidToSid`

## pseudocode

```c
__int64 __fastcall LsapIdProvHostLookUpUserInfo(
        __int64 a1,
        const WCHAR *a2,
        void *a3,
        int a4,
        struct _RTL_BALANCED_NODE **a5,
        unsigned int *a6)
{
  struct _RTL_BALANCED_NODE **v6; // r13
  int v10; // r12d
  int inited; // ebx
  __int64 v13; // r8
  unsigned int v14; // r13d
  int v15; // r12d
  int v16; // esi
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // r15d
  unsigned int v20; // ebx
  struct _UNICODE_STRING *v21; // rax
  struct _USER_INTERNAL6_INFORMATION *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // r12d
  _DWORD *Buffer; // rsi
  ULONG v26; // eax
  unsigned int Length; // edi
  int v28; // r13d
  int v29; // r8d
  LsaHandleCache *v30; // rcx
  int QualifiedIdentityName; // eax
  char *NoZero; // rbx
  bool v33; // zf
  void *v34; // rdx
  __int64 v35; // r8
  PWSTR v36; // rcx
  struct _USER_INTERNAL6_INFORMATION *v37; // rcx
  LsaHandleCache *v38; // rcx
  int v40; // edx
  LsaHandleCache *v41; // rcx
  int v42; // eax
  char *v43; // r14
  unsigned int v44; // ecx
  char *v45; // rsi
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // edx
  __int64 v49; // rdx
  int v50; // edx
  __int64 v51; // rdx
  __int64 v52; // r9
  _OWORD *v53; // rax
  __int64 v54; // rdx
  const char *v55; // rcx
  const char *v56; // rcx
  int NameForInternetUser; // eax
  __int64 v58; // rax
  struct _USER_INTERNAL6_INFORMATION *v59; // [rsp+68h] [rbp-98h] BYREF
  int v60; // [rsp+70h] [rbp-90h] BYREF
  void *v61; // [rsp+78h] [rbp-88h] BYREF
  int v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+84h] [rbp-7Ch]
  struct _RPC_SID *v64; // [rsp+88h] [rbp-78h] BYREF
  struct _RTL_BALANCED_NODE *v65; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING v66; // [rsp+98h] [rbp-68h] BYREF
  __int128 v67; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING *v68; // [rsp+B8h] [rbp-48h]
  void *v69; // [rsp+C0h] [rbp-40h]
  unsigned int *v70; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING v71; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v73; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v74[6]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a5;
  v70 = a6;
  v65 = 0;
  v61 = 0;
  v59 = 0;
  v10 = 1;
  v60 = 0;
  v64 = 0;
  DestinationString = 0;
  v71 = 0;
  v67 = 0;
  memset(v74, 0, 40);
  v73 = 0;
  v66 = 0;
  CONNECTED_TRACE_ENTER_0("LsapIdProvHostLookUpUserInfo");
  if ( !a1 || !a5 || !a6 )
  {
    inited = -1073741811;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v49 = 10;
      goto LABEL_190;
    }
    goto LABEL_59;
  }
  if ( !a2 && !a3 )
  {
    inited = -1073741811;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v49 = 11;
LABEL_190:
      WPP_SF_d(*((_QWORD *)v41 + 2), v49, &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids, 3221225485LL);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  *a5 = 0;
  *a6 = 0;
  if ( (unsigned int)a4 <= 0xF )
  {
    if ( *(_DWORD *)(a1 + 16) != 1164986707 )
    {
      inited = -1073741811;
      CONNECTED_TRACE_ERROR("LsapRefIdProv", 3221225485LL);
      goto LABEL_59;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
    v65 = (struct _RTL_BALANCED_NODE *)a1;
    if ( !RtlAcquireResourceShared(&g_ConnectedAccountStoreLock, 0) )
    {
      inited = -1073741604;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
          3221225692LL);
      goto LABEL_59;
    }
    inited = LsapLazyInitSamConnection();
    if ( inited < 0 )
    {
      v54 = (unsigned int)inited;
      v55 = "LsapLazyInitSamConnection";
    }
    else
    {
      if ( !a2 )
      {
        *((_QWORD *)&v67 + 1) = a3;
        LOWORD(v67) = RtlLengthSid(a3);
        WORD1(v67) = v67;
        v14 = 128;
        goto LABEL_11;
      }
      RtlInitUnicodeString(&DestinationString, a2);
      QualifiedIdentityName = LsapMakeQualifiedIdentityName(
                                &DestinationString,
                                (struct _UNICODE_STRING *)(a1 + 40),
                                &v71);
      inited = QualifiedIdentityName;
      if ( QualifiedIdentityName >= 0 )
      {
        v14 = 0x4000;
LABEL_11:
        v15 = 0x400000;
        if ( a4 != 5 )
          v15 = 0;
        if ( a4 == 1 || (v16 = 0, a4 == 6) )
          v16 = 0x80000;
        v17 = 1024;
        v18 = 327680;
        v19 = 0x40000;
        if ( a4 != 3 )
          v17 = 0;
        v63 = v17;
        if ( a4 != 11 )
          v18 = 0x40000;
        v62 = v18;
        if ( a4 )
        {
          if ( a4 == 10 )
          {
            v20 = 960;
          }
          else
          {
            v20 = 587202560;
            if ( a4 != 15 )
              v20 = 4;
          }
        }
        else
        {
          v20 = 2;
        }
        v21 = (struct _UNICODE_STRING *)&v67;
        if ( v14 == 0x4000 )
          v21 = &v71;
        v68 = v21;
        v69 = g_hIdProvExtSamAccountDomain;
        if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(&v71, 0, v13) )
        {
          inited = SamIGetUserLogonInformation2(
                     v69,
                     v14,
                     v68,
                     v20,
                     v63 | v62 | (((a4 - 2) & 0xFFFFFFFB) == 0 ? 0x100000 : 0) | v15 | (unsigned int)v16,
                     0,
                     &v59,
                     &v73,
                     &v61);
          if ( inited >= 0 )
          {
            v22 = v59;
            v23 = *((_QWORD *)v59 + 56) - *(_QWORD *)&GUID_NULL.Data1;
            if ( !v23 )
              v23 = *((_QWORD *)v59 + 57) - *(_QWORD *)GUID_NULL.Data4;
            if ( !v23 )
            {
              inited = -1073741724;
              if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
                  3221225572LL);
              }
              goto LABEL_40;
            }
            v24 = 0;
            if ( a4 > 7 )
            {
              if ( a4 != 8 )
              {
                if ( a4 == 10 )
                {
                  Length = 72;
                  Buffer = 0;
                  v50 = *((_DWORD *)v59 + 71);
                  if ( (v50 & 0x200) != 0 )
                    Length = *((unsigned __int16 *)v59 + 64) + 74;
                  if ( (v50 & 0x100) != 0 )
                    Length += *((unsigned __int16 *)v59 + 56) + 2;
                  if ( (v50 & 0x40) != 0 )
                    Length += *((unsigned __int16 *)v59 + 40) + 2;
                  if ( (v50 & 0x80u) != 0 )
                    Length += *((unsigned __int16 *)v59 + 48) + 2;
                  goto LABEL_37;
                }
                if ( a4 == 11 )
                {
                  v24 = 0x10000;
                  goto LABEL_147;
                }
                if ( a4 != 14 )
                {
                  if ( a4 == 15 )
                  {
                    if ( *((_BYTE *)v59 + 313) && *((_WORD *)v59 + 112) == 16 )
                    {
                      v53 = (_OWORD *)*((_QWORD *)v59 + 29);
                      DWORD1(v74[0]) |= 2u;
                      *(_OWORD *)((char *)&v74[1] + 8) = *v53;
                    }
                    Buffer = v74;
                    Length = 40;
                    goto LABEL_37;
                  }
LABEL_149:
                  inited = -1073741637;
LABEL_152:
                  v10 = 1;
                  goto LABEL_41;
                }
                NameForInternetUser = LsapSamExtRidToSid(v61, *((_DWORD *)v59 + 68), &v64);
                inited = NameForInternetUser;
                if ( NameForInternetUser >= 0 )
                {
                  Buffer = v64;
LABEL_36:
                  v26 = RtlLengthSid(Buffer);
                  v22 = v59;
                  Length = v26;
LABEL_37:
                  v28 = 0;
LABEL_38:
                  v29 = *((_DWORD *)v22 + 82);
                  if ( (v19 & v29) != v19 )
                  {
                    inited = -1073741595;
                    v30 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    {
                      goto LABEL_40;
                    }
                    v51 = 16;
                    v52 = v19;
                    goto LABEL_125;
                  }
                  if ( (v24 & *((_DWORD *)v22 + 71)) != v24 )
                  {
                    inited = -1073741595;
                    v30 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    {
                      goto LABEL_40;
                    }
                    v51 = 17;
                    v52 = v24;
LABEL_125:
                    WPP_SF_DDD(
                      *((_QWORD *)v30 + 2),
                      v51,
                      &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
                      v52,
                      v29,
                      -1073741595);
LABEL_40:
                    v10 = 1;
                    goto LABEL_41;
                  }
                  if ( !Length || !Buffer && a4 != 10 )
                  {
                    inited = -1073741275;
                    v10 = 0;
                    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        (unsigned int)WPP_beece53709d13be865c3a44b1735e315_Traceguids,
                        (unsigned int)"LsapIdProvHostLookUpUserInfo: SrcBuffer not found",
                        37);
                    }
                    goto LABEL_41;
                  }
                  if ( inited < 0 )
                  {
                    v10 = 1;
                    goto LABEL_41;
                  }
                  if ( v28 )
                  {
                    if ( (Length & 1) != 0 || (v10 = 1, Length > 0x7FFD) )
                    {
                      inited = -1073741595;
                      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          18,
                          &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
                          3221225701LL);
                      }
                      v10 = 1;
                      goto LABEL_41;
                    }
                  }
                  else
                  {
                    v10 = 1;
                  }
LABEL_53:
                  NoZero = (char *)LsapAllocateNoZero(Length + (unsigned __int64)(v28 != 0 ? 2 : 0));
                  *a5 = (struct _RTL_BALANCED_NODE *)NoZero;
                  if ( NoZero )
                  {
                    if ( a4 == 10 )
                    {
                      *(_DWORD *)NoZero = Length;
                      v43 = NoZero + 72;
                      if ( (*((_DWORD *)v59 + 71) & 0x200) != 0 )
                      {
                        v44 = *((unsigned __int16 *)v59 + 64);
                        *((_WORD *)NoZero + 4) = v44;
                        *((_WORD *)NoZero + 5) = v44 + 2;
                        *((_QWORD *)NoZero + 2) = v43;
                        memcpy_0(NoZero + 72, *((const void **)v59 + 17), v44);
                        *(_WORD *)(*((_QWORD *)NoZero + 2)
                                 + 2 * ((unsigned __int64)*((unsigned __int16 *)NoZero + 4) >> 1)) = 0;
                        v45 = &v43[*((unsigned __int16 *)NoZero + 5)];
                      }
                      else
                      {
                        v45 = NoZero + 72;
                        *(_OWORD *)(NoZero + 8) = 0;
                      }
                      if ( (*((_DWORD *)v59 + 71) & 0x100) != 0 )
                      {
                        v46 = *((unsigned __int16 *)v59 + 56);
                        *((_WORD *)NoZero + 12) = v46;
                        *((_WORD *)NoZero + 13) = v46 + 2;
                        *((_QWORD *)NoZero + 4) = v45;
                        memcpy_0(v45, *((const void **)v59 + 15), v46);
                        *(_WORD *)(*((_QWORD *)NoZero + 4)
                                 + 2 * ((unsigned __int64)*((unsigned __int16 *)NoZero + 12) >> 1)) = 0;
                        v45 += *((unsigned __int16 *)NoZero + 13);
                      }
                      else
                      {
                        *(_OWORD *)(NoZero + 24) = 0;
                      }
                      if ( (*((_BYTE *)v59 + 284) & 0x40) != 0 )
                      {
                        v47 = *((unsigned __int16 *)v59 + 40);
                        *((_WORD *)NoZero + 20) = v47;
                        *((_WORD *)NoZero + 21) = v47 + 2;
                        *((_QWORD *)NoZero + 6) = v45;
                        memcpy_0(v45, *((const void **)v59 + 11), v47);
                        *(_WORD *)(*((_QWORD *)NoZero + 6)
                                 + 2 * ((unsigned __int64)*((unsigned __int16 *)NoZero + 20) >> 1)) = 0;
                        v45 += *((unsigned __int16 *)NoZero + 21);
                      }
                      else
                      {
                        *(_OWORD *)(NoZero + 40) = 0;
                      }
                      if ( *((char *)v59 + 284) >= 0 )
                      {
                        *(_OWORD *)(NoZero + 56) = 0;
                      }
                      else
                      {
                        v48 = *((unsigned __int16 *)v59 + 48);
                        *((_WORD *)NoZero + 28) = v48;
                        *((_WORD *)NoZero + 29) = v48 + 2;
                        *((_QWORD *)NoZero + 8) = v45;
                        memcpy_0(v45, *((const void **)v59 + 13), v48);
                        *(_WORD *)(*((_QWORD *)NoZero + 8)
                                 + 2 * ((unsigned __int64)*((unsigned __int16 *)NoZero + 28) >> 1)) = 0;
                      }
                    }
                    else
                    {
                      memcpy_0(NoZero, Buffer, Length);
                    }
                    v33 = v28 == 0;
                    v6 = a5;
                    if ( !v33 )
                    {
                      v58 = -1;
                      *((_WORD *)(*a5)->Children + ((unsigned __int64)Length >> 1)) = 0;
                      do
                        ++v58;
                      while ( *((_WORD *)(*a5)->Children + v58) );
                      if ( Length != (_DWORD)v58 )
                      {
                        inited = -1073741595;
                        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            20,
                            &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
                            3221225701LL);
                        }
                        goto LABEL_58;
                      }
                      Length += 2;
                    }
                    inited = 0;
                    *v70 = Length;
LABEL_58:
                    RtlReleaseResource(&g_ConnectedAccountStoreLock);
                    goto LABEL_59;
                  }
                  inited = -1073741801;
                  CONNECTED_TRACE_ERROR("LsapAllocate", 3221225495LL);
LABEL_41:
                  v6 = a5;
                  goto LABEL_58;
                }
                v56 = "LsapSamExtRidToSid";
LABEL_151:
                CONNECTED_TRACE_ERROR(v56, (unsigned int)NameForInternetUser);
                goto LABEL_152;
              }
            }
            else if ( a4 != 7 )
            {
              if ( a4 )
              {
                if ( a4 != 1 )
                {
                  switch ( a4 )
                  {
                    case 2:
                      Buffer = (_DWORD *)*((_QWORD *)v59 + 60);
                      v19 = 1310720;
                      if ( !Buffer )
                      {
                        Length = 0;
                        goto LABEL_37;
                      }
                      goto LABEL_36;
                    case 3:
                      Buffer = (_DWORD *)*((_QWORD *)v59 + 64);
                      v19 = 263168;
                      Length = *((_DWORD *)v59 + 126);
                      goto LABEL_37;
                    case 5:
                      Buffer = (_DWORD *)*((_QWORD *)v59 + 62);
                      v19 = 4456448;
                      Length = *((_DWORD *)v59 + 122);
                      goto LABEL_37;
                    case 6:
                      v19 = 1835008;
                      if ( !*((_QWORD *)v59 + 60) || (v42 = 2, !*((_WORD *)v59 + 232)) )
                        v42 = 1;
                      v60 = v42;
                      Buffer = &v60;
                      Length = 4;
                      goto LABEL_37;
                  }
                  goto LABEL_149;
                }
                Buffer = (_DWORD *)*((_QWORD *)v59 + 59);
                v19 = 786432;
                Length = *((unsigned __int16 *)v59 + 232);
LABEL_148:
                v28 = 1;
                goto LABEL_38;
              }
              v24 = 2;
LABEL_147:
              Buffer = (_DWORD *)*((_QWORD *)v59 + 53);
              Length = *((unsigned __int16 *)v59 + 208);
              goto LABEL_148;
            }
            NameForInternetUser = LsapGetNameForInternetUser(v61, *((_DWORD *)v59 + 68), (a4 != 7) + 13, &v66);
            inited = NameForInternetUser;
            if ( NameForInternetUser >= 0 )
            {
              Buffer = v66.Buffer;
              v28 = 1;
              Length = v66.Length;
              v22 = v59;
              goto LABEL_38;
            }
            v56 = "LsapGetNameForInternetUser";
            goto LABEL_151;
          }
        }
        else
        {
          inited = -1073741637;
        }
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids,
            (unsigned int)inited);
        }
        if ( inited == -1073741709 )
        {
          if ( a4 == 6 )
          {
            v28 = 0;
            Buffer = &v60;
            v10 = 1;
            Length = 4;
            goto LABEL_53;
          }
          inited = -1073741724;
        }
        CONNECTED_TRACE_ERROR("LsapSamExtGetUserLogonInformation2", (unsigned int)inited);
        goto LABEL_40;
      }
      v54 = (unsigned int)QualifiedIdentityName;
      v55 = "LsapMakeQualifiedIdentityName";
    }
    CONNECTED_TRACE_ERROR(v55, v54);
    goto LABEL_58;
  }
  inited = -1073741811;
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v49 = 12;
    goto LABEL_190;
  }
LABEL_59:
  LsapDerefIdProv(v65);
  if ( inited < 0 && v6 && *v6 )
  {
    LsapSubProv_FreeRoutine(*v6, v34);
    *v6 = 0;
  }
  v36 = v71.Buffer;
  if ( v71.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v71.Buffer, v34);
  if ( v61 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v36, v34, v35) )
    SamrCloseHandle(&v61);
  v37 = v59;
  if ( v59 )
    LsapSamExtFreeUserInternal6Information(v59);
  if ( v66.Buffer )
    LsapFreeString(&v66);
  if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v37, v34, v35) )
    SamIFreeSidAndAttributesList(&v73);
  if ( v64 )
    LsapSamExtFreeVoid(v64);
  if ( v10 && inited < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v40 = 12;
LABEL_195:
      WPP_SF_sd(
        *((_QWORD *)v38 + 2),
        v40,
        (unsigned int)WPP_beece53709d13be865c3a44b1735e315_Traceguids,
        (unsigned int)"LsapIdProvHostLookUpUserInfo",
        inited);
    }
  }
  else
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v40 = 13;
      goto LABEL_195;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180060fa0  mov     [rsp-8+arg_18], rbx
0x180060fa5  push    rbp
0x180060fa6  push    rsi
0x180060fa7  push    rdi
0x180060fa8  push    r12
0x180060faa  push    r13
0x180060fac  push    r14
0x180060fae  push    r15
0x180060fb0  lea     rbp, [rsp-30h]
0x180060fb5  sub     rsp, 130h
0x180060fbc  mov     r13, [rbp+60h+arg_20]
0x180060fc3  xorps   xmm0, xmm0
0x180060fc6  mov     rbx, [rbp+60h+arg_28]
0x180060fcd  xorps   xmm1, xmm1
0x180060fd0  mov     rdi, rcx
0x180060fd3  mov     [rsp+160h+var_108], r13
0x180060fd8  xor     ecx, ecx
0x180060fda  mov     [rbp+60h+var_98], rbx
0x180060fde  mov     [rbp+60h+var_D0], rcx
0x180060fe2  xor     eax, eax
0x180060fe4  mov     [rsp+160h+var_E8], rcx
0x180060fe9  mov     r14d, r9d
0x180060fec  mov     [rsp+160h+var_F8], rcx
0x180060ff1  mov     r15, r8
0x180060ff4  lea     r12d, [rcx+1]
0x180060ff8  mov     [rsp+160h+var_F0], ecx
0x180060ffc  mov     [rbp+60h+var_D8], rcx
0x180061000  mov     rsi, rdx
0x180061003  lea     rcx, aLsapidprovhost_0; "LsapIdProvHostLookUpUserInfo"
0x18006100a  mov     [rsp+160h+var_110], r12d
0x18006100f  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180061013  mov     [rbp+60h+var_40], rax
0x180061017  movups  xmmword ptr [rbp+60h+var_90.Length], xmm1
0x18006101b  movups  [rbp+60h+var_B8], xmm0
0x18006101f  movups  [rbp+60h+var_60], xmm1
0x180061023  movups  [rbp+60h+var_50], xmm1
0x180061027  movups  [rbp+60h+var_70], xmm0
0x18006102b  movups  xmmword ptr [rbp+60h+var_C8.Length], xmm0
0x18006102f  call    CONNECTED_TRACE_ENTER_0
0x180061034  xor     eax, eax
0x180061036  lea     rdx, WPP_GLOBAL_Control
0x18006103d  test    rdi, rdi
0x180061040  jz      loc_1800614CD
0x180061046  test    r13, r13
0x180061049  jz      loc_1800614CD
0x18006104f  test    rbx, rbx
0x180061052  jz      loc_1800614CD
0x180061058  test    rsi, rsi
0x18006105b  jz      loc_180061725
0x180061061  mov     [r13+0], rax
0x180061065  mov     [rbx], eax
0x180061067  cmp     r14d, 0Fh
0x18006106b  ja      loc_180061BC2
0x180061071  cmp     dword ptr [rdi+10h], 45704953h
0x180061078  jnz     loc_180061587
0x18006107e  lock inc dword ptr [rdi+14h]
0x180061082  xor     edx, edx; Wait
0x180061084  mov     [rbp+60h+var_D0], rdi
0x180061088  lea     rcx, ?g_ConnectedAccountStoreLock@@3U_RTL_RESOURCE@@A; Resource
0x18006108f  call    cs:__imp_RtlAcquireResourceShared
0x180061096  nop     dword ptr [rax+rax+00h]
0x18006109b  test    al, al
0x18006109d  jz      loc_1800618A7
0x1800610a3  call    ?LsapLazyInitSamConnection@@YAJXZ; LsapLazyInitSamConnection(void)
0x1800610a8  mov     ebx, eax
0x1800610aa  test    eax, eax
0x1800610ac  js      loc_1800618ED
0x1800610b2  test    rsi, rsi
0x1800610b5  jnz     loc_1800612FC
0x1800610bb  mov     rcx, r15; Sid
0x1800610be  mov     qword ptr [rbp+60h+var_B8+8], r15
0x1800610c2  call    cs:__imp_RtlLengthSid
0x1800610c9  nop     dword ptr [rax+rax+00h]
0x1800610ce  mov     word ptr [rbp+60h+var_B8], ax
0x1800610d2  xor     edx, edx
0x1800610d4  mov     word ptr [rbp+60h+var_B8+2], ax
0x1800610d8  mov     r13d, 80h
0x1800610de  lea     eax, [r14-2]
0x1800610e2  mov     [rsp+160h+var_100], edx
0x1800610e6  and     eax, 0FFFFFFFBh
0x1800610e9  mov     r12d, 400000h
0x1800610ef  neg     eax
0x1800610f1  sbb     edi, edi
0x1800610f3  not     edi
0x1800610f5  and     edi, 100000h
0x1800610fb  cmp     r14d, 5
0x1800610ff  cmovnz  r12d, edx
0x180061103  cmp     r14d, 1
0x180061107  jnz     loc_1800614BC
0x18006110d  mov     esi, 80000h
0x180061112  cmp     r14d, 3
0x180061116  mov     ecx, 400h
0x18006111b  mov     eax, 50000h
0x180061120  mov     r15d, 40000h
0x180061126  cmovnz  ecx, edx
0x180061129  cmp     r14d, 0Bh
0x18006112d  mov     [rbp+60h+var_DC], ecx
0x180061130  cmovnz  eax, r15d
0x180061134  mov     [rbp+60h+var_E0], eax
0x180061137  test    r14d, r14d
0x18006113a  jz      loc_18006190B
0x180061140  cmp     r14d, 0Ah
0x180061144  jz      loc_18006171B
0x18006114a  cmp     r14d, 0Fh
0x18006114e  mov     ebx, 23000000h
0x180061153  mov     eax, 4
0x180061158  cmovnz  ebx, eax
0x18006115b  lea     rcx, [rbp+60h+var_90]
0x18006115f  cmp     r13d, 4000h
0x180061166  lea     rax, [rbp+60h+var_B8]
0x18006116a  cmovz   rax, rcx
0x18006116e  mov     [rbp+60h+var_A8], rax
0x180061172  mov     rax, cs:?g_hIdProvExtSamAccountDomain@@3PEAXEA; void * g_hIdProvExtSamAccountDomain
0x180061179  mov     [rbp+60h+var_A0], rax
0x18006117d  call    IsSamIDecodeClaimsBlobPresent
0x180061182  xor     r9d, r9d
0x180061185  test    al, al
0x180061187  jz      loc_180061B0A
0x18006118d  mov     r8, [rbp+60h+var_A8]
0x180061191  lea     rax, [rsp+160h+var_E8]
0x180061196  mov     rcx, [rbp+60h+var_A0]
0x18006119a  or      esi, r12d
0x18006119d  mov     [rsp+160h+var_120], rax
0x1800611a2  or      esi, edi
0x1800611a4  or      esi, [rbp+60h+var_E0]
0x1800611a7  lea     rax, [rbp+60h+var_70]
0x1800611ab  or      esi, [rbp+60h+var_DC]
0x1800611ae  mov     edx, r13d
0x1800611b1  mov     [rsp+160h+var_128], rax
0x1800611b6  lea     rax, [rsp+160h+var_F8]
0x1800611bb  mov     [rsp+160h+var_130], rax
0x1800611c0  mov     [rsp+160h+var_138], r9
0x1800611c5  mov     r9d, ebx
0x1800611c8  mov     [rsp+160h+var_140], esi
0x1800611cc  call    cs:__imp_SamIGetUserLogonInformation2
0x1800611d3  nop     dword ptr [rax+rax+00h]
0x1800611d8  xor     r9d, r9d
0x1800611db  mov     ebx, eax
0x1800611dd  test    eax, eax
0x1800611df  js      loc_180061540
0x1800611e5  mov     rcx, [rsp+160h+var_F8]
0x1800611ea  mov     rax, [rcx+1C0h]
0x1800611f1  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800611f8  jnz     short loc_180061208
0x1800611fa  mov     rax, [rcx+1C8h]
0x180061201  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180061208  test    rax, rax
0x18006120b  jz      loc_1800612C1
0x180061211  mov     r12d, r9d
0x180061214  mov     r10d, 10h
0x18006121a  cmp     r14d, 7
0x18006121e  jg      loc_180061762
0x180061224  jz      loc_1800619DE
0x18006122a  mov     edx, r14d
0x18006122d  test    r14d, r14d
0x180061230  jz      loc_18006194B
0x180061236  sub     edx, 1
0x180061239  jz      loc_180061935
0x18006123f  sub     edx, 1
0x180061242  jnz     loc_1800614EE
0x180061248  mov     rsi, [rcx+1E0h]
0x18006124f  mov     r15d, 140000h
0x180061255  test    rsi, rsi
0x180061258  jz      loc_18006192D
0x18006125e  mov     rcx, rsi; Sid
0x180061261  call    cs:__imp_RtlLengthSid
0x180061268  nop     dword ptr [rax+rax+00h]
0x18006126d  mov     rcx, [rsp+160h+var_F8]
0x180061272  xor     r9d, r9d
0x180061275  mov     edi, eax
0x180061277  lea     r10d, [r9+10h]
0x18006127b  mov     r13d, [rsp+160h+var_100]
0x180061280  mov     r8d, [rcx+148h]
0x180061287  mov     eax, r8d
0x18006128a  and     eax, r15d
0x18006128d  cmp     eax, r15d
0x180061290  jz      loc_180061337
0x180061296  mov     ebx, 0C00000E5h
0x18006129b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800612a2  lea     rsi, WPP_GLOBAL_Control
0x1800612a9  cmp     rcx, rsi
0x1800612ac  jnz     loc_180061A32
0x1800612b2  mov     r12d, [rsp+160h+var_110]
0x1800612b7  mov     r13, [rsp+160h+var_108]
0x1800612bc  jmp     loc_1800613D0
0x1800612c1  mov     ebx, 0C0000064h
0x1800612c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800612cd  lea     rsi, WPP_GLOBAL_Control
0x1800612d4  cmp     rcx, rsi
0x1800612d7  jz      short loc_1800612B2
0x1800612d9  test    byte ptr [rcx+1Ch], 1
0x1800612dd  jz      short loc_1800612B2
0x1800612df  mov     rcx, [rcx+10h]
0x1800612e3  lea     r8, WPP_c896614a5d5f31bdc85262060b313dd0_Traceguids
0x1800612ea  mov     edx, 0Fh
0x1800612ef  mov     r9d, 0C0000064h
0x1800612f5  call    WPP_SF_d
0x1800612fa  jmp     short loc_1800612B2
0x1800612fc  mov     rdx, rsi; SourceString
0x1800612ff  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180061303  call    cs:__imp_RtlInitUnicodeString
0x18006130a  nop     dword ptr [rax+rax+00h]
0x18006130f  lea     rdx, [rdi+28h]; struct _UNICODE_STRING *
0x180061313  lea     r8, [rbp+60h+var_90]; struct _UNICODE_STRING *
0x180061317  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x18006131b  call    ?LsapMakeQualifiedIdentityName@@YAJPEAU_UNICODE_STRING@@00@Z; LsapMakeQualifiedIdentityName(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180061320  xor     edx, edx
0x180061322  mov     ebx, eax
0x180061324  test    eax, eax
0x180061326  js      loc_1800618F8
0x18006132c  mov     r13d, 4000h
0x180061332  jmp     loc_1800610DE
0x180061337  mov     eax, [rcx+11Ch]
0x18006133d  and     eax, r12d
0x180061340  cmp     eax, r12d
0x180061343  jnz     loc_1800617C6
0x180061349  test    edi, edi
0x18006134b  jz      loc_180061A51
0x180061351  test    rsi, rsi
0x180061354  jz      loc_180061A47
0x18006135a  test    ebx, ebx
0x18006135c  js      loc_180061AFF
0x180061362  test    r13d, r13d
0x180061365  jnz     loc_180061AA3
0x18006136b  lea     r12d, [r13+1]
0x18006136f  mov     eax, r13d
0x180061372  mov     r15d, edi
0x180061375  neg     eax
0x180061377  sbb     rcx, rcx
0x18006137a  and     ecx, 2
0x18006137d  add     rcx, r15
0x180061380  call    LsapAllocateNoZero
0x180061385  mov     rbx, rax
0x180061388  mov     rax, [rsp+160h+var_108]
0x18006138d  mov     [rax], rbx
0x180061390  test    rbx, rbx
0x180061393  jz      loc_180061986
0x180061399  cmp     r14d, 0Ah
0x18006139d  jz      loc_18006159F
0x1800613a3  mov     r8d, r15d; Size
0x1800613a6  mov     rdx, rsi; Src
0x1800613a9  mov     rcx, rbx; void *
0x1800613ac  call    memcpy_0
0x1800613b1  xor     edx, edx
0x1800613b3  test    r13d, r13d
0x1800613b6  mov     r13, [rsp+160h+var_108]
0x1800613bb  jnz     loc_180061B3B
0x1800613c1  mov     rax, [rbp+60h+var_98]
0x1800613c5  mov     ebx, edx
0x1800613c7  mov     [rax], edi
0x1800613c9  lea     rsi, WPP_GLOBAL_Control
0x1800613d0  lea     rcx, ?g_ConnectedAccountStoreLock@@3U_RTL_RESOURCE@@A; Resource
0x1800613d7  call    cs:__imp_RtlReleaseResource
0x1800613de  nop     dword ptr [rax+rax+00h]
0x1800613e3  mov     rcx, [rbp+60h+var_D0]; struct _RTL_BALANCED_NODE *
0x1800613e7  call    ?LsapDerefIdProv@@YAXPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapDerefIdProv(_LSAP_IDPROV_REG_ENTRY *)
0x1800613ec  xor     edi, edi
0x1800613ee  test    ebx, ebx
0x1800613f0  js      loc_180061C12
0x1800613f6  mov     rcx, [rbp+60h+var_90.Buffer]; struct _RTL_BALANCED_NODE *
0x1800613fa  test    rcx, rcx
0x1800613fd  jnz     loc_180061816
0x180061403  cmp     [rsp+160h+var_E8], rdi
0x180061408  jz      short loc_180061424
0x18006140a  call    IsSamIDecodeClaimsBlobPresent
0x18006140f  test    al, al
0x180061411  jz      short loc_180061424
0x180061413  lea     rcx, [rsp+160h+var_E8]
0x180061418  call    cs:__imp_SamrCloseHandle
0x18006141f  nop     dword ptr [rax+rax+00h]
0x180061424  mov     rcx, [rsp+160h+var_F8]; struct _USER_INTERNAL6_INFORMATION *
0x180061429  test    rcx, rcx
0x18006142c  jz      short loc_180061433
0x18006142e  call    ?LsapSamExtFreeUserInternal6Information@@YAXPEAU_USER_INTERNAL6_INFORMATION@@@Z; LsapSamExtFreeUserInternal6Information(_USER_INTERNAL6_INFORMATION *)
0x180061433  cmp     [rbp+60h+var_C8.Buffer], rdi
0x180061437  jnz     loc_180061C36
0x18006143d  call    IsSamIDecodeClaimsBlobPresent
0x180061442  test    al, al
0x180061444  jz      short loc_180061456
0x180061446  lea     rcx, [rbp+60h+var_70]
0x18006144a  call    cs:__imp_SamIFreeSidAndAttributesList
0x180061451  nop     dword ptr [rax+rax+00h]
0x180061456  mov     rcx, [rbp+60h+var_D8]; void *
0x18006145a  test    rcx, rcx
0x18006145d  jnz     loc_180061C44
0x180061463  test    r12d, r12d
0x180061466  jnz     short loc_18006149C
0x180061468  mov     rcx, cs:WPP_GLOBAL_Control
0x18006146f  cmp     rcx, rsi
0x180061472  jz      short loc_18006147E
0x180061474  test    byte ptr [rcx+1Ch], 4
0x180061478  jnz     loc_180061C4E
0x18006147e  mov     eax, ebx
0x180061480  mov     rbx, [rsp+160h+arg_18]
0x180061488  add     rsp, 130h
0x18006148f  pop     r15
0x180061491  pop     r14
0x180061493  pop     r13
0x180061495  pop     r12
0x180061497  pop     rdi
  ... truncated ...
```
