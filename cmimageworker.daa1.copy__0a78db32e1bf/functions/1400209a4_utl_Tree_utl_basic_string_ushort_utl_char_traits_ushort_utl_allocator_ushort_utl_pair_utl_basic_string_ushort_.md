# utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::emplace<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)

- ea: `0x1400209a4`
- end: `0x140020b71`
- name: `??$emplace@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@$0A@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@0@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140020e00`

## callees

- `0x140002344`
- `0x140002b8c`
- `0x14001f660`
- `0x1400209a4`
- `0x140021288`

## pseudocode

```c
__int64 __fastcall utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::emplace<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
        unsigned __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  unsigned __int64 *v8; // rax
  unsigned __int64 *v9; // rbx
  _OWORD *v10; // rcx
  _OWORD *v11; // rdx
  _OWORD *v12; // rdx
  _OWORD *v13; // rcx
  _OWORD *InsertionPointUniqueUpper; // rax
  __int64 v15; // rbp
  unsigned __int64 *v16; // rcx
  _OWORD v18[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF

  v8 = (unsigned __int64 *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v10 = a3 + 2;
    v11 = v8 + 5;
    if ( (_QWORD *)*a3 == a3 + 2 )
    {
      v8[3] = (unsigned __int64)v11;
      v8[4] = (unsigned __int64)v8 + 2 * ((a3[1] - (_QWORD)a3 - 16LL) >> 1) + 40;
      *v11 = *v10;
    }
    else
    {
      v8[3] = *a3;
      v8[4] = a3[1];
      *(_QWORD *)v11 = *(_QWORD *)v10;
    }
    *a3 = v10;
    *(_WORD *)v10 = 0;
    v12 = v8 + 9;
    a3[1] = v10;
    v13 = a4 + 2;
    if ( (_QWORD *)*a4 == a4 + 2 )
    {
      v8[7] = (unsigned __int64)v12;
      v8[8] = (unsigned __int64)v8 + 2 * ((a4[1] - (_QWORD)a4 - 16LL) >> 1) + 72;
      *v12 = *v13;
    }
    else
    {
      v8[7] = *a4;
      v8[8] = a4[1];
      *(_QWORD *)v12 = *(_QWORD *)v13;
    }
    *a4 = v13;
    *(_WORD *)v13 = 0;
    a4[1] = v13;
  }
  *(_QWORD *)a2 = 0;
  *(_BYTE *)(a2 + 8) = 0;
  if ( !v8 )
    goto LABEL_20;
  if ( *(_QWORD *)(a1 + 16) == a1 )
  {
    *v8 = a1 | 1;
    v8[1] = (unsigned __int64)&utl::_TreeSentinel;
    v8[2] = (unsigned __int64)&utl::_TreeSentinel;
    *(_QWORD *)a1 = v8;
    *(_QWORD *)(a1 + 8) = v8;
    *(_QWORD *)(a1 + 16) = v8;
    ++*(_QWORD *)(a1 + 24);
LABEL_19:
    *(_BYTE *)(a2 + 8) = 1;
LABEL_20:
    *(_QWORD *)a2 = v9;
    return a2;
  }
  v19 = 0;
  InsertionPointUniqueUpper = (_OWORD *)utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_FindInsertionPointUniqueUpper(
                                          a1,
                                          v18,
                                          &v19,
                                          v8 + 3);
  v15 = v19;
  v18[0] = *InsertionPointUniqueUpper;
  if ( !v19 )
  {
    utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::_InsertAt(
      a1,
      v18,
      v9);
    goto LABEL_19;
  }
  v16 = (unsigned __int64 *)v9[7];
  if ( v16 != v9 + 9 )
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64 *)v9[3] != v9 + 5 )
    operator delete((void *)v9[3], (const struct std::nothrow_t *)&std::nothrow);
  operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)a2 = v15;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1400209a4  push    rbx
0x1400209a6  push    rbp
0x1400209a7  push    rsi
0x1400209a8  push    rdi
0x1400209a9  push    r14
0x1400209ab  push    r15
0x1400209ad  sub     rsp, 38h
0x1400209b1  mov     rdi, rdx
0x1400209b4  mov     rsi, rcx
0x1400209b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400209be  mov     ecx, 58h ; 'X'; unsigned __int64
0x1400209c3  mov     r14, r9
0x1400209c6  mov     r15, r8
0x1400209c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400209ce  mov     rbx, rax
0x1400209d1  test    rax, rax
0x1400209d4  jz      loc_140020A84
0x1400209da  mov     rax, [r15]
0x1400209dd  lea     rcx, [r15+10h]
0x1400209e1  lea     rdx, [rbx+28h]
0x1400209e5  cmp     rax, rcx
0x1400209e8  jnz     short loc_140020A11
0x1400209ea  mov     [rbx+18h], rdx
0x1400209ee  mov     rax, [r15+8]
0x1400209f2  sub     rax, r15
0x1400209f5  sub     rax, 10h
0x1400209f9  sar     rax, 1
0x1400209fc  add     rax, 14h
0x140020a00  lea     rax, [rbx+rax*2]
0x140020a04  mov     [rbx+20h], rax
0x140020a08  movups  xmm0, xmmword ptr [rcx]
0x140020a0b  movdqu  xmmword ptr [rdx], xmm0
0x140020a0f  jmp     short loc_140020A23
0x140020a11  mov     [rbx+18h], rax
0x140020a15  mov     rax, [r15+8]
0x140020a19  mov     [rbx+20h], rax
0x140020a1d  mov     rax, [rcx]
0x140020a20  mov     [rdx], rax
0x140020a23  xor     eax, eax
0x140020a25  mov     [r15], rcx
0x140020a28  mov     [rcx], ax
0x140020a2b  lea     rdx, [rbx+48h]
0x140020a2f  mov     [r15+8], rcx
0x140020a33  lea     rcx, [r14+10h]
0x140020a37  mov     rax, [r14]
0x140020a3a  cmp     rax, rcx
0x140020a3d  jnz     short loc_140020A66
0x140020a3f  mov     [rbx+38h], rdx
0x140020a43  mov     rax, [r14+8]
0x140020a47  sub     rax, r14
0x140020a4a  sub     rax, 10h
0x140020a4e  sar     rax, 1
0x140020a51  add     rax, 24h ; '$'
0x140020a55  lea     rax, [rbx+rax*2]
0x140020a59  mov     [rbx+40h], rax
0x140020a5d  movups  xmm0, xmmword ptr [rcx]
0x140020a60  movdqu  xmmword ptr [rdx], xmm0
0x140020a64  jmp     short loc_140020A78
0x140020a66  mov     [rbx+38h], rax
0x140020a6a  mov     rax, [r14+8]
0x140020a6e  mov     [rbx+40h], rax
0x140020a72  mov     rax, [rcx]
0x140020a75  mov     [rdx], rax
0x140020a78  xor     eax, eax
0x140020a7a  mov     [r14], rcx
0x140020a7d  mov     [rcx], ax
0x140020a80  mov     [r14+8], rcx
0x140020a84  mov     qword ptr [rdi], 0
0x140020a8b  mov     byte ptr [rdi+8], 0
0x140020a8f  test    rbx, rbx
0x140020a92  jz      loc_140020B5D
0x140020a98  cmp     [rsi+10h], rsi
0x140020a9c  jnz     short loc_140020ACB
0x140020a9e  mov     rax, rsi
0x140020aa1  or      rax, 1
0x140020aa5  mov     [rbx], rax
0x140020aa8  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140020aaf  mov     [rbx+8], rax
0x140020ab3  mov     [rbx+10h], rax
0x140020ab7  mov     [rsi], rbx
0x140020aba  mov     [rsi+8], rbx
0x140020abe  mov     [rsi+10h], rbx
0x140020ac2  inc     qword ptr [rsi+18h]
0x140020ac6  jmp     loc_140020B59
0x140020acb  lea     r14, [rbx+18h]
0x140020acf  mov     [rsp+68h+arg_8], 0
0x140020ad8  mov     r9, r14
0x140020adb  lea     r8, [rsp+68h+arg_8]
0x140020ae0  lea     rdx, [rsp+68h+var_48]
0x140020ae5  mov     rcx, rsi
0x140020ae8  call    ?_FindInsertionPointUniqueUpper@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@UCompareStringIgnoreCase@CommandLineParser@Tools@Manager@Container@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Container::Manager::Tools::CommandLineParser::CompareStringIgnoreCase,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> * &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x140020aed  mov     rbp, [rsp+68h+arg_8]
0x140020af2  movups  xmm0, xmmword ptr [rax]
0x140020af5  movdqu  [rsp+68h+var_48], xmm0
0x140020afb  test    rbp, rbp
0x140020afe  jz      short loc_140020B49
0x140020b00  mov     rcx, [r14+20h]; void *
0x140020b04  lea     rax, [r14+30h]
0x140020b08  cmp     rcx, rax
0x140020b0b  jz      short loc_140020B19
0x140020b0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020b14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020b19  lea     rax, [r14+10h]
0x140020b1d  cmp     [r14], rax
0x140020b20  jz      short loc_140020B31
0x140020b22  mov     rcx, [r14]; void *
0x140020b25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020b2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020b31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140020b38  mov     rcx, rbx; void *
0x140020b3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020b40  mov     [rdi], rbp
0x140020b43  mov     byte ptr [rdi+8], 0
0x140020b47  jmp     short loc_140020B60
0x140020b49  mov     r8, rbx
0x140020b4c  lea     rdx, [rsp+68h+var_48]
0x140020b51  mov     rcx, rsi
0x140020b54  call    ?_InsertAt@?$_Tree@W4RegistryHive@Image@Manager@Container@@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@U?$less@W4RegistryHive@Image@Manager@Container@@@6@V?$allocator@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@@6@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@@2@@Z; utl::_Tree<Container::Manager::Image::RegistryHive,utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>> *,bool> const &,utl::_TreeNode<utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>> *)
0x140020b59  mov     byte ptr [rdi+8], 1
0x140020b5d  mov     [rdi], rbx
0x140020b60  mov     rax, rdi
0x140020b63  add     rsp, 38h
0x140020b67  pop     r15
0x140020b69  pop     r14
0x140020b6b  pop     rdi
0x140020b6c  pop     rsi
0x140020b6d  pop     rbp
0x140020b6e  pop     rbx
0x140020b6f  retn
```
