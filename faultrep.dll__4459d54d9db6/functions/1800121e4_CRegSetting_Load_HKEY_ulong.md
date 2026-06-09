# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x1800121e4`
- end: `0x1800124b0`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `716`
- prototype: `__int64 __fastcall(CRegSetting *this, HKEY, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180012ef0`
- `0x18001e95c`
- `0x18002b9cc`
- `0x180034df8`
- `0x180035780`
- `0x180036764`
- `0x1800484a0`

## callees

- `0x1800028b4`
- `0x180003474`
- `0x18000a004`
- `0x18000aac8`
- `0x1800121e4`
- `0x180016528`
- `0x180049304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012494`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012494`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800122c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800122c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001228d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001228d`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  HKEY v4; // r14
  HKEY *phkResult; // rax
  int v8; // ebx
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // edx
  LPBYTE *v14; // rdi
  unsigned __int64 v15; // r15
  LPBYTE v16; // rax
  unsigned __int64 v17; // rbx
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // r9
  LPBYTE v21; // rax
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // r14
  LPBYTE v27; // rax
  size_t v28; // rbx
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h]
  char *v31; // [rsp+40h] [rbp-20h]
  _WORD v32[12]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Src = v32;
  Type = 0;
  v31 = (char *)v32;
  v4 = a2;
  cbData = 0;
  v32[0] = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    return 2149285891LL;
  if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
    goto LABEL_45;
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
LABEL_11:
    if ( RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
      goto LABEL_9;
    v10 = cbData;
    if ( Type - 1 <= 1 )
    {
      v10 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_17;
      v10 = cbData + 2;
    }
    cbData = v10;
LABEL_17:
    v11 = 0;
    while ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11 + 1) != Type )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= 0xB )
      {
        v12 = 9;
        goto LABEL_22;
      }
    }
    v12 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11);
LABEL_22:
    v13 = *((_DWORD *)this + 1);
    if ( v13 != v12 && v13 != 9 && (v13 != 5 || v12 != 1) && (v13 != 1 || v12 != 5) && (v13 || v12 != 1) )
      goto LABEL_9;
    v14 = (LPBYTE *)((char *)this + 8);
    *((_DWORD *)this + 1) = v12;
    v15 = v10;
    v16 = (LPBYTE)*((_QWORD *)this + 1);
    v17 = *((_QWORD *)this + 2) - (_QWORD)v16;
    if ( v15 > v17 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v15,
                               v9,
                               &CRegSetting::s_typeMapping) )
      {
LABEL_32:
        v8 = -2147024882;
        goto LABEL_46;
      }
      memset_0(*((void **)this + 2), 0, v15 - v17);
      v16 = *v14;
    }
    *((_QWORD *)this + 2) = &v16[v15];
    v18 = RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, *v14, &cbData) == 0;
    v21 = *v14;
    if ( !v18 )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = v21;
      goto LABEL_46;
    }
    v22 = cbData;
    v23 = *((_QWORD *)this + 2) - (_QWORD)v21;
    if ( cbData > v23 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 8,
                              cbData,
                              v19,
                              v20) )
      {
        memset_0(*((void **)this + 2), 0, v22 - v23);
        *((_QWORD *)this + 2) = &(*v14)[v22];
      }
    }
    else
    {
      *((_QWORD *)this + 2) = &v21[cbData];
    }
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings((LPCWSTR)*v14);
      if ( v8 < 0 )
        goto LABEL_46;
      v26 = Src;
      v27 = *v14;
      cbData = 2 * ((v31 - (_BYTE *)Src) >> 1) + 2;
      v28 = cbData;
      *((_QWORD *)this + 2) = v27;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               v28,
                               v24,
                               v25) )
        goto LABEL_32;
      memcpy_0(*((void **)this + 2), v26, v28);
      *((_QWORD *)this + 2) += v28;
    }
    *(_BYTE *)this = 1;
LABEL_45:
    v8 = 0;
    goto LABEL_46;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(v4, *((LPCWSTR *)this + 4), 0, a3 | 0x20019, phkResult) )
  {
    v4 = hKey;
    goto LABEL_11;
  }
LABEL_9:
  v8 = -2147467259;
LABEL_46:
  if ( Src != v32 )
    operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800121e4  mov     [rsp-28h+arg_0], rbx
