# _anonymous_namespace_::GetDatabasePath

- ea: `0x180014708`
- end: `0x1800148fe`
- name: `_anonymous_namespace_::GetDatabasePath`
- size: `502`
- prototype: `LSTATUS __fastcall(wchar_t *Source, BYTE *Destination, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180002ba0`

## callees

- `0x18000dc24`
- `0x180014708`

## import_xrefs

- `msvcrt!free` at `0x18001488a`
- `msvcrt!free` at `0x1800148a7`
- `msvcrt!free` at `0x18001488a`
- `msvcrt!free` at `0x1800148a7`
- `msvcrt!wcsncpy_s` at `0x18001489e`
- `msvcrt!wcsncpy_s` at `0x18001489e`
- `msvcrt!wcscat_s` at `0x1800148cc`
- `msvcrt!wcscat_s` at `0x1800148cc`
- `ADVAPI32!RegQueryValueExW` at `0x1800147cd`
- `ADVAPI32!RegQueryValueExW` at `0x1800147cd`
- `ADVAPI32!RegCloseKey` at `0x1800147da`
- `ADVAPI32!RegCloseKey` at `0x1800147da`
- `ADVAPI32!RegOpenKeyExW` at `0x180014776`
- `ADVAPI32!RegOpenKeyExW` at `0x180014776`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001483b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001487d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001483b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001487d`
- `KERNEL32!GetLastError` at `0x180014848`
- `KERNEL32!GetLastError` at `0x180014848`

## string_xrefs

- `0x180014768`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::GetDatabasePath(wchar_t *Source, BYTE *Destination, unsigned int *a3)
{
  unsigned int v6; // edi
  LSTATUS result; // eax
  rsize_t v8; // r13
  LSTATUS v9; // esi
  __int64 v10; // r15
  __int64 v11; // rcx
  unsigned int v12; // edi
  DWORD v13; // eax
  unsigned __int64 v14; // r12
  unsigned __int128 v15; // rax
  WCHAR *v16; // rax
  WCHAR *v17; // rdi
  unsigned int v18; // [rsp+30h] [rbp-48h]
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  if ( Source )
  {
    if ( Destination )
    {
      if ( a3 )
      {
        v6 = *a3;
        if ( *a3 )
        {
          *a3 = 0;
          hKey = 0;
          result = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
                     0,
                     0x20019u,
                     &hKey);
          if ( result )
            return result;
          v8 = v6 - 1;
          v18 = v6 - 1;
          cbData = 2 * v8;
          Type = 0;
          v9 = RegQueryValueExW(hKey, L"ProductDir", 0, &Type, Destination, &cbData);
          RegCloseKey(hKey);
          v10 = -1;
          v11 = -1;
          do
            ++v11;
          while ( Source[v11] );
          v12 = v11 + (cbData >> 1);
          if ( v9 )
          {
            if ( v9 != 234 )
              return v9;
LABEL_10:
            *a3 = v12;
            return v9;
          }
          if ( Type != 1 )
          {
            if ( Type != 2 )
              return -2147221165;
            v13 = ExpandEnvironmentStringsW((LPCWSTR)Destination, 0, 0);
            v14 = v13;
            if ( !v13 )
              return GetLastError();
            v15 = v13 * (unsigned __int128)2uLL;
            if ( !is_mul_ok(v14, 2u) )
              *(_QWORD *)&v15 = -1;
            v16 = (WCHAR *)operator new[](v15, *((const struct std::nothrow_t **)&v15 + 1));
            v17 = v16;
            if ( !v16 )
              return 8;
            if ( !ExpandEnvironmentStringsW((LPCWSTR)Destination, v16, v14) )
            {
              free(v17);
              return GetLastError();
            }
            wcsncpy_s((wchar_t *)Destination, v8, v17, v14);
            free(v17);
            do
              ++v10;
            while ( Source[v10] );
            v12 = v10 + v14;
          }
          if ( v12 > v18 )
            v9 = 234;
          else
            wcscat_s((wchar_t *)Destination, v8, Source);
          goto LABEL_10;
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180014708  mov     r11, rsp
0x18001470b  mov     [r11+10h], rbx
0x18001470f  push    rbp
0x180014710  push    rsi
0x180014711  push    rdi
0x180014712  push    r12
0x180014714  push    r13
0x180014716  push    r14
0x180014718  push    r15
0x18001471a  sub     rsp, 40h
0x18001471e  xor     r12d, r12d
0x180014721  mov     rbx, r8
0x180014724  mov     rbp, rdx
0x180014727  mov     r14, rcx
0x18001472a  test    rcx, rcx
0x18001472d  jz      loc_1800148E1
0x180014733  test    rdx, rdx
0x180014736  jz      loc_1800148E1
0x18001473c  test    rbx, rbx
0x18001473f  jz      loc_1800148E1
0x180014745  mov     edi, [r8]
0x180014748  test    edi, edi
0x18001474a  jz      loc_1800148E1
0x180014750  mov     [r8], r12d
0x180014753  lea     rax, [r11-40h]
0x180014757  xor     r8d, r8d; ulOptions
0x18001475a  mov     [r11-58h], rax
0x18001475e  mov     r9d, 20019h; samDesired
0x180014764  mov     [r11-40h], r12
0x180014768  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18001476f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014776  call    cs:__imp_RegOpenKeyExW
0x18001477c  test    eax, eax
0x18001477e  jnz     loc_1800148E6
0x180014784  mov     rcx, [rsp+78h+hKey]; hKey
0x180014789  lea     r13d, [rdi-1]
0x18001478d  lea     eax, ds:0[r13*2]
0x180014795  mov     [rsp+78h+var_48], r13d
0x18001479a  mov     [rsp+78h+cbData], eax
0x1800147a1  lea     r9, [rsp+78h+Type]; lpType
0x1800147a9  lea     rax, [rsp+78h+cbData]
0x1800147b1  mov     [rsp+78h+Type], r12d
0x1800147b9  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800147be  lea     rdx, aProductdir_0; "ProductDir"
0x1800147c5  xor     r8d, r8d; lpReserved
0x1800147c8  mov     [rsp+78h+lpData], rbp; lpData
0x1800147cd  call    cs:__imp_RegQueryValueExW
0x1800147d3  mov     rcx, [rsp+78h+hKey]; hKey
0x1800147d8  mov     esi, eax
0x1800147da  call    cs:__imp_RegCloseKey
0x1800147e0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800147e4  mov     rcx, r15
0x1800147e7  inc     rcx
0x1800147ea  cmp     [r14+rcx*2], r12w
0x1800147ef  jnz     short loc_1800147E7
0x1800147f1  mov     edi, [rsp+78h+cbData]
0x1800147f8  shr     edi, 1
0x1800147fa  add     edi, ecx
0x1800147fc  test    esi, esi
0x1800147fe  jz      short loc_180014811
0x180014800  cmp     esi, 0EAh
0x180014806  jnz     short loc_18001480A
0x180014808  mov     [rbx], edi
0x18001480a  mov     eax, esi
0x18001480c  jmp     loc_1800148E6
0x180014811  cmp     [rsp+78h+Type], 1
0x180014819  jz      loc_1800148BD
0x18001481f  cmp     [rsp+78h+Type], 2
0x180014827  jz      short loc_180014833
0x180014829  mov     eax, 80040153h
0x18001482e  jmp     loc_1800148E6
0x180014833  xor     r8d, r8d; nSize
0x180014836  xor     edx, edx; lpDst
0x180014838  mov     rcx, rbp; lpSrc
0x18001483b  call    cs:__imp_ExpandEnvironmentStringsW
0x180014841  mov     r12d, eax
0x180014844  test    eax, eax
0x180014846  jnz     short loc_180014853
0x180014848  call    cs:__imp_GetLastError
0x18001484e  jmp     loc_1800148E6
0x180014853  mov     eax, 2
0x180014858  mul     r12
0x18001485b  cmovb   rax, r15
0x18001485f  mov     rcx, rax; Size
0x180014862  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014867  mov     rdi, rax
0x18001486a  test    rax, rax
0x18001486d  jnz     short loc_180014874
0x18001486f  lea     eax, [rdi+8]
0x180014872  jmp     short loc_1800148E6
0x180014874  mov     r8d, r12d; nSize
0x180014877  mov     rdx, rdi; lpDst
0x18001487a  mov     rcx, rbp; lpSrc
0x18001487d  call    cs:__imp_ExpandEnvironmentStringsW
0x180014883  test    eax, eax
0x180014885  jnz     short loc_180014892
0x180014887  mov     rcx, rdi; Block
0x18001488a  call    cs:__imp_free
0x180014890  jmp     short loc_180014848
0x180014892  mov     r9, r12; MaxCount
0x180014895  mov     r8, rdi; Source
0x180014898  mov     rdx, r13; SizeInWords
0x18001489b  mov     rcx, rbp; Destination
0x18001489e  call    cs:__imp_wcsncpy_s
0x1800148a4  mov     rcx, rdi; Block
0x1800148a7  call    cs:__imp_free
0x1800148ad  xor     eax, eax
0x1800148af  inc     r15
0x1800148b2  cmp     [r14+r15*2], ax
0x1800148b7  jnz     short loc_1800148AF
0x1800148b9  lea     edi, [r15+r12]
0x1800148bd  cmp     edi, [rsp+78h+var_48]
0x1800148c1  ja      short loc_1800148D7
0x1800148c3  mov     r8, r14; Source
0x1800148c6  mov     rdx, r13; SizeInWords
0x1800148c9  mov     rcx, rbp; Destination
0x1800148cc  call    cs:__imp_wcscat_s
0x1800148d2  jmp     loc_180014808
0x1800148d7  mov     esi, 0EAh
0x1800148dc  jmp     loc_180014808
0x1800148e1  mov     eax, 57h ; 'W'
0x1800148e6  mov     rbx, [rsp+78h+arg_8]
0x1800148ee  add     rsp, 40h
0x1800148f2  pop     r15
0x1800148f4  pop     r14
0x1800148f6  pop     r13
0x1800148f8  pop     r12
0x1800148fa  pop     rdi
0x1800148fb  pop     rsi
0x1800148fc  pop     rbp
0x1800148fd  retn
```
