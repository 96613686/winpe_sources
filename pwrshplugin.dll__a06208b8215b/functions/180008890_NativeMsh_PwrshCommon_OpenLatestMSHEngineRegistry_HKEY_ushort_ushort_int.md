# NativeMsh::PwrshCommon::OpenLatestMSHEngineRegistry(HKEY__ * *,ushort * *,ushort * *,int *)

- ea: `0x180008890`
- end: `0x180008b80`
- name: `?OpenLatestMSHEngineRegistry@PwrshCommon@NativeMsh@@IEAA_NPEAPEAUHKEY__@@PEAPEAG1PEAH@Z`
- size: `752`
- prototype: `bool __fastcall(NativeMsh::PwrshCommon *this, HKEY *, const unsigned __int16 **, const unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007c2c`

## callees

- `0x180001318`
- `0x1800079f4`
- `0x180008890`
- `0x180008b88`
- `0x180008d34`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180008962`
- `msvcrt!wcschr` at `0x180008970`
- `msvcrt!wcschr` at `0x180008962`
- `msvcrt!wcschr` at `0x180008970`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b67`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008b67`
- `ADVAPI32!RegEnumKeyExW` at `0x180008aaa`
- `ADVAPI32!RegEnumKeyExW` at `0x180008aaa`
- `ADVAPI32!RegCloseKey` at `0x180008b59`
- `ADVAPI32!RegCloseKey` at `0x180008b59`

## pseudocode

```c
bool __fastcall NativeMsh::PwrshCommon::OpenLatestMSHEngineRegistry(
        NativeMsh::PwrshCommon *this,
        HKEY *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4,
        int *a5)
{
  const unsigned __int16 *v8; // r8
  bool v9; // bl
  WCHAR *v10; // rdi
  int v11; // esi
  void *v12; // rbx
  DWORD i; // edx
  wchar_t *v14; // rsi
  wchar_t *v15; // rax
  NativeMsh::PwrshCommon *v16; // rcx
  wchar_t *v17; // rax
  unsigned __int64 v18; // rsi
  _WORD *v19; // rax
  __int64 v20; // rcx
  WCHAR *v21; // rdx
  _WORD *v22; // rcx
  unsigned int v23; // eax
  int v25; // [rsp+40h] [rbp-28h]
  int v26; // [rsp+44h] [rbp-24h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-20h] BYREF
  DWORD dwIndex; // [rsp+4Ch] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-10h] BYREF

  hKey = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v10 = 0;
    goto LABEL_41;
  }
  v8 = *a4;
  *a5 = -1;
  if ( !NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(this, L"SOFTWARE\\Microsoft\\PowerShell", v8, &hKey) )
    return 0;
  v10 = (WCHAR *)operator new[](0x200u);
  if ( !v10 )
    goto LABEL_41;
  v25 = 0;
  v11 = 0;
  v12 = 0;
  dwIndex = 1;
  for ( i = 0; ; i = dwIndex++ )
  {
    ftLastWriteTime = 0;
    cchName = 256;
    v23 = RegEnumKeyExW(hKey, i, v10, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v23 == 259 )
      break;
    if ( v23 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *))(**((_QWORD **)this + 1) + 16LL))(
        *((_QWORD *)this + 1),
        v23,
        19,
        L"SOFTWARE\\Microsoft\\PowerShell");
      goto LABEL_41;
    }
    v26 = 0;
    if ( *v10 )
    {
      v14 = wcschr(v10, 0x2Eu);
      v15 = wcschr(v10, 0);
      if ( !v15 )
        goto LABEL_31;
      if ( v14 )
      {
        if ( !NativeMsh::PwrshCommon::ParseInt(v16, v10, v14, &v26) )
          goto LABEL_31;
        v17 = v14 + 1;
      }
      else
      {
        if ( !NativeMsh::PwrshCommon::ParseInt(v16, v10, v15, &v26) )
          goto LABEL_31;
        v17 = 0;
      }
      v11 = v25;
      if ( !v17 && v26 > v25 )
      {
        v18 = cchName + 1;
        if ( v12 )
          operator delete[](v12);
        v19 = operator new[](saturated_mul(v18, 2u));
        v12 = v19;
        if ( !v19 || !v18 )
          goto LABEL_41;
        if ( v18 > 0x7FFFFFFF )
        {
          *v19 = 0;
          goto LABEL_41;
        }
        v20 = 2147483646;
        v25 = v26;
        v21 = v10;
        do
        {
          if ( !v20 )
            break;
          if ( !*v21 )
            break;
          *v19++ = *v21++;
          --v20;
          --v18;
        }
        while ( v18 );
        v22 = v19 - 1;
        if ( v18 )
          v22 = v19;
        *v22 = 0;
        if ( !v18 )
          goto LABEL_41;
LABEL_31:
        v11 = v25;
      }
    }
  }
  if ( !v12 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), 0, 29);
    goto LABEL_41;
  }
  *a4 = (const unsigned __int16 *)v12;
  *a5 = v11;
  if ( NativeMsh::PwrshCommon::FormatStringWithErrorReporting(
         this,
         L"SOFTWARE\\Microsoft\\PowerShell\\%1!ls!\\PowerShellEngine",
         (unsigned __int16 **)a3,
         &dwIndex,
         23,
         v12) )
  {
    v9 = NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(this, *a3, *a4, a2);
    goto LABEL_42;
  }
