# CProfileMgr::AppendSSID(HINSTANCE__ *,uint,tagNETCON_PROPERTIES *)

- ea: `0x18001f3a4`
- end: `0x18001f53d`
- name: `?AppendSSID@CProfileMgr@@QEAAJPEAUHINSTANCE__@@IPEAUtagNETCON_PROPERTIES@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CProfileMgr *__hidden this, HINSTANCE, unsigned int, struct tagNETCON_PROPERTIES *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ea5c`
- `0x18001fde8`

## callees

- `0x180002270`
- `0x1800075a8`
- `0x180007618`
- `0x1800077a4`
- `0x180007b34`
- `0x180007ffc`
- `0x180013d68`
- `0x180014274`
- `0x18001f3a4`
- `0x180020928`
- `0x180021ff4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001f3f1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001f3f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProfileMgr::AppendSSID(
        CProfileMgr *this,
        HINSTANCE a2,
        __int64 a3,
        struct tagNETCON_PROPERTIES *a4)
{
  __int64 v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r9
  int WirelessInfo; // eax
  int v12; // ebx
  PVOID v13; // rcx
  WCHAR *v15; // [rsp+30h] [rbp-88h] BYREF
  __int64 v16; // [rsp+38h] [rbp-80h]
  __int64 v17; // [rsp+40h] [rbp-78h] BYREF
  __int64 v18; // [rsp+48h] [rbp-70h]
  _BYTE v19[80]; // [rsp+50h] [rbp-68h] BYREF

  std::list<tagNETCON_PROPERTIES *>::list<tagNETCON_PROPERTIES *>(&v17);
  try
  {
    if ( v18 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("list too long");
    v6 = v17;
    v15 = (WCHAR *)&v17;
    v16 = 0;
    v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
    v7[2] = a4;
    ++v18;
    v8 = *(_QWORD **)(v6 + 8);
    *v7 = v6;
    v7[1] = v8;
    v16 = 0;
    *(_QWORD *)(v6 + 8) = v7;
    *v8 = v7;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(&v15);
    LODWORD(v15) = 0;
    WirelessInfo = CProfileMgr::GetWirelessInfo(v9, &v17, (__int64)v19, v10, (unsigned int *)&v15);
  }
  catch ( ... )
  {
    LODWORD(v15) = -2147024882;
    v12 = -2147024882;
    goto LABEL_10;
  }
  v12 = WirelessInfo;
  if ( WirelessInfo )
  {
    if ( WirelessInfo == 1 )
      v12 = 0;
  }
  else
  {
    v15 = 0;
    v12 = ResourceStringCoAllocFormatMessage(a2, 196, &v15, a4->pszwName, v19);
    if ( v12 >= 0 )
    {
      CoTaskMemFree(a4->pszwName);
      a4->pszwName = v15;
    }
  }
LABEL_10:
  std::list<tagNETCON_PROPERTIES *>::clear(&v17);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)v12);
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(v13, v17);
  std::_Deallocate<16>(v17, 24);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f3a4  mov     [rsp+arg_0], rbx
0x18001f3a9  mov     [rsp+arg_10], rsi
0x18001f3ae  push    rdi
0x18001f3af  sub     rsp, 0B0h
0x18001f3b6  mov     rax, cs:__security_cookie
0x18001f3bd  xor     rax, rsp
0x18001f3c0  mov     [rsp+0B8h+var_18], rax
0x18001f3c8  mov     rdi, r9
0x18001f3cb  mov     rsi, rdx
0x18001f3ce  lea     rcx, [rsp+0B8h+var_78]
0x18001f3d3  call    ??0?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@QEAA@XZ; std::list<tagNETCON_PROPERTIES *>::list<tagNETCON_PROPERTIES *>(void)
0x18001f3d8  nop
0x18001f3d9  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001f3e3  cmp     [rsp+0B8h+var_70], rax
0x18001f3e8  jnz     short loc_18001F3F7
0x18001f3ea  lea     rcx, aListTooLong; "list too long"
0x18001f3f1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f3f7  mov     rbx, [rsp+0B8h+var_78]
0x18001f3fc  lea     rax, [rsp+0B8h+var_78]
0x18001f401  mov     [rsp+0B8h+var_88], rax
0x18001f406  mov     [rsp+0B8h+var_80], 0
0x18001f40f  mov     ecx, 18h
0x18001f414  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001f419  mov     [rax+10h], rdi
0x18001f41d  inc     [rsp+0B8h+var_70]
0x18001f422  mov     rcx, [rbx+8]
0x18001f426  mov     [rax], rbx
0x18001f429  mov     [rax+8], rcx
0x18001f42d  mov     [rsp+0B8h+var_80], 0
0x18001f436  mov     [rbx+8], rax
0x18001f43a  mov     [rcx], rax
0x18001f43d  lea     rcx, [rsp+0B8h+var_88]
0x18001f442  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAUtagNSC_INSTANCE_DATA@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(void)
0x18001f447  nop
0x18001f448  mov     dword ptr [rsp+0B8h+var_88], 0
0x18001f450  lea     rax, [rsp+0B8h+var_88]
0x18001f455  mov     [rsp+0B8h+var_98], rax
0x18001f45a  lea     r8, [rsp+0B8h+var_68]
0x18001f45f  lea     rdx, [rsp+0B8h+var_78]
0x18001f464  call    ?GetWirelessInfo@CProfileMgr@@QEAAJPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@PEAGIPEAK@Z; CProfileMgr::GetWirelessInfo(std::list<tagNETCON_PROPERTIES *> *,ushort *,uint,ulong *)
0x18001f469  mov     ebx, eax
0x18001f46b  test    eax, eax
0x18001f46d  jnz     short loc_18001F4B3
0x18001f46f  mov     [rsp+0B8h+var_88], 0
0x18001f478  lea     rax, [rsp+0B8h+var_68]
0x18001f47d  mov     [rsp+0B8h+var_98], rax
0x18001f482  mov     r9, [rdi+10h]
0x18001f486  lea     r8, [rsp+0B8h+var_88]
0x18001f48b  mov     edx, 0C4h
0x18001f490  mov     rcx, rsi
0x18001f493  call    ResourceStringCoAllocFormatMessage
0x18001f498  mov     ebx, eax
0x18001f49a  test    eax, eax
0x18001f49c  js      short loc_18001F4C1
0x18001f49e  mov     rcx, [rdi+10h]; pv
0x18001f4a2  call    cs:__imp_CoTaskMemFree
0x18001f4a8  mov     rcx, [rsp+0B8h+var_88]
0x18001f4ad  mov     [rdi+10h], rcx
0x18001f4b1  jmp     short loc_18001F4C1
0x18001f4b3  xor     eax, eax
0x18001f4b5  cmp     ebx, 1
0x18001f4b8  cmovz   ebx, eax
0x18001f4bb  jmp     short loc_18001F4C1
0x18001f4bd  mov     ebx, dword ptr [rsp+0B8h+var_88]
0x18001f4c1  lea     rcx, [rsp+0B8h+var_78]
0x18001f4c6  call    ?clear@?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@QEAAXXZ; std::list<tagNETCON_PROPERTIES *>::clear(void)
0x18001f4cb  lea     rax, WPP_GLOBAL_Control
0x18001f4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4d9  cmp     rcx, rax
0x18001f4dc  jz      short loc_18001F4FD
0x18001f4de  test    byte ptr [rcx+1Ch], 8
0x18001f4e2  jz      short loc_18001F4FD
0x18001f4e4  mov     edx, 37h ; '7'
0x18001f4e9  mov     r9d, ebx
0x18001f4ec  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x18001f4f3  mov     rcx, [rcx+10h]
0x18001f4f7  call    WPP_SF_d
0x18001f4fc  nop
0x18001f4fd  mov     rdx, [rsp+0B8h+var_78]
0x18001f502  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x18001f507  mov     edx, 18h
0x18001f50c  mov     rcx, [rsp+0B8h+var_78]
0x18001f511  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001f516  mov     eax, ebx
0x18001f518  mov     rcx, [rsp+0B8h+var_18]
0x18001f520  xor     rcx, rsp; StackCookie
0x18001f523  call    __security_check_cookie
0x18001f528  lea     r11, [rsp+0B8h+var_8]
0x18001f530  mov     rbx, [r11+10h]
0x18001f534  mov     rsi, [r11+20h]
0x18001f538  mov     rsp, r11
0x18001f53b  pop     rdi
0x18001f53c  retn
```
