# container::DownlevelProvider::GetContainerFixups(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x1800232f0`
- end: `0x1800238f9`
- name: `?GetContainerFixups@DownlevelProvider@container@@YA?AV?$vector@UContainerFixup@DownlevelProvider@container@@V?$allocator@UContainerFixup@DownlevelProvider@container@@@std@@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `1545`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180023900`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180004c40`
- `0x1800051b0`
- `0x18000be30`
- `0x18000ca10`
- `0x18000d668`
- `0x180022094`
- `0x1800227ec`
- `0x180022b54`
- `0x180022bfc`
- `0x180022c94`
- `0x180022df4`
- `0x180022eac`
- `0x180022fd0`
- `0x1800232f0`
- `0x180023bb4`
- `0x180023bdc`
- `0x180023e0c`
- `0x180023e44`
- `0x180023e64`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800233de`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800233de`

## string_xrefs

- `0x1800236af`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall container::DownlevelProvider::GetContainerFixups(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  int v8; // r15d
  __int64 v9; // r8
  __int128 *p_Src; // rcx
  _QWORD *v11; // rsi
  _QWORD *v12; // r13
  unsigned __int64 v13; // rdx
  __int128 *v14; // r9
  _QWORD *v15; // rax
  int v16; // r15d
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  __int128 *v19; // r9
  _QWORD *v20; // rax
  __int64 CiCatalogHint; // rax
  _QWORD *v22; // rbx
  const wchar_t *v23; // rdx
  size_t v24; // rdi
  size_t v25; // r14
  const wchar_t *v26; // rcx
  size_t v27; // r8
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // r8
  __int128 *v31; // r9
  __int128 *v32; // rax
  __int64 v33; // rax
  __int128 v34; // xmm6
  __int64 v35; // rdx
  const wchar_t *v36; // rdx
  size_t v37; // rbx
  size_t v38; // rdi
  const wchar_t *v39; // rcx
  size_t v40; // r8
  int v41; // eax
  _QWORD *v42; // rdi
  _QWORD *v43; // rbx
  wchar_t *S1_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  size_t v46; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v47; // [rsp+68h] [rbp-A0h]
  __int64 v48; // [rsp+70h] [rbp-98h]
  _QWORD *v49; // [rsp+78h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-88h]
  _QWORD *v51; // [rsp+88h] [rbp-80h]
  _QWORD *v52; // [rsp+90h] [rbp-78h]
  _QWORD *v53; // [rsp+98h] [rbp-70h]
  __int128 Src; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v56; // [rsp+B8h] [rbp-50h]
  __int128 v57; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-30h]
  __int64 v59; // [rsp+E0h] [rbp-28h]
  char v60; // [rsp+E8h] [rbp-20h]
  __int128 v61; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v62; // [rsp+108h] [rbp+0h]
  unsigned __int64 v63; // [rsp+110h] [rbp+8h]
  __int128 v64; // [rsp+118h] [rbp+10h] BYREF
  __int64 v65; // [rsp+128h] [rbp+20h]
  __int64 v66; // [rsp+130h] [rbp+28h]
  __int128 v67; // [rsp+138h] [rbp+30h] BYREF
  __int64 v68; // [rsp+148h] [rbp+40h]
  __int64 v69; // [rsp+150h] [rbp+48h]
  __int128 v70; // [rsp+158h] [rbp+50h] BYREF
  __int64 v71; // [rsp+168h] [rbp+60h]
  __int64 v72; // [rsp+170h] [rbp+68h]
  _BYTE v73[32]; // [rsp+178h] [rbp+70h] BYREF
  WCHAR Buffer[264]; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+400h] [rbp+2F8h]

  v53 = a1;
  v50 = 0;
  v4 = operator new(0x40u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v49 = v4;
  v61 = 0;
  v62 = 0;
  v63 = 7;
  LOWORD(v61) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 7;
  LOWORD(v64) = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v67 = 0;
  v68 = 0;
  v69 = 7;
  LOWORD(v67) = 0;
  LOBYTE(v48) = 0;
  Src = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(Src) = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v5, v6, v7);
  v57 = 0;
  v58 = 0;
  v59 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v57);
  v8 = 3;
  std::wstring::operator=(&Src, &v57);
  std::wstring::~wstring(&v57);
  p_Src = &Src;
  if ( v56 > 7 )
    p_Src = (__int128 *)Src;
  if ( *((_WORD *)p_Src + v55 - 1) != 92 )
    std::wstring::append(&Src, L"\\");
  v11 = *(_QWORD **)a2;
  v12 = *(_QWORD **)(a2 + 8);
  if ( *(_QWORD **)a2 != v12 )
  {
    do
    {
      v13 = v11[2];
      if ( 0x7FFFFFFFFFFFFFFELL - v55 < v13 )
        goto LABEL_65;
      v14 = &Src;
      if ( v56 > 7 )
        v14 = (__int128 *)Src;
      v15 = v11[3] <= 7u ? v11 : (_QWORD *)*v11;
      std::wstring::wstring(&v57, v13, v9, v14, v55, v15, v11[2]);
      v16 = v8 | 4;
      std::wstring::operator=(&v67, &v57);
      std::wstring::~wstring(&v57);
      std::wstring::operator=(&v61, v11);
      v18 = v11[2];
      if ( 0x7FFFFFFFFFFFFFFELL - v55 < v18 )
LABEL_65:
        std::_Xlen_string();
      v19 = &Src;
      if ( v56 > 7 )
        v19 = (__int128 *)Src;
      if ( v11[3] <= 7u )
        v20 = v11;
      else
        v20 = (_QWORD *)*v11;
      std::wstring::wstring(&v57, v18, v17, v19, v55, v20, v11[2]);
      v8 = v16 | 8;
      std::wstring::operator=(&v64, &v57);
      std::wstring::~wstring(&v57);
      std::vector<container::DownlevelProvider::ContainerFixup>::emplace_back<container::DownlevelProvider::ContainerFixup>(
        a1,
        &v61);
      CiCatalogHint = container::DownlevelProvider::GetCiCatalogHint((__int64)&v57, &v67);
      if ( *(_BYTE *)(CiCatalogHint + 32) )
      {
        if ( (_BYTE)v48 )
        {
          std::wstring::operator=(S1_8, CiCatalogHint);
        }
        else
        {
          *(_OWORD *)S1_8 = 0;
          v46 = 0;
          v47 = 0;
          *(_OWORD *)S1_8 = *(_OWORD *)CiCatalogHint;
          v46 = *(_QWORD *)(CiCatalogHint + 16);
          v47 = *(_QWORD *)(CiCatalogHint + 24);
          *(_QWORD *)(CiCatalogHint + 16) = 0;
          *(_QWORD *)(CiCatalogHint + 24) = 7;
          *(_WORD *)CiCatalogHint = 0;
          LOBYTE(v48) = 1;
        }
      }
      else if ( (_BYTE)v48 )
      {
        std::wstring::~wstring(S1_8);
        LOBYTE(v48) = 0;
      }
      if ( v60 )
        std::wstring::~wstring(&v57);
      if ( !(_BYTE)v48 )
        goto LABEL_60;
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
        &v49,
        &v57,
        S1_8);
      v22 = (_QWORD *)v58;
      if ( !*(_BYTE *)(v58 + 25) )
      {
        v23 = (const wchar_t *)(v58 + 32);
        v24 = *(_QWORD *)(v58 + 48);
        if ( *(_QWORD *)(v58 + 56) > 7u )
          v23 = *(const wchar_t **)v23;
        v25 = v46;
        v26 = (const wchar_t *)S1_8;
        if ( v47 > 7 )
          v26 = S1_8[0];
        v27 = v46;
        if ( v24 < v46 )
          v27 = *(_QWORD *)(v58 + 48);
        v28 = wmemcmp(v26, v23, v27);
        if ( v28 )
        {
          if ( v28 >= 0 )
            goto LABEL_39;
        }
        else if ( v25 >= v24 )
        {
LABEL_39:
          if ( v22 != v49 )
            goto LABEL_60;
        }
      }
      if ( !(_BYTE)v48 )
        std::_Throw_bad_optional_access();
      v70 = 0;
      v71 = 0;
      v72 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v70);
      v29 = std::operator+<unsigned short>(v73, &v70, S1_8);
      std::wstring::operator=(&v61, v29);
      std::wstring::~wstring(v73);
      std::wstring::~wstring(&v70);
      if ( 0x7FFFFFFFFFFFFFFELL - v55 < v62 )
        goto LABEL_65;
      v31 = &Src;
      if ( v56 > 7 )
        v31 = (__int128 *)Src;
      v32 = &v61;
      if ( v63 > 7 )
        v32 = (__int128 *)v61;
      std::wstring::wstring(&v57, v62, v30, v31, v55, v32, v62);
      v8 |= 0x10u;
      std::wstring::operator=(&v64, &v57);
      std::wstring::~wstring(&v57);
      std::vector<container::DownlevelProvider::ContainerFixup>::emplace_back<container::DownlevelProvider::ContainerFixup>(
        a1,
        &v61);
      if ( !(_BYTE)v48 )
        std::_Throw_bad_optional_access();
      v33 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              &v49,
              &v57,
              S1_8);
      v34 = *(_OWORD *)v33;
      v35 = *(_QWORD *)(v33 + 16);
      if ( *(_BYTE *)(v35 + 25) )
      {
LABEL_58:
        if ( v50 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v42 = v49;
        v51 = &v49;
        v52 = 0;
        v43 = operator new(0x40u);
        v52 = v43;
        std::wstring::wstring(v43 + 4, S1_8);
        *v43 = v42;
        v43[1] = v42;
        v43[2] = v42;
        *((_WORD *)v43 + 12) = 0;
        v52 = 0;
        v57 = v34;
        std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Insert_node(&v49, &v57, v43);
        goto LABEL_60;
      }
      v36 = (const wchar_t *)(v35 + 32);
      v37 = *((_QWORD *)v36 + 2);
      if ( *((_QWORD *)v36 + 3) > 7u )
        v36 = *(const wchar_t **)v36;
      v38 = v46;
      v39 = (const wchar_t *)S1_8;
      if ( v47 > 7 )
        v39 = S1_8[0];
      v40 = v46;
      if ( v37 < v46 )
        v40 = v37;
      v41 = wmemcmp(v39, v36, v40);
      if ( v41 )
      {
        if ( v41 < 0 )
          goto LABEL_58;
      }
      else if ( v38 < v37 )
      {
        goto LABEL_58;
      }
LABEL_60:
      v11 += 4;
    }
    while ( v11 != v12 );
  }
  std::wstring::~wstring(&Src);
  if ( (_BYTE)v48 )
    std::wstring::~wstring(S1_8);
  std::wstring::~wstring(&v67);
  std::wstring::~wstring(&v64);
  std::wstring::~wstring(&v61);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v49);
  return a1;
}

```

