# SpQueryContextAttributesOld(unsigned __int64,ulong,void *)

- ea: `0x18004e380`
- end: `0x18004ed1a`
- name: `?SpQueryContextAttributesOld@@YAJ_KKPEAX@Z`
- size: `2458`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b9e0`

## callees

- `0x180006680`
- `0x18000b300`
- `0x18002a930`
- `0x180036224`
- `0x18003a044`
- `0x180047140`
- `0x18004e380`
- `0x1800744cf`
- `0x180081690`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004e689`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004e689`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e3d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e3d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ec68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e922`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e732`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e732`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e8a8`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e8db`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e92f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e95b`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e8a8`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e8db`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e92f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18004e95b`
- `ntdll!RtlReleaseResource` at `0x18004e909`
- `ntdll!RtlReleaseResource` at `0x18004e909`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004e8ea`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004e8ea`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18004e4a9`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18004ebbc`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18004e4a9`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18004ebbc`
- `SspiCli!FreeContextBuffer` at `0x18004ec51`
- `SspiCli!FreeContextBuffer` at `0x18004ec51`
- `cryptdll!CDLocateCSystem` at `0x18004e57a`
- `cryptdll!CDLocateCSystem` at `0x18004ea16`
- `cryptdll!CDLocateCSystem` at `0x18004e57a`
- `cryptdll!CDLocateCSystem` at `0x18004ea16`

## string_xrefs

- `0x18004e915`: `Used tkt cache entry start time \n`
- `0x18004e93b`: `NO START TIME PRESENT IN CONTEXT, or CACHE ENTRY!\n`

## pseudocode

