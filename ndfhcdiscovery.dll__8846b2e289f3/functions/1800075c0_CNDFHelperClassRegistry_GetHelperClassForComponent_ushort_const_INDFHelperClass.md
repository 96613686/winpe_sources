# CNDFHelperClassRegistry::GetHelperClassForComponent(ushort const *,INDFHelperClass * *)

- ea: `0x1800075c0`
- end: `0x180007740`
- name: `?GetHelperClassForComponent@CNDFHelperClassRegistry@@UEAAJPEBGPEAPEAUINDFHelperClass@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, const unsigned __int16 *Src, struct INDFHelperClass **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800075c0`
- `0x180007a20`
- `0x180008a20`
- `0x18000a528`
- `0x18000af14`
- `0x18000b0cc`
- `0x1800136b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800076a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800076a1`
- `KERNEL32!EnterCriticalSection` at `0x180007600`
- `KERNEL32!EnterCriticalSection` at `0x180007600`
- `KERNEL32!LeaveCriticalSection` at `0x180007626`
- `KERNEL32!LeaveCriticalSection` at `0x180007646`
- `KERNEL32!LeaveCriticalSection` at `0x180007626`
- `KERNEL32!LeaveCriticalSection` at `0x180007646`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CNDFHelperClassRegistry::GetHelperClassForComponent(
        CNDFHelperClassRegistry *this,
        unsigned __int16 *Src,
        struct INDFHelperClass **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int v7; // esi
  int v9; // ecx
  __int64 v10; // rdi
  const unsigned __int16 *v11; // rdx
  _BYTE v12[8]; // [rsp+30h] [rbp-58h] BYREF
  void *v13[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v14; // [rsp+48h] [rbp-40h]
  unsigned __int64 v15; // [rsp+50h] [rbp-38h]

  if ( !Src || !a3 )
    return 2147942487LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 656);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  if ( !*((_DWORD *)this + 158) )
  {
    v7 = CNDFHelperClassRegistry::InitializeData(this);
    if ( v7 < 0 )
    {
      LeaveCriticalSection(v6);
      return (unsigned int)v7;
    }
    *((_DWORD *)this + 158) = 1;
  }
  LeaveCriticalSection(v6);
  v15 = 7;
  v14 = 0;
  LOWORD(v13[0]) = 0;
  std::wstring::assign(v13, Src);
  v10 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                     (char *)this + 616,
                     v12,
                     v13);
  if ( v15 >= 8 )
    operator delete(v13[0]);
  v15 = 7;
  v14 = 0;
  LOWORD(v13[0]) = 0;
  if ( v10 == *((_QWORD *)this + 77) )
  {
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqz_EventWriteTransfer(v9, (unsigned int)ComponentError, -2147024894, 369, (__int64)Src);
    return 2147942402LL;
  }
  else
  {
    v11 = (const unsigned __int16 *)(v10 + 64);
    if ( *(_QWORD *)(v10 + 88) >= 8u )
      v11 = *(const unsigned __int16 **)v11;
    return CNDFHelperClassRegistry::PrivGetHelperClass(this, v11, a3);
  }
}

