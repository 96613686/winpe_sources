# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> *>,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> * const)

- ea: `0x1800137c8`
- end: `0x1800139f1`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001129c`

## callees

- `0x1800137c8`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x1800137c8  mov     [rsp+arg_0], rbx
0x1800137cd  inc     qword ptr [rcx+8]
0x1800137d1  mov     r11, rcx
0x1800137d4  mov     r10, [rcx]
0x1800137d7  mov     rax, [rdx]
0x1800137da  mov     [r8+8], rax
0x1800137de  cmp     rax, r10
0x1800137e1  jnz     short loc_1800137F8
0x1800137e3  mov     [r10], r8
0x1800137e6  mov     [r10+8], r8
0x1800137ea  mov     [r10+10h], r8
0x1800137ee  mov     byte ptr [r8+18h], 1
0x1800137f3  jmp     loc_1800139E8
0x1800137f8  xor     ebx, ebx
0x1800137fa  cmp     [rdx+8], ebx
0x1800137fd  jnz     short loc_18001380F
0x1800137ff  mov     [rax+10h], r8
0x180013803  cmp     rax, [r10+10h]
0x180013807  jnz     short loc_18001381A
0x180013809  mov     [r10+10h], r8
0x18001380d  jmp     short loc_18001381A
0x18001380f  mov     [rax], r8
0x180013812  cmp     rax, [r10]
0x180013815  jnz     short loc_18001381A
0x180013817  mov     [r10], r8
0x18001381a  mov     rax, [r8+8]
0x18001381e  mov     rdx, r8
0x180013821  jmp     loc_1800139D7
0x180013826  mov     rcx, [rdx+8]
0x18001382a  mov     r9, [rcx+8]
0x18001382e  mov     rax, [r9]
0x180013831  cmp     rcx, rax
0x180013834  jnz     loc_1800138FB
0x18001383a  mov     rax, [r9+10h]
0x18001383e  cmp     [rax+18h], bl
0x180013841  jz      loc_180013900
0x180013847  mov     r9, [rcx+10h]
0x18001384b  cmp     rdx, r9
0x18001384e  jnz     short loc_180013896
0x180013850  mov     rax, [r9]
0x180013853  mov     rdx, rcx
0x180013856  mov     [rcx+10h], rax
0x18001385a  mov     rax, [r9]
0x18001385d  cmp     [rax+19h], bl
0x180013860  jnz     short loc_180013866
0x180013862  mov     [rax+8], rcx
0x180013866  mov     rax, [rcx+8]
0x18001386a  mov     [r9+8], rax
0x18001386e  mov     rax, [r11]
0x180013871  cmp     rcx, [rax+8]
0x180013875  jnz     short loc_18001387D
0x180013877  mov     [rax+8], r9
0x18001387b  jmp     short loc_18001388F
0x18001387d  mov     rax, [rcx+8]
0x180013881  cmp     rcx, [rax]
0x180013884  jnz     short loc_18001388B
0x180013886  mov     [rax], r9
0x180013889  jmp     short loc_18001388F
0x18001388b  mov     [rax+10h], r9
0x18001388f  mov     [r9], rcx
0x180013892  mov     [rcx+8], r9
0x180013896  mov     rax, [rdx+8]
0x18001389a  mov     byte ptr [rax+18h], 1
0x18001389e  mov     rax, [rdx+8]
0x1800138a2  mov     rcx, [rax+8]
0x1800138a6  mov     [rcx+18h], bl
0x1800138a9  mov     rax, [rdx+8]
0x1800138ad  mov     rcx, [rax+8]
0x1800138b1  mov     r9, [rcx]
0x1800138b4  mov     rax, [r9+10h]
0x1800138b8  mov     [rcx], rax
0x1800138bb  mov     rax, [r9+10h]
0x1800138bf  cmp     [rax+19h], bl
0x1800138c2  jnz     short loc_1800138C8
0x1800138c4  mov     [rax+8], rcx
0x1800138c8  mov     rax, [rcx+8]
0x1800138cc  mov     [r9+8], rax
0x1800138d0  mov     rax, [r11]
0x1800138d3  cmp     rcx, [rax+8]
0x1800138d7  jnz     short loc_1800138DF
0x1800138d9  mov     [rax+8], r9
0x1800138dd  jmp     short loc_1800138F2
0x1800138df  mov     rax, [rcx+8]
0x1800138e3  cmp     rcx, [rax+10h]
0x1800138e7  jnz     short loc_1800138EF
0x1800138e9  mov     [rax+10h], r9
0x1800138ed  jmp     short loc_1800138F2
0x1800138ef  mov     [rax], r9
0x1800138f2  mov     [r9+10h], rcx
0x1800138f6  jmp     loc_1800139CF
0x1800138fb  cmp     [rax+18h], bl
0x1800138fe  jnz     short loc_180013920
0x180013900  mov     byte ptr [rcx+18h], 1
0x180013904  mov     byte ptr [rax+18h], 1
0x180013908  mov     rax, [rdx+8]
0x18001390c  mov     rcx, [rax+8]
0x180013910  mov     [rcx+18h], bl
0x180013913  mov     rax, [rdx+8]
0x180013917  mov     rdx, [rax+8]
0x18001391b  jmp     loc_1800139D3
0x180013920  mov     r9, [rcx]
0x180013923  cmp     rdx, r9
0x180013926  jnz     short loc_180013971
0x180013928  mov     rax, [r9+10h]
0x18001392c  mov     rdx, rcx
0x18001392f  mov     [rcx], rax
0x180013932  mov     rax, [r9+10h]
0x180013936  cmp     [rax+19h], bl
0x180013939  jnz     short loc_18001393F
0x18001393b  mov     [rax+8], rcx
0x18001393f  mov     rax, [rcx+8]
0x180013943  mov     [r9+8], rax
0x180013947  mov     rax, [r11]
0x18001394a  cmp     rcx, [rax+8]
0x18001394e  jnz     short loc_180013956
0x180013950  mov     [rax+8], r9
0x180013954  jmp     short loc_180013969
0x180013956  mov     rax, [rcx+8]
0x18001395a  cmp     rcx, [rax+10h]
0x18001395e  jnz     short loc_180013966
0x180013960  mov     [rax+10h], r9
0x180013964  jmp     short loc_180013969
0x180013966  mov     [rax], r9
0x180013969  mov     [r9+10h], rcx
0x18001396d  mov     [rcx+8], r9
0x180013971  mov     rax, [rdx+8]
0x180013975  mov     byte ptr [rax+18h], 1
0x180013979  mov     rax, [rdx+8]
0x18001397d  mov     rcx, [rax+8]
0x180013981  mov     [rcx+18h], bl
0x180013984  mov     rax, [rdx+8]
0x180013988  mov     rcx, [rax+8]
0x18001398c  mov     r9, [rcx+10h]
0x180013990  mov     rax, [r9]
0x180013993  mov     [rcx+10h], rax
0x180013997  mov     rax, [r9]
0x18001399a  cmp     [rax+19h], bl
0x18001399d  jnz     short loc_1800139A3
0x18001399f  mov     [rax+8], rcx
0x1800139a3  mov     rax, [rcx+8]
0x1800139a7  mov     [r9+8], rax
0x1800139ab  mov     rax, [r11]
0x1800139ae  cmp     rcx, [rax+8]
0x1800139b2  jnz     short loc_1800139BA
0x1800139b4  mov     [rax+8], r9
0x1800139b8  jmp     short loc_1800139CC
0x1800139ba  mov     rax, [rcx+8]
0x1800139be  cmp     rcx, [rax]
0x1800139c1  jnz     short loc_1800139C8
0x1800139c3  mov     [rax], r9
0x1800139c6  jmp     short loc_1800139CC
0x1800139c8  mov     [rax+10h], r9
0x1800139cc  mov     [r9], rcx
0x1800139cf  mov     [rcx+8], r9
0x1800139d3  mov     rax, [rdx+8]
0x1800139d7  cmp     [rax+18h], bl
0x1800139da  jz      loc_180013826
0x1800139e0  mov     rax, [r10+8]
0x1800139e4  mov     byte ptr [rax+18h], 1
0x1800139e8  mov     rbx, [rsp+arg_0]
0x1800139ed  mov     rax, r8
0x1800139f0  retn
```
