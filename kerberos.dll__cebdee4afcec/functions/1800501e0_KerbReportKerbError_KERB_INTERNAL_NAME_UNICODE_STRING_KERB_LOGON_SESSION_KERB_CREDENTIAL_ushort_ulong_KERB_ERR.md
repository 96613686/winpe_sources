# KerbReportKerbError(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,ushort *,ulong,KERB_ERROR *,ulong,KERB_EXT_ERROR *,uchar)

- ea: `0x1800501e0`
- end: `0x18005092b`
- name: `?KerbReportKerbError@@YAXPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@PEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAGKPEAUKERB_ERROR@@KPEAUKERB_EXT_ERROR@@E@Z`
- size: `1867`
- prototype: `void __noreturn(struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, unsigned __int16 *, unsigned int, struct KERB_ERROR *, unsigned int, struct KERB_EXT_ERROR *, unsigned __int8)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180019678`
- `0x180021574`
- `0x180042a40`
- `0x1800b1618`
- `0x1800cdc30`
- `0x1800ce114`

## callees

- `0x180012750`
- `0x180015740`
- `0x1800163a0`
- `0x18003a044`
- `0x1800501e0`
- `0x180050fe0`
- `0x180070680`
- `0x18007108c`
- `0x1800710ec`
- `0x1800922d4`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005082d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050856`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005082d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050856`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508fb`
- `ntdll!NtClose` at `0x1800507db`
- `ntdll!NtClose` at `0x1800507db`
- `ntdll!NtOpenThreadToken` at `0x180050340`
- `ntdll!NtOpenThreadToken` at `0x180050340`
- `ntdll!RtlEnterCriticalSection` at `0x180050393`
- `ntdll!RtlEnterCriticalSection` at `0x180050393`
- `ntdll!NtSetInformationThread` at `0x180050379`
- `ntdll!NtSetInformationThread` at `0x1800507d0`
- `ntdll!NtSetInformationThread` at `0x180050379`
- `ntdll!NtSetInformationThread` at `0x1800507d0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503af`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503af`

## pseudocode

