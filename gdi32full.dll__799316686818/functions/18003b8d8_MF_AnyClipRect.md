# MF_AnyClipRect

- ea: `0x18003b8d8`
- end: `0x18003b9de`
- name: `MF_AnyClipRect`
- size: `262`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180053e70`
- `0x180068b00`

## callees

- `0x180023858`
- `0x18003b8d8`
- `0x18003b9e4`
- `0x18003ba90`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x18003b95a`
- `GDI32!CreateRectRgn` at `0x18003b95a`
- `GDI32!pldcGet` at `0x18003b8ef`
- `GDI32!pldcGet` at `0x18003b8ef`
- `GDI32!GdiSetLastError` at `0x18003b99b`
- `GDI32!GdiSetLastError` at `0x18003b99b`
- `GDI32!DeleteObject` at `0x18003b983`
- `GDI32!DeleteObject` at `0x18003b983`
- `win32u!NtGdiExtSelectClipRgn` at `0x18003b9d1`
- `win32u!NtGdiExtSelectClipRgn` at `0x18003b9d1`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x18003b9bb`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x18003b9bb`

## pseudocode

```c
_BOOL8 __fastcall MF_AnyClipRect(HDC hdc, int a2, int a3, int a4, int a5, int a6)
{
  __int64 v10; // rax
  MDC *v11; // rbx
  HRGN RectRgn; // rax
  HRGN v13; // rdi
  BOOL v14; // ebx
  int ClipRgn; // eax

  v10 = pldcGet(hdc);
  if ( !v10 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
  {
    GdiSetLastError(6);
    return 0;
  }
  v11 = *(MDC **)(v10 + 16);
  if ( !(unsigned int)MF_SetDDDD((_DWORD)hdc, a2, a3, a4, a5, a6) )
    return 0;
  MDC::vFlushBounds(v11);
  *((_DWORD *)v11 + 8) |= 0x40u;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v13 = RectRgn;
  if ( !RectRgn )
    return 0;
  v14 = 0;
  ClipRgn = GetClipRgn(hdc, RectRgn);
  if ( ClipRgn )
  {
    v14 = ClipRgn == 1;
  }
  else if ( SetRectRgn(v13, -32768, -32768, 0x7FFF, 0x7FFF) )
  {
    LOBYTE(v14) = (unsigned int)NtGdiExtSelectClipRgn(hdc, v13, 5) != 0;
  }
  DeleteObject(v13);
  return v14;
}

```

## disassembly

```asm
0x18003b8d8  push    rbx
0x18003b8da  push    rbp
0x18003b8db  push    rsi
0x18003b8dc  push    rdi
0x18003b8dd  push    r14
0x18003b8df  sub     rsp, 30h
0x18003b8e3  mov     edi, r9d
0x18003b8e6  mov     ebp, r8d
0x18003b8e9  mov     r14d, edx
0x18003b8ec  mov     rsi, rcx
0x18003b8ef  call    cs:__imp_pldcGet
0x18003b8f5  test    rax, rax
0x18003b8f8  jz      loc_18003B996
0x18003b8fe  mov     r10d, esi
0x18003b901  and     r10d, 7F0000h
0x18003b908  cmp     r10d, 660000h
0x18003b90f  jz      loc_18003B996
0x18003b915  mov     rbx, [rax+10h]
0x18003b919  mov     r9d, edi
0x18003b91c  mov     eax, [rsp+58h+arg_28]
0x18003b923  mov     r8d, ebp
0x18003b926  mov     [rsp+58h+var_30], eax
0x18003b92a  mov     edx, r14d
0x18003b92d  mov     eax, [rsp+58h+arg_20]
0x18003b934  mov     rcx, rsi
0x18003b937  mov     [rsp+58h+bottom], eax
0x18003b93b  call    MF_SetDDDD
0x18003b940  test    eax, eax
0x18003b942  jz      short loc_18003B9A1
0x18003b944  mov     rcx, rbx; this
0x18003b947  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x18003b94c  or      dword ptr [rbx+20h], 40h
0x18003b950  xor     r9d, r9d; y2
0x18003b953  xor     r8d, r8d; x2
0x18003b956  xor     edx, edx; y1
0x18003b958  xor     ecx, ecx; x1
0x18003b95a  call    cs:__imp_CreateRectRgn
0x18003b960  mov     rdi, rax
0x18003b963  test    rax, rax
0x18003b966  jz      short loc_18003B9A1
0x18003b968  mov     rdx, rax; hrgn
0x18003b96b  mov     rcx, rsi; hdc
0x18003b96e  xor     ebx, ebx
0x18003b970  call    GetClipRgn
0x18003b975  test    eax, eax
0x18003b977  jz      short loc_18003B9A5
0x18003b979  cmp     eax, 1
0x18003b97c  jnz     short loc_18003B980
0x18003b97e  mov     ebx, eax
0x18003b980  mov     rcx, rdi; ho
0x18003b983  call    cs:__imp_DeleteObject
0x18003b989  mov     eax, ebx
0x18003b98b  add     rsp, 30h
0x18003b98f  pop     r14
0x18003b991  pop     rdi
0x18003b992  pop     rsi
0x18003b993  pop     rbp
0x18003b994  pop     rbx
0x18003b995  retn
0x18003b996  mov     ecx, 6
0x18003b99b  call    cs:__imp_GdiSetLastError
0x18003b9a1  xor     eax, eax
0x18003b9a3  jmp     short loc_18003B98B
0x18003b9a5  mov     edx, 0FFFF8000h; left
0x18003b9aa  mov     r9d, 7FFFh; right
0x18003b9b0  mov     r8d, edx; top
0x18003b9b3  mov     [rsp+58h+bottom], r9d; bottom
0x18003b9b8  mov     rcx, rdi; hrgn
0x18003b9bb  call    cs:__imp_SetRectRgn
0x18003b9c1  test    eax, eax
0x18003b9c3  jz      short loc_18003B980
0x18003b9c5  mov     r8d, 5
0x18003b9cb  mov     rdx, rdi
0x18003b9ce  mov     rcx, rsi
0x18003b9d1  call    cs:__imp_NtGdiExtSelectClipRgn
0x18003b9d7  test    eax, eax
0x18003b9d9  setnz   bl
0x18003b9dc  jmp     short loc_18003B980
```
