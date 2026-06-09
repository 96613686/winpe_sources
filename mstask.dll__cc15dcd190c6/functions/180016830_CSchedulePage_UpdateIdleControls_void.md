# CSchedulePage::_UpdateIdleControls(void)

- ea: `0x180016830`
- end: `0x18001689e`
- name: `?_UpdateIdleControls@CSchedulePage@@AEAAXXZ`
- size: `110`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800159c0`
- `0x180015db8`

## callees

- `0x180016830`
- `0x18001b010`

## import_xrefs

- `USER32!SendDlgItemMessageW` at `0x180016892`
- `USER32!SendDlgItemMessageW` at `0x180016892`

## pseudocode

```c
void __fastcall CSchedulePage::_UpdateIdleControls(CSchedulePage *this)
{
  unsigned __int16 v2; // ax
  __int16 v3; // [rsp+40h] [rbp+8h] BYREF
  __int16 v4; // [rsp+48h] [rbp+10h] BYREF

  v3 = 0;
  v4 = 0;
  (*(void (__fastcall **)(_QWORD, __int16 *, __int16 *))(**((_QWORD **)this + 83) + 88LL))(
    *((_QWORD *)this + 83),
    &v3,
    &v4);
  v2 = v3;
  if ( (unsigned __int16)v3 > 0x3E7u )
  {
    v2 = 999;
    v3 = 999;
  }
  SendDlgItemMessageW(*((HWND *)this + 14), 1767, 0x467u, 0, v2);
}

```

## disassembly

```asm
0x180016830  push    rbx
0x180016832  sub     rsp, 30h
0x180016836  xor     eax, eax
0x180016838  lea     r8, [rsp+38h+arg_8]
0x18001683d  mov     [rsp+38h+arg_0], ax
0x180016842  lea     rdx, [rsp+38h+arg_0]
0x180016847  mov     [rsp+38h+arg_8], ax
0x18001684c  mov     rbx, rcx
0x18001684f  mov     rcx, [rcx+298h]
0x180016856  mov     rax, [rcx]
0x180016859  mov     rax, [rax+58h]
0x18001685d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016862  movzx   eax, [rsp+38h+arg_0]
0x180016867  mov     ecx, 3E7h
0x18001686c  cmp     ax, cx
0x18001686f  jbe     short loc_180016878
0x180016871  mov     eax, ecx
0x180016873  mov     [rsp+38h+arg_0], cx
0x180016878  mov     rcx, [rbx+70h]; hDlg
0x18001687c  xor     r9d, r9d; wParam
0x18001687f  movzx   eax, ax
0x180016882  mov     edx, 6E7h; nIDDlgItem
0x180016887  mov     r8d, 467h; Msg
0x18001688d  mov     [rsp+38h+lParam], rax; lParam
0x180016892  call    cs:__imp_SendDlgItemMessageW
0x180016898  add     rsp, 30h
0x18001689c  pop     rbx
0x18001689d  retn
```
