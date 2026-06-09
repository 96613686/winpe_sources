# dsGetCAConfig(_CERT_AUTHORITY_INFO * *,long *)

- ea: `0x18000d234`
- end: `0x18000d75e`
- name: `?dsGetCAConfig@@YAJPEAPEAU_CERT_AUTHORITY_INFO@@PEAJ@Z`
- size: `1322`
- prototype: `__int64 __fastcall(struct _CERT_AUTHORITY_INFO **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c15c`

## callees

- `0x18000a3c4`
- `0x18000a4f8`
- `0x18000b940`
- `0x18000b9cc`
- `0x18000d164`
- `0x18000d234`
- `0x18001f314`
- `0x180020a6c`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d2da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d461`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d4f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d2da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d461`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d4f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6e9`
- `CRYPT32!CertStrToNameW` at `0x18000d4d3`
- `CRYPT32!CertStrToNameW` at `0x18000d4d3`
- `certca!__imp_CAEnumFirstCA` at `0x18000d282`
- `certca!__imp_CAEnumFirstCA` at `0x18000d282`
- `certca!__imp_CAEnumNextCA` at `0x18000d5ff`
- `certca!__imp_CAEnumNextCA` at `0x18000d5ff`
- `certca!__imp_CACountCAs` at `0x18000d2c0`
- `certca!__imp_CACountCAs` at `0x18000d2c0`
- `certca!__imp_CACloseCA` at `0x18000d60b`
- `certca!__imp_CACloseCA` at `0x18000d6db`
- `certca!__imp_CACloseCA` at `0x18000d60b`
- `certca!__imp_CACloseCA` at `0x18000d6db`
- `certca!__imp_CAGetCAProperty` at `0x18000d320`
- `certca!__imp_CAGetCAProperty` at `0x18000d33f`
- `certca!__imp_CAGetCAProperty` at `0x18000d35e`
- `certca!__imp_CAGetCAProperty` at `0x18000d37d`
- `certca!__imp_CAGetCAProperty` at `0x18000d39c`
- `certca!__imp_CAGetCAProperty` at `0x18000d320`
- `certca!__imp_CAGetCAProperty` at `0x18000d33f`
- `certca!__imp_CAGetCAProperty` at `0x18000d35e`
- `certca!__imp_CAGetCAProperty` at `0x18000d37d`
- `certca!__imp_CAGetCAProperty` at `0x18000d39c`
- `certca!__imp_CAFreeCAProperty` at `0x18000d591`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5a8`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5bf`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5d6`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5ed`
- `certca!__imp_CAFreeCAProperty` at `0x18000d6fc`
- `certca!__imp_CAFreeCAProperty` at `0x18000d70f`
- `certca!__imp_CAFreeCAProperty` at `0x18000d722`
- `certca!__imp_CAFreeCAProperty` at `0x18000d735`
- `certca!__imp_CAFreeCAProperty` at `0x18000d591`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5a8`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5bf`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5d6`
- `certca!__imp_CAFreeCAProperty` at `0x18000d5ed`
- `certca!__imp_CAFreeCAProperty` at `0x18000d6fc`
- `certca!__imp_CAFreeCAProperty` at `0x18000d70f`
- `certca!__imp_CAFreeCAProperty` at `0x18000d722`
- `certca!__imp_CAFreeCAProperty` at `0x18000d735`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d2f4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d57e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d679`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d2f4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d57e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000d679`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000d555`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000d555`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000d2b6`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000d2b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall dsGetCAConfig(struct _CERT_AUTHORITY_INFO **a1, int *a2)
{
  BYTE *pbEncoded; // rdi
  int v3; // eax
  int v4; // eax
  int v5; // r12d
  struct _CERT_AUTHORITY_INFO *v6; // r14
  unsigned int v7; // ecx
  int v8; // edx
  int WebEnrollmentServers; // ebx
  int v10; // r15d
  int i; // r13d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned __int16 **v17; // rsi
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  int v23; // eax
  int DNInfo; // eax
  int v25; // ebx
  const unsigned __int16 **v27; // [rsp+40h] [rbp-38h] BYREF
  const unsigned __int16 **v28; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR *v29; // [rsp+50h] [rbp-28h] BYREF
  const unsigned __int16 **v30; // [rsp+58h] [rbp-20h] BYREF
  const unsigned __int16 **v31; // [rsp+60h] [rbp-18h] BYREF
  void *v32; // [rsp+68h] [rbp-10h] BYREF
  DWORD pcbEncoded; // [rsp+D0h] [rbp+58h] BYREF
  void *v36; // [rsp+D8h] [rbp+60h] BYREF

  *a1 = 0;
  pbEncoded = 0;
  *a2 = 0;
  v36 = 0;
  v32 = 0;
  v30 = 0;
  v28 = 0;
  v31 = 0;
  v27 = 0;
  v29 = 0;
  pcbEncoded = 0;
  v3 = CAEnumFirstCA(0, 80, &v36);
  if ( v3 != -2147023665 && v3 && v3 != -2147023541 && v3 != -2147023573 )
    CSPrintErrorLineFileData2(L"Ignored!", 0x19802C1u, v3, -2147023555);
  v4 = CACountCAs(v36);
  v5 = v4;
  if ( v4 <= 0 )
    goto LABEL_69;
  v6 = (struct _CERT_AUTHORITY_INFO *)LocalAlloc(0x40u, 104LL * v4);
  if ( !v6 )
  {
    v7 = 27525825;
LABEL_9:
    v8 = -2147024882;
    WebEnrollmentServers = -2147024882;
    goto LABEL_62;
  }
  v10 = 0;
  for ( i = 0; ; ++i )
  {
    pbEncoded = 0;
    if ( i >= v5 )
    {
LABEL_68:
      *a2 = v10;
      *a1 = v6;
LABEL_69:
      WebEnrollmentServers = 0;
      v6 = 0;
      goto LABEL_70;
    }
    v12 = CAGetCAProperty(v36, L"displayName", &v30);
    WebEnrollmentServers = v12;
    if ( v12 )
    {
      v8 = v12;
      v7 = 28705473;
      goto LABEL_62;
    }
    v13 = CAGetCAProperty(v36, L"cn", &v28);
    WebEnrollmentServers = v13;
    if ( v13 )
    {
      v8 = v13;
      v7 = 28902081;
      goto LABEL_62;
    }
    v14 = CAGetCAProperty(v36, L"Description", &v31);
    WebEnrollmentServers = v14;
    if ( v14 )
    {
      v8 = v14;
      v7 = 29098689;
      goto LABEL_62;
    }
    v15 = CAGetCAProperty(v36, L"dNSHostName", &v27);
    WebEnrollmentServers = v15;
    if ( v15 )
    {
      v8 = v15;
      v7 = 29295297;
      goto LABEL_62;
    }
    v16 = CAGetCAProperty(v36, L"cACertificateDN", &v29);
    WebEnrollmentServers = v16;
    if ( v16 )
    {
      v8 = v16;
      v7 = 29491905;
      goto LABEL_62;
    }
    if ( v30 && v28 && v27 && v29 )
      break;
    CSPrintErrorLineFile(0x1C902C1u, -2147024809);
LABEL_41:
    if ( v30 )
    {
      CAFreeCAProperty(v36);
      v30 = 0;
    }
    if ( v28 )
    {
      CAFreeCAProperty(v36);
      v28 = 0;
    }
    if ( v31 )
    {
      CAFreeCAProperty(v36);
      v31 = 0;
    }
    if ( v27 )
    {
      CAFreeCAProperty(v36);
      v27 = 0;
    }
    if ( v29 )
    {
      CAFreeCAProperty(v36);
      v29 = 0;
    }
    v25 = CAEnumNextCA(v36, &v32);
    CACloseCA(v36);
    v36 = v32;
    if ( v25 || !v32 )
      goto LABEL_68;
  }
  v17 = (unsigned __int16 **)((char *)v6 + 104 * v10);
  v18 = mySanitizeName(*v30, v17);
  pbEncoded = 0;
  WebEnrollmentServers = v18;
  if ( v18 )
  {
    v7 = 30278337;
    goto LABEL_61;
  }
  v18 = myDupString(*v28, v17 + 1);
  WebEnrollmentServers = v18;
  if ( v18 )
  {
    v7 = 30606017;
    goto LABEL_61;
  }
  if ( v31 )
  {
    v18 = myDupString(*v31, v17 + 10);
    WebEnrollmentServers = v18;
    if ( v18 )
    {
      v7 = 30933697;
LABEL_61:
      v8 = v18;
      goto LABEL_62;
    }
  }
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( (*v27)[v20] );
  do
    ++v19;
  while ( (*v17)[v19] );
  v21 = v20 + v19 + 2;
  v22 = (unsigned __int16 *)LocalAlloc(0, 2 * v21);
  v17[7] = v22;
  if ( v22 )
  {
    StringCchCopyW(v22, v21, *v27);
    StringCchCatW(v17[7], v21, L"\\");
    StringCchCatW(v17[7], v21, *v17);
    while ( 1 )
    {
      if ( !CertStrToNameW(1u, *v29, 0x200003u, 0, pbEncoded, &pcbEncoded, 0) )
      {
        v23 = myHLastError();
        WebEnrollmentServers = v23;
        if ( v23 )
        {
          v8 = v23;
          v7 = 33030849;
          goto LABEL_62;
        }
      }
      if ( pbEncoded )
        break;
      pbEncoded = (BYTE *)LocalAlloc(0x40u, pcbEncoded);
      if ( !pbEncoded )
      {
        v7 = 33817281;
        goto LABEL_9;
      }
    }
    DNInfo = ConfigLoadDNInfo(pbEncoded, pcbEncoded, (HLOCAL *)v17);
    WebEnrollmentServers = DNInfo;
    if ( DNInfo )
    {
      v8 = DNInfo;
      v7 = 34144961;
    }
    else
    {
      WebEnrollmentServers = ConfigLoadWebEnrollmentServers(v36, (struct _CERT_AUTHORITY_INFO *)v17);
      if ( WebEnrollmentServers >= 0 )
      {
LABEL_39:
        *((_DWORD *)v17 + 22) = 1;
        ++v10;
        LocalFree(pbEncoded);
        pbEncoded = 0;
        goto LABEL_41;
      }
      if ( WebEnrollmentServers == -2147023728 )
      {
        CSPrintErrorLineFileData(L"msPKI-Enrollment-Servers", 0x21102C1u, -2147023728);
        goto LABEL_39;
      }
      v8 = WebEnrollmentServers;
      v7 = 34996929;
    }
  }
  else
  {
    v8 = -2147024882;
    v7 = 31720129;
    WebEnrollmentServers = -2147024882;
  }
LABEL_62:
  CSPrintErrorLineFile(v7, v8);
LABEL_70:
  if ( v36 )
    CACloseCA(v36);
  if ( pbEncoded )
    LocalFree(pbEncoded);
  if ( v30 )
    CAFreeCAProperty(v36);
  if ( v28 )
    CAFreeCAProperty(v36);
  if ( v27 )
    CAFreeCAProperty(v36);
  if ( v29 )
    CAFreeCAProperty(v36);
  if ( v6 )
    dsFreeCAConfig(v5, v6);
  return (unsigned int)WebEnrollmentServers;
}

```

