# CflGetCorrelationVector

- ea: `0x1800107e0`
- end: `0x1800109f2`
- name: `CflGetCorrelationVector`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180008420`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180010700`
- `0x1800107e0`
- `0x180028124`
- `0x180028524`
- `0x18002a498`
- `0x18002cc60`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109b5`

## string_xrefs

- `0x180010871`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180010845`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CflGetCorrelationVector(_QWORD *a1)
{
  int CorrelationVectorInternal; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  HLOCAL v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  void (__fastcall ***v13)(_QWORD, __int64); // rax
  __int64 v14; // rbx
  __int128 *v15; // rdx
  __int64 *v16; // rax
  HLOCAL hMem; // [rsp+20h] [rbp-108h] BYREF
  __int64 v18; // [rsp+28h] [rbp-100h] BYREF
  __int128 v19; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-E8h]
  unsigned __int64 v21; // [rsp+48h] [rbp-E0h]
  _BYTE v22[32]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v23[32]; // [rsp+70h] [rbp-B8h] BYREF
  _QWORD v24[3]; // [rsp+90h] [rbp-98h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-80h]
  _BYTE v26[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v27[64]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v19 = 0;
  v20 = 0;
  v21 = 15;
  LOBYTE(v19) = 0;
  hMem = 0;
  CorrelationVectorInternal = CflApiNew::GetCorrelationVectorInternal(&hMem);
  v4 = CorrelationVectorInternal;
  if ( CorrelationVectorInternal >= 0 )
  {
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
      v24,
      v3);
    v6 = hMem;
    v7 = (_QWORD *)std::wstring::wstring(v23, hMem);
    if ( v7[3] <= 7u )
      v8 = v7;
    else
      v8 = (_QWORD *)*v7;
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v24,
      v22,
      v8,
      (char *)v8 + 2 * v7[2]);
    std::string::operator=(&v19, v22);
    std::string::~string(v22);
    std::wstring::~wstring(v23, v9, v10);
    v24[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v27, v11, v12);
    std::string::~string(v26);
    if ( v25 )
    {
      v13 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v13 )
        (**v13)(v13, 1);
    }
    if ( v6 )
      CflFreeBuffer(v6);
    v14 = 0;
    v18 = 0;
    if ( v20 )
    {
      v15 = &v19;
      if ( v21 > 0xF )
        v15 = (__int128 *)v19;
      v16 = (__int64 *)wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
                         &hMem,
                         v15);
      if ( &v18 != v16 )
      {
        v14 = *v16;
        *v16 = 0;
      }
      if ( hMem )
        LocalFree(hMem);
    }
    *a1 = v14;
    std::string::~string(&v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AC,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)CorrelationVectorInternal,
      (int)hMem);
    if ( hMem )
      CflFreeBuffer(hMem);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)v4,
      (int)hMem);
    std::string::~string(&v19);
    return v4;
  }
}

