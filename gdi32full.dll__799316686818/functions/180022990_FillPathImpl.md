# FillPathImpl

- ea: `0x180022990`
- end: `0x180022a3a`
- name: `FillPathImpl`
- size: `170`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180022898`
- `0x180022990`
- `0x180022f88`

## import_xrefs

- `GDI32!StartPage` at `0x180022a25`
- `GDI32!StartPage` at `0x180022a25`
- `GDI32!pldcGet` at `0x1800229b2`
- `GDI32!pldcGet` at `0x1800229b2`
- `GDI32!GdiSetLastError` at `0x180022a32`
- `GDI32!GdiSetLastError` at `0x180022a32`
- `win32u!NtGdiFillPath` at `0x180022a0d`
- `win32u!NtGdiFillPath` at `0x180022a0d`

## pseudocode

```c
__int64 __fastcall FillPathImpl(HDC hdc)
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
      if ( *(_DWORD *)(v2 + 12) != 2 || (unsigned int)MF_BoundRecord(hdc, 62) )
      {
        if ( (*(_BYTE *)(v3 + 8) & 0x20) != 0 )
          vSAPCallback(v3);
        if ( (*(_DWORD *)(v3 + 8) & 0x10000) == 0 )
        {
          if ( (*(_DWORD *)(v3 + 8) & 0x100) != 0 )
            StartPage(hdc);
LABEL_11:
          LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
          return NtGdiFillPath(hdc);
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
0x180022990  mov     [rsp+arg_0], rbx
0x180022995  push    rdi
0x180022996  sub     rsp, 20h
0x18002299a  mov     eax, ecx
0x18002299c  mov     rdi, rcx
0x18002299f  and     eax, 7F0000h
0x1800229a4  cmp     eax, 10000h
0x1800229a9  jz      short loc_1800229F7
0x1800229ab  cmp     eax, 660000h
0x1800229b0  jz      short loc_180022A1E
0x1800229b2  call    cs:__imp_pldcGet
0x1800229b8  mov     rbx, rax
0x1800229bb  test    rax, rax
0x1800229be  jz      short loc_180022A2D
0x1800229c0  cmp     dword ptr [rax+0Ch], 2
0x1800229c4  jnz     short loc_1800229D7
0x1800229c6  mov     edx, 3Eh ; '>'
0x1800229cb  mov     rcx, rdi
0x1800229ce  call    MF_BoundRecord
0x1800229d3  test    eax, eax
0x1800229d5  jz      short loc_180022A1E
0x1800229d7  test    byte ptr [rbx+8], 20h
0x1800229db  jz      short loc_1800229E5
0x1800229dd  mov     rcx, rbx
0x1800229e0  call    vSAPCallback
0x1800229e5  test    dword ptr [rbx+8], 10000h
0x1800229ec  jnz     short loc_180022A1E
0x1800229ee  test    dword ptr [rbx+8], 100h
0x1800229f5  jnz     short loc_180022A22
0x1800229f7  mov     rax, gs:30h
0x180022a00  mov     rcx, rdi
0x180022a03  mov     dword ptr [rax+808h], 0
0x180022a0d  call    cs:__imp_NtGdiFillPath
0x180022a13  mov     rbx, [rsp+28h+arg_0]
0x180022a18  add     rsp, 20h
0x180022a1c  pop     rdi
0x180022a1d  retn
0x180022a1e  xor     eax, eax
0x180022a20  jmp     short loc_180022A13
0x180022a22  mov     rcx, rdi; hdc
0x180022a25  call    cs:__imp_StartPage
0x180022a2b  jmp     short loc_1800229F7
0x180022a2d  mov     ecx, 6
0x180022a32  call    cs:__imp_GdiSetLastError
0x180022a38  jmp     short loc_180022A1E
```
