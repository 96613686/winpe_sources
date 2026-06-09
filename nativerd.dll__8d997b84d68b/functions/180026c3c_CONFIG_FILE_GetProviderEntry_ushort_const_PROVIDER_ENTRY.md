# CONFIG_FILE::GetProviderEntry(ushort const *,PROVIDER_ENTRY * *)

- ea: `0x180026c3c`
- end: `0x18002708d`
- name: `?GetProviderEntry@CONFIG_FILE@@QEAAJPEBGPEAPEAVPROVIDER_ENTRY@@@Z`
- size: `1105`
- prototype: `__int64 __fastcall(CONFIG_FILE *__hidden this, const unsigned __int16 *, struct PROVIDER_ENTRY **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800124bc`
- `0x18002eb10`

## callees

- `0x180011130`
- `0x180014b34`
- `0x18001c250`
- `0x180025fac`
- `0x180026c3c`
- `0x180027094`
- `0x1800306c0`
- `0x18004778c`
- `0x180047a6c`
- `0x180047b0c`
- `0x180059bf6`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180026e02`
- `msvcrt!wcsstr` at `0x180026e92`
- `msvcrt!wcsstr` at `0x180026eac`
- `msvcrt!wcsstr` at `0x180026f08`
- `msvcrt!wcsstr` at `0x180026e02`
- `msvcrt!wcsstr` at `0x180026e92`
- `msvcrt!wcsstr` at `0x180026eac`
- `msvcrt!wcsstr` at `0x180026f08`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026f80`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026f80`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180026f68`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180026f68`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180027002`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180027002`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026e3e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026fe3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026fed`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026e3e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026fe3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026fed`

## string_xrefs

- `0x180026dfb`: `System.Configuration.DpapiProtectedConfigurationProvider`
- `0x180026e8b`: `System.Configuration.RsaProtectedConfigurationProvider`
- `0x180026ea5`: `Microsoft.ApplicationHost.AesProtectedConfigurationProvider`
- `0x180026f01`: `Microsoft.ApplicationHost.CngProtectedConfigurationProvider`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::GetProviderEntry(CONFIG_FILE *this, wchar_t *a2, struct PROVIDER_ENTRY **a3)
{
  struct PROVIDER_ENTRY **v3; // r13
  CONFIG_ELEMENT *v5; // r14
  int ProvidersElement; // edi
  __int64 v7; // rcx
  unsigned int i; // r15d
  PROVIDER_ENTRY *v9; // rbx
  const unsigned __int16 *Name; // rax
  char *v11; // r8
  int v12; // ecx
  int v13; // edx
  int ChildElement; // eax
  __int64 v15; // r12
  __int64 j; // r15
  struct CONFIG_ELEMENT *v17; // r13
  wchar_t *v18; // rax
  int v19; // ecx
  int v20; // edx
  PROVIDER_ENTRY *v21; // rax
  PROVIDER_ENTRY *v22; // rax
  PROVIDER_ENTRY *v23; // rax
  PROVIDER_ENTRY *v24; // rax
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rdx
  struct CONFIG_ELEMENT *v28; // [rsp+30h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+48h] BYREF
  struct PROVIDER_ENTRY **v30; // [rsp+90h] [rbp+50h]
  wchar_t *Str; // [rsp+98h] [rbp+58h] BYREF

  v30 = a3;
  String1 = a2;
  v3 = a3;
  v28 = 0;
  Str = 0;
  v5 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  ProvidersElement = CONFIG_FILE::GetProvidersElement(this);
  if ( ProvidersElement < 0 )
    return (unsigned int)ProvidersElement;
  v7 = *((_QWORD *)this + 35);
  if ( !v7 )
    return (unsigned int)-2147023483;
  if ( !String1 )
  {
    (*(void (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)(v7 + 16) + 64LL))(
      v7 + 16,
      L"defaultProvider",
      &String1,
      0,
      0);
    if ( !String1 )
      return (unsigned int)-2147023483;
  }
  for ( i = 0; ; ++i )
  {
    v9 = 0;
    if ( i >= *((_DWORD *)this + 74) )
      goto LABEL_16;
    v9 = *(PROVIDER_ENTRY **)(*((_QWORD *)this + 36) + 8LL * i);
    Name = PROVIDER_ENTRY::QueryName(v9);
    v11 = (char *)((char *)String1 - (char *)Name);
    do
    {
      v12 = *(unsigned __int16 *)&v11[(_QWORD)Name];
      v13 = *Name - v12;
      if ( v13 )
        break;
      ++Name;
    }
    while ( v12 );
    if ( !v13 )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
  if ( v9 )
    goto LABEL_48;
LABEL_16:
  ChildElement = CONFIG_ELEMENT::GetChildElement(*((CONFIG_ELEMENT **)this + 35), L"providers", &v28);
  v5 = v28;
  ProvidersElement = ChildElement;
  if ( ChildElement < 0 )
    goto LABEL_51;
  v15 = *((_QWORD *)v28 + 11);
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= *(_DWORD *)(v15 + 32) )
      goto LABEL_45;
    v17 = *(struct CONFIG_ELEMENT **)(*(_QWORD *)(v15 + 40) + 24 * j);
    ProvidersElement = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*((_QWORD *)v17 + 2) + 64LL))(
                         (_QWORD *)v17 + 2,
                         L"name",
                         &Str,
                         0,
                         0);
    if ( ProvidersElement < 0 )
      goto LABEL_51;
    v18 = Str;
    do
    {
      v19 = *(wchar_t *)((char *)v18 + (char *)String1 - (char *)Str);
      v20 = *v18 - v19;
      if ( v20 )
        break;
      ++v18;
    }
    while ( v19 );
    if ( !v20 )
      break;
  }
  ProvidersElement = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*((_QWORD *)v17 + 2) + 64LL))(
                       (_QWORD *)v17 + 2,
                       L"type",
                       &Str,
                       0,
                       0);
  if ( ProvidersElement < 0 )
    goto LABEL_51;
  if ( wcsstr(Str, L"System.Configuration.DpapiProtectedConfigurationProvider") )
  {
    v21 = (PROVIDER_ENTRY *)operator new(0x68u);
    v9 = v21;
    if ( v21 )
    {
      PROVIDER_ENTRY::PROVIDER_ENTRY(v21, v17, 0, 0);
      *(_QWORD *)v9 = &DPAPI_PROVIDER_ENTRY::`vftable';
      STRU::STRU((PROVIDER_ENTRY *)((char *)v9 + 40));
      *((_DWORD *)v9 + 24) = 0;
      goto LABEL_42;
    }
