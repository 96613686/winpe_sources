# std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](HardwareAddress const &)

- ea: `0x180018540`
- end: `0x1800186fc`
- name: `??A?$unordered_map@VHardwareAddress@@VVisibleDock@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@4@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@@tr1@std@@QEAAAEAVVisibleDock@@AEBVHardwareAddress@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018790`
- `0x18001884c`
- `0x1800195cc`

## callees

- `0x180001588`
- `0x18000c308`
- `0x180017fe0`
- `0x18001821c`
- `0x1800184f8`
- `0x180018540`
- `0x180019be0`
- `0x18001a18c`
- `0x18001ca3e`
- `0x18001ca70`

## pseudocode

```c
__int64 __fastcall std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](
        __int64 a1,
        _BYTE *a2)
{
  __int64 v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  _QWORD v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v13; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v14; // [rsp+39h] [rbp-C7h]
  unsigned __int8 v15; // [rsp+3Ah] [rbp-C6h]
  unsigned __int8 v16; // [rsp+3Bh] [rbp-C5h]
  unsigned __int8 v17; // [rsp+3Ch] [rbp-C4h]
  unsigned __int8 v18; // [rsp+3Dh] [rbp-C3h]
  _BYTE v19[1168]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[8]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v21[1160]; // [rsp+4D8h] [rbp+3D8h] BYREF

  std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(
    a1,
    v11,
    a2);
  v4 = v11[0];
  if ( v11[0] == *(_QWORD *)(a1 + 8) )
  {
    v20[0] = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids, v20);
    }
    memset_0(v21, 0, 0x480u);
    v13 = a2[8];
    v14 = a2[9];
    v15 = a2[10];
    v16 = a2[11];
    v17 = a2[12];
    v18 = a2[13];
    v12 = v18 | ((v17 | ((v16 | ((v15 | ((v14 | ((unsigned __int64)v13 << 8)) << 8)) << 8)) << 8)) << 8);
    VisibleDock::VisibleDock((VisibleDock *)v19, (const struct VisibleDock *)v20);
    v5 = *(_QWORD **)(a1 + 8);
    v6 = *v5;
    v8 = std::_List_val<std::pair<HardwareAddress const,VisibleDock>>::_Buynode<std::pair<HardwareAddress const,VisibleDock>>(
           v7,
           *v5,
           *(_QWORD *)(*v5 + 8LL),
           &v12);
    v9 = *(_QWORD *)(a1 + 16);
    if ( v9 == 0x37BA5713280DEDLL )
      std::_Xlength_error("list<T> too long");
    *(_QWORD *)(a1 + 16) = v9 + 1;
    *(_QWORD *)(v6 + 8) = v8;
    **(_QWORD **)(v8 + 8) = v8;
    std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(
      a1,
      v11,
      **(_QWORD **)(a1 + 8) + 16LL);
    v4 = v11[0];
    VisibleDock::~VisibleDock((VisibleDock *)v19);
    VisibleDock::~VisibleDock((VisibleDock *)v20);
  }
  return v4 + 32;
}

```

## disassembly

