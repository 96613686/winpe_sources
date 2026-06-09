# HevcCompressor::GetSettings(void)

- ea: `0x18008f028`
- end: `0x18008f5c9`
- name: `?GetSettings@HevcCompressor@@IEAAXXZ`
- size: `1441`
- prototype: `void __fastcall(HevcCompressor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180092eb0`

## callees

- `0x180003d40`
- `0x18008f028`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f138`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f17e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f1c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f20a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f24b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f291`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f2d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f31d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f36e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f3b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f3fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f440`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f486`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f4c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f138`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f17e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f1c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f20a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f24b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f291`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f2d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f31d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f36e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f3b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f3fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f440`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f486`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008f4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f4e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f4e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008f0f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008f0f6`

## string_xrefs

- `0x18008f3b2`: `MaxAvcEncoderThreadPoolWorkitems`
- `0x18008f0e8`: `Software\Policies\Microsoft\Windows NT\Terminal Services\HevcEncoding`
- `0x18008f551`: `HEVC compressor settings`

## pseudocode

```c
void __fastcall HevcCompressor::GetSettings(HevcCompressor *this)
{
  __int64 *v2; // rdi
  char *v3; // r8
  int (__fastcall ***v4)(_QWORD, GUID *, char *); // rcx
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char v9; // di
  char v10; // dl
  int v11; // [rsp+70h] [rbp+7h] BYREF
  int v12; // [rsp+74h] [rbp+Bh] BYREF
  int v13; // [rsp+78h] [rbp+Fh] BYREF
  int v14; // [rsp+7Ch] [rbp+13h] BYREF
  int v15; // [rsp+80h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+1Fh] BYREF
  const char *v17; // [rsp+90h] [rbp+27h] BYREF
  DWORD Type; // [rsp+D0h] [rbp+67h] BYREF
  int Data; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+E0h] [rbp+77h] BYREF
  int v21; // [rsp+E8h] [rbp+7Fh] BYREF

  *((_DWORD *)this + 48) = 800;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *(_QWORD *)((char *)this + 196) = 300000000;
  v2 = (__int64 *)((char *)this + 352);
  *((_WORD *)this + 104) = -1;
  v3 = (char *)this + 352;
  v4 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 42);
  hKey = 0;
  if ( (**v4)(v4, &IID_IRDPENCPlatformContext, v3) >= 0 )
  {
    v5 = *v2;
    Type = 0;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, DWORD *))(*(_QWORD *)v5 + 32LL))(
           v5,
           L"WVD::UseXVPColorConversion",
           &Type) >= 0 )
      *((_DWORD *)this + 39) = Type;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\HevcEncoding",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableColorConversion", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 38) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"UseXVPColorConversion", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 39) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableHighQuality", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 40) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"PeakBandwidthKbps", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 41) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableHevcHWEncode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 42) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableSoftwareMFTEncode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 50) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ForceSwCscForHwEncode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 43) = Data != 0;
    cbData = 4;
    v9 = 38;
    if ( !RegQueryValueExW(hKey, L"SetMaxQP", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v10 = 38;
      if ( (unsigned int)(Data - 1) <= 0x32 )
        v10 = Data;
      *((_BYTE *)this + 208) = v10;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SetMinQP", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      if ( (unsigned int)(Data - 1) <= 0x32 )
        v9 = Data;
      *((_BYTE *)this + 209) = v9;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxAvcEncoderThreadPoolWorkitems", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 44) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableChroma", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 45) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SaveFramesForTesting", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 47) = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"KeyFrameDistanceThreshold", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 48) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"KeyFrameResetTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 49) = Data;
    RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    Data = *((_DWORD *)this + 45);
    cbData = *((_DWORD *)this + 44);
    LOBYTE(Type) = *((_BYTE *)this + 208);
    v21 = *((_DWORD *)this + 43);
    v11 = *((_DWORD *)this + 42);
    v12 = *((_DWORD *)this + 41);
    v13 = *((_DWORD *)this + 40);
    v14 = *((_DWORD *)this + 39);
    v15 = *((_DWORD *)this + 38);
    v17 = "HEVC compressor settings";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)byte_1801A1C93,
      v7,
      v8,
      (__int64)&v17,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11,
      (__int64)&v21,
      (__int64)&Type,
      (__int64)&cbData,
      (__int64)&Data);
  }
}

