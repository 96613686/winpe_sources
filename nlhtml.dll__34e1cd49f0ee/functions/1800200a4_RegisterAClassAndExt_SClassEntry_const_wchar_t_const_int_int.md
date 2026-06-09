# RegisterAClassAndExt(SClassEntry const &,wchar_t const *,int,int)

- ea: `0x1800200a4`
- end: `0x1800202fe`
- name: `?RegisterAClassAndExt@@YAJAEBUSClassEntry@@PEB_WHH@Z`
- size: `602`
- prototype: `__int64 __fastcall(const struct SClassEntry *, const wchar_t *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18002107c`

## callees

- `0x1800112e0`
- `0x180014130`
- `0x18001fd54`
- `0x1800200a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800201f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020276`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800201f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020276`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020195`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020288`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020288`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020153`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020248`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020153`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020248`

## pseudocode

```c
__int64 __fastcall RegisterAClassAndExt(const wchar_t **a1, const wchar_t *a2, int a3)
{
  const wchar_t *v4; // r8
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  LSTATUS v8; // eax
  const BYTE *v9; // rcx
  __int64 v10; // rax
  HKEY v11; // rcx
  WCHAR *v12; // r8
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = *a1;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  if ( !v4 )
  {
    v6 = 0;
    StringCchCopyW(SubKey, 0x104u, a1[1]);
    goto LABEL_18;
  }
  StringCchCopyW(SubKey, 0x104u, v4);
  v6 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( v6 )
  {
LABEL_26:
    v11 = hKey;
    goto LABEL_27;
  }
  if ( dwDisposition != 2 )
    goto LABEL_10;
  cbData = 520;
  v8 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)SubKey, &cbData);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 == 2 )
    {
      SubKey[0] = 0;
      v6 = 0;
    }
LABEL_10:
    if ( !a3 )
    {
      v9 = (const BYTE *)a1[1];
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&v9[2 * v10] );
      v6 = RegSetValueExW(hKey, 0, 0, 1u, v9, 2 * v10 + 2);
      SubKey[0] = 0;
    }
    if ( v6 )
      goto LABEL_26;
    goto LABEL_15;
  }
  if ( Type != 1 )
  {
    v6 = -2147467259;
    goto LABEL_26;
  }
LABEL_15:
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = RegCreateKeyExW(hKey, L"PersistentHandler", 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  if ( v6 )
    goto LABEL_26;
  v6 = RegSetValueExW(phkResult, 0, 0, 1u, L"{eec97550-47a9-11cf-b952-00aa0051fe20}", 0x4Eu);
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(phkResult);
LABEL_18:
  v11 = hKey;
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    v11 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( !v6 )
  {
    if ( SubKey[0] )
    {
      v12 = SubKey;
    }
    else
    {
      if ( a3 )
        goto LABEL_27;
      v12 = 0;
    }
    v6 = RegisterAClass((const struct SClassEntry *)a1, v7, v12, a3);
    goto LABEL_26;
  }
LABEL_27:
  if ( v11 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v11);
  return v6;
}

```

## disassembly

