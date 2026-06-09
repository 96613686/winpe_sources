# SHFusionCreateWindowEx

- ea: `0x14001c010`
- end: `0x14001c0be`
- name: `SHFusionCreateWindowEx`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014f60`

## callees

- `0x14001bf00`
- `0x14001bf68`
- `0x14001c010`
- `0x14001c234`

## import_xrefs

- `USER32!CreateWindowExW` at `0x14001c09f`
- `USER32!CreateWindowExW` at `0x14001c09f`

## pseudocode

```c
HWND SHFusionCreateWindowEx()
{
  HINSTANCE hInstance; // rbx
  HWND Window; // rbx
  ULONG_PTR ulCookie; // [rsp+80h] [rbp+18h] BYREF

  hInstance = g_hInstance;
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  if ( g_hActCtx != -3 )
    DelayLoadCC();
  Window = CreateWindowExW(8u, L"tooltips_class32", 0, 0x80000042, 0, 0, 0, 0, 0, 0, hInstance, 0);
  SHDeactivateContext(ulCookie);
  return Window;
}

```

## disassembly

```asm
0x14001c010  mov     rax, rsp
0x14001c013  mov     [rax+18h], r8
0x14001c017  push    rbx
0x14001c018  sub     rsp, 60h
0x14001c01c  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14001c023  lea     rcx, [rax+18h]
0x14001c027  mov     qword ptr [rax+18h], 0
0x14001c02f  call    SHActivateContext
0x14001c034  test    eax, eax
0x14001c036  jnz     short loc_14001C03C
0x14001c038  xor     eax, eax
0x14001c03a  jmp     short loc_14001C0B8
0x14001c03c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x14001c044  jz      short loc_14001C04B
0x14001c046  call    DelayLoadCC
0x14001c04b  mov     [rsp+68h+lpParam], 0; lpParam
0x14001c054  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x14001c05b  mov     [rsp+68h+hInstance], rbx; hInstance
0x14001c060  xor     r8d, r8d; lpWindowName
0x14001c063  mov     [rsp+68h+hMenu], 0; hMenu
0x14001c06c  mov     r9d, 80000042h; dwStyle
0x14001c072  mov     [rsp+68h+hWndParent], 0; hWndParent
0x14001c07b  mov     [rsp+68h+nHeight], 0; nHeight
0x14001c083  mov     [rsp+68h+nWidth], 0; nWidth
0x14001c08b  lea     ecx, [r8+8]; dwExStyle
0x14001c08f  mov     [rsp+68h+Y], 0; Y
0x14001c097  mov     [rsp+68h+X], 0; X
0x14001c09f  call    cs:__imp_CreateWindowExW
0x14001c0a5  mov     rcx, [rsp+68h+ulCookie]; ulCookie
0x14001c0ad  mov     rbx, rax
0x14001c0b0  call    SHDeactivateContext
0x14001c0b5  mov     rax, rbx
0x14001c0b8  add     rsp, 60h
0x14001c0bc  pop     rbx
0x14001c0bd  retn
```
