# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180003794`
- end: `0x1800039ee`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `602`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004680`

## callees

- `0x1800035fc`
- `0x180003794`
- `0x180004808`
- `0x180015cb2`
- `0x180015cf0`
- `0x180015db0`

## import_xrefs

- `msvcrt!malloc` at `0x1800038b2`
- `msvcrt!malloc` at `0x180003959`
- `msvcrt!malloc` at `0x1800038b2`
- `msvcrt!malloc` at `0x180003959`
- `msvcrt!free` at `0x1800039c6`
- `msvcrt!free` at `0x1800039c6`
- `KERNEL32!LoadLibraryExW` at `0x1800037d3`
- `KERNEL32!LoadLibraryExW` at `0x1800037d3`
- `KERNEL32!FreeLibrary` at `0x1800039b7`
- `KERNEL32!FreeLibrary` at `0x1800039b7`
- `KERNEL32!LoadResource` at `0x18000383e`
- `KERNEL32!LoadResource` at `0x18000383e`
- `KERNEL32!FindResourceExW` at `0x18000380c`
- `KERNEL32!FindResourceExW` at `0x18000380c`
- `KERNEL32!GetLastError` at `0x1800037e1`
- `KERNEL32!GetLastError` at `0x18000381a`
- `KERNEL32!GetLastError` at `0x1800037e1`
- `KERNEL32!GetLastError` at `0x18000381a`
- `KERNEL32!MultiByteToWideChar` at `0x180003990`
- `KERNEL32!MultiByteToWideChar` at `0x180003990`
- `KERNEL32!SizeofResource` at `0x180003852`
- `KERNEL32!SizeofResource` at `0x180003852`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  _QWORD *v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // r15
  signed int v9; // eax
  unsigned int v10; // edi
  HRSRC Resource; // rax
  HRSRC v12; // rdi
  signed int LastError; // eax
  HGLOBAL v14; // r14
  DWORD v15; // eax
  unsigned __int64 v16; // rdx
  __int64 v17; // r12
  unsigned int v18; // eax
  size_t v19; // rdi
  __int64 v20; // rax
  void *v21; // rsp
  CHAR *v22; // rsi
  _QWORD *v23; // rax
  __int64 v24; // rax
  int cchWideChar; // r14d
  unsigned __int64 v26; // rdi
  __int64 v27; // rax
  void *v28; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v30; // rax
  const unsigned __int16 *v31; // rdx
  void *v32; // rcx
  CHAR MultiByteStr[8]; // [rsp+30h] [rbp+0h] BYREF
  _QWORD v35[2]; // [rsp+38h] [rbp+8h] BYREF

  v6 = 0;
  *(_QWORD *)MultiByteStr = 0;
  v35[1] = this;
  v35[0] = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
    v12 = Resource;
    if ( !Resource || (v14 = LoadResource(v8, Resource)) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_37;
    }
    v15 = SizeofResource(v8, v12);
    v17 = v15;
    if ( *((_BYTE *)v14 + v15) )
    {
      v18 = v15 + 1;
      v19 = v18;
      if ( v18 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v18, v16) )
      {
        v20 = v19 + 15;
        if ( v19 + 15 < v19 )
          v20 = 0xFFFFFFFFFFFFFF0LL;
        v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
        v22 = MultiByteStr;
      }
      else if ( v19 + 16 >= v19 && (v23 = malloc(v19 + 16)) != 0 )
      {
        *v23 = 0;
        v6 = v23;
        *(_QWORD *)MultiByteStr = v23;
        v22 = (CHAR *)(v23 + 2);
      }
      else
      {
        v22 = 0;
      }
      if ( !v22 )
      {
        v10 = -2147024882;
LABEL_37:
        FreeLibrary(v8);
        goto LABEL_40;
      }
      memcpy_0(v22, v14, v19);
      v22[v17] = 0;
    }
    else
    {
      v22 = (CHAR *)v14;
    }
    v24 = -1;
    do
      ++v24;
    while ( v22[v24] );
    cchWideChar = v24 + 1;
    v26 = 2LL * ((int)v24 + 1);
    if ( v26 <= 0x400
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(2LL * cchWideChar), v16) )
    {
      v27 = v26 + 15;
      if ( v26 + 15 < v26 )
        v27 = 0xFFFFFFFFFFFFFF0LL;
      v28 = alloca(v27 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = (WCHAR *)MultiByteStr;
    }
    else if ( v26 + 16 >= v26 && (v30 = malloc(v26 + 16)) != 0 )
    {
      *v30 = v6;
      v6 = v30;
      *(_QWORD *)MultiByteStr = v30;
      lpWideCharStr = (WCHAR *)(v30 + 2);
    }
    else
    {
      lpWideCharStr = 0;
    }
    if ( lpWideCharStr )
    {
      *lpWideCharStr = 0;
      v31 = (const unsigned __int16 *)((unsigned __int64)lpWideCharStr
                                     & -(__int64)(MultiByteToWideChar(0, 0, v22, -1, lpWideCharStr, cchWideChar) != 0));
    }
    else
    {
      v31 = 0;
    }
    v10 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v35, v31, a5);
    goto LABEL_37;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
LABEL_40:
  while ( v6 )
  {
    v32 = v6;
    v6 = (_QWORD *)*v6;
    free(v32);
  }
  return v10;
}

```

