# SetRegistryValue(IIS_SETUP_REGISTRY_ENTRY *)

- ea: `0x180002d14`
- end: `0x180002e5b`
- name: `?SetRegistryValue@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800018e0`

## callees

- `0x180001ab0`
- `0x180001afc`
- `0x18000224c`
- `0x180002d14`
- `0x180002ff8`
- `0x180003650`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180002e02`
- `ADVAPI32!RegSetValueExW` at `0x180002e02`
- `ADVAPI32!RegCloseKey` at `0x180002e24`
- `ADVAPI32!RegCloseKey` at `0x180002e24`
- `ADVAPI32!RegCreateKeyExW` at `0x180002dcf`
- `ADVAPI32!RegCreateKeyExW` at `0x180002dcf`

## pseudocode

```c
__int64 __fastcall SetRegistryValue(struct IIS_SETUP_REGISTRY_ENTRY *a1)
{
  signed int v2; // ebx
  HKEY v3; // rsi
  LSTATUS v4; // eax
  bool v5; // cc
  DWORD v6; // eax
  DWORD cbData; // [rsp+50h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v10[4]; // [rsp+60h] [rbp-9h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp+17h]
  int v12; // [rsp+88h] [rbp+1Fh]
  __int16 v13; // [rsp+8Ch] [rbp+23h]

  hKey = 0;
  lpData = (BYTE *)v10;
  cbData = 0;
  v10[0] = 0;
  v12 = 32;
  v13 = 256;
  if ( a1 )
  {
    v3 = ConvertStringToHKey(*((wchar_t **)a1 + 1));
    v2 = GetRegistryValueToWrite(a1, (struct BUFFER *)v10, &cbData);
    if ( v2 >= 0 )
    {
      v4 = RegCreateKeyExW(v3, *((LPCWSTR *)a1 + 2), 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v5 = v4 <= 0;
      if ( v4
        || (v6 = ConvertStringToType(*((wchar_t **)a1 + 4)),
            v4 = RegSetValueExW(hKey, *((LPCWSTR *)a1 + 3), 0, v6, lpData, cbData),
            v5 = v4 <= 0,
            v4) )
      {
        if ( v5 )
          v2 = v4;
        else
          v2 = (unsigned __int16)v4 | 0x80070000;
      }
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( (_BYTE)v13 )
      BUFFER::FreeMemoryInternal((BUFFER *)v10);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002d14  push    rbp
0x180002d16  push    rbx
0x180002d17  push    rsi
0x180002d18  push    rdi
0x180002d19  lea     rbp, [rsp-3Fh]
0x180002d1e  sub     rsp, 0A8h
0x180002d25  mov     rax, cs:__security_cookie
0x180002d2c  xor     rax, rsp
0x180002d2f  mov     [rbp+57h+var_30], rax
0x180002d33  mov     [rbp+57h+hKey], 0
0x180002d3b  lea     rax, [rbp+57h+var_60]
0x180002d3f  mov     [rbp+57h+lpData], rax
0x180002d43  mov     rdi, rcx
0x180002d46  mov     [rbp+57h+cbData], 0
0x180002d4d  mov     [rbp+57h+var_60], 0
0x180002d55  mov     [rbp+57h+var_38], 20h ; ' '
0x180002d5c  mov     [rbp+57h+var_34], 100h
0x180002d62  test    rcx, rcx
0x180002d65  jnz     short loc_180002D71
0x180002d67  mov     ebx, 80070057h
0x180002d6c  jmp     loc_180002E41
0x180002d71  mov     rcx, [rcx+8]; String1
0x180002d75  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x180002d7a  lea     r8, [rbp+57h+cbData]; unsigned int *
0x180002d7e  mov     rcx, rdi; struct IIS_SETUP_REGISTRY_ENTRY *
0x180002d81  lea     rdx, [rbp+57h+var_60]; this
0x180002d85  mov     rsi, rax
0x180002d88  call    ?GetRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z; GetRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)
0x180002d8d  mov     ebx, eax
0x180002d8f  test    eax, eax
0x180002d91  js      loc_180002E1B
0x180002d97  mov     rdx, [rdi+10h]; lpSubKey
0x180002d9b  lea     rax, [rbp+57h+hKey]
0x180002d9f  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x180002da8  xor     r9d, r9d; lpClass
0x180002dab  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180002db0  xor     r8d, r8d; Reserved
0x180002db3  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180002dbc  mov     rcx, rsi; hKey
0x180002dbf  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x180002dc7  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x180002dcf  call    cs:__imp_RegCreateKeyExW
0x180002dd5  test    eax, eax
0x180002dd7  jnz     short loc_180002E0C
0x180002dd9  mov     rcx, [rdi+20h]; String1
0x180002ddd  call    ?ConvertStringToType@@YAKPEAG@Z; ConvertStringToType(ushort *)
0x180002de2  mov     r8d, [rbp+57h+cbData]
0x180002de6  mov     r9d, eax; dwType
0x180002de9  mov     rdx, [rdi+18h]; lpValueName
0x180002ded  mov     rcx, [rbp+57h+hKey]; hKey
0x180002df1  mov     [rsp+0C0h+samDesired], r8d; cbData
0x180002df6  mov     r8, [rbp+57h+lpData]
0x180002dfa  mov     qword ptr [rsp+0C0h+dwOptions], r8; lpData
0x180002dff  xor     r8d, r8d; Reserved
0x180002e02  call    cs:__imp_RegSetValueExW
0x180002e08  test    eax, eax
0x180002e0a  jz      short loc_180002E1B
0x180002e0c  jg      short loc_180002E12
0x180002e0e  mov     ebx, eax
0x180002e10  jmp     short loc_180002E1B
0x180002e12  movzx   ebx, ax
0x180002e15  or      ebx, 80070000h
0x180002e1b  mov     rcx, [rbp+57h+hKey]; hKey
0x180002e1f  test    rcx, rcx
0x180002e22  jz      short loc_180002E32
0x180002e24  call    cs:__imp_RegCloseKey
0x180002e2a  mov     [rbp+57h+hKey], 0
0x180002e32  cmp     byte ptr [rbp+57h+var_34], 0
0x180002e36  jz      short loc_180002E41
0x180002e38  lea     rcx, [rbp+57h+var_60]; this
0x180002e3c  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002e41  mov     eax, ebx
0x180002e43  mov     rcx, [rbp+57h+var_30]
0x180002e47  xor     rcx, rsp; StackCookie
0x180002e4a  call    __security_check_cookie
0x180002e4f  add     rsp, 0A8h
0x180002e56  pop     rdi
0x180002e57  pop     rsi
0x180002e58  pop     rbx
0x180002e59  pop     rbp
0x180002e5a  retn
```
