# Animate::~Animate(void)

- ea: `0x18000b0b4`
- end: `0x18000b140`
- name: `??1Animate@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(Animate *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b148`

## callees

- `0x18000b0b4`
- `0x18000bce4`

## import_xrefs

- `USER32!DestroyWindow` at `0x18000b119`
- `USER32!DestroyWindow` at `0x18000b119`
- `USER32!EnableWindow` at `0x18000b10a`
- `USER32!EnableWindow` at `0x18000b10a`
- `GDI32!DeleteObject` at `0x18000b0dd`
- `GDI32!DeleteObject` at `0x18000b0f4`
- `GDI32!DeleteObject` at `0x18000b0dd`
- `GDI32!DeleteObject` at `0x18000b0f4`
- `GDI32!DeleteDC` at `0x18000b0c6`
- `GDI32!DeleteDC` at `0x18000b0c6`

## pseudocode

```c
void __fastcall Animate::~Animate(Animate *this)
{
  HDC v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  HWND v5; // rcx

  v2 = (HDC)*((_QWORD *)this + 3);
  if ( v2 )
  {
    DeleteDC(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 4) = 0;
  }
  EnableWindow(*(HWND *)this, 1);
  v5 = (HWND)*((_QWORD *)this + 1);
  if ( v5 )
  {
    DestroyWindow(v5);
    *((_QWORD *)this + 1) = 0;
    IsolationAwareUnregisterClassA("Help_Animation", hInstance);
  }
}

```

## disassembly

```asm
0x18000b0b4  push    rbx
0x18000b0b6  sub     rsp, 20h
0x18000b0ba  mov     rbx, rcx
0x18000b0bd  mov     rcx, [rcx+18h]; hdc
0x18000b0c1  test    rcx, rcx
0x18000b0c4  jz      short loc_18000B0D4
0x18000b0c6  call    cs:__imp_DeleteDC
0x18000b0cc  mov     qword ptr [rbx+18h], 0
0x18000b0d4  mov     rcx, [rbx+10h]; ho
0x18000b0d8  test    rcx, rcx
0x18000b0db  jz      short loc_18000B0EB
0x18000b0dd  call    cs:__imp_DeleteObject
0x18000b0e3  mov     qword ptr [rbx+10h], 0
0x18000b0eb  mov     rcx, [rbx+20h]; ho
0x18000b0ef  test    rcx, rcx
0x18000b0f2  jz      short loc_18000B102
0x18000b0f4  call    cs:__imp_DeleteObject
0x18000b0fa  mov     qword ptr [rbx+20h], 0
0x18000b102  mov     rcx, [rbx]; hWnd
0x18000b105  mov     edx, 1; bEnable
0x18000b10a  call    cs:__imp_EnableWindow
0x18000b110  mov     rcx, [rbx+8]; hWnd
0x18000b114  test    rcx, rcx
0x18000b117  jz      short loc_18000B13A
0x18000b119  call    cs:__imp_DestroyWindow
0x18000b11f  mov     qword ptr [rbx+8], 0
0x18000b127  lea     rcx, aHelpAnimation; "Help_Animation"
0x18000b12e  mov     rdx, cs:hInstance; hInstance
0x18000b135  call    IsolationAwareUnregisterClassA
0x18000b13a  add     rsp, 20h
0x18000b13e  pop     rbx
0x18000b13f  retn
```
