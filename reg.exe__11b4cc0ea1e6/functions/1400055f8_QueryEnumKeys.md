# QueryEnumKeys

- ea: `0x1400055f8`
- end: `0x140005938`
- name: `QueryEnumKeys`
- size: `832`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400055f8`
- `0x140005bac`

## callees

- `0x140001bb2`
- `0x140001cc6`
- `0x140002b70`
- `0x1400055f8`
- `0x140005940`
- `0x14000612c`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000e020`
- `0x14000e2f8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058b3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400057a9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400057a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400056e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400056e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000573e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000573e`

## pseudocode

```c
__int64 __fastcall QueryEnumKeys(HKEY a1, const WCHAR *a2, __int64 a3, _DWORD *a4)
{
  unsigned int EnumValues; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  DWORD v11; // ecx
  void *v12; // r14
  int v13; // eax
  LPVOID v14; // r12
  DWORD i; // r15d
  int v16; // eax
  bool v17; // zf
  FILE *v18; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-5h] BYREF
  DWORD v22; // [rsp+68h] [rbp-1h]
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  LPVOID Memory; // [rsp+78h] [rbp+Fh] BYREF
  LPVOID v25[8]; // [rsp+80h] [rbp+17h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+67h] BYREF
  const WCHAR *v27; // [rsp+D8h] [rbp+6Fh]

  v27 = a2;
  cchName = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  Memory = 0;
  v25[0] = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    EnumValues = 87;
    goto LABEL_47;
  }
  if ( a4[1] != 1 )
  {
LABEL_9:
    if ( *(_DWORD *)(a3 + 112) == 1 && (a4[1] != 1 || !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128)) )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( *(_DWORD *)(a3 + 112) == 1 )
  {
    if ( !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128) )
      goto LABEL_14;
    goto LABEL_9;
  }
LABEL_13:
  EnumValues = QueryEnumValues(a1, (__int64)a2, a3, a4);
  if ( EnumValues )
    goto LABEL_49;
LABEL_14:
  v9 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  EnumValues = v9;
  if ( v9 )
  {
    v10 = v9;
LABEL_48:
    SaveErrorMessage(v10);
    goto LABEL_49;
  }
  v11 = cbMaxSubKeyLen;
  if ( !cSubKeys || cbMaxSubKeyLen )
  {
    if ( cbMaxSubKeyLen < 0x100 )
      v11 = 2 * cbMaxSubKeyLen;
  }
  else
  {
    v11 = 256;
  }
  cbMaxSubKeyLen = v11 + 1;
  Memory = AllocateMemory(2 * (v11 + 1));
  v12 = Memory;
  if ( !Memory
    || (v13 = lstrlenW(a2), v22 = cbMaxSubKeyLen + 1 + v13, v25[0] = AllocateMemory(2 * v22), (v14 = v25[0]) == 0) )
  {
    EnumValues = 14;
LABEL_47:
    v10 = EnumValues;
    goto LABEL_48;
  }
  EnumValues = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    memset_0(v12, 0, 2LL * cbMaxSubKeyLen);
    EnumValues = RegEnumKeyExW(a1, i, (LPWSTR)v12, &cchName, 0, 0, 0, 0);
    if ( !EnumValues )
    {
      a4[3] = 0;
      a4[1] = 1;
      if ( (*(_BYTE *)(a3 + 112) & 1) != 0 )
      {
        v16 = SearchData((LPCWSTR)v12);
        a4[1] = v16;
        if ( v16 )
        {
          a4[3] = 1;
        }
        else if ( !*(_DWORD *)(a3 + 32) && *(_DWORD *)(a3 + 112) == 1 )
        {
          continue;
        }
      }
      else if ( *(_DWORD *)(a3 + 112) || *(_QWORD *)(a3 + 96) )
      {
        a4[1] = 0;
      }
      StringCopyW(v14, v27, v22);
      StringConcatW(v14, L"\\", v22);
      StringConcatW(v14, v12, v22);
      v17 = a4[1] == 1;
      *a4 = 1;
      if ( v17 && !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128) )
      {
        ++a4[4];
        a4[3] = 0;
        *a4 = 0;
        v18 = o___acrt_iob_func_0(1u);
        ShowMessageEx(v18, 1, 1, L"%s\n", v14);
      }
      if ( *(_DWORD *)(a3 + 32) != 1 )
        continue;
      if ( !RegOpenKeyExW(a1, (LPCWSTR)v12, 0, *(_DWORD *)(a3 + 140) | 0x20019, &hKey) )
      {
        EnumValues = QueryEnumKeys(hKey, v14, a3, a4);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        continue;
      }
    }
    EnumValues = 0;
  }
LABEL_49:
  FreeMemory(&Memory);
  FreeMemory(v25);
  return EnumValues;
}

```