```

## disassembly

```asm
0x1800107e0  mov     [rsp+arg_8], rbx
0x1800107e5  push    rdi
0x1800107e6  sub     rsp, 120h
0x1800107ed  mov     rax, cs:__security_cookie
0x1800107f4  xor     rax, rsp
0x1800107f7  mov     [rsp+128h+var_18], rax
0x1800107ff  mov     rdi, rcx
0x180010802  xorps   xmm0, xmm0
0x180010805  movups  [rsp+128h+var_F8], xmm0
0x18001080a  mov     [rsp+128h+var_E8], 0
0x180010813  mov     [rsp+128h+var_E0], 0Fh
0x18001081c  mov     byte ptr [rsp+128h+var_F8], 0
0x180010821  mov     [rsp+128h+hMem], 0; int
0x18001082a  lea     rcx, [rsp+128h+hMem]
0x18001082f  call    CflApiNew__GetCorrelationVectorInternal
0x180010834  mov     ebx, eax
0x180010836  test    eax, eax
0x180010838  jns     short loc_180010894
0x18001083a  mov     rcx, [rsp+128h]; this
0x180010842  mov     r9d, eax; char *
0x180010845  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001084c  mov     edx, 1ACh; void *
0x180010851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010856  nop
0x180010857  mov     rcx, [rsp+128h+hMem]; hMem
0x18001085c  test    rcx, rcx
0x18001085f  jz      short loc_180010866
0x180010861  call    CflFreeBuffer
0x180010866  mov     rcx, [rsp+128h]; this
0x18001086e  mov     r9d, ebx; char *
0x180010871  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010878  mov     edx, 1DAh; void *
0x18001087d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010882  nop
0x180010883  lea     rcx, [rsp+128h+var_F8]
0x180010888  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001088d  mov     eax, ebx
0x18001088f  jmp     loc_1800109D0
0x180010894  lea     rcx, [rsp+128h+var_98]
0x18001089c  call    ??0?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800108a1  nop
0x1800108a2  mov     rbx, [rsp+128h+hMem]
0x1800108a7  mov     rdx, rbx
0x1800108aa  lea     rcx, [rsp+128h+var_B8]
0x1800108af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800108b4  nop
0x1800108b5  cmp     qword ptr [rax+18h], 7
0x1800108ba  jbe     short loc_1800108C1
0x1800108bc  mov     r8, [rax]
0x1800108bf  jmp     short loc_1800108C4
0x1800108c1  mov     r8, rax
0x1800108c4  mov     rax, [rax+10h]
0x1800108c8  lea     r9, [r8+rax*2]
0x1800108cc  lea     rdx, [rsp+128h+var_D8]
0x1800108d1  lea     rcx, [rsp+128h+var_98]
0x1800108d9  call    ?to_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x1800108de  lea     rdx, [rsp+128h+var_D8]
0x1800108e3  lea     rcx, [rsp+128h+var_F8]
0x1800108e8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800108ed  lea     rcx, [rsp+128h+var_D8]
0x1800108f2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800108f7  nop
0x1800108f8  lea     rcx, [rsp+128h+var_B8]
0x1800108fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010902  nop
0x180010903  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18001090a  mov     [rsp+128h+var_98], rax
0x180010912  lea     rcx, [rsp+128h+var_58]
0x18001091a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001091f  lea     rcx, [rsp+128h+var_78]
0x180010927  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001092c  mov     rcx, [rsp+128h+var_80]
0x180010934  test    rcx, rcx
0x180010937  jz      short loc_180010961
0x180010939  mov     rax, [rcx]
0x18001093c  mov     rax, [rax+10h]
0x180010940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010945  mov     r8, rax
0x180010948  test    rax, rax
0x18001094b  jz      short loc_180010961
0x18001094d  mov     rcx, [rax]
0x180010950  mov     rax, [rcx]
0x180010953  mov     edx, 1
0x180010958  mov     rcx, r8
0x18001095b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010960  nop
0x180010961  test    rbx, rbx
0x180010964  jz      short loc_18001096E
0x180010966  mov     rcx, rbx; hMem
0x180010969  call    CflFreeBuffer
0x18001096e  xor     ebx, ebx
0x180010970  mov     [rsp+128h+var_100], rbx
0x180010975  cmp     [rsp+128h+var_E8], rbx
0x18001097a  jz      short loc_1800109BB
0x18001097c  lea     rdx, [rsp+128h+var_F8]
0x180010981  cmp     [rsp+128h+var_E0], 0Fh
0x180010987  cmova   rdx, qword ptr [rsp+128h+var_F8]
0x18001098d  lea     rcx, [rsp+128h+hMem]
0x180010992  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x180010997  lea     rcx, [rsp+128h+var_100]
0x18001099c  cmp     rcx, rax
0x18001099f  jz      short loc_1800109AB
0x1800109a1  mov     rbx, [rax]
0x1800109a4  mov     qword ptr [rax], 0
0x1800109ab  mov     rcx, [rsp+128h+hMem]; hMem
0x1800109b0  test    rcx, rcx
0x1800109b3  jz      short loc_1800109BB
0x1800109b5  call    cs:__imp_LocalFree
0x1800109bb  mov     [rdi], rbx
0x1800109be  lea     rcx, [rsp+128h+var_F8]
0x1800109c3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800109c8  xor     eax, eax
0x1800109ca  jmp     short loc_1800109D0
0x1800109cc  mov     eax, dword ptr [rsp+128h+hMem]
0x1800109d0  mov     rcx, [rsp+128h+var_18]
0x1800109d8  xor     rcx, rsp; StackCookie
0x1800109db  call    __security_check_cookie
0x1800109e0  mov     rbx, [rsp+128h+arg_8]
0x1800109e8  add     rsp, 120h
0x1800109ef  pop     rdi
0x1800109f0  retn
```
