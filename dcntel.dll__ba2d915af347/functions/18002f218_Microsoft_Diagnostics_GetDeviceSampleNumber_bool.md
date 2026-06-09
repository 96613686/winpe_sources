# Microsoft::Diagnostics::GetDeviceSampleNumber(bool)

- ea: `0x18002f218`
- end: `0x18002f3de`
- name: `?GetDeviceSampleNumber@Diagnostics@Microsoft@@YAN_N@Z`
- size: `454`
- prototype: `double __fastcall(Microsoft::Diagnostics *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fd30`

## callees

- `0x18002f218`
- `0x180030554`

## import_xrefs

- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18002f288`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18002f29e`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18002f288`
- `msvcp_win!?_Random_device@std@@YAIXZ` at `0x18002f29e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f2d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f2d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f38b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f2d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f38b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f36b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f36b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f326`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f326`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f26a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f26a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall Microsoft::Diagnostics::GetDeviceSampleNumber(Microsoft::Diagnostics *this)
{
  __int64 v1; // rax
  HKEY v2; // rdi
  DWORD LastError; // ebx
  int v4; // eax
  int v5; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  int pdwTypea; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int Data; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  Data = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Reliability Analysis\\RAC",
    L"RacSampleNumber",
    0x18u,
    0,
    &Data,
    &pcbData);
  if ( (unsigned int)(Data - 1) > 0x5F5E0FF )
  {
    hKey = 0;
    v1 = 100000000LL * std::_Random_device();
    if ( (unsigned int)v1 <= 0x5A915FF )
    {
      do
        v1 = 100000000LL * std::_Random_device();
      while ( (unsigned int)v1 < 0x5A91600 );
    }
    Data = HIDWORD(v1) + 1;
    v2 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    hKey = 0;
    v4 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Reliability Analysis\\RAC",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"OneCore\\Private\\Base\\inc\\SamplingNumber.hpp",
        (const char *)(unsigned int)v4,
        pdwType);
    v5 = RegSetValueExW(hKey, L"RacSampleNumber", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"OneCore\\Private\\Base\\inc\\SamplingNumber.hpp",
        (const char *)(unsigned int)v5,
        pdwTypea);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (double)Data / 100000000.0 * 100.0;
}

