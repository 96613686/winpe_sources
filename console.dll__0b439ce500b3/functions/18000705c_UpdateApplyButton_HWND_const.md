# UpdateApplyButton(HWND__ * const)

- ea: `0x18000705c`
- end: `0x18000709b`
- name: `?UpdateApplyButton@@YAXQEAUHWND__@@@Z`
- size: `63`
- prototype: `void __fastcall(HWND wParam)`
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180009980`
- `0x18000b2e4`
- `0x18000bdf0`
- `0x18000cea0`
- `0x18000e15c`
- `0x18000e804`

## callees

- `0x18000705c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18000706e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18000706e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007088`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007088`

## pseudocode

```c
void __fastcall UpdateApplyButton(HWND wParam)
{
  HWND Parent; // rax

  if ( g_fHostedInFileProperties )
  {
    Parent = GetParent(wParam);
    SendMessageW(Parent, 0x468u, (WPARAM)wParam, 0);
  }
}

```

## disassembly

```asm
0x18000705c  push    rbx
0x18000705e  sub     rsp, 20h
0x180007062  cmp     cs:?g_fHostedInFileProperties@@3HA, 0; int g_fHostedInFileProperties
0x180007069  mov     rbx, rcx
0x18000706c  jz      short loc_180007094
0x18000706e  call    cs:__imp_GetParent
0x180007075  nop     dword ptr [rax+rax+00h]
0x18000707a  xor     r9d, r9d; lParam
0x18000707d  mov     r8, rbx; wParam
0x180007080  mov     rcx, rax; hWnd
0x180007083  mov     edx, 468h; Msg
0x180007088  call    cs:__imp_SendMessageW
0x18000708f  nop     dword ptr [rax+rax+00h]
0x180007094  add     rsp, 20h
0x180007098  pop     rbx
0x180007099  retn
```
