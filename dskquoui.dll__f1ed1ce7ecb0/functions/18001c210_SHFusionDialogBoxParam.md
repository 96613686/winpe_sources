# SHFusionDialogBoxParam

- ea: `0x18001c210`
- end: `0x18001c28f`
- name: `SHFusionDialogBoxParam`
- size: `127`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCWSTR lpTemplateName, HWND hWndParent, DLGPROC lpDialogFunc, LPARAM)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b8fc`
- `0x18000c8c4`
- `0x18000d5f8`
- `0x18000de10`

## callees

- `0x18001c0c4`
- `0x18001c210`
- `0x18001c888`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001c27d`
- `KERNEL32!DeactivateActCtx` at `0x18001c27d`
- `USER32!DialogBoxParamW` at `0x18001c268`
- `USER32!DialogBoxParamW` at `0x18001c268`

## pseudocode

```c
INT_PTR __fastcall SHFusionDialogBoxParam(
        HINSTANCE hInstance,
        LPCWSTR lpTemplateName,
        HWND hWndParent,
        DLGPROC lpDialogFunc,
        LPARAM dwInitParam)
{
  INT_PTR v10; // rbx
  ULONG_PTR ulCookie[7]; // [rsp+30h] [rbp-38h] BYREF

  ulCookie[0] = 0;
  if ( !(unsigned int)SHActivateContext(ulCookie) )
    return 0;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  v10 = DialogBoxParamW(hInstance, lpTemplateName, hWndParent, lpDialogFunc, dwInitParam);
  if ( ulCookie[0] )
    DeactivateActCtx(0, ulCookie[0]);
  return v10;
}

```

## disassembly

```asm
0x18001c210  push    rbx
0x18001c212  push    rbp
0x18001c213  push    rsi
0x18001c214  push    rdi
0x18001c215  sub     rsp, 48h
0x18001c219  mov     rbp, rcx
0x18001c21c  mov     [rsp+68h+ulCookie], 0
0x18001c225  lea     rcx, [rsp+68h+ulCookie]
0x18001c22a  mov     rbx, r9
0x18001c22d  mov     rdi, r8
0x18001c230  mov     rsi, rdx
0x18001c233  call    SHActivateContext
0x18001c238  test    eax, eax
0x18001c23a  jnz     short loc_18001C240
0x18001c23c  xor     eax, eax
0x18001c23e  jmp     short loc_18001C286
0x18001c240  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18001c248  jz      short loc_18001C24F
0x18001c24a  call    DelayLoadCC
0x18001c24f  mov     rax, [rsp+68h+arg_20]
0x18001c257  mov     r9, rbx; lpDialogFunc
0x18001c25a  mov     r8, rdi; hWndParent
0x18001c25d  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x18001c262  mov     rdx, rsi; lpTemplateName
0x18001c265  mov     rcx, rbp; hInstance
0x18001c268  call    cs:__imp_DialogBoxParamW
0x18001c26e  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18001c273  mov     rbx, rax
0x18001c276  test    rdx, rdx
0x18001c279  jz      short loc_18001C283
0x18001c27b  xor     ecx, ecx; dwFlags
0x18001c27d  call    cs:__imp_DeactivateActCtx
0x18001c283  mov     rax, rbx
0x18001c286  add     rsp, 48h
0x18001c28a  pop     rdi
0x18001c28b  pop     rsi
0x18001c28c  pop     rbp
0x18001c28d  pop     rbx
0x18001c28e  retn
```
