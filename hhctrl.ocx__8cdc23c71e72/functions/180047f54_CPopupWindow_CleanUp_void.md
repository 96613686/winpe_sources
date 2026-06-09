# CPopupWindow::CleanUp(void)

- ea: `0x180047f54`
- end: `0x180047ff4`
- name: `?CleanUp@CPopupWindow@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(CPopupWindow *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180047ffc`
- `0x180048b54`

## callees

- `0x180006708`
- `0x180013b6c`
- `0x180047f54`
- `0x180078010`

## import_xrefs

- `msvcrt!free` at `0x180047f8a`
- `msvcrt!free` at `0x180047fc9`
- `msvcrt!free` at `0x180047f8a`
- `msvcrt!free` at `0x180047fc9`
- `USER32!DestroyWindow` at `0x180047f6e`
- `USER32!DestroyWindow` at `0x180047f6e`
- `GDI32!DeleteObject` at `0x180047fa1`
- `GDI32!DeleteObject` at `0x180047fa1`

## pseudocode

```c
void __fastcall CPopupWindow::CleanUp(HWND *this)
{
  unsigned int v2; // edx
  HWND v3; // rcx
  HWND v4; // rcx
  void (__fastcall ***v5)(_QWORD, _QWORD); // rcx
  HWND v6; // rcx

  if ( (unsigned int)IsValidWindow(this[6]) )
    DestroyWindow(this[6]);
  if ( *this )
    CFSClient::`scalar deleting destructor'((CFSClient *)*this, v2);
  v3 = this[7];
  if ( v3 )
  {
    free(v3);
    this[7] = 0;
  }
  v4 = this[8];
  if ( v4 )
    DeleteObject(v4);
  v5 = (void (__fastcall ***)(_QWORD, _QWORD))this[11];
  if ( v5 )
    (**v5)(v5, 1);
  v6 = this[12];
  if ( v6 )
  {
    free(v6);
    this[12] = 0;
  }
  *this = 0;
  this[11] = 0;
  this[8] = 0;
}

```

## disassembly

```asm
0x180047f54  push    rbx
0x180047f56  sub     rsp, 20h
0x180047f5a  mov     rbx, rcx
0x180047f5d  mov     rcx, [rcx+30h]; HWND
0x180047f61  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180047f66  test    eax, eax
0x180047f68  jz      short loc_180047F74
0x180047f6a  mov     rcx, [rbx+30h]; hWnd
0x180047f6e  call    cs:__imp_DestroyWindow
0x180047f74  mov     rcx, [rbx]; this
0x180047f77  test    rcx, rcx
0x180047f7a  jz      short loc_180047F81
0x180047f7c  call    ??_GCFSClient@@QEAAPEAXI@Z; CFSClient::`scalar deleting destructor'(uint)
0x180047f81  mov     rcx, [rbx+38h]; Block
0x180047f85  test    rcx, rcx
0x180047f88  jz      short loc_180047F98
0x180047f8a  call    cs:__imp_free
0x180047f90  mov     qword ptr [rbx+38h], 0
0x180047f98  mov     rcx, [rbx+40h]; ho
0x180047f9c  test    rcx, rcx
0x180047f9f  jz      short loc_180047FA7
0x180047fa1  call    cs:__imp_DeleteObject
0x180047fa7  mov     rcx, [rbx+58h]
0x180047fab  test    rcx, rcx
0x180047fae  jz      short loc_180047FC0
0x180047fb0  mov     rax, [rcx]
0x180047fb3  mov     edx, 1
0x180047fb8  mov     rax, [rax]
0x180047fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fc0  mov     rcx, [rbx+60h]; Block
0x180047fc4  test    rcx, rcx
0x180047fc7  jz      short loc_180047FD7
0x180047fc9  call    cs:__imp_free
0x180047fcf  mov     qword ptr [rbx+60h], 0
0x180047fd7  mov     qword ptr [rbx], 0
0x180047fde  mov     qword ptr [rbx+58h], 0
0x180047fe6  mov     qword ptr [rbx+40h], 0
0x180047fee  add     rsp, 20h
0x180047ff2  pop     rbx
0x180047ff3  retn
```