```c
void __fastcall __noreturn KerbReportKerbError(
        struct _KERB_INTERNAL_NAME *a1,
        struct _UNICODE_STRING *a2,
        struct _RTL_CRITICAL_SECTION *a3,
        struct _KERB_CREDENTIAL *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        struct KERB_ERROR *a7,
        unsigned int a8,
        struct KERB_EXT_ERROR *a9,
        unsigned __int8 a10)
{
  int v10; // r13d
  NTSTATUS v14; // eax
  int v15; // eax
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  int v17; // ebx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rax
  CHAR *v21; // rax
  const wchar_t *v22; // r14
  const wchar_t *v23; // rbx
  CHAR *v24; // rax
  HLOCAL v25; // r14
  HLOCAL v26; // r12
  HLOCAL v27; // r13
  HLOCAL v28; // r15
  HLOCAL v29; // rbx
  HLOCAL v30; // rdi
  unsigned __int16 *v31; // rax
  __int64 v32; // rdx
  void *v33; // r8
  unsigned __int64 v34; // rax
  __int64 v35; // rcx
  bool v36; // al
  int v37; // ecx
  __int64 v38; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v39; // [rsp+28h] [rbp-D8h]
  void *v40; // [rsp+30h] [rbp-D0h]
  __int64 v41; // [rsp+38h] [rbp-C8h]
  __int64 v42; // [rsp+40h] [rbp-C0h]
  __int64 v43; // [rsp+48h] [rbp-B8h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  struct _STRING v46; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 ThreadInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _STRING v49; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v50[2]; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL v52[2]; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL v53[2]; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v54[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v55; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v56[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v57; // [rsp+120h] [rbp+20h]
  __int128 v58; // [rsp+130h] [rbp+30h]
  __int128 v59; // [rsp+140h] [rbp+40h]
  __int128 v60; // [rsp+150h] [rbp+50h]
  __int128 v61; // [rsp+160h] [rbp+60h]
  __int128 v62; // [rsp+170h] [rbp+70h]
  wchar_t v63[8]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v64; // [rsp+190h] [rbp+90h]
  wchar_t v65[8]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v66; // [rsp+1A8h] [rbp+A8h]
  wchar_t v67[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v68; // [rsp+1C0h] [rbp+C0h]
  __int128 v69; // [rsp+1D0h] [rbp+D0h]
  __int128 v70; // [rsp+1E0h] [rbp+E0h]
  __int128 v71; // [rsp+1F0h] [rbp+F0h]
  __int128 v72; // [rsp+200h] [rbp+100h]
  int v73; // [rsp+210h] [rbp+110h]
  wchar_t v74[8]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v75; // [rsp+230h] [rbp+130h]
  __int128 v76; // [rsp+240h] [rbp+140h]
  __int128 v77; // [rsp+250h] [rbp+150h]
  __int128 v78; // [rsp+260h] [rbp+160h]
  __int128 v79; // [rsp+270h] [rbp+170h]
  int v80; // [rsp+280h] [rbp+180h]
  wchar_t Buffer[128]; // [rsp+290h] [rbp+190h] BYREF

  v10 = a8;
  v73 = 0;
  v80 = 0;
  v66 = 0;
  v64 = 0;
  *(_OWORD *)v50 = 0;
  *(_OWORD *)v51 = 0;
  v55 = 0;
  *(_OWORD *)v52 = 0;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v53 = 0;
  *(_OWORD *)v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  *(_OWORD *)v65 = 0;
  *(_OWORD *)v63 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v45 = 0;
  v49 = 0;
  TokenHandle = 0;
  *(_OWORD *)v56 = 0;
  ThreadInformation = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  if ( !a10 && !KerbGlobalLoggingLevel )
    return;
  v14 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( v14 >= 0 )
  {
    if ( TokenHandle
      && NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) < 0 )
    {
      goto LABEL_41;
    }
  }
  else
  {
    if ( v14 != -1073741700 )
      goto LABEL_41;
    TokenHandle = 0;
  }
  if ( !a3
    || (RtlEnterCriticalSection(a3 + 2),
        v15 = KerbBuildFullServiceName(&a3[3].OwningThread, &a3[3], hMem),
        v16 = a3 + 2,
        v17 = v15,
        RtlLeaveCriticalSection(v16),
        !v17) )
  {
    if ( a9 )
      swprintf_s(Buffer, 0x7Fu, L"0x%x KLIN(%x)", *(unsigned int *)a9, *((_DWORD *)a9 + 1));
    if ( a1 && a2 )
      KerbConvertKdcNameToString((struct _UNICODE_STRING *)v53, a1, a2);
    swprintf_s(v65, 0xBu, L"%x", a6);
    if ( !a7 )
    {
      swprintf_s(v63, 0xBu, L"0x%x", a8);
      goto LABEL_43;
    }
    swprintf_s(v63, 0xBu, L"0x%x", *((unsigned int *)a7 + 13));
    v18 = -1;
    if ( (*(_BYTE *)a7 & 0x20) == 0 )
      goto LABEL_100;
    *(_DWORD *)(&v46.MaximumLength + 1) = 0;
    if ( a7 != (struct KERB_ERROR *)-56LL )
    {
      v19 = *((_QWORD *)a7 + 7);
      if ( v19 )
      {
        v46.Buffer = (PCHAR)*((_QWORD *)a7 + 7);
        v20 = -1;
        do
          ++v20;
        while ( *(_BYTE *)(v19 + v20) );
        if ( (unsigned int)v20 <= 0xFFFD )
        {
          v46.Length = v20;
          v46.MaximumLength = v20 + 1;
          if ( !(unsigned int)KerbStringToUnicodeString((struct _UNICODE_STRING *)v50, &v46) )
          {
LABEL_100:
            v21 = (CHAR *)*((_QWORD *)a7 + 10);
            if ( !v21 )
              goto LABEL_101;
            *(_DWORD *)(&v46.MaximumLength + 1) = 0;
            v46.Buffer = v21;
            do
              ++v18;
            while ( v21[v18] );
            if ( (unsigned int)v18 <= 0xFFFD )
            {
              v46.Length = v18;
              v46.MaximumLength = v18 + 1;
              if ( !(unsigned int)KerbStringToUnicodeString(&v55, &v46) )
              {
LABEL_101:
                if ( ((*(_BYTE *)a7 & 0x10) == 0
                   || !(unsigned int)KerbConvertPrincipalNameToString(v51, &v45, (char *)a7 + 64))
                  && !(unsigned int)KerbConvertPrincipalNameToString(v52, &v45, (char *)a7 + 88) )
                {
                  v22 = L"Z";
                  if ( *(char *)a7 < 0 )
                  {
                    v23 = L"Z";
                    if ( !*((_BYTE *)a7 + 22) )
                      v23 = &Class;
                    LODWORD(v38) = *((unsigned __int8 *)a7 + 17);
                    swprintf_s(
                      v67,
                      0x31u,
                      L"%d:%d:%d.%04d %d/%d/%d %ws",
                      *((unsigned __int8 *)a7 + 16),
                      v38,
                      *((unsigned __int8 *)a7 + 18),
                      *((unsigned __int16 *)a7 + 10),
                      *((unsigned __int8 *)a7 + 14),
                      *((unsigned __int8 *)a7 + 15),
                      *((unsigned __int16 *)a7 + 6),
                      v23);
                  }
                  if ( !*((_BYTE *)a7 + 42) )
                    v22 = &Class;
                  LODWORD(v43) = *((unsigned __int16 *)a7 + 16);
                  LODWORD(v42) = *((unsigned __int8 *)a7 + 35);
                  LODWORD(v41) = *((unsigned __int8 *)a7 + 34);
                  LODWORD(v40) = *((unsigned __int16 *)a7 + 20);
                  LODWORD(v39) = *((unsigned __int8 *)a7 + 38);
                  LODWORD(v38) = *((unsigned __int8 *)a7 + 37);
                  swprintf_s(
                    v74,
                    0x31u,
                    L"%d:%d:%d.%04d %d/%d/%d %ws",
                    *((unsigned __int8 *)a7 + 36),
                    v38,
                    v39,
                    v40,
                    v41,
                    v42,
                    v43,
                    v22);
                  if ( (*(_BYTE *)a7 & 8) == 0
                    || *((_DWORD *)a7 + 26) >= 0x7FFFu
                    || (v24 = (CHAR *)*((_QWORD *)a7 + 14),
                        v49.Length = *((_DWORD *)a7 + 26),
                        v49.Buffer = v24,
                        !(unsigned int)KerbStringToUnicodeString((struct _UNICODE_STRING *)v54, &v49)) )
                  {
                    v10 = *((_DWORD *)a7 + 13);
LABEL_43:
                    v29 = hMem[1];
                    v56[1] = v67;
                    v56[0] = (unsigned __int16 *)hMem[1];
                    *(_QWORD *)&v57 = v74;
                    *((_QWORD *)&v57 + 1) = v63;
                    v31 = KerbErrorToString(v10);
                    v25 = v50[1];
                    v26 = v51[1];
                    v27 = v52[1];
                    v30 = v53[1];
                    v28 = v54[1];
                    *((_QWORD *)&v58 + 1) = Buffer;
                    *((_QWORD *)&v62 + 1) = v65;
                    *(_QWORD *)&v60 = v55.Buffer;
                    *(_QWORD *)&v58 = v31;
                    *(HLOCAL *)&v59 = v50[1];
                    *((HLOCAL *)&v59 + 1) = v51[1];
                    *((HLOCAL *)&v60 + 1) = v52[1];
                    *(HLOCAL *)&v61 = v53[1];
                    *((HLOCAL *)&v61 + 1) = v54[1];
                    *(_QWORD *)&v62 = a5;
                    if ( !v29 )
                      v56[0] = (unsigned __int16 *)&Class;
                    if ( !v31 )
                      *(_QWORD *)&v58 = &Class;
                    if ( !v50[1] )
                      *(_QWORD *)&v59 = &Class;
                    if ( !v51[1] )
                      *((_QWORD *)&v59 + 1) = &Class;
                    if ( !v55.Buffer )
                      *(_QWORD *)&v60 = &Class;
                    if ( !v52[1] )
                      *((_QWORD *)&v60 + 1) = &Class;
                    if ( !v53[1] )
                      *(_QWORD *)&v61 = &Class;
                    if ( !v54[1] )
                      *((_QWORD *)&v61 + 1) = &Class;
                    if ( !a5 )
                      *(_QWORD *)&v62 = &Class;
                    v34 = (unsigned int)(*((_DWORD *)a7 + 13) - 25);
                    v36 = 0;
                    if ( (unsigned int)v34 <= 0x2C )
                    {
                      v35 = 0x100008000001LL;
                      if ( _bittest64(&v35, v34) )
                        v36 = 1;
                    }
                    v37 = 4;
                    if ( !v36 )
                      v37 = 1;
                    KerbWriteEventlog(v37, v32, -2147483645, 0xEu, v32, v56, v33);
                    goto LABEL_68;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  v25 = v50[1];
  v26 = v51[1];
  v27 = v52[1];
  v28 = v54[1];
  v29 = hMem[1];
  v30 = v53[1];
LABEL_68:
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    NtClose(TokenHandle);
  }
  if ( v29 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v29);
    else
      LocalFree(v29);
  }
  if ( v25 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v25);
    else
      LocalFree(v25);
  }
  if ( v26 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v26);
    else
      LocalFree(v26);
  }
  if ( v55.Buffer )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v55.Buffer);
  }
  if ( v27 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v27);
    else
      LocalFree(v27);
  }
  if ( v28 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v28);
    else
      LocalFree(v28);
  }
  if ( v30 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v30);
    else
      LocalFree(v30);
  }
}

```

