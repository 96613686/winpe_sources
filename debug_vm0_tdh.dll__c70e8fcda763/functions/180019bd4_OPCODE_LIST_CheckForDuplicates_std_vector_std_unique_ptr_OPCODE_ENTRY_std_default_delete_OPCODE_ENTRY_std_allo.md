# OPCODE_LIST::CheckForDuplicates(std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>> const &)

- ea: `0x180019bd4`
- end: `0x180019d60`
- name: `?CheckForDuplicates@OPCODE_LIST@@QEAAXAEBV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180018eb8`

## callees

- `0x180019bd4`
- `0x18001b340`
- `0x1800207e4`
- `0x18002cf00`
- `0x18002d058`
- `0x18002ecc0`
- `0x18003104c`
- `0x180031c88`
- `0x1800329ac`
- `0x1800329dc`
- `0x180033df0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OPCODE_LIST::CheckForDuplicates(__int64 a1, __int64 ***a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  __int64 **v5; // rdi
  __int64 **v6; // rbx
  __int64 *v7; // rdx
  __int64 **v8; // rax
  __int64 v9; // rax
  __int64 *v10; // r8
  _QWORD *v12; // [rsp+20h] [rbp-19h] BYREF
  __int64 v13; // [rsp+28h] [rbp-11h]
  _QWORD v14[2]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp+17h] BYREF
  _BYTE v17[16]; // [rsp+60h] [rbp+27h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp+37h] BYREF
  _BYTE v19[16]; // [rsp+80h] [rbp+47h] BYREF

  v14[1] = 0;
  v3 = operator new(0x38u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v14[0] = v3;
  v13 = 0;
  v4 = operator new(0x30u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v12 = v4;
  std::set<std::wstring_view>::set<std::wstring_view>(v15);
  v5 = *a2;
  v6 = a2[1];
  while ( v5 != v6 )
  {
    ((void (__fastcall *)(_QWORD *, _BYTE *, __int64 *, __int64 *, _QWORD *, __int64))std::_Tree<std::_Tset_traits<std::pair<std::wstring_view,TASK_ENTRY *>,std::less<std::pair<std::wstring_view,TASK_ENTRY *>>,std::allocator<std::pair<std::wstring_view,TASK_ENTRY *>>,0>>::_Emplace<std::wstring &,TASK_ENTRY * const &>)(
      v14,
      v16,
      *v5,
      *v5 + 16,
      v12,
      v13);
    v7 = *v5;
    if ( !v16[8] )
    {
      if ( (unsigned __int64)v7[3] > 7 )
        v7 = (__int64 *)*v7;
      ThrowWithFormatMessage(-1073221868, v7);
    }
    std::_Tree<std::_Tset_traits<std::pair<unsigned long,TASK_ENTRY *>,std::less<std::pair<unsigned long,TASK_ENTRY *>>,std::allocator<std::pair<unsigned long,TASK_ENTRY *>>,0>>::_Emplace<unsigned char &,TASK_ENTRY * const &>(
      &v12,
      v17,
      v7 + 4,
      v7 + 16);
    v8 = (__int64 **)*v5;
    if ( !v17[8] )
    {
      if ( (unsigned __int64)v8[3] <= 7 )
        v10 = *v5;
      else
        v10 = *v8;
      ThrowWithFormatMessage(-1073221867, *((unsigned __int8 *)v8 + 32), v10);
    }
    if ( v8[7] )
    {
      v9 = std::wstring::operator std::wstring_view(v8 + 5, v18);
      if ( !*(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(
                         v15,
                         v19,
                         v9)
                     + 8) )
        ThrowWithFormatMessage(-1073221866);
    }
    ++v5;
  }
  std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring_view,void *>>>(
    v15,
    v15);
  std::_Tree<std::_Tmap_traits<unsigned long,STRING_ENTRY *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,STRING_ENTRY *>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,STRING_ENTRY *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,STRING_ENTRY *>>,0>>(&v12);
  return std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>(v14);
}

```

## disassembly

