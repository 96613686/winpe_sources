# OpenDisplay

- ea: `0x180007bb0`
- end: `0x180007fa2`
- name: `OpenDisplay`
- size: `1010`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006f60`
- `0x180041d50`

## callees

- `0x180007bb0`
- `0x180008bf0`
- `0x18000efbc`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18004da68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f60`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f60`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007d18`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007d18`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007d9e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180007d9e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180007d62`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180007d62`
- `ntdll!RtlGetPersistedStateLocation` at `0x180007cad`
- `ntdll!RtlGetPersistedStateLocation` at `0x180007cad`
- `ntdll!RtlNtStatusToDosError` at `0x180007cb9`
- `ntdll!RtlNtStatusToDosError` at `0x180007cb9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f55`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007d43`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007d43`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007cce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007cce`

## pseudocode

```c
_BOOL8 __fastcall OpenDisplay(wchar_t *Str, HKEY *a2, __int64 a3, int a4)
{
  wchar_t *v7; // r8
  __int64 v8; // r14
  WCHAR *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  NTSTATUS PersistedStateLocation; // eax
  __int64 cchDest; // rbx
  WCHAR *lpDestStr; // rax
  wchar_t *v16; // rdi
  __int64 v17; // rdx
  wchar_t *v18; // rax
  signed int v19; // edx
  __int64 v20; // r8
  unsigned __int16 *v21; // rax
  __int64 v22; // r9
  const unsigned __int16 *v23; // rax
  __int64 v24; // rcx
  unsigned __int16 *v25; // r8
  __int64 v26; // rdx
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  WCHAR *v29; // rax
  __int64 v30; // r9
  const WCHAR *v31; // rcx
  WCHAR *v32; // rax
  __int64 v33; // r8
  WCHAR *v34; // rcx
  LSTATUS Key; // eax
  bool v36; // zf
  HKEY phkResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v40[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(SubKey, 0, 0x208u);
  memset_0(v40, 0, 0x208u);
  v7 = gszDeviceClass;
  v8 = 2147483646;
  phkResult[0] = 0;
  v9 = SubKey;
  v10 = 2147483646;
  v11 = 260;
  do
  {
    if ( !v10 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v10;
    --v11;
  }
  while ( v11 );
  v12 = v9 - 1;
  if ( v11 )
    v12 = v9;
  *v12 = 0;
  if ( v11 && (int)StringCchCatW(SubKey, 0x104u, gszMonitorGUID) >= 0 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"SystemColorProfileAssociations",
                               0,
                               L"System\\CurrentControlSet\\Control\\Class\\{4D36E96E-E325-11CE-BFC1-08002BE10318}",
                               0,
                               SubKey,
                               520,
                               0);
    if ( PersistedStateLocation < 0 )
    {
      RtlNtStatusToDosError(PersistedStateLocation);
      goto LABEL_51;
    }
    if ( lstrcmpiW(Str, gszDisplay) )
    {
      cchDest = -1;
      do
        ++cchDest;
      while ( Str[cchDest] );
      if ( (unsigned int)cchDest > 0x7FFFFFFE )
        goto LABEL_51;
      lpDestStr = (WCHAR *)malloc(2LL * (unsigned int)(cchDest + 1));
      v16 = lpDestStr;
      if ( !lpDestStr )
        goto LABEL_51;
      if ( !LCMapStringW(0x7Fu, 0x200u, Str, cchDest, lpDestStr, cchDest) )
        goto LABEL_50;
      v16[(unsigned int)cchDest] = 0;
      if ( !wcsstr(v16, gszMonitorGUID) )
        goto LABEL_50;
      LOBYTE(v17) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::GetImpl'::`2'::impl,
        v17);
      if ( (int)OpenDisplayMux(Str, 0, phkResult) >= 0 )
        goto LABEL_50;
      v18 = wcsrchr(Str, 0x5Cu);
      if ( v18 == (wchar_t *)-2LL )
      {
        v20 = 260;
        v21 = v40;
        do
        {
          if ( !*v21 )
            break;
          ++v21;
          --v20;
        }
        while ( v20 );
        v19 = v20 == 0 ? 0x80070057 : 0;
        v22 = (260 - v20) & -(__int64)(v20 != 0);
        if ( v20 )
        {
          v23 = L"0000";
          v24 = 2147483646;
          v25 = &v40[v22];
          v26 = 260 - v22;
          if ( v22 != 260 )
          {
            do
            {
              if ( !v24 )
                break;
              if ( !*v23 )
                break;
              *v25++ = *v23++;
              --v24;
              --v26;
            }
            while ( v26 );
          }
          v27 = v25 - 1;
          if ( v26 )
            v27 = v25;
          v19 = v26 == 0 ? 0x8007007A : 0;
          *v27 = 0;
        }
      }
      else
      {
        v19 = StringCchCatW(v40, 0x104u, v18 + 1);
      }
      if ( v19 < 0 )
      {
LABEL_50:
        free(v16);
        goto LABEL_51;
      }
      free(v16);
    }
    else if ( (int)StringCchCatW(v40, 0x104u, L"0000") < 0 )
    {
      goto LABEL_51;
    }
    v28 = 260;
    v29 = SubKey;
    do
    {
      if ( !*v29 )
        break;
      ++v29;
      --v28;
    }
    while ( v28 );
    v30 = (260 - v28) & -(__int64)(v28 != 0);
    if ( v28 )
    {
      v31 = L"\\";
      v32 = &SubKey[v30];
      v33 = 260 - v30;
      if ( v30 != 260 )
      {
        do
        {
          if ( !v8 )
            break;
          if ( !*v31 )
            break;
          *v32++ = *v31++;
          --v8;
          --v33;
        }
        while ( v33 );
      }
      v34 = v32 - 1;
      if ( v33 )
        v34 = v32;
      *v34 = 0;
      if ( v33 )
      {
        if ( (int)StringCchCatW(SubKey, 0x104u, v40) >= 0 )
        {
          Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, a4 != 0 ? 1 : 131079, 0, phkResult, 0);
          if ( Key )
            SetLastError(Key);
        }
      }
    }
  }
