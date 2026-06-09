# TestModeCheck

- ea: `0x18001ab4c`
- end: `0x18001ad40`
- name: `TestModeCheck`
- size: `500`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e2ec`
- `0x180010b60`
- `0x1800168b0`
- `0x180028ab4`
- `0x1800718b4`
- `0x180072dec`

## callees

- `0x18001ab4c`
- `0x18001b1dc`
- `0x18001b2a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001ab96`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ab96`
- `ADVAPI32!RegCloseKey` at `0x18001ad22`
- `ADVAPI32!RegCloseKey` at `0x18001ad22`
- `ADVAPI32!RegGetValueW` at `0x18001ac16`
- `ADVAPI32!RegGetValueW` at `0x18001ac16`

## pseudocode

```c
__int64 __fastcall TestModeCheck(LPCWSTR lpValue)
{
  unsigned int v2; // r14d
  LSTATUS ValueW; // eax
  int v4; // r8d
  _QWORD *v5; // rcx
  int v6; // edx
  PVOID *v7; // rcx
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  int pvData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+38h] BYREF

  pdwType = 0;
  pvData = 0;
  hkey = 0;
  pcbData = 4;
  v2 = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TermServLicensing", 0, 0xF003Fu, &hkey);
  if ( ValueW )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v6 = 50;
LABEL_5:
      WPP_SF_SSD(v5[2], v6, v4, (unsigned int)L"TestModeCheck", (__int64)lpValue, ValueW);
    }
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 0x10u, &pdwType, &pvData, &pcbData);
    if ( ValueW )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v6 = 51;
        goto LABEL_5;
      }
    }
    else
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          L"TestModeCheck");
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( pdwType == 4 && pvData == 1 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 )
          WPP_SF_SSd(
            v7[2],
            (unsigned int)(pvData + 52),
            &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
            L"TestModeCheck");
        v2 = 1;
      }
      else if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x1000) != 0 )
      {
        WPP_SF_SSd(v7[2], 54, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, L"TestModeCheck");
      }
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v2;
}

```

## disassembly

