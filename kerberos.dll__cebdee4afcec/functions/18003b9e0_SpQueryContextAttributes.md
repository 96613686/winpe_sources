# SpQueryContextAttributes

- ea: `0x18003b9e0`
- end: `0x18003c32f`
- name: `SpQueryContextAttributes`
- size: `2383`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004760`
- `0x180006680`
- `0x1800068d0`
- `0x18000b300`
- `0x18002a930`
- `0x180036224`
- `0x180036994`
- `0x18003a044`
- `0x18003b9e0`
- `0x180047140`
- `0x18004e380`
- `0x180066d68`
- `0x18006a2a8`
- `0x18006fe20`
- `0x1800744cf`
- `0x180081690`
- `0x18008b70c`
- `0x1800df16c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003be5d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003be5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ba2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c2dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ba2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c2dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003be0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003be0e`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003bd8f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003bdc2`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003be1b`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003be49`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003bd8f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003bdc2`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003be1b`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18003be49`
- `ntdll!RtlReleaseResource` at `0x18003bdf5`
- `ntdll!RtlReleaseResource` at `0x18003bdf5`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003bdd6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003bdd6`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18003bf6b`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18003c1e5`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18003bf6b`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18003c1e5`
- `SspiCli!FreeContextBuffer` at `0x18003c2d6`
- `SspiCli!FreeContextBuffer` at `0x18003c2d6`

## string_xrefs

- `0x18003be01`: `Used tkt cache entry start time \n`
- `0x18003be27`: `NO START TIME PRESENT IN CONTEXT, or CACHE ENTRY!\n`

## pseudocode

