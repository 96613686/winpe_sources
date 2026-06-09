# KerbCacheLogonInformation(_UNICODE_STRING *,_UNICODE_STRING *,_LM_OWF_PASSWORD *,_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *,_KERB_LOGON_SESSION *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,void *,ulong,void *,ulong,_FIDO_CACHE_BLOB * *)

- ea: `0x18003ca2c`
- end: `0x18003d06a`
- name: `?KerbCacheLogonInformation@@YAJPEAU_UNICODE_STRING@@0PEAU_LM_OWF_PASSWORD@@PEAU_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL@@PEAU_KERB_LOGON_SESSION@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAXK5KPEAPEAU_FIDO_CACHE_BLOB@@@Z`
- size: `1598`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _LM_OWF_PASSWORD *, struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *, struct _KERB_LOGON_SESSION *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO4 *, void *, unsigned int, void *, size_t, struct _FIDO_CACHE_BLOB **)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036ffc`
- `0x180058f14`
- `0x1800819b0`
- `0x1800b72b4`
- `0x1800be9bc`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x180007e80`
- `0x18000b300`
- `0x180039570`
- `0x18003ca2c`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800be880`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003ce17`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003ce17`
- `ntdll!RtlReleaseResource` at `0x18003ce7a`
- `ntdll!RtlReleaseResource` at `0x18003ce7a`
- `ntdll!RtlAcquireResourceShared` at `0x18003ce5b`
- `ntdll!RtlAcquireResourceShared` at `0x18003ce5b`

## string_xrefs

- `0x18003cb19`: `KerbCacheLogonInformation does not support cached logon for reamless workstation\n`
- `0x18003cb26`: `KerbCacheLogonInformation`
- `0x18003cb96`: `KerbCacheLogonInformation`
- `0x18003cbaa`: `KerbCacheLogonInformation logon session is null\n`
- `0x18003cbf3`: `KerbCacheLogonInformation caching MIT princ: logon %wZ\%wZ, validation info account %wZ\%wZ, cred %wZ\%wZ\n`
- `0x18003cdc2`: `Failed to make supplemental credentials for cache\n`
- `0x18003cf22`: `KerbCacheLogonInformation updating NLP Cache entry of %wZ\%wZ, flags %#x %s... \n`
- `0x18003cfb9`: `KerbCacheLogonInformation failed to cache credentials: 0x%x, 0x%x`
- `0x18003cff3`: `KerbBuildFidoCacheBlob failed with 0x%08X\n`

## pseudocode