```asm
0x18001ab4c  mov     [rsp-18h+arg_0], rsi
0x18001ab51  push    rbp
0x18001ab52  push    rdi
0x18001ab53  push    r14
0x18001ab55  mov     rbp, rsp
0x18001ab58  sub     rsp, 50h
0x18001ab5c  and     [rbp+pdwType], 0
0x18001ab60  lea     rax, [rbp+hkey]
0x18001ab64  and     [rbp+arg_8], 0
0x18001ab68  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\TermServLicensing"
0x18001ab6f  and     [rbp+hkey], 0
0x18001ab74  mov     rsi, rcx
0x18001ab77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ab7e  mov     [rsp+50h+phkResult], rax; phkResult
0x18001ab83  mov     r9d, 0F003Fh; samDesired
0x18001ab89  mov     [rbp+arg_18], 4
0x18001ab90  xor     r8d, r8d; ulOptions
0x18001ab93  xor     r14d, r14d
0x18001ab96  call    cs:__imp_RegOpenKeyExW
0x18001ab9d  nop     dword ptr [rax+rax+00h]
0x18001aba2  test    eax, eax
0x18001aba4  jz      short loc_18001ABEC
0x18001aba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abad  lea     rdi, WPP_GLOBAL_Control
0x18001abb4  cmp     rcx, rdi
0x18001abb7  jz      loc_18001AD19
0x18001abbd  test    dword ptr [rcx+1Ch], 1000h
0x18001abc4  jz      loc_18001AD19
0x18001abca  lea     edx, [r14+32h]
0x18001abce  mov     rcx, [rcx+10h]
0x18001abd2  lea     r9, aTestmodecheck; "TestModeCheck"
0x18001abd9  mov     dword ptr [rsp+50h+pvData], eax
0x18001abdd  mov     [rsp+50h+phkResult], rsi
0x18001abe2  call    WPP_SF_SSD
0x18001abe7  jmp     loc_18001AD19
0x18001abec  mov     rcx, [rbp+hkey]; hkey
0x18001abf0  lea     rax, [rbp+arg_18]
0x18001abf4  mov     [rsp+50h+pcbData], rax; pcbData
0x18001abf9  mov     r9d, 10h; dwFlags
0x18001abff  lea     rax, [rbp+arg_8]
0x18001ac03  mov     r8, rsi; lpValue
0x18001ac06  mov     [rsp+50h+pvData], rax; pvData
0x18001ac0b  xor     edx, edx; lpSubKey
0x18001ac0d  lea     rax, [rbp+pdwType]
0x18001ac11  mov     [rsp+50h+phkResult], rax; pdwType
0x18001ac16  call    cs:__imp_RegGetValueW
0x18001ac1d  nop     dword ptr [rax+rax+00h]
0x18001ac22  test    eax, eax
0x18001ac24  jz      short loc_18001AC54
0x18001ac26  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac2d  lea     rdi, WPP_GLOBAL_Control
0x18001ac34  cmp     rcx, rdi
0x18001ac37  jz      loc_18001AD19
0x18001ac3d  test    dword ptr [rcx+1Ch], 1000h
0x18001ac44  jz      loc_18001AD19
0x18001ac4a  mov     edx, 33h ; '3'
0x18001ac4f  jmp     loc_18001ABCE
0x18001ac54  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac5b  lea     rdi, WPP_GLOBAL_Control
0x18001ac62  cmp     rcx, rdi
0x18001ac65  jz      short loc_18001AC9F
0x18001ac67  test    dword ptr [rcx+1Ch], 1000h
0x18001ac6e  jz      short loc_18001AC9F
0x18001ac70  mov     eax, [rbp+arg_8]
0x18001ac73  lea     r9, aTestmodecheck; "TestModeCheck"
0x18001ac7a  mov     rcx, [rcx+10h]
0x18001ac7e  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18001ac85  mov     dword ptr [rsp+50h+pvData], eax
0x18001ac89  mov     edx, 34h ; '4'
0x18001ac8e  mov     [rsp+50h+phkResult], rsi
0x18001ac93  call    WPP_SF_SSd
0x18001ac98  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac9f  cmp     [rbp+pdwType], 4
0x18001aca3  mov     eax, [rbp+arg_8]
0x18001aca6  jnz     short loc_18001ACE6
0x18001aca8  cmp     eax, 1
0x18001acab  jnz     short loc_18001ACE6
0x18001acad  cmp     rcx, rdi
0x18001acb0  jz      short loc_18001ACDE
0x18001acb2  test    dword ptr [rcx+1Ch], 1000h
0x18001acb9  jz      short loc_18001ACDE
0x18001acbb  mov     rcx, [rcx+10h]
0x18001acbf  lea     edx, [rax+34h]
0x18001acc2  mov     dword ptr [rsp+50h+pvData], eax
0x18001acc6  lea     r9, aTestmodecheck; "TestModeCheck"
0x18001accd  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18001acd4  mov     [rsp+50h+phkResult], rsi
0x18001acd9  call    WPP_SF_SSd
0x18001acde  mov     r14d, 1
0x18001ace4  jmp     short loc_18001AD19
0x18001ace6  cmp     rcx, rdi
0x18001ace9  jz      short loc_18001AD19
0x18001aceb  test    dword ptr [rcx+1Ch], 1000h
0x18001acf2  jz      short loc_18001AD19
0x18001acf4  mov     rcx, [rcx+10h]
0x18001acf8  lea     r9, aTestmodecheck; "TestModeCheck"
0x18001acff  mov     dword ptr [rsp+50h+pvData], eax
0x18001ad03  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18001ad0a  mov     edx, 36h ; '6'
0x18001ad0f  mov     [rsp+50h+phkResult], rsi
0x18001ad14  call    WPP_SF_SSd
0x18001ad19  mov     rcx, [rbp+hkey]; hKey
0x18001ad1d  test    rcx, rcx
0x18001ad20  jz      short loc_18001AD2E
0x18001ad22  call    cs:__imp_RegCloseKey
0x18001ad29  nop     dword ptr [rax+rax+00h]
0x18001ad2e  mov     rsi, [rsp+50h+arg_0]
0x18001ad33  mov     eax, r14d
0x18001ad36  add     rsp, 50h
0x18001ad3a  pop     r14
0x18001ad3c  pop     rdi
0x18001ad3d  pop     rbp
0x18001ad3e  retn
```
