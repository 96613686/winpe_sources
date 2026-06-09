# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180010dd4`
- end: `0x180011030`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `604`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180012314`

## callees

- `0x180001f56`
- `0x180010c3c`
- `0x180010dd4`
- `0x1800124b0`
- `0x180012b40`
- `0x180012c00`

## import_xrefs

- `msvcrt!free` at `0x180011008`
- `msvcrt!free` at `0x180011008`
- `msvcrt!malloc` at `0x180010ef4`
- `msvcrt!malloc` at `0x180010f9b`
- `msvcrt!malloc` at `0x180010ef4`
- `msvcrt!malloc` at `0x180010f9b`
- `KERNEL32!LoadLibraryExW` at `0x180010e16`
- `KERNEL32!LoadLibraryExW` at `0x180010e16`
- `KERNEL32!MultiByteToWideChar` at `0x180010fd2`
- `KERNEL32!MultiByteToWideChar` at `0x180010fd2`
- `KERNEL32!SizeofResource` at `0x180010e94`
- `KERNEL32!SizeofResource` at `0x180010e94`
- `KERNEL32!FreeLibrary` at `0x180010ff9`
- `KERNEL32!FreeLibrary` at `0x180010ff9`
- `KERNEL32!LoadResource` at `0x180010e80`
- `KERNEL32!LoadResource` at `0x180010e80`
- `KERNEL32!FindResourceExW` at `0x180010e4e`
- `KERNEL32!FindResourceExW` at `0x180010e4e`
- `KERNEL32!GetLastError` at `0x180010e24`
- `KERNEL32!GetLastError` at `0x180010e5c`
- `KERNEL32!GetLastError` at `0x180010e24`
- `KERNEL32!GetLastError` at `0x180010e5c`

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
  _QWORD *v7; // rbx
  HMODULE Library; // rax
  HMODULE v9; // r15
  signed int v10; // eax
  unsigned int v11; // edi
  HRSRC Resource; // rax
  HRSRC v13; // rdi
  signed int LastError; // eax
  HGLOBAL v15; // r14
  DWORD v16; // eax
  unsigned __int64 v17; // rdx
  __int64 v18; // r12
  unsigned int v19; // eax
  size_t v20; // rdi
  __int64 v21; // rax
  void *v22; // rsp
  CHAR *v23; // rsi
  _QWORD *v24; // rax
  __int64 v25; // rax
  int cchWideChar; // r14d
  unsigned __int64 v27; // rdi
  __int64 v28; // rax
  void *v29; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v31; // rax
  const unsigned __int16 *v32; // rdx
  void *v33; // rcx
  CHAR MultiByteStr[8]; // [rsp+30h] [rbp+0h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp+8h] BYREF

  v7 = 0;
  *(_QWORD *)MultiByteStr = 0;
  v36[1] = this;
  v36[0] = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v9 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v13 = Resource;
    if ( !Resource || (v15 = LoadResource(v9, Resource)) == 0 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_37;
    }
    v16 = SizeofResource(v9, v13);
    v18 = v16;
    if ( *((_BYTE *)v15 + v16) )
    {
      v19 = v16 + 1;
      v20 = v19;
      if ( v19 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v19, v17) )
      {
        v21 = v20 + 15;
        if ( v20 + 15 < v20 )
          v21 = 0xFFFFFFFFFFFFFF0LL;
        v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
        v23 = MultiByteStr;
      }
      else if ( v20 + 16 >= v20 && (v24 = malloc(v20 + 16)) != 0 )
      {
        *v24 = 0;
        v7 = v24;
        *(_QWORD *)MultiByteStr = v24;
        v23 = (CHAR *)(v24 + 2);
      }
      else
      {
        v23 = 0;
      }
      if ( !v23 )
      {
        v11 = -2147024882;
LABEL_37:
        FreeLibrary(v9);
        goto LABEL_40;
      }
      memcpy_0(v23, v15, v20);
      v23[v18] = 0;
    }
    else
    {
      v23 = (CHAR *)v15;
    }
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    cchWideChar = v25 + 1;
    v27 = 2LL * ((int)v25 + 1);
    if ( v27 <= 0x400
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(2LL * cchWideChar), v17) )
    {
      v28 = v27 + 15;
      if ( v27 + 15 < v27 )
        v28 = 0xFFFFFFFFFFFFFF0LL;
      v29 = alloca(v28 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = (WCHAR *)MultiByteStr;
    }
    else if ( v27 + 16 >= v27 && (v31 = malloc(v27 + 16)) != 0 )
    {
      *v31 = v7;
      v7 = v31;
      *(_QWORD *)MultiByteStr = v31;
      lpWideCharStr = (WCHAR *)(v31 + 2);
    }
    else
    {
      lpWideCharStr = 0;
    }
    if ( lpWideCharStr )
    {
      *lpWideCharStr = 0;
      v32 = (const unsigned __int16 *)((unsigned __int64)lpWideCharStr
                                     & -(__int64)(MultiByteToWideChar(0, 0, v23, -1, lpWideCharStr, cchWideChar) != 0));
    }
    else
    {
      v32 = 0;
    }
    v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v36, v32, a5);
    goto LABEL_37;
  }
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
LABEL_40:
  while ( v7 )
  {
    v33 = v7;
    v7 = (_QWORD *)*v7;
    free(v33);
  }
  return v11;
}

```

