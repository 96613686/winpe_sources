# GetCallbackList

- ea: `0x180009588`
- end: `0x18000977c`
- name: `GetCallbackList`
- size: `500`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009a30`

## callees

- `0x1800088b8`
- `0x180009148`
- `0x180009588`
- `0x18000aad0`
- `0x18000ab10`
- `0x18000aba4`
- `0x18000ac40`
- `0x18000add4`
- `0x18000b100`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x1800096dc`
- `KERNEL32!RegCloseKey` at `0x18000973d`
- `KERNEL32!RegCloseKey` at `0x1800096dc`
- `KERNEL32!RegCloseKey` at `0x18000973d`
- `KERNEL32!RegEnumKeyExW` at `0x180009727`
- `KERNEL32!RegEnumKeyExW` at `0x180009727`
- `KERNEL32!GlobalFree` at `0x1800096d1`
- `KERNEL32!GlobalFree` at `0x1800096e7`
- `KERNEL32!GlobalFree` at `0x1800096f2`
- `KERNEL32!GlobalFree` at `0x1800096d1`
- `KERNEL32!GlobalFree` at `0x1800096e7`
- `KERNEL32!GlobalFree` at `0x1800096f2`
- `KERNEL32!RegOpenKeyExW` at `0x180009610`
- `KERNEL32!RegOpenKeyExW` at `0x180009669`
- `KERNEL32!RegOpenKeyExW` at `0x180009610`
- `KERNEL32!RegOpenKeyExW` at `0x180009669`

## pseudocode

