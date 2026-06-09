# _SHPrettyMenu(HMENU__ *)

- ea: `0x18000fed0`
- end: `0x18000ff89`
- name: `?_SHPrettyMenu@@YAXPEAUHMENU__@@@Z`
- size: `185`
- prototype: `void __fastcall(HMENU hmenu)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e710`
- `0x180026300`

## callees

- `0x18000fe28`
- `0x18000fed0`

## import_xrefs

- `USER32!GetMenuItemCount` at `0x18000fee5`
- `USER32!GetMenuItemCount` at `0x18000fee5`
- `USER32!DeleteMenu` at `0x18000ff24`
- `USER32!DeleteMenu` at `0x18000ff3c`
- `USER32!DeleteMenu` at `0x18000ff68`
- `USER32!DeleteMenu` at `0x18000ff24`
- `USER32!DeleteMenu` at `0x18000ff3c`
- `USER32!DeleteMenu` at `0x18000ff68`

## pseudocode

```c
void __fastcall _SHPrettyMenu(HMENU hmenu)
{
  int v1; // esi
  int v3; // r14d
  signed int i; // ebx
  HMENU v5; // rcx
  int v6; // [rsp+58h] [rbp+10h] BYREF

  v1 = 1;
  v3 = 1;
  for ( i = GetMenuItemCount(hmenu) - 1; ; --i )
  {
    v5 = hmenu;
    if ( i <= 0 )
      break;
    v6 = 0;
    if ( (unsigned int)_SHIsMenuSeparator2(hmenu, i, &v6) )
    {
      if ( v1 )
      {
        if ( !v6 || v3 )
        {
          DeleteMenu(hmenu, i, 0x400u);
        }
        else
        {
          DeleteMenu(hmenu, i + 1, 0x400u);
          v3 = v6;
        }
      }
      else
      {
        v3 = v6;
        v1 = 1;
      }
    }
    else
    {
      v1 = 0;
    }
  }
  while ( (unsigned int)_SHIsMenuSeparator2(v5, 0, 0) )
  {
    DeleteMenu(hmenu, 0, 0x400u);
    v5 = hmenu;
  }
}

```

## disassembly

```asm
0x18000fed0  push    rbx
0x18000fed2  push    rsi
0x18000fed3  push    rdi
0x18000fed4  push    r14
0x18000fed6  sub     rsp, 28h
0x18000feda  mov     esi, 1
0x18000fedf  mov     rdi, rcx
0x18000fee2  mov     r14d, esi
0x18000fee5  call    cs:__imp_GetMenuItemCount
0x18000feeb  lea     ebx, [rax-1]
0x18000feee  jmp     short loc_18000FF54
0x18000fef0  lea     r8, [rsp+48h+arg_8]; int *
0x18000fef5  mov     [rsp+48h+arg_8], 0
0x18000fefd  mov     edx, ebx; item
0x18000feff  call    ?_SHIsMenuSeparator2@@YAHPEAUHMENU__@@HPEAH@Z; _SHIsMenuSeparator2(HMENU__ *,int,int *)
0x18000ff04  test    eax, eax
0x18000ff06  jz      short loc_18000FF50
0x18000ff08  test    esi, esi
0x18000ff0a  jz      short loc_18000FF44
0x18000ff0c  cmp     [rsp+48h+arg_8], 0
0x18000ff11  jz      short loc_18000FF31
0x18000ff13  test    r14d, r14d
0x18000ff16  jnz     short loc_18000FF31
0x18000ff18  lea     edx, [rbx+1]; uPosition
0x18000ff1b  mov     r8d, 400h; uFlags
0x18000ff21  mov     rcx, rdi; hMenu
0x18000ff24  call    cs:__imp_DeleteMenu
0x18000ff2a  mov     r14d, [rsp+48h+arg_8]
0x18000ff2f  jmp     short loc_18000FF52
0x18000ff31  mov     r8d, 400h; uFlags
0x18000ff37  mov     edx, ebx; uPosition
0x18000ff39  mov     rcx, rdi; hMenu
0x18000ff3c  call    cs:__imp_DeleteMenu
0x18000ff42  jmp     short loc_18000FF52
0x18000ff44  mov     r14d, [rsp+48h+arg_8]
0x18000ff49  mov     esi, 1
0x18000ff4e  jmp     short loc_18000FF52
0x18000ff50  xor     esi, esi
0x18000ff52  dec     ebx
0x18000ff54  mov     rcx, rdi; hmenu
0x18000ff57  test    ebx, ebx
0x18000ff59  jg      short loc_18000FEF0
0x18000ff5b  jmp     short loc_18000FF71
0x18000ff5d  xor     edx, edx; uPosition
0x18000ff5f  mov     r8d, 400h; uFlags
0x18000ff65  mov     rcx, rdi; hMenu
0x18000ff68  call    cs:__imp_DeleteMenu
0x18000ff6e  mov     rcx, rdi; hmenu
0x18000ff71  xor     r8d, r8d; int *
0x18000ff74  xor     edx, edx; item
0x18000ff76  call    ?_SHIsMenuSeparator2@@YAHPEAUHMENU__@@HPEAH@Z; _SHIsMenuSeparator2(HMENU__ *,int,int *)
0x18000ff7b  test    eax, eax
0x18000ff7d  jnz     short loc_18000FF5D
0x18000ff7f  add     rsp, 28h
0x18000ff83  pop     r14
0x18000ff85  pop     rdi
0x18000ff86  pop     rsi
0x18000ff87  pop     rbx
0x18000ff88  retn
```
