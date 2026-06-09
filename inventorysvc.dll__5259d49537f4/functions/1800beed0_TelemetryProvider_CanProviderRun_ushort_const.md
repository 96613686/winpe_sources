# TelemetryProvider::CanProviderRun(ushort const *)

- ea: `0x1800beed0`
- end: `0x1800bf0be`
- name: `?CanProviderRun@TelemetryProvider@@SA_NPEBG@Z`
- size: `494`
- prototype: `bool __fastcall(LPCWSTR lpValue)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bfe9c`

## callees

- `0x180002bf0`
- `0x18000f698`
- `0x1800152d0`
- `0x180032394`
- `0x1800beed0`
- `0x1800bfedc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef40`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bef14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bef14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800bef36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800bef36`

## string_xrefs

- `0x1800bef50`: `GetSystemDirectoryW failed [%d]`
- `0x1800bf03e`: `%ls EOS via OneSettings. %hsCommercial so %hsrunning`

## pseudocode

```c
char __fastcall TelemetryProvider::CanProviderRun(unsigned __int16 *lpValue)
{
  char v2; // si
  UINT SystemDirectoryW; // eax
  unsigned __int64 v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  __int64 v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // rdx
  int v10; // eax
  bool v11; // cl
  bool v12; // bl
  const char *v13; // rdi
  const bool *v14; // rbx
  bool *v16; // [rsp+20h] [rbp-E0h]
  bool v17; // [rsp+40h] [rbp-C0h] BYREF
  bool v18; // [rsp+41h] [rbp-BFh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  SystemTimeAsFileTime = 0;
  v2 = 1;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v20 = (unsigned __int64)SystemTimeAsFileTime;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    LODWORD(v16) = GetLastError();
    v5 = 890;
LABEL_3:
    v6 = "GetSystemDirectoryW failed [%d]";
LABEL_4:
    v7 = 1;
LABEL_24:
    AslLogCallPrintf(v7, "TelemetryProvider::CanProviderRun", v5, v6, v16);
    return v2;
  }
  if ( SystemDirectoryW > 0x104 )
  {
    LODWORD(v16) = 111;
    v5 = 895;
    goto LABEL_3;
  }
  v8 = StringCchCatW(Buffer, v4, L"\\");
  if ( v8 < 0 )
  {
    LODWORD(v16) = v8;
    v6 = "StringCchPrintfW failed [%#x]";
    v5 = 902;
    goto LABEL_4;
  }
  v10 = StringCchCatW(Buffer, v9, lpValue);
  if ( v10 < 0 )
  {
    LODWORD(v16) = v10;
    v6 = "StringCchPrintfW failed [%#x]";
    v5 = 909;
    goto LABEL_4;
  }
  v17 = 0;
  v18 = 0;
  if ( !(unsigned int)TelemetryProvider::IsValidFromOneSettings(lpValue, Buffer, v20, &v17, &v18) )
  {
    v12 = v18;
    if ( v17 )
      goto LABEL_15;
    if ( !v18 )
      goto LABEL_22;
    if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(v11) )
LABEL_15:
      v2 = 0;
    if ( v12 )
    {
      v13 = (const char *)&word_1800D7582;
      v14 = (const bool *)&word_1800D7582;
      if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(v11) )
        v14 = "not ";
      if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial((bool)"not ") )
        v13 = "Not ";
      AslLogCallPrintf(
        3,
        "TelemetryProvider::CanProviderRun",
        925,
        "%ls EOS via OneSettings. %hsCommercial so %hsrunning",
        lpValue,
        v13,
        v14);
    }
