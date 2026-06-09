# StrokePathImpl

- ea: `0x180059cd0`
- end: `0x180059d78`
- name: `StrokePathImpl`
- size: `168`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180022898`
- `0x180022f88`
- `0x180059cd0`

## import_xrefs

- `GDI32!StartPage` at `0x180059d70`
- `GDI32!StartPage` at `0x180059d70`
- `GDI32!pldcGet` at `0x180059cf2`
- `GDI32!pldcGet` at `0x180059cf2`
- `GDI32!GdiSetLastError` at `0x180059d63`
- `GDI32!GdiSetLastError` at `0x180059d63`
- `win32u!NtGdiStrokePath` at `0x180059d4d`
- `win32u!NtGdiStrokePath` at `0x180059d4d`

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
0x180059cd0  mov     [rsp+arg_0], rbx
0x180059cd5  push    rdi
0x180059cd6  sub     rsp, 20h
0x180059cda  mov     eax, ecx
0x180059cdc  mov     rdi, rcx
0x180059cdf  and     eax, 7F0000h
0x180059ce4  cmp     eax, 10000h
0x180059ce9  jz      short loc_180059D37
0x180059ceb  cmp     eax, 660000h
0x180059cf0  jz      short loc_180059D69
0x180059cf2  call    cs:__imp_pldcGet
0x180059cf8  mov     rbx, rax
0x180059cfb  test    rax, rax
0x180059cfe  jz      short loc_180059D5E
0x180059d00  cmp     dword ptr [rax+0Ch], 2
0x180059d04  jnz     short loc_180059D17
0x180059d06  mov     edx, 40h ; '@'
0x180059d0b  mov     rcx, rdi
0x180059d0e  call    MF_BoundRecord
0x180059d13  test    eax, eax
0x180059d15  jz      short loc_180059D69
0x180059d17  test    byte ptr [rbx+8], 20h
0x180059d1b  jz      short loc_180059D25
0x180059d1d  mov     rcx, rbx
0x180059d20  call    vSAPCallback
0x180059d25  test    dword ptr [rbx+8], 10000h
0x180059d2c  jnz     short loc_180059D69
0x180059d2e  test    dword ptr [rbx+8], 100h
0x180059d35  jnz     short loc_180059D6D
0x180059d37  mov     rax, gs:30h
0x180059d40  mov     rcx, rdi
0x180059d43  mov     dword ptr [rax+808h], 0
0x180059d4d  call    cs:__imp_NtGdiStrokePath
0x180059d53  mov     rbx, [rsp+28h+arg_0]
0x180059d58  add     rsp, 20h
0x180059d5c  pop     rdi
0x180059d5d  retn
0x180059d5e  mov     ecx, 6
0x180059d63  call    cs:__imp_GdiSetLastError
0x180059d69  xor     eax, eax
0x180059d6b  jmp     short loc_180059D53
0x180059d6d  mov     rcx, rdi; hdc
0x180059d70  call    cs:__imp_StartPage
0x180059d76  jmp     short loc_180059D37
```