```c
__int64 __fastcall SpQueryContextAttributes(const void *a1, unsigned int a2, union _LARGE_INTEGER *a3)
{
  const void *v6; // rbx
  DWORD CurrentProcessId; // eax
  int v8; // eax
  struct _KERB_CONTEXT *v9; // r14
  int ContextAttributesOld; // edi
  char *v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  DWORD v14; // ecx
  __int64 (**v15)(void); // rax
  __int64 (*v16)(void); // rax
  void *v17; // rax
  _BYTE *v18; // rax
  struct _KERB_CONTEXT *v19; // rbx
  __int64 v20; // r12
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  void *v24; // rcx
  struct _SECPKG_DLL_FUNCTIONS *v25; // rax
  int v26; // ecx
  void *v27; // rax
  unsigned __int64 v28; // rbx
  LONGLONG QuadPart; // rcx
  _QWORD *v30; // r12
  union _LARGE_INTEGER *v31; // rcx
  wchar_t *v32; // rax
  const struct _UNICODE_STRING *v33; // rdx
  void *v34; // rax
  unsigned int v35; // ecx
  size_t *v36; // r12
  unsigned int *p_HighPart; // r8
  bool v38; // r10
  unsigned int v39; // edx
  int v40; // ecx
  int v41; // ebx
  LONG v42; // eax
  unsigned int LowPart; // edx
  unsigned int v44; // eax
  LONGLONG v45; // rax
  void *v46; // rax
  unsigned int v47; // eax
  DWORD v48; // eax
  __int64 v49; // rax
  __int64 v50; // rcx
  _OWORD *v51; // rcx
  unsigned int v52; // ebx
  unsigned int v53; // eax
  void *v54; // rax
  size_t v55; // rbx
  unsigned int v56; // eax
  DWORD v57; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-29h] BYREF
  __int64 v60; // [rsp+48h] [rbp-21h] BYREF
  __int64 v61; // [rsp+50h] [rbp-19h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v63[10]; // [rsp+70h] [rbp+7h] BYREF
  struct _KERB_CONTEXT *v64; // [rsp+D0h] [rbp+67h] BYREF
  bool v65; // [rsp+D8h] [rbp+6Fh] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+E8h] [rbp+7Fh] BYREF

  v64 = 0;
  SystemTimeAsFileTime = 0;
  ppPackageInfo = 0;
  *(_OWORD *)Src = 0;
  if ( a1 )
    v6 = (const void *)WORD1(a1);
  else
    v6 = 0;
  CurrentProcessId = GetCurrentProcessId();
  KerbTracerT::Log(
    7,
    "SpQueryContextAttributes",
    1154,
    "SpQueryContextAttributes called pid:0x%x, ctxt:%p, Attr:0x%x\n",
    CurrentProcessId,
    v6,
    a2);
  v8 = KerbReferenceContextByLsaHandle((unsigned __int64)a1, 0, &v64);
  v9 = v64;
  ContextAttributesOld = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_95d87aeda44130b8efc295250a7df1d2_Traceguids, a1, v8);
    goto LABEL_112;
  }
  v11 = (char *)v64 + 136;
  v12 = *((unsigned int *)v64 + 37);
  if ( (unsigned int)v12 <= 0x17 )
  {
    v13 = 8781834;
    if ( _bittest(&v13, v12) )
    {
      ContextAttributesOld = SpQueryContextAttributesOld((unsigned __int64)a1, a2, a3);
      goto LABEL_112;
    }
  }
  if ( a2 > 0x1B )
  {
    if ( a2 != 37 )
      goto LABEL_107;
    v56 = *((_DWORD *)v64 + 49);
    if ( (v56 & 4) == 0 && (*((_DWORD *)v64 + 48) & 0x400) != 0 )
      goto LABEL_107;
    ContextAttributesOld = 0;
    v47 = (v56 >> 17) & 1;
    goto LABEL_111;
  }
  if ( a2 == 27 )
  {
    if ( !a3 )
      goto LABEL_85;
    if ( *((_QWORD *)v64 + 52) )
    {
      v52 = 32766;
      v53 = *((_DWORD *)v64 + 106) >> 1;
      if ( v53 > 0x7FFE )
        goto LABEL_103;
      if ( v53 )
      {
        v52 = *((_DWORD *)v64 + 106) >> 1;
LABEL_103:
        v54 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)(2 * v52 + 2);
        a3->QuadPart = (LONGLONG)v54;
        if ( v54 )
        {
          v55 = 2LL * v52;
          memcpy_0(v54, *((const void **)v9 + 52), v55);
          *(_WORD *)(v55 + a3->QuadPart) = 0;
          goto LABEL_112;
        }
        goto LABEL_51;
      }
    }
    ContextAttributesOld = -2146893053;
    goto LABEL_112;
  }
  if ( a2 > 0xA )
  {
    if ( a2 == 12 )
      goto LABEL_94;
    if ( a2 == 14 )
    {
      if ( (*((_BYTE *)v64 + 196) & 4) != 0 )
      {
        v47 = KerbMapContextFlags(*((_DWORD *)v64 + 48));
      }
      else
      {
        v48 = *((_DWORD *)v64 + 48);
        a3->LowPart = v48;
        if ( (*((_DWORD *)v9 + 49) & 0x40000) == 0 )
          goto LABEL_112;
        v47 = v48 & 0xFFFFFFFD;
      }
    }
    else
    {
      if ( a2 != 17 )
      {
        if ( a2 == 18 )
        {
          v45 = *((_QWORD *)v64 + 15);
          if ( !v45 )
          {
            ContextAttributesOld = -2146893045;
            goto LABEL_112;
          }
        }
        else
        {
          if ( a2 != 21 )
            goto LABEL_107;
          v45 = *((_QWORD *)v64 + 6);
          if ( !v45 )
          {
            ContextAttributesOld = -2146893054;
            goto LABEL_112;
          }
        }
        a3->QuadPart = v45;
        goto LABEL_112;
      }
      if ( !a3 )
      {
LABEL_85:
        ContextAttributesOld = -1073741811;
        goto LABEL_112;
      }
      a3[1].QuadPart = 0;
      if ( !*((_QWORD *)v9 + 43) )
      {
        a3->LowPart = 0;
        goto LABEL_112;
      }
      v46 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)(*((unsigned int *)v9 + 88));
      a3[1].QuadPart = (LONGLONG)v46;
      if ( !v46 )
        goto LABEL_51;
      memcpy_0(v46, *((const void **)v9 + 43), *((unsigned int *)v9 + 88));
      v47 = *((_DWORD *)v9 + 88);
    }
LABEL_111:
    a3->LowPart = v47;
    goto LABEL_112;
  }
  if ( a2 == 10 )
  {
LABEL_94:
    v49 = ((__int64 (__fastcall *)(__int64))UserFunctions->AllocateHeap)(98);
    a3->QuadPart = v49;
    if ( !v49 )
      goto LABEL_51;
    *(_QWORD *)(v49 + 16) = v49 + 32;
    *(_QWORD *)(a3->QuadPart + 24) = *(_QWORD *)(a3->QuadPart + 16) + 18LL;
    v50 = *(_QWORD *)(a3->QuadPart + 16);
    *(_OWORD *)v50 = *(_OWORD *)L"Kerberos";
    *(_WORD *)(v50 + 16) = pszPackageName[8];
    v51 = *(_OWORD **)(a3->QuadPart + 24);
    *v51 = *(_OWORD *)L"Microsoft Kerberos V1.0";
    v51[1] = *(_OWORD *)L"t Kerberos V1.0";
    v51[2] = *(_OWORD *)L"os V1.0";
    *(_WORD *)(a3->QuadPart + 4) = 1;
    *(_WORD *)(a3->QuadPart + 6) = 16;
    *(_DWORD *)a3->QuadPart = 42941375;
    ContextAttributesOld = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
    if ( ContextAttributesOld >= 0 )
    {
      *(_DWORD *)(a3->QuadPart + 8) = ppPackageInfo->cbMaxToken;
      if ( a2 == 12 )
        a3[1].LowPart = *((_DWORD *)v9 + 50);
    }
    goto LABEL_112;
  }
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v32 = wcschr(*((const wchar_t **)v64 + 8), 0x40u);
      v33 = (const struct _UNICODE_STRING *)((char *)v9 + 56);
      if ( v32 )
      {
        ContextAttributesOld = KerbDuplicateStringEx((struct _UNICODE_STRING *)Src, v33);
        if ( ContextAttributesOld < 0 )
          goto LABEL_112;
      }
      else if ( (unsigned int)KerbBuildFullServiceName((char *)v9 + 72, v33, Src) )
      {
        goto LABEL_51;
      }
      v34 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)LOWORD(Src[0]) + 2);
      a3->QuadPart = (LONGLONG)v34;
      if ( v34 )
      {
        v28 = LOWORD(Src[0]);
        memcpy_0(v34, Src[1], LOWORD(Src[0]));
        QuadPart = a3->QuadPart;
        goto LABEL_49;
      }
LABEL_52:
      ContextAttributesOld = -1073741670;
      goto LABEL_53;
    }
    if ( a2 == 2 )
    {
      v30 = (_QWORD *)((char *)v64 + 40);
      if ( *((_QWORD *)v64 + 5) == KerbGlobalHasNeverTime.QuadPart )
      {
        v31 = (union _LARGE_INTEGER *)*((_QWORD *)v64 + 34);
        if ( v31 )
        {
          RtlSystemTimeToLocalTime(v31 + 31, a3);
          RtlAcquireResourceExclusive(&KerbContextResource, 1u);
          *v30 = *(_QWORD *)(*((_QWORD *)v9 + 34) + 248LL);
          RtlReleaseResource(&KerbContextResource);
          KerbTracerT::Log(1, "SpQueryContextAttributes", 1543, "Used tkt cache entry start time \n");
        }
        else
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          RtlSystemTimeToLocalTime((PLARGE_INTEGER)&SystemTimeAsFileTime, a3);
          KerbTracerT::Log(1, "SpQueryContextAttributes", 1559, "NO START TIME PRESENT IN CONTEXT, or CACHE ENTRY!\n");
        }
      }
      else
      {
        RtlSystemTimeToLocalTime((PLARGE_INTEGER)v64 + 5, a3);
        KerbTracerT::Log(3, "SpQueryContextAttributes", 1530, "Used context start time \n");
      }
      RtlSystemTimeToLocalTime((PLARGE_INTEGER)v9 + 3, a3 + 1);
      goto LABEL_112;
    }
    if ( a2 != 3 )
    {
      if ( a2 != 5 )
      {
        if ( a2 == 9 )
        {
          v14 = *((_DWORD *)v64 + 38);
          v15 = (__int64 (**)(void))UserFunctions;
          a3->LowPart = v14;
          v16 = *v15;
          if ( v14 )
          {
            v17 = (void *)v16();
            a3[1].QuadPart = (LONGLONG)v17;
            if ( v17 )
            {
              memcpy_0(v17, *((const void **)v9 + 20), *((unsigned int *)v9 + 38));
              goto LABEL_112;
            }
          }
          else
          {
            v18 = (_BYTE *)((__int64 (__fastcall *)(__int64))v16)(1);
            a3[1].QuadPart = (LONGLONG)v18;
            if ( v18 )
            {
              *v18 = 0;
              goto LABEL_112;
            }
          }
          goto LABEL_51;
        }
LABEL_107:
        ContextAttributesOld = -1073741637;
        goto LABEL_112;
      }
      *(_OWORD *)&a3->LowPart = 0;
      *(_OWORD *)&a3[2].LowPart = 0;
      KerberosCryptoPolicy::FromKerberosKey(&v64, v11, 0, 1);
      v19 = v64;
      if ( v64 )
      {
        v20 = KerberosCryptoPolicy::SelectEncryptionAlgorithm(
                v64,
                (-(__int64)((*((_DWORD *)v9 + 49) & 4) != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 24);
        if ( !v20
          || (v21 = KerberosCryptoPolicy::SelectChecksumAlgorithm(
                      v19,
                      (-(__int64)((*((_DWORD *)v9 + 49) & 4) != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 25)) == 0 )
        {
          ContextAttributesOld = -1073741059;
          goto LABEL_28;
        }
        a3[3].LowPart = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 216LL))(v20);
        a3[2].HighPart = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 104LL))(v21);
        a3[2].LowPart = 8 * *((_DWORD *)v9 + 38);
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v20 + 32LL))(v20, Src);
        (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 32LL))(v21, v63);
        v22 = ((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)(2 * LODWORD(Src[0]) + 2));
        a3[1].QuadPart = v22;
        if ( v22 )
        {
          v23 = ((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)(2 * LODWORD(v63[0]) + 2));
          v24 = (void *)a3[1].QuadPart;
          a3->QuadPart = v23;
          if ( v23 )
          {
            memcpy_0(v24, Src[1], 2 * (__int64)Src[0]);
            memcpy_0((void *)a3->QuadPart, (const void *)v63[1], 2LL * v63[0]);
            goto LABEL_28;
          }
          ((void (__fastcall *)(void *))UserFunctions->FreeHeap)(v24);
          a3[1].QuadPart = 0;
        }
      }
      ContextAttributesOld = -1073741670;
LABEL_28:
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
      goto LABEL_112;
    }
    if ( !(unsigned int)KerbBuildFullServiceName((char *)v64 + 72, (char *)v64 + 56, Src) )
    {
      v25 = UserFunctions;
      v26 = LOWORD(Src[0]);
      a3->LowPart = 1;
      v27 = (void *)((__int64 (__fastcall *)(_QWORD))v25->AllocateHeap)((unsigned int)(v26 + 2));
      a3[1].QuadPart = (LONGLONG)v27;
      if ( v27 )
      {
        v28 = LOWORD(Src[0]);
        memcpy_0(v27, Src[1], LOWORD(Src[0]));
        QuadPart = a3[1].QuadPart;
LABEL_49:
        *(_WORD *)(QuadPart + 2 * (v28 >> 1)) = 0;
LABEL_53:
        KerbFreeString((__int64)Src);
        goto LABEL_112;
      }
      goto LABEL_52;
    }
LABEL_51:
    ContextAttributesOld = -1073741670;
    goto LABEL_112;
  }
  Src[0] = 0;
  v64 = 0;
  v60 = 0;
  v61 = 0;
  ContextAttributesOld = KerberosCryptoPolicy::GetMessageSizes(v12, Src, &v64, &v60, &v61);
  if ( ContextAttributesOld >= 0 )
  {
    v35 = *((_DWORD *)v9 + 37);
    v65 = 0;
    ContextAttributesOld = KerberosCryptoPolicy::CipherHasAttribute(v35, 8, &v65);
    if ( ContextAttributesOld >= 0 )
    {
      v36 = &dword_1801400D0;
      if ( (*((_BYTE *)v9 + 196) & 0x10) == 0 )
        v36 = &dword_1801400A0;
      ContextAttributesOld = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
      if ( ContextAttributesOld >= 0 )
      {
        p_HighPart = (unsigned int *)&a3->HighPart;
        v38 = v65;
        a3->LowPart = ppPackageInfo->cbMaxToken;
        if ( (*((_DWORD *)v9 + 48) & 0x1001C) != 0 )
        {
          v39 = (unsigned int)v64;
          *p_HighPart = (unsigned int)v64;
          if ( v38 )
          {
            ContextAttributesOld = g_token_size((struct gss_OID_desc_struct *)v36, v39, p_HighPart);
            if ( ContextAttributesOld < 0 )
              goto LABEL_112;
          }
        }
        else
        {
          *p_HighPart = 4;
        }
        v40 = *((_DWORD *)v9 + 48);
        if ( (v40 & 0x210) == 0x200 || (v40 & 0x40000) != 0 )
        {
          a3[1].QuadPart = 0;
        }
        else
        {
          v41 = 1;
          if ( v60 )
            v41 = v60;
          v42 = v61;
          a3[1].LowPart = v41;
          a3[1].HighPart = v42;
          if ( v38 )
          {
            LowPart = a3->LowPart;
            v44 = a3->LowPart + v42;
            if ( v44 < a3->LowPart )
            {
              a3[1].HighPart = -1;
              ContextAttributesOld = -1073741675;
            }
            else
            {
              a3[1].HighPart = v44;
              ContextAttributesOld = g_token_size((struct gss_OID_desc_struct *)v36, LowPart, (unsigned int *)a3);
              if ( ContextAttributesOld >= 0 )
                a3[1].HighPart -= a3->LowPart;
            }
          }
        }
      }
    }
  }
LABEL_112:
  if ( v9 )
    KerbDereferenceContext(v9);
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  v57 = GetCurrentProcessId();
  KerbTracerT::Log(
    7,
    "SpQueryContextAttributes",
    1760,
    "SpQueryContextAttributes returned 0x%x, pid:0x%x, ctxt:%p, Attr:0x%x\n",
    ContextAttributesOld,
    v57,
    a1,
    a2);
  return (unsigned int)ContextAttributesOld;
}

```