```asm
0x180018540  mov     [rsp-8+arg_10], rbx
0x180018545  push    rbp
0x180018546  push    rsi
0x180018547  push    rdi
0x180018548  lea     rbp, [rsp-870h]
0x180018550  sub     rsp, 970h
0x180018557  mov     rax, cs:__security_cookie
0x18001855e  xor     rax, rsp
0x180018561  mov     [rbp+880h+var_20], rax
0x180018568  mov     rsi, rdx
0x18001856b  mov     rdi, rcx
0x18001856e  mov     r8, rdx
0x180018571  lea     rdx, [rsp+980h+var_960]
0x180018576  call    ?lower_bound@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@AEBVHardwareAddress@@@Z; std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(HardwareAddress const &)
0x18001857b  mov     rbx, [rsp+980h+var_960]
0x180018580  cmp     rbx, [rdi+8]
0x180018584  jnz     loc_1800186C9
0x18001858a  mov     [rbp+880h+var_4B0], 0
0x180018591  lea     rax, WPP_GLOBAL_Control
0x180018598  mov     rcx, cs:WPP_GLOBAL_Control
0x18001859f  cmp     rcx, rax
0x1800185a2  jz      short loc_1800185CC
0x1800185a4  cmp     byte ptr [rcx+19h], 4
0x1800185a8  jb      short loc_1800185CC
0x1800185aa  test    byte ptr [rcx+1Ch], 1
0x1800185ae  jz      short loc_1800185CC
0x1800185b0  mov     edx, 0Ah
0x1800185b5  lea     r9, [rbp+880h+var_4B0]
0x1800185bc  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x1800185c3  mov     rcx, [rcx+10h]
0x1800185c7  call    WPP_SF_q
0x1800185cc  xor     edx, edx; Val
0x1800185ce  mov     r8d, 480h; Size
0x1800185d4  lea     rcx, [rbp+880h+var_4A8]; void *
0x1800185db  call    memset_0
0x1800185e0  nop
0x1800185e1  movzx   r10d, byte ptr [rsi+8]
0x1800185e6  mov     [rsp+980h+var_948], r10b
0x1800185eb  movzx   eax, byte ptr [rsi+9]
0x1800185ef  mov     [rsp+980h+var_947], al
0x1800185f3  movzx   ecx, byte ptr [rsi+0Ah]
0x1800185f7  mov     [rsp+980h+var_946], cl
0x1800185fb  movzx   edx, byte ptr [rsi+0Bh]
0x1800185ff  mov     [rsp+980h+var_945], dl
0x180018603  movzx   r8d, byte ptr [rsi+0Ch]
0x180018608  mov     [rsp+980h+var_944], r8b
0x18001860d  movzx   r9d, byte ptr [rsi+0Dh]
0x180018612  mov     [rsp+980h+var_943], r9b
0x180018617  shl     r10, 8
0x18001861b  or      r10, rax
0x18001861e  shl     r10, 8
0x180018622  or      r10, rcx
0x180018625  shl     r10, 8
0x180018629  or      r10, rdx
0x18001862c  shl     r10, 8
0x180018630  or      r10, r8
0x180018633  shl     r10, 8
0x180018637  or      r10, r9
0x18001863a  mov     [rsp+980h+var_950], r10
0x18001863f  lea     rdx, [rbp+880h+var_4B0]; struct VisibleDock *
0x180018646  lea     rcx, [rsp+980h+var_940]; this
0x18001864b  call    ??0VisibleDock@@QEAA@AEBV0@@Z; VisibleDock::VisibleDock(VisibleDock const &)
0x180018650  nop
0x180018651  mov     rax, [rdi+8]
0x180018655  mov     rbx, [rax]
0x180018658  lea     r9, [rsp+980h+var_950]
0x18001865d  mov     r8, [rbx+8]
0x180018661  mov     rdx, rbx
0x180018664  call    ??$_Buynode@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@QEAAPEAU_Node@?$_List_nod@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@1@PEAU231@0$$QEAU?$pair@$$CBVHardwareAddress@@VVisibleDock@@@1@@Z; std::_List_val<std::pair<HardwareAddress const,VisibleDock>>::_Buynode<std::pair<HardwareAddress const,VisibleDock>>(std::_List_nod<std::pair<HardwareAddress const,VisibleDock>>::_Node *,std::_List_nod<std::pair<HardwareAddress const,VisibleDock>>::_Node *,std::pair<HardwareAddress const,VisibleDock> &&)
0x180018669  mov     rdx, rax
0x18001866c  mov     rax, [rdi+10h]
0x180018670  mov     rcx, 37BA5713280DEDh
0x18001867a  sub     rcx, rax
0x18001867d  cmp     rcx, 1
0x180018681  jb      short loc_1800186EF
0x180018683  inc     rax
0x180018686  mov     [rdi+10h], rax
0x18001868a  mov     [rbx+8], rdx
0x18001868e  mov     rax, [rdx+8]
0x180018692  mov     [rax], rdx
0x180018695  mov     r9, [rdi+8]
0x180018699  mov     r9, [r9]
0x18001869c  lea     r8, [r9+10h]
0x1800186a0  lea     rdx, [rsp+980h+var_960]
0x1800186a5  mov     rcx, rdi
0x1800186a8  call    ?_Insert@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_N@2@AEBU?$pair@$$CBVHardwareAddress@@VVisibleDock@@@2@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(std::pair<HardwareAddress const,VisibleDock> const &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>)
0x1800186ad  mov     rbx, [rsp+980h+var_960]
0x1800186b2  lea     rcx, [rsp+980h+var_940]; this
0x1800186b7  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x1800186bc  nop
0x1800186bd  lea     rcx, [rbp+880h+var_4B0]; this
0x1800186c4  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x1800186c9  lea     rax, [rbx+20h]
0x1800186cd  mov     rcx, [rbp+880h+var_20]
0x1800186d4  xor     rcx, rsp; StackCookie
0x1800186d7  call    __security_check_cookie
0x1800186dc  mov     rbx, [rsp+980h+arg_10]
0x1800186e4  add     rsp, 970h
0x1800186eb  pop     rdi
0x1800186ec  pop     rsi
0x1800186ed  pop     rbp
0x1800186ee  retn
0x1800186ef  lea     rcx, aListTTooLong; "list<T> too long"
0x1800186f6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