LABEL_29:
    ProvidersElement = -2147024888;
    goto LABEL_51;
  }
  if ( !wcscmp_0(String1, L"IISWASOnlyRsaProvider")
    || !wcscmp_0(String1, L"IISRsaProvider")
    || wcsstr(Str, L"System.Configuration.RsaProtectedConfigurationProvider") )
  {
    v24 = (PROVIDER_ENTRY *)operator new(0xA0u);
    v9 = v24;
    if ( !v24 )
      goto LABEL_29;
    PROVIDER_ENTRY::PROVIDER_ENTRY(v24, v17, *((void **)this + 17), *((void **)this + 18));
    *(_QWORD *)v9 = &RSA_PROVIDER_ENTRY::`vftable';
    STRU::STRU((PROVIDER_ENTRY *)((char *)v9 + 40));
    STRU::STRU((PROVIDER_ENTRY *)((char *)v9 + 96));
    *((_QWORD *)v9 + 19) = 1;
  }
  else if ( wcsstr(Str, L"Microsoft.ApplicationHost.AesProtectedConfigurationProvider") )
  {
    v22 = (PROVIDER_ENTRY *)operator new(0x40u);
    v9 = v22;
    if ( !v22 )
      goto LABEL_29;
    PROVIDER_ENTRY::PROVIDER_ENTRY(v22, v17, *((void **)this + 17), *((void **)this + 18));
    *((_QWORD *)v9 + 5) = 0;
    *(_QWORD *)v9 = &AES_PROVIDER_ENTRY::`vftable';
    *((_QWORD *)v9 + 6) = 0;
    *((_QWORD *)v9 + 7) = 0;
  }
  else
  {
    if ( !wcsstr(Str, L"Microsoft.ApplicationHost.CngProtectedConfigurationProvider") )
    {
LABEL_39:
      ProvidersElement = -2147023483;
      goto LABEL_51;
    }
    v23 = (PROVIDER_ENTRY *)operator new(0x150u);
    v9 = v23;
    if ( !v23 )
      goto LABEL_29;
    PROVIDER_ENTRY::PROVIDER_ENTRY(v23, v17, *((void **)this + 17), *((void **)this + 18));
    *((_QWORD *)v9 + 5) = 0;
    *(_QWORD *)v9 = &CNG_PROVIDER_ENTRY::`vftable';
    *((_QWORD *)v9 + 6) = 0;
    BUFFER::BUFFER((PROVIDER_ENTRY *)((char *)v9 + 56), (unsigned __int8 *)v9 + 104, 0x20u);
    STRU::STRU((PROVIDER_ENTRY *)((char *)v9 + 136), (unsigned __int16 *)v9 + 96, 0x40u);
    *((_QWORD *)v9 + 40) = 0;
    *((_DWORD *)v9 + 82) = 0;
    *((_DWORD *)v9 + 83) = 32;
  }
LABEL_42:
  v25 = STRU::QueryStr((CONFIG_FILE *)((char *)this + 72));
  v26 = &szDomain;
  if ( *((_QWORD *)this + 5) )
    v26 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  ProvidersElement = PROVIDER_ENTRY::Initialize(v9, v26, v25);
  if ( ProvidersElement < 0 )
    goto LABEL_49;
LABEL_45:
  ProvidersElement = ARRAY_LIST::AddEntry((CONFIG_FILE *)((char *)this + 288), v9, 0xFFFFFFFF);
  if ( ProvidersElement < 0 )
  {
LABEL_49:
    if ( v9 )
      PROVIDER_ENTRY::DereferenceProviderEntry(v9);
    goto LABEL_51;
  }
  _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
  if ( !v9 )
    goto LABEL_39;
  v3 = v30;
LABEL_48:
  *v3 = v9;
LABEL_51:
  if ( v5 )
    CONFIG_ELEMENT::DereferenceConfigElement(v5);
  return (unsigned int)ProvidersElement;
}

```

## disassembly

```asm
0x180026c3c  mov     [rsp-38h+arg_0], rbx
0x180026c41  mov     [rsp-38h+arg_10], r8
0x180026c46  mov     [rsp-38h+String1], rdx
0x180026c4b  push    rbp
0x180026c4c  push    rsi
0x180026c4d  push    rdi
0x180026c4e  push    r12
0x180026c50  push    r13
0x180026c52  push    r14
0x180026c54  push    r15
0x180026c56  mov     rbp, rsp
0x180026c59  sub     rsp, 40h
0x180026c5d  xor     r12d, r12d
0x180026c60  mov     r13, r8
0x180026c63  mov     [rbp+var_10], r12
0x180026c67  mov     rsi, rcx
0x180026c6a  mov     [rbp+Str], r12
0x180026c6e  mov     r14d, r12d
0x180026c71  test    r8, r8
0x180026c74  jnz     short loc_180026C80
0x180026c76  mov     edi, 80070057h
0x180026c7b  jmp     loc_180027073
0x180026c80  call    ?GetProvidersElement@CONFIG_FILE@@AEAAJXZ; CONFIG_FILE::GetProvidersElement(void)
0x180026c85  mov     edi, eax
0x180026c87  test    eax, eax
0x180026c89  js      loc_180027073
0x180026c8f  mov     rcx, [rsi+118h]
0x180026c96  test    rcx, rcx
0x180026c99  jnz     short loc_180026CA5
0x180026c9b  mov     edi, 80070585h
0x180026ca0  jmp     loc_180027073
0x180026ca5  cmp     [rbp+String1], r12
0x180026ca9  jnz     short loc_180026CD4
0x180026cab  add     rcx, 10h
0x180026caf  mov     [rsp+40h+var_20], r12
0x180026cb4  xor     r9d, r9d
0x180026cb7  lea     r8, [rbp+String1]
0x180026cbb  lea     rdx, aDefaultprovide; "defaultProvider"
0x180026cc2  mov     rax, [rcx]
0x180026cc5  mov     rax, [rax+40h]
0x180026cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cce  cmp     [rbp+String1], r12
0x180026cd2  jz      short loc_180026C9B
0x180026cd4  mov     r15d, r12d
0x180026cd7  mov     rbx, r12
0x180026cda  cmp     r15d, [rsi+128h]
0x180026ce1  jnb     short loc_180026D2A
0x180026ce3  mov     rax, [rsi+120h]
0x180026cea  mov     ecx, r15d
0x180026ced  mov     rbx, [rax+rcx*8]
0x180026cf1  mov     rcx, rbx; this
0x180026cf4  call    ?QueryName@PROVIDER_ENTRY@@QEAAPEBGXZ; PROVIDER_ENTRY::QueryName(void)
0x180026cf9  mov     r8, [rbp+String1]
0x180026cfd  sub     r8, rax
0x180026d00  movzx   edx, word ptr [rax]
0x180026d03  movzx   ecx, word ptr [rax+r8]
0x180026d08  sub     edx, ecx
0x180026d0a  jnz     short loc_180026D14
0x180026d0c  add     rax, 2
0x180026d10  test    ecx, ecx
0x180026d12  jnz     short loc_180026D00
0x180026d14  test    edx, edx
0x180026d16  jz      short loc_180026D1D
0x180026d18  inc     r15d
0x180026d1b  jmp     short loc_180026CD7
0x180026d1d  lock inc dword ptr [rbx+8]
0x180026d21  test    rbx, rbx
0x180026d24  jnz     loc_180027053
0x180026d2a  mov     rcx, [rsi+118h]; this
0x180026d31  lea     r8, [rbp+var_10]; struct CONFIG_ELEMENT **
0x180026d35  lea     rdx, aProviders; "providers"
0x180026d3c  call    ?GetChildElement@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAV1@@Z; CONFIG_ELEMENT::GetChildElement(ushort const *,CONFIG_ELEMENT * *)
0x180026d41  mov     r14, [rbp+var_10]
0x180026d45  mov     edi, eax
0x180026d47  test    eax, eax
0x180026d49  js      loc_180027066
0x180026d4f  mov     r12, [r14+58h]
0x180026d53  xor     r15d, r15d
0x180026d56  cmp     r15d, [r12+20h]
0x180026d5b  jnb     loc_180027029
0x180026d61  mov     rax, [r12+28h]
0x180026d66  lea     rcx, [r15+r15*2]
0x180026d6a  xor     r9d, r9d
0x180026d6d  mov     [rsp+40h+var_20], 0
0x180026d76  lea     r8, [rbp+Str]
0x180026d7a  lea     rdx, aName; "name"
0x180026d81  mov     r13, [rax+rcx*8]
0x180026d85  lea     rcx, [r13+10h]
0x180026d89  mov     rax, [rcx]
0x180026d8c  mov     rax, [rax+40h]
0x180026d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d95  mov     edi, eax
0x180026d97  test    eax, eax
0x180026d99  js      loc_180027066
0x180026d9f  mov     rax, [rbp+Str]
0x180026da3  mov     r8, [rbp+String1]
0x180026da7  sub     r8, rax
0x180026daa  movzx   edx, word ptr [rax]
0x180026dad  movzx   ecx, word ptr [rax+r8]
0x180026db2  sub     edx, ecx
0x180026db4  jnz     short loc_180026DBE
0x180026db6  add     rax, 2
0x180026dba  test    ecx, ecx
0x180026dbc  jnz     short loc_180026DAA
0x180026dbe  test    edx, edx
0x180026dc0  jz      short loc_180026DC7
0x180026dc2  inc     r15d
0x180026dc5  jmp     short loc_180026D56
0x180026dc7  lea     rcx, [r13+10h]
0x180026dcb  xor     r12d, r12d
0x180026dce  mov     rax, [rcx]
0x180026dd1  lea     r8, [rbp+Str]
0x180026dd5  xor     r9d, r9d
0x180026dd8  mov     [rsp+40h+var_20], r12
0x180026ddd  lea     rdx, aType; "type"
0x180026de4  mov     rax, [rax+40h]
0x180026de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ded  mov     edi, eax
0x180026def  test    eax, eax
0x180026df1  js      loc_180027066
0x180026df7  mov     rcx, [rbp+Str]; Str
0x180026dfb  lea     rdx, aSystemConfigur_0; "System.Configuration.DpapiProtectedConf"...
0x180026e02  call    cs:__imp_wcsstr
0x180026e08  test    rax, rax
0x180026e0b  jz      short loc_180026E57
0x180026e0d  lea     ecx, [r12+68h]; Size
0x180026e12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026e17  mov     rbx, rax
0x180026e1a  test    rax, rax
0x180026e1d  jz      short loc_180026E4D
0x180026e1f  xor     r9d, r9d; void *
0x180026e22  xor     r8d, r8d; void *
0x180026e25  mov     rdx, r13; struct CONFIG_ELEMENT *
0x180026e28  mov     rcx, rax; this
0x180026e2b  call    ??0PROVIDER_ENTRY@@QEAA@PEAVCONFIG_ELEMENT@@PEAX1@Z; PROVIDER_ENTRY::PROVIDER_ENTRY(CONFIG_ELEMENT *,void *,void *)
0x180026e30  lea     rax, ??_7DPAPI_PROVIDER_ENTRY@@6B@; const DPAPI_PROVIDER_ENTRY::`vftable'
0x180026e37  lea     rcx, [rbx+28h]
0x180026e3b  mov     [rbx], rax
0x180026e3e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180026e44  mov     [rbx+60h], r12d
0x180026e48  jmp     loc_180026FFE
0x180026e4d  mov     edi, 80070008h
0x180026e52  jmp     loc_180027066
0x180026e57  mov     rcx, [rbp+String1]; String1
0x180026e5b  lea     rdx, aIiswasonlyrsap; "IISWASOnlyRsaProvider"
0x180026e62  call    wcscmp_0
0x180026e67  test    eax, eax
0x180026e69  jz      loc_180026FA6
0x180026e6f  mov     rcx, [rbp+String1]; String1
0x180026e73  lea     rdx, aIisrsaprovider; "IISRsaProvider"
0x180026e7a  call    wcscmp_0
0x180026e7f  test    eax, eax
0x180026e81  jz      loc_180026FA6
0x180026e87  mov     rcx, [rbp+Str]; Str
0x180026e8b  lea     rdx, aSystemConfigur; "System.Configuration.RsaProtectedConfig"...
0x180026e92  call    cs:__imp_wcsstr
0x180026e98  test    rax, rax
0x180026e9b  jnz     loc_180026FA6
0x180026ea1  mov     rcx, [rbp+Str]; Str
0x180026ea5  lea     rdx, aMicrosoftAppli; "Microsoft.ApplicationHost.AesProtectedC"...
0x180026eac  call    cs:__imp_wcsstr
0x180026eb2  test    rax, rax
0x180026eb5  jz      short loc_180026EFD
0x180026eb7  mov     ecx, 40h ; '@'; Size
0x180026ebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026ec1  mov     rbx, rax
0x180026ec4  test    rax, rax
0x180026ec7  jz      short loc_180026E4D
0x180026ec9  mov     r9, [rsi+90h]; void *
0x180026ed0  mov     rdx, r13; struct CONFIG_ELEMENT *
0x180026ed3  mov     r8, [rsi+88h]; void *
0x180026eda  mov     rcx, rax; this
0x180026edd  call    ??0PROVIDER_ENTRY@@QEAA@PEAVCONFIG_ELEMENT@@PEAX1@Z; PROVIDER_ENTRY::PROVIDER_ENTRY(CONFIG_ELEMENT *,void *,void *)
0x180026ee2  lea     rax, ??_7AES_PROVIDER_ENTRY@@6B@; const AES_PROVIDER_ENTRY::`vftable'
0x180026ee9  mov     [rbx+28h], r12
0x180026eed  mov     [rbx], rax
0x180026ef0  mov     [rbx+30h], r12
0x180026ef4  mov     [rbx+38h], r12
0x180026ef8  jmp     loc_180026FFE
0x180026efd  mov     rcx, [rbp+Str]; Str
0x180026f01  lea     rdx, aMicrosoftAppli_0; "Microsoft.ApplicationHost.CngProtectedC"...
0x180026f08  call    cs:__imp_wcsstr
0x180026f0e  test    rax, rax
0x180026f11  jz      loc_180026F9C
0x180026f17  mov     ecx, 150h; Size
0x180026f1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026f21  mov     rbx, rax
0x180026f24  test    rax, rax
0x180026f27  jz      loc_180026E4D
0x180026f2d  mov     r9, [rsi+90h]; void *
0x180026f34  mov     rdx, r13; struct CONFIG_ELEMENT *
0x180026f37  mov     r8, [rsi+88h]; void *
0x180026f3e  mov     rcx, rax; this
0x180026f41  call    ??0PROVIDER_ENTRY@@QEAA@PEAVCONFIG_ELEMENT@@PEAX1@Z; PROVIDER_ENTRY::PROVIDER_ENTRY(CONFIG_ELEMENT *,void *,void *)
0x180026f46  lea     rax, ??_7CNG_PROVIDER_ENTRY@@6B@; const CNG_PROVIDER_ENTRY::`vftable'
0x180026f4d  mov     [rbx+28h], r12
0x180026f51  mov     edi, 20h ; ' '
0x180026f56  mov     [rbx], rax
0x180026f59  mov     r8d, edi
0x180026f5c  mov     [rbx+30h], r12
0x180026f60  lea     rdx, [rbx+68h]
0x180026f64  lea     rcx, [rbx+38h]
0x180026f68  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180026f6e  lea     rdx, [rbx+0C0h]
0x180026f75  lea     rcx, [rbx+88h]
0x180026f7c  lea     r8d, [rdi+20h]
0x180026f80  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026f86  mov     [rbx+140h], r12
0x180026f8d  mov     [rbx+148h], r12d
0x180026f94  mov     [rbx+14Ch], edi
0x180026f9a  jmp     short loc_180026FFE
0x180026f9c  mov     edi, 80070585h
0x180026fa1  jmp     loc_180027066
0x180026fa6  mov     ecx, 0A0h; Size
0x180026fab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026fb0  mov     rbx, rax
0x180026fb3  test    rax, rax
0x180026fb6  jz      loc_180026E4D
0x180026fbc  mov     r9, [rsi+90h]; void *
0x180026fc3  mov     rdx, r13; struct CONFIG_ELEMENT *
0x180026fc6  mov     r8, [rsi+88h]; void *
0x180026fcd  mov     rcx, rax; this
0x180026fd0  call    ??0PROVIDER_ENTRY@@QEAA@PEAVCONFIG_ELEMENT@@PEAX1@Z; PROVIDER_ENTRY::PROVIDER_ENTRY(CONFIG_ELEMENT *,void *,void *)
0x180026fd5  lea     rax, ??_7RSA_PROVIDER_ENTRY@@6B@; const RSA_PROVIDER_ENTRY::`vftable'
0x180026fdc  lea     rcx, [rbx+28h]
0x180026fe0  mov     [rbx], rax
0x180026fe3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180026fe9  lea     rcx, [rbx+60h]
0x180026fed  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180026ff3  mov     qword ptr [rbx+98h], 1
0x180026ffe  lea     rcx, [rsi+48h]
0x180027002  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180027008  cmp     [rsi+28h], r12
0x18002700c  lea     rdx, szDomain
0x180027013  mov     r8, rax; unsigned __int16 *
0x180027016  mov     rcx, rbx; this
0x180027019  cmovnz  rdx, [rsi+28h]; unsigned __int16 *
0x18002701e  call    ?Initialize@PROVIDER_ENTRY@@QEAAJPEBG0@Z; PROVIDER_ENTRY::Initialize(ushort const *,ushort const *)
0x180027023  mov     edi, eax
0x180027025  test    eax, eax
0x180027027  js      short loc_180027059
0x180027029  lea     rcx, [rsi+120h]; this
0x180027030  or      r8d, 0FFFFFFFFh; unsigned int
0x180027034  mov     rdx, rbx; struct IArrayListEntry *
0x180027037  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x18002703c  mov     edi, eax
0x18002703e  test    eax, eax
0x180027040  js      short loc_180027059
0x180027042  lock inc dword ptr [rbx+8]
0x180027046  test    rbx, rbx
0x180027049  jz      loc_180026F9C
0x18002704f  mov     r13, [rbp+arg_10]
0x180027053  mov     [r13+0], rbx
0x180027057  jmp     short loc_180027066
0x180027059  test    rbx, rbx
0x18002705c  jz      short loc_180027066
0x18002705e  mov     rcx, rbx; this
0x180027061  call    ?DereferenceProviderEntry@PROVIDER_ENTRY@@QEAAXXZ; PROVIDER_ENTRY::DereferenceProviderEntry(void)
0x180027066  test    r14, r14
0x180027069  jz      short loc_180027073
0x18002706b  mov     rcx, r14; this
0x18002706e  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180027073  mov     rbx, [rsp+40h+arg_0]
0x18002707b  mov     eax, edi
0x18002707d  add     rsp, 40h
0x180027081  pop     r15
0x180027083  pop     r14
0x180027085  pop     r13
0x180027087  pop     r12
0x180027089  pop     rdi
0x18002708a  pop     rsi
0x18002708b  pop     rbp
0x18002708c  retn
```
