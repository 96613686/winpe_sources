# GetScreenMetrics

- ea: `0x18006721c`
- end: `0x180067281`
- name: `GetScreenMetrics`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180068120`
- `0x18006a80c`

## callees

- `0x18006721c`

## import_xrefs

- `GDI32!DeleteDC` at `0x18006726e`
- `GDI32!DeleteDC` at `0x18006726e`
- `GDI32!CreateICA` at `0x18006723a`
- `GDI32!CreateICA` at `0x18006723a`
- `GDI32!GetDeviceCaps` at `0x18006724b`
- `GDI32!GetDeviceCaps` at `0x18006725f`
- `GDI32!GetDeviceCaps` at `0x18006724b`
- `GDI32!GetDeviceCaps` at `0x18006725f`

## pseudocode

```c
void GetScreenMetrics()
{
  HDC ICA; // rbx

  if ( !byte_18008C1A4 )
  {
    ICA = CreateICA("DISPLAY", 0, 0, 0);
    dword_18008C38C = GetDeviceCaps(ICA, 88);
    dword_18008C3A4 = GetDeviceCaps(ICA, 90);
    DeleteDC(ICA);
    byte_18008C1A4 = 1;
  }
}

```

## disassembly

```asm
0x18006721c  push    rbx
0x18006721e  sub     rsp, 20h
0x180067222  cmp     cs:byte_18008C1A4, 0
0x180067229  jnz     short loc_18006727B
0x18006722b  xor     r9d, r9d; pdm
0x18006722e  lea     rcx, pszDriver; "DISPLAY"
0x180067235  xor     r8d, r8d; pszPort
0x180067238  xor     edx, edx; pszDevice
0x18006723a  call    cs:__imp_CreateICA
0x180067240  mov     rcx, rax; hdc
0x180067243  mov     edx, 58h ; 'X'; index
0x180067248  mov     rbx, rax
0x18006724b  call    cs:__imp_GetDeviceCaps
0x180067251  mov     edx, 5Ah ; 'Z'; index
0x180067256  mov     rcx, rbx; hdc
0x180067259  mov     cs:dword_18008C38C, eax
0x18006725f  call    cs:__imp_GetDeviceCaps
0x180067265  mov     rcx, rbx; hdc
0x180067268  mov     cs:dword_18008C3A4, eax
0x18006726e  call    cs:__imp_DeleteDC
0x180067274  mov     cs:byte_18008C1A4, 1
0x18006727b  add     rsp, 20h
0x18006727f  pop     rbx
0x180067280  retn
```
