# CFveTpm::SqmOnTpmSeal(ulong,ePcrBitmapSource)

- ea: `0x18005095c`
- end: `0x180050c6e`
- name: `?SqmOnTpmSeal@CFveTpm@@KAXKW4ePcrBitmapSource@@@Z`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180090f94`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018700`
- `0x180018c68`
- `0x180019128`
- `0x18005095c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050acc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050acc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050bc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050bc8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050b51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050c13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050c13`

## pseudocode

```c
LSTATUS __fastcall CFveTpm::SqmOnTpmSeal(unsigned int a1, unsigned int a2)
{
  int v4; // edi
  unsigned int FirmwareType; // eax
  signed int v6; // ebx
  PVOID *v7; // rcx
  unsigned int v8; // eax
  LSTATUS v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  LSTATUS result; // eax
  bool v13; // [rsp+50h] [rbp-30h] BYREF
  enum _FIRMWARE_TYPE v14; // [rsp+54h] [rbp-2Ch] BYREF
  HKEY hkey; // [rsp+58h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 pvData; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-10h]

  hkey = 0;
  pvData = 0;
  v18 = 0;
  v13 = 0;
  v14 = FirmwareTypeUnknown;
  pcbData = 12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  if ( a2 == 7 )
  {
    v4 = 1;
  }
  else
  {
    FirmwareType = FveGetFirmwareType(&v14);
    v6 = FirmwareType;
    if ( FirmwareType )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          211,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          FirmwareType);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 < 0 )
        goto LABEL_39;
    }
    if ( v14 == FirmwareTypeBios )
    {
      v4 = 0;
    }
    else
    {
      v8 = NgscbCheckIsAOACDevice(&v13);
      v6 = v8;
      if ( v8 )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v8);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 < 0 )
          goto LABEL_39;
      }
      v4 = v13 + 1;
    }
  }
  v9 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\BitLockerSQM",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hkey,
         0);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( !v6 )
    goto LABEL_46;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      213,
      &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
      (unsigned int)v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
LABEL_46:
    if ( a2 == 4 && !RegGetValueW(hkey, 0, L"OSVPcrProfileData", 8u, 0, &pvData, &pcbData) && pcbData == 12 )
    {
      v10 = v18;
      if ( v18 != 4 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v18);
          v10 = v18;
        }
        a2 = v10;
      }
    }
    pvData = __PAIR64__(v4, a1);
    v18 = a2;
    v11 = RegSetValueExW(hkey, L"OSVPcrProfileData", 0, 3u, (const BYTE *)&pvData, 0xCu);
    v6 = v11;
    if ( !v11 )
      goto LABEL_38;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v11);
LABEL_38:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_39:
  result = (int)hkey;
  if ( hkey )
  {
    result = RegCloseKey(hkey);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    return WPP_SF_d(v7[2], 216, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)v6);
  return result;
}

```

## disassembly