```c
__int64 __fastcall GetCallbackList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  DWORD v6; // esi
  DWORD i; // edx
  __int64 CallbackNode; // rax
  LSTATUS v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-A8h]
  HGLOBAL v15; // [rsp+60h] [rbp-A0h] BYREF
  HGLOBAL v16; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[152]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v16 = 0;
  hMem = 0;
  v11 = 0;
  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList();
  v5 = result;
  if ( result )
  {
    if ( !RegOpenKeyExW(hKey, L"Callback", 0, 0x20019u, &hKeya) )
    {
      v6 = 0;
      for ( i = 0; ; i = v6 )
      {
        cchName = 148;
        v9 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v9 == 259 )
          break;
        if ( !v9 && (unsigned int)DeviceAndPortFromPsz(SubKey, &v15, &v16) )
        {
          if ( !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &phkResult) )
          {
            GetRegDword(phkResult, L"DeviceType", &v11);
            if ( !(unsigned int)GetRegSz(phkResult, L"Number") )
            {
              CallbackNode = CreateCallbackNode((STRSAFE_LPCWSTR)v16, (STRSAFE_LPCWSTR)v15, (STRSAFE_LPCWSTR)hMem);
              if ( CallbackNode )
                DtlAddNodeLast(v5, CallbackNode);
              GlobalFree(hMem);
            }
            RegCloseKey(phkResult);
          }
          GlobalFree(v15);
          GlobalFree(v16);
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
0x180009588  mov     [rsp-8+arg_10], rbx
0x18000958d  mov     [rsp-8+arg_18], rsi
0x180009592  push    rbp
0x180009593  push    rdi
0x180009594  push    r14
0x180009596  lea     rbp, [rsp-0B0h]
0x18000959e  sub     rsp, 1B0h
0x1800095a5  mov     rax, cs:__security_cookie
0x1800095ac  xor     rax, rsp
0x1800095af  mov     [rbp+0C0h+var_20], rax
0x1800095b6  xor     r14d, r14d
0x1800095b9  mov     rdi, rdx
0x1800095bc  mov     [rsp+1C0h+var_160], r14
0x1800095c1  mov     rsi, rcx
0x1800095c4  mov     [rsp+1C0h+var_158], r14
0x1800095c9  mov     [rsp+1C0h+hMem], r14
0x1800095ce  mov     [rsp+1C0h+var_17C], r14d
0x1800095d3  mov     [rsp+1C0h+cchName], r14d
0x1800095d8  mov     [rsp+1C0h+hKey], r14
0x1800095dd  mov     [rsp+1C0h+var_170], r14
0x1800095e2  call    DtlCreateList
0x1800095e7  mov     rbx, rax
0x1800095ea  test    rax, rax
0x1800095ed  jz      loc_180009755
0x1800095f3  lea     rax, [rsp+1C0h+hKey]
0x1800095f8  mov     r9d, 20019h; samDesired
0x1800095fe  xor     r8d, r8d; ulOptions
0x180009601  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180009606  lea     rdx, aCallback; "Callback"
0x18000960d  mov     rcx, rsi; hKey
0x180009610  call    cs:__imp_RegOpenKeyExW
0x180009616  test    eax, eax
0x180009618  jnz     loc_180009743
0x18000961e  mov     esi, r14d
0x180009621  xor     edx, edx
0x180009623  jmp     loc_1800096FC
0x180009628  test    eax, eax
0x18000962a  jnz     loc_1800096F8
0x180009630  lea     r8, [rsp+1C0h+var_158]
0x180009635  lea     rdx, [rsp+1C0h+var_160]
0x18000963a  lea     rcx, [rsp+1C0h+SubKey]
0x18000963f  call    DeviceAndPortFromPsz
0x180009644  test    eax, eax
0x180009646  jz      loc_1800096F8
0x18000964c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180009651  lea     rax, [rsp+1C0h+var_170]
0x180009656  mov     r9d, 20019h; samDesired
0x18000965c  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180009661  xor     r8d, r8d; ulOptions
0x180009664  lea     rdx, [rsp+1C0h+SubKey]; lpSubKey
0x180009669  call    cs:__imp_RegOpenKeyExW
0x18000966f  test    eax, eax
0x180009671  jnz     short loc_1800096E2
0x180009673  mov     rcx, [rsp+1C0h+var_170]
0x180009678  lea     r8, [rsp+1C0h+var_17C]
0x18000967d  lea     rdx, aDevicetype; "DeviceType"
0x180009684  call    GetRegDword
0x180009689  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18000968e  lea     r8, [rsp+1C0h+hMem]
0x180009693  lea     rdx, aNumber; "Number"
0x18000969a  call    GetRegSz
0x18000969f  test    eax, eax
0x1800096a1  jnz     short loc_1800096D7
0x1800096a3  mov     r9d, [rsp+1C0h+var_17C]
0x1800096a8  mov     r8, [rsp+1C0h+hMem]; STRSAFE_LPCWSTR
0x1800096ad  mov     rdx, [rsp+1C0h+var_160]; STRSAFE_LPCWSTR
0x1800096b2  mov     rcx, [rsp+1C0h+var_158]; pszSrc
0x1800096b7  call    CreateCallbackNode
0x1800096bc  test    rax, rax
0x1800096bf  jz      short loc_1800096CC
0x1800096c1  mov     rdx, rax
0x1800096c4  mov     rcx, rbx
0x1800096c7  call    DtlAddNodeLast
0x1800096cc  mov     rcx, [rsp+1C0h+hMem]; hMem
0x1800096d1  call    cs:__imp_GlobalFree
0x1800096d7  mov     rcx, [rsp+1C0h+var_170]; hKey
0x1800096dc  call    cs:__imp_RegCloseKey
0x1800096e2  mov     rcx, [rsp+1C0h+var_160]; hMem
0x1800096e7  call    cs:__imp_GlobalFree
0x1800096ed  mov     rcx, [rsp+1C0h+var_158]; hMem
0x1800096f2  call    cs:__imp_GlobalFree
0x1800096f8  inc     esi
0x1800096fa  mov     edx, esi; dwIndex
0x1800096fc  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180009701  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x180009706  mov     [rsp+1C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000970b  lea     r8, [rsp+1C0h+SubKey]; lpName
0x180009710  mov     [rsp+1C0h+lpcchClass], r14; lpcchClass
0x180009715  mov     [rsp+1C0h+lpClass], r14; lpClass
0x18000971a  mov     [rsp+1C0h+phkResult], r14; lpReserved
0x18000971f  mov     [rsp+1C0h+cchName], 94h
0x180009727  call    cs:__imp_RegEnumKeyExW
0x18000972d  cmp     eax, 103h
0x180009732  jnz     loc_180009628
0x180009738  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000973d  call    cs:__imp_RegCloseKey
0x180009743  mov     rcx, [rdi]; hMem
0x180009746  lea     rdx, DestroyCallbackNode
0x18000974d  call    DtlDestroyList
0x180009752  mov     [rdi], rbx
0x180009755  mov     rcx, [rbp+0C0h+var_20]
0x18000975c  xor     rcx, rsp; StackCookie
0x18000975f  call    __security_check_cookie
0x180009764  lea     r11, [rsp+1C0h+var_10]
0x18000976c  mov     rbx, [r11+30h]
0x180009770  mov     rsi, [r11+38h]
0x180009774  mov     rsp, r11
0x180009777  pop     r14
0x180009779  pop     rdi
0x18000977a  pop     rbp
0x18000977b  retn
```
