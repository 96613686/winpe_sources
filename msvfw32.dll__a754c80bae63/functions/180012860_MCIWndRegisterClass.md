# MCIWndRegisterClass

- ea: `0x180012860`
- end: `0x18001292d`
- name: `MCIWndRegisterClass`
- size: `205`
- prototype: `BOOL __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010730`

## callees

- `0x180001d62`
- `0x180012860`

## import_xrefs

- `COMCTL32!__imp_InitCommonControls` at `0x180012913`
- `COMCTL32!__imp_InitCommonControls` at `0x180012913`
- `USER32!RegisterClassW` at `0x180012908`
- `USER32!RegisterClassW` at `0x180012908`
- `USER32!GetClassInfoW` at `0x18001289a`
- `USER32!GetClassInfoW` at `0x18001289a`
- `USER32!UnregisterClassW` at `0x1800128b9`
- `USER32!UnregisterClassW` at `0x1800128b9`
- `USER32!LoadCursorW` at `0x1800128dc`
- `USER32!LoadCursorW` at `0x1800128dc`

## pseudocode

```c
BOOL __cdecl MCIWndRegisterClass()
{
  HINSTANCE v0; // rbx
  HCURSOR CursorW; // rax
  tagWNDCLASSW WndClass; // [rsp+20h] [rbp-50h] BYREF

  *(&WndClass.style + 1) = 0;
  memset_0(&WndClass, 0, 0x44u);
  v0 = ghInst;
  if ( GetClassInfoW(ghInst, aszMCIWndClassName, &WndClass) )
  {
    if ( (__int64 (__fastcall *)(HWND, UINT, unsigned __int64, unsigned int *))WndClass.lpfnWndProc == MCIWndProc )
      return 1;
    UnregisterClassW(aszMCIWndClassName, v0);
  }
  hInst = v0;
  WndClass.lpszClassName = aszMCIWndClassName;
  WndClass.lpfnWndProc = (WNDPROC)MCIWndProc;
  WndClass.style = 16427;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hIcon = 0;
  WndClass.hCursor = CursorW;
  WndClass.lpszMenuName = 0;
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.hInstance = v0;
  WndClass.cbClsExtra = 0;
  WndClass.cbWndExtra = 8;
  if ( RegisterClassW(&WndClass) )
  {
    InitCommonControls();
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012860  push    rbp
0x180012862  push    rbx
0x180012863  push    rsi
0x180012864  push    rdi
0x180012865  push    r14
0x180012867  mov     rbp, rsp
0x18001286a  sub     rsp, 70h
0x18001286e  xor     eax, eax
0x180012870  lea     rcx, [rbp+WndClass]; void *
0x180012874  xor     edx, edx; Val
0x180012876  mov     dword ptr [rbp+WndClass+4], eax
0x180012879  lea     r8d, [rax+44h]; Size
0x18001287d  call    memset_0
0x180012882  mov     rbx, cs:ghInst
0x180012889  lea     rsi, aszMCIWndClassName; "MCIWndClass"
0x180012890  mov     rdx, rsi; lpClassName
0x180012893  lea     r8, [rbp+WndClass]; lpWndClass
0x180012897  mov     rcx, rbx; hInstance
0x18001289a  call    cs:__imp_GetClassInfoW
0x1800128a0  xor     edi, edi
0x1800128a2  lea     r14, MCIWndProc
0x1800128a9  test    eax, eax
0x1800128ab  jz      short loc_1800128BF
0x1800128ad  cmp     [rbp+WndClass.lpfnWndProc], r14
0x1800128b1  jz      short loc_180012919
0x1800128b3  mov     rdx, rbx; hInstance
0x1800128b6  mov     rcx, rsi; lpClassName
0x1800128b9  call    cs:__imp_UnregisterClassW
0x1800128bf  mov     edx, 7F00h; lpCursorName
0x1800128c4  mov     cs:hInst, rbx
0x1800128cb  xor     ecx, ecx; hInstance
0x1800128cd  mov     [rbp+WndClass.lpszClassName], rsi
0x1800128d1  mov     [rbp+WndClass.lpfnWndProc], r14
0x1800128d5  mov     [rbp+WndClass.style], 402Bh
0x1800128dc  call    cs:__imp_LoadCursorW
0x1800128e2  lea     rcx, [rbp+WndClass]; lpWndClass
0x1800128e6  mov     [rbp+WndClass.hIcon], rdi
0x1800128ea  mov     [rbp+WndClass.hCursor], rax
0x1800128ee  mov     [rbp+WndClass.lpszMenuName], rdi
0x1800128f2  mov     [rbp+WndClass.hbrBackground], 6
0x1800128fa  mov     [rbp+WndClass.hInstance], rbx
0x1800128fe  mov     [rbp+WndClass.cbClsExtra], edi
0x180012901  mov     [rbp+WndClass.cbWndExtra], 8
0x180012908  call    cs:__imp_RegisterClassW
0x18001290e  test    ax, ax
0x180012911  jz      short loc_180012920
0x180012913  call    cs:__imp_InitCommonControls
0x180012919  mov     eax, 1
0x18001291e  jmp     short loc_180012922
0x180012920  xor     eax, eax
0x180012922  add     rsp, 70h
0x180012926  pop     r14
0x180012928  pop     rdi
0x180012929  pop     rsi
0x18001292a  pop     rbx
0x18001292b  pop     rbp
0x18001292c  retn
```
