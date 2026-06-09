# GetLocationList

- ea: `0x180009784`
- end: `0x18000990f`
- name: `GetLocationList`
- size: `395`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009a30`

## callees

- `0x1800091ec`
- `0x180009784`
- `0x18000aad0`
- `0x18000ab10`
- `0x18000aba4`
- `0x18000ac40`
- `0x18000b100`

## import_xrefs

- `msvcrt!_wtol` at `0x180009832`
- `msvcrt!_wtol` at `0x180009832`
- `KERNEL32!RegCloseKey` at `0x18000988c`
- `KERNEL32!RegCloseKey` at `0x1800098d4`
- `KERNEL32!RegCloseKey` at `0x18000988c`
- `KERNEL32!RegCloseKey` at `0x1800098d4`
- `KERNEL32!RegEnumKeyExW` at `0x1800098bf`
- `KERNEL32!RegEnumKeyExW` at `0x1800098bf`
- `KERNEL32!RegOpenKeyExW` at `0x1800097ea`
- `KERNEL32!RegOpenKeyExW` at `0x180009824`
- `KERNEL32!RegOpenKeyExW` at `0x1800097ea`
- `KERNEL32!RegOpenKeyExW` at `0x180009824`

## pseudocode

```c
__int64 __fastcall GetLocationList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  DWORD v6; // r14d
  DWORD i; // edx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 LocationNode; // rax
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v14; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-28h] BYREF
  WCHAR SubKey[12]; // [rsp+60h] [rbp-20h] BYREF

  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList();
  v5 = result;
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
          LocationNode = CreateLocationNode(v9, v14, v13);
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
    result = DtlDestroyList(*a2);
    *a2 = (HGLOBAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x180009784  mov     [rsp-28h+arg_10], rbx
0x180009789  push    rbp
0x18000978a  push    rsi
0x18000978b  push    rdi
0x18000978c  push    r14
0x18000978e  push    r15
0x180009790  mov     rbp, rsp
0x180009793  sub     rsp, 80h
0x18000979a  mov     rax, cs:__security_cookie
0x1800097a1  xor     rax, rsp
0x1800097a4  mov     [rbp+var_8], rax
0x1800097a8  xor     r15d, r15d
0x1800097ab  mov     rsi, rdx
0x1800097ae  mov     [rbp+cchName], r15d
0x1800097b2  mov     rbx, rcx
0x1800097b5  mov     [rbp+hKey], r15
0x1800097b9  mov     [rbp+var_28], r15
0x1800097bd  call    DtlCreateList
0x1800097c2  mov     rdi, rax
0x1800097c5  test    rax, rax
0x1800097c8  jz      loc_1800098EC
0x1800097ce  lea     rax, [rbp+hKey]
0x1800097d2  mov     r9d, 20019h; samDesired
0x1800097d8  xor     r8d, r8d; ulOptions
0x1800097db  mov     [rsp+80h+phkResult], rax; phkResult
0x1800097e0  lea     rdx, aLocation; "Location"
0x1800097e7  mov     rcx, rbx; hKey
0x1800097ea  call    cs:__imp_RegOpenKeyExW
0x1800097f0  test    eax, eax
0x1800097f2  jnz     loc_1800098DA
0x1800097f8  mov     r14d, r15d
0x1800097fb  xor     edx, edx
0x1800097fd  jmp     loc_180009898
0x180009802  test    eax, eax
0x180009804  jnz     loc_180009892
0x18000980a  mov     rcx, [rbp+hKey]; hKey
0x18000980e  lea     rax, [rbp+var_28]
0x180009812  mov     r9d, 20019h; samDesired
0x180009818  mov     [rsp+80h+phkResult], rax; phkResult
0x18000981d  xor     r8d, r8d; ulOptions
0x180009820  lea     rdx, [rbp+SubKey]; lpSubKey
0x180009824  call    cs:__imp_RegOpenKeyExW
0x18000982a  test    eax, eax
0x18000982c  jnz     short loc_180009892
0x18000982e  lea     rcx, [rbp+SubKey]; String
0x180009832  call    cs:__imp__wtol
0x180009838  mov     rcx, [rbp+var_28]
0x18000983c  lea     r8, [rbp+var_38]
0x180009840  lea     rdx, aPrefix; "Prefix"
0x180009847  mov     [rbp+var_38], r15d
0x18000984b  mov     ebx, eax
0x18000984d  call    GetRegDword
0x180009852  mov     rcx, [rbp+var_28]
0x180009856  lea     r8, [rbp+var_3C]
0x18000985a  lea     rdx, aSuffix; "Suffix"
0x180009861  mov     [rbp+var_3C], r15d
0x180009865  call    GetRegDword
0x18000986a  mov     r8d, [rbp+var_3C]
0x18000986e  mov     ecx, ebx
0x180009870  mov     edx, [rbp+var_38]
0x180009873  call    CreateLocationNode
0x180009878  test    rax, rax
0x18000987b  jz      short loc_180009892
0x18000987d  mov     rdx, rax
0x180009880  mov     rcx, rdi
0x180009883  call    DtlAddNodeLast
0x180009888  mov     rcx, [rbp+var_28]; hKey
0x18000988c  call    cs:__imp_RegCloseKey
0x180009892  inc     r14d
0x180009895  mov     edx, r14d; dwIndex
0x180009898  mov     rcx, [rbp+hKey]; hKey
0x18000989c  lea     r9, [rbp+cchName]; lpcchName
0x1800098a0  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800098a5  lea     r8, [rbp+SubKey]; lpName
0x1800098a9  mov     [rsp+80h+lpcchClass], r15; lpcchClass
0x1800098ae  mov     [rsp+80h+lpClass], r15; lpClass
0x1800098b3  mov     [rsp+80h+phkResult], r15; lpReserved
0x1800098b8  mov     [rbp+cchName], 0Ch
0x1800098bf  call    cs:__imp_RegEnumKeyExW
0x1800098c5  cmp     eax, 103h
0x1800098ca  jnz     loc_180009802
0x1800098d0  mov     rcx, [rbp+hKey]; hKey
0x1800098d4  call    cs:__imp_RegCloseKey
0x1800098da  mov     rcx, [rsi]; hMem
0x1800098dd  lea     rdx, DestroyLocationNode
0x1800098e4  call    DtlDestroyList
0x1800098e9  mov     [rsi], rdi
0x1800098ec  mov     rcx, [rbp+var_8]
0x1800098f0  xor     rcx, rsp; StackCookie
0x1800098f3  call    __security_check_cookie
0x1800098f8  mov     rbx, [rsp+80h+arg_10]
0x180009900  add     rsp, 80h
0x180009907  pop     r15
0x180009909  pop     r14
0x18000990b  pop     rdi
0x18000990c  pop     rsi
0x18000990d  pop     rbp
0x18000990e  retn
```
