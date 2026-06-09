# CPackager::_BuildCollectionTable(ulong,IHTMLDocument2 *,IMimeEditTagCollection * * *,ulong *)

- ea: `0x180075ab0`
- end: `0x180075e27`
- name: `?_BuildCollectionTable@CPackager@@AEAAJKPEAUIHTMLDocument2@@PEAPEAPEAUIMimeEditTagCollection@@PEAK@Z`
- size: `887`
- prototype: `int(CPackager *__hidden this, unsigned int, struct IHTMLDocument2 *, struct IMimeEditTagCollection ***, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180075690`

## callees

- `0x180002098`
- `0x180023b48`
- `0x180075ab0`
- `0x180083954`
- `0x180083ab8`
- `0x180083c4c`
- `0x180083d74`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszToUnicode` at `0x180075d21`
- `MSOERT2!PszToUnicode` at `0x180075d21`
- `ADVAPI32!RegOpenKeyExA` at `0x180075b6a`
- `ADVAPI32!RegOpenKeyExA` at `0x180075cac`
- `ADVAPI32!RegOpenKeyExA` at `0x180075b6a`
- `ADVAPI32!RegOpenKeyExA` at `0x180075cac`
- `ADVAPI32!RegCloseKey` at `0x180075bc7`
- `ADVAPI32!RegCloseKey` at `0x180075db0`
- `ADVAPI32!RegCloseKey` at `0x180075bc7`
- `ADVAPI32!RegCloseKey` at `0x180075db0`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180075bae`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180075bae`
- `ADVAPI32!RegEnumKeyExA` at `0x180075d02`
- `ADVAPI32!RegEnumKeyExA` at `0x180075d02`
- `ole32!CoCreateInstance` at `0x180075d5c`
- `ole32!CoCreateInstance` at `0x180075d5c`
- `ole32!IIDFromString` at `0x180075d36`
- `ole32!IIDFromString` at `0x180075d36`

## string_xrefs

- `0x180075b5c`: `SOFTWARE\Microsoft\MimeEdit\MHTML Extension`
- `0x180075c9e`: `SOFTWARE\Microsoft\MimeEdit\MHTML Extension`

## pseudocode

```c
__int64 __fastcall CPackager::_BuildCollectionTable(
        CPackager *this,
        char a2,
        struct IHTMLDocument2 *a3,
        struct IMimeEditTagCollection ***a4,
        unsigned int *a5)
{
  __int64 v5; // rbx
  int v6; // esi
  int v7; // r15d
  int v9; // eax
  unsigned int v10; // edi
  int v11; // r12d
  struct IMimeEditTagCollection **v13; // rsi
  unsigned int v14; // r14d
  struct IMimeEditTagCollection **v15; // r14
  DWORD i; // esi
  LSTATUS v17; // eax
  const OLECHAR *v18; // rax
  const OLECHAR *v19; // r15
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+74h] [rbp-8Ch]
  struct IMimeEditTagCollection **v24; // [rsp+78h] [rbp-88h] BYREF
  struct IMimeEditTagCollection ***v25; // [rsp+80h] [rbp-80h]
  unsigned int *v26; // [rsp+88h] [rbp-78h]
  IID iid; // [rsp+90h] [rbp-70h] BYREF
  CHAR Name[272]; // [rsp+A0h] [rbp-60h] BYREF

  LODWORD(v5) = 0;
  v26 = a5;
  v6 = a2 & 4;
  *a4 = 0;
  v25 = a4;
  *a5 = 0;
  v24 = 0;
  hKey = 0;
  cSubKeys = 0;
  v7 = a2 & 0x10;
  cchName = 0;
  v9 = v6 != 0 ? 3 : 1;
  if ( (a2 & 0x10) == 0 )
    v9 = (a2 & 4) != 0 ? 2 : 0;
  iid = 0;
  v23 = a2 & 0x20;
  v10 = v9 + 1;
  if ( (a2 & 0x20) == 0 )
    v10 = v9;
  v11 = a2 & 0x40;
  if ( (a2 & 0x40) != 0
    && !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\MimeEdit\\MHTML Extension", 0, 0x20019u, &hKey) )
  {
    if ( RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
      cSubKeys = 0;
    else
      v10 += cSubKeys;
    RegCloseKey(hKey);
  }
  if ( !v10 )
    return 0;
  if ( (unsigned int)MemAlloc((void **)&v24, 8 * v10) )
  {
    v15 = v24;
    memset_0(v24, 0, 8LL * v10);
    if ( v6 )
    {
      v5 = (int)CreateOEImageCollection(a3, v15) >= 0;
      if ( (int)CreateBGImageCollection(a3, &v15[v5]) >= 0 )
        LODWORD(v5) = v5 + 1;
    }
    if ( v7 && (int)CreateBGSoundCollection(a3, &v15[(unsigned int)v5]) >= 0 )
      LODWORD(v5) = v5 + 1;
    if ( v23 && (int)CreateActiveMovieCollection(a3, &v15[(unsigned int)v5]) >= 0 )
      LODWORD(v5) = v5 + 1;
    if ( v11
      && cSubKeys
      && !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\MimeEdit\\MHTML Extension", 0, 0x20019u, &hKey) )
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 260;
        v17 = RegEnumKeyExA(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v17 == 259 )
          break;
        if ( !v17 )
        {
          v18 = (const OLECHAR *)PszToUnicode(0, Name);
          v19 = v18;
          if ( v18 )
          {
            if ( !IIDFromString(v18, &iid)
              && !CoCreateInstance(&iid, 0, 1u, &IID_IMimeEditTagCollection, (LPVOID *)&v15[(unsigned int)v5]) )
            {
              if ( (*(int (__fastcall **)(struct IMimeEditTagCollection *, struct IHTMLDocument2 *))(*(_QWORD *)v15[(unsigned int)v5] + 24LL))(
                     v15[(unsigned int)v5],
                     a3) < 0 )
                OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v15[(unsigned int)v5]);
              else
                LODWORD(v5) = v5 + 1;
            }
            ((void (__fastcall *)(LPMALLOC, const OLECHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v19);
          }
        }
      }
      RegCloseKey(hKey);
    }
    *v25 = v15;
    *v26 = v5;
    LODWORD(v5) = 0;
    v13 = 0;
    v14 = 0;
  }
  else
  {
    v13 = v24;
    v14 = -2147024882;
  }
  if ( v13 )
  {
    do
    {
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13[(unsigned int)v5]);
      LODWORD(v5) = v5 + 1;
    }
    while ( (unsigned int)v5 < v10 );
    ((void (__fastcall *)(LPMALLOC, struct IMimeEditTagCollection **))g_pMalloc->lpVtbl->Free)(g_pMalloc, v13);
  }
  return v14;
}

