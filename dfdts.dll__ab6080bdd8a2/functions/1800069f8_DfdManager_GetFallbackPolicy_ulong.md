# DfdManager::GetFallbackPolicy(ulong)

- ea: `0x1800069f8`
- end: `0x180006b08`
- name: `?GetFallbackPolicy@DfdManager@@AEAAKK@Z`
- size: `272`
- prototype: `__int64 __fastcall(DfdManager *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006744`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x1800069f8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180006a43`
- `ADVAPI32!RegOpenKeyExW` at `0x180006a43`
- `ADVAPI32!RegCloseKey` at `0x180006afa`
- `ADVAPI32!RegCloseKey` at `0x180006afa`
- `ADVAPI32!RegQueryValueExW` at `0x180006a79`
- `ADVAPI32!RegQueryValueExW` at `0x180006a79`

## pseudocode

```c
__int64 __fastcall DfdManager::GetFallbackPolicy(DfdManager *this, unsigned int a2)
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v5 = HIDWORD(this);
  Data = 0;
  cbData = 4;
  Type = 4;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FallbackPolicy",
          0,
          0x20019u,
          &hKey)
    && !RegQueryValueExW(hKey, L"EnabledScenarioExecutionLevel", 0, &Type, (LPBYTE)&Data, &cbData) )
  {
    if ( Data == 1 )
    {
      a2 = 2;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
    }
    else
    {
      a2 = 12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, Data);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x1800069f8  mov     rax, rsp
0x1800069fb  mov     [rax+8], rcx
0x1800069ff  push    rbx
0x180006a00  sub     rsp, 30h
0x180006a04  mov     dword ptr [rax+10h], 0
0x180006a0b  mov     ebx, edx
0x180006a0d  mov     dword ptr [rax+8], 4
0x180006a14  mov     r9d, 20019h; samDesired
0x180006a1a  mov     dword ptr [rax+18h], 4
0x180006a21  xor     r8d, r8d; ulOptions
0x180006a24  mov     qword ptr [rax+20h], 0
0x180006a2c  lea     rax, [rax+20h]
0x180006a30  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180006a37  mov     [rsp+38h+phkResult], rax; phkResult
0x180006a3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006a43  call    cs:__imp_RegOpenKeyExW
0x180006a49  test    eax, eax
0x180006a4b  jnz     loc_180006AF0
0x180006a51  mov     rcx, [rsp+38h+hKey]; hKey
0x180006a56  lea     rax, [rsp+38h+cbData]
0x180006a5b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180006a60  lea     r9, [rsp+38h+Type]; lpType
0x180006a65  lea     rax, [rsp+38h+Data]
0x180006a6a  xor     r8d, r8d; lpReserved
0x180006a6d  lea     rdx, aEnabledscenari; "EnabledScenarioExecutionLevel"
0x180006a74  mov     [rsp+38h+phkResult], rax; lpData
0x180006a79  call    cs:__imp_RegQueryValueExW
0x180006a7f  test    eax, eax
0x180006a81  jnz     short loc_180006AF0
0x180006a83  mov     r9d, [rsp+38h+Data]
0x180006a88  cmp     r9d, 1
0x180006a8c  jnz     short loc_180006ABF
0x180006a8e  lea     ebx, [rax+2]
0x180006a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a98  lea     rax, WPP_GLOBAL_Control
0x180006a9f  cmp     rcx, rax
0x180006aa2  jz      short loc_180006AF0
0x180006aa4  test    byte ptr [rcx+1Ch], 4
0x180006aa8  jz      short loc_180006AF0
0x180006aaa  mov     rcx, [rcx+10h]
0x180006aae  lea     edx, [rbx+2Ah]
0x180006ab1  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006ab8  call    WPP_SF_
0x180006abd  jmp     short loc_180006AF0
0x180006abf  mov     ebx, 0Ch
0x180006ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006acb  lea     rax, WPP_GLOBAL_Control
0x180006ad2  cmp     rcx, rax
0x180006ad5  jz      short loc_180006AF0
0x180006ad7  test    byte ptr [rcx+1Ch], 1
0x180006adb  jz      short loc_180006AF0
0x180006add  mov     rcx, [rcx+10h]
0x180006ae1  lea     edx, [rbx+21h]
0x180006ae4  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006aeb  call    WPP_SF_d
0x180006af0  mov     rcx, [rsp+38h+hKey]; hKey
0x180006af5  test    rcx, rcx
0x180006af8  jz      short loc_180006B00
0x180006afa  call    cs:__imp_RegCloseKey
0x180006b00  mov     eax, ebx
0x180006b02  add     rsp, 30h
0x180006b06  pop     rbx
0x180006b07  retn
```
