# D3DCoreModule::RemoveSingletonShadow(_LUID,IUnknown *)

- ea: `0x180002754`
- end: `0x1800027ca`
- name: `?RemoveSingletonShadow@D3DCoreModule@@QEAAXU_LUID@@PEAUIUnknown@@@Z`
- size: `118`
- prototype: `void __fastcall(D3DCoreModule *__hidden this, struct _LUID, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800026a0`

## callees

- `0x180002754`
- `0x180006e2c`
- `0x18001010c`

## pseudocode

```c
void __fastcall D3DCoreModule::RemoveSingletonShadow(D3DCoreModule *this, struct _LUID a2, struct IUnknown *a3)
{
  char *v3; // r11
  __int64 *v4; // r10
  __int64 *v5; // r9
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 *v8; // rax

  v3 = (char *)this + 176;
  v4 = (__int64 *)*((_QWORD *)this + 22);
  v5 = v4;
  v6 = (__int64 *)v4[1];
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      v8 = v6 + 2;
      if ( v6[4] >= *(unsigned __int64 *)&a2 )
      {
        v8 = v6;
        v5 = v6;
      }
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( !*((_BYTE *)v5 + 25) && v5 != v4 && *(unsigned __int64 *)&a2 >= v5[4] && (struct IUnknown *)v5[5] == a3 )
  {
    v7 = std::_Tree_val<std::_Tree_simple_types<std::pair<_LUID const,IUnknown *>>>::_Extract(v3, v5);
    std::_Deallocate<16>(v7, 48);
  }
}

```

## disassembly

```asm
0x180002754  sub     rsp, 48h
0x180002758  lea     r11, [rcx+0B0h]
0x18000275f  xor     eax, eax
0x180002761  mov     r10, [r11]
0x180002764  mov     [rsp+48h+var_1C], eax
0x180002768  mov     r9, r10
0x18000276b  mov     rcx, [r10+8]
0x18000276f  cmp     [rcx+19h], al
0x180002772  jz      short loc_1800027AF
0x180002774  cmp     byte ptr [r9+19h], 0
0x180002779  jz      short loc_1800027A8
0x18000277b  add     rsp, 48h
0x18000277f  retn
0x180002780  cmp     rdx, [r9+20h]
0x180002784  jb      short loc_18000277B
0x180002786  cmp     [r9+28h], r8
0x18000278a  jnz     short loc_18000277B
0x18000278c  mov     rdx, r9
0x18000278f  mov     rcx, r11
0x180002792  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_LUID@@PEAUIUnknown@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_LUID@@PEAUIUnknown@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_LUID@@PEAUIUnknown@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_LUID const,IUnknown *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_LUID const,IUnknown *>>>,std::_Iterator_base0>)
0x180002797  mov     edx, 30h ; '0'
0x18000279c  mov     rcx, rax
0x18000279f  add     rsp, 48h
0x1800027a3  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800027a8  cmp     r9, r10
0x1800027ab  jz      short loc_18000277B
0x1800027ad  jmp     short loc_180002780
0x1800027af  cmp     [rcx+20h], rdx
0x1800027b3  lea     rax, [rcx+10h]
0x1800027b7  cmovnb  rax, rcx
0x1800027bb  cmovnb  r9, rcx
0x1800027bf  mov     rcx, [rax]
0x1800027c2  cmp     byte ptr [rcx+19h], 0
0x1800027c6  jz      short loc_1800027AF
0x1800027c8  jmp     short loc_180002774
```
