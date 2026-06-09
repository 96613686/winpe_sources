# CSNOCplCore::DoAddOrDeleteConnectionDUI(std::list<tagNETCON_PROPERTIES *,std::allocator<tagNETCON_PROPERTIES *>> *,_GUID const &,int,int *)

- ea: `0x180009c1c`
- end: `0x18000a007`
- name: `?DoAddOrDeleteConnectionDUI@CSNOCplCore@@AEAAJPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@AEBU_GUID@@HPEAH@Z`
- size: `1003`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b6cc`
- `0x18000b7d4`
- `0x18000b8bc`

## callees

- `0x1800075a8`
- `0x180007618`
- `0x180007ffc`
- `0x180008b7c`
- `0x18000981c`
- `0x180009c1c`
- `0x18000a2e0`
- `0x180013df4`
- `0x180014274`
- `0x1800142b4`
- `0x18001e670`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009e16`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009e16`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180009cbc`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180009cbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSNOCplCore::DoAddOrDeleteConnectionDUI(
        CSNOCplCore *a1,
        struct _GUID *a2,
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  int v9; // esi
  struct _GUID *v10; // r13
  int v11; // r15d
  struct _GUID *v12; // r8
  int v13; // r12d
  struct _GUID *v14; // r9
  _QWORD *v15; // rbx
  PVOID *v16; // rcx
  _QWORD **v17; // rdx
  struct tagNETCON_PROPERTIES *v18; // r15
  _QWORD **v19; // r9
  _QWORD *i; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  struct _GUID *v25; // [rsp+20h] [rbp-B8h]
  int v26; // [rsp+28h] [rbp-B0h]
  struct _GUID *v27; // [rsp+30h] [rbp-A8h]
  struct _GUID *v28; // [rsp+38h] [rbp-A0h]
  struct tagNETCON_PROPERTIES *pv; // [rsp+40h] [rbp-98h] BYREF
  int v30; // [rsp+48h] [rbp-90h]
  _QWORD *v31; // [rsp+50h] [rbp-88h]
  struct _GUID *v32; // [rsp+58h] [rbp-80h]
  struct _GUID *v33; // [rsp+60h] [rbp-78h]
  __int64 v34; // [rsp+68h] [rbp-70h]
  struct _GUID *v35; // [rsp+70h] [rbp-68h]
  struct _GUID *v36; // [rsp+78h] [rbp-60h]
  struct _GUID *v37; // [rsp+80h] [rbp-58h]
  struct _GUID *v38; // [rsp+88h] [rbp-50h] BYREF
  __int64 v39; // [rsp+90h] [rbp-48h]
  DirectUI::Element *v40; // [rsp+98h] [rbp-40h] BYREF
  unsigned int v41[14]; // [rsp+A0h] [rbp-38h] BYREF

  if ( a5 )
    *a5 = 0;
  std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(
    *((_QWORD *)a1 + 19),
    &pv,
    a3);
  if ( pv == **((struct tagNETCON_PROPERTIES ***)a1 + 19) )
    return 1;
  v9 = 0;
  v26 = 0;
  v10 = *(struct _GUID **)&pv->clsidThisObject.Data2;
  v35 = v10;
  if ( v10 )
  {
    v11 = 0;
    v40 = (DirectUI::Element *)*((_QWORD *)a1 + 40);
    v41[0] = 0;
    DirectUI::Element::StartDefer(v40, v41);
    v28 = v10 + 5;
    if ( a4 )
    {
      v12 = v10 + 5;
      v25 = v10 + 5;
    }
    else
    {
      v12 = a2;
      v25 = a2;
      a2 = v10 + 5;
    }
    if ( *(_QWORD *)a2->Data4 )
    {
      v36 = v10 + 5;
      v33 = v10 + 5;
      v13 = 0;
      v37 = v10;
      v14 = v12;
      v27 = v12;
      v15 = *(_QWORD **)&a2->Data1;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      while ( 1 )
      {
        do
        {
          v15 = (_QWORD *)*v15;
          v31 = v15;
          v17 = *(_QWORD ***)&a2->Data1;
          if ( v15 == *(_QWORD **)&a2->Data1 )
          {
            v11 = 0;
            goto LABEL_13;
          }
          if ( v13 )
          {
            v15 = *v17;
            v31 = *v17;
          }
          v13 = 0;
          v18 = (struct tagNETCON_PROPERTIES *)v15[2];
          pv = v18;
        }
        while ( !v18 );
        v30 = 0;
        v32 = a2;
        if ( *(_QWORD *)v14->Data4 )
        {
          v19 = *(_QWORD ***)&v12->Data1;
          for ( i = **(_QWORD ***)&v12->Data1; i != v19; i = (_QWORD *)*i )
          {
            v12 = (struct _GUID *)i[2];
            if ( v12 )
            {
              v21 = *(_QWORD *)&v18->guidId.Data1 - *(_QWORD *)&v12->Data1;
              if ( *(_QWORD *)&v18->guidId.Data1 == *(_QWORD *)&v12->Data1 )
                v21 = *(_QWORD *)v18->guidId.Data4 - *(_QWORD *)v12->Data4;
              if ( !v21 )
                goto LABEL_48;
            }
          }
        }
        if ( a4 == 1 )
        {
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
            WPP_SF_S(v16[2], 147, v12, v18->pszwName);
          v11 = CSNOCplCore::AddNewConnectionDUI(a1, v10, v10, v18);
          if ( v11 >= 0 )
          {
            try
            {
              v15[2] = 0;
              if ( *(_QWORD *)v10[5].Data4 == 0xAAAAAAAAAAAAAAALL )
                std::_Xlength_error("list too long");
              v34 = *(_QWORD *)&v28->Data1;
              v38 = v33;
              v39 = 0;
              v22 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
              v22[2] = pv;
              ++*(_QWORD *)v10[5].Data4;
              v23 = v34;
              v24 = *(_QWORD **)(v34 + 8);
              *v22 = v34;
              v22[1] = v24;
              v39 = 0;
              *(_QWORD *)(v23 + 8) = v22;
              *v24 = v22;
              std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(&v38);
            }
            catch ( ... )
            {
              v11 = -2147024882;
              v9 = v26;
              v10 = v35;
              a2 = v32;
              v15 = v31;
              v13 = v30;
              v28 = v36;
            }
          }
        }
        else
        {
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
            WPP_SF_S(v16[2], 148, v12, v18->pszwName);
          v11 = CSNOCplCore::DeleteConnectionDUI(a1, v10, v18);
          FreeNetConnProp(pv);
          v15[2] = 0;
          *(_QWORD *)v15[1] = *v15;
          *(_QWORD *)(*v15 + 8LL) = v15[1];
          --*(_QWORD *)v37[5].Data4;
          std::_Deallocate<16>(v15, 24);
          v15 = **(_QWORD ***)&a2->Data1;
          if ( v15 == *(_QWORD **)&a2->Data1 )
            goto LABEL_13;
          v13 = 1;
        }
        if ( a5 )
          *a5 = 1;
        if ( v11 >= 0 )
          goto LABEL_47;
        if ( !v9 )
          v9 = v11;
        v26 = v9;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          break;
LABEL_48:
        v12 = v25;
        v14 = v27;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
        (unsigned int)v11);
LABEL_47:
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_48;
    }
LABEL_13:
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v40);
  }
  else
  {
    v11 = -2147418113;
  }
  if ( v9 >= 0 )
    v9 = v11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      150,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009c1c  mov     [rsp+arg_8], rbx
