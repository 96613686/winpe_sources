# GetLocationList

- ea: `0x18003ef14`
- end: `0x18003f09f`
- name: `GetLocationList`
- size: `395`
- prototype: `void *__fastcall(HKEY hKey, __int64 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003f408`

## callees

- `0x18003b57c`
- `0x18003b5bc`
- `0x18003b6b8`
- `0x18003e940`
- `0x18003ef14`
- `0x18004146c`
- `0x18004d110`

## import_xrefs

- `msvcrt!_wtol` at `0x18003efc2`
- `msvcrt!_wtol` at `0x18003efc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ef7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003efb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ef7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003efb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f01c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f01c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f064`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f04f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f04f`

## pseudocode

```c
void *__fastcall GetLocationList(HKEY hKey, __int64 **a2)
{
  void *result; // rax
  __int64 v5; // rdi
  DWORD v6; // r14d
  DWORD i; // edx
  int v8; // eax
  int v9; // ebx
  _QWORD *LocationNode; // rax
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  int v13; // [rsp+44h] [rbp-3Ch] BYREF
  int v14; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-28h] BYREF
  WCHAR SubKey[12]; // [rsp+60h] [rbp-20h] BYREF

  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList();
  v5 = (__int64)result;
  if ( result )
  {
    if ( !RegOpenKeyExW(hKey, L"Location", 0, 0x20019u, &hKeya) )
    {
      v6 = 0;
      for ( i = 0; ; i = v6 )
      {
        cchName = 12;
        v11 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v11 == 259 )
          break;
        if ( !v11 && !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &phkResult) )
        {
          v8 = _wtol(SubKey);
          v14 = 0;
          v9 = v8;
          GetRegDword(phkResult, L"Prefix", &v14);
          v13 = 0;
          GetRegDword(phkResult, L"Suffix", &v13);
          LocationNode = (_QWORD *)CreateLocationNode(v9, v14, v13);
          if ( LocationNode )
          {
            DtlAddNodeLast(v5, LocationNode);
            RegCloseKey(phkResult);
          }
        }
        ++v6;
      }
      RegCloseKey(hKeya);
    }
    result = DtlDestroyList(*a2, (void (__fastcall *)(__int64))DestroyLocationNode);
    *a2 = (__int64 *)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18003ef14  mov     [rsp-28h+arg_10], rbx
0x18003ef19  push    rbp
0x18003ef1a  push    rsi
0x18003ef1b  push    rdi
0x18003ef1c  push    r14
0x18003ef1e  push    r15
0x18003ef20  mov     rbp, rsp
0x18003ef23  sub     rsp, 80h
0x18003ef2a  mov     rax, cs:__security_cookie
0x18003ef31  xor     rax, rsp
0x18003ef34  mov     [rbp+var_8], rax
0x18003ef38  xor     r15d, r15d
0x18003ef3b  mov     rsi, rdx
0x18003ef3e  mov     [rbp+cchName], r15d
0x18003ef42  mov     rbx, rcx
0x18003ef45  mov     [rbp+hKey], r15
0x18003ef49  mov     [rbp+var_28], r15
0x18003ef4d  call    DtlCreateList
0x18003ef52  mov     rdi, rax
0x18003ef55  test    rax, rax
0x18003ef58  jz      loc_18003F07C
0x18003ef5e  lea     rax, [rbp+hKey]
0x18003ef62  mov     r9d, 20019h; samDesired
0x18003ef68  xor     r8d, r8d; ulOptions
0x18003ef6b  mov     [rsp+80h+phkResult], rax; phkResult
0x18003ef70  lea     rdx, aLocation; "Location"
0x18003ef77  mov     rcx, rbx; hKey
0x18003ef7a  call    cs:__imp_RegOpenKeyExW
0x18003ef80  test    eax, eax
0x18003ef82  jnz     loc_18003F06A
0x18003ef88  mov     r14d, r15d
0x18003ef8b  xor     edx, edx
0x18003ef8d  jmp     loc_18003F028
0x18003ef92  test    eax, eax
0x18003ef94  jnz     loc_18003F022
0x18003ef9a  mov     rcx, [rbp+hKey]; hKey
0x18003ef9e  lea     rax, [rbp+var_28]
0x18003efa2  mov     r9d, 20019h; samDesired
0x18003efa8  mov     [rsp+80h+phkResult], rax; phkResult
0x18003efad  xor     r8d, r8d; ulOptions
0x18003efb0  lea     rdx, [rbp+SubKey]; lpSubKey
0x18003efb4  call    cs:__imp_RegOpenKeyExW
0x18003efba  test    eax, eax
0x18003efbc  jnz     short loc_18003F022
0x18003efbe  lea     rcx, [rbp+SubKey]; String
0x18003efc2  call    cs:__imp__wtol
0x18003efc8  mov     rcx, [rbp+var_28]
0x18003efcc  lea     r8, [rbp+var_38]
0x18003efd0  lea     rdx, aPrefix; "Prefix"
0x18003efd7  mov     [rbp+var_38], r15d
0x18003efdb  mov     ebx, eax
0x18003efdd  call    GetRegDword
0x18003efe2  mov     rcx, [rbp+var_28]
0x18003efe6  lea     r8, [rbp+var_3C]
0x18003efea  lea     rdx, aSuffix; "Suffix"
0x18003eff1  mov     [rbp+var_3C], r15d
0x18003eff5  call    GetRegDword
0x18003effa  mov     r8d, [rbp+var_3C]
0x18003effe  mov     ecx, ebx
0x18003f000  mov     edx, [rbp+var_38]
0x18003f003  call    CreateLocationNode
0x18003f008  test    rax, rax
0x18003f00b  jz      short loc_18003F022
0x18003f00d  mov     rdx, rax
0x18003f010  mov     rcx, rdi
0x18003f013  call    DtlAddNodeLast
0x18003f018  mov     rcx, [rbp+var_28]; hKey
0x18003f01c  call    cs:__imp_RegCloseKey
0x18003f022  inc     r14d
0x18003f025  mov     edx, r14d; dwIndex
0x18003f028  mov     rcx, [rbp+hKey]; hKey
0x18003f02c  lea     r9, [rbp+cchName]; lpcchName
0x18003f030  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003f035  lea     r8, [rbp+SubKey]; lpName
0x18003f039  mov     [rsp+80h+lpcchClass], r15; lpcchClass
0x18003f03e  mov     [rsp+80h+lpClass], r15; lpClass
0x18003f043  mov     [rsp+80h+phkResult], r15; lpReserved
0x18003f048  mov     [rbp+cchName], 0Ch
0x18003f04f  call    cs:__imp_RegEnumKeyExW
0x18003f055  cmp     eax, 103h
0x18003f05a  jnz     loc_18003EF92
0x18003f060  mov     rcx, [rbp+hKey]; hKey
0x18003f064  call    cs:__imp_RegCloseKey
0x18003f06a  mov     rcx, [rsi]; hMem
0x18003f06d  lea     rdx, DestroyLocationNode
0x18003f074  call    DtlDestroyList
0x18003f079  mov     [rsi], rdi
0x18003f07c  mov     rcx, [rbp+var_8]
0x18003f080  xor     rcx, rsp; StackCookie
0x18003f083  call    __security_check_cookie
0x18003f088  mov     rbx, [rsp+80h+arg_10]
0x18003f090  add     rsp, 80h
0x18003f097  pop     r15
0x18003f099  pop     r14
0x18003f09b  pop     rdi
0x18003f09c  pop     rsi
0x18003f09d  pop     rbp
0x18003f09e  retn
```
