# CandidateList::CandidateList(IMVCellularV2 *,ushort const *)

- ea: `0x180026070`
- end: `0x180026238`
- name: `??0CandidateList@@QEAA@PEAUIMVCellularV2@@PEBG@Z`
- size: `456`
- prototype: `CandidateList *__fastcall(CandidateList *this, struct IMVCellularV2 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a438`
- `0x18002d570`
- `0x1800308d0`

## callees

- `0x18000e0b0`
- `0x18000e308`
- `0x180012390`
- `0x180012e30`
- `0x180026070`
- `0x180026c90`
- `0x1800284c0`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800261cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800261cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800261b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800261b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CandidateList *__fastcall CandidateList::CandidateList(
        CandidateList *this,
        struct IMVCellularV2 *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rdi
  __int64 v6; // r8
  LPCWSTR *v7; // rdx
  char *v8; // rdx
  LPCWSTR *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-68h]
  HKEY hKey[2]; // [rsp+30h] [rbp-58h] BYREF
  void *v16[4]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  hKey[1] = (HKEY)this;
  *(_QWORD *)this = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMVCellularV2 *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + 4) = 7;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 4) = 0;
  v5 = -1;
  if ( *a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  std::wstring::assign((char *)this + 8, a3);
  *((_QWORD *)this + 5) = 0;
  if ( !qword_1800526A0 )
  {
    if ( *(_WORD *)gc_wszRegUICandidates )
    {
      do
        ++v5;
      while ( *((_WORD *)gc_wszRegUICandidates + v5) );
    }
    std::wstring::assign(&CandidateList::m_regParent, gc_wszRegUICandidates);
    v7 = &CandidateList::m_regParent;
    if ( (unsigned __int64)qword_1800526A8 >= 8 )
      v7 = (LPCWSTR *)CandidateList::m_regParent;
    v8 = (char *)v7 + 2 * qword_1800526A0;
    v9 = &CandidateList::m_regParent;
    if ( (unsigned __int64)qword_1800526A8 >= 8 )
      v9 = (LPCWSTR *)CandidateList::m_regParent;
    if ( v8 )
      v10 = (v8 - (char *)v9) >> 1;
    else
      v10 = 0;
    std::wstring::insert(&CandidateList::m_regParent, v10, 1);
    std::wstring::append(&CandidateList::m_regParent, (void *)L"UICC");
  }
  hKey[0] = 0;
  v11 = CandidateList::ComposeFullListPath(this, v16);
  if ( *(_QWORD *)(v11 + 24) >= 8u )
    v11 = *(_QWORD *)v11;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v11, 0, 0x2001Fu, hKey);
  if ( v16[3] >= (void *)8 )
    operator delete(v16[0]);
  if ( v12 )
  {
    if ( v12 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)v12,
        phkResult);
  }
  else
  {
    CandidateList::InitializePersistList(this, hKey);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return this;
}