## disassembly

```asm
0x1800232f0  mov     rax, rsp
0x1800232f3  mov     [rax+18h], rbx
0x1800232f7  push    rbp
0x1800232f8  push    rsi
0x1800232f9  push    rdi
0x1800232fa  push    r12
0x1800232fc  push    r13
0x1800232fe  push    r14
0x180023300  push    r15
0x180023302  lea     rbp, [rax-2F8h]
0x180023309  sub     rsp, 3C0h
0x180023310  movaps  xmmword ptr [rax-48h], xmm6
0x180023314  mov     rax, cs:__security_cookie
0x18002331b  xor     rax, rsp
0x18002331e  mov     [rbp+2F0h+var_50], rax
0x180023325  mov     rbx, rdx
0x180023328  mov     r12, rcx
0x18002332b  mov     [rbp+2F0h+var_360], rcx
0x18002332f  xor     r14d, r14d
0x180023332  mov     dword ptr [rsp+3F0h+S1], r14d
0x180023337  mov     [rsp+3F0h+var_380], r14
0x18002333c  mov     [rsp+3F0h+var_378], r14
0x180023341  lea     ecx, [r14+40h]; Size
0x180023345  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002334a  mov     [rax], rax
0x18002334d  mov     [rax+8], rax
0x180023351  mov     [rax+10h], rax
0x180023355  mov     word ptr [rax+18h], 101h
0x18002335b  mov     [rsp+3F0h+var_380], rax
0x180023360  xorps   xmm0, xmm0
0x180023363  movups  [rbp+2F0h+var_300], xmm0
0x180023367  mov     [rbp+2F0h+var_2F0], r14
0x18002336b  mov     [rbp+2F0h+var_2E8], 7
0x180023373  mov     word ptr [rbp+2F0h+var_300], r14w
0x180023378  movups  [rbp+2F0h+var_2E0], xmm0
0x18002337c  mov     [rbp+2F0h+var_2D0], r14
0x180023380  mov     [rbp+2F0h+var_2C8], 7
0x180023388  mov     word ptr [rbp+2F0h+var_2E0], r14w
0x18002338d  mov     [r12], r14
0x180023391  mov     [r12+8], r14
0x180023396  mov     [r12+10h], r14
0x18002339b  mov     dword ptr [rsp+3F0h+S1], 1
0x1800233a3  movups  [rbp+2F0h+var_2C0], xmm0
0x1800233a7  mov     [rbp+2F0h+var_2B0], r14
0x1800233ab  mov     [rbp+2F0h+var_2A8], 7
0x1800233b3  mov     word ptr [rbp+2F0h+var_2C0], r14w
0x1800233b8  mov     byte ptr [rsp+3F0h+var_388], r14b
0x1800233bd  movups  [rbp+2F0h+Src], xmm0
0x1800233c1  mov     [rbp+2F0h+var_348], r14
0x1800233c5  mov     [rbp+2F0h+var_340], 7
0x1800233cd  mov     word ptr [rbp+2F0h+Src], r14w
0x1800233d2  mov     edx, 104h; uSize
0x1800233d7  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x1800233de  call    cs:__imp_GetWindowsDirectoryW
0x1800233e5  nop     dword ptr [rax+rax+00h]
0x1800233ea  test    eax, eax
0x1800233ec  jz      loc_1800238E0
0x1800233f2  xorps   xmm0, xmm0
0x1800233f5  movups  [rbp+2F0h+var_330], xmm0
0x1800233f9  mov     [rbp+2F0h+var_320], r14
0x1800233fd  mov     [rbp+2F0h+var_318], r14
0x180023401  mov     r8d, eax
0x180023404  lea     rdx, [rbp+2F0h+Buffer]
0x18002340b  lea     rcx, [rbp+2F0h+var_330]
0x18002340f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023414  lea     r15d, [r14+3]
0x180023418  mov     dword ptr [rsp+3F0h+S1], r15d
0x18002341d  lea     rdx, [rbp+2F0h+var_330]
0x180023421  lea     rcx, [rbp+2F0h+Src]
0x180023425  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002342a  lea     rcx, [rbp+2F0h+var_330]
0x18002342e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023433  lea     rcx, [rbp+2F0h+Src]
0x180023437  cmp     [rbp+2F0h+var_340], 7
0x18002343c  cmova   rcx, qword ptr [rbp+2F0h+Src]
0x180023441  mov     rax, [rbp+2F0h+var_348]
0x180023445  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x18002344b  jz      short loc_18002345D
0x18002344d  lea     rdx, asc_180037DD0; "\\"
0x180023454  lea     rcx, [rbp+2F0h+Src]; Src
0x180023458  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002345d  mov     rsi, [rbx]
0x180023460  mov     r13, [rbx+8]
0x180023464  cmp     rsi, r13
0x180023467  jz      loc_18002385E
0x18002346d  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180023477  mov     rcx, [rbp+2F0h+var_348]
0x18002347b  mov     rdx, [rsi+10h]
0x18002347f  mov     rax, rdi
0x180023482  sub     rax, rcx
0x180023485  cmp     rax, rdx
0x180023488  jb      loc_1800238DA
0x18002348e  lea     r9, [rbp+2F0h+Src]
0x180023492  cmp     [rbp+2F0h+var_340], 7
0x180023497  cmova   r9, qword ptr [rbp+2F0h+Src]
0x18002349c  cmp     qword ptr [rsi+18h], 7
0x1800234a1  jbe     short loc_1800234A8
0x1800234a3  mov     rax, [rsi]
0x1800234a6  jmp     short loc_1800234AB
0x1800234a8  mov     rax, rsi
0x1800234ab  mov     [rsp+3F0h+var_3C0], rdx
0x1800234b0  mov     [rsp+3F0h+var_3C8], rax
0x1800234b5  mov     [rsp+3F0h+var_3D0], rcx
0x1800234ba  lea     rcx, [rbp+2F0h+var_330]
0x1800234be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800234c3  or      r15d, 4
0x1800234c7  mov     dword ptr [rsp+3F0h+S1], r15d
0x1800234cc  lea     rdx, [rbp+2F0h+var_330]
0x1800234d0  lea     rcx, [rbp+2F0h+var_2C0]
0x1800234d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800234d9  lea     rcx, [rbp+2F0h+var_330]
0x1800234dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800234e2  mov     rdx, rsi
0x1800234e5  lea     rcx, [rbp+2F0h+var_300]
0x1800234e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800234ee  mov     rcx, [rbp+2F0h+var_348]
0x1800234f2  mov     rdx, [rsi+10h]
0x1800234f6  mov     rax, rdi
0x1800234f9  sub     rax, rcx
0x1800234fc  cmp     rax, rdx
0x1800234ff  jb      loc_1800238DA
0x180023505  lea     r9, [rbp+2F0h+Src]
0x180023509  cmp     [rbp+2F0h+var_340], 7
0x18002350e  cmova   r9, qword ptr [rbp+2F0h+Src]
0x180023513  cmp     qword ptr [rsi+18h], 7
0x180023518  jbe     short loc_18002351F
0x18002351a  mov     rax, [rsi]
0x18002351d  jmp     short loc_180023522
0x18002351f  mov     rax, rsi
0x180023522  mov     [rsp+3F0h+var_3C0], rdx
0x180023527  mov     [rsp+3F0h+var_3C8], rax
0x18002352c  mov     [rsp+3F0h+var_3D0], rcx
0x180023531  lea     rcx, [rbp+2F0h+var_330]
0x180023535  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002353a  or      r15d, 8
0x18002353e  mov     dword ptr [rsp+3F0h+S1], r15d
0x180023543  lea     rdx, [rbp+2F0h+var_330]
0x180023547  lea     rcx, [rbp+2F0h+var_2E0]
0x18002354b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023550  lea     rcx, [rbp+2F0h+var_330]
0x180023554  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023559  lea     rdx, [rbp+2F0h+var_300]
0x18002355d  mov     rcx, r12
0x180023560  call    ??$emplace_back@UContainerFixup@DownlevelProvider@container@@@?$vector@UContainerFixup@DownlevelProvider@container@@V?$allocator@UContainerFixup@DownlevelProvider@container@@@std@@@std@@QEAAAEAUContainerFixup@DownlevelProvider@container@@$$QEAU234@@Z; std::vector<container::DownlevelProvider::ContainerFixup>::emplace_back<container::DownlevelProvider::ContainerFixup>(container::DownlevelProvider::ContainerFixup &&)
0x180023565  lea     rdx, [rbp+2F0h+var_2C0]
0x180023569  lea     rcx, [rbp+2F0h+var_330]
0x18002356d  call    ?GetCiCatalogHint@DownlevelProvider@container@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; container::DownlevelProvider::GetCiCatalogHint(std::wstring const &)
0x180023572  mov     rcx, rax
0x180023575  cmp     [rax+20h], r14b
0x180023579  jz      short loc_1800235DD
0x18002357b  cmp     byte ptr [rsp+3F0h+var_388], r14b
0x180023580  jz      short loc_180023591
0x180023582  mov     rdx, rax
0x180023585  lea     rcx, [rsp+3F0h+S1+8]
0x18002358a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002358f  jmp     short loc_1800235F3
0x180023591  xorps   xmm0, xmm0
0x180023594  movups  xmmword ptr [rsp+3F0h+S1+8], xmm0
0x180023599  mov     [rsp+3F0h+var_398], r14
0x18002359e  mov     [rsp+3F0h+var_390], r14
0x1800235a3  mov     rax, [rax]
0x1800235a6  mov     [rsp+3F0h+S1+8], rax
0x1800235ab  mov     rax, [rcx+8]
0x1800235af  mov     [rsp+3F0h+var_3A0], rax
0x1800235b4  mov     rax, [rcx+10h]
0x1800235b8  mov     [rsp+3F0h+var_398], rax
0x1800235bd  mov     rax, [rcx+18h]
0x1800235c1  mov     [rsp+3F0h+var_390], rax
0x1800235c6  mov     [rcx+10h], r14
0x1800235ca  mov     qword ptr [rcx+18h], 7
0x1800235d2  mov     [rcx], r14w
0x1800235d6  mov     byte ptr [rsp+3F0h+var_388], 1
0x1800235db  jmp     short loc_1800235F3
0x1800235dd  cmp     byte ptr [rsp+3F0h+var_388], r14b
0x1800235e2  jz      short loc_1800235F3
0x1800235e4  lea     rcx, [rsp+3F0h+S1+8]
0x1800235e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800235ee  mov     byte ptr [rsp+3F0h+var_388], r14b
0x1800235f3  cmp     [rbp+2F0h+var_310], r14b
0x1800235f7  jz      short loc_180023602
0x1800235f9  lea     rcx, [rbp+2F0h+var_330]
0x1800235fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023602  cmp     byte ptr [rsp+3F0h+var_388], r14b
0x180023607  jz      loc_180023851
0x18002360d  lea     r8, [rsp+3F0h+S1+8]
0x180023612  lea     rdx, [rbp+2F0h+var_330]
0x180023616  lea     rcx, [rsp+3F0h+var_380]
0x18002361b  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180023620  mov     rbx, [rbp+2F0h+var_320]
0x180023624  cmp     [rbx+19h], r14b
0x180023628  jnz     short loc_18002368F
0x18002362a  lea     rdx, [rbx+20h]
0x18002362e  mov     rdi, [rdx+10h]
0x180023632  cmp     qword ptr [rdx+18h], 7
0x180023637  jbe     short loc_18002363C
0x180023639  mov     rdx, [rdx]; S2
0x18002363c  mov     r14, [rsp+3F0h+var_398]
0x180023641  lea     rcx, [rsp+3F0h+S1+8]
0x180023646  cmp     [rsp+3F0h+var_390], 7
0x18002364c  cmova   rcx, [rsp+3F0h+S1+8]; S1
0x180023652  mov     r8, r14
0x180023655  cmp     rdi, r14
0x180023658  cmovb   r8, rdi; N
0x18002365c  call    wmemcmp
0x180023661  test    eax, eax
0x180023663  jz      short loc_18002366E
0x180023665  xor     r14d, r14d
0x180023668  test    eax, eax
0x18002366a  jns     short loc_180023676
0x18002366c  jmp     short loc_180023685
0x18002366e  cmp     r14, rdi
0x180023671  jb      short loc_180023682
0x180023673  xor     r14d, r14d
0x180023676  cmp     rbx, [rsp+3F0h+var_380]
0x18002367b  jz      short loc_180023685
0x18002367d  jmp     loc_180023847
0x180023682  xor     r14d, r14d
0x180023685  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18002368f  cmp     byte ptr [rsp+3F0h+var_388], r14b
0x180023694  jz      loc_1800238D4
0x18002369a  xorps   xmm0, xmm0
0x18002369d  movups  [rbp+2F0h+var_2A0], xmm0
0x1800236a1  mov     [rbp+2F0h+var_290], r14
0x1800236a5  mov     [rbp+2F0h+var_288], r14
0x1800236a9  mov     r8d, 38h ; '8'
0x1800236af  lea     rdx, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x1800236b6  lea     rcx, [rbp+2F0h+var_2A0]
0x1800236ba  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800236bf  nop
0x1800236c0  lea     r8, [rsp+3F0h+S1+8]
0x1800236c5  lea     rdx, [rbp+2F0h+var_2A0]
0x1800236c9  lea     rcx, [rbp+2F0h+var_280]
0x1800236cd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800236d2  mov     rdx, rax
0x1800236d5  lea     rcx, [rbp+2F0h+var_300]
0x1800236d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800236de  lea     rcx, [rbp+2F0h+var_280]
0x1800236e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236e7  nop
0x1800236e8  lea     rcx, [rbp+2F0h+var_2A0]
0x1800236ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236f1  mov     rcx, [rbp+2F0h+var_348]
0x1800236f5  mov     rdx, [rbp+2F0h+var_2F0]
0x1800236f9  mov     rax, rdi
0x1800236fc  sub     rax, rcx
0x1800236ff  cmp     rax, rdx
0x180023702  jb      loc_1800238DA
0x180023708  lea     r9, [rbp+2F0h+Src]
0x18002370c  cmp     [rbp+2F0h+var_340], 7
0x180023711  cmova   r9, qword ptr [rbp+2F0h+Src]
0x180023716  lea     rax, [rbp+2F0h+var_300]
0x18002371a  cmp     [rbp+2F0h+var_2E8], 7
0x18002371f  cmova   rax, qword ptr [rbp+2F0h+var_300]
0x180023724  mov     [rsp+3F0h+var_3C0], rdx
0x180023729  mov     [rsp+3F0h+var_3C8], rax
0x18002372e  mov     [rsp+3F0h+var_3D0], rcx
0x180023733  lea     rcx, [rbp+2F0h+var_330]
0x180023737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002373c  or      r15d, 10h
0x180023740  mov     dword ptr [rsp+3F0h+S1], r15d
0x180023745  lea     rdx, [rbp+2F0h+var_330]
0x180023749  lea     rcx, [rbp+2F0h+var_2E0]
0x18002374d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023752  lea     rcx, [rbp+2F0h+var_330]
0x180023756  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002375b  lea     rdx, [rbp+2F0h+var_300]
0x18002375f  mov     rcx, r12
0x180023762  call    ??$emplace_back@UContainerFixup@DownlevelProvider@container@@@?$vector@UContainerFixup@DownlevelProvider@container@@V?$allocator@UContainerFixup@DownlevelProvider@container@@@std@@@std@@QEAAAEAUContainerFixup@DownlevelProvider@container@@$$QEAU234@@Z; std::vector<container::DownlevelProvider::ContainerFixup>::emplace_back<container::DownlevelProvider::ContainerFixup>(container::DownlevelProvider::ContainerFixup &&)
0x180023767  cmp     byte ptr [rsp+3F0h+var_388], r14b
0x18002376c  jz      loc_1800238F3
0x180023772  lea     r8, [rsp+3F0h+S1+8]
0x180023777  lea     rdx, [rbp+2F0h+var_330]
0x18002377b  lea     rcx, [rsp+3F0h+var_380]
0x180023780  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180023785  movups  xmm6, xmmword ptr [rax]
0x180023788  mov     rdx, [rax+10h]
0x18002378c  cmp     [rdx+19h], r14b
0x180023790  jnz     short loc_1800237D6
0x180023792  add     rdx, 20h ; ' '
0x180023796  mov     rbx, [rdx+10h]
0x18002379a  cmp     qword ptr [rdx+18h], 7
0x18002379f  jbe     short loc_1800237A4
0x1800237a1  mov     rdx, [rdx]; S2
0x1800237a4  mov     rdi, [rsp+3F0h+var_398]
0x1800237a9  lea     rcx, [rsp+3F0h+S1+8]
0x1800237ae  cmp     [rsp+3F0h+var_390], 7
0x1800237b4  cmova   rcx, [rsp+3F0h+S1+8]; S1
0x1800237ba  mov     r8, rdi
0x1800237bd  cmp     rbx, rdi
0x1800237c0  cmovb   r8, rbx; N
0x1800237c4  call    wmemcmp
0x1800237c9  test    eax, eax
0x1800237cb  jz      short loc_1800237D1
0x1800237cd  jns     short loc_180023847
0x1800237cf  jmp     short loc_1800237D6
0x1800237d1  cmp     rdi, rbx
0x1800237d4  jnb     short loc_180023847
0x1800237d6  mov     rax, 3FFFFFFFFFFFFFFh
0x1800237e0  cmp     [rsp+3F0h+var_378], rax
0x1800237e5  jz      loc_1800238ED
  ... truncated ...
```
