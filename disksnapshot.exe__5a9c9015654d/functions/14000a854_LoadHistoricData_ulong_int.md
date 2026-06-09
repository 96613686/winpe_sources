# LoadHistoricData(ulong,int &)

- ea: `0x14000a854`
- end: `0x14000ac04`
- name: `?LoadHistoricData@@YAJKAEAH@Z`
- size: `944`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400082d0`

## callees

- `0x140001c50`
- `0x1400027d2`
- `0x1400089ac`
- `0x14000a854`
- `0x14000b144`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000aa82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000aa82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000abd5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000a96d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ab99`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000a96d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ab99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a9e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000aa2c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000aa6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a9e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000aa2c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000aa6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a927`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a9a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a927`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a9a6`

## pseudocode

```c
__int64 __fastcall LoadHistoricData(int a1, int *a2)
{
  int v4; // ebx
  LSTATUS ValueW; // eax
  bool v6; // cc
  DWORD v7; // edi
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  _QWORD *v11; // r11
  _QWORD *i; // rax
  HCRYPTHASH v13; // r9
  _QWORD *v14; // rcx
  char *v15; // r10
  int v16; // edx
  int v17; // r8d
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HCRYPTHASH v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 pvData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+290h] [rbp+190h] BYREF

  hKey = 0;
  hkey = 0;
  memset_0(SubKey, 0, 0x208u);
  memset_0(Name, 0, 0x208u);
  cchName = 0;
  pvData = 0;
  v25 = 0;
  v22 = 0;
  pcbData = 0;
  *a2 = 1;
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%i", L"SOFTWARE\\Microsoft\\DiskSnapshot\\v2", a1);
  if ( v4 >= 0 )
  {
    ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    if ( ValueW == 2 )
    {
      *a2 = 0;
      goto LABEL_35;
    }
    v6 = ValueW <= 0;
    if ( !ValueW )
    {
      v7 = 0;
      cchName = 260;
      ValueW = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( ValueW == 259 )
        goto LABEL_35;
      while ( 1 )
      {
        v6 = ValueW <= 0;
        if ( ValueW )
          break;
        ValueW = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &hkey);
        v6 = ValueW <= 0;
        if ( ValueW )
          break;
        pcbData = 8;
        ValueW = RegGetValueW(hkey, 0, L"Size", 0x48u, 0, &pvData, &pcbData);
        v6 = ValueW <= 0;
        if ( ValueW )
          break;
        pcbData = 4;
        ValueW = RegGetValueW(hkey, 0, L"Count", 0x18u, 0, &v22, &pcbData);
        v6 = ValueW <= 0;
        if ( ValueW )
          break;
        pcbData = 8;
        ValueW = RegGetValueW(hkey, 0, L"Category", 0x18u, 0, &v25, &pcbData);
        v6 = ValueW <= 0;
        if ( ValueW )
          break;
        RegCloseKey(hkey);
        v8 = 0;
        hkey = 0;
        v9 = -1;
        do
          ++v9;
        while ( Name[v9] );
        if ( v9 )
        {
          do
          {
            if ( Name[v8] == 63 )
              Name[v8] = 92;
            ++v8;
            v10 = -1;
            do
              ++v10;
            while ( Name[v10] );
          }
          while ( v8 < v10 );
        }
        v11 = *(_QWORD **)g_Rules;
        for ( i = **(_QWORD ***)g_Rules; ; i = (_QWORD *)*i )
        {
          v24 = 0;
          if ( i == v11 )
            break;
          v13 = i[2];
          v14 = *(_QWORD **)(v13 + 32);
          if ( v14[3] > 7u )
            v14 = (_QWORD *)*v14;
          v15 = (char *)((char *)Name - (char *)v14);
          do
          {
            v16 = *(unsigned __int16 *)&v15[(_QWORD)v14];
            v17 = *(unsigned __int16 *)v14 - v16;
            if ( v17 )
              break;
            v14 = (_QWORD *)((char *)v14 + 2);
          }
          while ( v16 );
          if ( !v17 )
            goto LABEL_30;
        }
        v4 = CreateBucket(Name, v25, L"*", 0, 0, 2, &v24);
        if ( v4 < 0 )
          goto LABEL_35;
        v13 = v24;
LABEL_30:
        *(_QWORD *)(v13 + 16) = pvData;
        ++v7;
        *(_DWORD *)(v13 + 24) = v22;
        cchName = 260;
        ValueW = RegEnumKeyExW(hKey, v7, Name, &cchName, 0, 0, 0, 0);
        if ( ValueW == 259 )
          goto LABEL_35;
      }
    }
    if ( v6 )
      v4 = ValueW;
    else
      v4 = (unsigned __int16)ValueW | 0x80070000;
  }
