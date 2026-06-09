# RasDefIntConnOpenKey

- ea: `0x18000f0bc`
- end: `0x18000f2b4`
- name: `RasDefIntConnOpenKey`
- size: `504`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000efe4`
- `0x18006bf8c`

## callees

- `0x18000f0bc`
- `0x18000f2bc`
- `0x18000f388`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f295`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f295`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f16c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f1bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f26c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f16c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f1bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f26c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1f7`

## pseudocode

```c
__int64 __fastcall RasDefIntConnOpenKey(int a1, int a2, int a3, HKEY *a4)
{
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // edi
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  HKEY v15; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF

  dwDisposition = 0;
  v15 = 0;
  hKey = 0;
  v8 = IsConsumerPlatform();
  if ( a1 )
  {
    if ( !v8 )
    {
      if ( a2 )
        return 87;
      goto LABEL_4;
    }
  }
  else if ( !v8 )
  {
    goto LABEL_4;
  }
  if ( a2 )
  {
    v10 = -2147483646;
    goto LABEL_5;
  }
LABEL_4:
  v9 = IsRasmanProcessInternal();
  v10 = -2147483647;
  if ( !v9 )
  {
LABEL_5:
    v11 = 0;
    v15 = (HKEY)v10;
LABEL_6:
    v12 = RegCreateKeyExW(
            (HKEY)v10,
            L"Software\\Microsoft\\RAS AutoDial",
            0,
            0,
            0,
            a3 != 0 ? 131101 : 131103,
            0,
            &hKey,
            &dwDisposition);
    v13 = v12;
    if ( !v12
      || a3
      && v12 == 5
      && (v13 = RegCreateKeyExW(v15, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x20019u, 0, &hKey, &dwDisposition)) == 0 )
    {
      v13 = RegCreateKeyExW(hKey, L"Default", 0, 0, 0, a3 != 0 ? 131097 : 131103, 0, a4, &dwDisposition);
    }
    goto LABEL_8;
  }
  v13 = RegOpenKeyExW(HKEY_CURRENT_USER, 0, 0, 0xF003Fu, &v15);
  if ( !v13 )
  {
    v10 = (__int64)v15;
    v11 = 1;
    goto LABEL_6;
  }
  v11 = 0;
LABEL_8:
  if ( v15 && v11 )
    RegCloseKey(v15);
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x18000f0bc  mov     [rsp-18h+arg_8], rbx
0x18000f0c1  mov     [rsp-18h+arg_10], rsi
0x18000f0c6  push    rbp
0x18000f0c7  push    rdi
0x18000f0c8  push    r14
0x18000f0ca  mov     rbp, rsp
0x18000f0cd  sub     rsp, 60h
0x18000f0d1  mov     r14, r9
0x18000f0d4  mov     [rbp+dwDisposition], 0
0x18000f0db  mov     esi, r8d
0x18000f0de  mov     [rbp+var_10], 0
0x18000f0e6  mov     edi, edx
0x18000f0e8  mov     [rbp+hKey], 0
0x18000f0f0  mov     ebx, ecx
0x18000f0f2  call    IsConsumerPlatform
0x18000f0f7  test    ebx, ebx
0x18000f0f9  jz      loc_18000F20B
0x18000f0ff  test    eax, eax
0x18000f101  jz      loc_18000F218
0x18000f107  test    edi, edi
0x18000f109  jnz     loc_18000F1FF
0x18000f10f  call    IsRasmanProcessInternal
0x18000f114  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f11b  test    eax, eax
0x18000f11d  jnz     loc_18000F281
0x18000f123  xor     edi, edi
0x18000f125  mov     [rbp+var_10], rcx
0x18000f129  mov     eax, esi
0x18000f12b  neg     eax
0x18000f12d  lea     rax, [rbp+dwDisposition]
0x18000f131  sbb     edx, edx
0x18000f133  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000f138  and     edx, 0FFFFFFFEh
0x18000f13b  lea     rax, [rbp+hKey]
0x18000f13f  mov     [rsp+60h+phkResult], rax; phkResult
0x18000f144  add     edx, 2001Fh
0x18000f14a  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f153  xor     r9d, r9d; lpClass
0x18000f156  mov     [rsp+60h+samDesired], edx; samDesired
0x18000f15a  xor     r8d, r8d; Reserved
0x18000f15d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18000f164  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18000f16c  call    cs:__imp_RegCreateKeyExW
0x18000f172  mov     ebx, eax
0x18000f174  test    eax, eax
0x18000f176  jnz     loc_18000F227
0x18000f17c  neg     esi
0x18000f17e  lea     rcx, [rbp+dwDisposition]
0x18000f182  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x18000f187  lea     rdx, aDefault; "Default"
0x18000f18e  mov     rcx, [rbp+hKey]; hKey
0x18000f192  sbb     eax, eax
0x18000f194  mov     [rsp+60h+phkResult], r14; phkResult
0x18000f199  and     eax, 0FFFFFFFAh
0x18000f19c  add     eax, 2001Fh
0x18000f1a1  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f1aa  mov     [rsp+60h+samDesired], eax; samDesired
0x18000f1ae  xor     r9d, r9d; lpClass
0x18000f1b1  xor     r8d, r8d; Reserved
0x18000f1b4  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18000f1bc  call    cs:__imp_RegCreateKeyExW
0x18000f1c2  mov     ebx, eax
0x18000f1c4  mov     rcx, [rbp+var_10]; hKey
0x18000f1c8  test    rcx, rcx
0x18000f1cb  jnz     short loc_18000F1F3
0x18000f1cd  mov     rcx, [rbp+hKey]; hKey
0x18000f1d1  test    rcx, rcx
0x18000f1d4  jz      short loc_18000F1DC
0x18000f1d6  call    cs:__imp_RegCloseKey
0x18000f1dc  mov     eax, ebx
0x18000f1de  lea     r11, [rsp+60h+var_s0]
0x18000f1e3  mov     rbx, [r11+28h]
0x18000f1e7  mov     rsi, [r11+30h]
0x18000f1eb  mov     rsp, r11
0x18000f1ee  pop     r14
0x18000f1f0  pop     rdi
0x18000f1f1  pop     rbp
0x18000f1f2  retn
0x18000f1f3  test    edi, edi
0x18000f1f5  jz      short loc_18000F1CD
0x18000f1f7  call    cs:__imp_RegCloseKey
0x18000f1fd  jmp     short loc_18000F1CD
0x18000f1ff  mov     rcx, 0FFFFFFFF80000002h
0x18000f206  jmp     loc_18000F123
0x18000f20b  test    eax, eax
0x18000f20d  jz      loc_18000F10F
0x18000f213  jmp     loc_18000F107
0x18000f218  test    edi, edi
0x18000f21a  jz      loc_18000F10F
0x18000f220  mov     eax, 57h ; 'W'
0x18000f225  jmp     short loc_18000F1DE
0x18000f227  test    esi, esi
0x18000f229  jz      short loc_18000F1C4
0x18000f22b  cmp     eax, 5
0x18000f22e  jnz     short loc_18000F1C4
0x18000f230  mov     rcx, [rbp+var_10]; hKey
0x18000f234  lea     rax, [rbp+dwDisposition]
0x18000f238  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000f23d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18000f244  lea     rax, [rbp+hKey]
0x18000f248  xor     r9d, r9d; lpClass
0x18000f24b  mov     [rsp+60h+phkResult], rax; phkResult
0x18000f250  xor     r8d, r8d; Reserved
0x18000f253  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f25c  mov     [rsp+60h+samDesired], 20019h; samDesired
0x18000f264  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18000f26c  call    cs:__imp_RegCreateKeyExW
0x18000f272  mov     ebx, eax
0x18000f274  test    eax, eax
0x18000f276  jnz     loc_18000F1C4
0x18000f27c  jmp     loc_18000F17C
0x18000f281  lea     rax, [rbp+var_10]
0x18000f285  mov     r9d, 0F003Fh; samDesired
0x18000f28b  xor     r8d, r8d; ulOptions
0x18000f28e  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x18000f293  xor     edx, edx; lpSubKey
0x18000f295  call    cs:__imp_RegOpenKeyExW
0x18000f29b  mov     ebx, eax
0x18000f29d  test    eax, eax
0x18000f29f  jnz     short loc_18000F2AD
0x18000f2a1  mov     rcx, [rbp+var_10]
0x18000f2a5  lea     edi, [rax+1]
0x18000f2a8  jmp     loc_18000F129
0x18000f2ad  xor     edi, edi
0x18000f2af  jmp     loc_18000F1C4
```
