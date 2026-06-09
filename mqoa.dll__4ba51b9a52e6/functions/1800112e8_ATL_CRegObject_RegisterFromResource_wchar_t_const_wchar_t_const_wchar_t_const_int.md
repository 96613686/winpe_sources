# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x1800112e8`
- end: `0x1800114fe`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `534`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180012854`

## callees

- `0x18000aa00`
- `0x18000c2fc`
- `0x180011168`
- `0x1800112e8`
- `0x180012ae8`
- `0x180027372`
- `0x1800273b0`
- `0x180027470`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001133e`
- `KERNEL32!GetLastError` at `0x180011376`
- `KERNEL32!GetLastError` at `0x18001133e`
- `KERNEL32!GetLastError` at `0x180011376`
- `KERNEL32!FreeLibrary` at `0x1800114d1`
- `KERNEL32!FreeLibrary` at `0x1800114d1`
- `KERNEL32!LoadLibraryExW` at `0x180011330`
- `KERNEL32!LoadLibraryExW` at `0x180011330`
- `KERNEL32!MultiByteToWideChar` at `0x1800114aa`
- `KERNEL32!MultiByteToWideChar` at `0x1800114aa`
- `KERNEL32!SizeofResource` at `0x1800113ae`
- `KERNEL32!SizeofResource` at `0x1800113ae`
- `KERNEL32!LoadResource` at `0x18001139a`
- `KERNEL32!LoadResource` at `0x18001139a`
- `KERNEL32!FindResourceExW` at `0x180011368`
- `KERNEL32!FindResourceExW` at `0x180011368`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // r14
  signed int v9; // eax
  unsigned int v10; // ebx
  HRSRC Resource; // rax
  HRSRC v12; // rbx
  signed int LastError; // eax
  HGLOBAL v14; // rsi
  DWORD v15; // eax
  unsigned __int64 v16; // rdx
  __int64 v17; // r15
  unsigned int v18; // eax
  size_t v19; // rbx
  __int64 v20; // rax
  void *v21; // rsp
  CHAR *v22; // rdi
  __int64 v23; // rax
  int cchWideChar; // esi
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  void *v27; // rsp
  unsigned __int64 lpWideCharStr; // rbx
  const wchar_t *v29; // rdx
  CHAR MultiByteStr[8]; // [rsp+30h] [rbp+0h] BYREF
  _QWORD v32[2]; // [rsp+38h] [rbp+8h] BYREF

  *(_QWORD *)MultiByteStr = 0;
  v32[1] = this;
  v32[0] = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v12 = Resource;
    if ( !Resource || (v14 = LoadResource(v8, Resource)) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_31;
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
      else
      {
        v22 = (CHAR *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                        MultiByteStr,
                        v19);
      }
      if ( !v22 )
      {
        v10 = -2147024882;
LABEL_31:
        FreeLibrary(v8);
        goto LABEL_32;
      }
      memcpy_0(v22, v14, v19);
      v22[v17] = 0;
    }
    else
    {
      v22 = (CHAR *)v14;
    }
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    cchWideChar = v23 + 1;
    v25 = 2LL * ((int)v23 + 1);
    if ( v25 <= 0x400
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(2LL * cchWideChar), v16) )
    {
      v26 = v25 + 15;
      if ( v25 + 15 < v25 )
        v26 = 0xFFFFFFFFFFFFFF0LL;
      v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = (unsigned __int64)MultiByteStr;
    }
    else
    {
      lpWideCharStr = ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                        MultiByteStr,
                        2LL * cchWideChar);
    }
    if ( lpWideCharStr )
    {
      *(_WORD *)lpWideCharStr = 0;
      v29 = (const wchar_t *)(lpWideCharStr
                            & -(__int64)(MultiByteToWideChar(0, 0, v22, -1, (LPWSTR)lpWideCharStr, cchWideChar) != 0));
    }
    else
    {
      v29 = 0;
    }
    v10 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v32, v29, a5);
    goto LABEL_31;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
