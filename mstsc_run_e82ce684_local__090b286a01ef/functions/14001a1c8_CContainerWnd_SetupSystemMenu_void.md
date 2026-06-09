# CContainerWnd::SetupSystemMenu(void)

- ea: `0x14001a1c8`
- end: `0x14001a76a`
- name: `?SetupSystemMenu@CContainerWnd@@AEAAHXZ`
- size: `1442`
- prototype: `__int64 __fastcall(CContainerWnd *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x140014918`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14001a1c8`
- `0x14001b088`
- `0x14001c76c`
- `0x14001cb8c`
- `0x14009693c`
- `0x14009fbb0`
- `0x1400fcad0`
- `0x140113390`

## import_xrefs

- `USER32!ModifyMenuW` at `0x14001a250`
- `USER32!ModifyMenuW` at `0x14001a250`
- `USER32!GetSystemMenu` at `0x14001a200`
- `USER32!GetSystemMenu` at `0x14001a200`
- `USER32!DeleteMenu` at `0x14001a2ac`
- `USER32!DeleteMenu` at `0x14001a2ac`
- `USER32!CreateMenu` at `0x14001a2d4`
- `USER32!CreateMenu` at `0x14001a364`
- `USER32!CreateMenu` at `0x14001a50c`
- `USER32!CreateMenu` at `0x14001a5a0`
- `USER32!CreateMenu` at `0x14001a2d4`
- `USER32!CreateMenu` at `0x14001a364`
- `USER32!CreateMenu` at `0x14001a50c`
- `USER32!CreateMenu` at `0x14001a5a0`
- `USER32!InsertMenuW` at `0x14001a2ce`
- `USER32!InsertMenuW` at `0x14001a316`
- `USER32!InsertMenuW` at `0x14001a3b2`
- `USER32!InsertMenuW` at `0x14001a552`
- `USER32!InsertMenuW` at `0x14001a5e6`
- `USER32!InsertMenuW` at `0x14001a65c`
- `USER32!InsertMenuW` at `0x14001a6b6`
- `USER32!InsertMenuW` at `0x14001a6fd`
- `USER32!InsertMenuW` at `0x14001a737`
- `USER32!InsertMenuW` at `0x14001a2ce`
- `USER32!InsertMenuW` at `0x14001a316`
- `USER32!InsertMenuW` at `0x14001a3b2`
- `USER32!InsertMenuW` at `0x14001a552`
- `USER32!InsertMenuW` at `0x14001a5e6`
- `USER32!InsertMenuW` at `0x14001a65c`
- `USER32!InsertMenuW` at `0x14001a6b6`
- `USER32!InsertMenuW` at `0x14001a6fd`
- `USER32!InsertMenuW` at `0x14001a737`

## pseudocode

```c
__int64 __fastcall CContainerWnd::SetupSystemMenu(CContainerWnd *this)
{
  HMENU SystemMenu; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HMENU Menu; // rdi
  unsigned int v5; // r9d
  unsigned int v6; // r9d
  HMENU v7; // rax
  HMENU v8; // rdi
  HINSTANCE v9; // rcx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  unsigned int v15; // r9d
  unsigned int v16; // r9d
  unsigned int v17; // r9d
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  HMENU v23; // rdi
  unsigned int v24; // r9d
  unsigned int v25; // r9d
  unsigned int v26; // r9d
  HMENU v27; // rax
  HMENU v28; // rdi
  HINSTANCE v29; // rcx
  unsigned int v30; // r9d
  unsigned int v31; // r9d
  WCHAR NewItem[256]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR lpNewItem[256]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR v35[256]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR v36[256]; // [rsp+630h] [rbp+530h] BYREF

  SystemMenu = GetSystemMenu(*((HWND *)this + 1), 0);
  *((_QWORD *)this + 5) = SystemMenu;
  if ( SystemMenu )
  {
    if ( TSLoadString(*((HINSTANCE *)this + 13), 0xBC5u, NewItem, 256)
      && !ModifyMenuW(*((HMENU *)this + 5), 0xF060u, 0, 0xF060u, NewItem)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    DeleteMenu(*((HMENU *)this + 5), 5u, 0x400u);
    InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0x800u, 0x9Fu, 0);
    Menu = CreateMenu();
    if ( Menu )
    {
      if ( TSLoadString(*((HINSTANCE *)this + 13), 0xBB8u, NewItem, 256) )
      {
        InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0x10u, (UINT_PTR)Menu, NewItem);
        CContainerWnd::SimpleAppendMenu(this, 0xBB9u, 0x70u, v5, Menu);
        CContainerWnd::SimpleAppendMenu(this, 0xBBAu, 0x6Du, v6, Menu);
      }
      *((_QWORD *)this + 6) = Menu;
    }
    if ( !*(_DWORD *)(*((_QWORD *)this + 95) + 203420LL) )
    {
      v7 = CreateMenu();
      v8 = v7;
      if ( v7 )
      {
        v9 = (HINSTANCE)*((_QWORD *)this + 13);
        *((_QWORD *)this + 7) = v7;
        if ( TSLoadString(v9, 0xBD9u, NewItem, 256) )
        {
          InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0x10u, (UINT_PTR)v8, NewItem);
          CContainerWnd::SimpleAppendMenu(this, 0xBDBu, 0xA0u, v10, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBDCu, 0xA1u, v11, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBDDu, 0xA2u, v12, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBDEu, 0xA3u, v13, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBDFu, 0xA4u, v14, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBE0u, 0xA5u, v15, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBE1u, 0xA6u, v16, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBE2u, 0xA7u, v17, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBE3u, 0xA8u, v18, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBF0u, 0xB2u, v19, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBF1u, 0xB3u, v20, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBF2u, 0xB4u, v21, v8);
          CContainerWnd::SimpleAppendMenu(this, 0xBF3u, 0xB5u, v22, v8);
          CContainerWnd::SyncZoomMenu(this);
        }
      }
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 95) + 65968LL) )
    {
      v23 = CreateMenu();
      if ( v23 )
      {
        if ( TSLoadString(*((HINSTANCE *)this + 13), 0xBECu, NewItem, 256) )
        {
          InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0x10u, (UINT_PTR)v23, NewItem);
          CContainerWnd::SimpleAppendMenu(this, 0xBEDu, 0xAFu, v24, v23);
          CContainerWnd::SimpleAppendMenu(this, 0xBEEu, 0xB0u, v25, v23);
          CContainerWnd::SimpleAppendMenu(this, 0xBEFu, 0xB1u, v26, v23);
        }
      }
    }
    v27 = CreateMenu();
    v28 = v27;
    if ( v27 )
    {
      v29 = (HINSTANCE)*((_QWORD *)this + 13);
      *((_QWORD *)this + 8) = v27;
      if ( TSLoadString(v29, 0xBE4u, NewItem, 256) )
      {
        InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0x10u, (UINT_PTR)v28, NewItem);
        CContainerWnd::SimpleAppendMenu(this, 0xBE5u, 0xA9u, v30, v28);
        CContainerWnd::SimpleAppendMenu(this, 0xBE6u, 0xAAu, v31, v28);
        CContainerWnd::UpdateClipboardSubmenuItems(this);
      }
    }
    if ( TSLoadString(*((HINSTANCE *)this + 13), 0xBD8u, lpNewItem, 256) )
      InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0, 0x9Du, lpNewItem);
    if ( (unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater()
      && TSLoadString(*((HINSTANCE *)this + 13), 0xBC9u, v35, 256) )
    {
      InsertMenuW(*((HMENU *)this + 5), 0xF060u, *(_DWORD *)(*((_QWORD *)this + 95) + 46160LL) != 0 ? 8 : 0, 0x91u, v35);
    }
    if ( (unsigned int)CUT::UT_StealthReadRegistryInt() && TSLoadString(*((HINSTANCE *)this + 13), 0xBD0u, v36, 256) )
      InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0, 0x97u, v36);
    if ( TSLoadString(*((HINSTANCE *)this + 13), 0xBD7u, NewItem, 256) )
      InsertMenuW(*((HMENU *)this + 5), 0xF060u, 0, 0x9Cu, NewItem);
  }
  return 1;
}