## disassembly

```asm
0x18000d234  mov     [rsp-40h+arg_8], rdx
0x18000d239  mov     [rsp-40h+arg_0], rcx
0x18000d23e  push    rbp
0x18000d23f  push    rbx
0x18000d240  push    rsi
0x18000d241  push    rdi
0x18000d242  push    r12
0x18000d244  push    r13
0x18000d246  push    r14
0x18000d248  push    r15
0x18000d24a  mov     rbp, rsp
0x18000d24d  sub     rsp, 78h
0x18000d251  xor     esi, esi
0x18000d253  lea     r8, [rbp+arg_18]
0x18000d257  mov     [rcx], rsi
0x18000d25a  mov     edi, esi
0x18000d25c  mov     [rdx], esi
0x18000d25e  xor     ecx, ecx
0x18000d260  mov     [rbp+arg_18], rsi
0x18000d264  lea     edx, [rsi+50h]
0x18000d267  mov     [rbp+var_10], rsi
0x18000d26b  mov     [rbp+var_20], rsi
0x18000d26f  mov     [rbp+var_30], rsi
0x18000d273  mov     [rbp+var_18], rsi
0x18000d277  mov     [rbp+var_38], rsi
0x18000d27b  mov     [rbp+var_28], rsi
0x18000d27f  mov     [rbp+arg_10], esi
0x18000d282  call    cs:__imp_CAEnumFirstCA
0x18000d288  cmp     eax, 800704CFh
0x18000d28d  jz      short loc_18000D2BC
0x18000d28f  test    eax, eax
0x18000d291  jz      short loc_18000D2BC
0x18000d293  cmp     eax, 8007054Bh
0x18000d298  jz      short loc_18000D2BC
0x18000d29a  cmp     eax, 8007052Bh
0x18000d29f  jz      short loc_18000D2BC
0x18000d2a1  mov     r9d, 8007053Dh
0x18000d2a7  lea     rcx, aIgnored; "Ignored!"
0x18000d2ae  mov     r8d, eax
0x18000d2b1  mov     edx, 19802C1h
0x18000d2b6  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d2bc  mov     rcx, [rbp+arg_18]
0x18000d2c0  call    cs:__imp_CACountCAs
0x18000d2c6  movsxd  r12, eax
0x18000d2c9  test    eax, eax
0x18000d2cb  jle     loc_18000D6CD
0x18000d2d1  imul    rdx, r12, 68h ; 'h'; uBytes
0x18000d2d5  mov     ecx, 40h ; '@'; uFlags
0x18000d2da  call    cs:__imp_LocalAlloc
0x18000d2e0  mov     r14, rax
0x18000d2e3  test    rax, rax
0x18000d2e6  jnz     short loc_18000D2FF
0x18000d2e8  mov     ecx, 1A402C1h
0x18000d2ed  mov     edx, 8007000Eh
0x18000d2f2  mov     ebx, edx
0x18000d2f4  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000d2fa  jmp     loc_18000D6D2
0x18000d2ff  mov     r15d, esi
0x18000d302  mov     r13d, esi
0x18000d305  mov     rdi, rsi
0x18000d308  cmp     r13d, r12d
0x18000d30b  jge     loc_18000D6BF
0x18000d311  mov     rcx, [rbp+arg_18]
0x18000d315  lea     r8, [rbp+var_20]
0x18000d319  lea     rdx, aDisplayname; "displayName"
0x18000d320  call    cs:__imp_CAGetCAProperty
0x18000d326  mov     ebx, eax
0x18000d328  test    eax, eax
0x18000d32a  jnz     loc_18000D6B3
0x18000d330  mov     rcx, [rbp+arg_18]
0x18000d334  lea     r8, [rbp+var_30]
0x18000d338  lea     rdx, aCn_0; "cn"
0x18000d33f  call    cs:__imp_CAGetCAProperty
0x18000d345  mov     ebx, eax
0x18000d347  test    eax, eax
0x18000d349  jnz     loc_18000D6A7
0x18000d34f  mov     rcx, [rbp+arg_18]
0x18000d353  lea     r8, [rbp+var_18]
0x18000d357  lea     rdx, aDescription; "Description"
0x18000d35e  call    cs:__imp_CAGetCAProperty
0x18000d364  mov     ebx, eax
0x18000d366  test    eax, eax
0x18000d368  jnz     loc_18000D69B
0x18000d36e  mov     rcx, [rbp+arg_18]
0x18000d372  lea     r8, [rbp+var_38]
0x18000d376  lea     rdx, aDnshostname; "dNSHostName"
0x18000d37d  call    cs:__imp_CAGetCAProperty
0x18000d383  mov     ebx, eax
0x18000d385  test    eax, eax
0x18000d387  jnz     loc_18000D68F
0x18000d38d  mov     rcx, [rbp+arg_18]
0x18000d391  lea     r8, [rbp+var_28]
0x18000d395  lea     rdx, aCacertificated; "cACertificateDN"
0x18000d39c  call    cs:__imp_CAGetCAProperty
0x18000d3a2  mov     ebx, eax
0x18000d3a4  test    eax, eax
0x18000d3a6  jnz     loc_18000D683
0x18000d3ac  mov     rcx, [rbp+var_20]
0x18000d3b0  test    rcx, rcx
0x18000d3b3  jz      loc_18000D574
0x18000d3b9  cmp     [rbp+var_30], rsi
0x18000d3bd  jz      loc_18000D574
0x18000d3c3  cmp     [rbp+var_38], rsi
0x18000d3c7  jz      loc_18000D574
0x18000d3cd  cmp     [rbp+var_28], rsi
0x18000d3d1  jz      loc_18000D574
0x18000d3d7  mov     rcx, [rcx]; unsigned __int16 *
0x18000d3da  movsxd  rax, r15d
0x18000d3dd  imul    rsi, rax, 68h ; 'h'
0x18000d3e1  add     rsi, r14
0x18000d3e4  mov     rdx, rsi; unsigned __int16 **
0x18000d3e7  call    ?mySanitizeName@@YAJPEBGPEAPEAG@Z; mySanitizeName(ushort const *,ushort * *)
0x18000d3ec  xor     edi, edi
0x18000d3ee  mov     ebx, eax
0x18000d3f0  test    eax, eax
0x18000d3f2  jnz     loc_18000D672
0x18000d3f8  mov     rcx, [rbp+var_30]
0x18000d3fc  lea     rdx, [rsi+8]; unsigned __int16 **
0x18000d400  mov     rcx, [rcx]; Src
0x18000d403  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18000d408  mov     ebx, eax
0x18000d40a  test    eax, eax
0x18000d40c  jnz     loc_18000D66B
0x18000d412  mov     rcx, [rbp+var_18]
0x18000d416  test    rcx, rcx
0x18000d419  jz      short loc_18000D431
0x18000d41b  mov     rcx, [rcx]; Src
0x18000d41e  lea     rdx, [rsi+50h]; unsigned __int16 **
0x18000d422  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18000d427  mov     ebx, eax
0x18000d429  test    eax, eax
0x18000d42b  jnz     loc_18000D632
0x18000d431  mov     rax, [rbp+var_38]
0x18000d435  mov     rdx, [rax]
0x18000d438  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d43c  mov     rcx, rax
0x18000d43f  inc     rcx
0x18000d442  cmp     [rdx+rcx*2], di
0x18000d446  jnz     short loc_18000D43F
0x18000d448  mov     rdx, [rsi]
0x18000d44b  inc     rax
0x18000d44e  cmp     [rdx+rax*2], di
0x18000d452  jnz     short loc_18000D44B
0x18000d454  lea     rbx, [rax+2]
0x18000d458  add     rbx, rcx
0x18000d45b  xor     ecx, ecx; uFlags
0x18000d45d  lea     rdx, [rbx+rbx]; uBytes
0x18000d461  call    cs:__imp_LocalAlloc
0x18000d467  mov     [rsi+38h], rax
0x18000d46b  test    rax, rax
0x18000d46e  jz      loc_18000D65D
0x18000d474  mov     r8, [rbp+var_38]
0x18000d478  mov     rdx, rbx; unsigned __int64
0x18000d47b  mov     rcx, rax; unsigned __int16 *
0x18000d47e  mov     r8, [r8]; unsigned __int16 *
0x18000d481  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d486  mov     rcx, [rsi+38h]; unsigned __int16 *
0x18000d48a  lea     r8, SubStr; "\\"
0x18000d491  mov     rdx, rbx; unsigned __int64
0x18000d494  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d499  mov     r8, [rsi]; unsigned __int16 *
0x18000d49c  mov     rdx, rbx; unsigned __int64
0x18000d49f  mov     rcx, [rsi+38h]; unsigned __int16 *
0x18000d4a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d4a8  mov     rdx, [rbp+var_28]
0x18000d4ac  lea     rax, [rbp+arg_10]
0x18000d4b0  xor     r9d, r9d; pvReserved
0x18000d4b3  mov     [rsp+78h+ppszError], 0; ppszError
0x18000d4bc  mov     [rsp+78h+pcbEncoded], rax; pcbEncoded
0x18000d4c1  mov     r8d, 200003h; dwStrType
0x18000d4c7  mov     [rsp+78h+pbEncoded], rdi; pbEncoded
0x18000d4cc  mov     rdx, [rdx]; pszX500
0x18000d4cf  lea     ecx, [r9+1]; dwCertEncodingType
0x18000d4d3  call    cs:__imp_CertStrToNameW
0x18000d4d9  test    eax, eax
0x18000d4db  jnz     short loc_18000D4EC
0x18000d4dd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000d4e2  mov     ebx, eax
0x18000d4e4  test    eax, eax
0x18000d4e6  jnz     loc_18000D639
0x18000d4ec  test    rdi, rdi
0x18000d4ef  jnz     short loc_18000D50F
0x18000d4f1  mov     edx, [rbp+arg_10]; uBytes
0x18000d4f4  lea     ecx, [rdi+40h]; uFlags
0x18000d4f7  call    cs:__imp_LocalAlloc
0x18000d4fd  mov     rdi, rax
0x18000d500  test    rax, rax
0x18000d503  jnz     short loc_18000D4A8
0x18000d505  mov     ecx, 20402C1h
0x18000d50a  jmp     loc_18000D2ED
0x18000d50f  mov     edx, [rbp+arg_10]; unsigned int
0x18000d512  mov     r8, rsi; struct _CERT_AUTHORITY_INFO *
0x18000d515  mov     rcx, rdi; unsigned __int8 *
0x18000d518  call    ?ConfigLoadDNInfo@@YAJPEBEKPEAU_CERT_AUTHORITY_INFO@@@Z; ConfigLoadDNInfo(uchar const *,ulong,_CERT_AUTHORITY_INFO *)
0x18000d51d  mov     ebx, eax
0x18000d51f  test    eax, eax
0x18000d521  jnz     loc_18000D651
0x18000d527  mov     rcx, [rbp+arg_18]; void *
0x18000d52b  mov     rdx, rsi; struct _CERT_AUTHORITY_INFO *
0x18000d52e  call    ?ConfigLoadWebEnrollmentServers@@YAJPEAXPEAU_CERT_AUTHORITY_INFO@@@Z; ConfigLoadWebEnrollmentServers(void *,_CERT_AUTHORITY_INFO *)
0x18000d533  mov     ebx, eax
0x18000d535  test    eax, eax
0x18000d537  jns     short loc_18000D55B
0x18000d539  mov     eax, 80070490h
0x18000d53e  cmp     ebx, eax
0x18000d540  jnz     loc_18000D645
0x18000d546  mov     r8d, eax
0x18000d549  lea     rcx, aMspkiEnrollmen; "msPKI-Enrollment-Servers"
0x18000d550  mov     edx, 21102C1h
0x18000d555  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18000d55b  mov     rcx, rdi; hMem
0x18000d55e  mov     dword ptr [rsi+58h], 1
0x18000d565  inc     r15d
0x18000d568  call    cs:__imp_LocalFree
0x18000d56e  xor     esi, esi
0x18000d570  mov     edi, esi
0x18000d572  jmp     short loc_18000D584
0x18000d574  mov     edx, 80070057h
0x18000d579  mov     ecx, 1C902C1h
0x18000d57e  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000d584  mov     rdx, [rbp+var_20]
0x18000d588  test    rdx, rdx
0x18000d58b  jz      short loc_18000D59B
0x18000d58d  mov     rcx, [rbp+arg_18]
0x18000d591  call    cs:__imp_CAFreeCAProperty
0x18000d597  mov     [rbp+var_20], rsi
0x18000d59b  mov     rdx, [rbp+var_30]
0x18000d59f  test    rdx, rdx
0x18000d5a2  jz      short loc_18000D5B2
0x18000d5a4  mov     rcx, [rbp+arg_18]
0x18000d5a8  call    cs:__imp_CAFreeCAProperty
0x18000d5ae  mov     [rbp+var_30], rsi
0x18000d5b2  mov     rdx, [rbp+var_18]
0x18000d5b6  test    rdx, rdx
0x18000d5b9  jz      short loc_18000D5C9
0x18000d5bb  mov     rcx, [rbp+arg_18]
0x18000d5bf  call    cs:__imp_CAFreeCAProperty
0x18000d5c5  mov     [rbp+var_18], rsi
0x18000d5c9  mov     rdx, [rbp+var_38]
0x18000d5cd  test    rdx, rdx
0x18000d5d0  jz      short loc_18000D5E0
0x18000d5d2  mov     rcx, [rbp+arg_18]
0x18000d5d6  call    cs:__imp_CAFreeCAProperty
0x18000d5dc  mov     [rbp+var_38], rsi
0x18000d5e0  mov     rdx, [rbp+var_28]
0x18000d5e4  test    rdx, rdx
0x18000d5e7  jz      short loc_18000D5F7
0x18000d5e9  mov     rcx, [rbp+arg_18]
0x18000d5ed  call    cs:__imp_CAFreeCAProperty
0x18000d5f3  mov     [rbp+var_28], rsi
0x18000d5f7  mov     rcx, [rbp+arg_18]
0x18000d5fb  lea     rdx, [rbp+var_10]
0x18000d5ff  call    cs:__imp_CAEnumNextCA
0x18000d605  mov     rcx, [rbp+arg_18]
0x18000d609  mov     ebx, eax
0x18000d60b  call    cs:__imp_CACloseCA
0x18000d611  mov     rax, [rbp+var_10]
0x18000d615  mov     [rbp+arg_18], rax
0x18000d619  test    ebx, ebx
0x18000d61b  jnz     loc_18000D6BF
0x18000d621  test    rax, rax
0x18000d624  jz      loc_18000D6BF
0x18000d62a  inc     r13d
0x18000d62d  jmp     loc_18000D305
0x18000d632  mov     ecx, 1D802C1h
0x18000d637  jmp     short loc_18000D677
0x18000d639  mov     edx, eax
0x18000d63b  mov     ecx, 1F802C1h
0x18000d640  jmp     loc_18000D2F4
0x18000d645  mov     edx, ebx
0x18000d647  mov     ecx, 21602C1h
0x18000d64c  jmp     loc_18000D2F4
0x18000d651  mov     edx, eax
0x18000d653  mov     ecx, 20902C1h
0x18000d658  jmp     loc_18000D2F4
0x18000d65d  mov     edx, 8007000Eh
0x18000d662  mov     ecx, 1E402C1h
0x18000d667  mov     ebx, edx
0x18000d669  jmp     short loc_18000D679
0x18000d66b  mov     ecx, 1D302C1h
0x18000d670  jmp     short loc_18000D677
0x18000d672  mov     ecx, 1CE02C1h
0x18000d677  mov     edx, eax
0x18000d679  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000d67f  xor     esi, esi
0x18000d681  jmp     short loc_18000D6D2
0x18000d683  mov     edx, eax
0x18000d685  mov     ecx, 1C202C1h
0x18000d68a  jmp     loc_18000D2F4
0x18000d68f  mov     edx, eax
0x18000d691  mov     ecx, 1BF02C1h
0x18000d696  jmp     loc_18000D2F4
0x18000d69b  mov     edx, eax
0x18000d69d  mov     ecx, 1BC02C1h
0x18000d6a2  jmp     loc_18000D2F4
0x18000d6a7  mov     edx, eax
0x18000d6a9  mov     ecx, 1B902C1h
0x18000d6ae  jmp     loc_18000D2F4
0x18000d6b3  mov     edx, eax
0x18000d6b5  mov     ecx, 1B602C1h
  ... truncated ...
```
