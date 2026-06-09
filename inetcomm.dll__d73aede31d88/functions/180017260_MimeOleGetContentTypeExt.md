# MimeOleGetContentTypeExt

- ea: `0x180017260`
- end: `0x1800173a3`
- name: `MimeOleGetContentTypeExt`
- size: `323`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d200`
- `0x180074be4`

## callees

- `0x180017260`

## import_xrefs

- `MSOERT2!PszAllocA` at `0x180017348`
- `MSOERT2!PszAllocA` at `0x180017348`
- `ADVAPI32!RegOpenKeyExA` at `0x1800172ba`
- `ADVAPI32!RegOpenKeyExA` at `0x18001730c`
- `ADVAPI32!RegOpenKeyExA` at `0x1800172ba`
- `ADVAPI32!RegOpenKeyExA` at `0x18001730c`
- `ADVAPI32!RegQueryValueExA` at `0x180017339`
- `ADVAPI32!RegQueryValueExA` at `0x18001737a`
- `ADVAPI32!RegQueryValueExA` at `0x180017339`
- `ADVAPI32!RegQueryValueExA` at `0x18001737a`
- `ADVAPI32!RegCloseKey` at `0x1800172d2`
- `ADVAPI32!RegCloseKey` at `0x1800172eb`
- `ADVAPI32!RegCloseKey` at `0x1800172d2`
- `ADVAPI32!RegCloseKey` at `0x1800172eb`

## string_xrefs

- `0x180017323`: `Extension`
- `0x180017362`: `Extension`

## pseudocode

```c
__int64 __fastcall MimeOleGetContentTypeExt(LPCSTR lpSubKey, BYTE **a2)
{
  unsigned int v4; // ebx
  BYTE *v6; // rax
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+38h] BYREF

  phkResult = 0;
  hKey = 0;
  cbData = 0;
  if ( !lpSubKey || !a2 )
    return 2147942487LL;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "MIME\\Database\\Content Type", 0, 0x20019u, &phkResult)
    || RegOpenKeyExA(phkResult, lpSubKey, 0, 0x20019u, &hKey)
    || RegQueryValueExA(hKey, "Extension", 0, 0, 0, &cbData) )
  {
    v4 = -2146644475;
  }
  else
  {
    v6 = (BYTE *)PszAllocA(cbData + 1);
    *a2 = v6;
    if ( v6 )
    {
      ++cbData;
      v4 = 0;
      if ( RegQueryValueExA(hKey, "Extension", 0, 0, v6, &cbData) )
        v4 = -2147467259;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x180017260  push    rbp
0x180017262  push    rbx
0x180017263  push    rdi
0x180017264  mov     rbp, rsp
0x180017267  sub     rsp, 30h
0x18001726b  mov     [rbp+arg_18], 0
0x180017273  mov     rbx, rdx
0x180017276  mov     [rbp+hKey], 0
0x18001727e  mov     rdi, rcx
0x180017281  mov     [rbp+cbData], 0
0x180017288  test    rcx, rcx
0x18001728b  jz      loc_180017399
0x180017291  test    rdx, rdx
0x180017294  jz      loc_180017399
0x18001729a  lea     rax, [rbp+arg_18]
0x18001729e  mov     r9d, 20019h; samDesired
0x1800172a4  xor     r8d, r8d; ulOptions
0x1800172a7  mov     [rsp+30h+phkResult], rax; phkResult
0x1800172ac  lea     rdx, c_szMDBContentType; "MIME\\Database\\Content Type"
0x1800172b3  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800172ba  call    cs:__imp_RegOpenKeyExA
0x1800172c0  test    eax, eax
0x1800172c2  jz      short loc_1800172F3
0x1800172c4  mov     ebx, 800CCE05h
0x1800172c9  mov     rcx, [rbp+hKey]; hKey
0x1800172cd  test    rcx, rcx
0x1800172d0  jz      short loc_1800172D8
0x1800172d2  call    cs:__imp_RegCloseKey
0x1800172d8  mov     rcx, [rbp+arg_18]; hKey
0x1800172dc  test    rcx, rcx
0x1800172df  jnz     short loc_1800172EB
0x1800172e1  mov     eax, ebx
0x1800172e3  add     rsp, 30h
0x1800172e7  pop     rdi
0x1800172e8  pop     rbx
0x1800172e9  pop     rbp
0x1800172ea  retn
0x1800172eb  call    cs:__imp_RegCloseKey
0x1800172f1  jmp     short loc_1800172E1
0x1800172f3  mov     rcx, [rbp+arg_18]; hKey
0x1800172f7  lea     rax, [rbp+hKey]
0x1800172fb  mov     r9d, 20019h; samDesired
0x180017301  mov     [rsp+30h+phkResult], rax; phkResult
0x180017306  xor     r8d, r8d; ulOptions
0x180017309  mov     rdx, rdi; lpSubKey
0x18001730c  call    cs:__imp_RegOpenKeyExA
0x180017312  test    eax, eax
0x180017314  jnz     short loc_1800172C4
0x180017316  mov     rcx, [rbp+hKey]; hKey
0x18001731a  lea     rax, [rbp+cbData]
0x18001731e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180017323  lea     rdx, c_szExtension; "Extension"
0x18001732a  xor     r9d, r9d; lpType
0x18001732d  mov     [rsp+30h+phkResult], 0; lpData
0x180017336  xor     r8d, r8d; lpReserved
0x180017339  call    cs:__imp_RegQueryValueExA
0x18001733f  test    eax, eax
0x180017341  jnz     short loc_1800172C4
0x180017343  mov     ecx, [rbp+cbData]
0x180017346  inc     ecx
0x180017348  call    cs:__imp_PszAllocA
0x18001734e  mov     [rbx], rax
0x180017351  test    rax, rax
0x180017354  jz      short loc_18001738F
0x180017356  inc     [rbp+cbData]
0x180017359  lea     rcx, [rbp+cbData]
0x18001735d  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180017362  lea     rdx, c_szExtension; "Extension"
0x180017369  mov     rcx, [rbp+hKey]; hKey
0x18001736d  xor     r9d, r9d; lpType
0x180017370  xor     r8d, r8d; lpReserved
0x180017373  mov     [rsp+30h+phkResult], rax; lpData
0x180017378  xor     ebx, ebx
0x18001737a  call    cs:__imp_RegQueryValueExA
0x180017380  test    eax, eax
0x180017382  mov     ecx, 80004005h
0x180017387  cmovnz  ebx, ecx
0x18001738a  jmp     loc_1800172C9
0x18001738f  mov     ebx, 8007000Eh
0x180017394  jmp     loc_1800172C9
0x180017399  mov     eax, 80070057h
0x18001739e  jmp     loc_1800172E3
```
