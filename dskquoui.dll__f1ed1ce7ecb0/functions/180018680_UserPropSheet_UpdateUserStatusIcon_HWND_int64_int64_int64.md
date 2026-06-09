# UserPropSheet::UpdateUserStatusIcon(HWND__ *,__int64,__int64,__int64)

- ea: `0x180018680`
- end: `0x1800186e0`
- name: `?UpdateUserStatusIcon@UserPropSheet@@AEAAXPEAUHWND__@@_J11@Z`
- size: `96`
- prototype: `void(UserPropSheet *__hidden this, HWND, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800170dc`
- `0x1800177fc`

## callees

- `0x180018680`

## import_xrefs

- `USER32!SendMessageW` at `0x1800186d9`
- `USER32!GetDlgItem` at `0x1800186c0`
- `USER32!GetDlgItem` at `0x1800186c0`

## pseudocode

```c
void __fastcall UserPropSheet::UpdateUserStatusIcon(UserPropSheet *this, HWND a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rbx
  WPARAM v6; // rbx
  HWND DlgItem; // rax

  if ( a5 == -1 || a3 <= a5 )
  {
    v5 = 0;
    if ( a4 != -1 )
      v5 = a3 > a4;
  }
  else
  {
    v5 = 2;
  }
  v6 = *((_QWORD *)this + v5 + 21);
  DlgItem = GetDlgItem(a2, 1044);
  SendMessageW(DlgItem, 0x170u, v6, 0);
}

```

## disassembly

```asm
0x180018680  push    rbx
0x180018682  sub     rsp, 20h
0x180018686  cmp     [rsp+28h+arg_20], 0FFFFFFFFFFFFFFFFh
0x18001868c  mov     rax, rdx
0x18001868f  jz      short loc_18001869F
0x180018691  cmp     r8, [rsp+28h+arg_20]
0x180018696  jle     short loc_18001869F
0x180018698  mov     ebx, 2
0x18001869d  jmp     short loc_1800186B0
0x18001869f  xor     ebx, ebx
0x1800186a1  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800186a5  jz      short loc_1800186B0
0x1800186a7  cmp     r8, r9
0x1800186aa  lea     edx, [rbx+1]
0x1800186ad  cmovg   ebx, edx
0x1800186b0  mov     rbx, [rcx+rbx*8+0A8h]
0x1800186b8  mov     edx, 414h; nIDDlgItem
0x1800186bd  mov     rcx, rax; hDlg
0x1800186c0  call    cs:__imp_GetDlgItem
0x1800186c6  xor     r9d, r9d
0x1800186c9  mov     r8, rbx
0x1800186cc  mov     rcx, rax
0x1800186cf  mov     edx, 170h
0x1800186d4  add     rsp, 20h
0x1800186d8  pop     rbx
0x1800186d9  jmp     cs:__imp_SendMessageW
```