```

## disassembly

```asm
0x14001a1c8  mov     [rsp-8+arg_8], rbx
0x14001a1cd  mov     [rsp-8+arg_10], rdi
0x14001a1d2  push    rbp
0x14001a1d3  push    r14
0x14001a1d5  push    r15
0x14001a1d7  lea     rbp, [rsp-740h]
0x14001a1df  sub     rsp, 840h
0x14001a1e6  mov     rax, cs:__security_cookie
0x14001a1ed  xor     rax, rsp
0x14001a1f0  mov     [rbp+750h+var_20], rax
0x14001a1f7  mov     rbx, rcx
0x14001a1fa  xor     edx, edx; bRevert
0x14001a1fc  mov     rcx, [rcx+8]; hWnd
0x14001a200  call    cs:__imp_GetSystemMenu
0x14001a206  mov     [rbx+28h], rax
0x14001a20a  test    rax, rax
0x14001a20d  jz      loc_14001A73D
0x14001a213  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a217  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a21c  mov     r15d, 100h
0x14001a222  mov     edx, 0BC5h; unsigned int
0x14001a227  mov     r9d, r15d; int
0x14001a22a  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a22f  mov     r14d, 0F060h
0x14001a235  test    eax, eax
0x14001a237  jz      short loc_14001A29D
0x14001a239  mov     rcx, [rbx+28h]; hMnu
0x14001a23d  lea     rax, [rsp+850h+NewItem]
0x14001a242  mov     r9d, r14d; uIDNewItem
0x14001a245  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a24a  xor     r8d, r8d; uFlags
0x14001a24d  mov     edx, r14d; uPosition
0x14001a250  call    cs:__imp_ModifyMenuW
0x14001a256  test    eax, eax
0x14001a258  jnz     short loc_14001A29D
0x14001a25a  mov     rax, cs:WPP_GLOBAL_Control
0x14001a261  lea     rcx, WPP_GLOBAL_Control
0x14001a268  cmp     rax, rcx
0x14001a26b  jz      short loc_14001A29D
0x14001a26d  test    byte ptr [rax+1Ch], 1
0x14001a271  jz      short loc_14001A29D
0x14001a273  cmp     byte ptr [rax+19h], 2
0x14001a277  jb      short loc_14001A29D
0x14001a279  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001a27e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a285  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x14001a28c  mov     edx, 2Ch ; ','
0x14001a291  mov     r9d, eax
0x14001a294  mov     rcx, [rcx+10h]
0x14001a298  call    WPP_SF_d
0x14001a29d  mov     rcx, [rbx+28h]; hMenu
0x14001a2a1  mov     edx, 5; uPosition
0x14001a2a6  mov     r8d, 400h; uFlags
0x14001a2ac  call    cs:__imp_DeleteMenu
0x14001a2b2  mov     rcx, [rbx+28h]; hMenu
0x14001a2b6  mov     r9d, 9Fh; uIDNewItem
0x14001a2bc  mov     r8d, 800h; uFlags
0x14001a2c2  mov     [rsp+850h+lpNewItem], 0; lpNewItem
0x14001a2cb  mov     edx, r14d; uPosition
0x14001a2ce  call    cs:__imp_InsertMenuW
0x14001a2d4  call    cs:__imp_CreateMenu
0x14001a2da  mov     rdi, rax
0x14001a2dd  test    rax, rax
0x14001a2e0  jz      short loc_14001A350
0x14001a2e2  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a2e6  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a2eb  mov     r9d, r15d; int
0x14001a2ee  mov     edx, 0BB8h; unsigned int
0x14001a2f3  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a2f8  test    eax, eax
0x14001a2fa  jz      short loc_14001A34C
0x14001a2fc  mov     rcx, [rbx+28h]; hMenu
0x14001a300  lea     rax, [rsp+850h+NewItem]
0x14001a305  mov     r9, rdi; uIDNewItem
0x14001a308  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a30d  mov     r8d, 10h; uFlags
0x14001a313  mov     edx, r14d; uPosition
0x14001a316  call    cs:__imp_InsertMenuW
0x14001a31c  mov     edx, 0BB9h; unsigned int
0x14001a321  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a326  mov     r8d, 70h ; 'p'; unsigned __int64
0x14001a32c  mov     rcx, rbx; this
0x14001a32f  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a334  mov     edx, 0BBAh; unsigned int
0x14001a339  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a33e  mov     r8d, 6Dh ; 'm'; unsigned __int64
0x14001a344  mov     rcx, rbx; this
0x14001a347  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a34c  mov     [rbx+30h], rdi
0x14001a350  mov     rax, [rbx+2F8h]
0x14001a357  cmp     dword ptr [rax+31A9Ch], 0
0x14001a35e  jnz     loc_14001A4F8
0x14001a364  call    cs:__imp_CreateMenu
0x14001a36a  mov     rdi, rax
0x14001a36d  test    rax, rax
0x14001a370  jz      loc_14001A4F8
0x14001a376  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a37a  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a37f  mov     r9d, r15d; int
0x14001a382  mov     [rbx+38h], rax
0x14001a386  mov     edx, 0BD9h; unsigned int
0x14001a38b  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a390  test    eax, eax
0x14001a392  jz      loc_14001A4F8
0x14001a398  mov     rcx, [rbx+28h]; hMenu
0x14001a39c  lea     rax, [rsp+850h+NewItem]
0x14001a3a1  mov     r9, rdi; uIDNewItem
0x14001a3a4  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a3a9  mov     r8d, 10h; uFlags
0x14001a3af  mov     edx, r14d; uPosition
0x14001a3b2  call    cs:__imp_InsertMenuW
0x14001a3b8  mov     edx, 0BDBh; unsigned int
0x14001a3bd  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a3c2  mov     r8d, 0A0h; unsigned __int64
0x14001a3c8  mov     rcx, rbx; this
0x14001a3cb  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a3d0  mov     edx, 0BDCh; unsigned int
0x14001a3d5  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a3da  mov     r8d, 0A1h; unsigned __int64
0x14001a3e0  mov     rcx, rbx; this
0x14001a3e3  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a3e8  mov     edx, 0BDDh; unsigned int
0x14001a3ed  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a3f2  mov     r8d, 0A2h; unsigned __int64
0x14001a3f8  mov     rcx, rbx; this
0x14001a3fb  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a400  mov     edx, 0BDEh; unsigned int
0x14001a405  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a40a  mov     r8d, 0A3h; unsigned __int64
0x14001a410  mov     rcx, rbx; this
0x14001a413  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a418  mov     edx, 0BDFh; unsigned int
0x14001a41d  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a422  mov     r8d, 0A4h; unsigned __int64
0x14001a428  mov     rcx, rbx; this
0x14001a42b  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a430  mov     edx, 0BE0h; unsigned int
0x14001a435  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a43a  mov     r8d, 0A5h; unsigned __int64
0x14001a440  mov     rcx, rbx; this
0x14001a443  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a448  mov     edx, 0BE1h; unsigned int
0x14001a44d  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a452  mov     r8d, 0A6h; unsigned __int64
0x14001a458  mov     rcx, rbx; this
0x14001a45b  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a460  mov     edx, 0BE2h; unsigned int
0x14001a465  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a46a  mov     r8d, 0A7h; unsigned __int64
0x14001a470  mov     rcx, rbx; this
0x14001a473  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a478  mov     edx, 0BE3h; unsigned int
0x14001a47d  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a482  mov     r8d, 0A8h; unsigned __int64
0x14001a488  mov     rcx, rbx; this
0x14001a48b  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a490  mov     edx, 0BF0h; unsigned int
0x14001a495  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a49a  mov     r8d, 0B2h; unsigned __int64
0x14001a4a0  mov     rcx, rbx; this
0x14001a4a3  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a4a8  mov     edx, 0BF1h; unsigned int
0x14001a4ad  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a4b2  mov     r8d, 0B3h; unsigned __int64
0x14001a4b8  mov     rcx, rbx; this
0x14001a4bb  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a4c0  mov     edx, 0BF2h; unsigned int
0x14001a4c5  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a4ca  mov     r8d, 0B4h; unsigned __int64
0x14001a4d0  mov     rcx, rbx; this
0x14001a4d3  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a4d8  mov     edx, 0BF3h; unsigned int
0x14001a4dd  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a4e2  mov     r8d, 0B5h; unsigned __int64
0x14001a4e8  mov     rcx, rbx; this
0x14001a4eb  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a4f0  mov     rcx, rbx; this
0x14001a4f3  call    ?SyncZoomMenu@CContainerWnd@@AEAAXXZ; CContainerWnd::SyncZoomMenu(void)
0x14001a4f8  mov     rax, [rbx+2F8h]
0x14001a4ff  cmp     dword ptr [rax+101B0h], 0
0x14001a506  jz      loc_14001A5A0
0x14001a50c  call    cs:__imp_CreateMenu
0x14001a512  mov     rdi, rax
0x14001a515  test    rax, rax
0x14001a518  jz      loc_14001A5A0
0x14001a51e  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a522  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a527  mov     r9d, r15d; int
0x14001a52a  mov     edx, 0BECh; unsigned int
0x14001a52f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a534  test    eax, eax
0x14001a536  jz      short loc_14001A5A0
0x14001a538  mov     rcx, [rbx+28h]; hMenu
0x14001a53c  lea     rax, [rsp+850h+NewItem]
0x14001a541  mov     r9, rdi; uIDNewItem
0x14001a544  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a549  mov     r8d, 10h; uFlags
0x14001a54f  mov     edx, r14d; uPosition
0x14001a552  call    cs:__imp_InsertMenuW
0x14001a558  mov     edx, 0BEDh; unsigned int
0x14001a55d  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a562  mov     r8d, 0AFh; unsigned __int64
0x14001a568  mov     rcx, rbx; this
0x14001a56b  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a570  mov     edx, 0BEEh; unsigned int
0x14001a575  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a57a  mov     r8d, 0B0h; unsigned __int64
0x14001a580  mov     rcx, rbx; this
0x14001a583  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a588  mov     edx, 0BEFh; unsigned int
0x14001a58d  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a592  mov     r8d, 0B1h; unsigned __int64
0x14001a598  mov     rcx, rbx; this
0x14001a59b  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a5a0  call    cs:__imp_CreateMenu
0x14001a5a6  mov     rdi, rax
0x14001a5a9  test    rax, rax
0x14001a5ac  jz      short loc_14001A624
0x14001a5ae  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a5b2  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a5b7  mov     r9d, r15d; int
0x14001a5ba  mov     [rbx+40h], rax
0x14001a5be  mov     edx, 0BE4h; unsigned int
0x14001a5c3  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a5c8  test    eax, eax
0x14001a5ca  jz      short loc_14001A624
0x14001a5cc  mov     rcx, [rbx+28h]; hMenu
0x14001a5d0  lea     rax, [rsp+850h+NewItem]
0x14001a5d5  mov     r9, rdi; uIDNewItem
0x14001a5d8  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a5dd  mov     r8d, 10h; uFlags
0x14001a5e3  mov     edx, r14d; uPosition
0x14001a5e6  call    cs:__imp_InsertMenuW
0x14001a5ec  mov     edx, 0BE5h; unsigned int
0x14001a5f1  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a5f6  mov     r8d, 0A9h; unsigned __int64
0x14001a5fc  mov     rcx, rbx; this
0x14001a5ff  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a604  mov     edx, 0BE6h; unsigned int
0x14001a609  mov     [rsp+850h+lpNewItem], rdi; HMENU
0x14001a60e  mov     r8d, 0AAh; unsigned __int64
0x14001a614  mov     rcx, rbx; this
0x14001a617  call    ?SimpleAppendMenu@CContainerWnd@@AEAAHI_KIPEAUHMENU__@@@Z; CContainerWnd::SimpleAppendMenu(uint,unsigned __int64,uint,HMENU__ *)
0x14001a61c  mov     rcx, rbx; this
0x14001a61f  call    ?UpdateClipboardSubmenuItems@CContainerWnd@@AEAAXXZ; CContainerWnd::UpdateClipboardSubmenuItems(void)
0x14001a624  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a628  lea     r8, [rbp+750h+var_620]; unsigned __int16 *
0x14001a62f  mov     r9d, r15d; int
0x14001a632  mov     edx, 0BD8h; unsigned int
0x14001a637  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a63c  test    eax, eax
0x14001a63e  jz      short loc_14001A662
0x14001a640  mov     rcx, [rbx+28h]; hMenu
0x14001a644  lea     rax, [rbp+750h+var_620]
0x14001a64b  mov     r9d, 9Dh; uIDNewItem
0x14001a651  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a656  xor     r8d, r8d; uFlags
0x14001a659  mov     edx, r14d; uPosition
0x14001a65c  call    cs:__imp_InsertMenuW
0x14001a662  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x14001a667  test    eax, eax
0x14001a669  jz      short loc_14001A6BC
0x14001a66b  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a66f  lea     r8, [rbp+750h+var_420]; unsigned __int16 *
0x14001a676  mov     r9d, r15d; int
0x14001a679  mov     edx, 0BC9h; unsigned int
0x14001a67e  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a683  test    eax, eax
0x14001a685  jz      short loc_14001A6BC
0x14001a687  mov     rax, [rbx+2F8h]
0x14001a68e  mov     r9d, 91h; uIDNewItem
0x14001a694  mov     edx, r14d; uPosition
0x14001a697  mov     ecx, [rax+0B450h]
0x14001a69d  lea     rax, [rbp+750h+var_420]
0x14001a6a4  neg     ecx
0x14001a6a6  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a6ab  mov     rcx, [rbx+28h]; hMenu
0x14001a6af  sbb     r8d, r8d
0x14001a6b2  and     r8d, 8; uFlags
0x14001a6b6  call    cs:__imp_InsertMenuW
0x14001a6bc  call    ?UT_StealthReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_StealthReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x14001a6c1  test    eax, eax
0x14001a6c3  jz      short loc_14001A703
0x14001a6c5  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a6c9  lea     r8, [rbp+750h+var_220]; unsigned __int16 *
0x14001a6d0  mov     r9d, r15d; int
0x14001a6d3  mov     edx, 0BD0h; unsigned int
0x14001a6d8  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14001a6dd  test    eax, eax
0x14001a6df  jz      short loc_14001A703
0x14001a6e1  mov     rcx, [rbx+28h]; hMenu
0x14001a6e5  lea     rax, [rbp+750h+var_220]
0x14001a6ec  mov     r9d, 97h; uIDNewItem
0x14001a6f2  mov     [rsp+850h+lpNewItem], rax; lpNewItem
0x14001a6f7  xor     r8d, r8d; uFlags
0x14001a6fa  mov     edx, r14d; uPosition
0x14001a6fd  call    cs:__imp_InsertMenuW
0x14001a703  mov     rcx, [rbx+68h]; HINSTANCE
0x14001a707  lea     r8, [rsp+850h+NewItem]; unsigned __int16 *
0x14001a70c  mov     r9d, r15d; int
  ... truncated ...
```
