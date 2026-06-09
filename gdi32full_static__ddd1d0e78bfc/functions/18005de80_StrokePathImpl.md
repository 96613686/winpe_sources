# StrokePathImpl

- ea: `0x18005de80`
- end: `0x18005df45`
- name: `StrokePathImpl`
- size: `197`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002b708`
- `0x18002bea8`
- `0x18005de80`

## import_xrefs

- `GDI32!StartPage` at `0x18005df37`
- `GDI32!StartPage` at `0x18005df37`
- `GDI32!pldcGet` at `0x18005dea6`
- `GDI32!pldcGet` at `0x18005dea6`
- `GDI32!GdiSetLastError` at `0x18005df24`
- `GDI32!GdiSetLastError` at `0x18005df24`
- `win32u!NtGdiStrokePath` at `0x18005df07`
- `win32u!NtGdiStrokePath` at `0x18005df07`

## pseudocode

```c
__int64 __fastcall StrokePathImpl(HDC hdc)
{
  __int64 v2; // rax
  __int64 v3; // rbx

  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    goto LABEL_11;
  if ( ((unsigned int)hdc & 0x7F0000) != 0x660000 )
  {
    v2 = pldcGet(hdc);
    v3 = v2;
    if ( v2 )
    {
      if ( *(_DWORD *)(v2 + 12) != 2 || (unsigned int)MF_BoundRecord(hdc, 64) )
      {
        if ( (*(_BYTE *)(v3 + 8) & 0x20) != 0 )
          vSAPCallback(v3);
        if ( (*(_DWORD *)(v3 + 8) & 0x10000) == 0 )
        {
          if ( (*(_DWORD *)(v3 + 8) & 0x100) != 0 )
            StartPage(hdc);
LABEL_11:
          LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
          return NtGdiStrokePath(hdc);
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
0x18005de80  mov     [rsp+arg_0], rbx
0x18005de85  push    rdi
0x18005de86  sub     rsp, 20h
0x18005de8a  mov     eax, ecx
0x18005de8c  mov     rdi, rcx
0x18005de8f  and     eax, 7F0000h
0x18005de94  cmp     eax, 10000h
0x18005de99  jz      short loc_18005DEF1
0x18005de9b  cmp     eax, 660000h
0x18005dea0  jz      loc_18005DF30
0x18005dea6  call    cs:__imp_pldcGet
0x18005dead  nop     dword ptr [rax+rax+00h]
0x18005deb2  mov     rbx, rax
0x18005deb5  test    rax, rax
0x18005deb8  jz      short loc_18005DF1F
0x18005deba  cmp     dword ptr [rax+0Ch], 2
0x18005debe  jnz     short loc_18005DED1
0x18005dec0  mov     edx, 40h ; '@'
0x18005dec5  mov     rcx, rdi
0x18005dec8  call    MF_BoundRecord
0x18005decd  test    eax, eax
0x18005decf  jz      short loc_18005DF30
0x18005ded1  test    byte ptr [rbx+8], 20h
0x18005ded5  jz      short loc_18005DEDF
0x18005ded7  mov     rcx, rbx
0x18005deda  call    vSAPCallback
0x18005dedf  test    dword ptr [rbx+8], 10000h
0x18005dee6  jnz     short loc_18005DF30
0x18005dee8  test    dword ptr [rbx+8], 100h
0x18005deef  jnz     short loc_18005DF34
0x18005def1  mov     rax, gs:30h
0x18005defa  mov     rcx, rdi
0x18005defd  mov     dword ptr [rax+808h], 0
0x18005df07  call    cs:__imp_NtGdiStrokePath
0x18005df0e  nop     dword ptr [rax+rax+00h]
0x18005df13  mov     rbx, [rsp+28h+arg_0]
0x18005df18  add     rsp, 20h
0x18005df1c  pop     rdi
0x18005df1d  retn
0x18005df1f  mov     ecx, 6
0x18005df24  call    cs:__imp_GdiSetLastError
0x18005df2b  nop     dword ptr [rax+rax+00h]
0x18005df30  xor     eax, eax
0x18005df32  jmp     short loc_18005DF13
0x18005df34  mov     rcx, rdi; hdc
0x18005df37  call    cs:__imp_StartPage
0x18005df3e  nop     dword ptr [rax+rax+00h]
0x18005df43  jmp     short loc_18005DEF1
```
