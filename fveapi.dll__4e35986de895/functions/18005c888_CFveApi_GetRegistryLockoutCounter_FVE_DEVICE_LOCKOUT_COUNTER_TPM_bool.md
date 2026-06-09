# CFveApi::GetRegistryLockoutCounter(_FVE_DEVICE_LOCKOUT_COUNTER_TPM *,bool)

- ea: `0x18005c888`
- end: `0x18005ca76`
- name: `?GetRegistryLockoutCounter@CFveApi@@AEAAJPEAU_FVE_DEVICE_LOCKOUT_COUNTER_TPM@@_N@Z`
- size: `494`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, struct _FVE_DEVICE_LOCKOUT_COUNTER_TPM *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c935c`
- `0x1800c9ac8`

## callees

- `0x18005c888`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c90e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c90e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ca06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ca06`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005c966`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005c966`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005ca34`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180121dc6`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005ca34`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180121dc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ca45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180121dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ca45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180121dd6`

## pseudocode

```c
__int64 __fastcall CFveApi::GetRegistryLockoutCounter(
        CFveApi *this,
        struct _FVE_DEVICE_LOCKOUT_COUNTER_TPM *a2,
        char a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS ValueW; // eax
  unsigned __int64 v8; // rax
  LSTATUS v9; // eax
  HKEY v10; // rcx
  HKEY hkey; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int64 pvData; // [rsp+60h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-20h] BYREF

  pvData = 0;
  cbData = 8;
  hkey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\FVE",
         0,
         0,
         0,
         0x2001Bu,
         0,
         &hkey,
         0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"DeviceLockoutCount", 0x40u, 0, &pvData, &cbData);
    v6 = ValueW;
    if ( ValueW > 0 )
      v6 = (unsigned __int16)ValueW | 0x80070000;
    if ( v6 == -2147024894 )
    {
      if ( a3 )
        ++*((_QWORD *)a2 + 1);
      pvData = *((_QWORD *)a2 + 1);
      a3 = 1;
LABEL_16:
      v9 = RegSetValueExW(hkey, L"DeviceLockoutCount", 0, 0xBu, (const BYTE *)&pvData, cbData);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_18;
    }
    if ( v6 >= 0 )
    {
      v8 = pvData;
      if ( *((_QWORD *)a2 + 1) > pvData )
      {
        v8 = *((_QWORD *)a2 + 1);
        pvData = v8;
      }
      if ( a3 )
        pvData = ++v8;
      *((_QWORD *)a2 + 1) = v8;
      if ( a3 )
        goto LABEL_16;
    }
  }
LABEL_18:
  v10 = hkey;
  if ( hkey )
  {
    if ( a3 )
    {
      RegFlushKey(hkey);
      v10 = hkey;
    }
    RegCloseKey(v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005c888  mov     r11, rsp
0x18005c88b  mov     [r11+8], rbx
0x18005c88f  mov     [r11+18h], rsi
0x18005c893  push    rdi
0x18005c894  sub     rsp, 80h
0x18005c89b  mov     rax, cs:__security_cookie
0x18005c8a2  xor     rax, rsp
0x18005c8a5  mov     [rsp+88h+var_18], rax
0x18005c8aa  mov     dil, r8b
0x18005c8ad  mov     rsi, rdx
0x18005c8b0  mov     qword ptr [r11-28h], 0
0x18005c8b8  mov     [rsp+88h+cbData], 8
0x18005c8c0  mov     qword ptr [r11-30h], 0
0x18005c8c8  mov     [rsp+88h+var_38], 0
0x18005c8cd  mov     [rsp+88h+var_38], r8b
0x18005c8d2  mov     qword ptr [r11-48h], 0
0x18005c8da  lea     rax, [r11-30h]
0x18005c8de  mov     [r11-50h], rax
0x18005c8e2  mov     qword ptr [r11-58h], 0
0x18005c8ea  mov     [rsp+88h+samDesired], 2001Bh; samDesired
0x18005c8f2  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18005c8fa  xor     r9d, r9d; lpClass
0x18005c8fd  xor     r8d, r8d; Reserved
0x18005c900  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005c907  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c90e  call    cs:__imp_RegCreateKeyExW
0x18005c915  nop     dword ptr [rax+rax+00h]
0x18005c91a  mov     ebx, eax
0x18005c91c  test    eax, eax
0x18005c91e  jle     short loc_18005C929
0x18005c920  movzx   ebx, ax
0x18005c923  or      ebx, 80070000h
0x18005c929  mov     [rsp+88h+var_34], ebx
0x18005c92d  test    ebx, ebx
0x18005c92f  js      loc_18005CA25
0x18005c935  lea     rax, [rsp+88h+cbData]
0x18005c93a  mov     [rsp+88h+pcbData], rax; pcbData
0x18005c93f  lea     rax, [rsp+88h+pvData]
0x18005c944  mov     qword ptr [rsp+88h+samDesired], rax; pvData
0x18005c949  mov     qword ptr [rsp+88h+dwOptions], 0; pdwType
0x18005c952  mov     r9d, 40h ; '@'; dwFlags
0x18005c958  lea     r8, aDevicelockoutc; "DeviceLockoutCount"
0x18005c95f  xor     edx, edx; lpSubKey
0x18005c961  mov     rcx, [rsp+88h+hkey]; hkey
0x18005c966  call    cs:__imp_RegGetValueW
0x18005c96d  nop     dword ptr [rax+rax+00h]
0x18005c972  mov     ebx, eax
0x18005c974  test    eax, eax
0x18005c976  jle     short loc_18005C981
0x18005c978  movzx   ebx, ax
0x18005c97b  or      ebx, 80070000h
0x18005c981  mov     [rsp+88h+var_34], ebx
0x18005c985  cmp     ebx, 80070002h
0x18005c98b  jnz     short loc_18005C9B1
0x18005c98d  mov     [rsp+88h+var_34], 0
0x18005c995  test    dil, dil
0x18005c998  jz      short loc_18005C99E
0x18005c99a  inc     qword ptr [rsi+8]
0x18005c99e  mov     rax, [rsi+8]
0x18005c9a2  mov     [rsp+88h+pvData], rax
0x18005c9a7  mov     dil, 1
0x18005c9aa  mov     [rsp+88h+var_38], dil
0x18005c9af  jmp     short loc_18005C9DF
0x18005c9b1  test    ebx, ebx
0x18005c9b3  js      short loc_18005CA25
0x18005c9b5  mov     rax, [rsp+88h+pvData]
0x18005c9ba  cmp     [rsi+8], rax
0x18005c9be  jbe     short loc_18005C9C9
0x18005c9c0  mov     rax, [rsi+8]
0x18005c9c4  mov     [rsp+88h+pvData], rax
0x18005c9c9  test    dil, dil
0x18005c9cc  jz      short loc_18005C9D6
0x18005c9ce  inc     rax
0x18005c9d1  mov     [rsp+88h+pvData], rax
0x18005c9d6  mov     [rsi+8], rax
0x18005c9da  test    dil, dil
0x18005c9dd  jz      short loc_18005CA25
0x18005c9df  mov     eax, [rsp+88h+cbData]
0x18005c9e3  mov     [rsp+88h+samDesired], eax; cbData
0x18005c9e7  lea     rax, [rsp+88h+pvData]
0x18005c9ec  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18005c9f1  mov     r9d, 0Bh; dwType
0x18005c9f7  xor     r8d, r8d; Reserved
0x18005c9fa  lea     rdx, aDevicelockoutc; "DeviceLockoutCount"
0x18005ca01  mov     rcx, [rsp+88h+hkey]; hKey
0x18005ca06  call    cs:__imp_RegSetValueExW
0x18005ca0d  nop     dword ptr [rax+rax+00h]
0x18005ca12  mov     ebx, eax
0x18005ca14  test    eax, eax
0x18005ca16  jle     short loc_18005CA21
0x18005ca18  movzx   ebx, ax
0x18005ca1b  or      ebx, 80070000h
0x18005ca21  mov     [rsp+88h+var_34], ebx
0x18005ca25  mov     rcx, [rsp+88h+hkey]; hKey
0x18005ca2a  test    rcx, rcx
0x18005ca2d  jz      short loc_18005CA51
0x18005ca2f  test    dil, dil
0x18005ca32  jz      short loc_18005CA45
0x18005ca34  call    cs:__imp_RegFlushKey
0x18005ca3b  nop     dword ptr [rax+rax+00h]
0x18005ca40  mov     rcx, [rsp+88h+hkey]; hKey
0x18005ca45  call    cs:__imp_RegCloseKey
0x18005ca4c  nop     dword ptr [rax+rax+00h]
0x18005ca51  mov     eax, ebx
0x18005ca53  mov     rcx, [rsp+88h+var_18]
0x18005ca58  xor     rcx, rsp; StackCookie
0x18005ca5b  call    __security_check_cookie
0x18005ca60  lea     r11, [rsp+88h+var_8]
0x18005ca68  mov     rbx, [r11+10h]
0x18005ca6c  mov     rsi, [r11+20h]
0x18005ca70  mov     rsp, r11
0x18005ca73  pop     rdi
0x18005ca74  retn
0x180121dae  push    rbp
0x180121db0  sub     rsp, 50h
0x180121db4  mov     rbp, rdx
0x180121db7  mov     rcx, [rbp+58h]; hKey
0x180121dbb  test    rcx, rcx
0x180121dbe  jz      short loc_180121DE3
0x180121dc0  cmp     byte ptr [rbp+50h], 0
0x180121dc4  jz      short loc_180121DD6
0x180121dc6  call    cs:__imp_RegFlushKey
0x180121dcd  nop     dword ptr [rax+rax+00h]
0x180121dd2  mov     rcx, [rbp+58h]; hKey
0x180121dd6  call    cs:__imp_RegCloseKey
0x180121ddd  nop     dword ptr [rax+rax+00h]
0x180121de2  nop
0x180121de3  add     rsp, 50h
0x180121de7  pop     rbp
0x180121de8  retn
```
