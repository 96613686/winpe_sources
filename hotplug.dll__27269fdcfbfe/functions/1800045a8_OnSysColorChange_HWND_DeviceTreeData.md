# OnSysColorChange(HWND__ *,_DeviceTreeData *)

- ea: `0x1800045a8`
- end: `0x18000465b`
- name: `?OnSysColorChange@@YAXPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `179`
- prototype: `void __fastcall(HWND, struct _DeviceTreeData *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003d70`
- `0x180004114`

## callees

- `0x1800045a8`

## import_xrefs

- `USER32!GetSysColor` at `0x1800045bf`
- `USER32!GetSysColor` at `0x1800045cc`
- `USER32!GetSysColor` at `0x1800045d9`
- `USER32!GetSysColor` at `0x1800045bf`
- `USER32!GetSysColor` at `0x1800045cc`
- `USER32!GetSysColor` at `0x1800045d9`
- `COMCTL32!ImageList_SetBkColor` at `0x180004645`
- `COMCTL32!ImageList_SetBkColor` at `0x180004645`

## pseudocode

```c
void __fastcall OnSysColorChange(HWND a1, struct _DeviceTreeData *a2)
{
  DWORD SysColor; // esi
  DWORD v4; // ebx
  struct _IMAGELIST *v5; // rcx

  SysColor = GetSysColor(5);
  v4 = GetSysColor(13);
  RemovalTextColor = GetSysColor(8);
  NormalImageBkColor = SysColor;
  v5 = (struct _IMAGELIST *)*((_QWORD *)a2 + 11);
  RemovalImageBkColor = (((unsigned __int8)SysColor + (unsigned int)(unsigned __int8)v4) >> 1)
                      | ((BYTE2(SysColor) + BYTE2(v4)) << 15) & 0xFFFF0000
                      | ((unsigned int)(BYTE1(SysColor) + BYTE1(v4)) >> 1 << 8);
  if ( v5 )
    ImageList_SetBkColor(v5, SysColor);
}

```

## disassembly

```asm
0x1800045a8  mov     [rsp+arg_0], rbx
0x1800045ad  mov     [rsp+arg_8], rsi
0x1800045b2  push    rdi
0x1800045b3  sub     rsp, 20h
0x1800045b7  mov     ecx, 5; nIndex
0x1800045bc  mov     rdi, rdx
0x1800045bf  call    cs:__imp_GetSysColor
0x1800045c5  mov     ecx, 0Dh; nIndex
0x1800045ca  mov     esi, eax
0x1800045cc  call    cs:__imp_GetSysColor
0x1800045d2  mov     ecx, 8; nIndex
0x1800045d7  mov     ebx, eax
0x1800045d9  call    cs:__imp_GetSysColor
0x1800045df  mov     r9d, eax
0x1800045e2  movzx   ecx, si
0x1800045e5  shr     ecx, 8
0x1800045e8  movzx   r8d, bx
0x1800045ec  shr     r8d, 8
0x1800045f0  add     r8d, ecx
0x1800045f3  mov     cs:?RemovalTextColor@@3KA, r9d; ulong RemovalTextColor
0x1800045fa  shr     r8d, 1
0x1800045fd  mov     ecx, ebx
0x1800045ff  shr     ecx, 10h
0x180004602  movzx   edx, cl
0x180004605  mov     ecx, esi
0x180004607  shr     ecx, 10h
0x18000460a  movzx   eax, cl
0x18000460d  add     edx, eax
0x18000460f  shl     r8d, 8
0x180004613  shl     edx, 0Fh
0x180004616  movzx   ecx, bl
0x180004619  and     edx, 0FFFF0000h
0x18000461f  or      r8d, edx
0x180004622  movzx   eax, sil
0x180004626  add     ecx, eax
0x180004628  mov     cs:?NormalImageBkColor@@3KA, esi; ulong NormalImageBkColor
0x18000462e  shr     ecx, 1
0x180004630  or      r8d, ecx
0x180004633  mov     rcx, [rdi+58h]; himl
0x180004637  mov     cs:?RemovalImageBkColor@@3KA, r8d; ulong RemovalImageBkColor
0x18000463e  test    rcx, rcx
0x180004641  jz      short loc_18000464B
0x180004643  mov     edx, esi; clrBk
0x180004645  call    cs:__imp_ImageList_SetBkColor
0x18000464b  mov     rbx, [rsp+28h+arg_0]
0x180004650  mov     rsi, [rsp+28h+arg_8]
0x180004655  add     rsp, 20h
0x180004659  pop     rdi
0x18000465a  retn
```
