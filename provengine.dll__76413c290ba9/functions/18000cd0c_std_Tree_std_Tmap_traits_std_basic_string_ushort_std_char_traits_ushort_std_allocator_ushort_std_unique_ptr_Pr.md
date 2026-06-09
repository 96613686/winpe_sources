# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>,0>>::_Insert_at<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>,void *> *>(bool,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>,void *> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>,void *> *)

- ea: `0x18000cd0c`
- end: `0x18000cf85`
- name: `??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@1@1@Z`
- size: `633`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dbac`
- `0x18000e5dc`

## callees

- `0x18000cd0c`
- `0x180020fe8`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000cd43`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000cd43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<ProvResults>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *>(
        _QWORD *a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  unsigned __int64 v6; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // r8
  __int64 **v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  if ( v6 >= 0x38E38E38E38E38DLL )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Destroy_if_not_nil(
      0x38E38E38E38E38DLL,
      a6);
    std::_Xlength_error("map/set<T> too long");
  }
  a1[1] = v6 + 1;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = a6;
    *(_QWORD *)*a1 = a6;
    v9 = *a1;
LABEL_9:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_10;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_10;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_9;
LABEL_10:
  v10 = *(_QWORD *)(a6 + 8);
  v11 = a6;
  while ( !*(_BYTE *)(v10 + 24) )
  {
    v12 = *(__int64 **)(v11 + 8);
    v13 = (__int64 *)v12[1];
    v14 = (__int64 *)*v13;
    if ( v12 == (__int64 *)*v13 )
    {
      v14 = (__int64 *)v13[2];
      if ( !*((_BYTE *)v14 + 24) )
        goto LABEL_31;
      v15 = (__int64 *)v12[2];
      if ( (__int64 *)v11 == v15 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        v12[2] = *v15;
        if ( !*(_BYTE *)(*v15 + 25) )
          *(_QWORD *)(*v15 + 8) = v12;
        v15[1] = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v15;
        }
        else
        {
          v16 = (__int64 **)v12[1];
          if ( v12 == *v16 )
            *v16 = v15;
          else
            v16[2] = v15;
        }
        *v15 = (__int64)v12;
        v12[1] = (__int64)v15;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      v18[2] = v17;
    }
    else
    {
      if ( !*((_BYTE *)v14 + 24) )
      {
LABEL_31:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_50;
      }
      v21 = *v12;
      if ( v11 == *v12 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        *v12 = *(_QWORD *)(v21 + 16);
        v22 = *(_QWORD *)(v21 + 16);
        if ( !*(_BYTE *)(v22 + 25) )
          *(_QWORD *)(v22 + 8) = v12;
        *(_QWORD *)(v21 + 8) = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v21;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (__int64 *)v23[2] )
            v23[2] = v21;
          else
            *v23 = v21;
        }
        *(_QWORD *)(v21 + 16) = v12;
        v12[1] = v21;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)v17[2];
      v17[2] = *v18;
      if ( !*(_BYTE *)(*v18 + 25LL) )
        *(_QWORD *)(*v18 + 8LL) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v24 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)*v24 )
          *v24 = v18;
        else
          v24[2] = v18;
      }
      *v18 = v17;
    }
    v17[1] = v18;
