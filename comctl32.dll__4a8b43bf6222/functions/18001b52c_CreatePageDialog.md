# _CreatePageDialog

- ea: `0x18001b52c`
- end: `0x18001b5df`
- name: `_CreatePageDialog`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b410`

## callees

- `0x18001af4c`
- `0x18001b398`
- `0x18001b52c`

## import_xrefs

- `KERNEL32!CheckForReadOnlyResource` at `0x18008f4e6`
- `KERNEL32!CheckForReadOnlyResource` at `0x18008f4e6`
- `USER32!CreateDialogIndirectParamA` at `0x18001b59b`
- `USER32!CreateDialogIndirectParamA` at `0x18001b59b`
- `USER32!CreateDialogIndirectParamW` at `0x18001b5b3`
- `USER32!CreateDialogIndirectParamW` at `0x18001b5b3`
- `USER32!DestroyWindow` at `0x18008f50d`
- `USER32!DestroyWindow` at `0x18008f50d`

## pseudocode

```c
__int64 __fastcall CreatePageDialog(__int64 a1, __int64 a2, HWND a3, const DLGTEMPLATE *a4)
{
  __int64 result; // rax
  _DWORD *v8; // rsi
  INT_PTR (__stdcall *v9)(HWND, UINT, WPARAM, LPARAM); // r9
  __int64 v10; // rcx
  LPARAM dwInitParam; // rax
  bool v12; // zf
  HINSTANCE v13; // rcx
  HWND DialogIndirectParamW; // rdi
  int v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  result = EditPropSheetTemplate(a4, &v15, *(unsigned int *)(a1 + 152));
  v8 = (_DWORD *)result;
  if ( result )
  {
    v9 = *(INT_PTR (__stdcall **)(HWND, UINT, WPARAM, LPARAM))(a2 + 104);
    v10 = *(_QWORD *)(a2 + 56);
    if ( v10 )
    {
      dwInitParam = v10 + 64;
    }
    else
    {
      dwInitParam = a2 + 48;
      if ( (*(_DWORD *)(a2 + 68) & 0x200) == 0 )
        dwInitParam = a2 + 64;
    }
    v12 = v10 == 0;
    v13 = *(HINSTANCE *)(a2 + 72);
    if ( v12 )
    {
      DialogIndirectParamW = CreateDialogIndirectParamW(v13, a4, a3, v9, dwInitParam);
    }
    else
    {
      DialogIndirectParamW = CreateDialogIndirectParamA(v13, a4, a3, v9, dwInitParam);
      RethunkShadowStrings(a2);
    }
    if ( *v8 != v15 )
      *v8 = v15;
    return (__int64)DialogIndirectParamW;
  }
  return result;
}

```

## disassembly

```asm
0x18001b52c  push    rbx
0x18001b52e  push    rsi
0x18001b52f  push    rdi
0x18001b530  push    r14
0x18001b532  sub     rsp, 48h
0x18001b536  mov     rdi, r9
0x18001b539  mov     r14, r8
0x18001b53c  mov     rbx, rdx
0x18001b53f  mov     [rsp+68h+arg_0], 0
0x18001b547  mov     r8d, [rcx+98h]
0x18001b54e  lea     rdx, [rsp+68h+arg_0]
0x18001b553  mov     rcx, r9
0x18001b556  call    EditPropSheetTemplate
0x18001b55b  mov     rsi, rax
0x18001b55e  test    rax, rax
0x18001b561  jz      short loc_18001B5D5
0x18001b563  mov     r9, [rbx+68h]; lpDialogFunc
0x18001b567  mov     rcx, [rbx+38h]
0x18001b56b  test    rcx, rcx
0x18001b56e  jz      short loc_18001B576
0x18001b570  lea     rax, [rcx+40h]
0x18001b574  jmp     short loc_18001B587
0x18001b576  test    dword ptr [rbx+44h], 200h
0x18001b57d  lea     rax, [rbx+30h]
0x18001b581  jnz     short loc_18001B587
0x18001b583  lea     rax, [rbx+40h]
0x18001b587  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x18001b58c  mov     r8, r14; hWndParent
0x18001b58f  mov     rdx, rdi; lpTemplate
0x18001b592  test    rcx, rcx
0x18001b595  mov     rcx, [rbx+48h]; hInstance
0x18001b599  jz      short loc_18001B5B3
0x18001b59b  call    cs:__imp_CreateDialogIndirectParamA
0x18001b5a1  mov     rdi, rax
0x18001b5a4  mov     [rsp+68h+var_38], rax
0x18001b5a9  mov     rcx, rbx
0x18001b5ac  call    RethunkShadowStrings
0x18001b5b1  jmp     short loc_18001B5C1
0x18001b5b3  call    cs:__imp_CreateDialogIndirectParamW
0x18001b5b9  mov     rdi, rax
0x18001b5bc  mov     [rsp+68h+var_38], rax
0x18001b5c1  mov     eax, [rsp+68h+arg_0]
0x18001b5c5  cmp     [rsi], eax
0x18001b5c7  jz      short loc_18001B5CB
0x18001b5c9  mov     [rsi], eax
0x18001b5cb  jmp     short loc_18001B5D2
0x18001b5cd  mov     rdi, [rsp+68h+var_38]
0x18001b5d2  mov     rax, rdi
0x18001b5d5  add     rsp, 48h
0x18001b5d9  pop     r14
0x18001b5db  pop     rdi
0x18001b5dc  pop     rsi
0x18001b5dd  pop     rbx
0x18001b5de  retn
0x18008f4d8  push    rbp
0x18008f4da  sub     rsp, 30h
0x18008f4de  mov     rbp, rdx
0x18008f4e1  mov     edx, 1
0x18008f4e6  call    cs:__imp_CheckForReadOnlyResource
0x18008f4ec  nop
0x18008f4ed  add     rsp, 30h
0x18008f4f1  pop     rbp
0x18008f4f2  retn
0x18008f4f4  push    rbp
0x18008f4f6  sub     rsp, 30h
0x18008f4fa  mov     rbp, rdx
0x18008f4fd  movzx   eax, cl
0x18008f500  test    cl, cl
0x18008f502  jz      short loc_18008F514
0x18008f504  mov     rcx, [rbp+30h]; hWnd
0x18008f508  test    rcx, rcx
0x18008f50b  jz      short loc_18008F514
0x18008f50d  call    cs:__imp_DestroyWindow
0x18008f513  nop
0x18008f514  add     rsp, 30h
0x18008f518  pop     rbp
0x18008f519  retn
```
