# StrokeAndFillPath

- ea: `0x180067850`
- end: `0x180067901`
- name: `StrokeAndFillPath`
- size: `177`
- prototype: `BOOL __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180091960`

## callees

- `0x180022898`
- `0x180022f88`
- `0x180067850`

## import_xrefs

- `GDI32!StartPage` at `0x1800678f6`
- `GDI32!StartPage` at `0x1800678f6`
- `GDI32!pldcGet` at `0x180067899`
- `GDI32!pldcGet` at `0x180067899`
- `GDI32!GdiSetLastError` at `0x1800678c7`
- `GDI32!GdiSetLastError` at `0x1800678c7`
- `win32u!NtGdiStrokeAndFillPath` at `0x180067881`
- `win32u!NtGdiStrokeAndFillPath` at `0x180067881`

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
0x180067850  mov     [rsp+arg_0], rbx
0x180067855  push    rdi
0x180067856  sub     rsp, 20h
0x18006785a  mov     eax, ecx
0x18006785c  mov     rdi, rcx
0x18006785f  and     eax, 7F0000h
0x180067864  cmp     eax, 10000h
0x180067869  jnz     short loc_180067892
0x18006786b  mov     rax, gs:30h
0x180067874  mov     rcx, rdi
0x180067877  mov     dword ptr [rax+808h], 0
0x180067881  call    cs:__imp_NtGdiStrokeAndFillPath
0x180067887  mov     rbx, [rsp+28h+arg_0]
0x18006788c  add     rsp, 20h
0x180067890  pop     rdi
0x180067891  retn
0x180067892  cmp     eax, 660000h
0x180067897  jz      short loc_1800678BE
0x180067899  call    cs:__imp_pldcGet
0x18006789f  mov     rbx, rax
0x1800678a2  test    rax, rax
0x1800678a5  jz      short loc_1800678C2
0x1800678a7  cmp     dword ptr [rax+0Ch], 2
0x1800678ab  jnz     short loc_1800678CF
0x1800678ad  mov     edx, 3Fh ; '?'
0x1800678b2  mov     rcx, rdi
0x1800678b5  call    MF_BoundRecord
0x1800678ba  test    eax, eax
0x1800678bc  jnz     short loc_1800678CF
0x1800678be  xor     eax, eax
0x1800678c0  jmp     short loc_180067887
0x1800678c2  mov     ecx, 6
0x1800678c7  call    cs:__imp_GdiSetLastError
0x1800678cd  jmp     short loc_1800678BE
0x1800678cf  test    byte ptr [rbx+8], 20h
0x1800678d3  jz      short loc_1800678DD
0x1800678d5  mov     rcx, rbx
0x1800678d8  call    vSAPCallback
0x1800678dd  test    dword ptr [rbx+8], 10000h
0x1800678e4  jnz     short loc_1800678BE
0x1800678e6  test    dword ptr [rbx+8], 100h
0x1800678ed  jz      loc_18006786B
0x1800678f3  mov     rcx, rdi; hdc
0x1800678f6  call    cs:__imp_StartPage
0x1800678fc  jmp     loc_18006786B
```