```

## disassembly

```asm
0x180075ab0  mov     [rsp-8+arg_0], rbx
0x180075ab5  push    rbp
0x180075ab6  push    rsi
0x180075ab7  push    rdi
0x180075ab8  push    r12
0x180075aba  push    r13
0x180075abc  push    r14
0x180075abe  push    r15
0x180075ac0  lea     rbp, [rsp-0C0h]
0x180075ac8  sub     rsp, 1C0h
0x180075acf  mov     rax, cs:__security_cookie
0x180075ad6  xor     rax, rsp
0x180075ad9  mov     [rbp+0F0h+var_40], rax
0x180075ae0  mov     rcx, [rbp+0F0h+arg_20]
0x180075ae7  xor     ebx, ebx
0x180075ae9  mov     [rbp+0F0h+var_168], rcx
0x180075aed  mov     esi, edx
0x180075aef  and     esi, 4
0x180075af2  mov     [r9], rbx
0x180075af5  mov     eax, esi
0x180075af7  mov     [rbp+0F0h+var_170], r9
0x180075afb  neg     eax
0x180075afd  mov     [rcx], ebx
0x180075aff  mov     r15d, edx
0x180075b02  mov     [rsp+1F0h+var_178], rbx
0x180075b07  sbb     ecx, ecx
0x180075b09  mov     [rsp+1F0h+hKey], rbx
0x180075b0e  and     ecx, 2
0x180075b11  mov     [rsp+1F0h+cSubKeys], ebx
0x180075b15  and     r15d, 10h
0x180075b19  mov     [rsp+1F0h+cchName], ebx
0x180075b1d  mov     r12d, edx
0x180075b20  xorps   xmm0, xmm0
0x180075b23  mov     r13, r8
0x180075b26  lea     eax, [rcx+1]
0x180075b29  cmovz   eax, ecx
0x180075b2c  mov     ecx, edx
0x180075b2e  and     ecx, 20h
0x180075b31  movups  xmmword ptr [rbp+0F0h+iid.Data1], xmm0
0x180075b35  mov     [rsp+1F0h+var_17C], ecx
0x180075b39  lea     edi, [rax+1]
0x180075b3c  cmovz   edi, eax
0x180075b3f  and     r12d, 40h
0x180075b43  jz      loc_180075BCD
0x180075b49  lea     rax, [rsp+1F0h+hKey]
0x180075b4e  mov     r9d, 20019h; samDesired
0x180075b54  xor     r8d, r8d; ulOptions
0x180075b57  mov     [rsp+1F0h+phkResult], rax; phkResult
0x180075b5c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MimeEdit\\MHTML Ex"...
0x180075b63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075b6a  call    cs:__imp_RegOpenKeyExA
0x180075b70  test    eax, eax
0x180075b72  jnz     short loc_180075BCD
0x180075b74  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180075b79  lea     rax, [rsp+1F0h+cSubKeys]
0x180075b7e  mov     [rsp+1F0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180075b83  xor     r9d, r9d; lpReserved
0x180075b86  mov     [rsp+1F0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180075b8b  xor     r8d, r8d; lpcchClass
0x180075b8e  mov     [rsp+1F0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180075b93  xor     edx, edx; lpClass
0x180075b95  mov     [rsp+1F0h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180075b9a  mov     [rsp+1F0h+lpcValues], rbx; lpcValues
0x180075b9f  mov     [rsp+1F0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180075ba4  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180075ba9  mov     [rsp+1F0h+phkResult], rax; lpcSubKeys
0x180075bae  call    cs:__imp_RegQueryInfoKeyA
0x180075bb4  test    eax, eax
0x180075bb6  jnz     short loc_180075BBE
0x180075bb8  add     edi, [rsp+1F0h+cSubKeys]
0x180075bbc  jmp     short loc_180075BC2
0x180075bbe  mov     [rsp+1F0h+cSubKeys], ebx
0x180075bc2  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180075bc7  call    cs:__imp_RegCloseKey
0x180075bcd  test    edi, edi
0x180075bcf  jnz     short loc_180075BD8
0x180075bd1  xor     eax, eax
0x180075bd3  jmp     loc_180075DFD
0x180075bd8  mov     eax, 1
0x180075bdd  lea     rcx, [rsp+1F0h+var_178]; void **
0x180075be2  cmp     edi, eax
0x180075be4  mov     edx, edi
0x180075be6  cmovb   edx, eax
0x180075be9  shl     edx, 3; unsigned int
0x180075bec  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x180075bf1  test    eax, eax
0x180075bf3  jnz     short loc_180075C05
0x180075bf5  mov     rsi, [rsp+1F0h+var_178]
0x180075bfa  mov     r14d, 8007000Eh
0x180075c00  jmp     loc_180075DCA
0x180075c05  mov     r14, [rsp+1F0h+var_178]
0x180075c0a  xor     edx, edx; Val
0x180075c0c  mov     r8d, edi
0x180075c0f  mov     rcx, r14; void *
0x180075c12  shl     r8, 3; Size
0x180075c16  call    memset_0
0x180075c1b  test    esi, esi
0x180075c1d  jz      short loc_180075C43
0x180075c1f  mov     rdx, r14; struct IMimeEditTagCollection **
0x180075c22  mov     rcx, r13; struct IHTMLDocument2 *
0x180075c25  call    ?CreateOEImageCollection@@YAJPEAUIHTMLDocument2@@PEAPEAUIMimeEditTagCollection@@@Z; CreateOEImageCollection(IHTMLDocument2 *,IMimeEditTagCollection * *)
0x180075c2a  not     eax
0x180075c2c  mov     rcx, r13; struct IHTMLDocument2 *
0x180075c2f  shr     eax, 1Fh
0x180075c32  mov     ebx, eax
0x180075c34  lea     rdx, [r14+rax*8]; struct IMimeEditTagCollection **
0x180075c38  call    ?CreateBGImageCollection@@YAJPEAUIHTMLDocument2@@PEAPEAUIMimeEditTagCollection@@@Z; CreateBGImageCollection(IHTMLDocument2 *,IMimeEditTagCollection * *)
0x180075c3d  test    eax, eax
0x180075c3f  js      short loc_180075C43
0x180075c41  inc     ebx
0x180075c43  test    r15d, r15d
0x180075c46  jz      short loc_180075C5C
0x180075c48  mov     eax, ebx
0x180075c4a  mov     rcx, r13; struct IHTMLDocument2 *
0x180075c4d  lea     rdx, [r14+rax*8]; struct IMimeEditTagCollection **
0x180075c51  call    ?CreateBGSoundCollection@@YAJPEAUIHTMLDocument2@@PEAPEAUIMimeEditTagCollection@@@Z; CreateBGSoundCollection(IHTMLDocument2 *,IMimeEditTagCollection * *)
0x180075c56  test    eax, eax
0x180075c58  js      short loc_180075C5C
0x180075c5a  inc     ebx
0x180075c5c  cmp     [rsp+1F0h+var_17C], 0
0x180075c61  jz      short loc_180075C77
0x180075c63  mov     eax, ebx
0x180075c65  mov     rcx, r13; struct IHTMLDocument2 *
0x180075c68  lea     rdx, [r14+rax*8]; struct IMimeEditTagCollection **
0x180075c6c  call    ?CreateActiveMovieCollection@@YAJPEAUIHTMLDocument2@@PEAPEAUIMimeEditTagCollection@@@Z; CreateActiveMovieCollection(IHTMLDocument2 *,IMimeEditTagCollection * *)
0x180075c71  test    eax, eax
0x180075c73  js      short loc_180075C77
0x180075c75  inc     ebx
0x180075c77  test    r12d, r12d
0x180075c7a  jz      loc_180075DB6
0x180075c80  cmp     [rsp+1F0h+cSubKeys], 0
0x180075c85  jz      loc_180075DB6
0x180075c8b  lea     rax, [rsp+1F0h+hKey]
0x180075c90  mov     r9d, 20019h; samDesired
0x180075c96  xor     r8d, r8d; ulOptions
0x180075c99  mov     [rsp+1F0h+phkResult], rax; phkResult
0x180075c9e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MimeEdit\\MHTML Ex"...
0x180075ca5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075cac  call    cs:__imp_RegOpenKeyExA
0x180075cb2  test    eax, eax
0x180075cb4  jnz     loc_180075DB6
0x180075cba  xor     esi, esi
0x180075cbc  cmp     [rsp+1F0h+cSubKeys], esi
0x180075cc0  jbe     loc_180075DAB
0x180075cc6  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180075ccb  lea     r9, [rsp+1F0h+cchName]; lpcchName
0x180075cd0  mov     [rsp+1F0h+lpcValues], 0; lpftLastWriteTime
0x180075cd9  lea     r8, [rbp+0F0h+Name]; lpName
0x180075cdd  mov     [rsp+1F0h+lpcbMaxClassLen], 0; lpcchClass
0x180075ce6  mov     edx, esi; dwIndex
0x180075ce8  mov     [rsp+1F0h+lpcbMaxSubKeyLen], 0; lpClass
0x180075cf1  mov     [rsp+1F0h+phkResult], 0; lpReserved
0x180075cfa  mov     [rsp+1F0h+cchName], 104h
0x180075d02  call    cs:__imp_RegEnumKeyExA
0x180075d08  cmp     eax, 103h
0x180075d0d  jz      loc_180075DAB
0x180075d13  test    eax, eax
0x180075d15  jnz     loc_180075D9F
0x180075d1b  lea     rdx, [rbp+0F0h+Name]
0x180075d1f  xor     ecx, ecx
0x180075d21  call    cs:__imp_PszToUnicode
0x180075d27  mov     r15, rax
0x180075d2a  test    rax, rax
0x180075d2d  jz      short loc_180075D9F
0x180075d2f  lea     rdx, [rbp+0F0h+iid]; lpiid
0x180075d33  mov     rcx, rax; lpsz
0x180075d36  call    cs:__imp_IIDFromString
0x180075d3c  test    eax, eax
0x180075d3e  jnz     short loc_180075D89
0x180075d40  mov     ecx, ebx
0x180075d42  lea     r9, IID_IMimeEditTagCollection; riid
0x180075d49  xor     edx, edx; pUnkOuter
0x180075d4b  lea     r8d, [rax+1]; dwClsContext
0x180075d4f  lea     r12, [r14+rcx*8]
0x180075d53  lea     rcx, [rbp+0F0h+iid]; rclsid
0x180075d57  mov     [rsp+1F0h+phkResult], r12; ppv
0x180075d5c  call    cs:__imp_CoCreateInstance
0x180075d62  test    eax, eax
0x180075d64  jnz     short loc_180075D89
0x180075d66  mov     rcx, [r12]
0x180075d6a  mov     rdx, r13
0x180075d6d  mov     rax, [rcx]
0x180075d70  mov     rax, [rax+18h]
0x180075d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d79  test    eax, eax
0x180075d7b  js      short loc_180075D81
0x180075d7d  inc     ebx
0x180075d7f  jmp     short loc_180075D89
0x180075d81  mov     rcx, r12
0x180075d84  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180075d89  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180075d90  mov     rdx, r15
0x180075d93  mov     rax, [rcx]
0x180075d96  mov     rax, [rax+28h]
0x180075d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d9f  inc     esi
0x180075da1  cmp     esi, [rsp+1F0h+cSubKeys]
0x180075da5  jb      loc_180075CC6
0x180075dab  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180075db0  call    cs:__imp_RegCloseKey
0x180075db6  mov     rax, [rbp+0F0h+var_170]
0x180075dba  mov     [rax], r14
0x180075dbd  mov     rax, [rbp+0F0h+var_168]
0x180075dc1  mov     [rax], ebx
0x180075dc3  xor     ebx, ebx
0x180075dc5  mov     esi, ebx
0x180075dc7  mov     r14d, ebx
0x180075dca  test    rsi, rsi
0x180075dcd  jz      short loc_180075DFA
0x180075dcf  test    edi, edi
0x180075dd1  jz      short loc_180075DE4
0x180075dd3  mov     eax, ebx
0x180075dd5  lea     rcx, [rsi+rax*8]
0x180075dd9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180075dde  inc     ebx
0x180075de0  cmp     ebx, edi
0x180075de2  jb      short loc_180075DD3
0x180075de4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180075deb  mov     rdx, rsi
0x180075dee  mov     r8, [rcx]
0x180075df1  mov     rax, [r8+28h]
0x180075df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dfa  mov     eax, r14d
0x180075dfd  mov     rcx, [rbp+0F0h+var_40]
0x180075e04  xor     rcx, rsp; StackCookie
0x180075e07  call    __security_check_cookie
0x180075e0c  mov     rbx, [rsp+1F0h+arg_0]
0x180075e14  add     rsp, 1C0h
0x180075e1b  pop     r15
0x180075e1d  pop     r14
0x180075e1f  pop     r13
0x180075e21  pop     r12
0x180075e23  pop     rdi
0x180075e24  pop     rsi
0x180075e25  pop     rbp
0x180075e26  retn
```
