# SHFusionCreateDialogParam

- ea: `0x14001bf88`
- end: `0x14001c007`
- name: `SHFusionCreateDialogParam`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140017eec`
- `0x14001b0e0`

## callees

- `0x14001bf00`
- `0x14001bf68`
- `0x14001bf88`
- `0x14001c234`

## import_xrefs

- `USER32!CreateDialogParamW` at `0x14001bfe8`
- `USER32!CreateDialogParamW` at `0x14001bfe8`

## pseudocode

```c
HWND __fastcall SHFusionCreateDialogParam(
        __int64 a1,
        const WCHAR *a2,
        HWND a3,
        INT_PTR (__stdcall *a4)(HWND, UINT, WPARAM, LPARAM),
        LPARAM dwInitParam)
{
  HINSTANCE v5; // rbp
  HWND DialogParamW; // rbx
  ULONG_PTR ulCookie; // [rsp+60h] [rbp+8h] BYREF

  v5 = g_hInstance;
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  if ( g_hActCtx != -3 )
    DelayLoadCC();
  DialogParamW = CreateDialogParamW(v5, a2, a3, a4, dwInitParam);
  SHDeactivateContext(ulCookie);
  return DialogParamW;
}

```

## disassembly

```asm
0x14001bf88  mov     [rsp+ulCookie], rcx
0x14001bf8d  push    rbx
0x14001bf8e  push    rbp
0x14001bf8f  push    rsi
0x14001bf90  push    rdi
0x14001bf91  sub     rsp, 38h
0x14001bf95  mov     rbp, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14001bf9c  lea     rcx, [rsp+58h+ulCookie]
0x14001bfa1  mov     rbx, r9
0x14001bfa4  mov     [rsp+58h+ulCookie], 0
0x14001bfad  mov     rdi, r8
0x14001bfb0  mov     rsi, rdx
0x14001bfb3  call    SHActivateContext
0x14001bfb8  test    eax, eax
0x14001bfba  jnz     short loc_14001BFC0
0x14001bfbc  xor     eax, eax
0x14001bfbe  jmp     short loc_14001BFFE
0x14001bfc0  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x14001bfc8  jz      short loc_14001BFCF
0x14001bfca  call    DelayLoadCC
0x14001bfcf  mov     rax, [rsp+58h+arg_20]
0x14001bfd7  mov     r9, rbx; lpDialogFunc
0x14001bfda  mov     r8, rdi; hWndParent
0x14001bfdd  mov     [rsp+58h+dwInitParam], rax; dwInitParam
0x14001bfe2  mov     rdx, rsi; lpTemplateName
0x14001bfe5  mov     rcx, rbp; hInstance
0x14001bfe8  call    cs:__imp_CreateDialogParamW
0x14001bfee  mov     rcx, [rsp+58h+ulCookie]; ulCookie
0x14001bff3  mov     rbx, rax
0x14001bff6  call    SHDeactivateContext
0x14001bffb  mov     rax, rbx
0x14001bffe  add     rsp, 38h
0x14001c002  pop     rdi
0x14001c003  pop     rsi
0x14001c004  pop     rbp
0x14001c005  pop     rbx
0x14001c006  retn
```