```

## disassembly

```asm
0x18008f028  push    rbp
0x18008f02a  push    rbx
0x18008f02b  push    rsi
0x18008f02c  push    rdi
0x18008f02d  push    r14
0x18008f02f  lea     rbp, [rsp-37h]
0x18008f034  sub     rsp, 0A0h
0x18008f03b  xor     esi, esi
0x18008f03d  mov     dword ptr [rcx+0C0h], 320h
0x18008f047  mov     [rcx+98h], rsi
0x18008f04e  lea     rdx, IID_IRDPENCPlatformContext
0x18008f055  mov     [rcx+0A0h], rsi
0x18008f05c  mov     rbx, rcx
0x18008f05f  mov     [rcx+0A8h], rsi
0x18008f066  mov     [rcx+0B0h], rsi
0x18008f06d  mov     [rcx+0B8h], rsi
0x18008f074  mov     qword ptr [rcx+0C4h], 11E1A300h
0x18008f07f  lea     rdi, [rbx+160h]
0x18008f086  mov     word ptr [rcx+0D0h], 0FFFFh
0x18008f08f  mov     r8, rdi
0x18008f092  mov     rcx, [rcx+150h]
0x18008f099  mov     [rbp+57h+hKey], rsi
0x18008f09d  mov     rax, [rcx]
0x18008f0a0  mov     rax, [rax]
0x18008f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f0a8  test    eax, eax
0x18008f0aa  js      short loc_18008F0D6
0x18008f0ac  mov     rcx, [rdi]
0x18008f0af  lea     r8, [rbp+57h+Type]
0x18008f0b3  mov     [rbp+57h+Type], esi
0x18008f0b6  lea     rdx, aWvdUsexvpcolor; "WVD::UseXVPColorConversion"
0x18008f0bd  mov     rax, [rcx]
0x18008f0c0  mov     rax, [rax+20h]
0x18008f0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f0c9  test    eax, eax
0x18008f0cb  js      short loc_18008F0D6
0x18008f0cd  mov     eax, [rbp+57h+Type]
0x18008f0d0  mov     [rbx+9Ch], eax
0x18008f0d6  lea     rax, [rbp+57h+hKey]
0x18008f0da  mov     r9d, 20019h; samDesired
0x18008f0e0  xor     r8d, r8d; ulOptions
0x18008f0e3  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18008f0e8  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18008f0ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008f0f6  call    cs:__imp_RegOpenKeyExW
0x18008f0fc  mov     r14d, 4
0x18008f102  test    eax, eax
0x18008f104  jnz     loc_18008F4EA
0x18008f10a  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f10e  lea     rax, [rbp+57h+cbData]
0x18008f112  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f117  lea     r9, [rbp+57h+Type]; lpType
0x18008f11b  lea     rax, [rbp+57h+Data]
0x18008f11f  mov     [rbp+57h+Data], esi
0x18008f122  xor     r8d, r8d; lpReserved
0x18008f125  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f12a  lea     rdx, aDisablecolorco; "DisableColorConversion"
0x18008f131  mov     [rbp+57h+Type], esi
0x18008f134  mov     [rbp+57h+cbData], r14d
0x18008f138  call    cs:__imp_RegQueryValueExW
0x18008f13e  test    eax, eax
0x18008f140  jnz     short loc_18008F156
0x18008f142  cmp     [rbp+57h+Type], r14d
0x18008f146  jnz     short loc_18008F156
0x18008f148  cmp     [rbp+57h+Data], esi
0x18008f14b  mov     eax, esi
0x18008f14d  setnz   al
0x18008f150  mov     [rbx+98h], eax
0x18008f156  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f15a  lea     rax, [rbp+57h+cbData]
0x18008f15e  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f163  lea     r9, [rbp+57h+Type]; lpType
0x18008f167  lea     rax, [rbp+57h+Data]
0x18008f16b  mov     [rbp+57h+cbData], r14d
0x18008f16f  xor     r8d, r8d; lpReserved
0x18008f172  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f177  lea     rdx, aUsexvpcolorcon; "UseXVPColorConversion"
0x18008f17e  call    cs:__imp_RegQueryValueExW
0x18008f184  test    eax, eax
0x18008f186  jnz     short loc_18008F19C
0x18008f188  cmp     [rbp+57h+Type], r14d
0x18008f18c  jnz     short loc_18008F19C
0x18008f18e  cmp     [rbp+57h+Data], esi
0x18008f191  mov     eax, esi
0x18008f193  setnz   al
0x18008f196  mov     [rbx+9Ch], eax
0x18008f19c  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f1a0  lea     rax, [rbp+57h+cbData]
0x18008f1a4  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f1a9  lea     r9, [rbp+57h+Type]; lpType
0x18008f1ad  lea     rax, [rbp+57h+Data]
0x18008f1b1  mov     [rbp+57h+cbData], r14d
0x18008f1b5  xor     r8d, r8d; lpReserved
0x18008f1b8  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f1bd  lea     rdx, aEnablehighqual; "EnableHighQuality"
0x18008f1c4  call    cs:__imp_RegQueryValueExW
0x18008f1ca  test    eax, eax
0x18008f1cc  jnz     short loc_18008F1E2
0x18008f1ce  cmp     [rbp+57h+Type], r14d
0x18008f1d2  jnz     short loc_18008F1E2
0x18008f1d4  cmp     [rbp+57h+Data], esi
0x18008f1d7  mov     eax, esi
0x18008f1d9  setnz   al
0x18008f1dc  mov     [rbx+0A0h], eax
0x18008f1e2  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f1e6  lea     rax, [rbp+57h+cbData]
0x18008f1ea  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f1ef  lea     r9, [rbp+57h+Type]; lpType
0x18008f1f3  lea     rax, [rbp+57h+Data]
0x18008f1f7  mov     [rbp+57h+cbData], r14d
0x18008f1fb  xor     r8d, r8d; lpReserved
0x18008f1fe  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f203  lea     rdx, aPeakbandwidthk; "PeakBandwidthKbps"
0x18008f20a  call    cs:__imp_RegQueryValueExW
0x18008f210  test    eax, eax
0x18008f212  jnz     short loc_18008F223
0x18008f214  cmp     [rbp+57h+Type], r14d
0x18008f218  jnz     short loc_18008F223
0x18008f21a  mov     eax, [rbp+57h+Data]
0x18008f21d  mov     [rbx+0A4h], eax
0x18008f223  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f227  lea     rax, [rbp+57h+cbData]
0x18008f22b  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f230  lea     r9, [rbp+57h+Type]; lpType
0x18008f234  lea     rax, [rbp+57h+Data]
0x18008f238  mov     [rbp+57h+cbData], r14d
0x18008f23c  xor     r8d, r8d; lpReserved
0x18008f23f  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f244  lea     rdx, aEnablehevchwen; "EnableHevcHWEncode"
0x18008f24b  call    cs:__imp_RegQueryValueExW
0x18008f251  test    eax, eax
0x18008f253  jnz     short loc_18008F269
0x18008f255  cmp     [rbp+57h+Type], r14d
0x18008f259  jnz     short loc_18008F269
0x18008f25b  cmp     [rbp+57h+Data], esi
0x18008f25e  mov     eax, esi
0x18008f260  setnz   al
0x18008f263  mov     [rbx+0A8h], eax
0x18008f269  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f26d  lea     rax, [rbp+57h+cbData]
0x18008f271  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f276  lea     r9, [rbp+57h+Type]; lpType
0x18008f27a  lea     rax, [rbp+57h+Data]
0x18008f27e  mov     [rbp+57h+cbData], r14d
0x18008f282  xor     r8d, r8d; lpReserved
0x18008f285  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f28a  lea     rdx, aDisablesoftwar; "DisableSoftwareMFTEncode"
0x18008f291  call    cs:__imp_RegQueryValueExW
0x18008f297  test    eax, eax
0x18008f299  jnz     short loc_18008F2AF
0x18008f29b  cmp     [rbp+57h+Type], r14d
0x18008f29f  jnz     short loc_18008F2AF
0x18008f2a1  cmp     [rbp+57h+Data], esi
0x18008f2a4  mov     eax, esi
0x18008f2a6  setnz   al
0x18008f2a9  mov     [rbx+0C8h], eax
0x18008f2af  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f2b3  lea     rax, [rbp+57h+cbData]
0x18008f2b7  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f2bc  lea     r9, [rbp+57h+Type]; lpType
0x18008f2c0  lea     rax, [rbp+57h+Data]
0x18008f2c4  mov     [rbp+57h+cbData], r14d
0x18008f2c8  xor     r8d, r8d; lpReserved
0x18008f2cb  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f2d0  lea     rdx, aForceswcscforh; "ForceSwCscForHwEncode"
0x18008f2d7  call    cs:__imp_RegQueryValueExW
0x18008f2dd  test    eax, eax
0x18008f2df  jnz     short loc_18008F2F5
0x18008f2e1  cmp     [rbp+57h+Type], r14d
0x18008f2e5  jnz     short loc_18008F2F5
0x18008f2e7  cmp     [rbp+57h+Data], esi
0x18008f2ea  mov     eax, esi
0x18008f2ec  setnz   al
0x18008f2ef  mov     [rbx+0ACh], eax
0x18008f2f5  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f2f9  lea     rax, [rbp+57h+cbData]
0x18008f2fd  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f302  lea     r9, [rbp+57h+Type]; lpType
0x18008f306  lea     rax, [rbp+57h+Data]
0x18008f30a  mov     [rbp+57h+cbData], r14d
0x18008f30e  xor     r8d, r8d; lpReserved
0x18008f311  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f316  lea     rdx, aSetmaxqp; "SetMaxQP"
0x18008f31d  call    cs:__imp_RegQueryValueExW
0x18008f323  mov     edi, 26h ; '&'
0x18008f328  test    eax, eax
0x18008f32a  jnz     short loc_18008F346
0x18008f32c  cmp     [rbp+57h+Type], r14d
0x18008f330  jnz     short loc_18008F346
0x18008f332  mov     ecx, [rbp+57h+Data]
0x18008f335  mov     edx, edi
0x18008f337  lea     eax, [rcx-1]
0x18008f33a  cmp     eax, 32h ; '2'
0x18008f33d  cmovbe  edx, ecx
0x18008f340  mov     [rbx+0D0h], dl
0x18008f346  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f34a  lea     rax, [rbp+57h+cbData]
0x18008f34e  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f353  lea     r9, [rbp+57h+Type]; lpType
0x18008f357  lea     rax, [rbp+57h+Data]
0x18008f35b  mov     [rbp+57h+cbData], r14d
0x18008f35f  xor     r8d, r8d; lpReserved
0x18008f362  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f367  lea     rdx, aSetminqp; "SetMinQP"
0x18008f36e  call    cs:__imp_RegQueryValueExW
0x18008f374  test    eax, eax
0x18008f376  jnz     short loc_18008F391
0x18008f378  cmp     [rbp+57h+Type], r14d
0x18008f37c  jnz     short loc_18008F391
0x18008f37e  mov     ecx, [rbp+57h+Data]
0x18008f381  lea     eax, [rcx-1]
0x18008f384  cmp     eax, 32h ; '2'
0x18008f387  cmovbe  edi, ecx
0x18008f38a  mov     [rbx+0D1h], dil
0x18008f391  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f395  lea     rax, [rbp+57h+cbData]
0x18008f399  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f39e  lea     r9, [rbp+57h+Type]; lpType
0x18008f3a2  lea     rax, [rbp+57h+Data]
0x18008f3a6  mov     [rbp+57h+cbData], r14d
0x18008f3aa  xor     r8d, r8d; lpReserved
0x18008f3ad  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f3b2  lea     rdx, aMaxavcencodert; "MaxAvcEncoderThreadPoolWorkitems"
0x18008f3b9  call    cs:__imp_RegQueryValueExW
0x18008f3bf  test    eax, eax
0x18008f3c1  jnz     short loc_18008F3D2
0x18008f3c3  cmp     [rbp+57h+Type], r14d
0x18008f3c7  jnz     short loc_18008F3D2
0x18008f3c9  mov     eax, [rbp+57h+Data]
0x18008f3cc  mov     [rbx+0B0h], eax
0x18008f3d2  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f3d6  lea     rax, [rbp+57h+cbData]
0x18008f3da  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f3df  lea     r9, [rbp+57h+Type]; lpType
0x18008f3e3  lea     rax, [rbp+57h+Data]
0x18008f3e7  mov     [rbp+57h+cbData], r14d
0x18008f3eb  xor     r8d, r8d; lpReserved
0x18008f3ee  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f3f3  lea     rdx, aDisablechroma; "DisableChroma"
0x18008f3fa  call    cs:__imp_RegQueryValueExW
0x18008f400  test    eax, eax
0x18008f402  jnz     short loc_18008F418
0x18008f404  cmp     [rbp+57h+Type], r14d
0x18008f408  jnz     short loc_18008F418
0x18008f40a  cmp     [rbp+57h+Data], esi
0x18008f40d  mov     eax, esi
0x18008f40f  setnz   al
0x18008f412  mov     [rbx+0B4h], eax
0x18008f418  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f41c  lea     rax, [rbp+57h+cbData]
0x18008f420  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f425  lea     r9, [rbp+57h+Type]; lpType
0x18008f429  lea     rax, [rbp+57h+Data]
0x18008f42d  mov     [rbp+57h+cbData], r14d
0x18008f431  xor     r8d, r8d; lpReserved
0x18008f434  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f439  lea     rdx, aSaveframesfort; "SaveFramesForTesting"
0x18008f440  call    cs:__imp_RegQueryValueExW
0x18008f446  test    eax, eax
0x18008f448  jnz     short loc_18008F45E
0x18008f44a  cmp     [rbp+57h+Type], r14d
0x18008f44e  jnz     short loc_18008F45E
0x18008f450  cmp     [rbp+57h+Data], esi
0x18008f453  mov     eax, esi
0x18008f455  setnz   al
0x18008f458  mov     [rbx+0BCh], eax
0x18008f45e  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f462  lea     rax, [rbp+57h+cbData]
0x18008f466  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f46b  lea     r9, [rbp+57h+Type]; lpType
0x18008f46f  lea     rax, [rbp+57h+Data]
0x18008f473  mov     [rbp+57h+cbData], r14d
0x18008f477  xor     r8d, r8d; lpReserved
0x18008f47a  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f47f  lea     rdx, aKeyframedistan; "KeyFrameDistanceThreshold"
0x18008f486  call    cs:__imp_RegQueryValueExW
0x18008f48c  test    eax, eax
0x18008f48e  jnz     short loc_18008F49F
0x18008f490  cmp     [rbp+57h+Type], r14d
0x18008f494  jnz     short loc_18008F49F
0x18008f496  mov     eax, [rbp+57h+Data]
0x18008f499  mov     [rbx+0C0h], eax
0x18008f49f  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f4a3  lea     rax, [rbp+57h+cbData]
0x18008f4a7  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18008f4ac  lea     r9, [rbp+57h+Type]; lpType
0x18008f4b0  lea     rax, [rbp+57h+Data]
0x18008f4b4  mov     [rbp+57h+cbData], r14d
0x18008f4b8  xor     r8d, r8d; lpReserved
0x18008f4bb  mov     [rsp+0C0h+phkResult], rax; lpData
0x18008f4c0  lea     rdx, aKeyframeresett; "KeyFrameResetTimeout"
0x18008f4c7  call    cs:__imp_RegQueryValueExW
0x18008f4cd  test    eax, eax
0x18008f4cf  jnz     short loc_18008F4E0
0x18008f4d1  cmp     [rbp+57h+Type], r14d
0x18008f4d5  jnz     short loc_18008F4E0
0x18008f4d7  mov     eax, [rbp+57h+Data]
0x18008f4da  mov     [rbx+0C4h], eax
0x18008f4e0  mov     rcx, [rbp+57h+hKey]; hKey
0x18008f4e4  call    cs:__imp_RegCloseKey
  ... truncated ...
```
