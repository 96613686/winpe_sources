# TelemetryProvider::CanProviderRun(ushort const *)

- ea: `0x1400039d0`
- end: `0x140003bae`
- name: `?CanProviderRun@TelemetryProvider@@SA_NPEBG@Z`
- size: `478`
- prototype: `char __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003610`

## callees

- `0x140002d00`
- `0x1400039d0`
- `0x140003bb4`
- `0x140003cd8`
- `0x140007074`
- `0x1400115f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003a0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003a0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140003a2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140003a2c`

## string_xrefs

- `0x140003a46`: `GetSystemDirectoryW failed [%d]`
- `0x140003b38`: `%ls EOS via OneSettings. %hsCommercial so %hsrunning`

## pseudocode

```c
char __fastcall TelemetryProvider::CanProviderRun(const unsigned __int16 *a1)
{
  char v1; // si
  UINT SystemDirectoryW; // eax
  unsigned __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  unsigned __int64 v8; // rdx
  int v9; // eax
  const unsigned __int16 *v10; // rcx
  bool v11; // cl
  bool v12; // bl
  __int64 *v13; // rdi
  __int64 *v14; // rbx
  bool *v16; // [rsp+20h] [rbp-E0h]
  bool v17; // [rsp+40h] [rbp-C0h] BYREF
  bool v18; // [rsp+41h] [rbp-BFh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  SystemTimeAsFileTime = 0;
  v1 = 1;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v20 = (unsigned __int64)SystemTimeAsFileTime;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    LODWORD(v16) = GetLastError();
    v4 = 890;
LABEL_3:
    v5 = "GetSystemDirectoryW failed [%d]";
LABEL_4:
    v6 = 1;
LABEL_24:
    AslLogCallPrintf(v6, "TelemetryProvider::CanProviderRun", v4, v5, v16);
    return v1;
  }
  if ( SystemDirectoryW > 0x104 )
  {
    LODWORD(v16) = 111;
    v4 = 895;
    goto LABEL_3;
  }
  v7 = StringCchCatW(Buffer, v3, L"\\");
  if ( v7 < 0 )
  {
    LODWORD(v16) = v7;
    v5 = "StringCchPrintfW failed [%#x]";
    v4 = 902;
    goto LABEL_4;
  }
  v9 = StringCchCatW(Buffer, v8, L"DeviceCensus.exe");
  if ( v9 < 0 )
  {
    LODWORD(v16) = v9;
    v5 = "StringCchPrintfW failed [%#x]";
    v4 = 909;
    goto LABEL_4;
  }
  v17 = 0;
  v18 = 0;
  if ( !(unsigned int)TelemetryProvider::IsValidFromOneSettings(v10, Buffer, v20, &v17, &v18) )
  {
    v12 = v18;
    if ( v17 )
      goto LABEL_15;
    if ( !v18 )
      goto LABEL_22;
    if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(v11) )
LABEL_15:
      v1 = 0;
    if ( v12 )
    {
      v13 = &qword_1400157F8;
      v14 = &qword_1400157F8;
      if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(v11) )
        v14 = (__int64 *)"not ";
      if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial((bool)"not ") )
        v13 = (__int64 *)"Not ";
      AslLogCallPrintf(
        3,
        "TelemetryProvider::CanProviderRun",
        925,
        "%ls EOS via OneSettings. %hsCommercial so %hsrunning",
        L"DeviceCensus.exe",
        v13,
        v14);
    }
LABEL_22:
    if ( v17 )
    {
      v16 = (bool *)L"DeviceCensus.exe";
      v5 = "TelemetryProvider binary:%ls is KillSwitched";
      v4 = 929;
      v6 = 3;
      goto LABEL_24;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400039d0  push    rbp
0x1400039d2  push    rbx
0x1400039d3  push    rsi
0x1400039d4  push    rdi
0x1400039d5  push    r12
0x1400039d7  lea     rbp, [rsp-180h]
0x1400039df  sub     rsp, 280h
0x1400039e6  mov     rax, cs:__security_cookie
0x1400039ed  xor     rax, rsp
0x1400039f0  mov     [rbp+1A0h+var_30], rax
0x1400039f7  lea     rcx, [rsp+2A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400039fc  mov     qword ptr [rsp+2A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140003a05  mov     esi, 1
0x140003a0a  call    cs:__imp_GetSystemTimeAsFileTime
0x140003a10  mov     eax, [rsp+2A0h+SystemTimeAsFileTime.dwHighDateTime]
0x140003a14  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x140003a19  mov     dword ptr [rsp+2A0h+var_250+4], eax
0x140003a1d  mov     ebx, 104h
0x140003a22  mov     eax, [rsp+2A0h+SystemTimeAsFileTime.dwLowDateTime]
0x140003a26  mov     edx, ebx; uSize
0x140003a28  mov     dword ptr [rsp+2A0h+var_250], eax
0x140003a2c  call    cs:__imp_GetSystemDirectoryW
0x140003a32  test    eax, eax
0x140003a34  jnz     short loc_140003A54
0x140003a36  call    cs:__imp_GetLastError
0x140003a3c  mov     dword ptr [rsp+2A0h+var_280], eax
0x140003a40  mov     r8d, 37Ah
0x140003a46  lea     r9, aGetsystemdirec; "GetSystemDirectoryW failed [%d]"
0x140003a4d  mov     ecx, esi
0x140003a4f  jmp     loc_140003B82
0x140003a54  cmp     eax, ebx
0x140003a56  jbe     short loc_140003A68
0x140003a58  mov     dword ptr [rsp+2A0h+var_280], 6Fh ; 'o'
0x140003a60  mov     r8d, 37Fh
0x140003a66  jmp     short loc_140003A46
0x140003a68  lea     r8, Source; "\\"
0x140003a6f  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x140003a74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003a79  test    eax, eax
0x140003a7b  jns     short loc_140003A90
0x140003a7d  mov     dword ptr [rsp+2A0h+var_280], eax
0x140003a81  lea     r9, aStringcchprint; "StringCchPrintfW failed [%#x]"
0x140003a88  mov     r8d, 386h
0x140003a8e  jmp     short loc_140003A4D
0x140003a90  lea     r12, aDevicecensusEx_0; "DeviceCensus.exe"
0x140003a97  mov     r8, r12; unsigned __int16 *
0x140003a9a  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x140003a9f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003aa4  test    eax, eax
0x140003aa6  jns     short loc_140003ABB
0x140003aa8  mov     dword ptr [rsp+2A0h+var_280], eax
0x140003aac  lea     r9, aStringcchprint; "StringCchPrintfW failed [%#x]"
0x140003ab3  mov     r8d, 38Dh
0x140003ab9  jmp     short loc_140003A4D
0x140003abb  mov     r8, [rsp+2A0h+var_250]; unsigned __int64
0x140003ac0  lea     rax, [rsp+2A0h+var_25F]
0x140003ac5  lea     r9, [rsp+2A0h+var_260]; bool *
0x140003aca  mov     [rsp+2A0h+var_280], rax; bool *
0x140003acf  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x140003ad4  mov     [rsp+2A0h+var_260], 0
0x140003ad9  mov     [rsp+2A0h+var_25F], 0
0x140003ade  call    ?IsValidFromOneSettings@TelemetryProvider@@CAJPEBG0_KAEA_N2@Z; TelemetryProvider::IsValidFromOneSettings(ushort const *,ushort const *,unsigned __int64,bool &,bool &)
0x140003ae3  test    eax, eax
0x140003ae5  jnz     loc_140003B8E
0x140003aeb  mov     bl, [rsp+2A0h+var_25F]
0x140003aef  cmp     [rsp+2A0h+var_260], al
0x140003af3  jnz     short loc_140003B02
0x140003af5  test    bl, bl
0x140003af7  jz      short loc_140003B64
0x140003af9  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x140003afe  test    al, al
0x140003b00  jnz     short loc_140003B05
0x140003b02  xor     sil, sil
0x140003b05  test    bl, bl
0x140003b07  jz      short loc_140003B64
0x140003b09  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x140003b0e  test    al, al
0x140003b10  lea     rcx, aNot; "not "
0x140003b17  lea     rdi, qword_1400157F8
0x140003b1e  mov     rbx, rdi
0x140003b21  cmovz   rbx, rcx
0x140003b25  call    ?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)
0x140003b2a  lea     rcx, aNot_0; "Not "
0x140003b31  mov     [rsp+2A0h+var_270], rbx
0x140003b36  test    al, al
0x140003b38  lea     r9, aLsEosViaOneset; "%ls EOS via OneSettings. %hsCommercial "...
0x140003b3f  mov     r8d, 39Dh
0x140003b45  lea     rdx, aTelemetryprovi; "TelemetryProvider::CanProviderRun"
0x140003b4c  cmovz   rdi, rcx
0x140003b50  mov     ecx, 3
0x140003b55  mov     [rsp+2A0h+var_278], rdi
0x140003b5a  mov     [rsp+2A0h+var_280], r12
0x140003b5f  call    AslLogCallPrintf
0x140003b64  cmp     [rsp+2A0h+var_260], 0
0x140003b69  jz      short loc_140003B8E
0x140003b6b  mov     [rsp+2A0h+var_280], r12
0x140003b70  lea     r9, aTelemetryprovi_1; "TelemetryProvider binary:%ls is KillSwi"...
0x140003b77  mov     r8d, 3A1h
0x140003b7d  mov     ecx, 3
0x140003b82  lea     rdx, aTelemetryprovi; "TelemetryProvider::CanProviderRun"
0x140003b89  call    AslLogCallPrintf
0x140003b8e  mov     al, sil
0x140003b91  mov     rcx, [rbp+1A0h+var_30]
0x140003b98  xor     rcx, rsp; StackCookie
0x140003b9b  call    __security_check_cookie
0x140003ba0  add     rsp, 280h
0x140003ba7  pop     r12
0x140003ba9  pop     rdi
0x140003baa  pop     rsi
0x140003bab  pop     rbx
0x140003bac  pop     rbp
0x140003bad  retn
```
