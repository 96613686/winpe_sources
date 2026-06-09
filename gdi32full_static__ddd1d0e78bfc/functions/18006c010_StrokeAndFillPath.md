# StrokeAndFillPath

- ea: `0x18006c010`
- end: `0x18006c0da`
- name: `StrokeAndFillPath`
- size: `202`
- prototype: `BOOL __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180097500`

## callees

- `0x18002b708`
- `0x18002bea8`
- `0x18006c010`

## import_xrefs

- `GDI32!StartPage` at `0x18006c0c9`
- `GDI32!StartPage` at `0x18006c0c9`
- `GDI32!pldcGet` at `0x18006c060`
- `GDI32!pldcGet` at `0x18006c060`
- `GDI32!GdiSetLastError` at `0x18006c094`
- `GDI32!GdiSetLastError` at `0x18006c094`
- `win32u!NtGdiStrokeAndFillPath` at `0x18006c041`
- `win32u!NtGdiStrokeAndFillPath` at `0x18006c041`

## pseudocode

```c
BOOL __stdcall StrokeAndFillPath(HDC hdc)
{
  __int64 v3; // rax
  __int64 v4; // rbx

  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    goto LABEL_2;
  if ( ((unsigned int)hdc & 0x7F0000) != 0x660000 )
  {
    v3 = pldcGet(hdc);
    v4 = v3;
    if ( v3 )
    {
      if ( *(_DWORD *)(v3 + 12) != 2 || (unsigned int)MF_BoundRecord(hdc, 63) )
      {
        if ( (*(_BYTE *)(v4 + 8) & 0x20) != 0 )
          vSAPCallback(v4);
        if ( (*(_DWORD *)(v4 + 8) & 0x10000) == 0 )
        {
          if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 )
            StartPage(hdc);
LABEL_2:
          LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
          return NtGdiStrokeAndFillPath(hdc);
        }
      }
    }
    else
    {
      GdiSetLastError(6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006c010  mov     [rsp+arg_0], rbx
0x18006c015  push    rdi
0x18006c016  sub     rsp, 20h
0x18006c01a  mov     eax, ecx
0x18006c01c  mov     rdi, rcx
0x18006c01f  and     eax, 7F0000h
0x18006c024  cmp     eax, 10000h
0x18006c029  jnz     short loc_18006C059
0x18006c02b  mov     rax, gs:30h
0x18006c034  mov     rcx, rdi
0x18006c037  mov     dword ptr [rax+808h], 0
0x18006c041  call    cs:__imp_NtGdiStrokeAndFillPath
0x18006c048  nop     dword ptr [rax+rax+00h]
0x18006c04d  mov     rbx, [rsp+28h+arg_0]
0x18006c052  add     rsp, 20h
0x18006c056  pop     rdi
0x18006c057  retn
0x18006c059  cmp     eax, 660000h
0x18006c05e  jz      short loc_18006C08B
0x18006c060  call    cs:__imp_pldcGet
0x18006c067  nop     dword ptr [rax+rax+00h]
0x18006c06c  mov     rbx, rax
0x18006c06f  test    rax, rax
0x18006c072  jz      short loc_18006C08F
0x18006c074  cmp     dword ptr [rax+0Ch], 2
0x18006c078  jnz     short loc_18006C0A2
0x18006c07a  mov     edx, 3Fh ; '?'
0x18006c07f  mov     rcx, rdi
0x18006c082  call    MF_BoundRecord
0x18006c087  test    eax, eax
0x18006c089  jnz     short loc_18006C0A2
0x18006c08b  xor     eax, eax
0x18006c08d  jmp     short loc_18006C04D
0x18006c08f  mov     ecx, 6
0x18006c094  call    cs:__imp_GdiSetLastError
0x18006c09b  nop     dword ptr [rax+rax+00h]
0x18006c0a0  jmp     short loc_18006C08B
0x18006c0a2  test    byte ptr [rbx+8], 20h
0x18006c0a6  jz      short loc_18006C0B0
0x18006c0a8  mov     rcx, rbx
0x18006c0ab  call    vSAPCallback
0x18006c0b0  test    dword ptr [rbx+8], 10000h
0x18006c0b7  jnz     short loc_18006C08B
0x18006c0b9  test    dword ptr [rbx+8], 100h
0x18006c0c0  jz      loc_18006C02B
0x18006c0c6  mov     rcx, rdi; hdc
0x18006c0c9  call    cs:__imp_StartPage
0x18006c0d0  nop     dword ptr [rax+rax+00h]
0x18006c0d5  jmp     loc_18006C02B
```