LABEL_32:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(MultiByteStr);
  return v10;
}

```

## disassembly

```asm
0x1800112e8  push    rbp
0x1800112ea  push    rbx
0x1800112eb  push    rsi
0x1800112ec  push    rdi
0x1800112ed  push    r13
0x1800112ef  push    r14
0x1800112f1  push    r15
0x1800112f3  sub     rsp, 50h
0x1800112f7  lea     rbp, [rsp+30h]
0x1800112fc  mov     rax, cs:__security_cookie
0x180011303  xor     rax, rbp
0x180011306  mov     [rbp+50h+var_38], rax
0x18001130a  mov     rbx, r9
0x18001130d  mov     rdi, r8
0x180011310  mov     rax, rdx
0x180011313  mov     qword ptr [rbp+50h+MultiByteStr], 0
0x18001131b  mov     [rbp+50h+var_40], rcx
0x18001131f  mov     [rbp+50h+var_48], 0
0x180011327  xor     edx, edx; hFile
0x180011329  lea     r8d, [rdx+2]; dwFlags
0x18001132d  mov     rcx, rax; lpLibFileName
0x180011330  call    cs:__imp_LoadLibraryExW
0x180011336  mov     r14, rax
0x180011339  test    rax, rax
0x18001133c  jnz     short loc_18001135C
0x18001133e  call    cs:__imp_GetLastError
0x180011344  mov     ebx, eax
0x180011346  test    eax, eax
0x180011348  jle     loc_1800114D8
0x18001134e  movzx   ebx, ax
0x180011351  or      ebx, 80070000h
0x180011357  jmp     loc_1800114D8
0x18001135c  xor     r9d, r9d; wLanguage
0x18001135f  mov     r8, rdi; lpName
0x180011362  mov     rdx, rbx; lpType
0x180011365  mov     rcx, r14; hModule
0x180011368  call    cs:__imp_FindResourceExW
0x18001136e  mov     rbx, rax
0x180011371  test    rax, rax
0x180011374  jnz     short loc_180011394
0x180011376  call    cs:__imp_GetLastError
0x18001137c  mov     ebx, eax
0x18001137e  test    eax, eax
0x180011380  jle     loc_1800114CE
0x180011386  movzx   ebx, ax
0x180011389  or      ebx, 80070000h
0x18001138f  jmp     loc_1800114CE
0x180011394  mov     rdx, rbx; hResInfo
0x180011397  mov     rcx, r14; hModule
0x18001139a  call    cs:__imp_LoadResource
0x1800113a0  mov     rsi, rax
0x1800113a3  test    rax, rax
0x1800113a6  jz      short loc_180011376
0x1800113a8  mov     rdx, rbx; hResInfo
0x1800113ab  mov     rcx, r14; hModule
0x1800113ae  call    cs:__imp_SizeofResource
0x1800113b4  mov     r15d, eax
0x1800113b7  mov     r13, 0FFFFFFFFFFFFFF0h
0x1800113c1  cmp     byte ptr [r15+rsi], 0
0x1800113c6  jz      short loc_180011430
0x1800113c8  inc     eax
0x1800113ca  mov     ebx, eax
0x1800113cc  cmp     eax, 400h
0x1800113d1  ja      short loc_1800113FD
0x1800113d3  mov     ecx, ebx; this
0x1800113d5  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800113da  test    al, al
0x1800113dc  jz      short loc_1800113FD
0x1800113de  lea     rax, [rbx+0Fh]
0x1800113e2  cmp     rax, rbx
0x1800113e5  ja      short loc_1800113EA
0x1800113e7  mov     rax, r13
0x1800113ea  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800113ee  call    _alloca_probe
0x1800113f3  sub     rsp, rax
0x1800113f6  lea     rdi, [rsp+80h+MultiByteStr]
0x1800113fb  jmp     short loc_18001140C
0x1800113fd  mov     rdx, rbx
0x180011400  lea     rcx, [rbp+50h+MultiByteStr]
0x180011404  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x180011409  mov     rdi, rax
0x18001140c  test    rdi, rdi
0x18001140f  jnz     short loc_18001141B
0x180011411  mov     ebx, 8007000Eh
0x180011416  jmp     loc_1800114CE
0x18001141b  mov     r8, rbx; Size
0x18001141e  mov     rdx, rsi; Src
0x180011421  mov     rcx, rdi; void *
0x180011424  call    memcpy_0
0x180011429  mov     byte ptr [r15+rdi], 0
0x18001142e  jmp     short loc_180011433
0x180011430  mov     rdi, rsi
0x180011433  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011437  mov     rax, r15
0x18001143a  inc     rax
0x18001143d  cmp     byte ptr [rdi+rax], 0
0x180011441  jnz     short loc_18001143A
0x180011443  lea     esi, [rax+1]
0x180011446  movsxd  rbx, esi
0x180011449  add     rbx, rbx
0x18001144c  cmp     rbx, 400h
0x180011453  ja      short loc_180011480
0x180011455  mov     rcx, rbx; this
0x180011458  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18001145d  test    al, al
0x18001145f  jz      short loc_180011480
0x180011461  lea     rax, [rbx+0Fh]
0x180011465  cmp     rax, rbx
0x180011468  ja      short loc_18001146D
0x18001146a  mov     rax, r13
0x18001146d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180011471  call    _alloca_probe
0x180011476  sub     rsp, rax
0x180011479  lea     rbx, [rsp+80h+MultiByteStr]
0x18001147e  jmp     short loc_18001148F
0x180011480  mov     rdx, rbx
0x180011483  lea     rcx, [rbp+50h+MultiByteStr]
0x180011487  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x18001148c  mov     rbx, rax
0x18001148f  test    rbx, rbx
0x180011492  jz      short loc_1800114BA
0x180011494  xor     ecx, ecx; CodePage
0x180011496  mov     [rbx], cx
0x180011499  mov     [rsp+80h+cchWideChar], esi; cchWideChar
0x18001149d  mov     [rsp+80h+lpWideCharStr], rbx; lpWideCharStr
0x1800114a2  mov     r9d, r15d; cbMultiByte
0x1800114a5  mov     r8, rdi; lpMultiByteStr
0x1800114a8  xor     edx, edx; dwFlags
0x1800114aa  call    cs:__imp_MultiByteToWideChar
0x1800114b0  neg     eax
0x1800114b2  sbb     rdx, rdx
0x1800114b5  and     rdx, rbx
0x1800114b8  jmp     short loc_1800114BC
0x1800114ba  xor     edx, edx; wchar_t *
0x1800114bc  mov     r8d, [rbp+50h+arg_20]; int
0x1800114c3  lea     rcx, [rbp+50h+var_48]; this
0x1800114c7  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEB_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t const *,int)
0x1800114cc  mov     ebx, eax
0x1800114ce  mov     rcx, r14; hLibModule
0x1800114d1  call    cs:__imp_FreeLibrary
0x1800114d7  nop
0x1800114d8  lea     rcx, [rbp+50h+MultiByteStr]
0x1800114dc  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800114e1  mov     eax, ebx
0x1800114e3  mov     rcx, [rbp+50h+var_38]
0x1800114e7  xor     rcx, rbp; StackCookie
0x1800114ea  call    __security_check_cookie
0x1800114ef  lea     rsp, [rbp+20h]
0x1800114f3  pop     r15
0x1800114f5  pop     r14
0x1800114f7  pop     r13
0x1800114f9  pop     rdi
0x1800114fa  pop     rsi
0x1800114fb  pop     rbx
0x1800114fc  pop     rbp
0x1800114fd  retn
```