```c
__int64 __fastcall SpQueryContextAttributesOld(unsigned __int64 a1, int a2, union _LARGE_INTEGER *a3)
{
  const void *v6; // rbx
  DWORD CurrentProcessId; // eax
  int v8; // eax
  struct _KERB_CONTEXT *v9; // r14
  int v10; // edi
  size_t *v11; // r15
  int v12; // r13d
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  unsigned int v16; // ebx
  int v17; // eax
  DWORD v18; // ecx
  __int64 (**v19)(void); // rax
  __int64 (*v20)(void); // rax
  void *v21; // rax
  _BYTE *v22; // rax
  wchar_t *v23; // rax
  const struct _UNICODE_STRING *v24; // rdx
  unsigned __int64 v25; // rbx
  void *v26; // rax
  void *v27; // r15
  struct _SECPKG_DLL_FUNCTIONS *v28; // rax
  unsigned __int64 v29; // rbx
  void *v30; // rax
  void *v31; // rax
  unsigned int v32; // ebx
  unsigned int v33; // eax
  void *v34; // rax
  size_t v35; // rbx
  union _LARGE_INTEGER *v36; // rcx
  __int64 v37; // r8
  const char *v38; // r9
  DWORD v39; // eax
  DWORD v40; // r8d
  int v41; // ecx
  const wchar_t *v42; // r15
  int v43; // eax
  struct _KERB_CONTEXT *v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  bool v48; // zf
  __int64 v49; // rax
  void *v50; // r9
  __int64 v51; // rax
  _WORD *v52; // rdx
  void *v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  _OWORD *v56; // rcx
  LONGLONG v57; // rax
  LONGLONG v58; // rax
  unsigned int v59; // eax
  const void *v60; // rbx
  DWORD v61; // eax
  __int64 v63; // [rsp+40h] [rbp-20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-18h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-10h] BYREF
  struct _KERB_CONTEXT *v66; // [rsp+A0h] [rbp+40h] BYREF
  int v67; // [rsp+A8h] [rbp+48h]
  PSecPkgInfoW ppPackageInfo; // [rsp+B8h] [rbp+58h] BYREF

  v67 = a2;
  v66 = 0;
  v63 = 0;
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
    "SpQueryContextAttributesOld",
    4077,
    "SpQueryContextAttributes called pid:0x%x, ctxt:%p, Attr:0x%x\n",
    CurrentProcessId,
    v6,
    a2);
  v8 = KerbReferenceContextByLsaHandle(a1, 0, &v66);
  v9 = v66;
  v10 = v8;
  if ( v8 >= 0 )
  {
    switch ( a2 )
    {
      case 0:
        v11 = &dword_1801400D0;
        if ( (*((_BYTE *)v66 + 196) & 0x10) == 0 )
          v11 = &dword_1801400A0;
        v10 = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
        if ( v10 < 0 )
          goto LABEL_109;
        a3->LowPart = ppPackageInfo->cbMaxToken;
        v12 = 0x40000000;
        v13 = *((_DWORD *)v9 + 48);
        if ( (v13 & 0x600) != 0 )
          v12 = 0;
        if ( (v13 & 0x1001C) != 0 )
        {
          if ( (unsigned int)(*((_DWORD *)v9 + 37) - 17) <= 1 )
          {
            a3->HighPart = 28;
          }
          else
          {
            v10 = g_token_size((struct gss_OID_desc_struct *)v11, 0x16u, (unsigned int *)&a3->HighPart);
            if ( v10 < 0 )
              goto LABEL_109;
          }
        }
        else
        {
          a3->HighPart = 4;
        }
        v14 = *((_DWORD *)v9 + 48);
        if ( (v14 & 0x210) == 0x200 || (v14 & 0x40000) != 0 )
        {
          a3[1].LowPart = 0;
          a3[1].HighPart = 0;
        }
        else
        {
          v15 = *((_DWORD *)v9 + 37);
          if ( (unsigned int)(v15 - 17) <= 1 )
          {
            a3[1].LowPart = 1;
            a3[1].HighPart = 76;
          }
          else
          {
            v16 = -132;
            if ( (unsigned int)(v15 - 1) > 2 && v15 != -132 )
              v16 = (v15 == 23) - 141;
            v17 = CDLocateCSystem(v16, &v63);
            v10 = v17;
            if ( v17 >= 0 )
            {
              a3[1].LowPart = *(_DWORD *)(v63 + 4);
              LODWORD(v66) = v12 + 30;
              v10 = g_token_size((struct gss_OID_desc_struct *)v11, v12 + 30, (unsigned int *)&v66);
              if ( v10 >= 0 )
                a3[1].HighPart = (_DWORD)v66 - v12;
            }
            else
            {
              KerbTracerT::Log(1, "SpQueryContextAttributesOld", 4215, "Failed to load %d crypt system: 0x%x", v16, v17);
            }
          }
        }
        goto LABEL_109;
      case 1:
        v23 = wcschr(*((const wchar_t **)v66 + 8), 0x40u);
        v24 = (const struct _UNICODE_STRING *)((char *)v9 + 56);
        if ( v23 )
        {
          v10 = KerbDuplicateStringEx((struct _UNICODE_STRING *)Src, v24);
          if ( v10 < 0 )
            goto LABEL_109;
        }
        else if ( (unsigned int)KerbBuildFullServiceName((char *)v9 + 72, v24, Src) )
        {
          goto LABEL_42;
        }
        v25 = LOWORD(Src[0]);
        v26 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)LOWORD(Src[0]) + 2);
        v27 = Src[1];
        a3->QuadPart = (LONGLONG)v26;
        if ( !v26 )
          goto LABEL_43;
        memcpy_0(v26, v27, (unsigned int)v25);
        *(_WORD *)(a3->QuadPart + 2 * (v25 >> 1)) = 0;
        goto LABEL_44;
      case 2:
        if ( *((_QWORD *)v66 + 5) == KerbGlobalHasNeverTime.QuadPart )
        {
          v36 = (union _LARGE_INTEGER *)*((_QWORD *)v66 + 34);
          if ( v36 )
          {
            RtlSystemTimeToLocalTime(v36 + 31, a3);
            RtlAcquireResourceExclusive(&KerbContextResource, 1u);
            *((_QWORD *)v9 + 5) = *(_QWORD *)(*((_QWORD *)v9 + 34) + 248LL);
            RtlReleaseResource(&KerbContextResource);
            v37 = 4484;
            v38 = "Used tkt cache entry start time \n";
          }
          else
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            RtlSystemTimeToLocalTime((PLARGE_INTEGER)&SystemTimeAsFileTime, a3);
            v37 = 4500;
            v38 = "NO START TIME PRESENT IN CONTEXT, or CACHE ENTRY!\n";
          }
          KerbTracerT::Log(1, "SpQueryContextAttributesOld", v37, v38);
        }
        else
        {
          RtlSystemTimeToLocalTime((PLARGE_INTEGER)v66 + 5, a3);
          KerbTracerT::Log(3, "SpQueryContextAttributesOld", 4471, "Used context start time \n");
        }
        RtlSystemTimeToLocalTime((PLARGE_INTEGER)v9 + 3, a3 + 1);
        goto LABEL_109;
      case 3:
        if ( (unsigned int)KerbBuildFullServiceName((char *)v66 + 72, (char *)v66 + 56, Src) )
        {
          v10 = -1073741670;
        }
        else
        {
          v28 = UserFunctions;
          v29 = LOWORD(Src[0]);
          a3->LowPart = 1;
          v30 = (void *)((__int64 (__fastcall *)(_QWORD))v28->AllocateHeap)((unsigned int)(v29 + 2));
          v27 = Src[1];
          a3[1].QuadPart = (LONGLONG)v30;
          if ( v30 )
          {
            memcpy_0(v30, v27, (unsigned int)v29);
            *(_WORD *)(a3[1].QuadPart + 2 * (v29 >> 1)) = 0;
          }
          else
          {
LABEL_43:
            v10 = -1073741670;
          }
LABEL_44:
          if ( v27 )
          {
            if ( KerbGlobalPackageState == 1 )
              ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v27);
            else
              LocalFree(v27);
          }
        }
        goto LABEL_109;
      case 5:
        v66 = 0;
        v40 = *((_DWORD *)v9 + 37);
        a3[3].LowPart = v40;
        v41 = *((_DWORD *)v9 + 37);
        if ( (unsigned int)(v41 - 17) <= 1 )
        {
          v42 = L"HMAC-SHA1-96";
          v43 = (v41 != 17) + 15;
        }
        else if ( (unsigned int)(v41 - 1) <= 2 || v41 == -132 )
        {
          v42 = L"MD2.5";
          v43 = -135;
        }
        else
        {
          v42 = L"HMAC-MD5";
          v43 = -138;
        }
        a3[2].HighPart = v43;
        a3->QuadPart = 0;
        a3[1].QuadPart = 0;
        v10 = CDLocateCSystem(v40, &v66);
        if ( v10 < 0 )
          goto LABEL_109;
        v44 = v66;
        v45 = -1;
        a3[2].LowPart = 8 * *((_DWORD *)v66 + 3);
        v46 = *((_QWORD *)v44 + 4);
        v47 = -1;
        do
          v48 = *(_WORD *)(v46 + 2 * v47++ + 2) == 0;
        while ( !v48 );
        v49 = ((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)(2 * v47 + 2));
        a3[1].QuadPart = v49;
        v50 = (void *)v49;
        if ( !v49 )
          goto LABEL_42;
        v51 = -1;
        v52 = (_WORD *)*((_QWORD *)v66 + 4);
        do
          v48 = v52[++v51] == 0;
        while ( !v48 );
        memcpy_0(v50, v52, 2LL * (unsigned int)(v51 + 1));
        do
          v48 = v42[++v45] == 0;
        while ( !v48 );
        v53 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)((unsigned int)(2 * v45 + 2));
        a3->QuadPart = (LONGLONG)v53;
        if ( v53 )
        {
          memcpy_0(v53, v42, 2LL * (unsigned int)(v45 + 1));
        }
        else
        {
          v10 = -1073741670;
          ((void (__fastcall *)(_QWORD))UserFunctions->FreeHeap)((union _LARGE_INTEGER)a3[1].QuadPart);
          a3[1].QuadPart = 0;
        }
        goto LABEL_109;
      case 9:
        v18 = *((_DWORD *)v66 + 38);
        v19 = (__int64 (**)(void))UserFunctions;
        a3->LowPart = v18;
        v20 = *v19;
        if ( v18 )
        {
          v21 = (void *)v20();
          a3[1].QuadPart = (LONGLONG)v21;
          if ( !v21 )
            goto LABEL_42;
          memcpy_0(v21, *((const void **)v9 + 20), *((unsigned int *)v9 + 38));
        }
        else
        {
          v22 = (_BYTE *)((__int64 (__fastcall *)(__int64))v20)(1);
          a3[1].QuadPart = (LONGLONG)v22;
          if ( !v22 )
            goto LABEL_42;
          *v22 = 0;
        }
        goto LABEL_109;
      case 10:
      case 12:
        v54 = ((__int64 (__fastcall *)(__int64))UserFunctions->AllocateHeap)(98);
        a3->QuadPart = v54;
        if ( v54 )
        {
          *(_QWORD *)(v54 + 16) = v54 + 32;
          *(_QWORD *)(a3->QuadPart + 24) = *(_QWORD *)(a3->QuadPart + 16) + 18LL;
          v55 = *(_QWORD *)(a3->QuadPart + 16);
          *(_OWORD *)v55 = *(_OWORD *)L"Kerberos";
          *(_WORD *)(v55 + 16) = pszPackageName[8];
          v56 = *(_OWORD **)(a3->QuadPart + 24);
          *v56 = *(_OWORD *)L"Microsoft Kerberos V1.0";
          v56[1] = *(_OWORD *)L"t Kerberos V1.0";
          v56[2] = *(_OWORD *)L"os V1.0";
          *(_WORD *)(a3->QuadPart + 4) = 1;
          *(_WORD *)(a3->QuadPart + 6) = 16;
          *(_DWORD *)a3->QuadPart = 42941375;
          v10 = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
          if ( v10 >= 0 )
          {
            *(_DWORD *)(a3->QuadPart + 8) = ppPackageInfo->cbMaxToken;
            if ( a2 == 12 )
              a3[1].LowPart = *((_DWORD *)v9 + 50);
          }
        }
        else
        {
          v10 = -1073741670;
        }
        goto LABEL_109;
      case 14:
        if ( (*((_BYTE *)v66 + 196) & 4) != 0 )
        {
          a3->LowPart = KerbMapContextFlags(*((_DWORD *)v66 + 48));
        }
        else
        {
          v39 = *((_DWORD *)v66 + 48);
          a3->LowPart = v39;
          if ( (*((_DWORD *)v9 + 49) & 0x40000) != 0 )
            a3->LowPart = v39 & 0xFFFFFFFD;
        }
        goto LABEL_109;
      case 17:
        if ( !a3 )
        {
          v10 = -1073741811;
          goto LABEL_109;
        }
        a3[1].QuadPart = 0;
        if ( !*((_QWORD *)v9 + 43) )
        {
          a3->LowPart = 0;
          goto LABEL_109;
        }
        v31 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)(*((unsigned int *)v9 + 88));
        a3[1].QuadPart = (LONGLONG)v31;
        if ( !v31 )
          goto LABEL_42;
        memcpy_0(v31, *((const void **)v9 + 43), *((unsigned int *)v9 + 88));
        a3->LowPart = *((_DWORD *)v9 + 88);
        goto LABEL_109;
      case 18:
        v57 = *((_QWORD *)v66 + 15);
        if ( v57 )
          a3->QuadPart = v57;
        else
          v10 = -2146893045;
        goto LABEL_109;
      case 21:
        v58 = *((_QWORD *)v66 + 6);
        if ( v58 )
          a3->QuadPart = v58;
        else
          v10 = -2146893054;
        goto LABEL_109;
      case 27:
        if ( a3 )
        {
          if ( *((_QWORD *)v66 + 52)
            && ((v32 = 32766, v33 = *((_DWORD *)v66 + 106) >> 1, v33 > 0x7FFE)
             || (v32 = *((_DWORD *)v66 + 106) >> 1, v33)) )
          {
            v34 = (void *)((__int64 (__fastcall *)(_QWORD))UserFunctions->AllocateHeap)(2 * v32 + 2);
            a3->QuadPart = (LONGLONG)v34;
            if ( v34 )
            {
              v35 = 2LL * v32;
              memcpy_0(v34, *((const void **)v9 + 52), v35);
              *(_WORD *)(v35 + a3->QuadPart) = 0;
            }
            else
            {
LABEL_42:
              v10 = -1073741670;
            }
          }
          else
          {
            v10 = -2146893053;
          }
        }
        else
        {
          v10 = -1073741811;
        }
        goto LABEL_109;
      case 37:
        v59 = *((_DWORD *)v66 + 49);
        if ( (v59 & 4) == 0 && (*((_DWORD *)v66 + 48) & 0x400) != 0 )
          goto LABEL_108;
        v10 = 0;
        a3->LowPart = (v59 >> 17) & 1;
        goto LABEL_109;
      default:
LABEL_108:
        v10 = -1073741637;
        goto LABEL_109;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_a1119ca399823668ae16bae9ee423caf_Traceguids, a1, v8);
LABEL_109:
  if ( v9 )
    KerbDereferenceContext(v9);
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  if ( a1 )
    v60 = (const void *)WORD1(a1);
  else
    v60 = 0;
  v61 = GetCurrentProcessId();
  KerbTracerT::Log(
    7,
    "SpQueryContextAttributesOld",
    4723,
    "SpQueryContextAttributes returned 0x%x, pid:0x%x, ctxt:%p, Attr:0x%x\n",
    v10,
    v61,
    v60,
    v67);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004e380  mov     [rsp-38h+arg_10], rbx
0x18004e385  mov     [rsp-38h+arg_8], edx
0x18004e389  push    rbp
0x18004e38a  push    rsi
0x18004e38b  push    rdi
0x18004e38c  push    r12
0x18004e38e  push    r13
0x18004e390  push    r14
0x18004e392  push    r15
0x18004e394  mov     rbp, rsp
0x18004e397  sub     rsp, 60h
0x18004e39b  xor     r13d, r13d
0x18004e39e  mov     r15d, edx
0x18004e3a1  mov     [rbp+arg_0], r13
0x18004e3a5  xorps   xmm0, xmm0
0x18004e3a8  mov     [rbp+var_20], r13
0x18004e3ac  mov     rsi, r8
0x18004e3af  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x18004e3b3  mov     r12, rcx
0x18004e3b6  mov     [rbp+ppPackageInfo], r13
0x18004e3ba  movups  xmmword ptr [rbp+Src], xmm0
0x18004e3be  test    rcx, rcx
0x18004e3c1  jz      short loc_18004E3CF
0x18004e3c3  mov     rax, rcx
0x18004e3c6  shr     rax, 10h
0x18004e3ca  movzx   ebx, ax
0x18004e3cd  jmp     short loc_18004E3D2
0x18004e3cf  mov     rbx, r13
0x18004e3d2  call    cs:__imp_GetCurrentProcessId
0x18004e3d8  mov     dword ptr [rsp+60h+var_30], r15d
0x18004e3dd  lea     r9, aSpquerycontext_2; "SpQueryContextAttributes called pid:0x%"...
0x18004e3e4  mov     [rsp+60h+var_38], rbx
0x18004e3e9  lea     rdx, aSpquerycontext_1; "SpQueryContextAttributesOld"
0x18004e3f0  mov     r8d, 0FEDh
0x18004e3f6  mov     [rsp+60h+var_40], eax
0x18004e3fa  mov     ecx, 7
0x18004e3ff  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004e404  lea     r8, [rbp+arg_0]; struct _KERB_CONTEXT **
0x18004e408  xor     edx, edx; unsigned __int8
0x18004e40a  mov     rcx, r12; unsigned __int64
0x18004e40d  call    ?KerbReferenceContextByLsaHandle@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z; KerbReferenceContextByLsaHandle(unsigned __int64,uchar,_KERB_CONTEXT * *)
0x18004e412  mov     r14, [rbp+arg_0]
0x18004e416  mov     edi, eax
0x18004e418  test    eax, eax
0x18004e41a  jns     short loc_18004E45E
0x18004e41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e423  lea     rax, WPP_GLOBAL_Control
0x18004e42a  cmp     rcx, rax
0x18004e42d  jz      loc_18004EC3B
0x18004e433  test    byte ptr [rcx+1Ch], 1
0x18004e437  jz      loc_18004EC3B
0x18004e43d  mov     rcx, [rcx+10h]
0x18004e441  lea     r8, WPP_a1119ca399823668ae16bae9ee423caf_Traceguids
0x18004e448  mov     edx, 19h
0x18004e44d  mov     [rsp+60h+var_40], edi
0x18004e451  mov     r9, r12
0x18004e454  call    WPP_SF_qD
0x18004e459  jmp     loc_18004EC3B
0x18004e45e  cmp     r15d, 25h; switch 38 cases
0x18004e462  ja      def_18004E482; jumptable 000000018004E482 default case, cases 4,6-8,11,13,15,16,19,20,22-26,28-36
0x18004e468  lea     rdx, __ImageBase
0x18004e46f  movzx   eax, ds:(byte_18004ECF4 - 180000000h)[rdx+r15]
0x18004e478  mov     ecx, ds:(jpt_18004E482 - 180000000h)[rdx+rax*4]
0x18004e47f  add     rcx, rdx
0x18004e482  jmp     rcx; switch jump
0x18004e484  test    byte ptr [r14+0C4h], 10h; jumptable 000000018004E482 case 0
0x18004e48c  lea     rax, dword_1801400A0
0x18004e493  lea     r15, dword_1801400D0
0x18004e49a  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x18004e49e  cmovz   r15, rax
0x18004e4a2  lea     rcx, pszPackageName; "Kerberos"
0x18004e4a9  call    cs:__imp_QuerySecurityPackageInfoW
0x18004e4af  mov     edi, eax
0x18004e4b1  test    eax, eax
0x18004e4b3  js      loc_18004EC3B
0x18004e4b9  mov     rax, [rbp+ppPackageInfo]
0x18004e4bd  mov     ecx, [rax+8]
0x18004e4c0  mov     eax, r13d
0x18004e4c3  mov     [rsi], ecx
0x18004e4c5  mov     r13d, 40000000h
0x18004e4cb  mov     ecx, [r14+0C0h]
0x18004e4d2  test    ecx, 600h
0x18004e4d8  cmovnz  r13d, eax
0x18004e4dc  test    ecx, 1001Ch
0x18004e4e2  jz      short loc_18004E518
0x18004e4e4  mov     eax, [r14+94h]
0x18004e4eb  sub     eax, 11h
0x18004e4ee  cmp     eax, 1
0x18004e4f1  jbe     short loc_18004E50F
0x18004e4f3  lea     r8, [rsi+4]; unsigned int *
0x18004e4f7  mov     edx, 16h; unsigned int
0x18004e4fc  mov     rcx, r15; struct gss_OID_desc_struct *
0x18004e4ff  call    ?g_token_size@@YAJPEAUgss_OID_desc_struct@@IPEAK@Z; g_token_size(gss_OID_desc_struct *,uint,ulong *)
0x18004e504  mov     edi, eax
0x18004e506  test    eax, eax
0x18004e508  jns     short loc_18004E51F
0x18004e50a  jmp     loc_18004EC3B
0x18004e50f  mov     dword ptr [rsi+4], 1Ch
0x18004e516  jmp     short loc_18004E51F
0x18004e518  mov     dword ptr [rsi+4], 4
0x18004e51f  mov     ecx, [r14+0C0h]
0x18004e526  mov     eax, ecx
0x18004e528  and     eax, 210h
0x18004e52d  cmp     eax, 200h
0x18004e532  jz      loc_18004E604
0x18004e538  bt      ecx, 12h
0x18004e53c  jb      loc_18004E604
0x18004e542  mov     ecx, [r14+94h]
0x18004e549  lea     eax, [rcx-11h]
0x18004e54c  cmp     eax, 1
0x18004e54f  jbe     loc_18004E5EB
0x18004e555  lea     eax, [rcx-1]
0x18004e558  mov     ebx, 0FFFFFF7Ch
0x18004e55d  cmp     eax, 2
0x18004e560  jbe     short loc_18004E574
0x18004e562  cmp     ecx, ebx
0x18004e564  jz      short loc_18004E574
0x18004e566  xor     ebx, ebx
0x18004e568  cmp     ecx, 17h
0x18004e56b  setz    bl
0x18004e56e  add     ebx, 0FFFFFF73h
0x18004e574  lea     rdx, [rbp+var_20]
0x18004e578  mov     ecx, ebx
0x18004e57a  call    cs:__imp_CDLocateCSystem
0x18004e580  mov     edi, eax
0x18004e582  test    eax, eax
0x18004e584  jns     short loc_18004E5B1
0x18004e586  mov     dword ptr [rsp+60h+var_38], eax
0x18004e58a  lea     r9, aFailedToLoadDC_0; "Failed to load %d crypt system: 0x%x"
0x18004e591  mov     r8d, 1077h
0x18004e597  mov     [rsp+60h+var_40], ebx
0x18004e59b  lea     rdx, aSpquerycontext_1; "SpQueryContextAttributesOld"
0x18004e5a2  mov     ecx, 1
0x18004e5a7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004e5ac  jmp     loc_18004EC3B
0x18004e5b1  mov     rax, [rbp+var_20]
0x18004e5b5  lea     r8, [rbp+arg_0]; unsigned int *
0x18004e5b9  mov     rcx, r15; struct gss_OID_desc_struct *
0x18004e5bc  mov     edx, [rax+4]
0x18004e5bf  mov     [rsi+8], edx
0x18004e5c2  lea     edx, [r13+1Eh]; unsigned int
0x18004e5c6  mov     dword ptr [rbp+arg_0], edx
0x18004e5c9  call    ?g_token_size@@YAJPEAUgss_OID_desc_struct@@IPEAK@Z; g_token_size(gss_OID_desc_struct *,uint,ulong *)
0x18004e5ce  mov     edi, eax
0x18004e5d0  test    eax, eax
0x18004e5d2  js      loc_18004EC3B
0x18004e5d8  mov     eax, dword ptr [rbp+arg_0]
0x18004e5db  mov     ecx, 0Ch
0x18004e5e0  sub     eax, r13d
0x18004e5e3  mov     [rsi+rcx], eax
0x18004e5e6  jmp     loc_18004EC3B
0x18004e5eb  mov     ecx, 0Ch
0x18004e5f0  mov     dword ptr [rsi+8], 1
0x18004e5f7  mov     eax, 4Ch ; 'L'
0x18004e5fc  mov     [rsi+rcx], eax
0x18004e5ff  jmp     loc_18004EC3B
0x18004e604  mov     dword ptr [rsi+8], 0
0x18004e60b  mov     rcx, rsi
0x18004e60e  mov     esi, 0Ch
0x18004e613  xor     eax, eax
0x18004e615  mov     [rsi+rcx], eax
0x18004e618  jmp     loc_18004EC3B
0x18004e61d  mov     ecx, [r14+98h]; jumptable 000000018004E482 case 9
0x18004e624  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18004e62b  mov     [rsi], ecx
0x18004e62d  mov     rax, [rax]
0x18004e630  test    ecx, ecx
0x18004e632  jz      short loc_18004E661
0x18004e634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e639  mov     [rsi+8], rax
0x18004e63d  test    rax, rax
0x18004e640  jz      loc_18004E6F9
0x18004e646  mov     r8d, [r14+98h]; Size
0x18004e64d  mov     rcx, rax; void *
0x18004e650  mov     rdx, [r14+0A0h]; Src
0x18004e657  call    memcpy_0
0x18004e65c  jmp     loc_18004EC3B
0x18004e661  mov     ecx, 1
0x18004e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e66b  mov     [rsi+8], rax
0x18004e66f  test    rax, rax
0x18004e672  jz      loc_18004E6F9
0x18004e678  mov     [rax], r13b
0x18004e67b  jmp     loc_18004EC3B
0x18004e680  mov     rcx, [r14+40h]; jumptable 000000018004E482 case 1
0x18004e684  mov     edx, 40h ; '@'; Ch
0x18004e689  call    cs:__imp_wcschr
0x18004e68f  lea     rdx, [r14+38h]; struct _UNICODE_STRING *
0x18004e693  test    rax, rax
0x18004e696  jz      short loc_18004E6E8
0x18004e698  lea     rcx, [rbp+Src]; struct _UNICODE_STRING *
0x18004e69c  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18004e6a1  mov     edi, eax
0x18004e6a3  test    eax, eax
0x18004e6a5  js      loc_18004EC3B
0x18004e6ab  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18004e6b2  movzx   ebx, word ptr [rbp+Src]
0x18004e6b6  mov     rax, [rax]
0x18004e6b9  lea     ecx, [rbx+2]
0x18004e6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6c1  mov     r15, [rbp+Src+8]
0x18004e6c5  mov     [rsi], rax
0x18004e6c8  test    rax, rax
0x18004e6cb  jz      short loc_18004E703
0x18004e6cd  mov     r8d, ebx; Size
0x18004e6d0  mov     rdx, r15; Src
0x18004e6d3  mov     rcx, rax; void *
0x18004e6d6  call    memcpy_0
0x18004e6db  mov     rcx, [rsi]
0x18004e6de  shr     rbx, 1
0x18004e6e1  mov     [rcx+rbx*2], r13w
0x18004e6e6  jmp     short loc_18004E708
0x18004e6e8  lea     rcx, [r14+48h]
0x18004e6ec  lea     r8, [rbp+Src]
0x18004e6f0  call    KerbBuildFullServiceName
0x18004e6f5  test    eax, eax
0x18004e6f7  jz      short loc_18004E6AB
0x18004e6f9  mov     edi, 0C000009Ah
0x18004e6fe  jmp     loc_18004EC3B
0x18004e703  mov     edi, 0C000009Ah
0x18004e708  test    r15, r15
0x18004e70b  jz      loc_18004EC3B
0x18004e711  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18004e718  mov     rcx, r15; hMem
0x18004e71b  jnz     short loc_18004E732
0x18004e71d  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18004e724  mov     rax, [rax+30h]
0x18004e728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e72d  jmp     loc_18004EC3B
0x18004e732  call    cs:__imp_LocalFree
0x18004e738  jmp     loc_18004EC3B
0x18004e73d  lea     rdx, [r14+38h]; jumptable 000000018004E482 case 3
0x18004e741  lea     rcx, [r14+48h]
0x18004e745  lea     r8, [rbp+Src]
0x18004e749  call    KerbBuildFullServiceName
0x18004e74e  test    eax, eax
0x18004e750  jz      short loc_18004E75C
0x18004e752  mov     edi, 0C000009Ah
0x18004e757  jmp     loc_18004EC3B
0x18004e75c  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18004e763  movzx   ebx, word ptr [rbp+Src]
0x18004e767  mov     dword ptr [rsi], 1
0x18004e76d  mov     rax, [rax]
0x18004e770  lea     ecx, [rbx+2]
0x18004e773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e778  mov     r15, [rbp+Src+8]
0x18004e77c  mov     [rsi+8], rax
0x18004e780  test    rax, rax
0x18004e783  jz      loc_18004E703
0x18004e789  mov     r8d, ebx; Size
0x18004e78c  mov     rdx, r15; Src
0x18004e78f  mov     rcx, rax; void *
0x18004e792  call    memcpy_0
0x18004e797  mov     rcx, [rsi+8]
0x18004e79b  shr     rbx, 1
0x18004e79e  mov     [rcx+rbx*2], r13w
0x18004e7a3  jmp     loc_18004E708
0x18004e7a8  test    rsi, rsi; jumptable 000000018004E482 case 17
0x18004e7ab  jnz     short loc_18004E7B7
0x18004e7ad  mov     edi, 0C000000Dh
0x18004e7b2  jmp     loc_18004EC3B
0x18004e7b7  mov     [rsi+8], r13
0x18004e7bb  cmp     [r14+158h], r13
0x18004e7c2  jnz     short loc_18004E7CC
0x18004e7c4  mov     [rsi], r13d
0x18004e7c7  jmp     loc_18004EC3B
0x18004e7cc  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18004e7d3  mov     ecx, [r14+160h]
0x18004e7da  mov     rax, [rax]
0x18004e7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7e2  mov     [rsi+8], rax
0x18004e7e6  test    rax, rax
0x18004e7e9  jz      loc_18004E6F9
0x18004e7ef  mov     r8d, [r14+160h]; Size
0x18004e7f6  mov     rcx, rax; void *
0x18004e7f9  mov     rdx, [r14+158h]; Src
0x18004e800  call    memcpy_0
0x18004e805  mov     eax, [r14+160h]
0x18004e80c  mov     [rsi], eax
0x18004e80e  jmp     loc_18004EC3B
0x18004e813  test    rsi, rsi; jumptable 000000018004E482 case 27
0x18004e816  jnz     short loc_18004E822
0x18004e818  mov     edi, 0C000000Dh
0x18004e81d  jmp     loc_18004EC3B
0x18004e822  cmp     [r14+1A0h], r13
0x18004e829  jz      short loc_18004E88A
0x18004e82b  mov     eax, [r14+1A8h]
0x18004e832  mov     ebx, 7FFEh
0x18004e837  shr     eax, 1
0x18004e839  cmp     eax, ebx
0x18004e83b  ja      short loc_18004E843
0x18004e83d  mov     ebx, eax
0x18004e83f  test    eax, eax
0x18004e841  jz      short loc_18004E88A
0x18004e843  mov     rax, cs:?UserFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * UserFunctions
0x18004e84a  lea     ecx, ds:2[rbx*2]
0x18004e851  mov     rax, [rax]
0x18004e854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e859  mov     [rsi], rax
0x18004e85c  test    rax, rax
  ... truncated ...
```
