# GetServiceLocation(ulong,uint,uint,ushort *,uint *,ushort *)

- ea: `0x180026568`
- end: `0x180026b2e`
- name: `?GetServiceLocation@@YAJKIIPEAGPEAI0@Z`
- size: `1478`
- prototype: `int(unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c1c0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017210`
- `0x1800253c8`
- `0x1800254d0`
- `0x180025728`
- `0x1800262b4`
- `0x180026568`
- `0x180026b34`
- `0x18002c758`
- `0x180039970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800268a9`
- `msvcrt!wcsrchr` at `0x1800268a9`

## string_xrefs

- `0x1800265c2`: `[msdrm]: Parameters uServiceType=%d,uServiceLocation=%d,wszIssuanceLicense=%S`
- `0x18002661d`: `[msdrm]: GetRegistryKey for CloudPubKey failed with hr = 0x%08x.Continuing with global cloud license server URL.`
- `0x18002686a`: `LicensingService`
- `0x180026871`: `LicensingInternalService`
- `0x180026714`: `SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing`
- `0x180026633`: `https://licensing.drm.microsoft.com/licensing`
- `0x1800266de`: `https://licensing.drm.microsoft.com/licensing`
- `0x180026605`: `SOFTWARE\Microsoft\MSDRM\ServiceLocation\CloudPublishing`
- `0x1800267dc`: `CertificationService`
- `0x1800269e0`: `CertificationService`
- `0x180026a15`: `CertificationService`
- `0x1800267ba`: `CertificationInternalService`
- `0x1800269bc`: `CertificationInternalService`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall GetServiceLocation(
        __int64 a1,
        char a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r15
  int v9; // r14d
  bool v10; // r12
  int v11; // edi
  HKEY v12; // rcx
  signed int CertificationUrlFromRegistryOrAD; // edi
  int RegistryKey; // eax
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rdx
  signed __int64 v18; // rdi
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // r14
  wchar_t *v22; // rax
  int ServiceLocationRequest; // edi
  int v24; // r13d
  const wchar_t *v25; // rcx
  const unsigned __int16 *v26; // rcx
  wchar_t *v27; // rax
  __int64 v28; // rax
  unsigned __int64 v29; // r12
  int v30; // eax
  int v31; // r13d
  unsigned int v32; // r14d
  unsigned int *v33; // r11
  wchar_t *Str; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 *v36; // [rsp+28h] [rbp-50h] BYREF
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v38[3]; // [rsp+38h] [rbp-40h] BYREF
  int v39; // [rsp+88h] [rbp+10h]
  int v40; // [rsp+88h] [rbp+10h]

  v38[1] = (unsigned __int16 *)-2LL;
  Str = 0;
  v38[0] = 0;
  v7 = 0;
  Block = 0;
  v8 = 0;
  v36 = 0;
  v9 = 1;
  v10 = (a2 & 0x10) != 0;
  v11 = a2 & 0xF;
  v39 = v11;
  _RTLTRACE("[msdrm]: Parameters uServiceType=%d,uServiceLocation=%d,wszIssuanceLicense=%S", v11, a3, a4);
  if ( (unsigned int)(v11 - 1) <= 1 )
  {
    if ( !a4 )
    {
      if ( a3 == 1 )
      {
        CertificationUrlFromRegistryOrAD = -2147168439;
        goto LABEL_85;
      }
      CertificationUrlFromRegistryOrAD = GetCertificationUrlFromRegistryOrAD(&Str);
      if ( CertificationUrlFromRegistryOrAD < 0 )
        goto LABEL_85;
      goto LABEL_76;
    }
    v30 = ExtractUrlFromIL(a4, (unsigned __int16 **)&Block, &v36);
    CertificationUrlFromRegistryOrAD = v30;
    if ( v30 < 0 )
    {
      _RTLTRACE("[msdrm]: ExtractUrlFromIL FAILED : %x ", v30);
      v7 = (unsigned __int16 *)Block;
      v8 = v36;
      goto LABEL_85;
    }
    v7 = (unsigned __int16 *)Block;
    v8 = v36;
    if ( !Block && !v36 )
    {
LABEL_61:
      CertificationUrlFromRegistryOrAD = -2147168440;
      goto LABEL_85;
    }
    if ( !(unsigned int)DoesSuffixMatchesIppOnline((const unsigned __int16 *)Block)
      || (unsigned int)IsIppOnlinePrepPackageInstalled() )
    {
      CertificationUrlFromRegistryOrAD = FindServiceLocationRequest(L"CertificationInternalService", v7, &Str, v10);
      if ( CertificationUrlFromRegistryOrAD >= 0 )
        goto LABEL_76;
      v31 = 0;
      CertificationUrlFromRegistryOrAD = FindServiceLocationRequest(L"CertificationService", v7, &Str, v10);
      if ( CertificationUrlFromRegistryOrAD >= 0 )
        goto LABEL_76;
    }
    else
    {
      v31 = 1;
    }
    if ( !(unsigned int)DoesSuffixMatchesIppOnline(v8) || (unsigned int)IsIppOnlinePrepPackageInstalled() )
    {
      v9 = 0;
      CertificationUrlFromRegistryOrAD = FindServiceLocationRequest(L"CertificationService", v8, &Str, v10);
      if ( CertificationUrlFromRegistryOrAD >= 0 )
        goto LABEL_76;
    }
    if ( !v31 && !v9 )
      goto LABEL_61;
    goto LABEL_72;
  }
  if ( v11 != 4 )
  {
    CertificationUrlFromRegistryOrAD = 0;
    if ( v39 != 8 )
      goto LABEL_76;
  }
  if ( a3 == 1 )
  {
    RegistryKey = GetRegistryKey(v12, L"SOFTWARE\\Microsoft\\MSDRM\\ServiceLocation\\CloudPublishing", 0, &Str);
    CertificationUrlFromRegistryOrAD = RegistryKey;
    if ( RegistryKey < 0 )
    {
      _RTLTRACE(
        "[msdrm]: GetRegistryKey for CloudPubKey failed with hr = 0x%08x.Continuing with global cloud license server URL.",
        RegistryKey);
      v15 = 0x7FFFFFFF;
      v16 = L"https://licensing.drm.microsoft.com/licensing";
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      CertificationUrlFromRegistryOrAD = v15 == 0 ? 0x80070057 : 0;
      v17 = (0x7FFFFFFF - v15) & ((unsigned __int128)-(__int128)(unsigned __int64)v15 >> 64);
      if ( !v15 )
        goto LABEL_85;
      v18 = v17 + 1;
      if ( v17 + 1 < v17 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v18 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v19 = 2LL * (unsigned int)v18;
      v20 = HIDWORD(v18) << 33;
      if ( v20 + v19 < v19 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v20 + v19 )
      {
        v21 = -1;
        v22 = (wchar_t *)operator new[](saturated_mul(v18, 2u));
        Str = v22;
        if ( !v22 )
        {
          CertificationUrlFromRegistryOrAD = -2147024882;
          goto LABEL_85;
        }
        CertificationUrlFromRegistryOrAD = StringCchCopyW(v22, v18, L"https://licensing.drm.microsoft.com/licensing");
        if ( CertificationUrlFromRegistryOrAD < 0 )
          goto LABEL_85;
      }
      else
      {
        v21 = -1;
      }
      CertificationUrlFromRegistryOrAD = 0;
      goto LABEL_77;
    }
    goto LABEL_76;
  }
  CertificationUrlFromRegistryOrAD = GetRegistryKey(
                                       v12,
                                       L"SOFTWARE\\Microsoft\\MSDRM\\ServiceLocation\\EnterprisePublishing",
                                       0,
                                       &Str);
  if ( CertificationUrlFromRegistryOrAD >= 0 )
    goto LABEL_76;
  if ( !a4 )
  {
    CertificationUrlFromRegistryOrAD = GetCertificationUrlFromRegistryOrAD(&Str);
    if ( CertificationUrlFromRegistryOrAD < 0 )
      goto LABEL_85;
    goto LABEL_42;
  }
  ServiceLocationRequest = ExtractUrlFromIL(a4, (unsigned __int16 **)&Block, &v36);
  v7 = (unsigned __int16 *)Block;
  v8 = v36;
  if ( ServiceLocationRequest < 0 || !Block && !v36 )
    goto LABEL_39;
  if ( !(unsigned int)DoesSuffixMatchesIppOnline((const unsigned __int16 *)Block)
    || (v40 = 1, (unsigned int)IsIppOnlinePrepPackageInstalled()) )
  {
    v40 = 0;
  }
  if ( !(unsigned int)DoesSuffixMatchesIppOnline(v8) || (v24 = 1, (unsigned int)IsIppOnlinePrepPackageInstalled()) )
    v24 = 0;
  if ( !v40 )
  {
    ServiceLocationRequest = FindServiceLocationRequest(L"CertificationInternalService", v7, &Str, v10);
    if ( ServiceLocationRequest >= 0 )
    {
LABEL_42:
      operator delete(v7);
      v7 = Str;
      Str = 0;
      if ( !(unsigned int)DoesSuffixMatchesIppOnline(v7) || (unsigned int)IsIppOnlinePrepPackageInstalled() )
      {
        v26 = L"LicensingInternalService";
        if ( !v9 )
          v26 = L"LicensingService";
        CertificationUrlFromRegistryOrAD = FindServiceLocationRequest(v26, v7, &Str, v10);
        if ( CertificationUrlFromRegistryOrAD < 0 )
        {
          v25 = v7;
          v38[0] = v7;
          v7 = 0;
          goto LABEL_48;
        }
LABEL_76:
        v21 = -1;
LABEL_77:
        if ( Str )
        {
          do
            ++v21;
          while ( Str[v21] );
          v32 = v21 + 1;
          v33 = a5;
          if ( a6 )
          {
            if ( *a5 >= v32 )
            {
              CertificationUrlFromRegistryOrAD = StringCchCopyW(a6, *a5, Str);
              if ( CertificationUrlFromRegistryOrAD < 0 )
                goto LABEL_85;
            }
            else
            {
              CertificationUrlFromRegistryOrAD = -2147024774;
            }
          }
          *v33 = v32;
          goto LABEL_85;
        }
        CertificationUrlFromRegistryOrAD = -2147168440;
        _RTLTRACE("[msdrm]:Failed with hr : %x", -2147168440);
        goto LABEL_85;
      }
LABEL_72:
      DisplayIppOnlineError((const unsigned __int16 *)0x1775, v10);
      CertificationUrlFromRegistryOrAD = -2147168444;
      goto LABEL_85;
    }
  }
  if ( !v24 )
  {
    ServiceLocationRequest = FindServiceLocationRequest(L"CertificationService", v8, &Str, v10);
    if ( ServiceLocationRequest >= 0 )
    {
      v9 = 0;
      goto LABEL_42;
    }
  }
  if ( v40 || v24 )
    goto LABEL_72;
  v9 = 0;
  if ( ServiceLocationRequest >= 0 )
    goto LABEL_42;
LABEL_39:
  CertificationUrlFromRegistryOrAD = GetCertificationUrlFromRegistryOrAD(v38);
  if ( CertificationUrlFromRegistryOrAD < 0 )
    goto LABEL_85;
  v25 = v38[0];
LABEL_48:
  v27 = wcsrchr(v25, 0x2Fu);
  if ( !v27 )
    goto LABEL_61;
  *v27 = 0;
  v21 = -1;
  v28 = -1;
  do
    ++v28;
  while ( v38[0][v28] );
  v29 = v28 + 11;
  Str = (wchar_t *)operator new[](saturated_mul(v28 + 11, 2u));
  if ( !Str )
  {
    CertificationUrlFromRegistryOrAD = -2147024882;
    goto LABEL_85;
  }
  CertificationUrlFromRegistryOrAD = StringCchCopyW(Str, v29, v38[0]);
  if ( CertificationUrlFromRegistryOrAD >= 0 )
  {
    CertificationUrlFromRegistryOrAD = StringCchCatW(Str, v29, L"/licensing");
    if ( CertificationUrlFromRegistryOrAD >= 0 )
      goto LABEL_77;
  }
LABEL_85:
  operator delete(Str);
  Str = 0;
  operator delete(v7);
  operator delete(v8);
  operator delete(v38[0]);
  return (unsigned int)CertificationUrlFromRegistryOrAD;
}

```

## disassembly

```asm
0x180026568  mov     rax, rsp
0x18002656b  mov     [rax+18h], r8d
0x18002656f  push    rdi
0x180026570  push    r12
0x180026572  push    r13
0x180026574  push    r14
0x180026576  push    r15
0x180026578  sub     rsp, 50h
0x18002657c  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180026584  mov     [rax+8], rbx
0x180026588  mov     [rax+20h], rsi
0x18002658c  mov     r13, r9
0x18002658f  mov     edi, edx
0x180026591  xor     ebx, ebx
0x180026593  mov     [rax-58h], rbx
0x180026597  mov     [rax-40h], rbx
0x18002659b  mov     esi, ebx
0x18002659d  mov     [rax-48h], rbx
0x1800265a1  mov     r15d, ebx
0x1800265a4  mov     [rax-50h], rbx
0x1800265a8  mov     r12d, edx
0x1800265ab  shr     r12d, 4
0x1800265af  lea     r14d, [rbx+1]
0x1800265b3  and     r12b, r14b
0x1800265b6  and     edi, 0Fh
0x1800265b9  mov     [rsp+78h+arg_8], edi
0x1800265c0  mov     edx, edi
0x1800265c2  lea     rcx, aMsdrmParameter; "[msdrm]: Parameters uServiceType=%d,uSe"...
0x1800265c9  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800265ce  lea     eax, [rdi-1]
0x1800265d1  cmp     eax, r14d
0x1800265d4  jbe     loc_18002693B
0x1800265da  cmp     edi, 4
0x1800265dd  jz      short loc_1800265EF
0x1800265df  mov     edi, ebx
0x1800265e1  cmp     [rsp+78h+arg_8], 8
0x1800265e9  jnz     loc_180026A6E
0x1800265ef  lea     r9, [rsp+78h+Str]; unsigned __int16 **
0x1800265f4  xor     r8d, r8d; unsigned __int16 *
0x1800265f7  cmp     [rsp+78h+arg_10], r14d
0x1800265ff  jnz     loc_180026714
0x180026605  lea     rdx, ?g_wszSD_CloudPubKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\ServiceLoca"...
0x18002660c  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180026611  mov     edi, eax
0x180026613  test    eax, eax
0x180026615  jns     loc_180026A6E
0x18002661b  mov     edx, eax
0x18002661d  lea     rcx, aMsdrmGetregist; "[msdrm]: GetRegistryKey for CloudPubKey"...
0x180026624  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180026629  nop
0x18002662a  mov     r8d, 7FFFFFFFh
0x180026630  mov     ecx, r8d
0x180026633  lea     rax, ?g_wszCloudLicenseServerUrl@@3QBGB; "https://licensing.drm.microsoft.com/lic"...
0x18002663a  cmp     [rax], bx
0x18002663d  jz      short loc_180026648
0x18002663f  add     rax, 2
0x180026643  sub     rcx, r14
0x180026646  jnz     short loc_18002663A
0x180026648  mov     rax, rcx
0x18002664b  neg     rax
0x18002664e  sbb     edi, edi
0x180026650  not     edi
0x180026652  and     edi, 80070057h
0x180026658  mov     rax, rcx
0x18002665b  sub     r8, rcx
0x18002665e  neg     rax
0x180026661  sbb     rdx, rdx
0x180026664  and     rdx, r8
0x180026667  test    rcx, rcx
0x18002666a  jnz     short loc_180026671
0x18002666c  jmp     loc_180026AD7
0x180026671  lea     rdi, [rdx+1]
0x180026675  cmp     rdi, rdx
0x180026678  jb      loc_180026B1C
0x18002667e  mov     rcx, rdi
0x180026681  shr     rcx, 20h
0x180026685  mov     rax, rcx
0x180026688  shr     rax, 1Fh
0x18002668c  test    eax, eax
0x18002668e  jnz     loc_180026B22
0x180026694  mov     eax, edi
0x180026696  add     rax, rax
0x180026699  shl     rcx, 21h
0x18002669d  lea     rdx, [rcx+rax]
0x1800266a1  cmp     rdx, rax
0x1800266a4  jb      loc_180026B27
0x1800266aa  test    rdx, rdx
0x1800266ad  jz      short loc_1800266FB
0x1800266af  mov     eax, 2
0x1800266b4  mul     rdi
0x1800266b7  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800266be  cmovb   rax, r14
0x1800266c2  mov     rcx, rax; unsigned __int64
0x1800266c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800266ca  mov     [rsp+78h+Str], rax
0x1800266cf  test    rax, rax
0x1800266d2  jnz     short loc_1800266DE
0x1800266d4  mov     edi, 8007000Eh
0x1800266d9  jmp     loc_180026AD7
0x1800266de  lea     r8, ?g_wszCloudLicenseServerUrl@@3QBGB; "https://licensing.drm.microsoft.com/lic"...
0x1800266e5  mov     rdx, rdi; unsigned __int64
0x1800266e8  mov     rcx, rax; unsigned __int16 *
0x1800266eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800266f0  mov     edi, eax
0x1800266f2  test    eax, eax
0x1800266f4  jns     short loc_1800266FF
0x1800266f6  jmp     loc_180026AD7
0x1800266fb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800266ff  mov     edi, ebx
0x180026701  jmp     loc_180026A72
0x180026706  xor     ebx, ebx
0x180026708  mov     edi, [rsp+78h+arg_8]
0x18002670f  jmp     loc_18002696A
0x180026714  lea     rdx, ?g_wszSD_EnterprisePubKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\ServiceLoca"...
0x18002671b  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180026720  mov     edi, eax
0x180026722  test    eax, eax
0x180026724  jns     loc_180026A6E
0x18002672a  test    r13, r13
0x18002672d  jz      loc_18002682B
0x180026733  lea     r8, [rsp+78h+var_50]; unsigned __int16 **
0x180026738  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x18002673d  mov     rcx, r13; unsigned __int16 *
0x180026740  call    ?ExtractUrlFromIL@@YAJPEAGPEAPEAG1@Z; ExtractUrlFromIL(ushort *,ushort * *,ushort * *)
0x180026745  mov     edi, eax
0x180026747  mov     rsi, [rsp+78h+Block]
0x18002674c  mov     r15, [rsp+78h+var_50]
0x180026751  test    eax, eax
0x180026753  js      loc_180026810
0x180026759  test    rsi, rsi
0x18002675c  jnz     short loc_180026767
0x18002675e  test    r15, r15
0x180026761  jz      loc_180026810
0x180026767  mov     rcx, rsi; unsigned __int16 *
0x18002676a  call    ?DoesSuffixMatchesIppOnline@@YAHPEBG@Z; DoesSuffixMatchesIppOnline(ushort const *)
0x18002676f  test    eax, eax
0x180026771  jz      short loc_180026784
0x180026773  call    ?IsIppOnlinePrepPackageInstalled@@YAHXZ; IsIppOnlinePrepPackageInstalled(void)
0x180026778  test    eax, eax
0x18002677a  mov     [rsp+78h+arg_8], r14d
0x180026782  jz      short loc_18002678B
0x180026784  mov     [rsp+78h+arg_8], ebx
0x18002678b  mov     rcx, r15; unsigned __int16 *
0x18002678e  call    ?DoesSuffixMatchesIppOnline@@YAHPEBG@Z; DoesSuffixMatchesIppOnline(ushort const *)
0x180026793  test    eax, eax
0x180026795  jz      short loc_1800267A3
0x180026797  call    ?IsIppOnlinePrepPackageInstalled@@YAHXZ; IsIppOnlinePrepPackageInstalled(void)
0x18002679c  test    eax, eax
0x18002679e  mov     r13d, r14d
0x1800267a1  jz      short loc_1800267A6
0x1800267a3  mov     r13d, ebx
0x1800267a6  cmp     [rsp+78h+arg_8], ebx
0x1800267ad  jnz     short loc_1800267CC
0x1800267af  mov     r9b, r12b; bool
0x1800267b2  lea     r8, [rsp+78h+Str]; unsigned __int16 **
0x1800267b7  mov     rdx, rsi; unsigned __int16 *
0x1800267ba  lea     rcx, ?g_wszPUB_CertificationInternalService@@3QBGB; "CertificationInternalService"
0x1800267c1  call    ?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z; FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)
0x1800267c6  mov     edi, eax
0x1800267c8  test    eax, eax
0x1800267ca  jns     short loc_18002683F
0x1800267cc  test    r13d, r13d
0x1800267cf  jnz     short loc_1800267F3
0x1800267d1  mov     r9b, r12b; bool
0x1800267d4  lea     r8, [rsp+78h+Str]; unsigned __int16 **
0x1800267d9  mov     rdx, r15; unsigned __int16 *
0x1800267dc  lea     rcx, ?g_wszPUB_CertificationService@@3QBGB; "CertificationService"
0x1800267e3  call    ?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z; FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)
0x1800267e8  mov     edi, eax
0x1800267ea  test    eax, eax
0x1800267ec  js      short loc_1800267F3
0x1800267ee  mov     r14d, ebx
0x1800267f1  jmp     short loc_18002683F
0x1800267f3  cmp     [rsp+78h+arg_8], ebx
0x1800267fa  jnz     loc_180026A35
0x180026800  test    r13d, r13d
0x180026803  jnz     loc_180026A35
0x180026809  mov     r14d, ebx
0x18002680c  test    edi, edi
0x18002680e  jns     short loc_18002683F
0x180026810  lea     rcx, [rsp+78h+var_40]; unsigned __int16 **
0x180026815  call    ?GetCertificationUrlFromRegistryOrAD@@YAJPEAPEAG@Z; GetCertificationUrlFromRegistryOrAD(ushort * *)
0x18002681a  mov     edi, eax
0x18002681c  test    eax, eax
0x18002681e  js      loc_180026AD7
0x180026824  mov     rcx, [rsp+78h+var_40]
0x180026829  jmp     short loc_1800268A4
0x18002682b  lea     rcx, [rsp+78h+Str]; unsigned __int16 **
0x180026830  call    ?GetCertificationUrlFromRegistryOrAD@@YAJPEAPEAG@Z; GetCertificationUrlFromRegistryOrAD(ushort * *)
0x180026835  mov     edi, eax
0x180026837  test    eax, eax
0x180026839  js      loc_180026AD7
0x18002683f  mov     rcx, rsi; Block
0x180026842  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026847  mov     rsi, [rsp+78h+Str]
0x18002684c  mov     [rsp+78h+Str], rbx
0x180026851  mov     rcx, rsi; unsigned __int16 *
0x180026854  call    ?DoesSuffixMatchesIppOnline@@YAHPEBG@Z; DoesSuffixMatchesIppOnline(ushort const *)
0x180026859  test    eax, eax
0x18002685b  jz      short loc_18002686A
0x18002685d  call    ?IsIppOnlinePrepPackageInstalled@@YAHXZ; IsIppOnlinePrepPackageInstalled(void)
0x180026862  test    eax, eax
0x180026864  jz      loc_180026A35
0x18002686a  lea     rax, ?g_wszPUB_LicensingService@@3QBGB; "LicensingService"
0x180026871  lea     rcx, ?g_wszPUB_LicensingInternalService@@3QBGB; "LicensingInternalService"
0x180026878  test    r14d, r14d
0x18002687b  cmovz   rcx, rax; unsigned __int16 *
0x18002687f  mov     r9b, r12b; bool
0x180026882  lea     r8, [rsp+78h+Str]; unsigned __int16 **
0x180026887  mov     rdx, rsi; unsigned __int16 *
0x18002688a  call    ?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z; FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)
0x18002688f  mov     edi, eax
0x180026891  test    eax, eax
0x180026893  jns     loc_180026A6E
0x180026899  mov     rcx, rsi; Str
0x18002689c  mov     [rsp+78h+var_40], rcx
0x1800268a1  mov     rsi, rbx
0x1800268a4  mov     edx, 2Fh ; '/'; Ch
0x1800268a9  call    cs:__imp_wcsrchr
0x1800268af  test    rax, rax
0x1800268b2  jz      loc_18002698D
0x1800268b8  mov     [rax], bx
0x1800268bb  mov     rcx, [rsp+78h+var_40]
0x1800268c0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800268c4  mov     rax, r14
0x1800268c7  inc     rax
0x1800268ca  cmp     [rcx+rax*2], bx
0x1800268ce  jnz     short loc_1800268C7
0x1800268d0  lea     r12, [rax+0Bh]
0x1800268d4  mov     eax, 2
0x1800268d9  mul     r12
0x1800268dc  cmovb   rax, r14
0x1800268e0  mov     rcx, rax; unsigned __int64
0x1800268e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800268e8  mov     [rsp+78h+Str], rax
0x1800268ed  test    rax, rax
0x1800268f0  jnz     short loc_1800268FC
0x1800268f2  mov     edi, 8007000Eh
0x1800268f7  jmp     loc_180026AD7
0x1800268fc  mov     r8, [rsp+78h+var_40]; unsigned __int16 *
0x180026901  mov     rdx, r12; unsigned __int64
0x180026904  mov     rcx, [rsp+78h+Str]; unsigned __int16 *
0x180026909  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002690e  mov     edi, eax
0x180026910  test    eax, eax
0x180026912  js      loc_180026AD7
0x180026918  lea     r8, aLicensing; "/licensing"
0x18002691f  mov     rdx, r12; unsigned __int64
0x180026922  mov     rcx, [rsp+78h+Str]; unsigned __int16 *
0x180026927  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002692c  mov     edi, eax
0x18002692e  test    eax, eax
0x180026930  jns     loc_180026A72
0x180026936  jmp     loc_180026AD7
0x18002693b  test    r13, r13
0x18002693e  jz      loc_180026A4D
0x180026944  lea     r8, [rsp+78h+var_50]; unsigned __int16 **
0x180026949  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x18002694e  mov     rcx, r13; unsigned __int16 *
0x180026951  call    ?ExtractUrlFromIL@@YAJPEAGPEAPEAG1@Z; ExtractUrlFromIL(ushort *,ushort * *,ushort * *)
0x180026956  mov     edi, eax
0x180026958  test    eax, eax
0x18002695a  jns     short loc_180026979
0x18002695c  mov     edx, eax
0x18002695e  lea     rcx, aMsdrmExtractur; "[msdrm]: ExtractUrlFromIL FAILED : %x "
0x180026965  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002696a  mov     rsi, [rsp+78h+Block]
0x18002696f  mov     r15, [rsp+78h+var_50]
0x180026974  jmp     loc_180026AD7
0x180026979  mov     rsi, [rsp+78h+Block]
0x18002697e  mov     r15, [rsp+78h+var_50]
0x180026983  test    rsi, rsi
0x180026986  jnz     short loc_180026997
0x180026988  test    r15, r15
0x18002698b  jnz     short loc_180026997
0x18002698d  mov     edi, 8004CF48h
0x180026992  jmp     loc_180026AD7
0x180026997  mov     rcx, rsi; unsigned __int16 *
0x18002699a  call    ?DoesSuffixMatchesIppOnline@@YAHPEBG@Z; DoesSuffixMatchesIppOnline(ushort const *)
0x18002699f  test    eax, eax
0x1800269a1  jz      short loc_1800269B1
0x1800269a3  call    ?IsIppOnlinePrepPackageInstalled@@YAHXZ; IsIppOnlinePrepPackageInstalled(void)
0x1800269a8  test    eax, eax
0x1800269aa  jnz     short loc_1800269B1
0x1800269ac  mov     r13d, r14d
0x1800269af  jmp     short loc_1800269F2
0x1800269b1  mov     r9b, r12b; bool
0x1800269b4  lea     r8, [rsp+78h+Str]; unsigned __int16 **
0x1800269b9  mov     rdx, rsi; unsigned __int16 *
0x1800269bc  lea     rcx, ?g_wszPUB_CertificationInternalService@@3QBGB; "CertificationInternalService"
0x1800269c3  call    ?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z; FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)
0x1800269c8  mov     edi, eax
0x1800269ca  test    eax, eax
0x1800269cc  jns     loc_180026A6E
0x1800269d2  mov     r13d, ebx
0x1800269d5  mov     r9b, r12b; bool
0x1800269d8  lea     r8, [rsp+78h+Str]; unsigned __int16 **
0x1800269dd  mov     rdx, rsi; unsigned __int16 *
0x1800269e0  lea     rcx, ?g_wszPUB_CertificationService@@3QBGB; "CertificationService"
0x1800269e7  call    ?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z; FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)
  ... truncated ...
```
