# HrUpdateMenu(HMENU__ * &,std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> &,ulong)

- ea: `0x18004deb8`
- end: `0x18004dfd0`
- name: `?HrUpdateMenu@@YAJAEAPEAUHMENU__@@AEAV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@K@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018d90`

## callees

- `0x18004d3c8`
- `0x18004d464`
- `0x18004deb8`
- `0x18004e140`

## import_xrefs

- `USER32!RemoveMenu` at `0x18004df5b`
- `USER32!RemoveMenu` at `0x18004df5b`
- `USER32!GetMenuItemCount` at `0x18004dee5`
- `USER32!GetMenuItemCount` at `0x18004dee5`
- `USER32!GetMenuItemID` at `0x18004defc`
- `USER32!GetMenuItemID` at `0x18004defc`
- `USER32!CheckMenuItem` at `0x18004dfad`
- `USER32!CheckMenuItem` at `0x18004dfad`
- `USER32!EnableMenuItem` at `0x18004df76`
- `USER32!EnableMenuItem` at `0x18004df76`

## pseudocode

```c
__int64 __fastcall HrUpdateMenu(HMENU *a1, int a2, unsigned int a3)
{
  HMENU v5; // rcx
  unsigned int v8; // esi
  signed int v9; // ebx
  int MenuItemCount; // ebp
  UINT MenuItemID; // eax
  unsigned int v12; // esi
  __int64 v13; // rcx
  HMENU v14; // rcx
  UINT v15; // r8d
  int v16; // [rsp+60h] [rbp+8h] BYREF
  int v17; // [rsp+78h] [rbp+20h] BYREF

  v5 = *a1;
  if ( !v5 )
    return 2147942487LL;
  v8 = 0;
  v9 = 0;
  MenuItemCount = GetMenuItemCount(v5);
  if ( MenuItemCount > 0 )
  {
    do
    {
      MenuItemID = GetMenuItemID(*a1, v9);
      v16 = 0;
      v17 = 0;
      v12 = NCCMDFromSFV(MenuItemID, a3) - a3;
      if ( (int)HrGetCommandState(a2, v12, (unsigned int)&v16, (unsigned int)&v17, -1, 4096) >= 0 )
      {
        v14 = *a1;
        if ( v16 == 3 )
          RemoveMenu(v14, v9, 0x400u);
        else
          EnableMenuItem(v14, v9, (v16 != 1) + 1024);
      }
      v16 = 0;
      v8 = HrGetCheckState(v13, v12, &v16);
      if ( !v8 )
      {
        v15 = 1024;
        if ( v16 == 1 )
          v15 = 1032;
        CheckMenuItem(*a1, v9, v15);
      }
      ++v9;
    }
    while ( v9 < MenuItemCount );
  }
  return v8;
}

```

## disassembly

```asm
0x18004deb8  mov     [rsp+arg_8], rbx
0x18004debd  push    rbp
0x18004debe  push    rsi
0x18004debf  push    rdi
0x18004dec0  push    r14
0x18004dec2  push    r15
0x18004dec4  sub     rsp, 30h
0x18004dec8  mov     rdi, rcx
0x18004decb  mov     r14d, r8d
0x18004dece  mov     rcx, [rcx]; hMenu
0x18004ded1  mov     r15, rdx
0x18004ded4  test    rcx, rcx
0x18004ded7  jnz     short loc_18004DEE3
0x18004ded9  mov     eax, 80070057h
0x18004dede  jmp     loc_18004DFBF
0x18004dee3  xor     esi, esi
0x18004dee5  call    cs:__imp_GetMenuItemCount
0x18004deeb  xor     ebx, ebx
0x18004deed  mov     ebp, eax
0x18004deef  test    eax, eax
0x18004def1  jle     loc_18004DFBD
0x18004def7  mov     rcx, [rdi]; hMenu
0x18004defa  mov     edx, ebx; nPos
0x18004defc  call    cs:__imp_GetMenuItemID
0x18004df02  mov     edx, r14d; unsigned int
0x18004df05  mov     [rsp+58h+arg_0], 0
0x18004df0d  mov     ecx, eax; int
0x18004df0f  mov     [rsp+58h+arg_18], 0
0x18004df17  call    ?NCCMDFromSFV@@YAHHK@Z; NCCMDFromSFV(int,ulong)
0x18004df1c  mov     esi, eax
0x18004df1e  mov     [rsp+58h+var_30], 1000h
0x18004df26  sub     esi, r14d
0x18004df29  mov     [rsp+58h+var_38], 0FFFFFFFFh
0x18004df31  mov     edx, esi
0x18004df33  lea     r9, [rsp+58h+arg_18]
0x18004df38  lea     r8, [rsp+58h+arg_0]
0x18004df3d  mov     rcx, r15
0x18004df40  call    ?HrGetCommandState@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@KAEAW4tagNCCS_STATE@@PEAKKK@Z; HrGetCommandState(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,ulong,tagNCCS_STATE &,ulong *,ulong,ulong)
0x18004df45  test    eax, eax
0x18004df47  js      short loc_18004DF7C
0x18004df49  cmp     [rsp+58h+arg_0], 3
0x18004df4e  mov     edx, ebx; uIDEnableItem
0x18004df50  mov     rcx, [rdi]; hMenu
0x18004df53  jnz     short loc_18004DF63
0x18004df55  mov     r8d, 400h; uFlags
0x18004df5b  call    cs:__imp_RemoveMenu
0x18004df61  jmp     short loc_18004DF7C
0x18004df63  xor     r8d, r8d
0x18004df66  cmp     [rsp+58h+arg_0], 1
0x18004df6b  setnz   r8b
0x18004df6f  add     r8d, 400h; uEnable
0x18004df76  call    cs:__imp_EnableMenuItem
0x18004df7c  lea     r8, [rsp+58h+arg_0]
0x18004df81  mov     [rsp+58h+arg_0], 0
0x18004df89  mov     edx, esi
0x18004df8b  call    ?HrGetCheckState@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@KAEAW4tagNCCS_CHECKED_STATE@@@Z; HrGetCheckState(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,ulong,tagNCCS_CHECKED_STATE &)
0x18004df90  mov     esi, eax
0x18004df92  test    eax, eax
0x18004df94  jnz     short loc_18004DFB3
0x18004df96  cmp     [rsp+58h+arg_0], 1
0x18004df9b  mov     eax, 408h
0x18004dfa0  mov     rcx, [rdi]; hMenu
0x18004dfa3  mov     edx, ebx; uIDCheckItem
0x18004dfa5  lea     r8d, [rax-8]
0x18004dfa9  cmovz   r8d, eax; uCheck
0x18004dfad  call    cs:__imp_CheckMenuItem
0x18004dfb3  inc     ebx
0x18004dfb5  cmp     ebx, ebp
0x18004dfb7  jl      loc_18004DEF7
0x18004dfbd  mov     eax, esi
0x18004dfbf  mov     rbx, [rsp+58h+arg_8]
0x18004dfc4  add     rsp, 30h
0x18004dfc8  pop     r15
0x18004dfca  pop     r14
0x18004dfcc  pop     rdi
0x18004dfcd  pop     rsi
0x18004dfce  pop     rbp
0x18004dfcf  retn
```
