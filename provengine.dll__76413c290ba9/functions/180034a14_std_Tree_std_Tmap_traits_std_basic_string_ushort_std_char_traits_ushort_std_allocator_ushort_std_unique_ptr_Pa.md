# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>>,0>>::_Insert_at<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>,void *> *>(bool,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>,void *> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>,void *> *)

- ea: `0x180034a14`
- end: `0x180034c8d`
- name: `??$_Insert_at@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@1@1@Z`
- size: `633`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, char, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035378`

## callees

- `0x180034a14`
- `0x180036758`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034a4b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034a4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_at<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(
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
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Destroy_if_not_nil(
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
0x180034a14  mov     [rsp+arg_0], rbx
0x180034a19  push    rdi
0x180034a1a  sub     rsp, 20h
0x180034a1e  mov     rax, [rcx+8]
0x180034a22  mov     r11, rcx
0x180034a25  mov     rcx, 38E38E38E38E38Dh
0x180034a2f  mov     r10, r9
0x180034a32  mov     rbx, rdx
0x180034a35  cmp     rax, rcx
0x180034a38  jb      short loc_180034A52
0x180034a3a  mov     rdx, [rsp+28h+arg_28]
0x180034a3f  call    ?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *)
0x180034a44  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180034a4b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180034a52  mov     r9, [rsp+28h+arg_28]
0x180034a57  inc     rax
0x180034a5a  mov     [r11+8], rax
0x180034a5e  xor     edi, edi
0x180034a60  mov     [r9+8], r10
0x180034a64  mov     rax, [r11]
0x180034a67  cmp     r10, rax
0x180034a6a  jnz     short loc_180034A7B
0x180034a6c  mov     [rax+8], r9
0x180034a70  mov     rax, [r11]
0x180034a73  mov     [rax], r9
0x180034a76  mov     rax, [r11]
0x180034a79  jmp     short loc_180034A9D
0x180034a7b  test    r8b, r8b
0x180034a7e  jz      short loc_180034A90
0x180034a80  mov     [r10], r9
0x180034a83  mov     rax, [r11]
0x180034a86  cmp     r10, [rax]
0x180034a89  jnz     short loc_180034AA1
0x180034a8b  mov     [rax], r9
0x180034a8e  jmp     short loc_180034AA1
0x180034a90  mov     [r10+10h], r9
0x180034a94  mov     rax, [r11]
0x180034a97  cmp     r10, [rax+10h]
0x180034a9b  jnz     short loc_180034AA1
0x180034a9d  mov     [rax+10h], r9
0x180034aa1  mov     rax, [r9+8]
0x180034aa5  mov     rdx, r9
0x180034aa8  jmp     loc_180034C67
0x180034aad  mov     rcx, [rdx+8]
0x180034ab1  mov     r8, [rcx+8]
0x180034ab5  mov     rax, [r8]
0x180034ab8  cmp     rcx, rax
0x180034abb  jnz     loc_180034B86
0x180034ac1  mov     rax, [r8+10h]
0x180034ac5  cmp     [rax+18h], dil
0x180034ac9  jz      loc_180034B8C
0x180034acf  mov     r8, [rcx+10h]
0x180034ad3  cmp     rdx, r8
0x180034ad6  jnz     short loc_180034B1F
0x180034ad8  mov     rax, [r8]
0x180034adb  mov     rdx, rcx
0x180034ade  mov     [rcx+10h], rax
0x180034ae2  mov     rax, [r8]
0x180034ae5  cmp     [rax+19h], dil
0x180034ae9  jnz     short loc_180034AEF
0x180034aeb  mov     [rax+8], rcx
0x180034aef  mov     rax, [rcx+8]
0x180034af3  mov     [r8+8], rax
0x180034af7  mov     rax, [r11]
0x180034afa  cmp     rcx, [rax+8]
0x180034afe  jnz     short loc_180034B06
0x180034b00  mov     [rax+8], r8
0x180034b04  jmp     short loc_180034B18
0x180034b06  mov     rax, [rcx+8]
0x180034b0a  cmp     rcx, [rax]
0x180034b0d  jnz     short loc_180034B14
0x180034b0f  mov     [rax], r8
0x180034b12  jmp     short loc_180034B18
0x180034b14  mov     [rax+10h], r8
0x180034b18  mov     [r8], rcx
0x180034b1b  mov     [rcx+8], r8
0x180034b1f  mov     rax, [rdx+8]
0x180034b23  mov     byte ptr [rax+18h], 1
0x180034b27  mov     rax, [rdx+8]
0x180034b2b  mov     rcx, [rax+8]
0x180034b2f  mov     [rcx+18h], dil
0x180034b33  mov     rax, [rdx+8]
0x180034b37  mov     rcx, [rax+8]
0x180034b3b  mov     r8, [rcx]
0x180034b3e  mov     rax, [r8+10h]
0x180034b42  mov     [rcx], rax
0x180034b45  mov     rax, [r8+10h]
0x180034b49  cmp     [rax+19h], dil
0x180034b4d  jnz     short loc_180034B53
0x180034b4f  mov     [rax+8], rcx
0x180034b53  mov     rax, [rcx+8]
0x180034b57  mov     [r8+8], rax
0x180034b5b  mov     rax, [r11]
0x180034b5e  cmp     rcx, [rax+8]
0x180034b62  jnz     short loc_180034B6A
0x180034b64  mov     [rax+8], r8
0x180034b68  jmp     short loc_180034B7D
0x180034b6a  mov     rax, [rcx+8]
0x180034b6e  cmp     rcx, [rax+10h]
0x180034b72  jnz     short loc_180034B7A
0x180034b74  mov     [rax+10h], r8
0x180034b78  jmp     short loc_180034B7D
0x180034b7a  mov     [rax], r8
0x180034b7d  mov     [r8+10h], rcx
0x180034b81  jmp     loc_180034C5F
0x180034b86  cmp     [rax+18h], dil
0x180034b8a  jnz     short loc_180034BAD
0x180034b8c  mov     byte ptr [rcx+18h], 1
0x180034b90  mov     byte ptr [rax+18h], 1
0x180034b94  mov     rax, [rdx+8]
0x180034b98  mov     rcx, [rax+8]
0x180034b9c  mov     [rcx+18h], dil
0x180034ba0  mov     rax, [rdx+8]
0x180034ba4  mov     rdx, [rax+8]
0x180034ba8  jmp     loc_180034C63
0x180034bad  mov     r8, [rcx]
0x180034bb0  cmp     rdx, r8
0x180034bb3  jnz     short loc_180034BFF
0x180034bb5  mov     rax, [r8+10h]
0x180034bb9  mov     rdx, rcx
0x180034bbc  mov     [rcx], rax
0x180034bbf  mov     rax, [r8+10h]
0x180034bc3  cmp     [rax+19h], dil
0x180034bc7  jnz     short loc_180034BCD
0x180034bc9  mov     [rax+8], rcx
0x180034bcd  mov     rax, [rcx+8]
0x180034bd1  mov     [r8+8], rax
0x180034bd5  mov     rax, [r11]
0x180034bd8  cmp     rcx, [rax+8]
0x180034bdc  jnz     short loc_180034BE4
0x180034bde  mov     [rax+8], r8
0x180034be2  jmp     short loc_180034BF7
0x180034be4  mov     rax, [rcx+8]
0x180034be8  cmp     rcx, [rax+10h]
0x180034bec  jnz     short loc_180034BF4
0x180034bee  mov     [rax+10h], r8
0x180034bf2  jmp     short loc_180034BF7
0x180034bf4  mov     [rax], r8
0x180034bf7  mov     [r8+10h], rcx
0x180034bfb  mov     [rcx+8], r8
0x180034bff  mov     rax, [rdx+8]
0x180034c03  mov     byte ptr [rax+18h], 1
0x180034c07  mov     rax, [rdx+8]
0x180034c0b  mov     rcx, [rax+8]
0x180034c0f  mov     [rcx+18h], dil
0x180034c13  mov     rax, [rdx+8]
0x180034c17  mov     rcx, [rax+8]
0x180034c1b  mov     r8, [rcx+10h]
0x180034c1f  mov     rax, [r8]
0x180034c22  mov     [rcx+10h], rax
0x180034c26  mov     rax, [r8]
0x180034c29  cmp     [rax+19h], dil
0x180034c2d  jnz     short loc_180034C33
0x180034c2f  mov     [rax+8], rcx
0x180034c33  mov     rax, [rcx+8]
0x180034c37  mov     [r8+8], rax
0x180034c3b  mov     rax, [r11]
0x180034c3e  cmp     rcx, [rax+8]
0x180034c42  jnz     short loc_180034C4A
0x180034c44  mov     [rax+8], r8
0x180034c48  jmp     short loc_180034C5C
0x180034c4a  mov     rax, [rcx+8]
0x180034c4e  cmp     rcx, [rax]
0x180034c51  jnz     short loc_180034C58
0x180034c53  mov     [rax], r8
0x180034c56  jmp     short loc_180034C5C
0x180034c58  mov     [rax+10h], r8
0x180034c5c  mov     [r8], rcx
0x180034c5f  mov     [rcx+8], r8
0x180034c63  mov     rax, [rdx+8]
0x180034c67  cmp     [rax+18h], dil
0x180034c6b  jz      loc_180034AAD
0x180034c71  mov     rax, [r11]
0x180034c74  mov     [rbx], r9
0x180034c77  mov     rcx, [rax+8]
0x180034c7b  mov     rax, rbx
0x180034c7e  mov     rbx, [rsp+28h+arg_0]
0x180034c83  mov     byte ptr [rcx+18h], 1
0x180034c87  add     rsp, 20h
0x180034c8b  pop     rdi
0x180034c8c  retn
```