```asm
0x1800200a4  push    rbp
0x1800200a6  push    rbx
0x1800200a7  push    rsi
0x1800200a8  push    rdi
0x1800200a9  push    r14
0x1800200ab  push    r15
0x1800200ad  lea     rbp, [rsp-198h]
0x1800200b5  sub     rsp, 298h
0x1800200bc  mov     rax, cs:__security_cookie
0x1800200c3  xor     rax, rsp
0x1800200c6  mov     [rbp+1C0h+var_40], rax
0x1800200cd  xor     r14d, r14d
0x1800200d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800200d4  mov     esi, r8d
0x1800200d7  mov     [rsp+2C0h+hKey], r15
0x1800200dc  mov     r8, [rcx]; wchar_t *
0x1800200df  mov     rdi, rcx
0x1800200e2  mov     [rsp+2C0h+dwDisposition], r14d
0x1800200e7  mov     edx, 104h; unsigned __int64
0x1800200ec  mov     [rsp+2C0h+Type], r14d
0x1800200f1  mov     [rsp+2C0h+cbData], r14d
0x1800200f6  test    r8, r8
0x1800200f9  jnz     short loc_180020111
0x1800200fb  mov     r8, [rcx+8]; wchar_t *
0x1800200ff  mov     ebx, r14d
0x180020102  lea     rcx, [rsp+2C0h+SubKey]; wchar_t *
0x180020107  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002010c  jmp     loc_18002028E
0x180020111  lea     rcx, [rsp+2C0h+SubKey]; wchar_t *
0x180020116  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002011b  lea     r11, [rsp+2C0h+dwDisposition]
0x180020120  xor     r9d, r9d; lpClass
0x180020123  mov     [rsp+2C0h+lpdwDisposition], r11; lpdwDisposition
0x180020128  lea     rax, [rsp+2C0h+hKey]
0x18002012d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180020132  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180020137  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002013c  xor     r8d, r8d; Reserved
0x18002013f  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x180020147  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002014e  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x180020153  call    cs:__imp_RegCreateKeyExW
0x180020159  mov     ebx, eax
0x18002015b  test    eax, eax
0x18002015d  jnz     loc_1800202CD
0x180020163  cmp     [rsp+2C0h+dwDisposition], 2
0x180020168  jnz     short loc_1800201C0
0x18002016a  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18002016f  lea     rax, [rsp+2C0h+cbData]
0x180020174  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x180020179  lea     r9, [rsp+2C0h+Type]; lpType
0x18002017e  lea     rax, [rsp+2C0h+SubKey]
0x180020183  mov     [rsp+2C0h+cbData], 208h
0x18002018b  xor     r8d, r8d; lpReserved
0x18002018e  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x180020193  xor     edx, edx; lpValueName
0x180020195  call    cs:__imp_RegQueryValueExW
0x18002019b  mov     ebx, eax
0x18002019d  test    eax, eax
0x18002019f  jnz     short loc_1800201B2
0x1800201a1  cmp     [rsp+2C0h+Type], 1
0x1800201a6  jz      short loc_18002020B
0x1800201a8  mov     ebx, 80004005h
0x1800201ad  jmp     loc_1800202CD
0x1800201b2  cmp     eax, 2
0x1800201b5  jnz     short loc_1800201C0
0x1800201b7  mov     [rsp+2C0h+SubKey], r14w
0x1800201bd  mov     ebx, r14d
0x1800201c0  test    esi, esi
0x1800201c2  jnz     short loc_180020203
0x1800201c4  mov     rcx, [rdi+8]
0x1800201c8  mov     rax, r15
0x1800201cb  inc     rax
0x1800201ce  cmp     [rcx+rax*2], r14w
0x1800201d3  jnz     short loc_1800201CB
0x1800201d5  lea     eax, ds:2[rax*2]
0x1800201dc  mov     r9d, 1; dwType
0x1800201e2  mov     [rsp+2C0h+samDesired], eax; cbData
0x1800201e6  xor     r8d, r8d; Reserved
0x1800201e9  mov     qword ptr [rsp+2C0h+dwOptions], rcx; lpData
0x1800201ee  xor     edx, edx; lpValueName
0x1800201f0  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800201f5  call    cs:__imp_RegSetValueExW
0x1800201fb  mov     ebx, eax
0x1800201fd  mov     [rsp+2C0h+SubKey], r14w
0x180020203  test    ebx, ebx
0x180020205  jnz     loc_1800202CD
0x18002020b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180020210  lea     rax, [rsp+2C0h+dwDisposition]
0x180020215  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x18002021a  lea     rdx, SubKey; "PersistentHandler"
0x180020221  lea     rax, [rsp+2C0h+var_258]
0x180020226  mov     [rsp+2C0h+var_258], r15
0x18002022b  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180020230  xor     r9d, r9d; lpClass
0x180020233  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180020238  xor     r8d, r8d; Reserved
0x18002023b  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x180020243  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x180020248  call    cs:__imp_RegCreateKeyExW
0x18002024e  mov     ebx, eax
0x180020250  test    eax, eax
0x180020252  jnz     short loc_1800202CD
0x180020254  mov     rcx, [rsp+2C0h+var_258]; hKey
0x180020259  lea     rax, Data; "{eec97550-47a9-11cf-b952-00aa0051fe20}"
0x180020260  mov     [rsp+2C0h+samDesired], 4Eh ; 'N'; cbData
0x180020268  lea     r9d, [rbx+1]; dwType
0x18002026c  xor     r8d, r8d; Reserved
0x18002026f  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x180020274  xor     edx, edx; lpValueName
0x180020276  call    cs:__imp_RegSetValueExW
0x18002027c  mov     rcx, [rsp+2C0h+var_258]; hKey
0x180020281  mov     ebx, eax
0x180020283  cmp     rcx, r15
0x180020286  jz      short loc_18002028E
0x180020288  call    cs:__imp_RegCloseKey
0x18002028e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180020293  cmp     rcx, r15
0x180020296  jz      short loc_1800202A6
0x180020298  call    cs:__imp_RegCloseKey
0x18002029e  mov     rcx, r15
0x1800202a1  mov     [rsp+2C0h+hKey], rcx
0x1800202a6  test    ebx, ebx
0x1800202a8  jnz     short loc_1800202D2
0x1800202aa  cmp     [rsp+2C0h+SubKey], r14w
0x1800202b0  jnz     short loc_1800202BB
0x1800202b2  test    esi, esi
0x1800202b4  jnz     short loc_1800202D2
0x1800202b6  mov     r8, r14
0x1800202b9  jmp     short loc_1800202C0
0x1800202bb  lea     r8, [rsp+2C0h+SubKey]; wchar_t *
0x1800202c0  mov     r9d, esi; int
0x1800202c3  mov     rcx, rdi; struct SClassEntry *
0x1800202c6  call    ?RegisterAClass@@YAJAEBUSClassEntry@@PEB_W1H@Z; RegisterAClass(SClassEntry const &,wchar_t const *,wchar_t const *,int)
0x1800202cb  mov     ebx, eax
0x1800202cd  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800202d2  cmp     rcx, r15
0x1800202d5  jz      short loc_1800202DD
0x1800202d7  call    cs:__imp_RegCloseKey
0x1800202dd  mov     eax, ebx
0x1800202df  mov     rcx, [rbp+1C0h+var_40]
0x1800202e6  xor     rcx, rsp; StackCookie
0x1800202e9  call    __security_check_cookie
0x1800202ee  add     rsp, 298h
0x1800202f5  pop     r15
0x1800202f7  pop     r14
0x1800202f9  pop     rdi
0x1800202fa  pop     rsi
0x1800202fb  pop     rbx
0x1800202fc  pop     rbp
0x1800202fd  retn
```