```

## disassembly

```asm
0x180026070  mov     [rsp+arg_8], rbx
0x180026075  push    rbp
0x180026076  push    rsi
0x180026077  push    rdi
0x180026078  sub     rsp, 70h
0x18002607c  mov     rax, cs:__security_cookie
0x180026083  xor     rax, rsp
0x180026086  mov     [rsp+88h+var_28], rax
0x18002608b  mov     rsi, r8
0x18002608e  mov     rbx, rcx
0x180026091  mov     [rsp+88h+var_50], rcx
0x180026096  mov     [rcx], rdx
0x180026099  xor     ebp, ebp
0x18002609b  test    rdx, rdx
0x18002609e  jz      short loc_1800260B0
0x1800260a0  mov     rax, [rdx]
0x1800260a3  mov     rcx, rdx
0x1800260a6  mov     rax, [rax+8]
0x1800260aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260af  nop
0x1800260b0  lea     rcx, [rbx+8]; void *
0x1800260b4  mov     qword ptr [rcx+18h], 7
0x1800260bc  mov     [rcx+10h], rbp
0x1800260c0  mov     [rcx], bp
0x1800260c3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800260c7  cmp     [rsi], bp
0x1800260ca  jnz     short loc_1800260D1
0x1800260cc  mov     r8, rbp
0x1800260cf  jmp     short loc_1800260DE
0x1800260d1  mov     r8, rdi
0x1800260d4  inc     r8
0x1800260d7  cmp     [rsi+r8*2], bp
0x1800260dc  jnz     short loc_1800260D4
0x1800260de  mov     rdx, rsi; Src
0x1800260e1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800260e6  nop
0x1800260e7  mov     [rbx+28h], rbp
0x1800260eb  cmp     cs:qword_1800526A0, rbp
0x1800260f2  jnz     loc_18002617F
0x1800260f8  mov     rdx, cs:?gc_wszRegUICandidates@@3PEBGEB; Src
0x1800260ff  cmp     [rdx], bp
0x180026102  jnz     short loc_180026109
0x180026104  mov     rdi, rbp
0x180026107  jmp     short loc_180026112
0x180026109  inc     rdi
0x18002610c  cmp     [rdx+rdi*2], bp
0x180026110  jnz     short loc_180026109
0x180026112  mov     r8, rdi
0x180026115  lea     rdi, ?m_regParent@CandidateList@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CandidateList::m_regParent
0x18002611c  mov     rcx, rdi; void *
0x18002611f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180026124  mov     rdx, rdi
0x180026127  cmp     cs:qword_1800526A8, 8
0x18002612f  cmovnb  rdx, cs:?m_regParent@CandidateList@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CandidateList::m_regParent
0x180026137  mov     rax, cs:qword_1800526A0
0x18002613e  lea     rdx, [rdx+rax*2]
0x180026142  mov     rax, rdi
0x180026145  cmovnb  rax, cs:?m_regParent@CandidateList@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CandidateList::m_regParent
0x18002614d  test    rdx, rdx
0x180026150  jnz     short loc_180026157
0x180026152  mov     rdx, rbp
0x180026155  jmp     short loc_18002615D
0x180026157  sub     rdx, rax
0x18002615a  sar     rdx, 1
0x18002615d  mov     r9d, 5Ch ; '\'
0x180026163  lea     r8d, [r9-5Bh]
0x180026167  mov     rcx, rdi
0x18002616a  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0G@Z; std::wstring::insert(unsigned __int64,unsigned __int64,ushort)
0x18002616f  lea     rdx, ?c_uicc@@3QBGB; "UICC"
0x180026176  mov     rcx, rdi; Src
0x180026179  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18002617e  nop
0x18002617f  mov     [rsp+88h+hKey], rbp
0x180026184  lea     rdx, [rsp+88h+var_48]
0x180026189  mov     rcx, rbx
0x18002618c  call    ?ComposeFullListPath@CandidateList@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CandidateList::ComposeFullListPath(void)
0x180026191  cmp     qword ptr [rax+18h], 8
0x180026196  jb      short loc_18002619B
0x180026198  mov     rax, [rax]
0x18002619b  lea     rcx, [rsp+88h+hKey]
0x1800261a0  mov     qword ptr [rsp+88h+phkResult], rcx; unsigned int
0x1800261a5  mov     r9d, 2001Fh; samDesired
0x1800261ab  xor     r8d, r8d; ulOptions
0x1800261ae  mov     rdx, rax; lpSubKey
0x1800261b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800261b8  call    cs:__imp_RegOpenKeyExW
0x1800261be  mov     edi, eax
0x1800261c0  cmp     [rsp+88h+var_30], 8
0x1800261c6  jb      short loc_1800261D3
0x1800261c8  mov     rcx, [rsp+88h+var_48]
0x1800261cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800261d3  test    edi, edi
0x1800261d5  jnz     short loc_180026216
0x1800261d7  lea     rdx, [rsp+88h+hKey]
0x1800261dc  mov     rcx, rbx
0x1800261df  call    ?InitializePersistList@CandidateList@@IEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CandidateList::InitializePersistList(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800261e4  nop
0x1800261e5  mov     rcx, [rsp+88h+hKey]; hKey
0x1800261ea  test    rcx, rcx
0x1800261ed  jz      short loc_1800261F6
0x1800261ef  call    cs:__imp_RegCloseKey
0x1800261f5  nop
0x1800261f6  mov     rax, rbx
0x1800261f9  mov     rcx, [rsp+88h+var_28]
0x1800261fe  xor     rcx, rsp; StackCookie
0x180026201  call    __security_check_cookie
0x180026206  mov     rbx, [rsp+88h+arg_8]
0x18002620e  add     rsp, 70h
0x180026212  pop     rdi
0x180026213  pop     rsi
0x180026214  pop     rbp
0x180026215  retn
0x180026216  cmp     edi, 2
0x180026219  jz      short loc_1800261E5
0x18002621b  mov     rcx, [rsp+88h]; this
0x180026223  mov     r9d, edi; char *
0x180026226  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002622d  mov     edx, 0AFh; void *
0x180026232  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