```asm
0x18005095c  mov     [rsp-28h+arg_10], rbx
0x180050961  mov     [rsp-28h+arg_18], rsi
0x180050966  push    rbp
0x180050967  push    rdi
0x180050968  push    r12
0x18005096a  push    r13
0x18005096c  push    r14
0x18005096e  mov     rbp, rsp
0x180050971  sub     rsp, 80h
0x180050978  mov     rax, cs:__security_cookie
0x18005097f  xor     rax, rsp
0x180050982  mov     [rbp+var_8], rax
0x180050986  xor     eax, eax
0x180050988  mov     [rbp+hkey], 0
0x180050990  mov     [rbp+pvData], rax
0x180050994  mov     esi, edx
0x180050996  mov     [rbp+var_10], eax
0x180050999  mov     r14d, ecx
0x18005099c  mov     [rbp+var_30], 0
0x1800509a0  mov     [rbp+var_2C], 0
0x1800509a7  mov     [rbp+pcbData], 0Ch
0x1800509ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800509b5  lea     r12, WPP_GLOBAL_Control
0x1800509bc  lea     r13, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800509c3  cmp     rcx, r12
0x1800509c6  jz      short loc_1800509DF
0x1800509c8  test    byte ptr [rcx+1Ch], 20h
0x1800509cc  jz      short loc_1800509DF
0x1800509ce  mov     rcx, [rcx+10h]
0x1800509d2  mov     edx, 0D2h
0x1800509d7  mov     r8, r13
0x1800509da  call    WPP_SF_
0x1800509df  cmp     esi, 7
0x1800509e2  jnz     short loc_1800509EC
0x1800509e4  lea     edi, [rsi-6]
0x1800509e7  jmp     loc_180050A8D
0x1800509ec  lea     rcx, [rbp+var_2C]; enum _FIRMWARE_TYPE *
0x1800509f0  call    ?FveGetFirmwareType@@YAJPEAW4_FIRMWARE_TYPE@@@Z; FveGetFirmwareType(_FIRMWARE_TYPE *)
0x1800509f5  mov     ebx, eax
0x1800509f7  test    eax, eax
0x1800509f9  jz      short loc_180050A30
0x1800509fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a02  cmp     rcx, r12
0x180050a05  jz      short loc_180050A28
0x180050a07  test    byte ptr [rcx+1Ch], 40h
0x180050a0b  jz      short loc_180050A28
0x180050a0d  mov     rcx, [rcx+10h]
0x180050a11  mov     edx, 0D3h
0x180050a16  mov     r9d, eax
0x180050a19  mov     r8, r13
0x180050a1c  call    WPP_SF_d
0x180050a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a28  test    ebx, ebx
0x180050a2a  js      loc_180050C07
0x180050a30  mov     edi, 1
0x180050a35  cmp     [rbp+var_2C], edi
0x180050a38  jnz     short loc_180050A3E
0x180050a3a  xor     edi, edi
0x180050a3c  jmp     short loc_180050A8D
0x180050a3e  lea     rcx, [rbp+var_30]; bool *
0x180050a42  call    ?NgscbCheckIsAOACDevice@@YAJPEA_N@Z; NgscbCheckIsAOACDevice(bool *)
0x180050a47  mov     ebx, eax
0x180050a49  test    eax, eax
0x180050a4b  jz      short loc_180050A82
0x180050a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a54  cmp     rcx, r12
0x180050a57  jz      short loc_180050A7A
0x180050a59  test    byte ptr [rcx+1Ch], 40h
0x180050a5d  jz      short loc_180050A7A
0x180050a5f  mov     rcx, [rcx+10h]
0x180050a63  mov     edx, 0D4h
0x180050a68  mov     r9d, eax
0x180050a6b  mov     r8, r13
0x180050a6e  call    WPP_SF_d
0x180050a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a7a  test    ebx, ebx
0x180050a7c  js      loc_180050C07
0x180050a82  mov     al, [rbp+var_30]
0x180050a85  neg     al
0x180050a87  sbb     ecx, ecx
0x180050a89  neg     ecx
0x180050a8b  add     edi, ecx
0x180050a8d  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x180050a96  lea     rax, [rbp+hkey]
0x180050a9a  mov     [rsp+80h+phkResult], rax; phkResult
0x180050a9f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180050aa6  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180050aaf  xor     r9d, r9d; lpClass
0x180050ab2  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x180050aba  xor     r8d, r8d; Reserved
0x180050abd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050ac4  mov     [rsp+80h+dwOptions], 0; dwOptions
0x180050acc  call    cs:__imp_RegCreateKeyExW
0x180050ad3  nop     dword ptr [rax+rax+00h]
0x180050ad8  mov     ebx, eax
0x180050ada  test    eax, eax
0x180050adc  jle     short loc_180050AE7
0x180050ade  movzx   ebx, ax
0x180050ae1  or      ebx, 80070000h
0x180050ae7  test    ebx, ebx
0x180050ae9  jz      short loc_180050B20
0x180050aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180050af2  cmp     rcx, r12
0x180050af5  jz      short loc_180050B18
0x180050af7  test    byte ptr [rcx+1Ch], 40h
0x180050afb  jz      short loc_180050B18
0x180050afd  mov     rcx, [rcx+10h]
0x180050b01  mov     edx, 0D5h
0x180050b06  mov     r9d, ebx
0x180050b09  mov     r8, r13
0x180050b0c  call    WPP_SF_d
0x180050b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b18  test    ebx, ebx
0x180050b1a  js      loc_180050C07
0x180050b20  cmp     esi, 4
0x180050b23  jnz     short loc_180050B99
0x180050b25  mov     rcx, [rbp+hkey]; hkey
0x180050b29  lea     rax, [rbp+pcbData]
0x180050b2d  mov     [rsp+80h+lpSecurityAttributes], rax; pcbData
0x180050b32  lea     r9d, [rsi+4]; dwFlags
0x180050b36  lea     rax, [rbp+pvData]
0x180050b3a  xor     edx, edx; lpSubKey
0x180050b3c  mov     qword ptr [rsp+80h+samDesired], rax; pvData
0x180050b41  lea     r8, ValueName; "OSVPcrProfileData"
0x180050b48  mov     qword ptr [rsp+80h+dwOptions], 0; pdwType
0x180050b51  call    cs:__imp_RegGetValueW
0x180050b58  nop     dword ptr [rax+rax+00h]
0x180050b5d  test    eax, eax
0x180050b5f  jnz     short loc_180050B99
0x180050b61  cmp     [rbp+pcbData], 0Ch
0x180050b65  jnz     short loc_180050B99
0x180050b67  mov     eax, [rbp+var_10]
0x180050b6a  cmp     eax, esi
0x180050b6c  jz      short loc_180050B99
0x180050b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b75  cmp     rcx, r12
0x180050b78  jz      short loc_180050B97
0x180050b7a  test    byte ptr [rcx+1Ch], 8
0x180050b7e  jz      short loc_180050B97
0x180050b80  mov     rcx, [rcx+10h]
0x180050b84  mov     edx, 0D6h
0x180050b89  mov     r9d, eax
0x180050b8c  mov     r8, r13
0x180050b8f  call    WPP_SF_D
0x180050b94  mov     eax, [rbp+var_10]
0x180050b97  mov     esi, eax
0x180050b99  mov     rcx, [rbp+hkey]; hKey
0x180050b9d  lea     rax, [rbp+pvData]
0x180050ba1  mov     [rsp+80h+samDesired], 0Ch; cbData
0x180050ba9  lea     rdx, ValueName; "OSVPcrProfileData"
0x180050bb0  mov     r9d, 3; dwType
0x180050bb6  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x180050bbb  xor     r8d, r8d; Reserved
0x180050bbe  mov     dword ptr [rbp+pvData], r14d
0x180050bc2  mov     dword ptr [rbp+pvData+4], edi
0x180050bc5  mov     [rbp+var_10], esi
0x180050bc8  call    cs:__imp_RegSetValueExW
0x180050bcf  nop     dword ptr [rax+rax+00h]
0x180050bd4  mov     ebx, eax
0x180050bd6  test    eax, eax
0x180050bd8  jz      short loc_180050C00
0x180050bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180050be1  cmp     rcx, r12
0x180050be4  jz      short loc_180050C07
0x180050be6  test    byte ptr [rcx+1Ch], 40h
0x180050bea  jz      short loc_180050C07
0x180050bec  mov     rcx, [rcx+10h]
0x180050bf0  mov     edx, 0D7h
0x180050bf5  mov     r9d, eax
0x180050bf8  mov     r8, r13
0x180050bfb  call    WPP_SF_d
0x180050c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c07  mov     rax, [rbp+hkey]
0x180050c0b  test    rax, rax
0x180050c0e  jz      short loc_180050C26
0x180050c10  mov     rcx, rax; hKey
0x180050c13  call    cs:__imp_RegCloseKey
0x180050c1a  nop     dword ptr [rax+rax+00h]
0x180050c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c26  cmp     rcx, r12
0x180050c29  jz      short loc_180050C45
0x180050c2b  test    byte ptr [rcx+1Ch], 20h
0x180050c2f  jz      short loc_180050C45
0x180050c31  mov     rcx, [rcx+10h]
0x180050c35  mov     edx, 0D8h
0x180050c3a  mov     r9d, ebx
0x180050c3d  mov     r8, r13
0x180050c40  call    WPP_SF_d
0x180050c45  mov     rcx, [rbp+var_8]
0x180050c49  xor     rcx, rsp; StackCookie
0x180050c4c  call    __security_check_cookie
0x180050c51  lea     r11, [rsp+80h+var_s0]
0x180050c59  mov     rbx, [r11+40h]
0x180050c5d  mov     rsi, [r11+48h]
0x180050c61  mov     rsp, r11
0x180050c64  pop     r14
0x180050c66  pop     r13
0x180050c68  pop     r12
0x180050c6a  pop     rdi
0x180050c6b  pop     rbp
0x180050c6c  retn
```
