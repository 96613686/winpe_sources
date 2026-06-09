# CTxtWinHost::TxViewChange(int)

- ea: `0x180040f90`
- end: `0x180040fe2`
- name: `?TxViewChange@CTxtWinHost@@UEAAXH@Z`
- size: `82`
- prototype: `void __fastcall(CTxtWinHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180040f90`

## import_xrefs

- `USER32!GetParent` at `0x180040fb0`
- `USER32!GetParent` at `0x180040fb0`
- `USER32!UpdateWindow` at `0x180040fbf`
- `USER32!UpdateWindow` at `0x180040fcf`
- `USER32!UpdateWindow` at `0x180040fbf`
- `USER32!UpdateWindow` at `0x180040fcf`

## pseudocode

```c
void __fastcall CTxtWinHost::TxViewChange(HWND *this, int a2)
{
  HWND Parent; // rax

  if ( (*((_DWORD *)this + 13) & 0x200) != 0 && a2 )
  {
    if ( ((_BYTE)this[6] & 0x20) != 0 )
    {
      Parent = GetParent(this[2]);
      UpdateWindow(Parent);
    }
    UpdateWindow(this[2]);
  }
}

```

## disassembly

```asm
0x180040f90  push    rbx
0x180040f92  sub     rsp, 20h
0x180040f96  test    dword ptr [rcx+34h], 200h
0x180040f9d  mov     rbx, rcx
0x180040fa0  jz      short loc_180040FDB
0x180040fa2  test    edx, edx
0x180040fa4  jz      short loc_180040FDB
0x180040fa6  test    byte ptr [rcx+30h], 20h
0x180040faa  jz      short loc_180040FCB
0x180040fac  mov     rcx, [rcx+10h]; hWnd
0x180040fb0  call    cs:__imp_GetParent
0x180040fb7  nop     dword ptr [rax+rax+00h]
0x180040fbc  mov     rcx, rax; hWnd
0x180040fbf  call    cs:__imp_UpdateWindow
0x180040fc6  nop     dword ptr [rax+rax+00h]
0x180040fcb  mov     rcx, [rbx+10h]; hWnd
0x180040fcf  call    cs:__imp_UpdateWindow
0x180040fd6  nop     dword ptr [rax+rax+00h]
0x180040fdb  add     rsp, 20h
0x180040fdf  pop     rbx
0x180040fe0  retn
```
