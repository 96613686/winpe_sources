# std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,unsigned __int64>>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,unsigned __int64>,0>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,unsigned __int64> &&)

- ea: `0x18000debc`
- end: `0x18000e044`
- name: `??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@1@@Z`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e188`

## callees

- `0x180001570`
- `0x180001f76`
- `0x18000c4e0`
- `0x18000c710`
- `0x18000debc`

## pseudocode

```c
__int64 __fastcall std::map<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>>::insert<std::pair<std::wstring,unsigned __int64>,0>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // r13
  __int64 inserted; // rbx
  __int64 v7; // rdi
  int v8; // r12d
  _QWORD *v9; // r14
  char v10; // bp
  __int64 v11; // r13
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rcx
  __int64 v16; // rbx
  _OWORD *v17; // rax
  _QWORD *v19; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  __int64 v22; // [rsp+38h] [rbp-40h]

  v22 = -2;
  v5 = a1;
  v19 = a1;
  inserted = *a1;
  v7 = *(_QWORD *)(*a1 + 8LL);
  v8 = 0;
  v21 = 0;
  v9 = (_QWORD *)(a3 + 24);
  v10 = 1;
  if ( !*(_BYTE *)(v7 + 25) )
  {
    do
    {
      v11 = v7;
      v12 = (const wchar_t *)(v7 + 32);
      if ( *v9 <= 7u )
        v13 = (const wchar_t *)a3;
      else
        v13 = *(const wchar_t **)a3;
      if ( *(_QWORD *)(v7 + 56) > 7u )
        v12 = *(const wchar_t **)v12;
      if ( wcsicmp(v12, v13) >= 0 )
      {
        v8 = 1;
        inserted = v7;
        v7 = *(_QWORD *)v7;
      }
      else
      {
        v8 = 0;
        v7 = *(_QWORD *)(v7 + 16);
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
    v7 = v11;
    v5 = v19;
  }
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_20;
  v14 = (const wchar_t *)(inserted + 32);
  if ( *(_QWORD *)(inserted + 56) > 7u )
    v14 = *(const wchar_t **)v14;
  v15 = *v9 <= 7u ? (const wchar_t *)a3 : *(const wchar_t **)a3;
  if ( wcsicmp(v15, v14) < 0 )
  {
LABEL_20:
    if ( v5[1] == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v16 = *v5;
    v19 = v5;
    v20 = 0;
    v17 = operator new(0x48u);
    v17[2] = 0;
    *((_QWORD *)v17 + 6) = 0;
    *((_QWORD *)v17 + 7) = 0;
    v17[2] = *(_OWORD *)a3;
    v17[3] = *(_OWORD *)(a3 + 16);
    *(_QWORD *)(a3 + 16) = 0;
    *v9 = 7;
    *(_WORD *)a3 = 0;
    *((_QWORD *)v17 + 8) = *(_QWORD *)(a3 + 32);
    *(_QWORD *)v17 = v16;
    *((_QWORD *)v17 + 1) = v16;
    *((_QWORD *)v17 + 2) = v16;
    *((_WORD *)v17 + 12) = 0;
    v19 = (_QWORD *)v7;
    v20 = __PAIR64__(v21, v8);
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
                 v5,
                 &v19,
                 v17);
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x18000debc  mov     rax, rsp
0x18000debf  push    rbp
0x18000dec0  push    rsi
0x18000dec1  push    rdi
0x18000dec2  push    r12
0x18000dec4  push    r13
0x18000dec6  push    r14
0x18000dec8  push    r15
0x18000deca  sub     rsp, 40h
0x18000dece  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18000ded6  mov     [rax+20h], rbx
0x18000deda  mov     rsi, r8
0x18000dedd  mov     r15, rdx
0x18000dee0  mov     r13, rcx
0x18000dee3  mov     [rsp+78h+var_58], rcx
0x18000dee8  mov     rbx, [rcx]
0x18000deeb  mov     rdi, [rbx+8]
0x18000deef  xor     r12d, r12d
0x18000def2  xor     eax, eax
0x18000def4  mov     [rsp+78h+var_48], rax
0x18000def9  lea     r14, [r8+18h]
0x18000defd  lea     ebp, [rax+1]
0x18000df00  cmp     [rdi+19h], al
0x18000df03  jnz     short loc_18000DF4D
0x18000df05  mov     r13, rdi
0x18000df08  lea     rcx, [rdi+20h]
0x18000df0c  cmp     qword ptr [r14], 7
0x18000df10  jbe     short loc_18000DF17
0x18000df12  mov     rdx, [rsi]
0x18000df15  jmp     short loc_18000DF1A
0x18000df17  mov     rdx, rsi; String2
0x18000df1a  cmp     qword ptr [rcx+18h], 7
0x18000df1f  jbe     short loc_18000DF24
0x18000df21  mov     rcx, [rcx]; String1
0x18000df24  call    _wcsicmp
0x18000df29  test    eax, eax
0x18000df2b  jns     short loc_18000DF36
0x18000df2d  xor     r12d, r12d
0x18000df30  mov     rdi, [rdi+10h]
0x18000df34  jmp     short loc_18000DF3F
0x18000df36  mov     r12d, ebp
0x18000df39  mov     rbx, rdi
0x18000df3c  mov     rdi, [rdi]
0x18000df3f  cmp     byte ptr [rdi+19h], 0
0x18000df43  jz      short loc_18000DF05
0x18000df45  mov     rdi, r13
0x18000df48  mov     r13, [rsp+78h+var_58]
0x18000df4d  cmp     byte ptr [rbx+19h], 0
0x18000df51  jnz     short loc_18000DF80
0x18000df53  lea     rdx, [rbx+20h]
0x18000df57  cmp     qword ptr [rdx+18h], 7
0x18000df5c  jbe     short loc_18000DF61
0x18000df5e  mov     rdx, [rdx]; String2
0x18000df61  cmp     qword ptr [r14], 7
0x18000df65  jbe     short loc_18000DF6C
0x18000df67  mov     rcx, [rsi]
0x18000df6a  jmp     short loc_18000DF6F
0x18000df6c  mov     rcx, rsi; String1
0x18000df6f  call    _wcsicmp
0x18000df74  test    eax, eax
0x18000df76  js      short loc_18000DF80
0x18000df78  xor     bpl, bpl
0x18000df7b  jmp     loc_18000E01C
0x18000df80  mov     rax, 38E38E38E38E38Eh
0x18000df8a  cmp     [r13+8], rax
0x18000df8e  jz      loc_18000E03E
0x18000df94  mov     rbx, [r13+0]
0x18000df98  mov     [rsp+78h+var_58], r13
0x18000df9d  mov     [rsp+78h+var_50], 0
0x18000dfa6  mov     ecx, 48h ; 'H'; Size
0x18000dfab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dfb0  mov     r8, rax
0x18000dfb3  xorps   xmm0, xmm0
0x18000dfb6  movups  xmmword ptr [rax+20h], xmm0
0x18000dfba  xor     ecx, ecx
0x18000dfbc  mov     [rax+30h], rcx
0x18000dfc0  mov     [rax+38h], rcx
0x18000dfc4  movups  xmm0, xmmword ptr [rsi]
0x18000dfc7  movups  xmmword ptr [rax+20h], xmm0
0x18000dfcb  movups  xmm1, xmmword ptr [rsi+10h]
0x18000dfcf  movups  xmmword ptr [rax+30h], xmm1
0x18000dfd3  mov     [rsi+10h], rcx
0x18000dfd7  mov     qword ptr [r14], 7
0x18000dfde  mov     [rsi], cx
0x18000dfe1  mov     rax, [rsi+20h]
0x18000dfe5  mov     [r8+40h], rax
0x18000dfe9  mov     [r8], rbx
0x18000dfec  mov     [r8+8], rbx
0x18000dff0  mov     [r8+10h], rbx
0x18000dff4  mov     [r8+18h], cx
0x18000dff9  mov     [rsp+78h+var_58], rdi
0x18000dffe  mov     dword ptr [rsp+78h+var_50], r12d
0x18000e003  mov     rax, [rsp+78h+var_48]
0x18000e008  mov     dword ptr [rsp+78h+var_50+4], eax
0x18000e00c  lea     rdx, [rsp+78h+var_58]
0x18000e011  mov     rcx, r13
0x18000e014  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000e019  mov     rbx, rax
0x18000e01c  mov     [r15], rbx
0x18000e01f  mov     [r15+8], bpl
0x18000e023  mov     rax, r15
0x18000e026  mov     rbx, [rsp+78h+arg_18]
0x18000e02e  add     rsp, 40h
0x18000e032  pop     r15
0x18000e034  pop     r14
0x18000e036  pop     r13
0x18000e038  pop     r12
0x18000e03a  pop     rdi
0x18000e03b  pop     rsi
0x18000e03c  pop     rbp
0x18000e03d  retn
0x18000e03e  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