```

## disassembly

```asm
0x18002f218  mov     byte ptr [rsp-18h+Data], cl
0x18002f21c  push    rbp
0x18002f21d  push    rbx
0x18002f21e  push    rdi
0x18002f21f  mov     rbp, rsp
0x18002f222  sub     rsp, 50h
0x18002f226  mov     [rbp+Data], 0
0x18002f22d  mov     [rbp+arg_8], 4
0x18002f234  lea     rax, [rbp+arg_8]
0x18002f238  mov     [rsp+50h+pcbData], rax; pcbData
0x18002f23d  lea     rax, [rbp+Data]
0x18002f241  mov     [rsp+50h+pvData], rax; pvData
0x18002f246  mov     [rsp+50h+pdwType], 0; pdwType
0x18002f24f  mov     r9d, 18h; dwFlags
0x18002f255  lea     r8, aRacsamplenumbe; "RacSampleNumber"
0x18002f25c  lea     rdx, aSoftwareMicros_59; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x18002f263  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002f26a  call    cs:__imp_RegGetValueW
0x18002f270  mov     eax, [rbp+Data]
0x18002f273  dec     eax
0x18002f275  cmp     eax, 5F5E0FFh
0x18002f27a  jbe     loc_18002F391
0x18002f280  mov     [rbp+hKey], 0
0x18002f288  call    cs:__imp_?_Random_device@std@@YAIXZ; std::_Random_device(void)
0x18002f28e  mov     ecx, eax
0x18002f290  imul    rax, rcx, 5F5E100h
0x18002f297  cmp     eax, 5A915FFh
0x18002f29c  ja      short loc_18002F2B4
0x18002f29e  call    cs:__imp_?_Random_device@std@@YAIXZ; std::_Random_device(void)
0x18002f2a4  mov     ecx, eax
0x18002f2a6  imul    rax, rcx, 5F5E100h
0x18002f2ad  cmp     eax, 5A91600h
0x18002f2b2  jb      short loc_18002F29E
0x18002f2b4  shr     rax, 20h
0x18002f2b8  inc     eax
0x18002f2ba  mov     [rbp+Data], eax
0x18002f2bd  mov     rdi, [rbp+hKey]
0x18002f2c1  test    rdi, rdi
0x18002f2c4  jz      short loc_18002F2DF
0x18002f2c6  call    cs:__imp_GetLastError
0x18002f2cc  mov     ebx, eax
0x18002f2ce  mov     rcx, rdi; hKey
0x18002f2d1  call    cs:__imp_RegCloseKey
0x18002f2d7  mov     ecx, ebx; dwErrCode
0x18002f2d9  call    cs:__imp_SetLastError
0x18002f2df  mov     [rbp+hKey], 0
0x18002f2e7  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x18002f2f0  lea     rax, [rbp+hKey]
0x18002f2f4  mov     [rsp+50h+phkResult], rax; phkResult
0x18002f2f9  mov     [rsp+50h+pcbData], 0; lpSecurityAttributes
0x18002f302  mov     dword ptr [rsp+50h+pvData], 20006h; samDesired
0x18002f30a  mov     dword ptr [rsp+50h+pdwType], 0; int
0x18002f312  xor     r9d, r9d; lpClass
0x18002f315  xor     r8d, r8d; Reserved
0x18002f318  lea     rdx, aSoftwareMicros_59; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x18002f31f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f326  call    cs:__imp_RegCreateKeyExW
0x18002f32c  mov     ebx, 80070000h
0x18002f331  test    eax, eax
0x18002f333  jle     short loc_18002F33A
0x18002f335  movzx   eax, ax
0x18002f338  or      eax, ebx
0x18002f33a  mov     rcx, [rbp+18h]; this
0x18002f33e  test    eax, eax
0x18002f340  js      loc_18002F3C9
0x18002f346  mov     dword ptr [rsp+50h+pvData], 4; cbData
0x18002f34e  lea     rax, [rbp+Data]
0x18002f352  mov     [rsp+50h+pdwType], rax; int
0x18002f357  mov     r9d, 4; dwType
0x18002f35d  xor     r8d, r8d; Reserved
0x18002f360  lea     rdx, aRacsamplenumbe; "RacSampleNumber"
0x18002f367  mov     rcx, [rbp+hKey]; hKey
0x18002f36b  call    cs:__imp_RegSetValueExW
0x18002f371  test    eax, eax
0x18002f373  jle     short loc_18002F37A
0x18002f375  movzx   eax, ax
0x18002f378  or      eax, ebx
0x18002f37a  mov     rcx, [rbp+18h]; this
0x18002f37e  test    eax, eax
0x18002f380  js      short loc_18002F3B4
0x18002f382  mov     rcx, [rbp+hKey]; hKey
0x18002f386  test    rcx, rcx
0x18002f389  jz      short loc_18002F391
0x18002f38b  call    cs:__imp_RegCloseKey
0x18002f391  mov     eax, [rbp+Data]
0x18002f394  xorps   xmm0, xmm0
0x18002f397  cvtsi2sd xmm0, rax
0x18002f39c  divsd   xmm0, cs:__real@4197d78400000000
0x18002f3a4  mulsd   xmm0, cs:__real@4059000000000000
0x18002f3ac  add     rsp, 50h
0x18002f3b0  pop     rdi
0x18002f3b1  pop     rbx
0x18002f3b2  pop     rbp
0x18002f3b3  retn
0x18002f3b4  mov     r9d, eax; char *
0x18002f3b7  lea     r8, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\SamplingNu"...
0x18002f3be  mov     edx, 4Ch ; 'L'; void *
0x18002f3c3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002f3c9  mov     r9d, eax; char *
0x18002f3cc  lea     r8, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\SamplingNu"...
0x18002f3d3  mov     edx, 44h ; 'D'; void *
0x18002f3d8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