## disassembly

```asm
0x180010dd4  push    rbp
0x180010dd6  push    rbx
0x180010dd7  push    rsi
0x180010dd8  push    rdi
0x180010dd9  push    r12
0x180010ddb  push    r14
0x180010ddd  push    r15
0x180010ddf  sub     rsp, 50h
0x180010de3  lea     rbp, [rsp+30h]
0x180010de8  mov     rax, cs:__security_cookie
0x180010def  xor     rax, rbp
0x180010df2  mov     [rbp+50h+var_38], rax
0x180010df6  mov     rdi, r9
0x180010df9  mov     rsi, r8
0x180010dfc  mov     rax, rdx
0x180010dff  xor     ebx, ebx
0x180010e01  mov     qword ptr [rbp+50h+MultiByteStr], rbx
0x180010e05  mov     [rbp+50h+var_40], rcx
0x180010e09  mov     [rbp+50h+var_48], rbx
0x180010e0d  xor     edx, edx; hFile
0x180010e0f  lea     r8d, [rbx+2]; dwFlags
0x180010e13  mov     rcx, rax; lpLibFileName
0x180010e16  call    cs:__imp_LoadLibraryExW
0x180010e1c  mov     r15, rax
0x180010e1f  test    rax, rax
0x180010e22  jnz     short loc_180010E42
0x180010e24  call    cs:__imp_GetLastError
0x180010e2a  mov     edi, eax
0x180010e2c  test    eax, eax
0x180010e2e  jle     loc_180011000
0x180010e34  movzx   edi, ax
0x180010e37  or      edi, 80070000h
0x180010e3d  jmp     loc_180011000
0x180010e42  xor     r9d, r9d; wLanguage
0x180010e45  mov     r8, rsi; lpName
0x180010e48  mov     rdx, rdi; lpType
0x180010e4b  mov     rcx, r15; hModule
0x180010e4e  call    cs:__imp_FindResourceExW
0x180010e54  mov     rdi, rax
0x180010e57  test    rax, rax
0x180010e5a  jnz     short loc_180010E7A
0x180010e5c  call    cs:__imp_GetLastError
0x180010e62  mov     edi, eax
0x180010e64  test    eax, eax
0x180010e66  jle     loc_180010FF6
0x180010e6c  movzx   edi, ax
0x180010e6f  or      edi, 80070000h
0x180010e75  jmp     loc_180010FF6
0x180010e7a  mov     rdx, rdi; hResInfo
0x180010e7d  mov     rcx, r15; hModule
0x180010e80  call    cs:__imp_LoadResource
0x180010e86  mov     r14, rax
0x180010e89  test    rax, rax
0x180010e8c  jz      short loc_180010E5C
0x180010e8e  mov     rdx, rdi; hResInfo
0x180010e91  mov     rcx, r15; hModule
0x180010e94  call    cs:__imp_SizeofResource
0x180010e9a  mov     r12d, eax
0x180010e9d  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180010ea7  cmp     byte ptr [r12+r14], 0
0x180010eac  jz      loc_180010F35
0x180010eb2  inc     eax
0x180010eb4  mov     edi, eax
0x180010eb6  cmp     eax, 400h
0x180010ebb  ja      short loc_180010EE7
0x180010ebd  mov     ecx, edi; this
0x180010ebf  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180010ec4  test    al, al
0x180010ec6  jz      short loc_180010EE7
0x180010ec8  lea     rax, [rdi+0Fh]
0x180010ecc  cmp     rax, rdi
0x180010ecf  ja      short loc_180010ED4
0x180010ed1  mov     rax, rsi
0x180010ed4  and     rax, 0FFFFFFFFFFFFFFF0h
0x180010ed8  call    _alloca_probe
0x180010edd  sub     rsp, rax
0x180010ee0  lea     rsi, [rsp+80h+MultiByteStr]
0x180010ee5  jmp     short loc_180010F11
0x180010ee7  lea     rcx, [rdi+10h]; Size
0x180010eeb  cmp     rcx, rdi
0x180010eee  jnb     short loc_180010EF4
0x180010ef0  xor     esi, esi
0x180010ef2  jmp     short loc_180010F11
0x180010ef4  call    cs:__imp_malloc
0x180010efa  test    rax, rax
0x180010efd  jz      short loc_180010EF0
0x180010eff  mov     qword ptr [rax], 0
0x180010f06  mov     rbx, rax
0x180010f09  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180010f0d  lea     rsi, [rax+10h]
0x180010f11  test    rsi, rsi
0x180010f14  jnz     short loc_180010F20
0x180010f16  mov     edi, 8007000Eh
0x180010f1b  jmp     loc_180010FF6
0x180010f20  mov     r8, rdi; Size
0x180010f23  mov     rdx, r14; Src
0x180010f26  mov     rcx, rsi; void *
0x180010f29  call    memcpy_0
0x180010f2e  mov     byte ptr [r12+rsi], 0
0x180010f33  jmp     short loc_180010F38
0x180010f35  mov     rsi, r14
0x180010f38  or      r12, 0FFFFFFFFFFFFFFFFh
0x180010f3c  mov     rax, r12
0x180010f3f  inc     rax
0x180010f42  cmp     byte ptr [rsi+rax], 0
0x180010f46  jnz     short loc_180010F3F
0x180010f48  lea     r14d, [rax+1]
0x180010f4c  movsxd  rax, r14d
0x180010f4f  lea     rdi, [rax+rax]
0x180010f53  cmp     rdi, 400h
0x180010f5a  ja      short loc_180010F8E
0x180010f5c  mov     rcx, rdi; this
0x180010f5f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180010f64  test    al, al
0x180010f66  jz      short loc_180010F8E
0x180010f68  lea     rax, [rdi+0Fh]
0x180010f6c  cmp     rax, rdi
0x180010f6f  ja      short loc_180010F7B
0x180010f71  mov     rax, 0FFFFFFFFFFFFFF0h
0x180010f7b  and     rax, 0FFFFFFFFFFFFFFF0h
0x180010f7f  call    _alloca_probe
0x180010f84  sub     rsp, rax
0x180010f87  lea     rdi, [rsp+80h+MultiByteStr]
0x180010f8c  jmp     short loc_180010FB4
0x180010f8e  lea     rcx, [rdi+10h]; Size
0x180010f92  cmp     rcx, rdi
0x180010f95  jnb     short loc_180010F9B
0x180010f97  xor     edi, edi
0x180010f99  jmp     short loc_180010FB4
0x180010f9b  call    cs:__imp_malloc
0x180010fa1  test    rax, rax
0x180010fa4  jz      short loc_180010F97
0x180010fa6  mov     [rax], rbx
0x180010fa9  mov     rbx, rax
0x180010fac  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180010fb0  lea     rdi, [rax+10h]
0x180010fb4  test    rdi, rdi
0x180010fb7  jz      short loc_180010FE2
0x180010fb9  xor     eax, eax
0x180010fbb  mov     [rdi], ax
0x180010fbe  mov     [rsp+80h+cchWideChar], r14d; cchWideChar
0x180010fc3  mov     [rsp+80h+lpWideCharStr], rdi; lpWideCharStr
0x180010fc8  mov     r9d, r12d; cbMultiByte
0x180010fcb  mov     r8, rsi; lpMultiByteStr
0x180010fce  xor     edx, edx; dwFlags
0x180010fd0  xor     ecx, ecx; CodePage
0x180010fd2  call    cs:__imp_MultiByteToWideChar
0x180010fd8  neg     eax
0x180010fda  sbb     rdx, rdx
0x180010fdd  and     rdx, rdi
0x180010fe0  jmp     short loc_180010FE4
0x180010fe2  xor     edx, edx; unsigned __int16 *
0x180010fe4  mov     r8d, [rbp+50h+arg_20]; int
0x180010feb  lea     rcx, [rbp+50h+var_48]; this
0x180010fef  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z; ATL::CRegParser::RegisterBuffer(ushort const *,int)
0x180010ff4  mov     edi, eax
0x180010ff6  mov     rcx, r15; hLibModule
0x180010ff9  call    cs:__imp_FreeLibrary
0x180010fff  nop
0x180011000  jmp     short loc_18001100E
0x180011002  mov     rcx, rbx; Block
0x180011005  mov     rbx, [rbx]
0x180011008  call    cs:__imp_free
0x18001100e  test    rbx, rbx
0x180011011  jnz     short loc_180011002
0x180011013  mov     eax, edi
0x180011015  mov     rcx, [rbp+50h+var_38]
0x180011019  xor     rcx, rbp; StackCookie
0x18001101c  call    __security_check_cookie
0x180011021  lea     rsp, [rbp+20h]
0x180011025  pop     r15
0x180011027  pop     r14
0x180011029  pop     r12
0x18001102b  pop     rdi
0x18001102c  pop     rsi
0x18001102d  pop     rbx
0x18001102e  pop     rbp
0x18001102f  retn
```
