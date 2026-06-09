# CSNOCplCore::UpdateConnectionList(_GUID const &,_GUID const &,std::list<tagNETCON_PROPERTIES *,std::allocator<tagNETCON_PROPERTIES *>> *,std::list<tagNETCON_PROPERTIES *,std::allocator<tagNETCON_PROPERTIES *>> *)

- ea: `0x180012b6c`
- end: `0x180012ebe`
- name: `?UpdateConnectionList@CSNOCplCore@@AEAAJAEBU_GUID@@0PEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@1@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f9ec`

## callees

- `0x180002270`
- `0x180002c2c`
- `0x180006b70`
- `0x180008b7c`
- `0x18000981c`
- `0x180012580`
- `0x180012978`
- `0x180012b6c`
- `0x180014274`
- `0x1800142b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012de7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012cc8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c99`
- `DUI70!StrToID` at `0x180012cdf`
- `DUI70!StrToID` at `0x180012d00`
- `DUI70!StrToID` at `0x180012d43`
- `DUI70!StrToID` at `0x180012cdf`
- `DUI70!StrToID` at `0x180012d00`
- `DUI70!StrToID` at `0x180012d43`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012ceb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012d0c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012d4f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012ceb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012d0c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012d4f`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::UpdateConnectionList(
        CSNOCplCore *a1,
        GUID *a2,
        const struct _GUID *a3,
        __int64 a4,
        __int64 a5)
{
  CSNOCplCore *v6; // rbp
  PVOID *v7; // rcx
  unsigned __int64 v8; // r15
  int v9; // edi
  unsigned __int64 v10; // r13
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbp
  _QWORD *v13; // rbx
  struct tagNETCON_PROPERTIES *v14; // rdi
  int v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // r15
  DirectUI::Element *v18; // rbx
  unsigned __int16 v19; // ax
  DirectUI::Element *Descendent; // rbx
  __int64 v21; // r8
  unsigned __int16 v22; // ax
  DirectUI::Element *v23; // r13
  _QWORD *v24; // rbx
  unsigned __int64 i; // rbp
  unsigned __int16 v26; // ax
  struct DirectUI::Element *v27; // rax
  const struct _GUID *v28; // r14
  _QWORD *v29; // rbx
  unsigned __int64 v30; // rbp
  bool j; // sf
  struct tagNETCON_PROPERTIES *v32; // rdi
  int updated; // eax
  unsigned __int64 v34; // rbp
  _QWORD *v35; // rbx
  struct tagNETCON_PROPERTIES *v36; // rdi
  int v37; // eax
  unsigned __int64 v40; // [rsp+28h] [rbp-C0h]
  OLECHAR sz[40]; // [rsp+40h] [rbp-A8h] BYREF

  v6 = a1;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a4 || !a5 )
    return 2147500035LL;
  v8 = *(_QWORD *)(a4 + 8);
  v9 = 0;
  v10 = *(_QWORD *)(a5 + 8);
  v11 = v8;
  v40 = v10;
  if ( v8 >= v10 )
    v11 = *(_QWORD *)(a5 + 8);
  if ( v8 > v11 )
  {
    v12 = 0;
    v13 = **(_QWORD ***)a4;
    while ( v12 < v8 )
    {
      if ( v12 >= v11 )
      {
        v14 = (struct tagNETCON_PROPERTIES *)v13[2];
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
          WPP_SF_S(v7[2], 139, a3, v14->pszwName);
        v15 = CSNOCplCore::DeleteConnectionDUI(a1, a2, v14);
        v7 = (PVOID *)WPP_GLOBAL_Control;
        v9 = v15;
      }
      v13 = (_QWORD *)*v13;
      ++v12;
      if ( v9 < 0 )
        goto LABEL_52;
    }
    v6 = a1;
  }
  if ( v11 )
  {
    v16 = CoTaskMemAlloc(8 * v11);
    v17 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, 8 * v11);
      StringFromGUID2(a2, sz, 39);
      v18 = (DirectUI::Element *)*((_QWORD *)v6 + 40);
      v9 = -2147467259;
      v19 = StrToID(sz);
      Descendent = DirectUI::Element::FindDescendent(v18, v19);
      if ( Descendent )
      {
        v22 = StrToID(L"connlist");
        v23 = DirectUI::Element::FindDescendent(Descendent, v22);
        if ( v23 && *(_QWORD *)(a4 + 8) )
        {
          v24 = *(_QWORD **)a4;
          v9 = 0;
          for ( i = 0; ; ++i )
          {
            v24 = (_QWORD *)*v24;
            if ( i >= v11 )
              break;
            StringFromGUID2((struct _GUID *)v24[2], sz, v21);
            v26 = StrToID(sz);
            v27 = DirectUI::Element::FindDescendent(v23, v26);
            v17[i] = v27;
            if ( !v27 )
            {
              v9 = -2147467259;
              break;
            }
          }
        }
        v10 = v40;
      }
      v28 = a3;
      if ( *(_QWORD *)(a5 + 8) )
      {
        v29 = *(_QWORD **)a5;
        v30 = 0;
        for ( j = v9 < 0; ; j = updated < 0 )
        {
          v29 = (_QWORD *)*v29;
          if ( j || v30 >= v11 )
            break;
          v32 = (struct tagNETCON_PROPERTIES *)v29[2];
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, v21, v32->pszwName);
          updated = CSNOCplCore::UpdateConnectionDUI(a1, (struct DirectUI::Element *)v17[v30++], a3, v32);
          v9 = updated;
        }
      }
    }
    else
    {
      v28 = a3;
      v9 = -2147024882;
    }
    CoTaskMemFree(v17);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( v9 < 0 )
      goto LABEL_52;
  }
  else
  {
    v28 = a3;
  }
  if ( v10 > v11 )
  {
    v34 = 0;
    v35 = **(_QWORD ***)a5;
    do
    {
      if ( v34 >= v10 )
        break;
      if ( v34 >= v11 )
      {
        v36 = (struct tagNETCON_PROPERTIES *)v35[2];
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
          WPP_SF_S(v7[2], 141, a3, v36->pszwName);
        v37 = CSNOCplCore::AddNewConnectionDUI(a1, a2, v28, v36);
        v7 = (PVOID *)WPP_GLOBAL_Control;
        v9 = v37;
      }
      v35 = (_QWORD *)*v35;
      ++v34;
    }
    while ( v9 >= 0 );
  }
LABEL_52:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_d(v7[2], 142, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012b6c  push    rbx
0x180012b6e  push    rbp
0x180012b6f  push    rsi
0x180012b70  push    rdi
0x180012b71  push    r12
0x180012b73  push    r13
0x180012b75  push    r14
0x180012b77  push    r15
0x180012b79  sub     rsp, 0A8h
0x180012b80  mov     rax, cs:__security_cookie
0x180012b87  xor     rax, rsp
0x180012b8a  mov     [rsp+0E8h+var_58], rax
0x180012b92  mov     r12, [rsp+0E8h+arg_20]
0x180012b9a  mov     r14, r9
0x180012b9d  mov     [rsp+0E8h+var_C8], r8
0x180012ba2  mov     rbp, rcx
0x180012ba5  mov     [rsp+0E8h+rguid], rdx
0x180012baa  mov     [rsp+0E8h+var_B8], rcx
0x180012baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bb6  lea     rax, WPP_GLOBAL_Control
0x180012bbd  cmp     rcx, rax
0x180012bc0  jz      short loc_180012BEB
0x180012bc2  test    byte ptr [rcx+1Ch], 8
0x180012bc6  jz      short loc_180012BEB
0x180012bc8  mov     rcx, [rcx+10h]
0x180012bcc  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180012bd3  mov     edx, 84h
0x180012bd8  call    WPP_SF_
0x180012bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012be4  lea     rax, WPP_GLOBAL_Control
0x180012beb  test    r14, r14
0x180012bee  jz      loc_180012E95
0x180012bf4  test    r12, r12
0x180012bf7  jz      loc_180012E95
0x180012bfd  mov     r15, [r14+8]
0x180012c01  xor     edi, edi
0x180012c03  mov     r13, [r12+8]
0x180012c08  mov     rsi, r15
0x180012c0b  cmp     r15, r13
0x180012c0e  mov     [rsp+0E8h+var_C0], r13
0x180012c13  cmovnb  rsi, r13
0x180012c17  cmp     r15, rsi
0x180012c1a  jbe     short loc_180012C85
0x180012c1c  mov     rbx, [r14]
0x180012c1f  xor     ebp, ebp
0x180012c21  mov     rbx, [rbx]
0x180012c24  cmp     rbp, r15
0x180012c27  jnb     short loc_180012C80
0x180012c29  cmp     rbp, rsi
0x180012c2c  jb      short loc_180012C6A
0x180012c2e  mov     rdi, [rbx+10h]
0x180012c32  cmp     rcx, rax
0x180012c35  jz      short loc_180012C4F
0x180012c37  test    byte ptr [rcx+1Ch], 8
0x180012c3b  jz      short loc_180012C4F
0x180012c3d  mov     r9, [rdi+10h]
0x180012c41  mov     edx, 8Bh
0x180012c46  mov     rcx, [rcx+10h]
0x180012c4a  call    WPP_SF_S
0x180012c4f  mov     rdx, [rsp+0E8h+rguid]; struct _GUID *
0x180012c54  mov     r8, rdi; struct tagNETCON_PROPERTIES *
0x180012c57  mov     rcx, [rsp+0E8h+var_B8]; this
0x180012c5c  call    ?DeleteConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::DeleteConnectionDUI(_GUID const &,tagNETCON_PROPERTIES *)
0x180012c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c68  mov     edi, eax
0x180012c6a  mov     rbx, [rbx]
0x180012c6d  lea     rax, WPP_GLOBAL_Control
0x180012c74  inc     rbp
0x180012c77  test    edi, edi
0x180012c79  jns     short loc_180012C24
0x180012c7b  jmp     loc_180012E67
0x180012c80  mov     rbp, [rsp+0E8h+var_B8]
0x180012c85  test    rsi, rsi
0x180012c88  jz      loc_180012DFA
0x180012c8e  lea     rbx, ds:0[rsi*8]
0x180012c96  mov     rcx, rbx; cb
0x180012c99  call    cs:__imp_CoTaskMemAlloc
0x180012c9f  mov     r15, rax
0x180012ca2  test    rax, rax
0x180012ca5  jz      loc_180012DDA
0x180012cab  mov     r8, rbx; Size
0x180012cae  xor     edx, edx; Val
0x180012cb0  mov     rcx, rax; void *
0x180012cb3  call    memset_0
0x180012cb8  mov     rcx, [rsp+0E8h+rguid]; rguid
0x180012cbd  lea     rdx, [rsp+0E8h+sz]; lpsz
0x180012cc2  mov     r8d, 27h ; '''; cchMax
0x180012cc8  call    cs:__imp_StringFromGUID2
0x180012cce  mov     rbx, [rbp+140h]
0x180012cd5  lea     rcx, [rsp+0E8h+sz]
0x180012cda  mov     edi, 80004005h
0x180012cdf  call    cs:__imp_StrToID
0x180012ce5  movzx   edx, ax
0x180012ce8  mov     rcx, rbx
0x180012ceb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012cf1  mov     rbx, rax
0x180012cf4  test    rax, rax
0x180012cf7  jz      short loc_180012D6D
0x180012cf9  lea     rcx, aConnlist; "connlist"
0x180012d00  call    cs:__imp_StrToID
0x180012d06  movzx   edx, ax
0x180012d09  mov     rcx, rbx
0x180012d0c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012d12  mov     r13, rax
0x180012d15  test    rax, rax
0x180012d18  jz      short loc_180012D68
0x180012d1a  cmp     qword ptr [r14+8], 0
0x180012d1f  jz      short loc_180012D68
0x180012d21  mov     rbx, [r14]
0x180012d24  xor     edi, edi
0x180012d26  xor     ebp, ebp
0x180012d28  mov     rbx, [rbx]
0x180012d2b  cmp     rbp, rsi
0x180012d2e  jnb     short loc_180012D68
0x180012d30  mov     rcx, [rbx+10h]; struct _GUID *
0x180012d34  lea     rdx, [rsp+0E8h+sz]; unsigned __int16 *
0x180012d39  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x180012d3e  lea     rcx, [rsp+0E8h+sz]
0x180012d43  call    cs:__imp_StrToID
0x180012d49  movzx   edx, ax
0x180012d4c  mov     rcx, r13
0x180012d4f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012d55  mov     [r15+rbp*8], rax
0x180012d59  test    rax, rax
0x180012d5c  jz      short loc_180012D63
0x180012d5e  inc     rbp
0x180012d61  jmp     short loc_180012D28
0x180012d63  mov     edi, 80004005h
0x180012d68  mov     r13, [rsp+0E8h+var_C0]
0x180012d6d  cmp     qword ptr [r12+8], 0
0x180012d73  mov     r14, [rsp+0E8h+var_C8]
0x180012d78  jz      short loc_180012DE4
0x180012d7a  mov     rbx, [r12]
0x180012d7e  xor     ebp, ebp
0x180012d80  test    edi, edi
0x180012d82  jmp     short loc_180012DD3
0x180012d84  cmp     rbp, rsi
0x180012d87  jnb     short loc_180012DE4
0x180012d89  mov     rdi, [rbx+10h]
0x180012d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d94  lea     rax, WPP_GLOBAL_Control
0x180012d9b  cmp     rcx, rax
0x180012d9e  jz      short loc_180012DB8
0x180012da0  test    byte ptr [rcx+1Ch], 8
0x180012da4  jz      short loc_180012DB8
0x180012da6  mov     r9, [rdi+10h]
0x180012daa  mov     edx, 8Ch
0x180012daf  mov     rcx, [rcx+10h]
0x180012db3  call    WPP_SF_S
0x180012db8  mov     rdx, [r15+rbp*8]; struct DirectUI::Element *
0x180012dbc  mov     r9, rdi; struct tagNETCON_PROPERTIES *
0x180012dbf  mov     rcx, [rsp+0E8h+var_B8]; this
0x180012dc4  mov     r8, r14; struct _GUID *
0x180012dc7  call    ?UpdateConnectionDUI@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::UpdateConnectionDUI(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)
0x180012dcc  inc     rbp
0x180012dcf  mov     edi, eax
0x180012dd1  test    eax, eax
0x180012dd3  mov     rbx, [rbx]
0x180012dd6  jns     short loc_180012D84
0x180012dd8  jmp     short loc_180012DE4
0x180012dda  mov     r14, [rsp+0E8h+var_C8]
0x180012ddf  mov     edi, 8007000Eh
0x180012de4  mov     rcx, r15; pv
0x180012de7  call    cs:__imp_CoTaskMemFree
0x180012ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180012df4  test    edi, edi
0x180012df6  jns     short loc_180012DFF
0x180012df8  jmp     short loc_180012E67
0x180012dfa  mov     r14, [rsp+0E8h+var_C8]
0x180012dff  cmp     r13, rsi
0x180012e02  jbe     short loc_180012E67
0x180012e04  mov     rbx, [r12]
0x180012e08  xor     ebp, ebp
0x180012e0a  mov     rbx, [rbx]
0x180012e0d  cmp     rbp, r13
0x180012e10  jnb     short loc_180012E67
0x180012e12  cmp     rbp, rsi
0x180012e15  jb      short loc_180012E5D
0x180012e17  mov     rdi, [rbx+10h]
0x180012e1b  lea     rax, WPP_GLOBAL_Control
0x180012e22  cmp     rcx, rax
0x180012e25  jz      short loc_180012E3F
0x180012e27  test    byte ptr [rcx+1Ch], 8
0x180012e2b  jz      short loc_180012E3F
0x180012e2d  mov     r9, [rdi+10h]
0x180012e31  mov     edx, 8Dh
0x180012e36  mov     rcx, [rcx+10h]
0x180012e3a  call    WPP_SF_S
0x180012e3f  mov     rdx, [rsp+0E8h+rguid]; rguid
0x180012e44  mov     r9, rdi; struct tagNETCON_PROPERTIES *
0x180012e47  mov     rcx, [rsp+0E8h+var_B8]; this
0x180012e4c  mov     r8, r14; struct _GUID *
0x180012e4f  call    ?AddNewConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@0PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::AddNewConnectionDUI(_GUID const &,_GUID const &,tagNETCON_PROPERTIES *)
0x180012e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e5b  mov     edi, eax
0x180012e5d  mov     rbx, [rbx]
0x180012e60  inc     rbp
0x180012e63  test    edi, edi
0x180012e65  jns     short loc_180012E0D
0x180012e67  lea     rax, WPP_GLOBAL_Control
0x180012e6e  cmp     rcx, rax
0x180012e71  jz      short loc_180012E91
0x180012e73  test    byte ptr [rcx+1Ch], 8
0x180012e77  jz      short loc_180012E91
0x180012e79  mov     rcx, [rcx+10h]
0x180012e7d  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180012e84  mov     edx, 8Eh
0x180012e89  mov     r9d, edi
0x180012e8c  call    WPP_SF_d
0x180012e91  mov     eax, edi
0x180012e93  jmp     short loc_180012E9A
0x180012e95  mov     eax, 80004003h
0x180012e9a  mov     rcx, [rsp+0E8h+var_58]
0x180012ea2  xor     rcx, rsp; StackCookie
0x180012ea5  call    __security_check_cookie
0x180012eaa  add     rsp, 0A8h
0x180012eb1  pop     r15
0x180012eb3  pop     r14
0x180012eb5  pop     r13
0x180012eb7  pop     r12
0x180012eb9  pop     rdi
0x180012eba  pop     rsi
0x180012ebb  pop     rbp
0x180012ebc  pop     rbx
0x180012ebd  retn
```
