# Combo<Device>::GetSelectedLParam(Device * *)

- ea: `0x18000cd08`
- end: `0x18000cd7c`
- name: `?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(HWND *, LRESULT *)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d338`
- `0x18000d67c`
- `0x18000d7dc`
- `0x18000d9a0`
- `0x18000dc0c`
- `0x18000dcdc`
- `0x18000de80`
- `0x18000dfe4`
- `0x18000e094`
- `0x18000e144`
- `0x18000e3fc`
- `0x18000e558`
- `0x18000e7ac`

## callees

- `0x18000cd08`

## import_xrefs

- `USER32!SendMessageW` at `0x18000cd39`
- `USER32!SendMessageW` at `0x18000cd52`
- `USER32!SendMessageW` at `0x18000cd39`
- `USER32!SendMessageW` at `0x18000cd52`

## pseudocode

```c
__int64 __fastcall Combo<Device>::GetSelectedLParam(HWND *a1, LRESULT *a2)
{
  HWND v5; // rcx
  int v6; // eax
  LRESULT v7; // rax

  if ( !a2 )
    return 2147942487LL;
  v5 = *a1;
  *a2 = 0;
  v6 = SendMessageW(v5, 0x147u, 0, 0);
  if ( v6 == -1 )
    return 1;
  v7 = SendMessageW(*a1, 0x150u, v6, 0);
  if ( v7 == -1 )
    return 2147500037LL;
  *a2 = v7;
  return 0;
}

```

## disassembly

```asm
0x18000cd08  mov     [rsp+arg_0], rbx
0x18000cd0d  push    rdi
0x18000cd0e  sub     rsp, 20h
0x18000cd12  mov     rbx, rdx
0x18000cd15  mov     rdi, rcx
0x18000cd18  test    rdx, rdx
0x18000cd1b  jnz     short loc_18000CD24
0x18000cd1d  mov     eax, 80070057h
0x18000cd22  jmp     short loc_18000CD71
0x18000cd24  mov     rcx, [rcx]; hWnd
0x18000cd27  xor     r9d, r9d; lParam
0x18000cd2a  mov     qword ptr [rdx], 0
0x18000cd31  xor     r8d, r8d; wParam
0x18000cd34  mov     edx, 147h; Msg
0x18000cd39  call    cs:__imp_SendMessageW
0x18000cd3f  cmp     eax, 0FFFFFFFFh
0x18000cd42  jz      short loc_18000CD6C
0x18000cd44  mov     rcx, [rdi]; hWnd
0x18000cd47  xor     r9d, r9d; lParam
0x18000cd4a  movsxd  r8, eax; wParam
0x18000cd4d  mov     edx, 150h; Msg
0x18000cd52  call    cs:__imp_SendMessageW
0x18000cd58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cd5c  jnz     short loc_18000CD65
0x18000cd5e  mov     eax, 80004005h
0x18000cd63  jmp     short loc_18000CD71
0x18000cd65  mov     [rbx], rax
0x18000cd68  xor     eax, eax
0x18000cd6a  jmp     short loc_18000CD71
0x18000cd6c  mov     eax, 1
0x18000cd71  mov     rbx, [rsp+28h+arg_0]
0x18000cd76  add     rsp, 20h
0x18000cd7a  pop     rdi
0x18000cd7b  retn
```