0x1800121e9  push    rbp
0x1800121ea  push    rsi
0x1800121eb  push    rdi
0x1800121ec  push    r14
0x1800121ee  push    r15
0x1800121f0  mov     rbp, rsp
0x1800121f3  sub     rsp, 60h
0x1800121f7  lea     rax, [rbp+var_18]
0x1800121fb  mov     [rbp+hKey], 0
0x180012203  mov     [rbp+Src], rax
0x180012207  mov     ebx, r8d
0x18001220a  lea     rax, [rbp+var_18]
0x18001220e  mov     [rbp+Type], 0
0x180012215  mov     [rbp+var_20], rax
0x180012219  mov     r14, rdx
0x18001221c  xor     eax, eax
0x18001221e  mov     [rbp+cbData], 0
0x180012225  mov     [rbp+var_18], ax
0x180012229  mov     rsi, rcx
0x18001222c  test    rdx, rdx
0x18001222f  jnz     short loc_18001223B
0x180012231  mov     eax, 80070057h
0x180012236  jmp     loc_18001249C
0x18001223b  mov     rax, [rcx+48h]
0x18001223f  cmp     [rcx+40h], rax
0x180012243  jnz     short loc_18001224F
0x180012245  mov     eax, 801B8003h
0x18001224a  jmp     loc_18001249C
0x18001224f  cmp     byte ptr [rcx+1], 0
0x180012253  jz      loc_180012470
0x180012259  cmp     byte ptr [rcx], 0
0x18001225c  jnz     loc_180012470
0x180012262  mov     rax, [rcx+28h]
0x180012266  cmp     [rcx+20h], rax
0x18001226a  jz      short loc_1800122A5
0x18001226c  lea     rcx, [rbp+hKey]
0x180012270  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180012275  mov     rdx, [rsi+20h]; lpSubKey
0x180012279  or      ebx, 20019h
0x18001227f  mov     r9d, ebx; samDesired
0x180012282  mov     [rsp+60h+phkResult], rax; phkResult
0x180012287  xor     r8d, r8d; ulOptions
0x18001228a  mov     rcx, r14; hKey
0x18001228d  call    cs:__imp_RegOpenKeyExW
0x180012293  test    eax, eax
0x180012295  jz      short loc_1800122A1
0x180012297  mov     ebx, 80004005h
0x18001229c  jmp     loc_180012472
0x1800122a1  mov     r14, [rbp+hKey]
0x1800122a5  mov     rdx, [rsi+40h]; lpValueName
0x1800122a9  lea     rax, [rbp+cbData]
0x1800122ad  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800122b2  lea     r9, [rbp+Type]; lpType
0x1800122b6  xor     r8d, r8d; lpReserved
0x1800122b9  mov     [rsp+60h+phkResult], 0; lpData
0x1800122c2  mov     rcx, r14; hKey
0x1800122c5  call    cs:__imp_RegQueryValueExW
0x1800122cb  test    eax, eax
0x1800122cd  jnz     short loc_180012297
0x1800122cf  mov     edx, [rbp+Type]
0x1800122d2  lea     eax, [rdx-1]
0x1800122d5  cmp     eax, 1
0x1800122d8  mov     eax, [rbp+cbData]
0x1800122db  jbe     short loc_1800122E7
0x1800122dd  cmp     edx, 7
0x1800122e0  jnz     short loc_1800122EC
0x1800122e2  add     eax, 2
0x1800122e5  jmp     short loc_1800122E9
0x1800122e7  inc     eax
0x1800122e9  mov     [rbp+cbData], eax
0x1800122ec  xor     ecx, ecx
0x1800122ee  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x1800122f5  cmp     [r9+rcx*8+4], edx
0x1800122fa  jz      short loc_18001230A
0x1800122fc  inc     ecx
0x1800122fe  cmp     ecx, 0Bh
0x180012301  jb      short loc_1800122F5
0x180012303  mov     ecx, 9
0x180012308  jmp     short loc_18001230E
0x18001230a  mov     ecx, [r9+rcx*8]
0x18001230e  mov     edx, [rsi+4]
0x180012311  cmp     edx, ecx
0x180012313  jz      short loc_18001233F
0x180012315  cmp     edx, 9
0x180012318  jz      short loc_18001233F
0x18001231a  cmp     edx, 5
0x18001231d  jnz     short loc_180012324
0x18001231f  cmp     ecx, 1
0x180012322  jz      short loc_18001233F
0x180012324  cmp     edx, 1
0x180012327  jnz     short loc_18001232E
0x180012329  cmp     ecx, 5
0x18001232c  jz      short loc_18001233F
0x18001232e  test    edx, edx
0x180012330  jnz     loc_180012297
0x180012336  cmp     ecx, 1
0x180012339  jnz     loc_180012297
0x18001233f  lea     rdi, [rsi+8]
0x180012343  mov     [rsi+4], ecx
0x180012346  mov     rbx, [rdi+8]
0x18001234a  mov     r15d, eax
0x18001234d  mov     rax, [rdi]
0x180012350  sub     rbx, rax
0x180012353  cmp     r15, rbx
0x180012356  jbe     short loc_180012385
0x180012358  mov     edx, r15d
0x18001235b  mov     rcx, rdi
0x18001235e  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180012363  test    al, al
0x180012365  jnz     short loc_180012371
0x180012367  mov     ebx, 8007000Eh
0x18001236c  jmp     loc_180012472
0x180012371  mov     rcx, [rdi+8]; void *
0x180012375  mov     r8, r15
0x180012378  sub     r8, rbx; Size
0x18001237b  xor     edx, edx; Val
0x18001237d  call    memset_0
0x180012382  mov     rax, [rdi]
0x180012385  add     rax, r15
0x180012388  lea     r9, [rbp+Type]; lpType
0x18001238c  mov     [rdi+8], rax
0x180012390  xor     r8d, r8d; lpReserved
0x180012393  mov     rdx, [rsi+40h]; lpValueName
0x180012397  lea     rax, [rbp+cbData]
0x18001239b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800123a0  mov     rcx, r14; hKey
0x1800123a3  mov     rax, [rdi]
0x1800123a6  mov     [rsp+60h+phkResult], rax; lpData
0x1800123ab  call    cs:__imp_RegQueryValueExW
0x1800123b1  test    eax, eax
0x1800123b3  mov     rax, [rdi]
0x1800123b6  jz      short loc_1800123C6
0x1800123b8  mov     ebx, 80004005h
0x1800123bd  mov     [rdi+8], rax
0x1800123c1  jmp     loc_180012472
0x1800123c6  mov     r14, [rdi+8]
0x1800123ca  mov     ebx, [rbp+cbData]
0x1800123cd  sub     r14, rax
0x1800123d0  cmp     rbx, r14
0x1800123d3  ja      short loc_1800123DE
0x1800123d5  add     rax, rbx
0x1800123d8  mov     [rdi+8], rax
0x1800123dc  jmp     short loc_180012408
0x1800123de  mov     rdx, rbx
0x1800123e1  mov     rcx, rdi
0x1800123e4  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1800123e9  test    al, al
0x1800123eb  jz      short loc_180012408
0x1800123ed  mov     rcx, [rdi+8]; void *
0x1800123f1  mov     r8, rbx
0x1800123f4  sub     r8, r14; Size
0x1800123f7  xor     edx, edx; Val
0x1800123f9  call    memset_0
0x1800123fe  mov     rcx, [rdi]
0x180012401  add     rcx, rbx
0x180012404  mov     [rdi+8], rcx
0x180012408  cmp     dword ptr [rsi+4], 5
0x18001240c  jnz     short loc_18001246D
0x18001240e  mov     rcx, [rdi]; lpSrc
0x180012411  lea     rdx, [rbp+Src]
0x180012415  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001241a  mov     ebx, eax
0x18001241c  test    eax, eax
0x18001241e  js      short loc_180012472
0x180012420  mov     r14, [rbp+Src]
0x180012424  mov     rax, [rbp+var_20]
0x180012428  sub     rax, r14
0x18001242b  sar     rax, 1
0x18001242e  lea     ecx, ds:2[rax*2]
0x180012435  mov     rax, [rdi]
0x180012438  mov     ebx, ecx
0x18001243a  mov     [rbp+cbData], ecx
0x18001243d  sub     rbx, r14
0x180012440  add     rbx, r14
0x180012443  mov     [rdi+8], rax
0x180012447  mov     rdx, rbx
0x18001244a  mov     rcx, rdi
0x18001244d  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180012452  test    al, al
0x180012454  jz      loc_180012367
0x18001245a  mov     rcx, [rdi+8]; void *
0x18001245e  mov     r8, rbx; Size
0x180012461  mov     rdx, r14; Src
0x180012464  call    memcpy_0
0x180012469  add     [rdi+8], rbx
0x18001246d  mov     byte ptr [rsi], 1
0x180012470  xor     ebx, ebx
0x180012472  mov     rcx, [rbp+Src]; void *
0x180012476  lea     rax, [rbp+var_18]
0x18001247a  cmp     rcx, rax
0x18001247d  jz      short loc_18001248B
0x18001247f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012486  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001248b  mov     rcx, [rbp+hKey]; hKey
0x18001248f  test    rcx, rcx
0x180012492  jz      short loc_18001249A
0x180012494  call    cs:__imp_RegCloseKey
0x18001249a  mov     eax, ebx
0x18001249c  mov     rbx, [rsp+60h+arg_0]
0x1800124a4  add     rsp, 60h
0x1800124a8  pop     r15
0x1800124aa  pop     r14
0x1800124ac  pop     rdi
0x1800124ad  pop     rsi
0x1800124ae  pop     rbp
0x1800124af  retn
```