```c
__int64 __fastcall KerbCacheLogonInformation(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _LM_OWF_PASSWORD *a3,
        struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *a4,
        struct _KERB_LOGON_SESSION *a5,
        unsigned int a6,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a7,
        void *a8,
        unsigned int a9,
        void *a10,
        size_t a11,
        struct _FIDO_CACHE_BLOB **a12)
{
  char *v15; // rdx
  int *v16; // rdi
  int v17; // ecx
  int SupplementalCacheInfo; // ebx
  struct _UNICODE_STRING v19; // xmm0
  char v20; // r15
  unsigned int v21; // eax
  struct _UNICODE_STRING v22; // xmm1
  unsigned __int16 *v23; // r15
  char *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  int v28; // ecx
  unsigned int v29; // eax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  void *v34; // rsp
  void *v35; // rsp
  int *v36; // rax
  __int64 v37; // rbx
  int *v38; // r12
  unsigned __int64 v39; // r15
  unsigned int v40; // eax
  unsigned int v41; // eax
  const char *v42; // rax
  int v43; // esi
  int v44; // eax
  __int64 v46; // [rsp+0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+30h] [rbp-20h]
  int v48; // [rsp+50h] [rbp+0h] BYREF
  __int128 v49; // [rsp+58h] [rbp+8h] BYREF
  struct _UNICODE_STRING *v50; // [rsp+68h] [rbp+18h]
  int v51[4]; // [rsp+70h] [rbp+20h] BYREF
  int v52; // [rsp+80h] [rbp+30h] BYREF
  struct _UNICODE_STRING *v53; // [rsp+88h] [rbp+38h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v54; // [rsp+90h] [rbp+40h]
  void *Src; // [rsp+98h] [rbp+48h] BYREF
  unsigned int Size; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int Size_4; // [rsp+A4h] [rbp+54h]
  __int64 v58; // [rsp+A8h] [rbp+58h]
  struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *v59; // [rsp+B0h] [rbp+60h]
  ULONG v60; // [rsp+B8h] [rbp+68h]
  struct _UNICODE_STRING *v61; // [rsp+C0h] [rbp+70h]
  struct _UNICODE_STRING v62; // [rsp+C8h] [rbp+78h] BYREF
  _QWORD v63[2]; // [rsp+D8h] [rbp+88h] BYREF
  void *v64; // [rsp+E8h] [rbp+98h]
  struct _LM_OWF_PASSWORD *v65; // [rsp+F0h] [rbp+A0h]
  struct _FIDO_CACHE_BLOB **v66; // [rsp+F8h] [rbp+A8h]
  __int64 v67; // [rsp+100h] [rbp+B0h] BYREF
  struct _UNICODE_STRING v68; // [rsp+110h] [rbp+C0h] BYREF
  int v69; // [rsp+120h] [rbp+D0h]
  _OWORD v70[4]; // [rsp+130h] [rbp+E0h] BYREF

  v61 = a2;
  v64 = a10;
  v65 = a3;
  v50 = a1;
  v66 = a12;
  memset_0(&v68, 0, 0x60u);
  memset_0(&v52, 0, 0x40u);
  v15 = 0;
  v63[0] = 4980810;
  v67 = 0;
  v63[1] = L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0";
  v51[0] = 0;
  v16 = 0;
  v48 = 0;
  *(_QWORD *)&v62.Length = 0;
  v49 = 0;
  if ( a5 )
    v17 = (*((_DWORD *)a5 + 226) >> 5) & 1;
  else
    v17 = 0;
  v62.Buffer = 0;
  if ( !BYTE1(KerbGlobalRoles) )
  {
    KerbTracerT::Log(
      2,
      "KerbCacheLogonInformation",
      3644,
      "KerbCacheLogonInformation does not support cached logon for reamless workstation\n");
    SupplementalCacheInfo = -1073741637;
    goto LABEL_65;
  }
  v19 = *a2;
  v20 = a6;
  v21 = a6;
  Size_4 = a6;
  v22 = *a1;
  v68 = v19;
  v70[0] = v22;
  if ( a5 )
  {
    v58 = *((_QWORD *)a5 + 8);
    v21 = a6 | 0x100;
    Size_4 = a6 | 0x100;
  }
  if ( a4 )
  {
    v59 = a4;
    Size_4 = v21 | 0x200;
    v60 = a4->EncryptedCredsSize + 8;
  }
  if ( v17 )
  {
    if ( !a5 )
    {
      KerbTracerT::Log(1, "KerbCacheLogonInformation", 3676, "KerbCacheLogonInformation logon session is null\n");
      SupplementalCacheInfo = -1073741811;
      goto LABEL_65;
    }
    v23 = (unsigned __int16 *)((char *)a5 + 120);
    if ( a7 )
    {
      v24 = (char *)a7 + 208;
      v15 = (char *)a7 + 48;
    }
    else
    {
      v24 = 0;
    }
    KerbTracerT::Log(
      3,
      "KerbCacheLogonInformation",
      3685,
      "KerbCacheLogonInformation caching MIT princ: logon %wZ\\%wZ, validation info account %wZ\\%wZ, cred %wZ\\%wZ\n",
      v61,
      v50,
      v24,
      v15,
      (char *)a5 + 136,
      (char *)a5 + 120);
    v27 = *v23;
    v28 = *((unsigned __int16 *)a5 + 68) + 3;
    Size_4 |= 1u;
    v29 = (v28 & 0xFFFFFFFC) + 32 + ((v27 + 3) & 0xFFFFFFFC);
    v30 = v29;
    LODWORD(v50) = v29;
    if ( v29 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_73;
    v31 = v29 + g_ulAdditionalProbeSize + 8;
    if ( v31 < v29 || !(unsigned int)VerifyStackAvailable(v31, 4294967292LL, v25, v26) )
      goto LABEL_73;
    v32 = v30 + 23;
    if ( v30 + 23 <= v30 + 8 )
      v32 = 0xFFFFFFFFFFFFFF0LL;
    v33 = v32 & 0xFFFFFFFFFFFFFFF0uLL;
    v34 = alloca(v33);
    v35 = alloca(v33);
    v16 = &v48;
    if ( &v46 == (__int64 *)-80LL || (v48 = 1801679955, (v16 = (int *)&v49) == 0) )
    {
LABEL_73:
      if ( v30 + 8 >= v30 )
      {
        v36 = (int *)((__int64 (*)(void))g_pfnAllocate)();
        v16 = v36;
        if ( v36 )
        {
          *v36 = 1885431112;
          v16 = v36 + 2;
        }
      }
    }
    if ( !v16 )
    {
      SupplementalCacheInfo = -1073741670;
      goto LABEL_65;
    }
    v37 = *v23;
    v38 = v16 + 4;
    WORD1(v49) = v37;
    LOWORD(v49) = v37;
    if ( (_WORD)v37 )
    {
      memcpy_0(v16 + 4, *((const void **)a5 + 16), (unsigned int)v37);
      *((_QWORD *)&v49 + 1) = 16;
    }
    else
    {
      *((_QWORD *)&v49 + 1) = 0;
    }
    v39 = (v37 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
    *(_OWORD *)v16 = v49;
    v40 = *((unsigned __int16 *)a5 + 68);
    WORD1(v49) = v40;
    LOWORD(v49) = v40;
    if ( (_WORD)v40 )
    {
      memcpy_0((char *)v38 + v39 + 16, *((const void **)a5 + 18), v40);
      *((_QWORD *)&v49 + 1) = (unsigned int)(v39 + 32);
    }
    else
    {
      *((_QWORD *)&v49 + 1) = 0;
    }
    v41 = (unsigned int)v50;
    *(_OWORD *)((char *)v38 + v39) = v49;
    v20 = a6;
    Src = v16;
    Size = v41;
  }
  else
  {
    Size = a9;
    Src = a8;
    if ( a7 && !*((_WORD *)a7 + 144) && a5 && *((_WORD *)a5 + 68) && wcschr(*((const wchar_t **)a5 + 18), 0x2Eu) )
      *((_OWORD *)a7 + 18) = *(_OWORD *)((char *)a5 + 136);
  }
  SupplementalCacheInfo = KerbMakeSupplementalCacheInfo(Src, Size, v64, (unsigned int)a11, &Src, &Size);
  if ( SupplementalCacheInfo >= 0 )
  {
    if ( Src )
      Size_4 |= 0x40u;
    v69 = 16;
    RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
    SupplementalCacheInfo = KerbDuplicateStringEx(&v62, &KerbGlobalMachineName);
    RtlReleaseResource(&KerberosGlobalResource);
    if ( SupplementalCacheInfo >= 0 )
    {
      v70[1] = v62;
      if ( v65 )
        v70[3] = *v65;
      v52 = 8;
      v53 = &v68;
      v54 = a7;
      if ( (v20 & 4) != 0 )
      {
        v42 = "deleting";
      }
      else if ( (v20 & 0x10) != 0 )
      {
        v42 = "deleting all";
      }
      else if ( (v20 & 0x20) != 0 )
      {
        v42 = "disabling optimized logon";
      }
      else
      {
        v42 = "with claims";
        if ( !(_DWORD)a11 )
          v42 = (const char *)&word_1800FEE0E;
      }
      LODWORD(v47) = Size_4;
      KerbTracerT::Log(
        2,
        "KerbCacheLogonInformation",
        3837,
        "KerbCacheLogonInformation updating NLP Cache entry of %wZ\\%wZ, flags %#x %s... \n",
        &v68,
        v70,
        v47,
        v42);
      Size_4 |= 2u;
      if ( v66 )
      {
        v44 = KerbBuildFidoCache((struct _MSV1_0_CACHE_LOGON_REQUEST_EX *)&v52, v66);
        SupplementalCacheInfo = v44;
        if ( v44 < 0 )
          KerbTracerT::Log(1, "KerbCacheLogonInformation", 3871, "KerbBuildFidoCacheBlob failed with 0x%08X\n", v44);
      }
      else
      {
        v43 = ((__int64 (__fastcall *)(_QWORD *, int *, __int64, __int64 *, int *, int *))LsaFunctions->CallPackage)(
                v63,
                &v52,
                64,
                &v67,
                v51,
                &v48);
        if ( v43 < 0 || v48 < 0 )
        {
          KerbTracerT::Log(
            1,
            "KerbCacheLogonInformation",
            3857,
            "KerbCacheLogonInformation failed to cache credentials: 0x%x, 0x%x",
            v43,
            v48);
          SupplementalCacheInfo = v43;
          if ( v43 >= 0 )
            SupplementalCacheInfo = v48;
        }
      }
    }
    else
    {
      KerbTracerT::Log(1, "KerbCacheLogonInformation", 3815, "Failed to duplicate KerbGlobalMachineName\n");
    }
  }
  else
  {
    KerbTracerT::Log(1, "KerbCacheLogonInformation", 3794, "Failed to make supplemental credentials for cache\n");
  }
LABEL_65:
  if ( Src )
    KerbFree(Src);
  KerbFreeString((__int64)&v62);
  if ( v16 && *(v16 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)SupplementalCacheInfo;
}

```