```asm
0x180019bd4  mov     [rsp-8+arg_0], rbx
0x180019bd9  mov     [rsp-8+arg_8], rdi
0x180019bde  push    rbp
0x180019bdf  lea     rbp, [rsp-57h]
0x180019be4  sub     rsp, 90h
0x180019beb  mov     rbx, rdx
0x180019bee  mov     [rbp+57h+var_60], 0
0x180019bf6  mov     [rbp+57h+var_58], 0
0x180019bfe  mov     ecx, 38h ; '8'; Size
0x180019c03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019c08  mov     [rax], rax
0x180019c0b  mov     [rax+8], rax
0x180019c0f  mov     [rax+10h], rax
0x180019c13  mov     word ptr [rax+18h], 101h
0x180019c19  mov     [rbp+57h+var_60], rax
0x180019c1d  mov     [rbp+57h+var_70], 0
0x180019c25  mov     [rbp+57h+var_68], 0
0x180019c2d  mov     ecx, 30h ; '0'; Size
0x180019c32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019c37  mov     [rax], rax
0x180019c3a  mov     [rax+8], rax
0x180019c3e  mov     [rax+10h], rax
0x180019c42  mov     word ptr [rax+18h], 101h
0x180019c48  mov     [rbp+57h+var_70], rax
0x180019c4c  lea     rcx, [rbp+57h+var_50]
0x180019c50  call    ??0?$set@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring_view>::set<std::wstring_view>(void)
0x180019c55  nop
0x180019c56  mov     rdi, [rbx]
0x180019c59  mov     rbx, [rbx+8]
0x180019c5d  cmp     rdi, rbx
0x180019c60  jz      loc_180019D2A
0x180019c66  mov     r8, [rdi]
0x180019c69  lea     r9, [r8+80h]
0x180019c70  lea     rdx, [rbp+57h+var_40]
0x180019c74  lea     rcx, [rbp+57h+var_60]
0x180019c78  call    ??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBQEAVTASK_ENTRY@@@?$_Tree@V?$_Tset_traits@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@U?$less@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@V?$allocator@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEAVTASK_ENTRY@@@Z; std::_Tree<std::_Tset_traits<std::pair<std::wstring_view,TASK_ENTRY *>,std::less<std::pair<std::wstring_view,TASK_ENTRY *>>,std::allocator<std::pair<std::wstring_view,TASK_ENTRY *>>,0>>::_Emplace<std::wstring &,TASK_ENTRY * const &>(std::wstring &,TASK_ENTRY * const &)
0x180019c7d  mov     rdx, [rdi]
0x180019c80  cmp     [rbp+57h+var_38], 0
0x180019c84  jz      loc_180019D15
0x180019c8a  lea     r9, [rdx+80h]
0x180019c91  lea     r8, [rdx+20h]
0x180019c95  lea     rdx, [rbp+57h+var_30]
0x180019c99  lea     rcx, [rbp+57h+var_70]
0x180019c9d  call    ??$_Emplace@AEAEAEBQEAVTASK_ENTRY@@@?$_Tree@V?$_Tset_traits@U?$pair@KPEAVTASK_ENTRY@@@std@@U?$less@U?$pair@KPEAVTASK_ENTRY@@@std@@@2@V?$allocator@U?$pair@KPEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@KPEAVTASK_ENTRY@@@std@@PEAX@std@@_N@1@AEAEAEBQEAVTASK_ENTRY@@@Z; std::_Tree<std::_Tset_traits<std::pair<ulong,TASK_ENTRY *>,std::less<std::pair<ulong,TASK_ENTRY *>>,std::allocator<std::pair<ulong,TASK_ENTRY *>>,0>>::_Emplace<uchar &,TASK_ENTRY * const &>(uchar &,TASK_ENTRY * const &)
0x180019ca2  mov     rax, [rdi]
0x180019ca5  cmp     [rbp+57h+var_28], 0
0x180019ca9  jz      short loc_180019CF7
0x180019cab  cmp     qword ptr [rax+38h], 0
0x180019cb0  jz      short loc_180019CD5
0x180019cb2  lea     rcx, [rax+28h]
0x180019cb6  lea     rdx, [rbp+57h+var_20]
0x180019cba  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180019cbf  mov     r8, rax
0x180019cc2  lea     rdx, [rbp+57h+var_10]
0x180019cc6  lea     rcx, [rbp+57h+var_50]
0x180019cca  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(std::wstring_view &&)
0x180019ccf  cmp     byte ptr [rax+8], 0
0x180019cd3  jz      short loc_180019CDB
0x180019cd5  add     rdi, 8
0x180019cd9  jmp     short loc_180019C5D
0x180019cdb  mov     rdx, [rdi]
0x180019cde  add     rdx, 28h ; '('
0x180019ce2  cmp     qword ptr [rdx+18h], 7
0x180019ce7  jbe     short loc_180019CEC
0x180019ce9  mov     rdx, [rdx]
0x180019cec  mov     ecx, 0C007EF16h; int
0x180019cf1  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x180019cf7  cmp     qword ptr [rax+18h], 7
0x180019cfc  jbe     short loc_180019D03
0x180019cfe  mov     r8, [rax]
0x180019d01  jmp     short loc_180019D06
0x180019d03  mov     r8, rax
0x180019d06  movzx   edx, byte ptr [rax+20h]
0x180019d0a  mov     ecx, 0C007EF15h; int
0x180019d0f  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x180019d15  cmp     qword ptr [rdx+18h], 7
0x180019d1a  jbe     short loc_180019D1F
0x180019d1c  mov     rdx, [rdx]
0x180019d1f  mov     ecx, 0C007EF14h; int
0x180019d24  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x180019d2a  lea     rdx, [rbp+57h+var_50]
0x180019d2e  lea     rcx, [rbp+57h+var_50]
0x180019d32  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring_view,void *>>>(std::allocator<std::_Tree_node<std::wstring_view,void *>> &)
0x180019d37  nop
0x180019d38  lea     rcx, [rbp+57h+var_70]
0x180019d3c  call    ??1?$_Tree@V?$_Tmap_traits@KPEAVSTRING_ENTRY@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVSTRING_ENTRY@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,STRING_ENTRY *,std::less<ulong>,std::allocator<std::pair<ulong const,STRING_ENTRY *>>,0>>::~_Tree<std::_Tmap_traits<ulong,STRING_ENTRY *,std::less<ulong>,std::allocator<std::pair<ulong const,STRING_ENTRY *>>,0>>(void)
0x180019d41  nop
0x180019d42  lea     rcx, [rbp+57h+var_60]
0x180019d46  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>(void)
0x180019d4b  lea     r11, [rsp+90h+var_s0]
0x180019d53  mov     rbx, [r11+10h]
0x180019d57  mov     rdi, [r11+18h]
0x180019d5b  mov     rsp, r11
0x180019d5e  pop     rbp
0x180019d5f  retn
```