0x180009c21  mov     [rsp+arg_18], r9d
0x180009c26  mov     [rsp+arg_0], rcx
0x180009c2b  push    rsi
0x180009c2c  push    r12
0x180009c2e  push    r13
0x180009c30  push    r14
0x180009c32  push    r15
0x180009c34  sub     rsp, 0B0h
0x180009c3b  mov     r12d, r9d
0x180009c3e  mov     r14, rdx
0x180009c41  mov     rbx, rcx
0x180009c44  mov     rax, [rsp+0D8h+arg_20]
0x180009c4c  test    rax, rax
0x180009c4f  jz      short loc_180009C57
0x180009c51  mov     dword ptr [rax], 0
0x180009c57  lea     rdx, [rsp+0D8h+pv]
0x180009c5c  mov     rcx, [rcx+98h]
0x180009c63  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(_GUID const &)
0x180009c68  mov     rcx, [rbx+98h]
0x180009c6f  mov     rax, [rsp+0D8h+pv]
0x180009c74  cmp     rax, [rcx]
0x180009c77  jnz     short loc_180009C83
0x180009c79  mov     eax, 1
0x180009c7e  jmp     loc_180009FEE
0x180009c83  xor     esi, esi
0x180009c85  mov     [rsp+0D8h+var_B0], esi
0x180009c89  mov     r13, [rax+30h]
0x180009c8d  mov     [rsp+0D8h+var_68], r13
0x180009c92  test    r13, r13
0x180009c95  jz      loc_180009FAF
0x180009c9b  xor     r15d, r15d
0x180009c9e  mov     rcx, [rbx+140h]
0x180009ca5  mov     [rsp+0D8h+var_40], rcx
0x180009cad  mov     [rsp+0D8h+var_38], esi
0x180009cb4  lea     rdx, [rsp+0D8h+var_38]
0x180009cbc  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180009cc2  nop
0x180009cc3  lea     rax, [r13+50h]
0x180009cc7  mov     [rsp+0D8h+var_A0], rax
0x180009ccc  test    r12d, r12d
0x180009ccf  jz      short loc_180009CDB
0x180009cd1  mov     r8, rax
0x180009cd4  mov     [rsp+0D8h+var_B8], rax
0x180009cd9  jmp     short loc_180009CE6
0x180009cdb  mov     r8, r14
0x180009cde  mov     [rsp+0D8h+var_B8], r14
0x180009ce3  mov     r14, rax
0x180009ce6  cmp     qword ptr [r14+8], 0
0x180009ceb  jz      short loc_180009D2E
0x180009ced  mov     [rsp+0D8h+var_60], rax
0x180009cf2  mov     [rsp+0D8h+var_78], rax
0x180009cf7  xor     r12d, r12d
0x180009cfa  mov     [rsp+0D8h+var_58], r13
0x180009d02  mov     r9, r8
0x180009d05  mov     [rsp+0D8h+var_A8], r8
0x180009d0a  mov     rbx, [r14]
0x180009d0d  lea     rax, WPP_GLOBAL_Control
0x180009d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d1b  mov     rbx, [rbx]
0x180009d1e  mov     [rsp+0D8h+var_88], rbx
0x180009d23  mov     rdx, [r14]
0x180009d26  cmp     rbx, rdx
0x180009d29  jnz     short loc_180009D48
0x180009d2b  xor     r15d, r15d
0x180009d2e  lea     rbx, WPP_GLOBAL_Control
0x180009d35  lea     rcx, [rsp+0D8h+var_40]; this
0x180009d3d  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180009d42  nop
0x180009d43  jmp     loc_180009FBC
0x180009d48  test    r12d, r12d
0x180009d4b  jz      short loc_180009D55
0x180009d4d  mov     rbx, [rdx]
0x180009d50  mov     [rsp+0D8h+var_88], rbx
0x180009d55  xor     r12d, r12d
0x180009d58  mov     r15, [rbx+10h]
0x180009d5c  mov     [rsp+0D8h+pv], r15
0x180009d61  test    r15, r15
0x180009d64  jz      short loc_180009D1B
0x180009d66  mov     [rsp+0D8h+var_90], r12d
0x180009d6b  mov     [rsp+0D8h+var_80], r14
0x180009d70  cmp     [r9+8], r12
0x180009d74  jz      short loc_180009DAF
0x180009d76  mov     r9, [r8]
0x180009d79  mov     rax, [r9]
0x180009d7c  cmp     rax, r9
0x180009d7f  jz      short loc_180009DA8
0x180009d81  mov     r8, [rax+10h]
0x180009d85  test    r8, r8
0x180009d88  jz      short loc_180009DA3
0x180009d8a  mov     rdx, [r15]
0x180009d8d  sub     rdx, [r8]
0x180009d90  jnz     short loc_180009D9A
0x180009d92  mov     rdx, [r15+8]
0x180009d96  sub     rdx, [r8+8]
0x180009d9a  test    rdx, rdx
0x180009d9d  jz      loc_180009F99
0x180009da3  mov     rax, [rax]
0x180009da6  jmp     short loc_180009D7C
0x180009da8  lea     rax, WPP_GLOBAL_Control
0x180009daf  cmp     [rsp+0D8h+arg_18], 1
0x180009db7  jnz     loc_180009EBB
0x180009dbd  cmp     rcx, rax
0x180009dc0  jz      short loc_180009DDA
0x180009dc2  test    byte ptr [rcx+1Ch], 4
0x180009dc6  jz      short loc_180009DDA
0x180009dc8  mov     edx, 93h
0x180009dcd  mov     r9, [r15+10h]
0x180009dd1  mov     rcx, [rcx+10h]
0x180009dd5  call    WPP_SF_S
0x180009dda  mov     r9, r15; struct tagNETCON_PROPERTIES *
0x180009ddd  mov     r8, r13; struct _GUID *
0x180009de0  mov     rdx, r13; rguid
0x180009de3  mov     rcx, [rsp+0D8h+arg_0]; this
0x180009deb  call    ?AddNewConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@0PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::AddNewConnectionDUI(_GUID const &,_GUID const &,tagNETCON_PROPERTIES *)
0x180009df0  mov     r15d, eax
0x180009df3  test    eax, eax
0x180009df5  js      loc_180009F3F
0x180009dfb  mov     [rbx+10h], r12
0x180009dff  mov     rax, 0AAAAAAAAAAAAAAAh
0x180009e09  cmp     [r13+58h], rax
0x180009e0d  jnz     short loc_180009E1C
0x180009e0f  lea     rcx, aListTooLong; "list too long"
0x180009e16  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009e1c  mov     rax, [rsp+0D8h+var_A0]
0x180009e21  mov     rax, [rax]
0x180009e24  mov     [rsp+0D8h+var_70], rax
0x180009e29  mov     rax, [rsp+0D8h+var_78]
0x180009e2e  mov     [rsp+0D8h+var_50], rax
0x180009e36  mov     [rsp+0D8h+var_48], 0
0x180009e42  mov     ecx, 18h
0x180009e47  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009e4c  mov     rcx, [rsp+0D8h+pv]
0x180009e51  mov     [rax+10h], rcx
0x180009e55  inc     qword ptr [r13+58h]
0x180009e59  mov     rdx, [rsp+0D8h+var_70]
0x180009e5e  mov     rcx, [rdx+8]
0x180009e62  mov     [rax], rdx
0x180009e65  mov     [rax+8], rcx
0x180009e69  mov     [rsp+0D8h+var_48], 0
0x180009e75  mov     [rdx+8], rax
0x180009e79  mov     [rcx], rax
0x180009e7c  lea     rcx, [rsp+0D8h+var_50]
0x180009e84  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAUtagNSC_INSTANCE_DATA@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(void)
0x180009e89  nop
0x180009e8a  jmp     loc_180009F3F
0x180009e8f  mov     r15d, dword ptr [rsp+0D8h+var_A0]
0x180009e94  mov     esi, [rsp+0D8h+var_B0]
0x180009e98  mov     r13, [rsp+0D8h+var_68]
0x180009e9d  mov     r14, [rsp+0D8h+var_80]
0x180009ea2  mov     rbx, [rsp+0D8h+var_88]
0x180009ea7  mov     r12d, [rsp+0D8h+var_90]
0x180009eac  mov     rax, [rsp+0D8h+var_60]
0x180009eb1  mov     [rsp+0D8h+var_A0], rax
0x180009eb6  jmp     loc_180009F3F
0x180009ebb  cmp     rcx, rax
0x180009ebe  jz      short loc_180009ED8
0x180009ec0  test    byte ptr [rcx+1Ch], 4
0x180009ec4  jz      short loc_180009ED8
0x180009ec6  mov     edx, 94h
0x180009ecb  mov     r9, [r15+10h]
0x180009ecf  mov     rcx, [rcx+10h]
0x180009ed3  call    WPP_SF_S
0x180009ed8  mov     r8, r15; struct tagNETCON_PROPERTIES *
0x180009edb  mov     rdx, r13; struct _GUID *
0x180009ede  mov     rcx, [rsp+0D8h+arg_0]; this
0x180009ee6  call    ?DeleteConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::DeleteConnectionDUI(_GUID const &,tagNETCON_PROPERTIES *)
0x180009eeb  mov     r15d, eax
0x180009eee  mov     rcx, [rsp+0D8h+pv]; pv
0x180009ef3  call    ?FreeNetConnProp@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetConnProp(tagNETCON_PROPERTIES *)
0x180009ef8  mov     [rbx+10h], r12
0x180009efc  mov     rcx, [rbx+8]
0x180009f00  mov     rax, [rbx]
0x180009f03  mov     [rcx], rax
0x180009f06  mov     rcx, [rbx]
0x180009f09  mov     rax, [rbx+8]
0x180009f0d  mov     [rcx+8], rax
0x180009f11  mov     rax, [rsp+0D8h+var_58]
0x180009f19  dec     qword ptr [rax+58h]
0x180009f1d  mov     edx, 18h
0x180009f22  mov     rcx, rbx
0x180009f25  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009f2a  mov     rax, [r14]
0x180009f2d  mov     rbx, [rax]
0x180009f30  cmp     rbx, rax
0x180009f33  jz      loc_180009D2E
0x180009f39  mov     r12d, 1
0x180009f3f  mov     rax, [rsp+0D8h+arg_20]
0x180009f47  test    rax, rax
0x180009f4a  jz      short loc_180009F52
0x180009f4c  mov     dword ptr [rax], 1
0x180009f52  test    r15d, r15d
0x180009f55  jns     short loc_180009F92
0x180009f57  test    esi, esi
0x180009f59  cmovz   esi, r15d
0x180009f5d  mov     [rsp+0D8h+var_B0], esi
0x180009f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f68  lea     rax, WPP_GLOBAL_Control
0x180009f6f  cmp     rcx, rax
0x180009f72  jz      short loc_180009FA0
0x180009f74  test    byte ptr [rcx+1Ch], 2
0x180009f78  jz      short loc_180009FA0
0x180009f7a  mov     edx, 95h
0x180009f7f  mov     r9d, r15d
0x180009f82  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009f89  mov     rcx, [rcx+10h]
0x180009f8d  call    WPP_SF_d
0x180009f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f99  lea     rax, WPP_GLOBAL_Control
0x180009fa0  mov     r8, [rsp+0D8h+var_B8]
0x180009fa5  mov     r9, [rsp+0D8h+var_A8]
0x180009faa  jmp     loc_180009D1B
0x180009faf  mov     r15d, 8000FFFFh
0x180009fb5  lea     rbx, WPP_GLOBAL_Control
0x180009fbc  test    esi, esi
0x180009fbe  cmovns  esi, r15d
0x180009fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fc9  cmp     rcx, rbx
0x180009fcc  jz      short loc_180009FEC
0x180009fce  test    byte ptr [rcx+1Ch], 8
0x180009fd2  jz      short loc_180009FEC
0x180009fd4  mov     edx, 96h
0x180009fd9  mov     r9d, esi
0x180009fdc  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009fe3  mov     rcx, [rcx+10h]
0x180009fe7  call    WPP_SF_d
0x180009fec  mov     eax, esi
0x180009fee  mov     rbx, [rsp+0D8h+arg_8]
0x180009ff6  add     rsp, 0B0h
0x180009ffd  pop     r15
0x180009fff  pop     r14
0x18000a001  pop     r13
0x18000a003  pop     r12
0x18000a005  pop     rsi
0x18000a006  retn
```
