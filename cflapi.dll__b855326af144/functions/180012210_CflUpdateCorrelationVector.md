# CflUpdateCorrelationVector

- ea: `0x180012210`
- end: `0x180012382`
- name: `CflUpdateCorrelationVector`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180012210`
- `0x180028124`
- `0x180028524`
- `0x18002c204`
- `0x18002cc60`
- `0x180030010`

## string_xrefs

- `0x180012336`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CflUpdateCorrelationVector(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdx
  _QWORD *v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  void (__fastcall ***v7)(_QWORD, __int64); // r8
  void (__fastcall ***v8)(_QWORD, __int64); // rax
  const char *v9; // rdx
  CflApiNew *v10; // rcx
  int updated; // eax
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-108h]
  CflApiNew *v15[2]; // [rsp+28h] [rbp-100h] BYREF
  __m128i si128; // [rsp+38h] [rbp-F0h]
  _BYTE v17[32]; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE v18[40]; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD v19[3]; // [rsp+90h] [rbp-98h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-80h]
  _BYTE v21[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v22[64]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  *(_OWORD *)v15 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v15[0]) = 0;
  v1 = (_QWORD *)std::wstring::wstring(v18, a1);
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
    v19,
    v2);
  if ( v1[3] <= 7u )
    v3 = v1;
  else
    v3 = (_QWORD *)*v1;
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v19,
    v17,
    v3,
    (char *)v3 + 2 * v1[2]);
  std::string::operator=(v15, v17);
  std::string::~string(v17);
  v19[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::~wstring(v22, v4, v5);
  std::string::~string(v21);
  if ( v20 )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v7 = v8;
    if ( v8 )
      (**v8)(v8, 1);
  }
  std::wstring::~wstring(v18, v6, v7);
  v10 = (CflApiNew *)v15;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v10 = v15[0];
  updated = CflApiNew::UpdateCorrelationVectorString(v10, v9);
  v12 = updated;
  if ( updated >= 0 )
  {
    std::string::~string(v15);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)updated,
      v14);
    std::string::~string(v15);
    return v12;
  }
}

```

## disassembly

```asm
0x180012210  push    rbx
0x180012212  sub     rsp, 120h
0x180012219  mov     rax, cs:__security_cookie
0x180012220  xor     rax, rsp
0x180012223  mov     [rsp+128h+var_18], rax
0x18001222b  xorps   xmm0, xmm0
0x18001222e  movups  xmmword ptr [rsp+128h+var_100], xmm0
0x180012233  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18001223b  movdqu  [rsp+128h+var_F0], xmm1
0x180012241  mov     byte ptr [rsp+128h+var_100], 0
0x180012246  mov     rdx, rcx
0x180012249  lea     rcx, [rsp+128h+var_C0]
0x18001224e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012253  mov     rbx, rax
0x180012256  lea     rcx, [rsp+128h+var_98]
0x18001225e  call    ??0?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180012263  nop
0x180012264  cmp     qword ptr [rbx+18h], 7
0x180012269  jbe     short loc_180012270
0x18001226b  mov     r8, [rbx]
0x18001226e  jmp     short loc_180012273
0x180012270  mov     r8, rbx
0x180012273  mov     rax, [rbx+10h]
0x180012277  lea     r9, [r8+rax*2]
0x18001227b  lea     rdx, [rsp+128h+var_E0]
0x180012280  lea     rcx, [rsp+128h+var_98]
0x180012288  call    ?to_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18001228d  lea     rdx, [rsp+128h+var_E0]
0x180012292  lea     rcx, [rsp+128h+var_100]
0x180012297  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001229c  lea     rcx, [rsp+128h+var_E0]
0x1800122a1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800122a6  nop
0x1800122a7  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x1800122ae  mov     [rsp+128h+var_98], rax
0x1800122b6  lea     rcx, [rsp+128h+var_58]
0x1800122be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122c3  lea     rcx, [rsp+128h+var_78]
0x1800122cb  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800122d0  mov     rcx, [rsp+128h+var_80]
0x1800122d8  test    rcx, rcx
0x1800122db  jz      short loc_180012305
0x1800122dd  mov     rax, [rcx]
0x1800122e0  mov     rax, [rax+10h]
0x1800122e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122e9  mov     r8, rax
0x1800122ec  test    rax, rax
0x1800122ef  jz      short loc_180012305
0x1800122f1  mov     rcx, [rax]
0x1800122f4  mov     rax, [rcx]
0x1800122f7  mov     edx, 1
0x1800122fc  mov     rcx, r8
0x1800122ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012304  nop
0x180012305  lea     rcx, [rsp+128h+var_C0]
0x18001230a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001230f  lea     rcx, [rsp+128h+var_100]
0x180012314  cmp     qword ptr [rsp+128h+var_F0+8], 0Fh
0x18001231a  cmova   rcx, [rsp+128h+var_100]; this
0x180012320  call    ?UpdateCorrelationVectorString@CflApiNew@@YAJPEBD@Z; CflApiNew::UpdateCorrelationVectorString(char const *)
0x180012325  mov     ebx, eax
0x180012327  test    eax, eax
0x180012329  jns     short loc_180012356
0x18001232b  mov     rcx, [rsp+128h]; this
0x180012333  mov     r9d, eax; char *
0x180012336  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x18001233d  mov     edx, 224h; void *
0x180012342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012347  nop
0x180012348  lea     rcx, [rsp+128h+var_100]
0x18001234d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012352  mov     eax, ebx
0x180012354  jmp     short loc_180012368
0x180012356  lea     rcx, [rsp+128h+var_100]
0x18001235b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012360  xor     eax, eax
0x180012362  jmp     short loc_180012368
0x180012364  mov     eax, [rsp+128h+var_108]
0x180012368  mov     rcx, [rsp+128h+var_18]
0x180012370  xor     rcx, rsp; StackCookie
0x180012373  call    __security_check_cookie
0x180012378  add     rsp, 120h
0x18001237f  pop     rbx
0x180012380  retn
```
