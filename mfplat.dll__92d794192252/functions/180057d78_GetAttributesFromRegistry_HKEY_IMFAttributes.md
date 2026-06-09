# GetAttributesFromRegistry(HKEY__ *,IMFAttributes *)

- ea: `0x180057d78`
- end: `0x180057e7b`
- name: `?GetAttributesFromRegistry@@YAJPEAUHKEY__@@PEAUIMFAttributes@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(HKEY hKey, IMFAttributes *pAttributes)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056c20`
- `0x18005735c`
- `0x1800a8634`

## callees

- `0x180057d78`
- `0x180058600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057dba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057e35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057dba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057dd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057dd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057e08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057e08`

## pseudocode

```c
__int64 __fastcall GetAttributesFromRegistry(HKEY hKey, IMFAttributes *pAttributes)
{
  BYTE *lpData; // rdi
  int v5; // eax
  bool v6; // sf
  int v7; // ebx
  LSTATUS Value; // eax
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF
  DWORD v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  lpData = 0;
  LODWORD(cb) = 0;
  v5 = RegQueryValueExW(hKey, L"Attributes", 0, &v11, 0, (LPDWORD)&cb);
  v6 = v5 < 0;
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5 | 0x80070000;
    v6 = v5 < 0;
  }
  if ( v6 )
  {
    v7 = 0;
    if ( v5 != -2147024894 )
      v7 = v5;
  }
  else if ( (_DWORD)cb && v11 == 3 )
  {
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( lpData )
    {
      Value = RegQueryValueExW(hKey, L"Attributes", 0, 0, lpData, (LPDWORD)&cb);
      v7 = Value;
      if ( Value > 0 )
        v7 = (unsigned __int16)Value | 0x80070000;
      if ( v7 >= 0 )
        v7 = MFInitAttributesFromBlob(pAttributes, lpData, cb);
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147467259;
  }
  CoTaskMemFree(lpData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180057d78  mov     r11, rsp
0x180057d7b  mov     [r11+8], rbx
0x180057d7f  mov     [r11+10h], rsi
0x180057d83  push    rdi
0x180057d84  sub     rsp, 30h
0x180057d88  lea     rax, [r11+18h]
0x180057d8c  mov     [rsp+38h+arg_18], 0
0x180057d94  mov     rsi, rdx
0x180057d97  mov     [r11-10h], rax
0x180057d9b  xor     edi, edi
0x180057d9d  mov     dword ptr [rsp+38h+cb], 0
0x180057da5  lea     r9, [r11+20h]; lpType
0x180057da9  mov     [r11-18h], rdi
0x180057dad  xor     r8d, r8d; lpReserved
0x180057db0  lea     rdx, ValueName; "Attributes"
0x180057db7  mov     rbx, rcx
0x180057dba  call    cs:__imp_RegQueryValueExW
0x180057dc0  test    eax, eax
0x180057dc2  jg      short loc_180057DEB
0x180057dc4  jns     short loc_180057DF7
0x180057dc6  xor     ebx, ebx
0x180057dc8  cmp     eax, 80070002h
0x180057dcd  cmovnz  ebx, eax
0x180057dd0  mov     rcx, rdi; pv
0x180057dd3  call    cs:__imp_CoTaskMemFree
0x180057dd9  mov     rsi, [rsp+38h+arg_8]
0x180057dde  mov     eax, ebx
0x180057de0  mov     rbx, [rsp+38h+arg_0]
0x180057de5  add     rsp, 30h
0x180057de9  pop     rdi
0x180057dea  retn
0x180057deb  movzx   eax, ax
0x180057dee  or      eax, 80070000h
0x180057df3  test    eax, eax
0x180057df5  jmp     short loc_180057DC4
0x180057df7  mov     eax, dword ptr [rsp+38h+cb]
0x180057dfb  test    eax, eax
0x180057dfd  jz      short loc_180057E67
0x180057dff  cmp     [rsp+38h+arg_18], 3
0x180057e04  jnz     short loc_180057E67
0x180057e06  mov     ecx, eax; cb
0x180057e08  call    cs:__imp_CoTaskMemAlloc
0x180057e0e  mov     rdi, rax
0x180057e11  test    rax, rax
0x180057e14  jz      short loc_180057E71
0x180057e16  lea     rax, [rsp+38h+cb]
0x180057e1b  xor     r9d, r9d; lpType
0x180057e1e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180057e23  lea     rdx, ValueName; "Attributes"
0x180057e2a  xor     r8d, r8d; lpReserved
0x180057e2d  mov     [rsp+38h+lpData], rdi; lpData
0x180057e32  mov     rcx, rbx; hKey
0x180057e35  call    cs:__imp_RegQueryValueExW
0x180057e3b  mov     ebx, eax
0x180057e3d  test    eax, eax
0x180057e3f  jg      short loc_180057E5C
0x180057e41  test    ebx, ebx
0x180057e43  js      short loc_180057DD0
0x180057e45  mov     r8d, dword ptr [rsp+38h+cb]; cbBufSize
0x180057e4a  mov     rdx, rdi; pBuf
0x180057e4d  mov     rcx, rsi; pAttributes
0x180057e50  call    MFInitAttributesFromBlob
0x180057e55  mov     ebx, eax
0x180057e57  jmp     loc_180057DD0
0x180057e5c  movzx   ebx, ax
0x180057e5f  or      ebx, 80070000h
0x180057e65  jmp     short loc_180057E41
0x180057e67  mov     ebx, 80004005h
0x180057e6c  jmp     loc_180057DD0
0x180057e71  mov     ebx, 8007000Eh
0x180057e76  jmp     loc_180057DD0
```
