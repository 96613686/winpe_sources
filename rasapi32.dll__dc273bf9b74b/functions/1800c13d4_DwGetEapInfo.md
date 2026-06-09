# DwGetEapInfo

- ea: `0x1800c13d4`
- end: `0x1800c1561`
- name: `DwGetEapInfo`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c1568`
- `0x1800c19ec`

## callees

- `0x1800c13d4`
- `0x1800c1c78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c1482`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c1482`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c151c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c151c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c14ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c14fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c14ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c14fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c14c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c14c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c14ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c14ce`

## pseudocode

```c
__int64 __fastcall DwGetEapInfo(char *a1, int a2, BYTE **a3, DWORD *a4, HKEY *a5)
{
  BYTE *v8; // rdi
  HKEY v9; // rcx
  unsigned int EapKeyFromToken; // eax
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  DWORD LastError; // eax
  __int64 result; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF

  v8 = 0;
  v9 = 0;
  hKey = 0;
  dwDisposition = 0;
  cbData = 0;
  Type = 0;
  if ( a3 && a4 )
  {
    if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || a2 )
    {
      v12 = L"Software\\Microsoft\\Router EAP\\IfEapInfo";
      if ( !a2 )
        v12 = L"Software\\Microsoft\\RAS EAP\\UserEapInfo";
      EapKeyFromToken = RegCreateKeyExW(
                          (HKEY)((a2 != 0) - 0x7FFFFFFFLL),
                          v12,
                          0,
                          0,
                          0,
                          0xF003Fu,
                          0,
                          &hKey,
                          &dwDisposition);
    }
    else
    {
      EapKeyFromToken = lrGetEapKeyFromToken(a1, &hKey);
    }
    v13 = EapKeyFromToken;
    if ( !EapKeyFromToken )
    {
      v13 = RegQueryValueExW(hKey, L"EapInfo", 0, &Type, 0, &cbData);
      if ( !v13 )
      {
        v8 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v8 )
          LastError = RegQueryValueExW(hKey, L"EapInfo", 0, &Type, v8, &cbData);
        else
          LastError = GetLastError();
        v13 = LastError;
      }
    }
    v9 = hKey;
  }
  else
  {
    v13 = -2147024809;
  }
  if ( a5 )
  {
    *a5 = v9;
  }
  else if ( v9 )
  {
    RegCloseKey(v9);
  }
  if ( a3 )
  {
    *a3 = v8;
  }
  else if ( v8 )
  {
    LocalFree(v8);
  }
  if ( a4 )
    *a4 = cbData;
  result = 0;
  if ( v13 != 2 )
    return v13;
  return result;
}

