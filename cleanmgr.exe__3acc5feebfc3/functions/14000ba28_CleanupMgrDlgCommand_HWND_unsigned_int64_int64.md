# CleanupMgrDlgCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x14000ba28`
- end: `0x14000badb`
- name: `?CleanupMgrDlgCommand@@YAHPEAUHWND__@@_K_J@Z`
- size: `179`
- prototype: `__int64 __fastcall(HWND hWnd, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c910`

## callees

- `0x14000ba28`
- `0x14000dde4`
- `0x140018010`

## import_xrefs

- `USER32!GetParent` at `0x14000bab3`
- `USER32!GetParent` at `0x14000bab3`
- `USER32!GetDlgItem` at `0x14000ba42`
- `USER32!GetDlgItem` at `0x14000ba42`
- `USER32!SendMessageW` at `0x14000ba5d`
- `USER32!SendMessageW` at `0x14000ba5d`
- `USER32!PostMessageW` at `0x14000bac8`
- `USER32!PostMessageW` at `0x14000bac8`
- `USER32!GetWindowLongPtrW` at `0x14000ba9b`
- `USER32!GetWindowLongPtrW` at `0x14000ba9b`

## pseudocode

```c
__int64 __fastcall CleanupMgrDlgCommand(HWND hWnd, __int16 a2)
{
  HWND DlgItem; // rdi
  int v4; // eax
  __int64 ItemData; // rax
  LONG_PTR WindowLongPtrW; // rax
  HWND Parent; // rax

  if ( a2 == 1002 )
  {
    DlgItem = GetDlgItem(hWnd, 1000);
    v4 = SendMessageW(DlgItem, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
    if ( v4 != -1 )
    {
      ItemData = ListView_GetItemData(DlgItem, v4);
      if ( ItemData )
        (*(void (__fastcall **)(_QWORD, HWND))(**(_QWORD **)(ItemData + 24) + 48LL))(*(_QWORD *)(ItemData + 24), hWnd);
    }
  }
  else if ( a2 == 1004 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
    if ( WindowLongPtrW )
    {
      *(_DWORD *)(WindowLongPtrW + 1628) = 5;
      Parent = GetParent(hWnd);
      PostMessageW(Parent, 0x471u, 3u, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000ba28  mov     [rsp+arg_0], rbx
0x14000ba2d  push    rdi
0x14000ba2e  sub     rsp, 20h
0x14000ba32  mov     eax, 3EAh
0x14000ba37  mov     rbx, rcx
0x14000ba3a  cmp     ax, dx
0x14000ba3d  jnz     short loc_14000BA8C
0x14000ba3f  lea     edx, [rax-2]; nIDDlgItem
0x14000ba42  call    cs:__imp_GetDlgItem
0x14000ba48  mov     r9d, 2; lParam
0x14000ba4e  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x14000ba52  mov     rcx, rax; hWnd
0x14000ba55  mov     edx, 100Ch; Msg
0x14000ba5a  mov     rdi, rax
0x14000ba5d  call    cs:__imp_SendMessageW
0x14000ba63  cmp     eax, 0FFFFFFFFh
0x14000ba66  jz      short loc_14000BACE
0x14000ba68  mov     edx, eax; int
0x14000ba6a  mov     rcx, rdi; hWnd
0x14000ba6d  call    ?ListView_GetItemData@@YA_JPEAUHWND__@@H@Z; ListView_GetItemData(HWND__ *,int)
0x14000ba72  test    rax, rax
0x14000ba75  jz      short loc_14000BACE
0x14000ba77  mov     rcx, [rax+18h]
0x14000ba7b  mov     rdx, rbx
0x14000ba7e  mov     rax, [rcx]
0x14000ba81  mov     rax, [rax+30h]
0x14000ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba8a  jmp     short loc_14000BACE
0x14000ba8c  mov     eax, 3ECh
0x14000ba91  cmp     ax, dx
0x14000ba94  jnz     short loc_14000BACE
0x14000ba96  mov     edx, 10h; nIndex
0x14000ba9b  call    cs:__imp_GetWindowLongPtrW
0x14000baa1  test    rax, rax
0x14000baa4  jz      short loc_14000BACE
0x14000baa6  mov     rcx, rbx; hWnd
0x14000baa9  mov     dword ptr [rax+65Ch], 5
0x14000bab3  call    cs:__imp_GetParent
0x14000bab9  xor     r9d, r9d; lParam
0x14000babc  mov     edx, 471h; Msg
0x14000bac1  mov     rcx, rax; hWnd
0x14000bac4  lea     r8d, [r9+3]; wParam
0x14000bac8  call    cs:__imp_PostMessageW
0x14000bace  mov     rbx, [rsp+28h+arg_0]
0x14000bad3  xor     eax, eax
0x14000bad5  add     rsp, 20h
0x14000bad9  pop     rdi
0x14000bada  retn
```