## disassembly

```asm
0x1400055f8  mov     [rsp-8+arg_10], rbx
0x1400055fd  mov     [rsp-8+arg_8], rdx
0x140005602  push    rbp
0x140005603  push    rsi
0x140005604  push    rdi
0x140005605  push    r12
0x140005607  push    r13
0x140005609  push    r14
0x14000560b  push    r15
0x14000560d  lea     rbp, [rsp-27h]
0x140005612  sub     rsp, 90h
0x140005619  xor     r12d, r12d
0x14000561c  mov     rsi, r9
0x14000561f  mov     [rbp+57h+cchName], r12d
0x140005623  mov     rdi, r8
0x140005626  mov     [rbp+57h+cSubKeys], r12d
0x14000562a  mov     r15, rdx
0x14000562d  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x140005631  mov     r13, rcx
0x140005634  mov     [rbp+57h+hKey], r12
0x140005638  mov     [rbp+57h+var_48], r12
0x14000563c  mov     [rbp+57h+var_40], r12
0x140005640  test    rcx, rcx
0x140005643  jz      loc_1400058FD
0x140005649  test    rdx, rdx
0x14000564c  jz      loc_1400058FD
0x140005652  test    r8, r8
0x140005655  jz      loc_1400058FD
0x14000565b  test    r9, r9
0x14000565e  jz      loc_1400058FD
0x140005664  cmp     dword ptr [r9+4], 1
0x140005669  jnz     short loc_140005681
0x14000566b  cmp     dword ptr [r8+70h], 1
0x140005670  jnz     short loc_14000569E
0x140005672  cmp     [r8+60h], r12
0x140005676  jnz     short loc_140005681
0x140005678  cmp     [r8+80h], r12
0x14000567f  jz      short loc_1400056AD
0x140005681  cmp     dword ptr [r8+70h], 1
0x140005686  jnz     short loc_14000569E
0x140005688  cmp     dword ptr [r9+4], 1
0x14000568d  jnz     short loc_1400056AD
0x14000568f  cmp     [r8+60h], r12
0x140005693  jnz     short loc_14000569E
0x140005695  cmp     [r8+80h], r12
0x14000569c  jz      short loc_1400056AD
0x14000569e  call    QueryEnumValues
0x1400056a3  mov     ebx, eax
0x1400056a5  test    eax, eax
0x1400056a7  jnz     loc_140005909
0x1400056ad  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400056b2  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1400056b6  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400056bb  xor     r9d, r9d; lpReserved
0x1400056be  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1400056c3  xor     r8d, r8d; lpcchClass
0x1400056c6  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1400056cb  xor     edx, edx; lpClass
0x1400056cd  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x1400056d2  mov     rcx, r13; hKey
0x1400056d5  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1400056da  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400056df  lea     rax, [rbp+57h+cSubKeys]
0x1400056e3  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x1400056e8  call    cs:__imp_RegQueryInfoKeyW
0x1400056ee  mov     ebx, eax
0x1400056f0  test    eax, eax
0x1400056f2  jz      short loc_1400056FB
0x1400056f4  mov     ecx, eax
0x1400056f6  jmp     loc_140005904
0x1400056fb  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1400056fe  cmp     [rbp+57h+cSubKeys], r12d
0x140005702  jz      short loc_14000570F
0x140005704  test    ecx, ecx
0x140005706  jnz     short loc_14000570F
0x140005708  mov     ecx, 100h
0x14000570d  jmp     short loc_140005719
0x14000570f  cmp     ecx, 100h
0x140005715  jnb     short loc_140005719
0x140005717  add     ecx, ecx
0x140005719  inc     ecx
0x14000571b  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x14000571e  add     ecx, ecx; dwBytes
0x140005720  call    AllocateMemory
0x140005725  mov     [rbp+57h+var_48], rax
0x140005729  mov     r14, rax
0x14000572c  test    rax, rax
0x14000572f  jnz     short loc_14000573B
0x140005731  mov     ebx, 0Eh
0x140005736  jmp     loc_140005902
0x14000573b  mov     rcx, r15; lpString
0x14000573e  call    cs:__imp_lstrlenW
0x140005744  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x140005747  inc     ecx
0x140005749  add     eax, ecx
0x14000574b  mov     [rbp+57h+var_58], eax
0x14000574e  lea     ecx, [rax+rax]; dwBytes
0x140005751  call    AllocateMemory
0x140005756  mov     [rbp+57h+var_40], rax
0x14000575a  mov     r12, rax
0x14000575d  test    rax, rax
0x140005760  jz      short loc_140005731
0x140005762  xor     ebx, ebx
0x140005764  xor     r15d, r15d
0x140005767  cmp     [rbp+57h+cSubKeys], ebx
0x14000576a  jbe     loc_140005909
0x140005770  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140005773  xor     edx, edx; Val
0x140005775  mov     r8d, eax
0x140005778  mov     [rbp+57h+cchName], eax
0x14000577b  add     r8, r8; Size
0x14000577e  mov     rcx, r14; void *
0x140005781  call    memset_0
0x140005786  xor     eax, eax
0x140005788  lea     r9, [rbp+57h+cchName]; lpcchName
0x14000578c  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x140005791  mov     r8, r14; lpName
0x140005794  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpcchClass
0x140005799  mov     edx, r15d; dwIndex
0x14000579c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpClass
0x1400057a1  mov     rcx, r13; hKey
0x1400057a4  mov     [rsp+0C0h+lpcSubKeys], rax; lpReserved
0x1400057a9  call    cs:__imp_RegEnumKeyExW
0x1400057af  xor     ecx, ecx
0x1400057b1  mov     ebx, eax
0x1400057b3  test    eax, eax
0x1400057b5  jnz     loc_1400058EC
0x1400057bb  lea     eax, [rbx+1]
0x1400057be  mov     [rsi+0Ch], ecx
0x1400057c1  mov     [rsi+4], eax
0x1400057c4  test    [rdi+70h], al
0x1400057c7  jz      short loc_140005800
0x1400057c9  mov     r8d, [rbp+57h+cchName]
0x1400057cd  mov     r9, rdi
0x1400057d0  add     r8d, r8d
0x1400057d3  mov     edx, eax
0x1400057d5  mov     rcx, r14; lpString
0x1400057d8  call    SearchData
0x1400057dd  xor     ecx, ecx
0x1400057df  mov     [rsi+4], eax
0x1400057e2  test    eax, eax
0x1400057e4  jnz     short loc_1400057F7
0x1400057e6  cmp     [rdi+20h], ecx
0x1400057e9  jnz     short loc_14000580E
0x1400057eb  cmp     dword ptr [rdi+70h], 1
0x1400057ef  jz      loc_1400058EE
0x1400057f5  jmp     short loc_14000580E
0x1400057f7  mov     dword ptr [rsi+0Ch], 1
0x1400057fe  jmp     short loc_14000580E
0x140005800  cmp     [rdi+70h], ecx
0x140005803  jnz     short loc_14000580B
0x140005805  cmp     [rdi+60h], rcx
0x140005809  jz      short loc_14000580E
0x14000580b  mov     [rsi+4], ecx
0x14000580e  mov     r8d, [rbp+57h+var_58]
0x140005812  mov     rcx, r12
0x140005815  mov     rdx, [rbp+57h+arg_8]
0x140005819  call    StringCopyW
0x14000581e  mov     r8d, [rbp+57h+var_58]
0x140005822  lea     rdx, asc_14001081C; "\\"
0x140005829  mov     rcx, r12
0x14000582c  call    StringConcatW
0x140005831  mov     r8d, [rbp+57h+var_58]
0x140005835  mov     rdx, r14
0x140005838  mov     rcx, r12
0x14000583b  call    StringConcatW
0x140005840  cmp     dword ptr [rsi+4], 1
0x140005844  mov     dword ptr [rsi], 1
0x14000584a  jnz     short loc_14000588D
0x14000584c  xor     ecx, ecx
0x14000584e  cmp     [rdi+60h], rcx
0x140005852  jnz     short loc_14000588D
0x140005854  cmp     [rdi+80h], rcx
0x14000585b  jnz     short loc_14000588D
0x14000585d  inc     dword ptr [rsi+10h]
0x140005860  mov     [rsi+0Ch], ecx
0x140005863  mov     [rsi], ecx
0x140005865  mov     ecx, 1; Ix
0x14000586a  call    _o___acrt_iob_func_0
0x14000586f  mov     rcx, rax
0x140005872  mov     [rsp+0C0h+lpcSubKeys], r12
0x140005877  mov     eax, 1
0x14000587c  lea     r9, aS_5; "%s\n"
0x140005883  mov     r8d, eax
0x140005886  mov     edx, eax
0x140005888  call    ShowMessageEx
0x14000588d  cmp     dword ptr [rdi+20h], 1
0x140005891  jnz     short loc_1400058EE
0x140005893  mov     r9d, [rdi+8Ch]
0x14000589a  lea     rax, [rbp+57h+hKey]
0x14000589e  or      r9d, 20019h; samDesired
0x1400058a5  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x1400058aa  xor     r8d, r8d; ulOptions
0x1400058ad  mov     rdx, r14; lpSubKey
0x1400058b0  mov     rcx, r13; hKey
0x1400058b3  call    cs:__imp_RegOpenKeyExW
0x1400058b9  xor     ecx, ecx
0x1400058bb  test    eax, eax
0x1400058bd  jnz     short loc_1400058EC
0x1400058bf  mov     rcx, [rbp+57h+hKey]
0x1400058c3  mov     r9, rsi
0x1400058c6  mov     r8, rdi
0x1400058c9  mov     rdx, r12
0x1400058cc  call    QueryEnumKeys
0x1400058d1  mov     rcx, [rbp+57h+hKey]; hKey
0x1400058d5  mov     ebx, eax
0x1400058d7  test    rcx, rcx
0x1400058da  jz      short loc_1400058EE
0x1400058dc  call    cs:__imp_RegCloseKey
0x1400058e2  mov     [rbp+57h+hKey], 0
0x1400058ea  jmp     short loc_1400058EE
0x1400058ec  mov     ebx, ecx
0x1400058ee  inc     r15d
0x1400058f1  cmp     r15d, [rbp+57h+cSubKeys]
0x1400058f5  jb      loc_140005770
0x1400058fb  jmp     short loc_140005909
0x1400058fd  mov     ebx, 57h ; 'W'
0x140005902  mov     ecx, ebx
0x140005904  call    SaveErrorMessage
0x140005909  lea     rcx, [rbp+57h+var_48]
0x14000590d  call    FreeMemory
0x140005912  lea     rcx, [rbp+57h+var_40]
0x140005916  call    FreeMemory
0x14000591b  mov     eax, ebx
0x14000591d  mov     rbx, [rsp+0C0h+arg_10]
0x140005925  add     rsp, 90h
0x14000592c  pop     r15
0x14000592e  pop     r14
0x140005930  pop     r13
0x140005932  pop     r12
0x140005934  pop     rdi
0x140005935  pop     rsi
0x140005936  pop     rbp
0x140005937  retn
```