LABEL_22:
    if ( v17 )
    {
      v16 = (bool *)lpValue;
      v6 = "TelemetryProvider binary:%ls is KillSwitched";
      v5 = 929;
      v7 = 3;
      goto LABEL_24;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800beed0  mov     [rsp-8+arg_8], rbx
0x1800beed5  mov     [rsp-8+arg_10], rsi
0x1800beeda  push    rbp
0x1800beedb  push    rdi
0x1800beedc  push    r14
0x1800beede  lea     rbp, [rsp-180h]
0x1800beee6  sub     rsp, 280h
0x1800beeed  mov     rax, cs:__security_cookie
0x1800beef4  xor     rax, rsp
0x1800beef7  mov     [rbp+190h+var_20], rax
0x1800beefe  mov     r14, rcx
0x1800bef01  mov     qword ptr [rsp+290h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800bef0a  lea     rcx, [rsp+290h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800bef0f  mov     esi, 1
0x1800bef14  call    cs:__imp_GetSystemTimeAsFileTime
0x1800bef1a  mov     eax, [rsp+290h+SystemTimeAsFileTime.dwHighDateTime]
0x1800bef1e  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x1800bef23  mov     dword ptr [rsp+290h+var_240+4], eax
0x1800bef27  mov     ebx, 104h
0x1800bef2c  mov     eax, [rsp+290h+SystemTimeAsFileTime.dwLowDateTime]
0x1800bef30  mov     edx, ebx; uSize
0x1800bef32  mov     dword ptr [rsp+290h+var_240], eax
0x1800bef36  call    cs:__imp_GetSystemDirectoryW
0x1800bef3c  test    eax, eax
0x1800bef3e  jnz     short loc_1800BEF5E
0x1800bef40  call    cs:__imp_GetLastError
0x1800bef46  mov     dword ptr [rsp+290h+var_270], eax
0x1800bef4a  mov     r8d, 37Ah
0x1800bef50  lea     r9, aGetsystemdirec; "GetSystemDirectoryW failed [%d]"
0x1800bef57  mov     ecx, esi
0x1800bef59  jmp     loc_1800BF088
0x1800bef5e  cmp     eax, ebx
0x1800bef60  jbe     short loc_1800BEF72
0x1800bef62  mov     dword ptr [rsp+290h+var_270], 6Fh ; 'o'
0x1800bef6a  mov     r8d, 37Fh
0x1800bef70  jmp     short loc_1800BEF50
0x1800bef72  lea     r8, SubBlock; "\\"
0x1800bef79  lea     rcx, [rsp+290h+Buffer]; unsigned __int16 *
0x1800bef7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bef83  test    eax, eax
0x1800bef85  jns     short loc_1800BEF9A
0x1800bef87  mov     dword ptr [rsp+290h+var_270], eax
0x1800bef8b  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x1800bef92  mov     r8d, 386h
0x1800bef98  jmp     short loc_1800BEF57
0x1800bef9a  mov     r8, r14; unsigned __int16 *
0x1800bef9d  lea     rcx, [rsp+290h+Buffer]; unsigned __int16 *
0x1800befa2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800befa7  test    eax, eax
0x1800befa9  jns     short loc_1800BEFBE
0x1800befab  mov     dword ptr [rsp+290h+var_270], eax
0x1800befaf  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x1800befb6  mov     r8d, 38Dh
0x1800befbc  jmp     short loc_1800BEF57
0x1800befbe  mov     r8, [rsp+290h+var_240]; unsigned __int64
0x1800befc3  lea     rax, [rsp+290h+var_24F]
0x1800befc8  lea     r9, [rsp+290h+var_250]; bool *
0x1800befcd  mov     [rsp+290h+var_270], rax; bool *
0x1800befd2  lea     rdx, [rsp+290h+Buffer]; unsigned __int16 *
0x1800befd7  mov     [rsp+290h+var_250], 0
0x1800befdc  mov     rcx, r14; lpValue
0x1800befdf  mov     [rsp+290h+var_24F], 0
0x1800befe4  call    ?IsValidFromOneSettings@TelemetryProvider@@CAJPEBG0_KAEA_N2@Z; TelemetryProvider::IsValidFromOneSettings(ushort const *,ushort const *,unsigned __int64,bool &,bool &)
0x1800befe9  test    eax, eax
0x1800befeb  jnz     loc_1800BF094
0x1800beff1  mov     bl, [rsp+290h+var_24F]
0x1800beff5  cmp     [rsp+290h+var_250], al
0x1800beff9  jnz     short loc_1800BF008
0x1800beffb  test    bl, bl
0x1800beffd  jz      short loc_1800BF06A
0x1800befff  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x1800bf004  test    al, al
0x1800bf006  jnz     short loc_1800BF00B
0x1800bf008  xor     sil, sil
0x1800bf00b  test    bl, bl
0x1800bf00d  jz      short loc_1800BF06A
0x1800bf00f  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x1800bf014  test    al, al
0x1800bf016  lea     rcx, aNot; "not "
0x1800bf01d  lea     rdi, word_1800D7582
0x1800bf024  mov     rbx, rdi
0x1800bf027  cmovz   rbx, rcx
0x1800bf02b  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x1800bf030  lea     rcx, aNot_0; "Not "
0x1800bf037  mov     [rsp+290h+var_260], rbx
0x1800bf03c  test    al, al
0x1800bf03e  lea     r9, aLsEosViaOneset; "%ls EOS via OneSettings. %hsCommercial "...
0x1800bf045  mov     r8d, 39Dh
0x1800bf04b  lea     rdx, aTelemetryprovi_5; "TelemetryProvider::CanProviderRun"
0x1800bf052  cmovz   rdi, rcx
0x1800bf056  mov     ecx, 3
0x1800bf05b  mov     [rsp+290h+var_268], rdi
0x1800bf060  mov     [rsp+290h+var_270], r14
0x1800bf065  call    AslLogCallPrintf
0x1800bf06a  cmp     [rsp+290h+var_250], 0
0x1800bf06f  jz      short loc_1800BF094
0x1800bf071  mov     [rsp+290h+var_270], r14
0x1800bf076  lea     r9, aTelemetryprovi_16; "TelemetryProvider binary:%ls is KillSwi"...
0x1800bf07d  mov     r8d, 3A1h
0x1800bf083  mov     ecx, 3
0x1800bf088  lea     rdx, aTelemetryprovi_5; "TelemetryProvider::CanProviderRun"
0x1800bf08f  call    AslLogCallPrintf
0x1800bf094  mov     al, sil
0x1800bf097  mov     rcx, [rbp+190h+var_20]
0x1800bf09e  xor     rcx, rsp; StackCookie
0x1800bf0a1  call    __security_check_cookie
0x1800bf0a6  lea     r11, [rsp+290h+var_10]
0x1800bf0ae  mov     rbx, [r11+28h]
0x1800bf0b2  mov     rsi, [r11+30h]
0x1800bf0b6  mov     rsp, r11
0x1800bf0b9  pop     r14
0x1800bf0bb  pop     rdi
0x1800bf0bc  pop     rbp
0x1800bf0bd  retn
```
