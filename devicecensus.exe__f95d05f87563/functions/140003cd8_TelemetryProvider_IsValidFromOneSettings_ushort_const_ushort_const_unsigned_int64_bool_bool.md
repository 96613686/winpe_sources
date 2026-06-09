# TelemetryProvider::IsValidFromOneSettings(ushort const *,ushort const *,unsigned __int64,bool &,bool &)

- ea: `0x140003cd8`
- end: `0x14000417b`
- name: `?IsValidFromOneSettings@TelemetryProvider@@CAJPEBG0_KAEA_N2@Z`
- size: `1187`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, bool *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400039d0`

## callees

- `0x14000233f`
- `0x1400024f0`
- `0x140003cd8`
- `0x140004184`
- `0x140004210`
- `0x140007074`
- `0x140007184`
- `0x1400115f0`

## import_xrefs

- `msvcrt!wcsstr` at `0x140004001`
- `msvcrt!wcsstr` at `0x140004001`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003dae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000414c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003dae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000414c`
- `msvcrt!_wtoi64` at `0x1400040b8`
- `msvcrt!_wtoi64` at `0x1400040b8`
- `msvcrt!wcstok_s` at `0x140003f4f`
- `msvcrt!wcstok_s` at `0x14000401a`
- `msvcrt!wcstok_s` at `0x140003f4f`
- `msvcrt!wcstok_s` at `0x14000401a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003d92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003e1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003d92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003e1f`

## string_xrefs

