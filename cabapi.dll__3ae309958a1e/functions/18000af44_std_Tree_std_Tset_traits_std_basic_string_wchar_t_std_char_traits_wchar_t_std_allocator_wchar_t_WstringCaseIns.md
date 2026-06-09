# std::_Tree<std::_Tset_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,0>>::insert<0,0>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000af44`
- end: `0x18000b0f8`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z`
- size: `436`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c38c`

## callees

- `0x180001570`
- `0x180001f82`
- `0x180007fd0`
- `0x18000af44`
- `0x18000c4e0`
- `0x18000c710`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::insert<0,0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // r12
  __int64 inserted; // rdi
  int v7; // r15d
  __int64 v8; // rbx
  char v9; // r13
  const wchar_t *v10; // rdx
  size_t v11; // r15
  const wchar_t *v12; // rcx
  size_t v13; // r12
  size_t v14; // r8
  int v15; // eax
  const wchar_t *v16; // rdx
  size_t v17; // rbx
  const wchar_t *v18; // rcx
  size_t v19; // rbp
  size_t v20; // r8
  int v21; // eax
  __int64 v22; // rbx
  _QWORD *v23; // rdi
  __int64 *v25; // [rsp+20h] [rbp-68h] BYREF
  int v26; // [rsp+28h] [rbp-60h]
  int v27; // [rsp+2Ch] [rbp-5Ch]
  __int64 v28; // [rsp+30h] [rbp-58h]
  __int64 v29; // [rsp+38h] [rbp-50h]
  __int64 v30; // [rsp+40h] [rbp-48h]

  v30 = -2;
  v5 = a1;
  v25 = a1;
  inserted = *a1;
  v28 = *(_QWORD *)(*a1 + 8);
  v7 = 0;
  v29 = 0;
  v8 = v28;
  v9 = 1;
  if ( !*(_BYTE *)(v28 + 25) )
  {
    while ( 1 )
    {
      v28 = v8;
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v10 = (const wchar_t *)a3;
      else
        v10 = *(const wchar_t **)a3;
      v11 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(v8 + 56) <= 7u )
        v12 = (const wchar_t *)(v8 + 32);
      else
        v12 = *(const wchar_t **)(v8 + 32);
      v13 = *(_QWORD *)(v8 + 48);
      v14 = v13;
      if ( v13 > v11 )
        v14 = *(_QWORD *)(a3 + 16);
      v15 = wcsnicmp(v12, v10, v14);
      if ( v15 )
      {
        if ( v15 < 0 )
          goto LABEL_19;
      }
      else if ( v13 < v11 )
      {
LABEL_19:
        v7 = 0;
        v8 = *(_QWORD *)(v8 + 16);
        goto LABEL_13;
      }
      v7 = 1;
      inserted = v8;
      v8 = *(_QWORD *)v8;
LABEL_13:
      if ( *(_BYTE *)(v8 + 25) )
      {
        v5 = v25;
        break;
      }
    }
  }
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_28;
  if ( *(_QWORD *)(inserted + 56) <= 7u )
    v16 = (const wchar_t *)(inserted + 32);
  else
    v16 = *(const wchar_t **)(inserted + 32);
  v17 = *(_QWORD *)(inserted + 48);
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v18 = (const wchar_t *)a3;
  else
    v18 = *(const wchar_t **)a3;
  v19 = *(_QWORD *)(a3 + 16);
  v20 = v19;
  if ( v19 > v17 )
    v20 = *(_QWORD *)(inserted + 48);
  v21 = wcsnicmp(v18, v16, v20);
  if ( !v21 )
  {
    if ( v19 < v17 )
      goto LABEL_28;
LABEL_32:
    v9 = 0;
    goto LABEL_30;
  }
  if ( v21 >= 0 )
    goto LABEL_32;
LABEL_28:
  if ( v5[1] == 0x3FFFFFFFFFFFFFFLL )
    std::_Throw_tree_length_error();
  v22 = *v5;
  v23 = operator new(0x40u);
  std::wstring::wstring(v23 + 4, a3);
  *v23 = v22;
  v23[1] = v22;
  v23[2] = v22;
  *((_WORD *)v23 + 12) = 0;
  v25 = (__int64 *)v28;
  v26 = v7;
  v27 = v29;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
               v5,
               &v25,
               v23);
LABEL_30:
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v9;
  return a2;
}

