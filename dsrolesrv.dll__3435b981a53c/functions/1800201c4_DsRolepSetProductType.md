# DsRolepSetProductType

- ea: `0x1800201c4`
- end: `0x1800202ba`
- name: `DsRolepSetProductType`
- size: `246`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011240`
- `0x180012460`
- `0x180014524`

## callees

- `0x180016538`
- `0x1800201c4`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002021f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002021f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002024b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002024b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020258`

## pseudocode

```c
__int64 __fastcall DsRolepSetProductType(unsigned int a1)
{
  const BYTE *v2; // rdi
  unsigned int v3; // ebx
  const wchar_t *v4; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-18h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( !a1 )
    goto LABEL_9;
  if ( a1 == 1 )
  {
    v2 = (const BYTE *)L"ServerNT";
    goto LABEL_6;
  }
  if ( a1 != 2 )
  {
LABEL_9:
    v4 = L"(NULL)";
    v3 = 87;
    v2 = 0;
    goto LABEL_10;
  }
  v2 = L"LanmanNT";
LABEL_6:
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProductOptions", 0, 0x20006u, &hKey);
  if ( !v3 )
  {
    v3 = RegSetValueExW(hKey, L"ProductType", 0, 1u, v2, 0x12u);
    RegCloseKey(hKey);
  }
  v4 = (const wchar_t *)v2;
LABEL_10:
  LODWORD(phkResult) = v3;
  DsRolepLogPrintRoutine(4, "SetProductType to %lu [%ws] returned %lu\n", a1, v4, phkResult);
  if ( v3 )
    DsRolepSetFailureMessage(v3, 3221254682LL, v2, 0, 0);
  return v3;
}

```

## disassembly

```asm
0x1800201c4  mov     [rsp+arg_0], rbx
0x1800201c9  mov     [rsp+arg_10], rsi
0x1800201ce  push    rdi
0x1800201cf  sub     rsp, 30h
0x1800201d3  mov     [rsp+38h+hKey], 0
0x1800201dc  mov     esi, ecx
0x1800201de  mov     edx, ecx
0x1800201e0  test    ecx, ecx
0x1800201e2  jz      short loc_180020263
0x1800201e4  sub     edx, 1
0x1800201e7  jz      short loc_1800201F7
0x1800201e9  cmp     edx, 1
0x1800201ec  jnz     short loc_180020263
0x1800201ee  lea     rdi, aLanmannt; "LanmanNT"
0x1800201f5  jmp     short loc_1800201FE
0x1800201f7  lea     rdi, aServernt; "ServerNT"
0x1800201fe  lea     rax, [rsp+38h+hKey]
0x180020203  mov     r9d, 20006h; samDesired
0x180020209  xor     r8d, r8d; ulOptions
0x18002020c  mov     [rsp+38h+phkResult], rax; phkResult
0x180020211  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Pro"...
0x180020218  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002021f  call    cs:__imp_RegOpenKeyExW
0x180020225  mov     ebx, eax
0x180020227  test    eax, eax
0x180020229  jnz     short loc_18002025E
0x18002022b  mov     rcx, [rsp+38h+hKey]; hKey
0x180020230  lea     r9d, [rax+1]; dwType
0x180020234  mov     [rsp+38h+cbData], 12h; cbData
0x18002023c  lea     rdx, aProducttype; "ProductType"
0x180020243  xor     r8d, r8d; Reserved
0x180020246  mov     [rsp+38h+phkResult], rdi; lpData
0x18002024b  call    cs:__imp_RegSetValueExW
0x180020251  mov     rcx, [rsp+38h+hKey]; hKey
0x180020256  mov     ebx, eax
0x180020258  call    cs:__imp_RegCloseKey
0x18002025e  mov     r9, rdi
0x180020261  jmp     short loc_180020271
0x180020263  lea     r9, aNull; "(NULL)"
0x18002026a  mov     ebx, 57h ; 'W'
0x18002026f  xor     edi, edi
0x180020271  mov     r8d, esi
0x180020274  mov     dword ptr [rsp+38h+phkResult], ebx
0x180020278  lea     rdx, aSetproducttype; "SetProductType to %lu [%ws] returned %l"...
0x18002027f  mov     ecx, 4
0x180020284  call    DsRolepLogPrintRoutine
0x180020289  test    ebx, ebx
0x18002028b  jz      short loc_1800202A8
0x18002028d  xor     r9d, r9d
0x180020290  mov     [rsp+38h+phkResult], 0
0x180020299  mov     r8, rdi
0x18002029c  mov     edx, 0C000721Ah
0x1800202a1  mov     ecx, ebx
0x1800202a3  call    DsRolepSetFailureMessage
0x1800202a8  mov     rsi, [rsp+38h+arg_10]
0x1800202ad  mov     eax, ebx
0x1800202af  mov     rbx, [rsp+38h+arg_0]
0x1800202b4  add     rsp, 30h
0x1800202b8  pop     rdi
0x1800202b9  retn
```