LABEL_50:
    v10 = *(_QWORD *)(v11 + 8);
  }
  v25 = *a1;
  *a2 = a6;
  v26 = *(_QWORD *)(v25 + 8);
  result = a2;
  *(_BYTE *)(v26 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18000cd0c  mov     [rsp+arg_0], rbx
0x18000cd11  push    rdi
0x18000cd12  sub     rsp, 20h
0x18000cd16  mov     rax, [rcx+8]
0x18000cd1a  mov     r11, rcx
0x18000cd1d  mov     rcx, 38E38E38E38E38Dh
0x18000cd27  mov     r10, r9
0x18000cd2a  mov     rbx, rdx
0x18000cd2d  cmp     rax, rcx
0x18000cd30  jb      short loc_18000CD4A
0x18000cd32  mov     rdx, [rsp+28h+arg_28]
0x18000cd37  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *)
0x18000cd3c  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x18000cd43  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000cd4a  mov     r9, [rsp+28h+arg_28]
0x18000cd4f  inc     rax
0x18000cd52  mov     [r11+8], rax
0x18000cd56  xor     edi, edi
0x18000cd58  mov     [r9+8], r10
0x18000cd5c  mov     rax, [r11]
0x18000cd5f  cmp     r10, rax
0x18000cd62  jnz     short loc_18000CD73
0x18000cd64  mov     [rax+8], r9
0x18000cd68  mov     rax, [r11]
0x18000cd6b  mov     [rax], r9
0x18000cd6e  mov     rax, [r11]
0x18000cd71  jmp     short loc_18000CD95
0x18000cd73  test    r8b, r8b
0x18000cd76  jz      short loc_18000CD88
0x18000cd78  mov     [r10], r9
0x18000cd7b  mov     rax, [r11]
0x18000cd7e  cmp     r10, [rax]
0x18000cd81  jnz     short loc_18000CD99
0x18000cd83  mov     [rax], r9
0x18000cd86  jmp     short loc_18000CD99
0x18000cd88  mov     [r10+10h], r9
0x18000cd8c  mov     rax, [r11]
0x18000cd8f  cmp     r10, [rax+10h]
0x18000cd93  jnz     short loc_18000CD99
0x18000cd95  mov     [rax+10h], r9
0x18000cd99  mov     rax, [r9+8]
0x18000cd9d  mov     rdx, r9
0x18000cda0  jmp     loc_18000CF5F
0x18000cda5  mov     rcx, [rdx+8]
0x18000cda9  mov     r8, [rcx+8]
0x18000cdad  mov     rax, [r8]
0x18000cdb0  cmp     rcx, rax
0x18000cdb3  jnz     loc_18000CE7E
0x18000cdb9  mov     rax, [r8+10h]
0x18000cdbd  cmp     [rax+18h], dil
0x18000cdc1  jz      loc_18000CE84
0x18000cdc7  mov     r8, [rcx+10h]
0x18000cdcb  cmp     rdx, r8
0x18000cdce  jnz     short loc_18000CE17
0x18000cdd0  mov     rax, [r8]
0x18000cdd3  mov     rdx, rcx
0x18000cdd6  mov     [rcx+10h], rax
0x18000cdda  mov     rax, [r8]
0x18000cddd  cmp     [rax+19h], dil
0x18000cde1  jnz     short loc_18000CDE7
0x18000cde3  mov     [rax+8], rcx
0x18000cde7  mov     rax, [rcx+8]
0x18000cdeb  mov     [r8+8], rax
0x18000cdef  mov     rax, [r11]
0x18000cdf2  cmp     rcx, [rax+8]
0x18000cdf6  jnz     short loc_18000CDFE
0x18000cdf8  mov     [rax+8], r8
0x18000cdfc  jmp     short loc_18000CE10
0x18000cdfe  mov     rax, [rcx+8]
0x18000ce02  cmp     rcx, [rax]
0x18000ce05  jnz     short loc_18000CE0C
0x18000ce07  mov     [rax], r8
0x18000ce0a  jmp     short loc_18000CE10
0x18000ce0c  mov     [rax+10h], r8
0x18000ce10  mov     [r8], rcx
0x18000ce13  mov     [rcx+8], r8
0x18000ce17  mov     rax, [rdx+8]
0x18000ce1b  mov     byte ptr [rax+18h], 1
0x18000ce1f  mov     rax, [rdx+8]
0x18000ce23  mov     rcx, [rax+8]
0x18000ce27  mov     [rcx+18h], dil
0x18000ce2b  mov     rax, [rdx+8]
0x18000ce2f  mov     rcx, [rax+8]
0x18000ce33  mov     r8, [rcx]
0x18000ce36  mov     rax, [r8+10h]
0x18000ce3a  mov     [rcx], rax
0x18000ce3d  mov     rax, [r8+10h]
0x18000ce41  cmp     [rax+19h], dil
0x18000ce45  jnz     short loc_18000CE4B
0x18000ce47  mov     [rax+8], rcx
0x18000ce4b  mov     rax, [rcx+8]
0x18000ce4f  mov     [r8+8], rax
0x18000ce53  mov     rax, [r11]
0x18000ce56  cmp     rcx, [rax+8]
0x18000ce5a  jnz     short loc_18000CE62
0x18000ce5c  mov     [rax+8], r8
0x18000ce60  jmp     short loc_18000CE75
0x18000ce62  mov     rax, [rcx+8]
0x18000ce66  cmp     rcx, [rax+10h]
0x18000ce6a  jnz     short loc_18000CE72
0x18000ce6c  mov     [rax+10h], r8
0x18000ce70  jmp     short loc_18000CE75
0x18000ce72  mov     [rax], r8
0x18000ce75  mov     [r8+10h], rcx
0x18000ce79  jmp     loc_18000CF57
0x18000ce7e  cmp     [rax+18h], dil
0x18000ce82  jnz     short loc_18000CEA5
0x18000ce84  mov     byte ptr [rcx+18h], 1
0x18000ce88  mov     byte ptr [rax+18h], 1
0x18000ce8c  mov     rax, [rdx+8]
0x18000ce90  mov     rcx, [rax+8]
0x18000ce94  mov     [rcx+18h], dil
0x18000ce98  mov     rax, [rdx+8]
0x18000ce9c  mov     rdx, [rax+8]
0x18000cea0  jmp     loc_18000CF5B
0x18000cea5  mov     r8, [rcx]
0x18000cea8  cmp     rdx, r8
0x18000ceab  jnz     short loc_18000CEF7
0x18000cead  mov     rax, [r8+10h]
0x18000ceb1  mov     rdx, rcx
0x18000ceb4  mov     [rcx], rax
0x18000ceb7  mov     rax, [r8+10h]
0x18000cebb  cmp     [rax+19h], dil
0x18000cebf  jnz     short loc_18000CEC5
0x18000cec1  mov     [rax+8], rcx
0x18000cec5  mov     rax, [rcx+8]
0x18000cec9  mov     [r8+8], rax
0x18000cecd  mov     rax, [r11]
0x18000ced0  cmp     rcx, [rax+8]
0x18000ced4  jnz     short loc_18000CEDC
0x18000ced6  mov     [rax+8], r8
0x18000ceda  jmp     short loc_18000CEEF
0x18000cedc  mov     rax, [rcx+8]
0x18000cee0  cmp     rcx, [rax+10h]
0x18000cee4  jnz     short loc_18000CEEC
0x18000cee6  mov     [rax+10h], r8
0x18000ceea  jmp     short loc_18000CEEF
0x18000ceec  mov     [rax], r8
0x18000ceef  mov     [r8+10h], rcx
0x18000cef3  mov     [rcx+8], r8
0x18000cef7  mov     rax, [rdx+8]
0x18000cefb  mov     byte ptr [rax+18h], 1
0x18000ceff  mov     rax, [rdx+8]
0x18000cf03  mov     rcx, [rax+8]
0x18000cf07  mov     [rcx+18h], dil
0x18000cf0b  mov     rax, [rdx+8]
0x18000cf0f  mov     rcx, [rax+8]
0x18000cf13  mov     r8, [rcx+10h]
0x18000cf17  mov     rax, [r8]
0x18000cf1a  mov     [rcx+10h], rax
0x18000cf1e  mov     rax, [r8]
0x18000cf21  cmp     [rax+19h], dil
0x18000cf25  jnz     short loc_18000CF2B
0x18000cf27  mov     [rax+8], rcx
0x18000cf2b  mov     rax, [rcx+8]
0x18000cf2f  mov     [r8+8], rax
0x18000cf33  mov     rax, [r11]
0x18000cf36  cmp     rcx, [rax+8]
0x18000cf3a  jnz     short loc_18000CF42
0x18000cf3c  mov     [rax+8], r8
0x18000cf40  jmp     short loc_18000CF54
0x18000cf42  mov     rax, [rcx+8]
0x18000cf46  cmp     rcx, [rax]
0x18000cf49  jnz     short loc_18000CF50
0x18000cf4b  mov     [rax], r8
0x18000cf4e  jmp     short loc_18000CF54
0x18000cf50  mov     [rax+10h], r8
0x18000cf54  mov     [r8], rcx
0x18000cf57  mov     [rcx+8], r8
0x18000cf5b  mov     rax, [rdx+8]
0x18000cf5f  cmp     [rax+18h], dil
0x18000cf63  jz      loc_18000CDA5
0x18000cf69  mov     rax, [r11]
0x18000cf6c  mov     [rbx], r9
0x18000cf6f  mov     rcx, [rax+8]
0x18000cf73  mov     rax, rbx
0x18000cf76  mov     rbx, [rsp+28h+arg_0]
0x18000cf7b  mov     byte ptr [rcx+18h], 1
0x18000cf7f  add     rsp, 20h
0x18000cf83  pop     rdi
0x18000cf84  retn
```
