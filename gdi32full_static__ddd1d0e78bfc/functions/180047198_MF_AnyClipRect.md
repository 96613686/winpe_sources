# MF_AnyClipRect

- ea: `0x180047198`
- end: `0x1800472c3`
- name: `MF_AnyClipRect`
- size: `299`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180059960`
- `0x18006cfa0`

## callees

- `0x18002c7b8`
- `0x180047198`
- `0x1800472cc`
- `0x180047380`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x180047220`
- `GDI32!CreateRectRgn` at `0x180047220`
- `GDI32!pldcGet` at `0x1800471af`
- `GDI32!pldcGet` at `0x1800471af`
- `GDI32!GdiSetLastError` at `0x18004726e`
- `GDI32!GdiSetLastError` at `0x18004726e`
- `GDI32!DeleteObject` at `0x18004724f`
- `GDI32!DeleteObject` at `0x18004724f`
- `win32u!NtGdiExtSelectClipRgn` at `0x1800472b0`
- `win32u!NtGdiExtSelectClipRgn` at `0x1800472b0`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180047294`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180047294`

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
0x180047198  push    rbx
0x18004719a  push    rbp
0x18004719b  push    rsi
0x18004719c  push    rdi
0x18004719d  push    r14
0x18004719f  sub     rsp, 30h
0x1800471a3  mov     edi, r9d
0x1800471a6  mov     ebp, r8d
0x1800471a9  mov     r14d, edx
0x1800471ac  mov     rsi, rcx
0x1800471af  call    cs:__imp_pldcGet
0x1800471b6  nop     dword ptr [rax+rax+00h]
0x1800471bb  test    rax, rax
0x1800471be  jz      loc_180047269
0x1800471c4  mov     r10d, esi
0x1800471c7  and     r10d, 7F0000h
0x1800471ce  cmp     r10d, 660000h
0x1800471d5  jz      loc_180047269
0x1800471db  mov     rbx, [rax+10h]
0x1800471df  mov     r9d, edi
0x1800471e2  mov     eax, [rsp+58h+arg_28]
0x1800471e9  mov     r8d, ebp
0x1800471ec  mov     [rsp+58h+var_30], eax
0x1800471f0  mov     edx, r14d
0x1800471f3  mov     eax, [rsp+58h+arg_20]
0x1800471fa  mov     rcx, rsi
0x1800471fd  mov     [rsp+58h+bottom], eax
0x180047201  call    MF_SetDDDD
0x180047206  test    eax, eax
0x180047208  jz      short loc_18004727A
0x18004720a  mov     rcx, rbx; this
0x18004720d  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x180047212  or      dword ptr [rbx+20h], 40h
0x180047216  xor     r9d, r9d; y2
0x180047219  xor     r8d, r8d; x2
0x18004721c  xor     edx, edx; y1
0x18004721e  xor     ecx, ecx; x1
0x180047220  call    cs:__imp_CreateRectRgn
0x180047227  nop     dword ptr [rax+rax+00h]
0x18004722c  mov     rdi, rax
0x18004722f  test    rax, rax
0x180047232  jz      short loc_18004727A
0x180047234  mov     rdx, rax; hrgn
0x180047237  mov     rcx, rsi; hdc
0x18004723a  xor     ebx, ebx
0x18004723c  call    GetClipRgn
0x180047241  test    eax, eax
0x180047243  jz      short loc_18004727E
0x180047245  cmp     eax, 1
0x180047248  jnz     short loc_18004724C
0x18004724a  mov     ebx, eax
0x18004724c  mov     rcx, rdi; ho
0x18004724f  call    cs:__imp_DeleteObject
0x180047256  nop     dword ptr [rax+rax+00h]
0x18004725b  mov     eax, ebx
0x18004725d  add     rsp, 30h
0x180047261  pop     r14
0x180047263  pop     rdi
0x180047264  pop     rsi
0x180047265  pop     rbp
0x180047266  pop     rbx
0x180047267  retn
0x180047269  mov     ecx, 6
0x18004726e  call    cs:__imp_GdiSetLastError
0x180047275  nop     dword ptr [rax+rax+00h]
0x18004727a  xor     eax, eax
0x18004727c  jmp     short loc_18004725D
0x18004727e  mov     edx, 0FFFF8000h; left
0x180047283  mov     r9d, 7FFFh; right
0x180047289  mov     r8d, edx; top
0x18004728c  mov     [rsp+58h+bottom], r9d; bottom
0x180047291  mov     rcx, rdi; hrgn
0x180047294  call    cs:__imp_SetRectRgn
0x18004729b  nop     dword ptr [rax+rax+00h]
0x1800472a0  test    eax, eax
0x1800472a2  jz      short loc_18004724C
0x1800472a4  mov     r8d, 5
0x1800472aa  mov     rdx, rdi
0x1800472ad  mov     rcx, rsi
0x1800472b0  call    cs:__imp_NtGdiExtSelectClipRgn
0x1800472b7  nop     dword ptr [rax+rax+00h]
0x1800472bc  test    eax, eax
0x1800472be  setnz   bl
0x1800472c1  jmp     short loc_18004724C
```