LABEL_41:
  v9 = 0;
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    operator delete[](v10);
  return v9;
}

```

## disassembly

```asm
0x180008890  mov     [rsp-40h+arg_8], rdx
0x180008895  push    rbp
0x180008896  push    rbx
0x180008897  push    rsi
0x180008898  push    rdi
0x180008899  push    r12
0x18000889b  push    r13
0x18000889d  push    r14
0x18000889f  push    r15
0x1800088a1  mov     rbp, rsp
0x1800088a4  sub     rsp, 68h
0x1800088a8  mov     r15, r9
0x1800088ab  mov     r13, r8
0x1800088ae  xor     r9d, r9d
0x1800088b1  mov     r14, rcx
0x1800088b4  mov     [rbp+hKey], r9
0x1800088b8  test    rdx, rdx
0x1800088bb  jz      loc_180008B4A
0x1800088c1  test    r8, r8
0x1800088c4  jz      loc_180008B4A
0x1800088ca  test    r15, r15
0x1800088cd  jz      loc_180008B4A
0x1800088d3  mov     r12, [rbp+arg_20]
0x1800088d7  test    r12, r12
0x1800088da  jz      loc_180008B4A
0x1800088e0  mov     r8, [r15]; unsigned __int16 *
0x1800088e3  lea     r9, [rbp+hKey]; HKEY *
0x1800088e7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\PowerShell"
0x1800088ee  mov     dword ptr [r12], 0FFFFFFFFh
0x1800088f6  call    ?RegOpenKeyWithErrorReport@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAPEAUHKEY__@@@Z; NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(ushort const *,ushort const *,HKEY__ * *)
0x1800088fb  xor     ecx, ecx
0x1800088fd  test    al, al
0x1800088ff  jnz     short loc_180008908
0x180008901  mov     bl, cl
0x180008903  jmp     loc_180008B6D
0x180008908  mov     ecx, 200h; unsigned __int64
0x18000890d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008912  xor     r9d, r9d
0x180008915  mov     rdi, rax
0x180008918  test    rax, rax
0x18000891b  jz      loc_180008B4D
0x180008921  lea     rax, [rbp+ftLastWriteTime]
0x180008925  mov     [rbp+var_28], r9d
0x180008929  mov     [rsp+68h+lpftLastWriteTime], rax
0x18000892e  mov     esi, r9d
0x180008931  mov     ebx, r9d
0x180008934  mov     [rbp+dwIndex], 1
0x18000893b  xor     edx, edx
0x18000893d  jmp     loc_180008A85
0x180008942  xor     r9d, r9d
0x180008945  test    edx, edx
0x180008947  jnz     loc_180008AE0
0x18000894d  mov     [rbp+var_24], r9d
0x180008951  cmp     r9w, [rdi]
0x180008955  jz      loc_180008A72
0x18000895b  lea     edx, [r9+2Eh]; Ch
0x18000895f  mov     rcx, rdi; Str
0x180008962  call    cs:__imp_wcschr
0x180008968  xor     edx, edx; Ch
0x18000896a  mov     rcx, rdi; Str
0x18000896d  mov     rsi, rax
0x180008970  call    cs:__imp_wcschr
0x180008976  xor     r9d, r9d
0x180008979  test    rax, rax
0x18000897c  jz      loc_180008A6F
0x180008982  lea     r9, [rbp+var_24]; int *
0x180008986  mov     rdx, rdi; unsigned __int16 *
0x180008989  test    rsi, rsi
0x18000898c  jz      short loc_1800089A7
0x18000898e  mov     r8, rsi; unsigned __int16 *
0x180008991  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180008996  xor     r9d, r9d
0x180008999  test    al, al
0x18000899b  jz      loc_180008A6F
0x1800089a1  lea     rax, [rsi+2]
0x1800089a5  jmp     short loc_1800089BD
0x1800089a7  mov     r8, rax; unsigned __int16 *
0x1800089aa  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800089af  xor     r9d, r9d
0x1800089b2  test    al, al
0x1800089b4  jz      loc_180008A6F
0x1800089ba  mov     eax, r9d
0x1800089bd  mov     esi, [rbp+var_28]
0x1800089c0  test    rax, rax
0x1800089c3  jnz     loc_180008A72
0x1800089c9  cmp     [rbp+var_24], esi
0x1800089cc  jle     loc_180008A72
0x1800089d2  mov     esi, [rbp+cchName]
0x1800089d5  inc     esi
0x1800089d7  test    rbx, rbx
0x1800089da  jz      short loc_1800089E5
0x1800089dc  mov     rcx, rbx
0x1800089df  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800089e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800089ec  mov     eax, 2
0x1800089f1  mul     rsi
0x1800089f4  cmovb   rax, rcx
0x1800089f8  mov     rcx, rax; unsigned __int64
0x1800089fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008a00  xor     r9d, r9d
0x180008a03  mov     rbx, rax
0x180008a06  test    rax, rax
0x180008a09  jz      loc_180008B4D
0x180008a0f  test    rsi, rsi
0x180008a12  jz      loc_180008B4D
0x180008a18  cmp     rsi, 7FFFFFFFh
0x180008a1f  ja      loc_180008ADA
0x180008a25  mov     eax, [rbp+var_24]
0x180008a28  mov     ecx, 7FFFFFFEh
0x180008a2d  mov     [rbp+var_28], eax
0x180008a30  mov     rdx, rdi
0x180008a33  mov     rax, rbx
0x180008a36  test    rcx, rcx
0x180008a39  jz      short loc_180008A5A
0x180008a3b  movzx   r8d, word ptr [rdx]
0x180008a3f  test    r8w, r8w
0x180008a43  jz      short loc_180008A5A
0x180008a45  mov     [rax], r8w
0x180008a49  add     rdx, 2
0x180008a4d  add     rax, 2
0x180008a51  dec     rcx
0x180008a54  sub     rsi, 1
0x180008a58  jnz     short loc_180008A36
0x180008a5a  test    rsi, rsi
0x180008a5d  lea     rcx, [rax-2]
0x180008a61  cmovnz  rcx, rax
0x180008a65  mov     [rcx], r9w
0x180008a69  jz      loc_180008B4D
0x180008a6f  mov     esi, [rbp+var_28]
0x180008a72  mov     eax, [rbp+dwIndex]
0x180008a75  lea     rcx, [rbp+ftLastWriteTime]
0x180008a79  mov     edx, eax; dwIndex
0x180008a7b  mov     [rsp+68h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180008a80  inc     eax
0x180008a82  mov     [rbp+dwIndex], eax
0x180008a85  mov     rcx, [rbp+hKey]; hKey
0x180008a89  mov     r8, rdi; lpName
0x180008a8c  mov     [rsp+68h+lpcchClass], r9; lpcchClass
0x180008a91  mov     [rsp+68h+lpClass], r9; lpClass
0x180008a96  mov     [rsp+68h+lpReserved], r9; lpReserved
0x180008a9b  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], r9
0x180008a9f  lea     r9, [rbp+cchName]; lpcchName
0x180008aa3  mov     [rbp+cchName], 100h
0x180008aaa  call    cs:__imp_RegEnumKeyExW
0x180008ab0  mov     edx, eax
0x180008ab2  cmp     eax, 103h
0x180008ab7  jnz     loc_180008942
0x180008abd  test    rbx, rbx
0x180008ac0  jnz     short loc_180008B02
0x180008ac2  mov     rcx, [r14+8]
0x180008ac6  lea     r8d, [rbx+1Dh]
0x180008aca  xor     edx, edx
0x180008acc  mov     rax, [rcx]
0x180008acf  mov     rax, [rax+8]
0x180008ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad8  jmp     short loc_180008AFD
0x180008ada  mov     [rax], r9w
0x180008ade  jmp     short loc_180008B4D
0x180008ae0  mov     rcx, [r14+8]
0x180008ae4  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\PowerShell"
0x180008aeb  mov     r8d, 13h
0x180008af1  mov     rax, [rcx]
0x180008af4  mov     rax, [rax+10h]
0x180008af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008afd  xor     r9d, r9d
0x180008b00  jmp     short loc_180008B4D
0x180008b02  mov     [rsp+68h+lpClass], rbx
0x180008b07  lea     r9, [rbp+dwIndex]; unsigned int *
0x180008b0b  mov     r8, r13; unsigned __int16 **
0x180008b0e  mov     dword ptr [rsp+68h+lpReserved], 17h; int
0x180008b16  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\PowerShell\\%1!ls!"...
0x180008b1d  mov     [r15], rbx
0x180008b20  mov     rcx, r14; this
0x180008b23  mov     [r12], esi
0x180008b27  call    ?FormatStringWithErrorReporting@PwrshCommon@NativeMsh@@IEAA_NPEBGPEAPEAGPEAKHZZ; NativeMsh::PwrshCommon::FormatStringWithErrorReporting(ushort const *,ushort * *,ulong *,int,...)
0x180008b2c  xor     r9d, r9d
0x180008b2f  test    al, al
0x180008b31  jz      short loc_180008B4D
0x180008b33  mov     r9, [rbp+arg_8]; HKEY *
0x180008b37  mov     rcx, r14; this
0x180008b3a  mov     r8, [r15]; unsigned __int16 *
0x180008b3d  mov     rdx, [r13+0]; unsigned __int16 *
0x180008b41  call    ?RegOpenKeyWithErrorReport@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAPEAUHKEY__@@@Z; NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(ushort const *,ushort const *,HKEY__ * *)
0x180008b46  mov     bl, al
0x180008b48  jmp     short loc_180008B50
0x180008b4a  mov     rdi, r9
0x180008b4d  mov     bl, r9b
0x180008b50  mov     rcx, [rbp+hKey]; hKey
0x180008b54  test    rcx, rcx
0x180008b57  jz      short loc_180008B5F
0x180008b59  call    cs:__imp_RegCloseKey
0x180008b5f  test    rdi, rdi
0x180008b62  jz      short loc_180008B6D
0x180008b64  mov     rcx, rdi
0x180008b67  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008b6d  mov     al, bl
0x180008b6f  add     rsp, 68h
0x180008b73  pop     r15
0x180008b75  pop     r14
0x180008b77  pop     r13
0x180008b79  pop     r12
0x180008b7b  pop     rdi
0x180008b7c  pop     rsi
0x180008b7d  pop     rbx
0x180008b7e  pop     rbp
0x180008b7f  retn
```