## disassembly

```asm
0x18003b9e0  mov     [rsp-8+arg_10], rbx
0x18003b9e5  push    rbp
0x18003b9e6  push    rsi
0x18003b9e7  push    rdi
0x18003b9e8  push    r12
0x18003b9ea  push    r13
0x18003b9ec  push    r14
0x18003b9ee  push    r15
0x18003b9f0  lea     rbp, [rsp-27h]
0x18003b9f5  sub     rsp, 90h
0x18003b9fc  xor     r12d, r12d
0x18003b9ff  xorps   xmm0, xmm0
0x18003ba02  mov     [rbp+57h+arg_0], r12
0x18003ba06  mov     rsi, r8
0x18003ba09  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18003ba0d  mov     r15d, edx
0x18003ba10  mov     [rbp+57h+ppPackageInfo], r12
0x18003ba14  mov     r13, rcx
0x18003ba17  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18003ba1b  test    rcx, rcx
0x18003ba1e  jz      short loc_18003BA2C
0x18003ba20  mov     rax, rcx
0x18003ba23  shr     rax, 10h
0x18003ba27  movzx   ebx, ax
0x18003ba2a  jmp     short loc_18003BA2F
0x18003ba2c  mov     rbx, r12
0x18003ba2f  call    cs:__imp_GetCurrentProcessId
0x18003ba35  mov     dword ptr [rsp+0C0h+var_90], r15d
0x18003ba3a  lea     r9, aSpquerycontext_2; "SpQueryContextAttributes called pid:0x%"...
0x18003ba41  mov     [rsp+0C0h+var_98], rbx
0x18003ba46  lea     rdx, aSpquerycontext_0; "SpQueryContextAttributes"
0x18003ba4d  mov     r8d, 482h
0x18003ba53  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18003ba57  mov     ecx, 7
0x18003ba5c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003ba61  lea     r8, [rbp+57h+arg_0]; struct _KERB_CONTEXT **
0x18003ba65  xor     edx, edx; unsigned __int8
0x18003ba67  mov     rcx, r13; unsigned __int64
0x18003ba6a  call    ?KerbReferenceContextByLsaHandle@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z; KerbReferenceContextByLsaHandle(unsigned __int64,uchar,_KERB_CONTEXT * *)
0x18003ba6f  mov     r14, [rbp+57h+arg_0]
0x18003ba73  mov     edi, eax
0x18003ba75  test    eax, eax
0x18003ba77  jns     short loc_18003BABD
0x18003ba79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba80  lea     rax, WPP_GLOBAL_Control
0x18003ba87  cmp     rcx, rax
0x18003ba8a  jz      loc_18003C2C0
0x18003ba90  mov     ebx, 1
0x18003ba95  test    [rcx+1Ch], bl
0x18003ba98  jz      loc_18003C2C0
0x18003ba9e  mov     rcx, [rcx+10h]
0x18003baa2  lea     edx, [rbx+10h]
0x18003baa5  mov     r9, r13
0x18003baa8  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18003baac  lea     r8, WPP_95d87aeda44130b8efc295250a7df1d2_Traceguids
0x18003bab3  call    WPP_SF_qD
0x18003bab8  jmp     loc_18003C2C0
0x18003babd  lea     rdx, [r14+88h]
0x18003bac4  mov     ecx, [rdx+0Ch]
0x18003bac7  cmp     ecx, 17h
0x18003baca  ja      short loc_18003BAEB
0x18003bacc  mov     eax, 86000Ah
0x18003bad1  bt      eax, ecx
0x18003bad4  jnb     short loc_18003BAEB
0x18003bad6  mov     r8, rsi; void *
0x18003bad9  mov     edx, r15d; unsigned int
0x18003badc  mov     rcx, r13; unsigned __int64
0x18003badf  call    ?SpQueryContextAttributesOld@@YAJ_KKPEAX@Z; SpQueryContextAttributesOld(unsigned __int64,ulong,void *)
0x18003bae4  mov     edi, eax
0x18003bae6  jmp     loc_18003C2C0
0x18003baeb  cmp     r15d, 1Bh
0x18003baef  ja      loc_18003C290
0x18003baf5  jz      loc_18003C21B
0x18003bafb  cmp     r15d, 0Ah
0x18003baff  ja      loc_18003C043
0x18003bb05  jz      loc_18003C142
0x18003bb0b  mov     eax, r15d
0x18003bb0e  test    r15d, r15d
0x18003bb11  jz      loc_18003BEEB
0x18003bb17  sub     eax, 1
0x18003bb1a  jz      loc_18003BE54
0x18003bb20  sub     eax, 1
0x18003bb23  jz      loc_18003BD78
0x18003bb29  sub     eax, 1
0x18003bb2c  jz      loc_18003BD1A
0x18003bb32  sub     eax, 2
0x18003bb35  jz      short loc_18003BBA3
0x18003bb37  cmp     eax, 4
0x18003bb3a  jnz     loc_18003C296
0x18003bb40  mov     ecx, [r14+98h]
0x18003bb47  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003bb4e  mov     [rsi], ecx
0x18003bb50  mov     rax, [rax]
0x18003bb53  test    ecx, ecx
0x18003bb55  jz      short loc_18003BB84
0x18003bb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb5c  mov     [rsi+8], rax
0x18003bb60  test    rax, rax
0x18003bb63  jz      loc_18003BECE
0x18003bb69  mov     r8d, [r14+98h]; Size
0x18003bb70  mov     rcx, rax; void *
0x18003bb73  mov     rdx, [r14+0A0h]; Src
0x18003bb7a  call    memcpy_0
0x18003bb7f  jmp     loc_18003C2C0
0x18003bb84  mov     ecx, 1
0x18003bb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb8e  mov     [rsi+8], rax
0x18003bb92  test    rax, rax
0x18003bb95  jz      loc_18003BECE
0x18003bb9b  mov     [rax], r12b
0x18003bb9e  jmp     loc_18003C2C0
0x18003bba3  xorps   xmm0, xmm0
0x18003bba6  lea     rcx, [rbp+57h+arg_0]
0x18003bbaa  movups  xmmword ptr [rsi], xmm0
0x18003bbad  mov     r9d, 1
0x18003bbb3  xor     r8d, r8d
0x18003bbb6  movups  xmmword ptr [rsi+10h], xmm0
0x18003bbba  call    ?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)
0x18003bbbf  mov     rbx, [rbp+57h+arg_0]
0x18003bbc3  test    rbx, rbx
0x18003bbc6  jnz     short loc_18003BBDB
0x18003bbc8  mov     edi, 0C000009Ah
0x18003bbcd  lea     rcx, [rbp+57h+arg_0]
0x18003bbd1  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18003bbd6  jmp     loc_18003C2C0
0x18003bbdb  mov     eax, [r14+0C4h]
0x18003bbe2  mov     rcx, rbx
0x18003bbe5  and     al, 4
0x18003bbe7  neg     al
0x18003bbe9  sbb     rdx, rdx
0x18003bbec  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18003bbf0  add     rdx, 18h
0x18003bbf4  call    ?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x18003bbf9  mov     r12, rax
0x18003bbfc  test    rax, rax
0x18003bbff  jnz     short loc_18003BC08
0x18003bc01  mov     edi, 0C00002FDh
0x18003bc06  jmp     short loc_18003BBCD
0x18003bc08  mov     eax, [r14+0C4h]
0x18003bc0f  mov     rcx, rbx
0x18003bc12  and     al, 4
0x18003bc14  neg     al
0x18003bc16  sbb     rdx, rdx
0x18003bc19  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18003bc1d  add     rdx, 19h
0x18003bc21  call    ?SelectChecksumAlgorithm@KerberosCryptoPolicy@@QEAAPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectChecksumAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x18003bc26  mov     rbx, rax
0x18003bc29  test    rax, rax
0x18003bc2c  jz      short loc_18003BC01
0x18003bc2e  mov     rax, [r12]
0x18003bc32  mov     rcx, r12
0x18003bc35  mov     rax, [rax+0D8h]
0x18003bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc41  mov     [rsi+18h], eax
0x18003bc44  mov     rcx, rbx
0x18003bc47  mov     rax, [rbx]
0x18003bc4a  mov     rax, [rax+68h]
0x18003bc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc53  mov     [rsi+14h], eax
0x18003bc56  lea     rdx, [rbp+57h+Src]
0x18003bc5a  mov     eax, [r14+98h]
0x18003bc61  mov     rcx, r12
0x18003bc64  shl     eax, 3
0x18003bc67  mov     [rsi+10h], eax
0x18003bc6a  mov     rax, [r12]
0x18003bc6e  mov     rax, [rax+20h]
0x18003bc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc77  mov     rax, [rbx]
0x18003bc7a  lea     rdx, [rbp+57h+var_50]
0x18003bc7e  mov     rcx, rbx
0x18003bc81  mov     rax, [rax+20h]
0x18003bc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc8a  mov     ecx, dword ptr [rbp+57h+Src]
0x18003bc8d  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003bc94  lea     ecx, ds:2[rcx*2]
0x18003bc9b  mov     rax, [rax]
0x18003bc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bca3  mov     [rsi+8], rax
0x18003bca7  test    rax, rax
0x18003bcaa  jz      loc_18003BBC8
0x18003bcb0  mov     ecx, dword ptr [rbp+57h+var_50]
0x18003bcb3  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003bcba  lea     ecx, ds:2[rcx*2]
0x18003bcc1  mov     rax, [rax]
0x18003bcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcc9  mov     rcx, [rsi+8]; void *
0x18003bccd  mov     [rsi], rax
0x18003bcd0  test    rax, rax
0x18003bcd3  jnz     short loc_18003BCF2
0x18003bcd5  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003bcdc  mov     rax, [rax+8]
0x18003bce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bce5  mov     qword ptr [rsi+8], 0
0x18003bced  jmp     loc_18003BBC8
0x18003bcf2  mov     r8, [rbp+57h+Src]
0x18003bcf6  mov     rdx, [rbp+57h+Src+8]; Src
0x18003bcfa  add     r8, r8; Size
0x18003bcfd  call    memcpy_0
0x18003bd02  mov     r8, [rbp+57h+var_50]
0x18003bd06  mov     rdx, [rbp+57h+var_48]; Src
0x18003bd0a  add     r8, r8; Size
0x18003bd0d  mov     rcx, [rsi]; void *
0x18003bd10  call    memcpy_0
0x18003bd15  jmp     loc_18003BBCD
0x18003bd1a  lea     rdx, [r14+38h]
0x18003bd1e  lea     rcx, [r14+48h]
0x18003bd22  lea     r8, [rbp+57h+Src]
0x18003bd26  call    KerbBuildFullServiceName
0x18003bd2b  test    eax, eax
0x18003bd2d  jnz     loc_18003BECE
0x18003bd33  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003bd3a  movzx   ecx, word ptr [rbp+57h+Src]
0x18003bd3e  mov     dword ptr [rsi], 1
0x18003bd44  add     ecx, 2
0x18003bd47  mov     rax, [rax]
0x18003bd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd4f  mov     [rsi+8], rax
0x18003bd53  test    rax, rax
0x18003bd56  jz      loc_18003BED8
0x18003bd5c  movzx   ebx, word ptr [rbp+57h+Src]
0x18003bd60  mov     rcx, rax; void *
0x18003bd63  mov     rdx, [rbp+57h+Src+8]; Src
0x18003bd67  mov     r8d, ebx; Size
0x18003bd6a  call    memcpy_0
0x18003bd6f  mov     rcx, [rsi+8]
0x18003bd73  jmp     loc_18003BEB3
0x18003bd78  mov     rax, cs:?KerbGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalHasNeverTime
0x18003bd7f  lea     r12, [r14+28h]
0x18003bd83  cmp     [r12], rax
0x18003bd87  jz      short loc_18003BDAC
0x18003bd89  mov     rdx, rsi; LocalTime
0x18003bd8c  mov     rcx, r12; SystemTime
0x18003bd8f  call    cs:__imp_RtlSystemTimeToLocalTime
0x18003bd95  mov     r8d, 5FAh
0x18003bd9b  lea     r9, aUsedContextSta; "Used context start time \n"
0x18003bda2  mov     ebx, 3
0x18003bda7  jmp     loc_18003BE33
0x18003bdac  mov     rcx, [r14+110h]
0x18003bdb3  test    rcx, rcx
0x18003bdb6  jz      short loc_18003BE0A
0x18003bdb8  add     rcx, 0F8h; SystemTime
0x18003bdbf  mov     rdx, rsi; LocalTime
0x18003bdc2  call    cs:__imp_RtlSystemTimeToLocalTime
0x18003bdc8  mov     ebx, 1
0x18003bdcd  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18003bdd4  mov     dl, bl; Wait
0x18003bdd6  call    cs:__imp_RtlAcquireResourceExclusive
0x18003bddc  mov     rax, [r14+110h]
0x18003bde3  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18003bdea  mov     rdx, [rax+0F8h]
0x18003bdf1  mov     [r12], rdx
0x18003bdf5  call    cs:__imp_RtlReleaseResource
0x18003bdfb  mov     r8d, 607h
0x18003be01  lea     r9, aUsedTktCacheEn; "Used tkt cache entry start time \n"
0x18003be08  jmp     short loc_18003BE33
0x18003be0a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003be0e  call    cs:__imp_GetSystemTimeAsFileTime
0x18003be14  mov     rdx, rsi; LocalTime
0x18003be17  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; SystemTime
0x18003be1b  call    cs:__imp_RtlSystemTimeToLocalTime
0x18003be21  mov     r8d, 617h
0x18003be27  lea     r9, aNoStartTimePre; "NO START TIME PRESENT IN CONTEXT, or CA"...
0x18003be2e  mov     ebx, 1
0x18003be33  lea     rdx, aSpquerycontext_0; "SpQueryContextAttributes"
0x18003be3a  mov     ecx, ebx
0x18003be3c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003be41  lea     rdx, [rsi+8]; LocalTime
0x18003be45  lea     rcx, [r14+18h]; SystemTime
0x18003be49  call    cs:__imp_RtlSystemTimeToLocalTime
0x18003be4f  jmp     loc_18003C2C0
0x18003be54  mov     rcx, [r14+40h]; Str
0x18003be58  mov     edx, 40h ; '@'; Ch
0x18003be5d  call    cs:__imp_wcschr
0x18003be63  lea     rdx, [r14+38h]; struct _UNICODE_STRING *
0x18003be67  test    rax, rax
0x18003be6a  jz      short loc_18003BEBD
0x18003be6c  lea     rcx, [rbp+57h+Src]; struct _UNICODE_STRING *
0x18003be70  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18003be75  mov     edi, eax
0x18003be77  test    eax, eax
0x18003be79  js      loc_18003C2C0
0x18003be7f  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18003be86  movzx   ecx, word ptr [rbp+57h+Src]
0x18003be8a  add     ecx, 2
0x18003be8d  mov     rax, [rax]
0x18003be90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be95  mov     [rsi], rax
0x18003be98  test    rax, rax
0x18003be9b  jz      short loc_18003BED8
0x18003be9d  movzx   ebx, word ptr [rbp+57h+Src]
0x18003bea1  mov     rcx, rax; void *
0x18003bea4  mov     rdx, [rbp+57h+Src+8]; Src
0x18003bea8  mov     r8d, ebx; Size
0x18003beab  call    memcpy_0
0x18003beb0  mov     rcx, [rsi]
0x18003beb3  shr     rbx, 1
0x18003beb6  mov     [rcx+rbx*2], r12w
0x18003bebb  jmp     short loc_18003BEDD
0x18003bebd  lea     rcx, [r14+48h]
0x18003bec1  lea     r8, [rbp+57h+Src]
  ... truncated ...
```