## disassembly

```asm
0x18003ca2c  push    rbp
0x18003ca2e  push    rbx
0x18003ca2f  push    rsi
0x18003ca30  push    rdi
0x18003ca31  push    r12
0x18003ca33  push    r13
0x18003ca35  push    r14
0x18003ca37  push    r15
0x18003ca39  sub     rsp, 188h
0x18003ca40  lea     rbp, [rsp+50h]
0x18003ca45  mov     rax, cs:__security_cookie
0x18003ca4c  xor     rax, rbp
0x18003ca4f  mov     [rbp+170h+var_50], rax
0x18003ca56  mov     rax, [rbp+170h+arg_48]
0x18003ca5d  mov     r15, rdx
0x18003ca60  mov     rsi, [rbp+170h+arg_20]
0x18003ca67  mov     r14, rcx
0x18003ca6a  mov     r13, [rbp+170h+arg_30]
0x18003ca71  mov     rbx, r9
0x18003ca74  mov     r12, [rbp+170h+arg_38]
0x18003ca7b  mov     [rbp+170h+var_100], rdx
0x18003ca7f  xor     edx, edx; Val
0x18003ca81  mov     [rbp+170h+var_D8], rax
0x18003ca88  mov     rax, [rbp+170h+arg_58]
0x18003ca8f  mov     [rbp+170h+var_D0], r8
0x18003ca96  mov     [rbp+170h+var_158], rcx
0x18003ca9a  lea     r8d, [rdx+60h]; Size
0x18003ca9e  lea     rcx, [rbp+170h+var_B0]; void *
0x18003caa5  mov     [rbp+170h+var_C8], rax
0x18003caac  call    memset_0
0x18003cab1  xor     edx, edx; Val
0x18003cab3  lea     rcx, [rbp+170h+var_140]; void *
0x18003cab7  lea     r8d, [rdx+40h]; Size
0x18003cabb  call    memset_0
0x18003cac0  xor     edx, edx
0x18003cac2  mov     [rbp+170h+var_E8], 4C004Ah
0x18003cacd  mov     [rbp+170h+var_C0], rdx
0x18003cad4  lea     rax, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18003cadb  mov     [rbp+170h+var_E0], rax
0x18003cae2  xorps   xmm0, xmm0
0x18003cae5  mov     [rbp+170h+var_150], edx
0x18003cae8  mov     edi, edx
0x18003caea  mov     [rbp+170h+var_170], edx
0x18003caed  mov     qword ptr [rbp+170h+var_F8.Length], rdx
0x18003caf1  movups  [rbp+170h+var_168], xmm0
0x18003caf5  test    rsi, rsi
0x18003caf8  jz      short loc_18003CB08
0x18003cafa  mov     ecx, [rsi+388h]
0x18003cb00  shr     ecx, 5
0x18003cb03  and     ecx, 1
0x18003cb06  jmp     short loc_18003CB0A
0x18003cb08  mov     ecx, edx
0x18003cb0a  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A+1, dl; _KerberosSystemRole KerbGlobalRoles
0x18003cb10  mov     [rbp+170h+var_F8.Buffer], rdx
0x18003cb17  jnz     short loc_18003CB41
0x18003cb19  lea     r9, aKerbcachelogon_4; "KerbCacheLogonInformation does not supp"...
0x18003cb20  mov     r8d, 0E3Ch
0x18003cb26  lea     rdx, aKerbcachelogon_5; "KerbCacheLogonInformation"
0x18003cb2d  mov     ecx, 2
0x18003cb32  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003cb37  mov     ebx, 0C00000BBh
0x18003cb3c  jmp     loc_18003D011
0x18003cb41  movups  xmm0, xmmword ptr [r15]
0x18003cb45  mov     r15d, [rbp+170h+arg_28]
0x18003cb4c  mov     eax, r15d
0x18003cb4f  mov     dword ptr [rbp+170h+Size+4], eax
0x18003cb52  movups  xmm1, xmmword ptr [r14]
0x18003cb56  movdqu  [rbp+170h+var_B0], xmm0
0x18003cb5e  movdqu  [rbp+170h+var_90], xmm1
0x18003cb66  test    rsi, rsi
0x18003cb69  jz      short loc_18003CB7D
0x18003cb6b  mov     rax, [rsi+40h]
0x18003cb6f  mov     [rbp+170h+var_118], rax
0x18003cb73  mov     eax, r15d
0x18003cb76  bts     eax, 8
0x18003cb7a  mov     dword ptr [rbp+170h+Size+4], eax
0x18003cb7d  test    rbx, rbx
0x18003cb80  jz      short loc_18003CB96
0x18003cb82  bts     eax, 9
0x18003cb86  mov     [rbp+170h+var_110], rbx
0x18003cb8a  mov     dword ptr [rbp+170h+Size+4], eax
0x18003cb8d  mov     eax, [rbx+4]
0x18003cb90  add     eax, 8
0x18003cb93  mov     [rbp+170h+var_108], eax
0x18003cb96  lea     r14, aKerbcachelogon_5; "KerbCacheLogonInformation"
0x18003cb9d  test    ecx, ecx
0x18003cb9f  jz      loc_18003CDE1
0x18003cba5  test    rsi, rsi
0x18003cba8  jnz     short loc_18003CBCC
0x18003cbaa  lea     r9, aKerbcachelogon_3; "KerbCacheLogonInformation logon session"...
0x18003cbb1  mov     r8d, 0E5Ch
0x18003cbb7  mov     rdx, r14
0x18003cbba  lea     ecx, [rsi+1]
0x18003cbbd  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003cbc2  mov     ebx, 0C000000Dh
0x18003cbc7  jmp     loc_18003D011
0x18003cbcc  lea     r15, [rsi+78h]
0x18003cbd0  test    r13, r13
0x18003cbd3  jz      short loc_18003CBE2
0x18003cbd5  lea     rcx, [r13+0D0h]
0x18003cbdc  lea     rdx, [r13+30h]
0x18003cbe0  jmp     short loc_18003CBE5
0x18003cbe2  mov     rcx, rdx
0x18003cbe5  mov     [rsp+1C0h+var_178], r15
0x18003cbea  lea     rax, [r15+10h]
0x18003cbee  mov     [rsp+1C0h+var_180], rax
0x18003cbf3  lea     r9, aKerbcachelogon_2; "KerbCacheLogonInformation caching MIT p"...
0x18003cbfa  mov     rax, [rbp+170h+var_158]
0x18003cbfe  mov     r8d, 0E65h
0x18003cc04  mov     [rsp+1C0h+var_188], rdx
0x18003cc09  mov     rdx, r14
0x18003cc0c  mov     [rsp+1C0h+var_190], rcx
0x18003cc11  mov     ecx, 3
0x18003cc16  mov     [rsp+1C0h+var_198], rax
0x18003cc1b  mov     rax, [rbp+170h+var_100]
0x18003cc1f  mov     [rsp+1C0h+var_1A0], rax
0x18003cc24  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003cc29  movzx   ecx, word ptr [rsi+88h]
0x18003cc30  mov     edx, 0FFFFFFFCh
0x18003cc35  movzx   eax, word ptr [r15]
0x18003cc39  add     ecx, 3
0x18003cc3c  or      dword ptr [rbp+170h+Size+4], 1
0x18003cc40  add     eax, 3
0x18003cc43  and     ecx, edx
0x18003cc45  and     eax, edx
0x18003cc47  add     ecx, 20h ; ' '
0x18003cc4a  xor     r12d, r12d
0x18003cc4d  add     eax, ecx
0x18003cc4f  mov     ebx, eax
0x18003cc51  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18003cc58  mov     dword ptr [rbp+170h+var_158], eax
0x18003cc5b  ja      short loc_18003CCB5
0x18003cc5d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003cc64  add     rcx, 8
0x18003cc68  add     rcx, rbx
0x18003cc6b  cmp     rcx, rbx
0x18003cc6e  jb      short loc_18003CCB5
0x18003cc70  call    VerifyStackAvailable
0x18003cc75  test    eax, eax
0x18003cc77  jz      short loc_18003CCB5
0x18003cc79  lea     rax, [rbx+8]
0x18003cc7d  lea     rcx, [rax+0Fh]
0x18003cc81  cmp     rcx, rax
0x18003cc84  ja      short loc_18003CC90
0x18003cc86  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003cc90  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003cc94  mov     rax, rcx
0x18003cc97  call    _alloca_probe
0x18003cc9c  sub     rsp, rcx
0x18003cc9f  lea     rdi, [rsp+1C0h+var_170]
0x18003cca4  test    rdi, rdi
0x18003cca7  jz      short loc_18003CCB5
0x18003cca9  mov     dword ptr [rdi], 6B637453h
0x18003ccaf  add     rdi, 8
0x18003ccb3  jnz     short loc_18003CCDC
0x18003ccb5  lea     rcx, [rbx+8]
0x18003ccb9  cmp     rcx, rbx
0x18003ccbc  jb      short loc_18003CCDC
0x18003ccbe  mov     rax, cs:g_pfnAllocate
0x18003ccc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccca  mov     rdi, rax
0x18003cccd  test    rax, rax
0x18003ccd0  jz      short loc_18003CCDC
0x18003ccd2  mov     dword ptr [rax], 70616548h
0x18003ccd8  add     rdi, 8
0x18003ccdc  test    rdi, rdi
0x18003ccdf  jnz     short loc_18003CCEB
0x18003cce1  mov     ebx, 0C000009Ah
0x18003cce6  jmp     loc_18003D011
0x18003cceb  movzx   ebx, word ptr [r15]
0x18003ccef  lea     r12, [rdi+10h]
0x18003ccf3  xor     ecx, ecx
0x18003ccf5  mov     word ptr [rbp+170h+var_168+2], bx
0x18003ccf9  mov     word ptr [rbp+170h+var_168], bx
0x18003ccfd  test    bx, bx
0x18003cd00  jz      short loc_18003CD21
0x18003cd02  mov     rdx, [rsi+80h]; Src
0x18003cd09  mov     r8d, ebx; Size
0x18003cd0c  mov     rcx, r12; void *
0x18003cd0f  call    memcpy_0
0x18003cd14  mov     eax, r12d
0x18003cd17  sub     eax, edi
0x18003cd19  mov     qword ptr [rbp+170h+var_168+8], rax
0x18003cd1d  xor     ecx, ecx
0x18003cd1f  jmp     short loc_18003CD25
0x18003cd21  mov     qword ptr [rbp+170h+var_168+8], rcx
0x18003cd25  movups  xmm0, [rbp+170h+var_168]
0x18003cd29  lea     r15, [rbx+3]
0x18003cd2d  and     r15, 0FFFFFFFFFFFFFFFCh
0x18003cd31  movdqu  xmmword ptr [rdi], xmm0
0x18003cd35  movzx   eax, word ptr [rsi+88h]
0x18003cd3c  mov     word ptr [rbp+170h+var_168+2], ax
0x18003cd40  mov     word ptr [rbp+170h+var_168], ax
0x18003cd44  test    ax, ax
0x18003cd47  jz      short loc_18003CD6C
0x18003cd49  mov     rdx, [rsi+90h]; Src
0x18003cd50  lea     rbx, [r15+10h]
0x18003cd54  add     rbx, r12
0x18003cd57  mov     r8d, eax; Size
0x18003cd5a  mov     rcx, rbx; void *
0x18003cd5d  call    memcpy_0
0x18003cd62  sub     ebx, edi
0x18003cd64  mov     eax, ebx
0x18003cd66  mov     qword ptr [rbp+170h+var_168+8], rax
0x18003cd6a  jmp     short loc_18003CD70
0x18003cd6c  mov     qword ptr [rbp+170h+var_168+8], rcx
0x18003cd70  movups  xmm0, [rbp+170h+var_168]
0x18003cd74  mov     eax, dword ptr [rbp+170h+var_158]
0x18003cd77  movdqu  xmmword ptr [r15+r12], xmm0
0x18003cd7d  mov     r15d, [rbp+170h+arg_28]
0x18003cd84  mov     [rbp+170h+Src], rdi
0x18003cd88  mov     dword ptr [rbp+170h+Size], eax
0x18003cd8b  xor     r12d, r12d
0x18003cd8e  mov     esi, dword ptr [rbp+170h+arg_50]
0x18003cd94  lea     rax, [rbp+170h+Size]
0x18003cd98  mov     r8, [rbp+170h+var_D8]; void *
0x18003cd9f  mov     r9d, esi; size_t
0x18003cda2  mov     edx, dword ptr [rbp+170h+Size]; Size
0x18003cda5  mov     rcx, [rbp+170h+Src]; Src
0x18003cda9  mov     [rsp+1C0h+var_198], rax; unsigned int *
0x18003cdae  lea     rax, [rbp+170h+Src]
0x18003cdb2  mov     [rsp+1C0h+var_1A0], rax; void **
0x18003cdb7  call    ?KerbMakeSupplementalCacheInfo@@YAJPEAXK0KPEAPEAXPEAK@Z; KerbMakeSupplementalCacheInfo(void *,ulong,void *,ulong,void * *,ulong *)
0x18003cdbc  mov     ebx, eax
0x18003cdbe  test    eax, eax
0x18003cdc0  jns     short loc_18003CE3E
0x18003cdc2  lea     r9, aFailedToMakeSu; "Failed to make supplemental credentials"...
0x18003cdc9  mov     r8d, 0ED2h
0x18003cdcf  mov     rdx, r14
0x18003cdd2  mov     ecx, 1
0x18003cdd7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003cddc  jmp     loc_18003D011
0x18003cde1  mov     eax, [rbp+170h+arg_40]
0x18003cde7  mov     dword ptr [rbp+170h+Size], eax
0x18003cdea  mov     [rbp+170h+Src], r12
0x18003cdee  test    r13, r13
0x18003cdf1  jz      short loc_18003CD8B
0x18003cdf3  cmp     [r13+120h], dx
0x18003cdfb  jnz     short loc_18003CD8B
0x18003cdfd  test    rsi, rsi
0x18003ce00  jz      short loc_18003CD8B
0x18003ce02  cmp     [rsi+88h], dx
0x18003ce09  jz      short loc_18003CD8B
0x18003ce0b  mov     rcx, [rsi+90h]; Str
0x18003ce12  mov     edx, 2Eh ; '.'; Ch
0x18003ce17  call    cs:__imp_wcschr
0x18003ce1d  xor     r12d, r12d
0x18003ce20  test    rax, rax
0x18003ce23  jz      loc_18003CD8E
0x18003ce29  movups  xmm0, xmmword ptr [rsi+88h]
0x18003ce30  movdqu  xmmword ptr [r13+120h], xmm0
0x18003ce39  jmp     loc_18003CD8E
0x18003ce3e  cmp     [rbp+170h+Src], r12
0x18003ce42  jz      short loc_18003CE48
0x18003ce44  or      dword ptr [rbp+170h+Size+4], 40h
0x18003ce48  mov     dl, 1; Wait
0x18003ce4a  mov     [rbp+170h+var_A0], 10h
0x18003ce54  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x18003ce5b  call    cs:__imp_RtlAcquireResourceShared
0x18003ce61  lea     rdx, ?KerbGlobalMachineName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x18003ce68  lea     rcx, [rbp+170h+var_F8]; struct _UNICODE_STRING *
0x18003ce6c  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18003ce71  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x18003ce78  mov     ebx, eax
0x18003ce7a  call    cs:__imp_RtlReleaseResource
0x18003ce80  test    ebx, ebx
0x18003ce82  jns     short loc_18003CE96
0x18003ce84  lea     r9, aFailedToDuplic; "Failed to duplicate KerbGlobalMachineNa"...
0x18003ce8b  mov     r8d, 0EE7h
0x18003ce91  jmp     loc_18003CDCF
0x18003ce96  mov     rax, qword ptr [rbp+170h+var_F8.Length]
0x18003ce9a  mov     [rbp+170h+var_80], rax
0x18003cea1  mov     rax, [rbp+170h+var_F8.Buffer]
0x18003cea8  mov     [rbp+170h+var_78], rax
0x18003ceaf  mov     rax, [rbp+170h+var_D0]
0x18003ceb6  test    rax, rax
0x18003ceb9  jz      short loc_18003CEC6
0x18003cebb  movups  xmm0, xmmword ptr [rax]
0x18003cebe  movdqu  [rbp+170h+var_60], xmm0
0x18003cec6  mov     [rbp+170h+var_140], 8
0x18003cecd  lea     rax, [rbp+170h+var_B0]
0x18003ced4  mov     [rbp+170h+var_138], rax
0x18003ced8  mov     [rbp+170h+var_130], r13
0x18003cedc  test    r15b, 4
0x18003cee0  jz      short loc_18003CEEB
0x18003cee2  lea     rax, aDeleting; "deleting"
0x18003cee9  jmp     short loc_18003CF1D
0x18003ceeb  test    r15b, 10h
0x18003ceef  jz      short loc_18003CEFA
0x18003cef1  lea     rax, aDeletingAll; "deleting all"
0x18003cef8  jmp     short loc_18003CF1D
0x18003cefa  test    r15b, 20h
0x18003cefe  jz      short loc_18003CF09
0x18003cf00  lea     rax, aDisablingOptim; "disabling optimized logon"
0x18003cf07  jmp     short loc_18003CF1D
0x18003cf09  test    esi, esi
0x18003cf0b  lea     rax, aWithClaims; "with claims"
0x18003cf12  lea     rcx, word_1800FEE0E
0x18003cf19  cmovz   rax, rcx
0x18003cf1d  mov     [rsp+1C0h+var_188], rax
  ... truncated ...
```
