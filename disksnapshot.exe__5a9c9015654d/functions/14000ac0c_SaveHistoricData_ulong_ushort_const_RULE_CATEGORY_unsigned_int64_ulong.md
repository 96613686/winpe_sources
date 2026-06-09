# SaveHistoricData(ulong,ushort const *,RULE_CATEGORY,unsigned __int64,ulong)

- ea: `0x14000ac0c`
- end: `0x14000ae53`
- name: `?SaveHistoricData@@YAJKPEBGW4RULE_CATEGORY@@_KK@Z`
- size: `583`
- prototype: `__int64(int, WCHAR *, int, __int64, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008a38`

## callees

- `0x140001c50`
- `0x1400027d2`
- `0x1400089ac`
- `0x14000ac0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ae2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ae2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000ad80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000ad80`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000adb4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ade2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ae0b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000adb4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ade2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ae0b`

## pseudocode

```c
__int64 SaveHistoricData(int a1, WCHAR *a2, int a3, __int64 a4, ...)
{
  __int64 v7; // rdx
  WCHAR *v8; // r8
  __int64 v9; // rax
  WCHAR *v10; // rcx
  signed int v11; // ebx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  LSTATUS v15; // eax
  bool v16; // cc
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Data; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v21[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  va_list va; // [rsp+4F0h] [rbp+3F0h] BYREF

  va_start(va, a4);
  Data = a4;
  hKey = 0;
  memset_0(v21, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  v19 = a3;
  v7 = 260;
  v8 = v21;
  v9 = 2147483646;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v8++ = *a2++;
    --v9;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  v11 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  if ( v7 )
  {
    v12 = -1;
    v13 = 0;
    do
      ++v12;
    while ( v21[v12] );
    if ( v12 )
    {
      do
      {
        if ( v21[v13] == 92 )
          v21[v13] = 63;
        ++v13;
        v14 = -1;
        do
          ++v14;
        while ( v21[v14] );
      }
      while ( v13 < v14 );
    }
    v11 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%i\\%s", L"SOFTWARE\\Microsoft\\DiskSnapshot\\v2", a1, v21);
    if ( v11 >= 0 )
    {
      v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v16 = v15 <= 0;
      if ( v15
        || (v15 = RegSetKeyValueW(hKey, 0, L"Size", 0xBu, &Data, 8u), v16 = v15 <= 0, v15)
        || (v15 = RegSetKeyValueW(hKey, 0, L"Count", 4u, va, 4u), v16 = v15 <= 0, v15)
        || (v15 = RegSetKeyValueW(hKey, 0, L"Category", 4u, &v19, 4u), v16 = v15 <= 0, v15) )
      {
        if ( v16 )
          v11 = v15;
        else
          v11 = (unsigned __int16)v15 | 0x80070000;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000ac0c  push    rbp
0x14000ac0e  push    rbx
0x14000ac0f  push    rsi
0x14000ac10  push    rdi
0x14000ac11  push    r15
0x14000ac13  lea     rbp, [rsp-3A0h]
0x14000ac1b  sub     rsp, 4A0h
0x14000ac22  mov     rax, cs:__security_cookie
0x14000ac29  xor     rax, rsp
0x14000ac2c  mov     [rbp+3C0h+var_30], rax
0x14000ac33  mov     ebx, r8d
0x14000ac36  mov     [rsp+4C0h+Data], r9
0x14000ac3b  mov     rdi, rdx
0x14000ac3e  mov     esi, ecx
0x14000ac40  xor     r15d, r15d
0x14000ac43  lea     rcx, [rsp+4C0h+var_450]; void *
0x14000ac48  xor     edx, edx; Val
0x14000ac4a  mov     [rsp+4C0h+hKey], r15
0x14000ac4f  mov     r8d, 208h; Size
0x14000ac55  call    memset_0
0x14000ac5a  xor     edx, edx; Val
0x14000ac5c  lea     rcx, [rbp+3C0h+SubKey]; void *
0x14000ac63  mov     r8d, 208h; Size
0x14000ac69  call    memset_0
0x14000ac6e  mov     r10d, 104h
0x14000ac74  mov     [rsp+4C0h+var_468], ebx
0x14000ac78  mov     edx, r10d
0x14000ac7b  lea     r8, [rsp+4C0h+var_450]
0x14000ac80  mov     eax, 7FFFFFFEh
0x14000ac85  test    rax, rax
0x14000ac88  jz      short loc_14000ACA7
0x14000ac8a  movzx   ecx, word ptr [rdi]
0x14000ac8d  test    cx, cx
0x14000ac90  jz      short loc_14000ACA7
0x14000ac92  mov     [r8], cx
0x14000ac96  add     rdi, 2
0x14000ac9a  add     r8, 2
0x14000ac9e  dec     rax
0x14000aca1  sub     rdx, 1
0x14000aca5  jnz     short loc_14000AC85
0x14000aca7  mov     rax, rdx
0x14000acaa  lea     rcx, [r8-2]
0x14000acae  neg     rax
0x14000acb1  sbb     ebx, ebx
0x14000acb3  not     ebx
0x14000acb5  and     ebx, 8007007Ah
0x14000acbb  test    rdx, rdx
0x14000acbe  cmovnz  rcx, r8
0x14000acc2  mov     [rcx], r15w
0x14000acc6  jz      loc_14000AE24
0x14000accc  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000acd0  lea     rdx, [rsp+4C0h+var_450]
0x14000acd5  mov     rcx, r8
0x14000acd8  mov     rax, r15
0x14000acdb  inc     rcx
0x14000acde  cmp     [rdx+rcx*2], r15w
0x14000ace3  jnz     short loc_14000ACDB
0x14000ace5  test    rcx, rcx
0x14000ace8  jz      short loc_14000AD16
0x14000acea  cmp     [rsp+rax*2+4C0h+var_450], 5Ch ; '\'
0x14000acf0  jnz     short loc_14000ACFC
0x14000acf2  mov     ecx, 3Fh ; '?'
0x14000acf7  mov     [rsp+rax*2+4C0h+var_450], cx
0x14000acfc  inc     rax
0x14000acff  lea     rdx, [rsp+4C0h+var_450]
0x14000ad04  mov     rcx, r8
0x14000ad07  inc     rcx
0x14000ad0a  cmp     [rdx+rcx*2], r15w
0x14000ad0f  jnz     short loc_14000AD07
0x14000ad11  cmp     rax, rcx
0x14000ad14  jb      short loc_14000ACEA
0x14000ad16  lea     rax, [rsp+4C0h+var_450]
0x14000ad1b  mov     rdx, r10; unsigned __int64
0x14000ad1e  mov     qword ptr [rsp+4C0h+samDesired], rax
0x14000ad23  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\DiskSnapshot\\v2"
0x14000ad2a  lea     r8, aSIS; "%s\\%i\\%s"
0x14000ad31  mov     [rsp+4C0h+dwOptions], esi
0x14000ad35  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x14000ad3c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ad41  mov     ebx, eax
0x14000ad43  test    eax, eax
0x14000ad45  js      loc_14000AE24
0x14000ad4b  mov     [rsp+4C0h+lpdwDisposition], r15; lpdwDisposition
0x14000ad50  lea     rax, [rsp+4C0h+hKey]
0x14000ad55  mov     [rsp+4C0h+phkResult], rax; phkResult
0x14000ad5a  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x14000ad61  mov     [rsp+4C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14000ad66  xor     r9d, r9d; lpClass
0x14000ad69  mov     [rsp+4C0h+samDesired], 20006h; samDesired
0x14000ad71  xor     r8d, r8d; Reserved
0x14000ad74  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ad7b  mov     [rsp+4C0h+dwOptions], r15d; dwOptions
0x14000ad80  call    cs:__imp_RegCreateKeyExW
0x14000ad86  test    eax, eax
0x14000ad88  jnz     loc_14000AE15
0x14000ad8e  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000ad93  lea     rax, [rsp+4C0h+Data]
0x14000ad98  mov     [rsp+4C0h+samDesired], 8; cbData
0x14000ada0  lea     r8, ValueName; "Size"
0x14000ada7  mov     r9d, 0Bh; dwType
0x14000adad  mov     qword ptr [rsp+4C0h+dwOptions], rax; lpData
0x14000adb2  xor     edx, edx; lpSubKey
0x14000adb4  call    cs:__imp_RegSetKeyValueW
0x14000adba  test    eax, eax
0x14000adbc  jnz     short loc_14000AE15
0x14000adbe  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000adc3  lea     edi, [rax+4]
0x14000adc6  lea     rax, [rbp+3C0h+arg_20]
0x14000adcd  mov     [rsp+4C0h+samDesired], edi; cbData
0x14000add1  mov     r9d, edi; dwType
0x14000add4  mov     qword ptr [rsp+4C0h+dwOptions], rax; lpData
0x14000add9  lea     r8, aCount; "Count"
0x14000ade0  xor     edx, edx; lpSubKey
0x14000ade2  call    cs:__imp_RegSetKeyValueW
0x14000ade8  test    eax, eax
0x14000adea  jnz     short loc_14000AE15
0x14000adec  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000adf1  lea     rax, [rsp+4C0h+var_468]
0x14000adf6  mov     [rsp+4C0h+samDesired], edi; cbData
0x14000adfa  lea     r8, aCategory; "Category"
0x14000ae01  mov     r9d, edi; dwType
0x14000ae04  mov     qword ptr [rsp+4C0h+dwOptions], rax; lpData
0x14000ae09  xor     edx, edx; lpSubKey
0x14000ae0b  call    cs:__imp_RegSetKeyValueW
0x14000ae11  test    eax, eax
0x14000ae13  jz      short loc_14000AE24
0x14000ae15  jg      short loc_14000AE1B
0x14000ae17  mov     ebx, eax
0x14000ae19  jmp     short loc_14000AE24
0x14000ae1b  movzx   ebx, ax
0x14000ae1e  or      ebx, 80070000h
0x14000ae24  mov     rcx, [rsp+4C0h+hKey]; hKey
0x14000ae29  test    rcx, rcx
0x14000ae2c  jz      short loc_14000AE34
0x14000ae2e  call    cs:__imp_RegCloseKey
0x14000ae34  mov     eax, ebx
0x14000ae36  mov     rcx, [rbp+3C0h+var_30]
0x14000ae3d  xor     rcx, rsp; StackCookie
0x14000ae40  call    __security_check_cookie
0x14000ae45  add     rsp, 4A0h
0x14000ae4c  pop     r15
0x14000ae4e  pop     rdi
0x14000ae4f  pop     rsi
0x14000ae50  pop     rbx
0x14000ae51  pop     rbp
0x14000ae52  retn
```
