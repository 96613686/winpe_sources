# CMpegAudioCodec::InitClass(int,_GUID const *)

- ea: `0x180026330`
- end: `0x18002641d`
- name: `?InitClass@CMpegAudioCodec@@SAXHPEBU_GUID@@@Z`
- size: `237`
- prototype: `void __fastcall(int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180026330`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180026411`
- `KERNEL32!InitializeCriticalSection` at `0x1800263f9`
- `ADVAPI32!RegQueryValueExW` at `0x1800263ae`
- `ADVAPI32!RegQueryValueExW` at `0x1800263ae`
- `ADVAPI32!RegOpenKeyExW` at `0x180026370`
- `ADVAPI32!RegOpenKeyExW` at `0x180026370`
- `ADVAPI32!RegCloseKey` at `0x1800263c9`
- `ADVAPI32!RegCloseKey` at `0x1800263c9`

## pseudocode

```c
void __fastcall CMpegAudioCodec::InitClass(int a1, const struct _GUID *a2)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  if ( a1 )
  {
    hKey = 0;
    Data = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Multimedia\\ActiveMovie Filters\\MPEG Decoder",
            0,
            1u,
            &hKey) )
    {
      Type = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"NoSSE2", 0, &Type, (LPBYTE)&Data, &cbData) )
        Data = 0;
      RegCloseKey(hKey);
    }
    g_bMMX = 0;
    g_bSSE2 = Data == 0;
    InitializeCriticalSection(&stru_1801A1FB8);
  }
  else
  {
    DeleteCriticalSection(&stru_1801A1FB8);
  }
}

```

## disassembly

```asm
0x180026330  push    rbp
0x180026332  mov     rbp, rsp
0x180026335  sub     rsp, 40h
0x180026339  test    ecx, ecx
0x18002633b  jz      loc_180026405
0x180026341  lea     rax, [rbp+hKey]
0x180026345  mov     [rbp+hKey], 0
0x18002634d  mov     r9d, 1; samDesired
0x180026353  mov     [rsp+40h+phkResult], rax; phkResult
0x180026358  xor     r8d, r8d; ulOptions
0x18002635b  mov     [rbp+Data], 0
0x180026362  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Multimedia\\Active"...
0x180026369  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180026370  call    cs:__imp_RegOpenKeyExW
0x180026377  nop     dword ptr [rax+rax+00h]
0x18002637c  test    eax, eax
0x18002637e  jnz     short loc_1800263D5
0x180026380  mov     rcx, [rbp+hKey]; hKey
0x180026384  lea     r9, [rbp+Type]; lpType
0x180026388  mov     [rbp+Type], eax
0x18002638b  lea     rdx, aNosse2; "NoSSE2"
0x180026392  lea     rax, [rbp+cbData]
0x180026396  mov     [rbp+cbData], 4
0x18002639d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800263a2  xor     r8d, r8d; lpReserved
0x1800263a5  lea     rax, [rbp+Data]
0x1800263a9  mov     [rsp+40h+phkResult], rax; lpData
0x1800263ae  call    cs:__imp_RegQueryValueExW
0x1800263b5  nop     dword ptr [rax+rax+00h]
0x1800263ba  test    eax, eax
0x1800263bc  jz      short loc_1800263C5
0x1800263be  mov     [rbp+Data], 0
0x1800263c5  mov     rcx, [rbp+hKey]; hKey
0x1800263c9  call    cs:__imp_RegCloseKey
0x1800263d0  nop     dword ptr [rax+rax+00h]
0x1800263d5  xor     eax, eax
0x1800263d7  mov     cs:?g_bMMX@@3HA, 0; int g_bMMX
0x1800263e1  cmp     [rbp+Data], eax
0x1800263e4  lea     rcx, stru_1801A1FB8
0x1800263eb  setz    al
0x1800263ee  mov     cs:?g_bSSE2@@3HA, eax; int g_bSSE2
0x1800263f4  add     rsp, 40h
0x1800263f8  pop     rbp
0x1800263f9  jmp     cs:__imp_InitializeCriticalSection
0x180026405  lea     rcx, stru_1801A1FB8
0x18002640c  add     rsp, 40h
0x180026410  pop     rbp
0x180026411  jmp     cs:__imp_DeleteCriticalSection
```
