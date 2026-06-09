# NgscbSetBoolRegistryHelper

- ea: `0x180010910`
- end: `0x180010a42`
- name: `NgscbSetBoolRegistryHelper`
- size: `306`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010a48`

## callees

- `0x1800037a0`
- `0x180010910`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800109e2`
- `ADVAPI32!RegSetValueExW` at `0x1800109e2`
- `ADVAPI32!RegCreateKeyExW` at `0x180010970`
- `ADVAPI32!RegCreateKeyExW` at `0x180010970`
- `ADVAPI32!RegCloseKey` at `0x180010a2f`
- `ADVAPI32!RegCloseKey` at `0x180010a2f`

## pseudocode

```c
__int64 NgscbSetBoolRegistryHelper()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF

  Data = 0;
  hKey = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\BitLocker", 0, 0, 0, 2u, 0, &hKey, 0);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( !v1 )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v1);
  if ( (v1 & 0x80000000) == 0 )
  {
LABEL_8:
    v2 = RegSetValueExW(hKey, L"PreventDeviceEncryption", 0, 4u, (const BYTE *)&Data, 4u);
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180010910  mov     rax, rsp
0x180010913  mov     [rax+18h], rbx
0x180010917  mov     [rax+10h], dl
0x18001091a  mov     [rax+8], rcx
0x18001091e  push    rsi
0x18001091f  sub     rsp, 50h
0x180010923  mov     qword ptr [rax-18h], 0
0x18001092b  xor     r9d, r9d; lpClass
0x18001092e  mov     dword ptr [rax+10h], 0
0x180010935  xor     r8d, r8d; Reserved
0x180010938  mov     qword ptr [rax+8], 0
0x180010940  lea     rax, [rax+8]
0x180010944  mov     [rsp+58h+phkResult], rax; phkResult
0x180010949  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x180010950  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010959  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010960  mov     [rsp+58h+samDesired], 2; samDesired
0x180010968  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180010970  call    cs:__imp_RegCreateKeyExW
0x180010976  mov     ebx, eax
0x180010978  test    eax, eax
0x18001097a  jle     short loc_180010985
0x18001097c  movzx   ebx, ax
0x18001097f  or      ebx, 80070000h
0x180010985  lea     rsi, WPP_GLOBAL_Control
0x18001098c  test    ebx, ebx
0x18001098e  jz      short loc_1800109BE
0x180010990  mov     rcx, cs:WPP_GLOBAL_Control
0x180010997  cmp     rcx, rsi
0x18001099a  jz      short loc_1800109BA
0x18001099c  test    byte ptr [rcx+1Ch], 40h
0x1800109a0  jz      short loc_1800109BA
0x1800109a2  mov     rcx, [rcx+10h]
0x1800109a6  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800109ad  mov     edx, 12Bh
0x1800109b2  mov     r9d, ebx
0x1800109b5  call    WPP_SF_d
0x1800109ba  test    ebx, ebx
0x1800109bc  js      short loc_180010A25
0x1800109be  mov     rcx, [rsp+58h+hKey]; hKey
0x1800109c3  lea     rax, [rsp+58h+Data]
0x1800109c8  mov     r9d, 4; dwType
0x1800109ce  lea     rdx, ValueName; "PreventDeviceEncryption"
0x1800109d5  mov     [rsp+58h+samDesired], r9d; cbData
0x1800109da  xor     r8d, r8d; Reserved
0x1800109dd  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800109e2  call    cs:__imp_RegSetValueExW
0x1800109e8  mov     ebx, eax
0x1800109ea  test    eax, eax
0x1800109ec  jle     short loc_1800109F7
0x1800109ee  movzx   ebx, ax
0x1800109f1  or      ebx, 80070000h
0x1800109f7  test    ebx, ebx
0x1800109f9  jz      short loc_180010A25
0x1800109fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a02  cmp     rcx, rsi
0x180010a05  jz      short loc_180010A25
0x180010a07  test    byte ptr [rcx+1Ch], 40h
0x180010a0b  jz      short loc_180010A25
0x180010a0d  mov     rcx, [rcx+10h]
0x180010a11  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010a18  mov     edx, 12Ch
0x180010a1d  mov     r9d, ebx
0x180010a20  call    WPP_SF_d
0x180010a25  mov     rcx, [rsp+58h+hKey]; hKey
0x180010a2a  test    rcx, rcx
0x180010a2d  jz      short loc_180010A35
0x180010a2f  call    cs:__imp_RegCloseKey
0x180010a35  mov     eax, ebx
0x180010a37  mov     rbx, [rsp+58h+arg_10]
0x180010a3c  add     rsp, 50h
0x180010a40  pop     rsi
0x180010a41  retn
```