LABEL_35:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000a854  mov     [rsp-8+arg_10], rbx
0x14000a859  mov     [rsp-8+arg_18], rsi
0x14000a85e  push    rbp
0x14000a85f  push    rdi
0x14000a860  push    r14
0x14000a862  lea     rbp, [rsp-3B0h]
0x14000a86a  sub     rsp, 4B0h
0x14000a871  mov     rax, cs:__security_cookie
0x14000a878  xor     rax, rsp
0x14000a87b  mov     [rbp+3C0h+var_20], rax
0x14000a882  mov     rdi, rdx
0x14000a885  mov     ebx, ecx
0x14000a887  xor     r14d, r14d
0x14000a88a  lea     rcx, [rbp+3C0h+SubKey]; void *
0x14000a891  mov     esi, 208h
0x14000a896  mov     [rsp+4C0h+hKey], r14
0x14000a89b  mov     r8d, esi; Size
0x14000a89e  mov     [rsp+4C0h+hkey], r14
0x14000a8a3  xor     edx, edx; Val
0x14000a8a5  call    memset_0
0x14000a8aa  mov     r8d, esi; Size
0x14000a8ad  lea     rcx, [rbp+3C0h+Name]; void *
0x14000a8b1  xor     edx, edx; Val
0x14000a8b3  call    memset_0
0x14000a8b8  mov     esi, 104h
0x14000a8bd  mov     [rsp+4C0h+cchName], r14d
0x14000a8c2  mov     edx, esi; unsigned __int64
0x14000a8c4  mov     [rsp+4C0h+pvData], r14
0x14000a8c9  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\DiskSnapshot\\v2"
0x14000a8d0  mov     [rsp+4C0h+var_458], r14
0x14000a8d5  lea     r8, aSI; "%s\\%i"
0x14000a8dc  mov     [rsp+4C0h+var_470], r14d
0x14000a8e1  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x14000a8e8  mov     [rsp+4C0h+pcbData], r14d
0x14000a8ed  mov     dword ptr [rdi], 1
0x14000a8f3  mov     dword ptr [rsp+4C0h+phkResult], ebx
0x14000a8f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a8fc  mov     ebx, eax
0x14000a8fe  test    eax, eax
0x14000a900  js      loc_14000ABBB
0x14000a906  lea     rax, [rsp+4C0h+hKey]
0x14000a90b  mov     r9d, 20019h; samDesired
0x14000a911  xor     r8d, r8d; ulOptions
0x14000a914  mov     [rsp+4C0h+phkResult], rax; phkResult
0x14000a919  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x14000a920  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a927  call    cs:__imp_RegOpenKeyExW
0x14000a92d  cmp     eax, 2
0x14000a930  jnz     short loc_14000A93A
0x14000a932  mov     [rdi], r14d
0x14000a935  jmp     loc_14000ABBB
0x14000a93a  test    eax, eax
0x14000a93c  jnz     loc_14000ABAC
0x14000a942  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000a947  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x14000a94c  mov     [rsp+4C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14000a951  lea     r8, [rbp+3C0h+Name]; lpName
0x14000a955  mov     [rsp+4C0h+lpcchClass], r14; lpcchClass
0x14000a95a  xor     edx, edx; dwIndex
0x14000a95c  mov     [rsp+4C0h+lpClass], r14; lpClass
0x14000a961  mov     edi, r14d
0x14000a964  mov     [rsp+4C0h+phkResult], r14; lpReserved
0x14000a969  mov     [rsp+4C0h+cchName], esi
0x14000a96d  call    cs:__imp_RegEnumKeyExW
0x14000a973  cmp     eax, 103h
0x14000a978  jz      loc_14000ABBB
0x14000a97e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000a982  test    eax, eax
0x14000a984  jnz     loc_14000ABAC
0x14000a98a  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000a98f  lea     rax, [rsp+4C0h+hkey]
0x14000a994  mov     r9d, 20019h; samDesired
0x14000a99a  mov     [rsp+4C0h+phkResult], rax; phkResult
0x14000a99f  xor     r8d, r8d; ulOptions
0x14000a9a2  lea     rdx, [rbp+3C0h+Name]; lpSubKey
0x14000a9a6  call    cs:__imp_RegOpenKeyExW
0x14000a9ac  test    eax, eax
0x14000a9ae  jnz     loc_14000ABAC
0x14000a9b4  mov     rcx, [rsp+4C0h+hkey]; hkey
0x14000a9b9  lea     rax, [rsp+4C0h+pcbData]
0x14000a9be  mov     [rsp+4C0h+lpcchClass], rax; pcbData
0x14000a9c3  lea     r8, ValueName; "Size"
0x14000a9ca  lea     rax, [rsp+4C0h+pvData]
0x14000a9cf  mov     [rsp+4C0h+pcbData], 8
0x14000a9d7  mov     [rsp+4C0h+lpClass], rax; pvData
0x14000a9dc  mov     r9d, 48h ; 'H'; dwFlags
0x14000a9e2  xor     edx, edx; lpSubKey
0x14000a9e4  mov     [rsp+4C0h+phkResult], r14; pdwType
0x14000a9e9  call    cs:__imp_RegGetValueW
0x14000a9ef  test    eax, eax
0x14000a9f1  jnz     loc_14000ABAC
0x14000a9f7  mov     rcx, [rsp+4C0h+hkey]; hkey
0x14000a9fc  lea     rax, [rsp+4C0h+pcbData]
0x14000aa01  mov     [rsp+4C0h+lpcchClass], rax; pcbData
0x14000aa06  lea     r8, aCount; "Count"
0x14000aa0d  lea     rax, [rsp+4C0h+var_470]
0x14000aa12  mov     [rsp+4C0h+pcbData], 4
0x14000aa1a  mov     [rsp+4C0h+lpClass], rax; pvData
0x14000aa1f  mov     r9d, 18h; dwFlags
0x14000aa25  xor     edx, edx; lpSubKey
0x14000aa27  mov     [rsp+4C0h+phkResult], r14; pdwType
0x14000aa2c  call    cs:__imp_RegGetValueW
0x14000aa32  test    eax, eax
0x14000aa34  jnz     loc_14000ABAC
0x14000aa3a  mov     rcx, [rsp+4C0h+hkey]; hkey
0x14000aa3f  lea     rax, [rsp+4C0h+pcbData]
0x14000aa44  mov     [rsp+4C0h+lpcchClass], rax; pcbData
0x14000aa49  lea     r8, aCategory; "Category"
0x14000aa50  lea     rax, [rsp+4C0h+var_458]
0x14000aa55  mov     [rsp+4C0h+pcbData], 8
0x14000aa5d  mov     [rsp+4C0h+lpClass], rax; pvData
0x14000aa62  mov     r9d, 18h; dwFlags
0x14000aa68  xor     edx, edx; lpSubKey
0x14000aa6a  mov     [rsp+4C0h+phkResult], r14; pdwType
0x14000aa6f  call    cs:__imp_RegGetValueW
0x14000aa75  test    eax, eax
0x14000aa77  jnz     loc_14000ABAC
0x14000aa7d  mov     rcx, [rsp+4C0h+hkey]; hKey
0x14000aa82  call    cs:__imp_RegCloseKey
0x14000aa88  mov     rax, r14
0x14000aa8b  mov     [rsp+4C0h+hkey], r14
0x14000aa90  lea     rdx, [rbp+3C0h+Name]
0x14000aa94  mov     rcx, rsi
0x14000aa97  inc     rcx
0x14000aa9a  cmp     [rdx+rcx*2], r14w
0x14000aa9f  jnz     short loc_14000AA97
0x14000aaa1  test    rcx, rcx
0x14000aaa4  jz      short loc_14000AAD1
0x14000aaa6  cmp     [rbp+rax*2+3C0h+Name], 3Fh ; '?'
0x14000aaac  jnz     short loc_14000AAB8
0x14000aaae  mov     ecx, 5Ch ; '\'
0x14000aab3  mov     [rbp+rax*2+3C0h+Name], cx
0x14000aab8  inc     rax
0x14000aabb  lea     rdx, [rbp+3C0h+Name]
0x14000aabf  mov     rcx, rsi
0x14000aac2  inc     rcx
0x14000aac5  cmp     [rdx+rcx*2], r14w
0x14000aaca  jnz     short loc_14000AAC2
0x14000aacc  cmp     rax, rcx
0x14000aacf  jb      short loc_14000AAA6
0x14000aad1  mov     rax, cs:?g_Rules@@3PEAV?$list@PEAU_RULE_BUCKET@@V?$allocator@PEAU_RULE_BUCKET@@@std@@@std@@EA; std::list<_RULE_BUCKET *> * g_Rules
0x14000aad8  mov     r11, [rax]
0x14000aadb  mov     rax, [r11]
0x14000aade  mov     [rsp+4C0h+var_460], r14
0x14000aae3  cmp     rax, r11
0x14000aae6  jz      short loc_14000AB21
0x14000aae8  mov     r9, [rax+10h]
0x14000aaec  mov     rcx, [r9+20h]
0x14000aaf0  cmp     qword ptr [rcx+18h], 7
0x14000aaf5  jbe     short loc_14000AAFA
0x14000aaf7  mov     rcx, [rcx]
0x14000aafa  lea     r10, [rbp+3C0h+Name]
0x14000aafe  sub     r10, rcx
0x14000ab01  movzx   r8d, word ptr [rcx]
0x14000ab05  movzx   edx, word ptr [rcx+r10]
0x14000ab0a  sub     r8d, edx
0x14000ab0d  jnz     short loc_14000AB17
0x14000ab0f  add     rcx, 2
0x14000ab13  test    edx, edx
0x14000ab15  jnz     short loc_14000AB01
0x14000ab17  test    r8d, r8d
0x14000ab1a  jz      short loc_14000AB5A
0x14000ab1c  mov     rax, [rax]
0x14000ab1f  jmp     short loc_14000AADE
0x14000ab21  mov     edx, dword ptr [rsp+4C0h+var_458]
0x14000ab25  lea     rax, [rsp+4C0h+var_460]
0x14000ab2a  mov     [rsp+4C0h+lpcchClass], rax
0x14000ab2f  lea     r8, asc_14000FDDC; "*"
0x14000ab36  mov     dword ptr [rsp+4C0h+lpClass], 2
0x14000ab3e  lea     rcx, [rbp+3C0h+Name]
0x14000ab42  xor     r9d, r9d
0x14000ab45  mov     [rsp+4C0h+phkResult], r14
0x14000ab4a  call    ?CreateBucket@@YAJPEBGW4RULE_CATEGORY@@000W4RULE_TYPE@@PEAPEAU_RULE_BUCKET@@@Z; CreateBucket(ushort const *,RULE_CATEGORY,ushort const *,ushort const *,ushort const *,RULE_TYPE,_RULE_BUCKET * *)
0x14000ab4f  mov     ebx, eax
0x14000ab51  test    eax, eax
0x14000ab53  js      short loc_14000ABBB
0x14000ab55  mov     r9, [rsp+4C0h+var_460]
0x14000ab5a  mov     rax, [rsp+4C0h+pvData]
0x14000ab5f  lea     r8, [rbp+3C0h+Name]; lpName
0x14000ab63  mov     [r9+10h], rax
0x14000ab67  inc     edi
0x14000ab69  mov     eax, [rsp+4C0h+var_470]
0x14000ab6d  mov     edx, edi; dwIndex
0x14000ab6f  mov     [r9+18h], eax
0x14000ab73  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x14000ab78  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000ab7d  mov     [rsp+4C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14000ab82  mov     [rsp+4C0h+lpcchClass], r14; lpcchClass
0x14000ab87  mov     [rsp+4C0h+lpClass], r14; lpClass
0x14000ab8c  mov     [rsp+4C0h+cchName], 104h
0x14000ab94  mov     [rsp+4C0h+phkResult], r14; lpReserved
0x14000ab99  call    cs:__imp_RegEnumKeyExW
0x14000ab9f  cmp     eax, 103h
0x14000aba4  jnz     loc_14000A982
0x14000abaa  jmp     short loc_14000ABBB
0x14000abac  jg      short loc_14000ABB2
0x14000abae  mov     ebx, eax
0x14000abb0  jmp     short loc_14000ABBB
0x14000abb2  movzx   ebx, ax
0x14000abb5  or      ebx, 80070000h
0x14000abbb  mov     rcx, [rsp+4C0h+hkey]; hKey
0x14000abc0  test    rcx, rcx
0x14000abc3  jz      short loc_14000ABCB
0x14000abc5  call    cs:__imp_RegCloseKey
0x14000abcb  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000abd0  test    rcx, rcx
0x14000abd3  jz      short loc_14000ABDB
0x14000abd5  call    cs:__imp_RegCloseKey
0x14000abdb  mov     eax, ebx
0x14000abdd  mov     rcx, [rbp+3C0h+var_20]
0x14000abe4  xor     rcx, rsp; StackCookie
0x14000abe7  call    __security_check_cookie
0x14000abec  lea     r11, [rsp+4C0h+var_10]
0x14000abf4  mov     rbx, [r11+30h]
0x14000abf8  mov     rsi, [r11+38h]
0x14000abfc  mov     rsp, r11
0x14000abff  pop     r14
0x14000ac01  pop     rdi
0x14000ac02  pop     rbp
0x14000ac03  retn
```