- `0x140004090`: `StringCchCopyW failed [%#x]`
- `0x1400040a2`: `StringCchCopyW failed [%#x]`
- `0x140003ec7`: `AslFileGetVersionForPath failed [%#x]`
- `0x140003d79`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderEos`
- `0x140003e0e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderEos`

## pseudocode

```c
__int64 __fastcall TelemetryProvider::IsValidFromOneSettings(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        bool *a4,
        bool *a5)
{
  bool *v5; // rsi
  unsigned __int64 v8; // r14
  void *v9; // r12
  __int64 v10; // r8
  signed int ValueW; // ebx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  int v14; // ebx
  int v15; // eax
  __int64 v16; // r9
  int VersionForPath; // eax
  int v18; // eax
  wchar_t *v19; // rax
  unsigned __int8 v20; // di
  __int64 v21; // rsi
  __int64 v22; // r15
  __int64 v23; // rcx
  wchar_t *v24; // r8
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  wchar_t v27; // ax
  wchar_t *v28; // r14
  wchar_t *v29; // rcx
  wchar_t *v30; // rdx
  wchar_t *v31; // rcx
  const char *v32; // r9
  __int64 v33; // r8
  unsigned __int64 v34; // rdx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-BCh] BYREF
  int v41; // [rsp+48h] [rbp-B8h] BYREF
  int v42; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-B0h] BYREF
  bool *v44; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h]
  wchar_t Str[8]; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  wchar_t SubStr[32]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String[32]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a5;
  *a4 = 0;
  v45 = a3;
  v44 = a5;
  *a5 = 0;
  v8 = a3;
  v9 = operator new[](0x80u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
  {
    v10 = 970;
LABEL_3:
    LODWORD(pdwType) = -2147024882;
    ValueW = -2147024882;
    AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", v10, "new failed [%#x]", pdwType);
    goto LABEL_59;
  }
  pcbData = 128;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\ProviderEos",
             L"DeviceCensus.exe",
             2u,
             0,
             v9,
             &pcbData);
  if ( ValueW == 234 )
  {
    v12 = pcbData >> 1;
    operator delete[](v9);
    v13 = 2 * v12;
    if ( !is_mul_ok(v12, 2u) )
      v13 = -1;
    v9 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v9 )
    {
      v10 = 984;
      goto LABEL_3;
    }
    pcbData = 2 * v12;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\ProviderEos",
               L"DeviceCensus.exe",
               2u,
               0,
               v9,
               &pcbData);
  }
  if ( ValueW == 2 )
  {
    ValueW = 1;
    goto LABEL_59;
  }
  if ( ValueW )
  {
    AslLogCallPrintf(
      1,
      "TelemetryProvider::IsValidFromOneSettings",
      1001,
      "OneSettingsQuery::GetSetting failed [%d]",
      ValueW);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_59;
  }
  v14 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  if ( TelemetryProvider::UseOneSettingsPpe() )
  {
    v15 = 21341;
    v16 = 10;
  }
  else
  {
    VersionForPath = AslFileGetVersionForPath(&v40, &v41, &v42, a2);
    if ( (VersionForPath & 0xC0000000) == 0xC0000000 )
    {
      LODWORD(pdwType) = VersionForPath;
      ValueW = VersionForPath | 0x10000000;
      AslLogCallPrintf(
        1,
        "TelemetryProvider::IsValidFromOneSettings",
        1019,
        "AslFileGetVersionForPath failed [%#x]",
        pdwType);
      goto LABEL_59;
    }
    v16 = v40;
    v14 = v41;
    v15 = v42;
  }
  LODWORD(pvData) = v15;
  v47 = 0;
  LODWORD(pdwType) = v14;
  *(_OWORD *)Str = 0;
  v18 = StringCchPrintfW(Str, 0xAu, L"%02d%01d%05d", v16, pdwType, pvData);
  ValueW = v18;
  if ( v18 < 0 )
  {
    LODWORD(pdwTypea) = v18;
    AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", 1028, "StringCchPrintfW failed [%#x]", pdwTypea);
    goto LABEL_59;
  }
  Context = 0;
  memset_0(String, 0, sizeof(String));
  v19 = wcstok_s((wchar_t *)v9, L";", &Context);
  v20 = 1;
  if ( !v19 )
    goto LABEL_41;
  v21 = 32;
  v22 = 2147483646;
  while ( 1 )
  {
    v23 = 2147483646;
    v24 = SubStr;
    v25 = 32;
    do
    {
      if ( !v23 )
        break;
      if ( !*v19 )
        break;
      *v24++ = *v19++;
      --v23;
      --v25;
    }
    while ( v25 );
    v26 = v24 - 1;
    ValueW = v25 == 0 ? 0x8007007A : 0;
    if ( v25 )
      v26 = v24;
    *v26 = 0;
    if ( !v25 )
    {
      v32 = "StringCchCopyW failed [%#x]";
      v33 = 1047;
LABEL_58:
      LODWORD(pdwTypea) = ValueW;
      AslLogCallPrintf(1, "TelemetryProvider::IsValidFromOneSettings", v33, v32, pdwTypea);
      goto LABEL_59;
    }
    v27 = SubStr[0];
    v28 = 0;
    if ( SubStr[0] )
    {
      v29 = SubStr;
      while ( 1 )
      {
        if ( v27 == 42 )
          goto LABEL_36;
        if ( v27 == 58 )
          break;
LABEL_37:
        v27 = *++v29;
        if ( !*v29 )
          goto LABEL_38;
      }
      v28 = v29 + 1;
LABEL_36:
      *v29 = 0;
      if ( v28 )
        goto LABEL_38;
      goto LABEL_37;
    }
LABEL_38:
    if ( wcsstr(Str, SubStr) )
      break;
    v19 = wcstok_s(0, L";", &Context);
    if ( !v19 )
      goto LABEL_40;
  }
  v30 = String;
  do
  {
    if ( !v22 )
      break;
    if ( !*v28 )
      break;
    *v30++ = *v28++;
    --v22;
    --v21;
  }
  while ( v21 );
  v31 = v30 - 1;
  ValueW = v21 == 0 ? 0x8007007A : 0;
  if ( v21 )
    v31 = v30;
  *v31 = 0;
  if ( !v21 )
  {
    v32 = "StringCchCopyW failed [%#x]";
    v33 = 1083;
    goto LABEL_58;
  }
LABEL_40:
  v8 = v45;
  v5 = v44;
LABEL_41:
  if ( !String[0] )
  {
    ValueW = 1;
    goto LABEL_59;
  }
  v34 = _wtoi64(String);
  if ( v34 > 0x1F7E33BE0D39C00LL )
  {
    ValueW = -2147418113;
    v32 = "OneSettings EoL match found but invalid expiration date [%#x]";
    v33 = 1100;
    goto LABEL_58;
  }
  *a4 = v34 == 0;
  if ( !v34 || v34 >= v8 )
    v20 = 0;
  *v5 = v20;
  AslLogCallPrintf(
    3,
    "TelemetryProvider::IsValidFromOneSettings",
    1111,
    "OneSettings match was found:%I64u. KillSwitch:%d EoL:%d",
    v34,
    *a4,
    v20);
LABEL_59:
  operator delete[](v9);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x140003cd8  mov     [rsp-8+arg_0], rbx
0x140003cdd  push    rbp
0x140003cde  push    rsi
0x140003cdf  push    rdi
0x140003ce0  push    r12
0x140003ce2  push    r13
0x140003ce4  push    r14
0x140003ce6  push    r15
0x140003ce8  lea     rbp, [rsp-10h]
0x140003ced  sub     rsp, 110h
0x140003cf4  mov     rax, cs:__security_cookie
0x140003cfb  xor     rax, rsp
0x140003cfe  mov     [rbp+40h+var_40], rax
0x140003d02  mov     rsi, [rbp+40h+arg_20]
0x140003d06  xor     r15d, r15d
0x140003d09  mov     rdi, rdx
0x140003d0c  mov     [r9], r15b
0x140003d0f  mov     ebx, 80h
0x140003d14  mov     [rsp+140h+var_E0], r8
0x140003d19  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003d20  mov     [rsp+140h+var_E8], rsi
0x140003d25  mov     ecx, ebx; unsigned __int64
0x140003d27  mov     [rsi], r15b
0x140003d2a  mov     r13, r9
0x140003d2d  mov     r14, r8
0x140003d30  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140003d35  mov     r12, rax
0x140003d38  test    rax, rax
0x140003d3b  jnz     short loc_140003D5F
0x140003d3d  mov     r8d, 3CAh
0x140003d43  mov     ecx, 8007000Eh
0x140003d48  lea     r9, aNewFailedX; "new failed [%#x]"
0x140003d4f  mov     dword ptr [rsp+140h+pdwType], ecx
0x140003d53  mov     ebx, ecx
0x140003d55  mov     ecx, 1
0x140003d5a  jmp     loc_14000413D
0x140003d5f  lea     rax, [rsp+140h+var_100]
0x140003d64  mov     [rsp+140h+var_100], ebx
0x140003d68  mov     [rsp+140h+pcbData], rax; pcbData
0x140003d6d  lea     r8, aDevicecensusEx_0; "DeviceCensus.exe"
0x140003d74  mov     [rsp+140h+pvData], r12; pvData
0x140003d79  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140003d80  mov     r9d, 2; dwFlags
0x140003d86  mov     [rsp+140h+pdwType], r15; pdwType
0x140003d8b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003d92  call    cs:__imp_RegGetValueW
0x140003d98  mov     ebx, eax
0x140003d9a  cmp     eax, 0EAh
0x140003d9f  jnz     loc_140003E27
0x140003da5  mov     ebx, [rsp+140h+var_100]
0x140003da9  mov     rcx, r12
0x140003dac  shr     ebx, 1
0x140003dae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003db4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140003dbb  mov     eax, 2
0x140003dc0  mul     rbx
0x140003dc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003dca  cmovb   rax, rcx
0x140003dce  mov     rcx, rax; unsigned __int64
0x140003dd1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140003dd6  mov     r12, rax
0x140003dd9  test    rax, rax
0x140003ddc  jnz     short loc_140003DE9
0x140003dde  mov     r8d, 3D8h
0x140003de4  jmp     loc_140003D43
0x140003de9  lea     eax, [rbx+rbx]
0x140003dec  mov     r9d, 2; dwFlags
0x140003df2  mov     [rsp+140h+var_100], eax
0x140003df6  lea     r8, aDevicecensusEx_0; "DeviceCensus.exe"
0x140003dfd  lea     rax, [rsp+140h+var_100]
0x140003e02  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003e09  mov     [rsp+140h+pcbData], rax; pcbData
0x140003e0e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140003e15  mov     [rsp+140h+pvData], r12; pvData
0x140003e1a  mov     [rsp+140h+pdwType], r15; pdwType
0x140003e1f  call    cs:__imp_RegGetValueW
0x140003e25  mov     ebx, eax
0x140003e27  cmp     ebx, 2
0x140003e2a  jnz     short loc_140003E36
0x140003e2c  mov     ebx, 1
0x140003e31  jmp     loc_140004149
0x140003e36  test    ebx, ebx
0x140003e38  jz      short loc_140003E72
0x140003e3a  lea     r9, aOnesettingsque; "OneSettingsQuery::GetSetting failed [%d"...
0x140003e41  mov     dword ptr [rsp+140h+pdwType], ebx
0x140003e45  mov     r8d, 3E9h
0x140003e4b  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::IsValidFromOneSettin"...
0x140003e52  mov     ecx, 1
0x140003e57  call    AslLogCallPrintf
0x140003e5c  test    ebx, ebx
0x140003e5e  jle     loc_140004149
0x140003e64  movzx   ebx, bx
0x140003e67  or      ebx, 80070000h
0x140003e6d  jmp     loc_140004149
0x140003e72  mov     ebx, r15d
0x140003e75  mov     [rsp+140h+var_FC], r15d
0x140003e7a  mov     [rsp+140h+var_F8], ebx
0x140003e7e  mov     [rsp+140h+var_F4], r15d
0x140003e83  call    ?UseOneSettingsPpe@TelemetryProvider@@CA_NXZ; TelemetryProvider::UseOneSettingsPpe(void)
0x140003e88  test    al, al
0x140003e8a  jz      short loc_140003E99
0x140003e8c  mov     eax, 535Dh
0x140003e91  mov     r9d, 0Ah
0x140003e97  jmp     short loc_140003EE6
0x140003e99  mov     r9, rdi
0x140003e9c  lea     r8, [rsp+140h+var_F4]
0x140003ea1  lea     rdx, [rsp+140h+var_F8]
0x140003ea6  lea     rcx, [rsp+140h+var_FC]
0x140003eab  call    AslFileGetVersionForPath
0x140003eb0  mov     edx, 0C0000000h
0x140003eb5  mov     ecx, eax
0x140003eb7  and     ecx, edx
0x140003eb9  cmp     ecx, edx
0x140003ebb  jnz     short loc_140003ED9
0x140003ebd  mov     ebx, eax
0x140003ebf  mov     dword ptr [rsp+140h+pdwType], eax
0x140003ec3  bts     ebx, 1Ch
0x140003ec7  lea     r9, aAslfilegetvers; "AslFileGetVersionForPath failed [%#x]"
0x140003ece  mov     r8d, 3FBh
0x140003ed4  jmp     loc_140003D55
0x140003ed9  mov     r9d, [rsp+140h+var_FC]
0x140003ede  mov     ebx, [rsp+140h+var_F8]
0x140003ee2  mov     eax, [rsp+140h+var_F4]
0x140003ee6  xor     ecx, ecx
0x140003ee8  mov     dword ptr [rsp+140h+pvData], eax
0x140003eec  xorps   xmm0, xmm0
0x140003eef  mov     [rsp+140h+var_C8], ecx
0x140003ef3  lea     r8, a02d01d05d; "%02d%01d%05d"
0x140003efa  mov     dword ptr [rsp+140h+pdwType], ebx
0x140003efe  movups  xmmword ptr [rsp+140h+Str], xmm0
0x140003f03  lea     edx, [rcx+0Ah]; unsigned __int64
0x140003f06  lea     rcx, [rsp+140h+Str]; unsigned __int16 *
0x140003f0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003f10  mov     ebx, eax
0x140003f12  test    eax, eax
0x140003f14  jns     short loc_140003F2C
0x140003f16  mov     dword ptr [rsp+140h+pdwType], eax
0x140003f1a  lea     r9, aStringcchprint; "StringCchPrintfW failed [%#x]"
0x140003f21  mov     r8d, 404h
0x140003f27  jmp     loc_140003D55
0x140003f2c  xor     edx, edx; Val
0x140003f2e  mov     [rsp+140h+Context], r15
0x140003f33  lea     rcx, [rbp+40h+String]; void *
0x140003f37  lea     r8d, [rdx+40h]; Size
0x140003f3b  call    memset_0
0x140003f40  lea     r8, [rsp+140h+Context]; Context
0x140003f45  mov     rcx, r12; String
0x140003f48  lea     rdx, Delimiter; ";"
0x140003f4f  call    cs:__imp_wcstok_s
0x140003f55  mov     edi, 1
0x140003f5a  test    rax, rax
0x140003f5d  jz      loc_140004039
0x140003f63  lea     esi, [rdi+1Fh]
0x140003f66  mov     r15d, 7FFFFFFEh
0x140003f6c  xor     r10d, r10d
0x140003f6f  mov     rcx, r15
0x140003f72  lea     r8, [rbp+40h+SubStr]
0x140003f76  mov     rdx, rsi
0x140003f79  test    rcx, rcx
0x140003f7c  jz      short loc_140003F9C
0x140003f7e  movzx   r9d, word ptr [rax]
0x140003f82  test    r9w, r9w
0x140003f86  jz      short loc_140003F9C
0x140003f88  mov     [r8], r9w
0x140003f8c  add     rax, 2
0x140003f90  add     r8, 2
0x140003f94  sub     rcx, rdi
0x140003f97  sub     rdx, rdi
0x140003f9a  jnz     short loc_140003F79
0x140003f9c  mov     rax, rdx
0x140003f9f  lea     rcx, [r8-2]
0x140003fa3  neg     rax
0x140003fa6  sbb     ebx, ebx
0x140003fa8  not     ebx
0x140003faa  and     ebx, 8007007Ah
0x140003fb0  test    rdx, rdx
0x140003fb3  cmovnz  rcx, r8
0x140003fb7  mov     [rcx], r10w
0x140003fbb  jz      loc_1400040A2
0x140003fc1  movzx   eax, [rbp+40h+SubStr]
0x140003fc5  mov     r14, r10
0x140003fc8  test    ax, ax
0x140003fcb  jz      short loc_140003FF8
0x140003fcd  lea     rcx, [rbp+40h+SubStr]
0x140003fd1  cmp     ax, 2Ah ; '*'
0x140003fd5  jz      short loc_140003FE1
0x140003fd7  cmp     ax, 3Ah ; ':'
0x140003fdb  jnz     short loc_140003FEC
0x140003fdd  lea     r14, [rcx+2]
0x140003fe1  mov     eax, r10d
0x140003fe4  mov     [rcx], ax
0x140003fe7  test    r14, r14
0x140003fea  jnz     short loc_140003FF8
0x140003fec  add     rcx, 2
0x140003ff0  movzx   eax, word ptr [rcx]
0x140003ff3  test    ax, ax
0x140003ff6  jnz     short loc_140003FD1
0x140003ff8  lea     rdx, [rbp+40h+SubStr]; SubStr
0x140003ffc  lea     rcx, [rsp+140h+Str]; Str
0x140004001  call    cs:__imp_wcsstr
0x140004007  xor     ecx, ecx; String
0x140004009  test    rax, rax
0x14000400c  jnz     short loc_140004047
0x14000400e  lea     r8, [rsp+140h+Context]; Context
0x140004013  lea     rdx, Delimiter; ";"
0x14000401a  call    cs:__imp_wcstok_s
0x140004020  xor     r10d, r10d
0x140004023  test    rax, rax
0x140004026  jnz     loc_140003F6F
0x14000402c  xor     r15d, r15d
0x14000402f  mov     r14, [rsp+140h+var_E0]
0x140004034  mov     rsi, [rsp+140h+var_E8]
0x140004039  cmp     [rbp+40h+String], r15w
0x14000403e  jnz     short loc_1400040B4
0x140004040  mov     ebx, edi
0x140004042  jmp     loc_140004149
0x140004047  lea     rdx, [rbp+40h+String]
0x14000404b  test    r15, r15
0x14000404e  jz      short loc_14000406C
0x140004050  movzx   eax, word ptr [r14]
0x140004054  test    ax, ax
0x140004057  jz      short loc_14000406C
0x140004059  mov     [rdx], ax
0x14000405c  add     r14, 2
0x140004060  add     rdx, 2
0x140004064  sub     r15, rdi
0x140004067  sub     rsi, rdi
0x14000406a  jnz     short loc_14000404B
0x14000406c  mov     rax, rsi
0x14000406f  lea     rcx, [rdx-2]
0x140004073  neg     rax
0x140004076  sbb     ebx, ebx
0x140004078  xor     r15d, r15d
0x14000407b  not     ebx
0x14000407d  and     ebx, 8007007Ah
0x140004083  test    rsi, rsi
0x140004086  cmovnz  rcx, rdx
0x14000408a  mov     [rcx], r15w
0x14000408e  jnz     short loc_14000402F
0x140004090  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x140004097  mov     r8d, 43Bh
0x14000409d  jmp     loc_140004137
0x1400040a2  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x1400040a9  mov     r8d, 417h
0x1400040af  jmp     loc_140004137
0x1400040b4  lea     rcx, [rbp+40h+String]; String
0x1400040b8  call    cs:__imp__wtoi64
0x1400040be  mov     rdx, rax
0x1400040c1  mov     rax, 1F7E33BE0D39C00h
0x1400040cb  cmp     rdx, rax
0x1400040ce  ja      short loc_140004125
0x1400040d0  test    rdx, rdx
0x1400040d3  setz    cl
0x1400040d6  mov     [r13+0], cl
0x1400040da  test    rdx, rdx
0x1400040dd  jz      short loc_1400040E4
0x1400040df  cmp     rdx, r14
0x1400040e2  jb      short loc_1400040E7
0x1400040e4  mov     dil, r15b
0x1400040e7  mov     ecx, r15d
0x1400040ea  mov     [rsi], dil
0x1400040ed  cmp     [r13+0], r15b
0x1400040f1  lea     r9, aOnesettingsMat; "OneSettings match was found:%I64u. Kill"...
0x1400040f8  movzx   eax, dil
0x1400040fc  mov     r8d, 457h
0x140004102  setnz   cl
0x140004105  mov     dword ptr [rsp+140h+pcbData], eax
0x140004109  mov     dword ptr [rsp+140h+pvData], ecx
0x14000410d  mov     ecx, 3
0x140004112  mov     [rsp+140h+pdwType], rdx
0x140004117  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::IsValidFromOneSettin"...
0x14000411e  call    AslLogCallPrintf
0x140004123  jmp     short loc_140004149
0x140004125  mov     ebx, 8000FFFFh
0x14000412a  lea     r9, aOnesettingsEol; "OneSettings EoL match found but invalid"...
0x140004131  mov     r8d, 44Ch
0x140004137  mov     dword ptr [rsp+140h+pdwType], ebx
0x14000413b  mov     ecx, edi
0x14000413d  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::IsValidFromOneSettin"...
0x140004144  call    AslLogCallPrintf
0x140004149  mov     rcx, r12
0x14000414c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140004152  mov     eax, ebx
0x140004154  mov     rcx, [rbp+40h+var_40]
0x140004158  xor     rcx, rsp; StackCookie
0x14000415b  call    __security_check_cookie
0x140004160  mov     rbx, [rsp+140h+arg_0]
0x140004168  add     rsp, 110h
0x14000416f  pop     r15
0x140004171  pop     r14
0x140004173  pop     r13
0x140004175  pop     r12
0x140004177  pop     rdi
0x140004178  pop     rsi
0x140004179  pop     rbp
0x14000417a  retn
```