```

## disassembly

```asm
0x1800c13d4  mov     [rsp-18h+arg_0], rbx
0x1800c13d9  mov     [rsp-18h+arg_8], rsi
0x1800c13de  push    rbp
0x1800c13df  push    rdi
0x1800c13e0  push    r14
0x1800c13e2  mov     rbp, rsp
0x1800c13e5  sub     rsp, 60h
0x1800c13e9  mov     r14, r8
0x1800c13ec  mov     rsi, r9
0x1800c13ef  mov     r9, rcx
0x1800c13f2  xor     edi, edi
0x1800c13f4  xor     ecx, ecx; hKey
0x1800c13f6  mov     r8d, edx
0x1800c13f9  mov     [rbp+hKey], rcx
0x1800c13fd  mov     [rbp+dwDisposition], ecx
0x1800c1400  mov     [rbp+cbData], ecx
0x1800c1403  mov     [rbp+Type], ecx
0x1800c1406  test    r14, r14
0x1800c1409  jz      loc_1800C1504
0x1800c140f  test    rsi, rsi
0x1800c1412  jz      loc_1800C1504
0x1800c1418  lea     rax, [r9-1]
0x1800c141c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c1420  ja      short loc_1800C1434
0x1800c1422  test    edx, edx
0x1800c1424  jnz     short loc_1800C1434
0x1800c1426  lea     rdx, [rbp+hKey]
0x1800c142a  mov     rcx, r9
0x1800c142d  call    lrGetEapKeyFromToken
0x1800c1432  jmp     short loc_1800C1488
0x1800c1434  test    r8d, r8d
0x1800c1437  lea     rax, aSoftwareMicros_6; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x1800c143e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Router EAP\\IfEapI"...
0x1800c1445  cmovz   rdx, rax; lpSubKey
0x1800c1449  neg     r8d
0x1800c144c  lea     rax, [rbp+dwDisposition]
0x1800c1450  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800c1455  sbb     rcx, rcx
0x1800c1458  lea     rax, [rbp+hKey]
0x1800c145c  neg     rcx
0x1800c145f  mov     [rsp+60h+phkResult], rax; phkResult
0x1800c1464  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800c146b  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800c1470  xor     r9d, r9d; lpClass
0x1800c1473  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800c147b  xor     r8d, r8d; Reserved
0x1800c147e  mov     [rsp+60h+dwOptions], edi; dwOptions
0x1800c1482  call    cs:__imp_RegCreateKeyExW
0x1800c1488  mov     ebx, eax
0x1800c148a  test    eax, eax
0x1800c148c  jnz     short loc_1800C14D6
0x1800c148e  mov     rcx, [rbp+hKey]; hKey
0x1800c1492  lea     rax, [rbp+cbData]
0x1800c1496  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x1800c149b  lea     r9, [rbp+Type]; lpType
0x1800c149f  xor     r8d, r8d; lpReserved
0x1800c14a2  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800c14a7  lea     rdx, aEapinfo; "EapInfo"
0x1800c14ae  call    cs:__imp_RegQueryValueExW
0x1800c14b4  mov     ebx, eax
0x1800c14b6  test    eax, eax
0x1800c14b8  jnz     short loc_1800C14D6
0x1800c14ba  mov     edx, [rbp+cbData]; uBytes
0x1800c14bd  lea     ecx, [rax+40h]; uFlags
0x1800c14c0  call    cs:__imp_LocalAlloc
0x1800c14c6  mov     rdi, rax
0x1800c14c9  test    rax, rax
0x1800c14cc  jnz     short loc_1800C14DC
0x1800c14ce  call    cs:__imp_GetLastError
0x1800c14d4  mov     ebx, eax
0x1800c14d6  mov     rcx, [rbp+hKey]
0x1800c14da  jmp     short loc_1800C1509
0x1800c14dc  mov     rcx, [rbp+hKey]; hKey
0x1800c14e0  lea     rax, [rbp+cbData]
0x1800c14e4  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x1800c14e9  lea     r9, [rbp+Type]; lpType
0x1800c14ed  xor     r8d, r8d; lpReserved
0x1800c14f0  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800c14f5  lea     rdx, aEapinfo; "EapInfo"
0x1800c14fc  call    cs:__imp_RegQueryValueExW
0x1800c1502  jmp     short loc_1800C14D4
0x1800c1504  mov     ebx, 80070057h
0x1800c1509  mov     rax, [rbp+arg_20]
0x1800c150d  test    rax, rax
0x1800c1510  jz      short loc_1800C1517
0x1800c1512  mov     [rax], rcx
0x1800c1515  jmp     short loc_1800C1522
0x1800c1517  test    rcx, rcx
0x1800c151a  jz      short loc_1800C1522
0x1800c151c  call    cs:__imp_RegCloseKey
0x1800c1522  test    r14, r14
0x1800c1525  jz      short loc_1800C152C
0x1800c1527  mov     [r14], rdi
0x1800c152a  jmp     short loc_1800C153A
0x1800c152c  test    rdi, rdi
0x1800c152f  jz      short loc_1800C153A
0x1800c1531  mov     rcx, rdi; hMem
0x1800c1534  call    cs:__imp_LocalFree
0x1800c153a  test    rsi, rsi
0x1800c153d  jz      short loc_1800C1544
0x1800c153f  mov     eax, [rbp+cbData]
0x1800c1542  mov     [rsi], eax
0x1800c1544  xor     eax, eax
0x1800c1546  lea     r11, [rsp+60h+var_s0]
0x1800c154b  mov     rsi, [r11+28h]
0x1800c154f  cmp     ebx, 2
0x1800c1552  cmovnz  eax, ebx
0x1800c1555  mov     rbx, [r11+20h]
0x1800c1559  mov     rsp, r11
0x1800c155c  pop     r14
0x1800c155e  pop     rdi
0x1800c155f  pop     rbp
0x1800c1560  retn
```