## disassembly

```asm
0x1800501e0  mov     [rsp-8+arg_18], rbx
0x1800501e5  push    rbp
0x1800501e6  push    rsi
0x1800501e7  push    rdi
0x1800501e8  push    r12
0x1800501ea  push    r13
0x1800501ec  push    r14
0x1800501ee  push    r15
0x1800501f0  lea     rbp, [rsp-2A0h]
0x1800501f8  sub     rsp, 3A0h
0x1800501ff  mov     rax, cs:__security_cookie
0x180050206  xor     rax, rsp
0x180050209  mov     [rbp+2D0h+var_40], rax
0x180050210  mov     rsi, [rbp+2D0h+arg_30]
0x180050217  xorps   xmm0, xmm0
0x18005021a  mov     r14, [rbp+2D0h+arg_40]
0x180050221  xorps   xmm1, xmm1
0x180050224  mov     r13d, [rbp+2D0h+arg_38]
0x18005022b  xor     eax, eax
0x18005022d  mov     rbx, r8
0x180050230  mov     [rbp+2D0h+var_1C0], eax
0x180050236  mov     r12, rdx
0x180050239  mov     [rbp+2D0h+var_150], eax
0x18005023f  mov     r15, rcx
0x180050242  mov     [rbp+2D0h+var_228], rax
0x180050249  xor     edx, edx; Val
0x18005024b  mov     [rbp+2D0h+var_240], rax
0x180050252  mov     r8d, 100h; Size
0x180050258  lea     rcx, [rbp+2D0h+Buffer]; void *
0x18005025f  movups  xmmword ptr [rbp+2D0h+var_328], xmm0
0x180050263  movups  xmmword ptr [rbp+2D0h+var_318], xmm1
0x180050267  movups  xmmword ptr [rbp+2D0h+var_2D8.Length], xmm0
0x18005026b  movups  xmmword ptr [rbp+2D0h+var_308], xmm1
0x18005026f  movups  xmmword ptr [rbp+2D0h+var_2E8], xmm0
0x180050273  movups  xmmword ptr [rbp+2D0h+hMem], xmm1
0x180050277  movups  xmmword ptr [rbp+2D0h+var_2F8], xmm0
0x18005027b  movups  xmmword ptr [rbp+2D0h+var_220], xmm1
0x180050282  movups  [rbp+2D0h+var_210], xmm1
0x180050289  movups  [rbp+2D0h+var_200], xmm1
0x180050290  movups  [rbp+2D0h+var_1F0], xmm1
0x180050297  movups  [rbp+2D0h+var_1E0], xmm1
0x18005029e  movups  [rbp+2D0h+var_1D0], xmm1
0x1800502a5  movups  xmmword ptr [rbp+2D0h+var_1B0], xmm0
0x1800502ac  movups  [rbp+2D0h+var_1A0], xmm0
0x1800502b3  movups  [rbp+2D0h+var_190], xmm0
0x1800502ba  movups  [rbp+2D0h+var_180], xmm0
0x1800502c1  movups  [rbp+2D0h+var_170], xmm0
0x1800502c8  movups  [rbp+2D0h+var_160], xmm0
0x1800502cf  movups  xmmword ptr [rbp+2D0h+var_238], xmm0
0x1800502d6  movups  xmmword ptr [rbp+2D0h+var_250], xmm1
0x1800502dd  call    memset_0
0x1800502e2  xorps   xmm1, xmm1
0x1800502e5  xor     edi, edi
0x1800502e7  xorps   xmm0, xmm0
0x1800502ea  mov     [rsp+3D0h+var_368], edi
0x1800502ee  movups  xmmword ptr [rbp+2D0h+var_338.Length], xmm0
0x1800502f2  mov     [rsp+3D0h+TokenHandle], rdi
0x1800502f7  movups  xmmword ptr [rbp+2D0h+var_2C0], xmm1
0x1800502fb  mov     [rbp+2D0h+ThreadInformation], rdi
0x1800502ff  movups  [rbp+2D0h+var_2B0], xmm1
0x180050303  movups  [rbp+2D0h+var_2A0], xmm1
0x180050307  movups  [rbp+2D0h+var_290], xmm1
0x18005030b  movups  [rbp+2D0h+var_280], xmm1
0x18005030f  movups  [rbp+2D0h+var_270], xmm1
0x180050313  movups  [rbp+2D0h+var_260], xmm1
0x180050317  cmp     [rbp+2D0h+arg_48], dil
0x18005031e  jnz     short loc_18005032C
0x180050320  cmp     cs:?KerbGlobalLoggingLevel@@3KA, edi
0x180050326  jz      loc_180050901
0x18005032c  lea     r9, [rsp+3D0h+TokenHandle]; TokenHandle
0x180050331  mov     r8b, 1; OpenAsSelf
0x180050334  mov     edx, 0Ch; DesiredAccess
0x180050339  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180050340  call    cs:__imp_NtOpenThreadToken
0x180050346  test    eax, eax
0x180050348  jns     short loc_18005035C
0x18005034a  cmp     eax, 0C000007Ch
0x18005034f  jnz     loc_180050654
0x180050355  mov     [rsp+3D0h+TokenHandle], rdi
0x18005035a  jmp     short loc_180050387
0x18005035c  cmp     [rsp+3D0h+TokenHandle], rdi
0x180050361  jz      short loc_180050387
0x180050363  mov     r9d, 8; ThreadInformationLength
0x180050369  lea     r8, [rbp+2D0h+ThreadInformation]; ThreadInformation
0x18005036d  mov     edx, 5; ThreadInformationClass
0x180050372  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180050379  call    cs:__imp_NtSetInformationThread
0x18005037f  test    eax, eax
0x180050381  js      loc_180050654
0x180050387  test    rbx, rbx
0x18005038a  jz      short loc_1800503BD
0x18005038c  lea     rdi, [rbx+50h]
0x180050390  mov     rcx, rdi; CriticalSection
0x180050393  call    cs:__imp_RtlEnterCriticalSection
0x180050399  lea     rdx, [rbx+78h]
0x18005039d  lea     rcx, [rdx+10h]
0x1800503a1  lea     r8, [rbp+2D0h+hMem]
0x1800503a5  call    KerbBuildFullServiceName
0x1800503aa  mov     rcx, rdi; CriticalSection
0x1800503ad  mov     ebx, eax
0x1800503af  call    cs:__imp_RtlLeaveCriticalSection
0x1800503b5  test    ebx, ebx
0x1800503b7  jnz     loc_180050654
0x1800503bd  test    r14, r14
0x1800503c0  jz      short loc_1800503E5
0x1800503c2  mov     eax, [r14+4]
0x1800503c6  lea     r8, a0xXKlinX
0x1800503cd  mov     r9d, [r14]
0x1800503d0  lea     rcx, [rbp+2D0h+Buffer]; Buffer
0x1800503d7  mov     edx, 7Fh; BufferCount
0x1800503dc  mov     dword ptr [rsp+3D0h+var_3B0], eax
0x1800503e0  call    swprintf_s
0x1800503e5  test    r15, r15
0x1800503e8  jz      short loc_1800503FE
0x1800503ea  test    r12, r12
0x1800503ed  jz      short loc_1800503FE
0x1800503ef  mov     r8, r12; struct _UNICODE_STRING *
0x1800503f2  lea     rcx, [rbp+2D0h+var_2F8]; struct _UNICODE_STRING *
0x1800503f6  mov     rdx, r15; struct _KERB_INTERNAL_NAME *
0x1800503f9  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z
0x1800503fe  mov     r9d, [rbp+2D0h+arg_28]
0x180050405  lea     r8, asc_18010D80C
0x18005040c  mov     edx, 0Bh; BufferCount
0x180050411  lea     rcx, [rbp+2D0h+var_238]; Buffer
0x180050418  call    swprintf_s
0x18005041d  lea     rdi, Class
0x180050424  mov     edx, 0Bh; BufferCount
0x180050429  lea     r8, a0xX
0x180050430  lea     rcx, [rbp+2D0h+var_250]; Buffer
0x180050437  test    rsi, rsi
0x18005043a  jz      loc_180050671
0x180050440  mov     r9d, [rsi+34h]
0x180050444  call    swprintf_s
0x180050449  test    byte ptr [rsi], 20h
0x18005044c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180050453  jz      short loc_1800504B7
0x180050455  lea     rcx, [rsi+38h]
0x180050459  mov     dword ptr [rsp+3D0h+var_360+4], 0
0x180050461  test    rcx, rcx
0x180050464  jz      loc_180050654
0x18005046a  mov     rcx, [rcx]
0x18005046d  test    rcx, rcx
0x180050470  jz      loc_180050654
0x180050476  mov     [rsp+3D0h+var_360.Buffer], rcx
0x18005047b  mov     rax, rbx
0x18005047e  xchg    ax, ax
0x180050480  inc     rax
0x180050483  cmp     byte ptr [rcx+rax], 0
0x180050487  jnz     short loc_180050480
0x180050489  cmp     eax, 0FFFDh
0x18005048e  ja      loc_180050654
0x180050494  mov     [rsp+3D0h+var_360.Length], ax
0x180050499  lea     rdx, [rsp+3D0h+var_360]; struct _STRING *
0x18005049e  inc     ax
0x1800504a1  lea     rcx, [rbp+2D0h+var_328]; struct _UNICODE_STRING *
0x1800504a5  mov     [rsp+3D0h+var_360.MaximumLength], ax
0x1800504aa  call    ?KerbStringToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAU_STRING@@@Z
0x1800504af  test    eax, eax
0x1800504b1  jnz     loc_180050654
0x1800504b7  mov     rax, [rsi+50h]
0x1800504bb  test    rax, rax
0x1800504be  jz      short loc_180050508
0x1800504c0  mov     dword ptr [rsp+3D0h+var_360+4], 0
0x1800504c8  mov     [rsp+3D0h+var_360.Buffer], rax
0x1800504cd  nop     dword ptr [rax]
0x1800504d0  inc     rbx
0x1800504d3  cmp     byte ptr [rax+rbx], 0
0x1800504d7  jnz     short loc_1800504D0
0x1800504d9  cmp     ebx, 0FFFDh
0x1800504df  ja      loc_180050654
0x1800504e5  mov     [rsp+3D0h+var_360.Length], bx
0x1800504ea  lea     rdx, [rsp+3D0h+var_360]; struct _STRING *
0x1800504ef  inc     bx
0x1800504f2  lea     rcx, [rbp+2D0h+var_2D8]; struct _UNICODE_STRING *
0x1800504f6  mov     [rsp+3D0h+var_360.MaximumLength], bx
0x1800504fb  call    ?KerbStringToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAU_STRING@@@Z
0x180050500  test    eax, eax
0x180050502  jnz     loc_180050654
0x180050508  test    byte ptr [rsi], 10h
0x18005050b  jz      short loc_180050527
0x18005050d  lea     r8, [rsi+40h]
0x180050511  lea     rdx, [rsp+3D0h+var_368]
0x180050516  lea     rcx, [rbp+2D0h+var_318]
0x18005051a  call    KerbConvertPrincipalNameToString
0x18005051f  test    eax, eax
0x180050521  jnz     loc_180050654
0x180050527  lea     r8, [rsi+58h]
0x18005052b  lea     rdx, [rsp+3D0h+var_368]
0x180050530  lea     rcx, [rbp+2D0h+var_308]
0x180050534  call    KerbConvertPrincipalNameToString
0x180050539  test    eax, eax
0x18005053b  jnz     loc_180050654
0x180050541  test    byte ptr [rsi], 80h
0x180050544  lea     r14, aZ
0x18005054b  jz      short loc_1800505AF
0x18005054d  cmp     [rsi+16h], al
0x180050550  mov     rbx, r14
0x180050553  movzx   ecx, byte ptr [rsi+0Fh]
0x180050557  movzx   edx, byte ptr [rsi+0Eh]
0x18005055b  cmovz   rbx, rdi
0x18005055f  movzx   r8d, word ptr [rsi+14h]
0x180050564  movzx   eax, word ptr [rsi+0Ch]
0x180050568  movzx   r10d, byte ptr [rsi+12h]
0x18005056d  movzx   r11d, byte ptr [rsi+11h]
0x180050572  movzx   r9d, byte ptr [rsi+10h]
0x180050577  mov     [rsp+3D0h+var_380], rbx
0x18005057c  mov     dword ptr [rsp+3D0h+var_388], eax
0x180050580  mov     dword ptr [rsp+3D0h+var_390], ecx
0x180050584  lea     rcx, [rbp+2D0h+var_220]; Buffer
0x18005058b  mov     dword ptr [rsp+3D0h+var_398], edx
0x18005058f  mov     edx, 31h ; '1'; BufferCount
0x180050594  mov     dword ptr [rsp+3D0h+var_3A0], r8d
0x180050599  lea     r8, aDDD04dDDDWs
0x1800505a0  mov     dword ptr [rsp+3D0h+var_3A8], r10d
0x1800505a5  mov     dword ptr [rsp+3D0h+var_3B0], r11d
0x1800505aa  call    swprintf_s
0x1800505af  movzx   ecx, byte ptr [rsi+23h]
0x1800505b3  lea     r8, aDDD04dDDDWs
0x1800505ba  cmp     byte ptr [rsi+2Ah], 0
0x1800505be  mov     edx, 31h ; '1'; BufferCount
0x1800505c3  movzx   eax, word ptr [rsi+20h]
0x1800505c7  movzx   r10d, byte ptr [rsi+22h]
0x1800505cc  cmovz   r14, rdi
0x1800505d0  movzx   r11d, word ptr [rsi+28h]
0x1800505d5  movzx   ebx, byte ptr [rsi+26h]
0x1800505d9  movzx   edi, byte ptr [rsi+25h]
0x1800505dd  movzx   r9d, byte ptr [rsi+24h]
0x1800505e2  mov     [rsp+3D0h+var_380], r14
0x1800505e7  mov     dword ptr [rsp+3D0h+var_388], eax
0x1800505eb  mov     dword ptr [rsp+3D0h+var_390], ecx
0x1800505ef  lea     rcx, [rbp+2D0h+var_1B0]; Buffer
0x1800505f6  mov     dword ptr [rsp+3D0h+var_398], r10d
0x1800505fb  mov     dword ptr [rsp+3D0h+var_3A0], r11d
0x180050600  mov     dword ptr [rsp+3D0h+var_3A8], ebx
0x180050604  mov     dword ptr [rsp+3D0h+var_3B0], edi
0x180050608  call    swprintf_s
0x18005060d  test    byte ptr [rsi], 8
0x180050610  jz      short loc_18005063A
0x180050612  mov     ecx, [rsi+68h]
0x180050615  cmp     ecx, 7FFFh
0x18005061b  jnb     short loc_18005063A
0x18005061d  mov     rax, [rsi+70h]
0x180050621  lea     rdx, [rbp+2D0h+var_338]; struct _STRING *
0x180050625  mov     [rbp+2D0h+var_338.Length], cx
0x180050629  lea     rcx, [rbp+2D0h+var_2E8]; struct _UNICODE_STRING *
0x18005062d  mov     [rbp+2D0h+var_338.Buffer], rax
0x180050631  call    ?KerbStringToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAU_STRING@@@Z
0x180050636  test    eax, eax
0x180050638  jnz     short loc_180050654
0x18005063a  xor     edx, edx
0x18005063c  xor     r8d, r8d
0x18005063f  test    byte ptr [rsi], 4
0x180050642  jz      short loc_18005064E
0x180050644  mov     edx, [rsi+78h]
0x180050647  mov     r8, [rsi+80h]
0x18005064e  mov     r13d, [rsi+34h]
0x180050652  jmp     short loc_18005067E
0x180050654  mov     r14, [rbp+2D0h+var_328+8]
0x180050658  mov     r12, [rbp+2D0h+var_318+8]
0x18005065c  mov     r13, [rbp+2D0h+var_308+8]
0x180050660  mov     r15, [rbp+2D0h+var_2E8+8]
0x180050664  mov     rbx, [rbp+2D0h+hMem+8]
0x180050668  mov     rdi, [rbp+2D0h+var_2F8+8]
0x18005066c  jmp     loc_1800507B1
0x180050671  mov     r9d, r13d
0x180050674  call    swprintf_s
0x180050679  xor     edx, edx
0x18005067b  xor     r8d, r8d
0x18005067e  mov     rbx, [rbp+2D0h+hMem+8]
0x180050682  lea     rax, [rbp+2D0h+var_220]
0x180050689  mov     [rbp+2D0h+var_2C0+8], rax
0x18005068d  mov     ecx, r13d; int
0x180050690  lea     rax, [rbp+2D0h+var_1B0]
0x180050697  mov     [rbp+2D0h+var_2C0], rbx
0x18005069b  mov     qword ptr [rbp+2D0h+var_2B0], rax
0x18005069f  lea     rax, [rbp+2D0h+var_250]
0x1800506a6  mov     qword ptr [rbp+2D0h+var_2B0+8], rax
0x1800506aa  call    ?KerbErrorToString@@YAPEAGJ@Z
0x1800506af  mov     r14, [rbp+2D0h+var_328+8]
0x1800506b3  lea     rcx, [rbp+2D0h+Buffer]
0x1800506ba  mov     r12, [rbp+2D0h+var_318+8]
0x1800506be  lea     r10, [rbp+2D0h+var_238]
0x1800506c5  mov     r13, [rbp+2D0h+var_308+8]
0x1800506c9  mov     rdi, [rbp+2D0h+var_2F8+8]
0x1800506cd  mov     r15, [rbp+2D0h+var_2E8+8]
0x1800506d1  mov     r9, [rbp+2D0h+arg_20]
0x1800506d8  mov     qword ptr [rbp+2D0h+var_2A0+8], rcx
0x1800506dc  mov     rcx, [rbp+2D0h+var_2D8.Buffer]
0x1800506e0  mov     qword ptr [rbp+2D0h+var_260+8], r10
0x1800506e4  lea     r10, Class
0x1800506eb  mov     qword ptr [rbp+2D0h+var_280], rcx
0x1800506ef  mov     qword ptr [rbp+2D0h+var_2A0], rax
0x1800506f3  mov     qword ptr [rbp+2D0h+var_290], r14
0x1800506f7  mov     qword ptr [rbp+2D0h+var_290+8], r12
0x1800506fb  mov     qword ptr [rbp+2D0h+var_280+8], r13
0x1800506ff  mov     qword ptr [rbp+2D0h+var_270], rdi
0x180050703  mov     qword ptr [rbp+2D0h+var_270+8], r15
0x180050707  mov     qword ptr [rbp+2D0h+var_260], r9
0x18005070b  test    rbx, rbx
0x18005070e  jnz     short loc_180050714
  ... truncated ...
```