```

## disassembly

```asm
0x18000af44  mov     rax, rsp
0x18000af47  push    rbp
0x18000af48  push    rsi
0x18000af49  push    rdi
0x18000af4a  push    r12
0x18000af4c  push    r13
0x18000af4e  push    r14
0x18000af50  push    r15
0x18000af52  sub     rsp, 50h
0x18000af56  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000af5e  mov     [rax+20h], rbx
0x18000af62  mov     rsi, r8
0x18000af65  mov     r14, rdx
0x18000af68  mov     r12, rcx
0x18000af6b  mov     [rsp+88h+var_68], rcx
0x18000af70  mov     rdi, [rcx]
0x18000af73  mov     rax, [rdi+8]
0x18000af77  mov     [rsp+88h+var_58], rax
0x18000af7c  xor     r15d, r15d
0x18000af7f  xor     ecx, ecx
0x18000af81  mov     [rsp+88h+var_50], rcx
0x18000af86  mov     rbx, rax
0x18000af89  lea     r13d, [r15+1]
0x18000af8d  cmp     [rax+19h], cl
0x18000af90  jnz     short loc_18000AFE8
0x18000af92  mov     [rsp+88h+var_58], rbx
0x18000af97  cmp     qword ptr [rsi+18h], 7
0x18000af9c  jbe     short loc_18000AFA3
0x18000af9e  mov     rdx, [rsi]
0x18000afa1  jmp     short loc_18000AFA6
0x18000afa3  mov     rdx, rsi; String2
0x18000afa6  mov     r15, [rsi+10h]
0x18000afaa  cmp     qword ptr [rbx+38h], 7
0x18000afaf  jbe     short loc_18000AFB7
0x18000afb1  mov     rcx, [rbx+20h]
0x18000afb5  jmp     short loc_18000AFBB
0x18000afb7  lea     rcx, [rbx+20h]; String1
0x18000afbb  mov     r12, [rbx+30h]
0x18000afbf  mov     r8, r12
0x18000afc2  cmp     r12, r15
0x18000afc5  cmova   r8, r15; MaxCount
0x18000afc9  call    _wcsnicmp
0x18000afce  test    eax, eax
0x18000afd0  jz      short loc_18000AFFB
0x18000afd2  js      short loc_18000B000
0x18000afd4  mov     r15d, r13d
0x18000afd7  mov     rdi, rbx
0x18000afda  mov     rbx, [rbx]
0x18000afdd  cmp     byte ptr [rbx+19h], 0
0x18000afe1  jz      short loc_18000AF92
0x18000afe3  mov     r12, [rsp+88h+var_68]
0x18000afe8  cmp     byte ptr [rdi+19h], 0
0x18000afec  jnz     short loc_18000B041
0x18000afee  cmp     qword ptr [rdi+38h], 7
0x18000aff3  jbe     short loc_18000B009
0x18000aff5  mov     rdx, [rdi+20h]
0x18000aff9  jmp     short loc_18000B00D
0x18000affb  cmp     r12, r15
0x18000affe  jnb     short loc_18000AFD4
0x18000b000  xor     r15d, r15d
0x18000b003  mov     rbx, [rbx+10h]
0x18000b007  jmp     short loc_18000AFDD
0x18000b009  lea     rdx, [rdi+20h]; String2
0x18000b00d  mov     rbx, [rdi+30h]
0x18000b011  cmp     qword ptr [rsi+18h], 7
0x18000b016  jbe     short loc_18000B01D
0x18000b018  mov     rcx, [rsi]
0x18000b01b  jmp     short loc_18000B020
0x18000b01d  mov     rcx, rsi; String1
0x18000b020  mov     rbp, [rsi+10h]
0x18000b024  mov     r8, rbp
0x18000b027  cmp     rbp, rbx
0x18000b02a  cmova   r8, rbx; MaxCount
0x18000b02e  call    _wcsnicmp
0x18000b033  test    eax, eax
0x18000b035  jz      loc_18000B0E4
0x18000b03b  jns     loc_18000B0ED
0x18000b041  mov     rax, 3FFFFFFFFFFFFFFh
0x18000b04b  cmp     [r12+8], rax
0x18000b050  jz      loc_18000B0F2
0x18000b056  mov     rbx, [r12]
0x18000b05a  mov     [rsp+88h+var_68], r12
0x18000b05f  mov     [rsp+88h+var_60], 0
0x18000b068  mov     ecx, 40h ; '@'; Size
0x18000b06d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b072  mov     rdi, rax
0x18000b075  mov     [rsp+88h+var_60], rax
0x18000b07a  lea     rcx, [rax+20h]
0x18000b07e  mov     rdx, rsi
0x18000b081  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b086  mov     [rdi], rbx
0x18000b089  mov     [rdi+8], rbx
0x18000b08d  mov     [rdi+10h], rbx
0x18000b091  mov     word ptr [rdi+18h], 0
0x18000b097  mov     rax, [rsp+88h+var_58]
0x18000b09c  mov     [rsp+88h+var_68], rax
0x18000b0a1  mov     dword ptr [rsp+88h+var_60], r15d
0x18000b0a6  mov     rax, [rsp+88h+var_50]
0x18000b0ab  mov     dword ptr [rsp+88h+var_60+4], eax
0x18000b0af  mov     r8, rdi
0x18000b0b2  lea     rdx, [rsp+88h+var_68]
0x18000b0b7  mov     rcx, r12
0x18000b0ba  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000b0bf  mov     rdi, rax
0x18000b0c2  mov     [r14], rdi
0x18000b0c5  mov     [r14+8], r13b
0x18000b0c9  mov     rax, r14
0x18000b0cc  mov     rbx, [rsp+88h+arg_18]
0x18000b0d4  add     rsp, 50h
0x18000b0d8  pop     r15
0x18000b0da  pop     r14
0x18000b0dc  pop     r13
0x18000b0de  pop     r12
0x18000b0e0  pop     rdi
0x18000b0e1  pop     rsi
0x18000b0e2  pop     rbp
0x18000b0e3  retn
0x18000b0e4  cmp     rbp, rbx
0x18000b0e7  jb      loc_18000B041
0x18000b0ed  xor     r13b, r13b
0x18000b0f0  jmp     short loc_18000B0C2
0x18000b0f2  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
