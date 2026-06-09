# CConnectionFolderContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x18004e670`
- end: `0x18004e7c3`
- name: `?QueryContextMenu@CConnectionFolderContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `339`
- prototype: `int(CConnectionFolderContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001bc10`
- `0x180034cc8`
- `0x180049e0c`
- `0x18004d034`
- `0x18004e670`

## import_xrefs

- `SHELL32!__imp_Shell_MergeMenus` at `0x18004e79b`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18004e79b`
- `USER32!DestroyMenu` at `0x18004e7ad`
- `USER32!DestroyMenu` at `0x18004e7ad`
- `USER32!CreateMenu` at `0x18004e710`
- `USER32!CreateMenu` at `0x18004e710`
- `USER32!SetMenuInfo` at `0x18004e774`
- `USER32!SetMenuInfo` at `0x18004e774`

## pseudocode

```c
__int64 __fastcall CConnectionFolderContextMenu::QueryContextMenu(
        CConnectionFolderContextMenu *this,
        HMENU a2,
        UINT a3,
        int a4,
        UINT uIDAdjustMax,
        unsigned int a6)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v13; // ebx
  HMENU hmSrc; // [rsp+30h] [rbp-68h] BYREF
  MENUINFO v15; // [rsp+38h] [rbp-60h] BYREF

  if ( a6 == 1
    && (unsigned int)IsMediaRASType((enum tagNETCON_MEDIATYPE)*(_DWORD *)(**((_QWORD **)this + 9) + 48LL))
    && (unsigned int)FCheckGroupMembershipInternal(v11, v10, 0x222u, 0) )
  {
    NcMsgBox(hInst, 0, 0x424u, 0x449u, 0x30u);
    return 2147500037LL;
  }
  else
  {
    v13 = 0;
    if ( *((_QWORD *)this + 10) != *((_QWORD *)this + 9) && (a6 & 0x10000) == 0 )
    {
      hmSrc = CreateMenu();
      if ( hmSrc )
      {
        v13 = HrBuildMenu(&hmSrc, (a6 >> 1) & 1, (char *)this + 72);
        if ( v13 >= 0 )
        {
          v15.cbSize = 40;
          memset(&v15.cyMax, 0, 28);
          v15.fMask = 16;
          v15.dwStyle = 0x4000000;
          SetMenuInfo(a2, &v15);
          v13 = (unsigned __int16)(Shell_MergeMenus(a2, hmSrc, a3, a4, uIDAdjustMax, 3u) - a4);
        }
        DestroyMenu(hmSrc);
      }
    }
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18004e670  push    rbx
0x18004e672  push    rsi
0x18004e673  push    rdi
0x18004e674  push    r12
0x18004e676  push    r14
0x18004e678  push    r15
0x18004e67a  sub     rsp, 68h
0x18004e67e  mov     esi, [rsp+98h+arg_28]
0x18004e685  mov     r14d, r9d
0x18004e688  shr     esi, 1
0x18004e68a  mov     r12d, r8d
0x18004e68d  and     esi, 1
0x18004e690  mov     r15, rdx
0x18004e693  cmp     [rsp+98h+arg_28], 1
0x18004e69b  mov     rdi, rcx
0x18004e69e  jnz     short loc_18004E6EF
0x18004e6a0  mov     rax, [rcx+48h]
0x18004e6a4  mov     rcx, [rax]
0x18004e6a7  mov     ecx, [rcx+30h]; enum tagNETCON_MEDIATYPE
0x18004e6aa  call    ?IsMediaRASType@@YAHW4tagNETCON_MEDIATYPE@@@Z; IsMediaRASType(tagNETCON_MEDIATYPE)
0x18004e6af  test    eax, eax
0x18004e6b1  jz      short loc_18004E6EF
0x18004e6b3  xor     r9d, r9d; int
0x18004e6b6  mov     r8d, 222h; unsigned int
0x18004e6bc  call    ?FCheckGroupMembershipInternal@@YAHEKKH@Z; FCheckGroupMembershipInternal(uchar,ulong,ulong,int)
0x18004e6c1  test    eax, eax
0x18004e6c3  jz      short loc_18004E6EF
0x18004e6c5  mov     rcx, cs:hInst; hModule
0x18004e6cc  mov     r9d, 449h; unsigned int
0x18004e6d2  xor     edx, edx; hWnd
0x18004e6d4  mov     [rsp+98h+uIDAdjustMax], 30h ; '0'; uType
0x18004e6dc  lea     r8d, [r9-25h]; unsigned int
0x18004e6e0  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18004e6e5  mov     eax, 80004005h
0x18004e6ea  jmp     loc_18004E7B5
0x18004e6ef  mov     rax, [rdi+50h]
0x18004e6f3  xor     ebx, ebx
0x18004e6f5  cmp     rax, [rdi+48h]
0x18004e6f9  jz      loc_18004E7B3
0x18004e6ff  test    [rsp+98h+arg_28], 10000h
0x18004e70a  jnz     loc_18004E7B3
0x18004e710  call    cs:__imp_CreateMenu
0x18004e716  mov     [rsp+98h+hmSrc], rax
0x18004e71b  test    rax, rax
0x18004e71e  jz      loc_18004E7B3
0x18004e724  lea     r8, [rdi+48h]
0x18004e728  mov     edx, esi
0x18004e72a  lea     rcx, [rsp+98h+hmSrc]
0x18004e72f  call    ?HrBuildMenu@@YAJAEAPEAUHMENU__@@HAEAV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@K@Z; HrBuildMenu(HMENU__ * &,int,std::vector<CPConFoldPidl<ConFoldPidl_v3>> &,ulong)
0x18004e734  mov     ebx, eax
0x18004e736  test    eax, eax
0x18004e738  js      short loc_18004E7A8
0x18004e73a  xorps   xmm0, xmm0
0x18004e73d  mov     qword ptr [rsp+98h+var_60+1Ch], 0
0x18004e746  lea     rdx, [rsp+98h+var_60]; LPCMENUINFO
0x18004e74b  mov     dword ptr [rsp+98h+var_60.dwMenuData+4], 0
0x18004e753  mov     rcx, r15; HMENU
0x18004e756  mov     [rsp+98h+var_60.cbSize], 28h ; '('
0x18004e75e  movdqu  xmmword ptr [rsp+98h+var_60.cyMax], xmm0
0x18004e764  mov     [rsp+98h+var_60.fMask], 10h
0x18004e76c  mov     [rsp+98h+var_60.dwStyle], 4000000h
0x18004e774  call    cs:__imp_SetMenuInfo
0x18004e77a  mov     eax, [rsp+98h+arg_20]
0x18004e781  mov     r9d, r14d; uIDAdjust
0x18004e784  mov     rdx, [rsp+98h+hmSrc]; hmSrc
0x18004e789  mov     r8d, r12d; uInsert
0x18004e78c  mov     rcx, r15; hmDst
0x18004e78f  mov     [rsp+98h+uFlags], 3; uFlags
0x18004e797  mov     [rsp+98h+uIDAdjustMax], eax; uIDAdjustMax
0x18004e79b  call    cs:__imp_Shell_MergeMenus
0x18004e7a1  sub     ax, r14w
0x18004e7a5  movzx   ebx, ax
0x18004e7a8  mov     rcx, [rsp+98h+hmSrc]; hMenu
0x18004e7ad  call    cs:__imp_DestroyMenu
0x18004e7b3  mov     eax, ebx
0x18004e7b5  add     rsp, 68h
0x18004e7b9  pop     r15
0x18004e7bb  pop     r14
0x18004e7bd  pop     r12
0x18004e7bf  pop     rdi
0x18004e7c0  pop     rsi
0x18004e7c1  pop     rbx
0x18004e7c2  retn
```