LABEL_51:
  v36 = phkResult[0] == 0;
  *a2 = phkResult[0];
  return !v36;
}

```

## disassembly

```asm
0x180007bb0  mov     [rsp-8+arg_10], rbx
0x180007bb5  push    rbp
0x180007bb6  push    rsi
0x180007bb7  push    rdi
0x180007bb8  push    r12
0x180007bba  push    r13
0x180007bbc  push    r14
0x180007bbe  push    r15
0x180007bc0  lea     rbp, [rsp-390h]
0x180007bc8  sub     rsp, 490h
0x180007bcf  mov     rax, cs:__security_cookie
0x180007bd6  xor     rax, rsp
0x180007bd9  mov     [rbp+3C0h+var_40], rax
0x180007be0  mov     r12, rdx
0x180007be3  mov     rsi, rcx
0x180007be6  mov     edi, 208h
0x180007beb  lea     rcx, [rsp+4C0h+SubKey]; void *
0x180007bf0  mov     r8d, edi; Size
0x180007bf3  xor     edx, edx; Val
0x180007bf5  mov     r15d, r9d
0x180007bf8  call    memset_0
0x180007bfd  mov     r8d, edi; Size
0x180007c00  lea     rcx, [rbp+3C0h+var_250]; void *
0x180007c07  xor     edx, edx; Val
0x180007c09  call    memset_0
0x180007c0e  xor     r13d, r13d
0x180007c11  lea     r8, gszDeviceClass; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x180007c18  mov     r14d, 7FFFFFFEh
0x180007c1e  mov     [rsp+4C0h+var_470], r13
0x180007c23  mov     ebx, 104h
0x180007c28  lea     rax, [rsp+4C0h+SubKey]
0x180007c2d  mov     ecx, r14d
0x180007c30  mov     edx, ebx
0x180007c32  test    rcx, rcx
0x180007c35  jz      short loc_180007C56
0x180007c37  movzx   r9d, word ptr [r8]
0x180007c3b  test    r9w, r9w
0x180007c3f  jz      short loc_180007C56
0x180007c41  mov     [rax], r9w
0x180007c45  add     r8, 2
0x180007c49  add     rax, 2
0x180007c4d  dec     rcx
0x180007c50  sub     rdx, 1
0x180007c54  jnz     short loc_180007C32
0x180007c56  test    rdx, rdx
0x180007c59  lea     rcx, [rax-2]
0x180007c5d  cmovnz  rcx, rax
0x180007c61  mov     [rcx], r13w
0x180007c65  jz      loc_180007F66
0x180007c6b  lea     r8, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x180007c72  mov     rdx, rbx; unsigned __int64
0x180007c75  lea     rcx, [rsp+4C0h+SubKey]; unsigned __int16 *
0x180007c7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c7f  test    eax, eax
0x180007c81  js      loc_180007F66
0x180007c87  mov     [rsp+4C0h+lpSecurityAttributes], r13
0x180007c8c  lea     rax, [rsp+4C0h+SubKey]
0x180007c91  mov     [rsp+4C0h+cchDest], edi
0x180007c95  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cla"...
0x180007c9c  xor     r9d, r9d
0x180007c9f  mov     [rsp+4C0h+lpDestStr], rax
0x180007ca4  xor     edx, edx
0x180007ca6  lea     rcx, aSystemcolorpro; "SystemColorProfileAssociations"
0x180007cad  call    cs:__imp_RtlGetPersistedStateLocation
0x180007cb3  test    eax, eax
0x180007cb5  jns     short loc_180007CC4
0x180007cb7  mov     ecx, eax; Status
0x180007cb9  call    cs:__imp_RtlNtStatusToDosError
0x180007cbf  jmp     loc_180007F66
0x180007cc4  lea     rdx, gszDisplay; "DISPLAY"
0x180007ccb  mov     rcx, rsi; lpString1
0x180007cce  call    cs:__imp_lstrcmpiW
0x180007cd4  test    eax, eax
0x180007cd6  jnz     short loc_180007CFB
0x180007cd8  lea     r8, a0000; "0000"
0x180007cdf  mov     rdx, rbx; unsigned __int64
0x180007ce2  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180007ce9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007cee  test    eax, eax
0x180007cf0  jns     loc_180007E76
0x180007cf6  jmp     loc_180007F66
0x180007cfb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007cff  inc     rbx
0x180007d02  cmp     [rsi+rbx*2], r13w
0x180007d07  jnz     short loc_180007CFF
0x180007d09  cmp     ebx, r14d
0x180007d0c  ja      loc_180007F66
0x180007d12  lea     ecx, [rbx+1]
0x180007d15  add     rcx, rcx; Size
0x180007d18  call    cs:__imp_malloc
0x180007d1e  mov     rdi, rax
0x180007d21  test    rax, rax
0x180007d24  jz      loc_180007F66
0x180007d2a  mov     [rsp+4C0h+cchDest], ebx; cchDest
0x180007d2e  mov     r9d, ebx; cchSrc
0x180007d31  mov     r8, rsi; lpSrcStr
0x180007d34  mov     [rsp+4C0h+lpDestStr], rax; lpDestStr
0x180007d39  mov     edx, 200h; dwMapFlags
0x180007d3e  mov     ecx, 7Fh; Locale
0x180007d43  call    cs:__imp_LCMapStringW
0x180007d49  test    eax, eax
0x180007d4b  jz      loc_180007F5D
0x180007d51  mov     ecx, ebx
0x180007d53  lea     rdx, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x180007d5a  mov     [rdi+rcx*2], r13w
0x180007d5f  mov     rcx, rdi; Str
0x180007d62  call    cs:__imp_wcsstr
0x180007d68  test    rax, rax
0x180007d6b  jz      loc_180007F5D
0x180007d71  mov     dl, 1
0x180007d73  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation> `wil::Feature<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::GetImpl(void)'::`2'::impl
0x180007d7a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180007d7f  lea     r8, [rsp+4C0h+var_470]; HKEY *
0x180007d84  xor     edx, edx; int
0x180007d86  mov     rcx, rsi; unsigned __int16 *
0x180007d89  call    ?OpenDisplayMux@@YAJPEBGHPEAPEAUHKEY__@@@Z; OpenDisplayMux(ushort const *,int,HKEY__ * *)
0x180007d8e  test    eax, eax
0x180007d90  jns     loc_180007F5D
0x180007d96  mov     edx, 5Ch ; '\'; Ch
0x180007d9b  mov     rcx, rsi; Str
0x180007d9e  call    cs:__imp_wcsrchr
0x180007da4  mov     ebx, 104h
0x180007da9  lea     r8, [rax+2]; unsigned __int16 *
0x180007dad  test    r8, r8
0x180007db0  jz      short loc_180007DC7
0x180007db2  mov     edx, ebx; unsigned __int64
0x180007db4  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180007dbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007dc0  mov     edx, eax
0x180007dc2  jmp     loc_180007E65
0x180007dc7  mov     r8, rbx
0x180007dca  lea     rax, [rbp+3C0h+var_250]
0x180007dd1  cmp     [rax], r13w
0x180007dd5  jz      short loc_180007DE1
0x180007dd7  add     rax, 2
0x180007ddb  sub     r8, 1
0x180007ddf  jnz     short loc_180007DD1
0x180007de1  mov     rax, r8
0x180007de4  mov     rcx, rbx
0x180007de7  neg     rax
0x180007dea  mov     rax, r8
0x180007ded  sbb     edx, edx
0x180007def  sub     rcx, r8
0x180007df2  not     edx
0x180007df4  and     edx, 80070057h
0x180007dfa  neg     rax
0x180007dfd  sbb     r9, r9
0x180007e00  and     r9, rcx
0x180007e03  test    r8, r8
0x180007e06  jz      short loc_180007E65
0x180007e08  mov     rdx, rbx
0x180007e0b  lea     r8, [rbp+3C0h+var_250]
0x180007e12  lea     rax, a0000; "0000"
0x180007e19  mov     rcx, r14
0x180007e1c  lea     r8, [r8+r9*2]
0x180007e20  sub     rdx, r9
0x180007e23  jz      short loc_180007E49
0x180007e25  test    rcx, rcx
0x180007e28  jz      short loc_180007E49
0x180007e2a  movzx   r9d, word ptr [rax]
0x180007e2e  test    r9w, r9w
0x180007e32  jz      short loc_180007E49
0x180007e34  mov     [r8], r9w
0x180007e38  add     rax, 2
0x180007e3c  add     r8, 2
0x180007e40  dec     rcx
0x180007e43  sub     rdx, 1
0x180007e47  jnz     short loc_180007E25
0x180007e49  test    rdx, rdx
0x180007e4c  lea     rcx, [r8-2]
0x180007e50  cmovnz  rcx, r8
0x180007e54  neg     rdx
0x180007e57  sbb     edx, edx
0x180007e59  not     edx
0x180007e5b  and     edx, 8007007Ah
0x180007e61  mov     [rcx], r13w
0x180007e65  test    edx, edx
0x180007e67  js      loc_180007F5D
0x180007e6d  mov     rcx, rdi; Block
0x180007e70  call    cs:__imp_free
0x180007e76  mov     rdx, rbx
0x180007e79  lea     rax, [rsp+4C0h+SubKey]
0x180007e7e  cmp     [rax], r13w
0x180007e82  jz      short loc_180007E8E
0x180007e84  add     rax, 2
0x180007e88  sub     rdx, 1
0x180007e8c  jnz     short loc_180007E7E
0x180007e8e  mov     rcx, rbx
0x180007e91  mov     rax, rdx
0x180007e94  sub     rcx, rdx
0x180007e97  neg     rax
0x180007e9a  sbb     r9, r9
0x180007e9d  and     r9, rcx
0x180007ea0  test    rdx, rdx
0x180007ea3  jz      loc_180007F66
0x180007ea9  mov     r8, rbx
0x180007eac  lea     rax, [rsp+4C0h+SubKey]
0x180007eb1  lea     rcx, StringValue; "\\"
0x180007eb8  lea     rax, [rax+r9*2]
0x180007ebc  sub     r8, r9
0x180007ebf  jz      short loc_180007EE2
0x180007ec1  test    r14, r14
0x180007ec4  jz      short loc_180007EE2
0x180007ec6  movzx   edx, word ptr [rcx]
0x180007ec9  test    dx, dx
0x180007ecc  jz      short loc_180007EE2
0x180007ece  mov     [rax], dx
0x180007ed1  add     rcx, 2
0x180007ed5  add     rax, 2
0x180007ed9  dec     r14
0x180007edc  sub     r8, 1
0x180007ee0  jnz     short loc_180007EC1
0x180007ee2  test    r8, r8
0x180007ee5  lea     rcx, [rax-2]
0x180007ee9  cmovnz  rcx, rax
0x180007eed  mov     [rcx], r13w
0x180007ef1  jz      short loc_180007F66
0x180007ef3  lea     r8, [rbp+3C0h+var_250]; unsigned __int16 *
0x180007efa  mov     rdx, rbx; unsigned __int64
0x180007efd  lea     rcx, [rsp+4C0h+SubKey]; unsigned __int16 *
0x180007f02  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f07  test    eax, eax
0x180007f09  js      short loc_180007F66
0x180007f0b  mov     [rsp+4C0h+lpdwDisposition], r13; lpdwDisposition
0x180007f10  lea     rcx, [rsp+4C0h+var_470]
0x180007f15  mov     [rsp+4C0h+phkResult], rcx; phkResult
0x180007f1a  lea     rdx, [rsp+4C0h+SubKey]; lpSubKey
0x180007f1f  mov     [rsp+4C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180007f24  neg     r15d
0x180007f27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007f2e  sbb     eax, eax
0x180007f30  xor     r9d, r9d; lpClass
0x180007f33  and     eax, 0FFFDFFFAh
0x180007f38  xor     r8d, r8d; Reserved
0x180007f3b  add     eax, 20007h
0x180007f40  mov     [rsp+4C0h+cchDest], eax; samDesired
0x180007f44  mov     dword ptr [rsp+4C0h+lpDestStr], r13d; dwOptions
0x180007f49  call    cs:__imp_RegCreateKeyExW
0x180007f4f  test    eax, eax
0x180007f51  jz      short loc_180007F66
0x180007f53  mov     ecx, eax; dwErrCode
0x180007f55  call    cs:__imp_SetLastError
0x180007f5b  jmp     short loc_180007F66
0x180007f5d  mov     rcx, rdi; Block
0x180007f60  call    cs:__imp_free
0x180007f66  mov     rcx, [rsp+4C0h+var_470]
0x180007f6b  mov     eax, r13d
0x180007f6e  test    rcx, rcx
0x180007f71  mov     [r12], rcx
0x180007f75  setnz   al
0x180007f78  mov     rcx, [rbp+3C0h+var_40]
0x180007f7f  xor     rcx, rsp; StackCookie
0x180007f82  call    __security_check_cookie
0x180007f87  mov     rbx, [rsp+4C0h+arg_10]
0x180007f8f  add     rsp, 490h
0x180007f96  pop     r15
0x180007f98  pop     r14
0x180007f9a  pop     r13
0x180007f9c  pop     r12
0x180007f9e  pop     rdi
0x180007f9f  pop     rsi
0x180007fa0  pop     rbp
0x180007fa1  retn
```
