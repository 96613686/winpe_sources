# CreateColorMenu(HMENU__ * *)

- ea: `0x1800861f4`
- end: `0x18008627d`
- name: `?CreateColorMenu@@YAJPEAPEAUHMENU__@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(HMENU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800856e0`

## callees

- `0x1800861f4`

## import_xrefs

- `USER32!LoadMenuA` at `0x180086225`
- `USER32!LoadMenuA` at `0x180086225`
- `USER32!GetSubMenu` at `0x180086238`
- `USER32!GetSubMenu` at `0x180086238`
- `USER32!RemoveMenu` at `0x18008624c`
- `USER32!RemoveMenu` at `0x18008624c`
- `USER32!DestroyMenu` at `0x180086255`
- `USER32!DestroyMenu` at `0x180086255`

## pseudocode

```c
__int64 __fastcall CreateColorMenu(HMENU *a1)
{
  HMENU MenuA; // rax
  HMENU v4; // rsi
  HMENU SubMenu; // rbx

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  MenuA = LoadMenuA(g_hLocRes, (LPCSTR)5);
  v4 = MenuA;
  if ( MenuA )
  {
    SubMenu = GetSubMenu(MenuA, 0);
    RemoveMenu(v4, 0, 0x400u);
    DestroyMenu(v4);
    *a1 = SubMenu;
  }
  return *a1 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800861f4  mov     [rsp+arg_0], rbx
0x1800861f9  mov     [rsp+arg_8], rsi
0x1800861fe  push    rdi
0x1800861ff  sub     rsp, 20h
0x180086203  mov     rdi, rcx
0x180086206  test    rcx, rcx
0x180086209  jnz     short loc_180086212
0x18008620b  mov     eax, 80070057h
0x180086210  jmp     short loc_18008626D
0x180086212  mov     qword ptr [rcx], 0
0x180086219  mov     edx, 5; lpMenuName
0x18008621e  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180086225  call    cs:__imp_LoadMenuA
0x18008622b  mov     rsi, rax
0x18008622e  test    rax, rax
0x180086231  jz      short loc_18008625E
0x180086233  xor     edx, edx; nPos
0x180086235  mov     rcx, rax; hMenu
0x180086238  call    cs:__imp_GetSubMenu
0x18008623e  xor     edx, edx; uPosition
0x180086240  mov     r8d, 400h; uFlags
0x180086246  mov     rcx, rsi; hMenu
0x180086249  mov     rbx, rax
0x18008624c  call    cs:__imp_RemoveMenu
0x180086252  mov     rcx, rsi; hMenu
0x180086255  call    cs:__imp_DestroyMenu
0x18008625b  mov     [rdi], rbx
0x18008625e  mov     rax, [rdi]
0x180086261  neg     rax
0x180086264  sbb     eax, eax
0x180086266  not     eax
0x180086268  and     eax, 80004005h
0x18008626d  mov     rbx, [rsp+28h+arg_0]
0x180086272  mov     rsi, [rsp+28h+arg_8]
0x180086277  add     rsp, 20h
0x18008627b  pop     rdi
0x18008627c  retn
```