## disassembly

```asm
0x180003794  push    rbp
0x180003796  push    rbx
0x180003797  push    rsi
0x180003798  push    rdi
0x180003799  push    r12
0x18000379b  push    r14
0x18000379d  push    r15
0x18000379f  sub     rsp, 50h
0x1800037a3  lea     rbp, [rsp+30h]
0x1800037a8  mov     rax, cs:__security_cookie
0x1800037af  xor     rax, rbp
0x1800037b2  mov     [rbp+50h+var_38], rax
0x1800037b6  mov     rdi, r9
0x1800037b9  mov     rax, rdx
0x1800037bc  xor     ebx, ebx
0x1800037be  mov     qword ptr [rbp+50h+MultiByteStr], rbx
0x1800037c2  mov     [rbp+50h+var_40], rcx
0x1800037c6  mov     [rbp+50h+var_48], rbx
0x1800037ca  xor     edx, edx; hFile
0x1800037cc  lea     r8d, [rbx+2]; dwFlags
0x1800037d0  mov     rcx, rax; lpLibFileName
0x1800037d3  call    cs:__imp_LoadLibraryExW
0x1800037d9  mov     r15, rax
0x1800037dc  test    rax, rax
0x1800037df  jnz     short loc_1800037FF
0x1800037e1  call    cs:__imp_GetLastError
0x1800037e7  mov     edi, eax
0x1800037e9  test    eax, eax
0x1800037eb  jle     loc_1800039BE
0x1800037f1  movzx   edi, ax
0x1800037f4  or      edi, 80070000h
0x1800037fa  jmp     loc_1800039BE
0x1800037ff  xor     r9d, r9d; wLanguage
0x180003802  lea     r8d, [r9+65h]; lpName
0x180003806  mov     rdx, rdi; lpType
0x180003809  mov     rcx, r15; hModule
0x18000380c  call    cs:__imp_FindResourceExW
0x180003812  mov     rdi, rax
0x180003815  test    rax, rax
0x180003818  jnz     short loc_180003838
0x18000381a  call    cs:__imp_GetLastError
0x180003820  mov     edi, eax
0x180003822  test    eax, eax
0x180003824  jle     loc_1800039B4
0x18000382a  movzx   edi, ax
0x18000382d  or      edi, 80070000h
0x180003833  jmp     loc_1800039B4
0x180003838  mov     rdx, rdi; hResInfo
0x18000383b  mov     rcx, r15; hModule
0x18000383e  call    cs:__imp_LoadResource
0x180003844  mov     r14, rax
0x180003847  test    rax, rax
0x18000384a  jz      short loc_18000381A
0x18000384c  mov     rdx, rdi; hResInfo
0x18000384f  mov     rcx, r15; hModule
0x180003852  call    cs:__imp_SizeofResource
0x180003858  mov     r12d, eax
0x18000385b  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180003865  cmp     byte ptr [r12+r14], 0
0x18000386a  jz      loc_1800038F3
0x180003870  inc     eax
0x180003872  mov     edi, eax
0x180003874  cmp     eax, 400h
0x180003879  ja      short loc_1800038A5
0x18000387b  mov     ecx, edi; this
0x18000387d  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003882  test    al, al
0x180003884  jz      short loc_1800038A5
0x180003886  lea     rax, [rdi+0Fh]
0x18000388a  cmp     rax, rdi
0x18000388d  ja      short loc_180003892
0x18000388f  mov     rax, rsi
0x180003892  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003896  call    _alloca_probe
0x18000389b  sub     rsp, rax
0x18000389e  lea     rsi, [rsp+80h+MultiByteStr]
0x1800038a3  jmp     short loc_1800038CF
0x1800038a5  lea     rcx, [rdi+10h]; Size
0x1800038a9  cmp     rcx, rdi
0x1800038ac  jnb     short loc_1800038B2
0x1800038ae  xor     esi, esi
0x1800038b0  jmp     short loc_1800038CF
0x1800038b2  call    cs:__imp_malloc
0x1800038b8  test    rax, rax
0x1800038bb  jz      short loc_1800038AE
0x1800038bd  mov     qword ptr [rax], 0
0x1800038c4  mov     rbx, rax
0x1800038c7  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x1800038cb  lea     rsi, [rax+10h]
0x1800038cf  test    rsi, rsi
0x1800038d2  jnz     short loc_1800038DE
0x1800038d4  mov     edi, 8007000Eh
0x1800038d9  jmp     loc_1800039B4
0x1800038de  mov     r8, rdi; Size
0x1800038e1  mov     rdx, r14; Src
0x1800038e4  mov     rcx, rsi; void *
0x1800038e7  call    memcpy_0
0x1800038ec  mov     byte ptr [r12+rsi], 0
0x1800038f1  jmp     short loc_1800038F6
0x1800038f3  mov     rsi, r14
0x1800038f6  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800038fa  mov     rax, r12
0x1800038fd  inc     rax
0x180003900  cmp     byte ptr [rsi+rax], 0
0x180003904  jnz     short loc_1800038FD
0x180003906  lea     r14d, [rax+1]
0x18000390a  movsxd  rax, r14d
0x18000390d  lea     rdi, [rax+rax]
0x180003911  cmp     rdi, 400h
0x180003918  ja      short loc_18000394C
0x18000391a  mov     rcx, rdi; this
0x18000391d  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003922  test    al, al
0x180003924  jz      short loc_18000394C
0x180003926  lea     rax, [rdi+0Fh]
0x18000392a  cmp     rax, rdi
0x18000392d  ja      short loc_180003939
0x18000392f  mov     rax, 0FFFFFFFFFFFFFF0h
0x180003939  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000393d  call    _alloca_probe
0x180003942  sub     rsp, rax
0x180003945  lea     rdi, [rsp+80h+MultiByteStr]
0x18000394a  jmp     short loc_180003972
0x18000394c  lea     rcx, [rdi+10h]; Size
0x180003950  cmp     rcx, rdi
0x180003953  jnb     short loc_180003959
0x180003955  xor     edi, edi
0x180003957  jmp     short loc_180003972
0x180003959  call    cs:__imp_malloc
0x18000395f  test    rax, rax
0x180003962  jz      short loc_180003955
0x180003964  mov     [rax], rbx
0x180003967  mov     rbx, rax
0x18000396a  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18000396e  lea     rdi, [rax+10h]
0x180003972  test    rdi, rdi
0x180003975  jz      short loc_1800039A0
0x180003977  xor     eax, eax
0x180003979  mov     [rdi], ax
0x18000397c  mov     [rsp+80h+cchWideChar], r14d; cchWideChar
0x180003981  mov     [rsp+80h+lpWideCharStr], rdi; lpWideCharStr
0x180003986  mov     r9d, r12d; cbMultiByte
0x180003989  mov     r8, rsi; lpMultiByteStr
0x18000398c  xor     edx, edx; dwFlags
0x18000398e  xor     ecx, ecx; CodePage
0x180003990  call    cs:__imp_MultiByteToWideChar
0x180003996  neg     eax
0x180003998  sbb     rdx, rdx
0x18000399b  and     rdx, rdi
0x18000399e  jmp     short loc_1800039A2
0x1800039a0  xor     edx, edx; unsigned __int16 *
0x1800039a2  mov     r8d, [rbp+50h+arg_20]; int
0x1800039a9  lea     rcx, [rbp+50h+var_48]; this
0x1800039ad  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z; ATL::CRegParser::RegisterBuffer(ushort const *,int)
0x1800039b2  mov     edi, eax
0x1800039b4  mov     rcx, r15; hLibModule
0x1800039b7  call    cs:__imp_FreeLibrary
0x1800039bd  nop
0x1800039be  jmp     short loc_1800039CC
0x1800039c0  mov     rcx, rbx; Block
0x1800039c3  mov     rbx, [rbx]
0x1800039c6  call    cs:__imp_free
0x1800039cc  test    rbx, rbx
0x1800039cf  jnz     short loc_1800039C0
0x1800039d1  mov     eax, edi
0x1800039d3  mov     rcx, [rbp+50h+var_38]
0x1800039d7  xor     rcx, rbp; StackCookie
0x1800039da  call    __security_check_cookie
0x1800039df  lea     rsp, [rbp+20h]
0x1800039e3  pop     r15
0x1800039e5  pop     r14
0x1800039e7  pop     r12
0x1800039e9  pop     rdi
0x1800039ea  pop     rsi
0x1800039eb  pop     rbx
0x1800039ec  pop     rbp
0x1800039ed  retn
```
