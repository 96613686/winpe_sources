# CSpellContextHandler::CreateLanguageSubmenu(void)

- ea: `0x180278d34`
- end: `0x180278e79`
- name: `?CreateLanguageSubmenu@CSpellContextHandler@@AEAAPEAUHMENU__@@XZ`
- size: `325`
- prototype: `HMENU __fastcall(CSpellContextHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180279718`

## callees

- `0x180278d34`
- `0x180279a4c`
- `0x180279c28`
- `0x180279c98`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x180278d9d`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x180278d9d`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x180278de2`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x180278e57`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x180278de2`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x180278e57`

## pseudocode

```c
HMENU __fastcall CSpellContextHandler::CreateLanguageSubmenu(CSpellContextHandler *this, __int64 a2)
{
  HMENU v3; // rbx
  __int64 v4; // rcx
  HMENU PopupMenu; // rdi
  __int64 v6; // r9
  __int64 v7; // rcx
  bool inserted; // al
  UINT v9; // edx
  bool v10; // al
  unsigned int v11; // r8d
  bool v12; // al
  unsigned int v14; // [rsp+40h] [rbp+8h] BYREF
  int v15; // [rsp+48h] [rbp+10h] BYREF

  LOBYTE(a2) = 1;
  v3 = (HMENU)(*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 232LL))(
                *(_QWORD *)(*((_QWORD *)this + 3) + 72LL),
                a2);
  if ( v3 )
  {
    v4 = *((_QWORD *)this + 3);
    v14 = 0;
    if ( (*(int (__fastcall **)(_QWORD, HMENU, unsigned int *, _QWORD))(**(_QWORD **)(v4 + 72) + 264LL))(
           *(_QWORD *)(v4 + 72),
           v3,
           &v14,
           0) < 0 )
      goto LABEL_9;
    PopupMenu = CreatePopupMenu();
    if ( PopupMenu )
    {
      v7 = *((_QWORD *)this + 3);
      v15 = 0;
      LOBYTE(v6) = 1;
      if ( (*(int (__fastcall **)(_QWORD, HMENU, int *, __int64))(**(_QWORD **)(v7 + 72) + 264LL))(
             *(_QWORD *)(v7 + 72),
             PopupMenu,
             &v15,
             v6) < 0 )
      {
        DestroyMenu(PopupMenu);
        PopupMenu = 0;
      }
    }
    inserted = CSpellContextHandler::InsertSubMenuFromResource(this, v3, v14, *((_DWORD *)this + 32), PopupMenu);
    v9 = ++v14;
    if ( !inserted
      || (v10 = CSpellContextHandler::InsertSeparator(v3, v9), v11 = v14 + 1, ++v14, !v10)
      || (v12 = CSpellContextHandler::InsertMenuItemFromResource(
                  this,
                  v3,
                  v11,
                  *((_DWORD *)this + 33),
                  *((_DWORD *)this + 23)),
          ++v14,
          !v12) )
    {
LABEL_9:
      DestroyMenu(v3);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180278d34  mov     [rsp+arg_10], rbx
0x180278d39  mov     [rsp+arg_18], rsi
0x180278d3e  push    rdi
0x180278d3f  sub     rsp, 30h
0x180278d43  mov     rax, [rcx+18h]
0x180278d47  mov     rsi, rcx
0x180278d4a  mov     dl, 1
0x180278d4c  mov     rcx, [rax+48h]
0x180278d50  mov     rax, [rcx]
0x180278d53  mov     rax, [rax+0E8h]
0x180278d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278d5f  mov     rbx, rax
0x180278d62  test    rax, rax
0x180278d65  jz      loc_180278E65
0x180278d6b  mov     rcx, [rsi+18h]
0x180278d6f  lea     r8, [rsp+38h+arg_0]
0x180278d74  mov     [rsp+38h+arg_0], 0
0x180278d7c  xor     r9d, r9d
0x180278d7f  mov     rcx, [rcx+48h]
0x180278d83  mov     rdx, [rcx]
0x180278d86  mov     rax, [rdx+108h]
0x180278d8d  mov     rdx, rbx
0x180278d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278d95  test    eax, eax
0x180278d97  js      loc_180278E54
0x180278d9d  call    cs:__imp_CreatePopupMenu
0x180278da4  nop     dword ptr [rax+rax+00h]
0x180278da9  mov     rdi, rax
0x180278dac  test    rax, rax
0x180278daf  jz      short loc_180278DF0
0x180278db1  mov     rcx, [rsi+18h]
0x180278db5  lea     r8, [rsp+38h+arg_8]
0x180278dba  mov     [rsp+38h+arg_8], 0
0x180278dc2  mov     r9b, 1
0x180278dc5  mov     rcx, [rcx+48h]
0x180278dc9  mov     rdx, [rcx]
0x180278dcc  mov     rax, [rdx+108h]
0x180278dd3  mov     rdx, rdi
0x180278dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278ddb  test    eax, eax
0x180278ddd  jns     short loc_180278DF0
0x180278ddf  mov     rcx, rdi; hMenu
0x180278de2  call    cs:__imp_DestroyMenu
0x180278de9  nop     dword ptr [rax+rax+00h]
0x180278dee  xor     edi, edi
0x180278df0  mov     r9d, [rsi+80h]; unsigned int
0x180278df7  mov     rdx, rbx; HMENU
0x180278dfa  mov     r8d, [rsp+38h+arg_0]; unsigned int
0x180278dff  mov     rcx, rsi; this
0x180278e02  mov     [rsp+38h+var_18], rdi; HMENU
0x180278e07  call    ?InsertSubMenuFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@II0@Z; CSpellContextHandler::InsertSubMenuFromResource(HMENU__ *,uint,uint,HMENU__ *)
0x180278e0c  mov     edx, [rsp+38h+arg_0]
0x180278e10  inc     edx; item
0x180278e12  mov     [rsp+38h+arg_0], edx
0x180278e16  test    al, al
0x180278e18  jz      short loc_180278E54
0x180278e1a  mov     rcx, rbx; hmenu
0x180278e1d  call    ?InsertSeparator@CSpellContextHandler@@CA_NPEAUHMENU__@@I@Z; CSpellContextHandler::InsertSeparator(HMENU__ *,uint)
0x180278e22  mov     r8d, [rsp+38h+arg_0]
0x180278e27  inc     r8d; unsigned int
0x180278e2a  mov     [rsp+38h+arg_0], r8d
0x180278e2f  test    al, al
0x180278e31  jz      short loc_180278E54
0x180278e33  mov     eax, [rsi+5Ch]
0x180278e36  mov     rdx, rbx; HMENU
0x180278e39  mov     r9d, [rsi+84h]; unsigned int
0x180278e40  mov     rcx, rsi; this
0x180278e43  mov     dword ptr [rsp+38h+var_18], eax; unsigned int
0x180278e47  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180278e4c  inc     [rsp+38h+arg_0]
0x180278e50  test    al, al
0x180278e52  jnz     short loc_180278E65
0x180278e54  mov     rcx, rbx; hMenu
0x180278e57  call    cs:__imp_DestroyMenu
0x180278e5e  nop     dword ptr [rax+rax+00h]
0x180278e63  xor     ebx, ebx
0x180278e65  mov     rsi, [rsp+38h+arg_18]
0x180278e6a  mov     rax, rbx
0x180278e6d  mov     rbx, [rsp+38h+arg_10]
0x180278e72  add     rsp, 30h
0x180278e76  pop     rdi
0x180278e77  retn
```
