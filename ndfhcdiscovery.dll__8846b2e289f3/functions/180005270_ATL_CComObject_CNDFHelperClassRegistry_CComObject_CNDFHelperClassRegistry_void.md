# ATL::CComObject<CNDFHelperClassRegistry>::CComObject<CNDFHelperClassRegistry>(void *)

- ea: `0x180005270`
- end: `0x1800053a0`
- name: `??0?$CComObject@VCNDFHelperClassRegistry@@@ATL@@QEAA@PEAX@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c9c`

## callees

- `0x180005270`
- `0x180009fcc`
- `0x18000a00c`
- `0x180015010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180005362`
- `KERNEL32!InitializeCriticalSection` at `0x180005362`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComObject<CNDFHelperClassRegistry>::CComObject<CNDFHelperClassRegistry>(__int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // rdx
  wchar_t *v4; // rax
  _BYTE *v5; // rcx
  __int64 v6; // rcx
  const wchar_t *v7; // rdx
  wchar_t v8; // r9
  wchar_t *v9; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_QWORD *)a1 = &CNDFHelperClassRegistry::`vftable';
  *(_QWORD *)(a1 + 584) = 0;
  *(_QWORD *)(a1 + 592) = 0;
  *(_QWORD *)(a1 + 584) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode();
  *(_QWORD *)(a1 + 600) = 0;
  *(_QWORD *)(a1 + 608) = 0;
  *(_QWORD *)(a1 + 600) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode();
  *(_QWORD *)(a1 + 616) = 0;
  *(_QWORD *)(a1 + 624) = 0;
  *(_QWORD *)(a1 + 616) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
  *(_DWORD *)(a1 + 632) = 0;
  *(_QWORD *)(a1 + 640) = 0;
  *(_QWORD *)(a1 + 648) = 0;
  v2 = 260;
  v3 = 260;
  v4 = (wchar_t *)(a1 + 64);
  v5 = (_BYTE *)(a1 + 64);
  do
  {
    *v5++ = 0;
    --v3;
  }
  while ( v3 );
  v6 = 2147483646;
  v7 = L"SYSTEM\\CurrentControlSet\\Control\\NetDiagFx";
  do
  {
    if ( !v6 )
      break;
    v8 = *v7;
    if ( !*v7 )
      break;
    ++v7;
    *v4++ = v8;
    --v6;
    --v2;
  }
  while ( v2 );
  v9 = v4 - 1;
  if ( v2 )
    v9 = v4;
  *v9 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 656));
  *(_QWORD *)a1 = &ATL::CComObject<CNDFHelperClassRegistry>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x180005270  mov     [rsp+arg_10], rbx
0x180005275  mov     [rsp+arg_18], rsi
0x18000527a  mov     [rsp+arg_0], rcx
0x18000527f  push    rdi
0x180005280  sub     rsp, 20h
0x180005284  mov     rdi, rcx
0x180005287  xor     esi, esi
0x180005289  mov     [rcx+8], esi
0x18000528c  xorps   xmm0, xmm0
0x18000528f  xor     eax, eax
0x180005291  movups  xmmword ptr [rcx+10h], xmm0
0x180005295  movups  xmmword ptr [rcx+20h], xmm0
0x180005299  mov     [rcx+30h], rax
0x18000529d  mov     [rcx+38h], sil
0x1800052a1  lea     rax, ??_7CNDFHelperClassRegistry@@6B@; const CNDFHelperClassRegistry::`vftable'
0x1800052a8  mov     [rcx], rax
0x1800052ab  lea     rbx, [rcx+248h]
0x1800052b2  mov     [rbx], rsi
0x1800052b5  mov     [rbx+8], rsi
0x1800052b9  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode(void)
0x1800052be  mov     [rbx], rax
0x1800052c1  lea     rbx, [rdi+258h]
0x1800052c8  mov     [rbx], rsi
0x1800052cb  mov     [rbx+8], rsi
0x1800052cf  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,CNDFHelperClass *>>>::_Buyheadnode(void)
0x1800052d4  mov     [rbx], rax
0x1800052d7  lea     rbx, [rdi+268h]
0x1800052de  mov     [rbx], rsi
0x1800052e1  mov     [rbx+8], rsi
0x1800052e5  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x1800052ea  mov     [rbx], rax
0x1800052ed  mov     [rdi+278h], esi
0x1800052f3  mov     [rdi+280h], rsi
0x1800052fa  mov     [rdi+288h], rsi
0x180005301  mov     r8d, 104h
0x180005307  mov     edx, r8d
0x18000530a  lea     rax, [rdi+40h]
0x18000530e  mov     rcx, rax
0x180005311  mov     [rcx], sil
0x180005314  inc     rcx
0x180005317  sub     rdx, 1
0x18000531b  jnz     short loc_180005311
0x18000531d  mov     ecx, 7FFFFFFEh
0x180005322  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180005329  test    rcx, rcx
0x18000532c  jz      short loc_18000534D
0x18000532e  movzx   r9d, word ptr [rdx]
0x180005332  test    r9w, r9w
0x180005336  jz      short loc_18000534D
0x180005338  add     rdx, 2
0x18000533c  mov     [rax], r9w
0x180005340  add     rax, 2
0x180005344  dec     rcx
0x180005347  sub     r8, 1
0x18000534b  jnz     short loc_180005329
0x18000534d  lea     rcx, [rax-2]
0x180005351  test    r8, r8
0x180005354  cmovnz  rcx, rax
0x180005358  mov     [rcx], si
0x18000535b  lea     rcx, [rdi+290h]; lpCriticalSection
0x180005362  call    cs:__imp_InitializeCriticalSection
0x180005369  nop     dword ptr [rax+rax+00h]
0x18000536e  nop
0x18000536f  lea     rax, ??_7?$CComObject@VCNDFHelperClassRegistry@@@ATL@@6B@; const ATL::CComObject<CNDFHelperClassRegistry>::`vftable'
0x180005376  mov     [rdi], rax
0x180005379  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005380  mov     rax, [rcx]
0x180005383  mov     rax, [rax+8]
0x180005387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538c  mov     rax, rdi
0x18000538f  mov     rbx, [rsp+28h+arg_10]
0x180005394  mov     rsi, [rsp+28h+arg_18]
0x180005399  add     rsp, 20h
0x18000539d  pop     rdi
0x18000539e  retn
```