```

## disassembly

```asm
0x1800075c0  push    rbx
0x1800075c2  push    rsi
0x1800075c3  push    rdi
0x1800075c4  push    r14
0x1800075c6  push    r15
0x1800075c8  sub     rsp, 60h
0x1800075cc  mov     rax, cs:__security_cookie
0x1800075d3  xor     rax, rsp
0x1800075d6  mov     [rsp+88h+var_30], rax
0x1800075db  mov     r15, r8
0x1800075de  mov     r14, rdx
0x1800075e1  mov     rbx, rcx
0x1800075e4  test    rdx, rdx
0x1800075e7  jz      loc_180007721
0x1800075ed  test    r8, r8
0x1800075f0  jz      loc_180007721
0x1800075f6  lea     rdi, [rcx+290h]
0x1800075fd  mov     rcx, rdi; lpCriticalSection
0x180007600  call    cs:__imp_EnterCriticalSection
0x180007607  nop     dword ptr [rax+rax+00h]
0x18000760c  cmp     dword ptr [rbx+278h], 0
0x180007613  jnz     short loc_180007643
0x180007615  mov     rcx, rbx; this
0x180007618  call    ?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ; CNDFHelperClassRegistry::InitializeData(void)
0x18000761d  mov     esi, eax
0x18000761f  test    eax, eax
0x180007621  jns     short loc_180007639
0x180007623  mov     rcx, rdi; lpCriticalSection
0x180007626  call    cs:__imp_LeaveCriticalSection
0x18000762d  nop     dword ptr [rax+rax+00h]
0x180007632  mov     eax, esi
0x180007634  jmp     loc_180007726
0x180007639  mov     dword ptr [rbx+278h], 1
0x180007643  mov     rcx, rdi; lpCriticalSection
0x180007646  call    cs:__imp_LeaveCriticalSection
0x18000764d  nop     dword ptr [rax+rax+00h]
0x180007652  mov     [rsp+88h+var_38], 7
0x18000765b  mov     [rsp+88h+var_40], 0
0x180007664  xor     eax, eax
0x180007666  mov     word ptr [rsp+88h+var_50], ax
0x18000766b  mov     rdx, r14; Src
0x18000766e  lea     rcx, [rsp+88h+var_50]; void *
0x180007673  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007678  lea     rsi, [rbx+268h]
0x18000767f  lea     r8, [rsp+88h+var_50]
0x180007684  lea     rdx, [rsp+88h+var_58]
0x180007689  mov     rcx, rsi
0x18000768c  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180007691  mov     rdi, [rax]
0x180007694  cmp     [rsp+88h+var_38], 8
0x18000769a  jb      short loc_1800076AD
0x18000769c  mov     rcx, [rsp+88h+var_50]
0x1800076a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800076a8  nop     dword ptr [rax+rax+00h]
0x1800076ad  mov     [rsp+88h+var_38], 7
0x1800076b6  mov     [rsp+88h+var_40], 0
0x1800076bf  xor     eax, eax
0x1800076c1  mov     word ptr [rsp+88h+var_50], ax
0x1800076c6  cmp     rdi, [rsi]
0x1800076c9  jz      short loc_1800076E6
0x1800076cb  lea     rdx, [rdi+40h]
0x1800076cf  cmp     qword ptr [rdx+18h], 8
0x1800076d4  jb      short loc_1800076D9
0x1800076d6  mov     rdx, [rdx]; unsigned __int16 *
0x1800076d9  mov     r8, r15; struct INDFHelperClass **
0x1800076dc  mov     rcx, rbx; this
0x1800076df  call    ?PrivGetHelperClass@CNDFHelperClassRegistry@@AEAAJPEBGPEAPEAUINDFHelperClass@@@Z; CNDFHelperClassRegistry::PrivGetHelperClass(ushort const *,INDFHelperClass * *)
0x1800076e4  jmp     short loc_180007726
0x1800076e6  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x1800076ed  jz      short loc_18000770C
0x1800076ef  mov     [rsp+88h+var_68], r14
0x1800076f4  mov     r9d, 171h
0x1800076fa  mov     r8d, 80070002h
0x180007700  lea     rdx, ComponentError
0x180007707  call    McTemplateU0qqz_EventWriteTransfer
0x18000770c  mov     eax, 80070002h
0x180007711  jmp     short loc_180007726
0x180007713  mov     eax, 8007000Eh
0x180007718  jmp     short loc_18000771F
0x18000771a  mov     eax, 80004005h
0x18000771f  jmp     short loc_180007726
0x180007721  mov     eax, 80070057h
0x180007726  mov     rcx, [rsp+88h+var_30]
0x18000772b  xor     rcx, rsp; StackCookie
0x18000772e  call    __security_check_cookie
0x180007733  add     rsp, 60h
0x180007737  pop     r15
0x180007739  pop     r14
0x18000773b  pop     rdi
0x18000773c  pop     rsi
0x18000773d  pop     rbx
0x18000773e  retn
```
