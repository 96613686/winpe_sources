# ExtCreatePen

- ea: `0x180025210`
- end: `0x1800253a0`
- name: `ExtCreatePen`
- size: `400`
- prototype: `HPEN __stdcall(DWORD iPenStyle, DWORD cWidth, const LOGBRUSH *plbrush, DWORD cStyle, const DWORD *pstyle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e900`

## callees

- `0x18001d4fc`
- `0x180025210`
- `0x180026cf0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800252c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800252c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180025333`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180025333`
- `GDI32!GdiSetLastError` at `0x180025325`
- `GDI32!GdiSetLastError` at `0x180025325`
- `ntdll!RtlFreeHeap` at `0x180025395`
- `ntdll!RtlFreeHeap` at `0x180025395`
- `win32u!NtGdiExtCreatePen` at `0x1800252b4`
- `win32u!NtGdiExtCreatePen` at `0x1800252b4`

## pseudocode

```c
HPEN __stdcall ExtCreatePen(DWORD iPenStyle, DWORD cWidth, const LOGBRUSH *plbrush, DWORD cStyle, const DWORD *pstyle)
{
  const DWORD *v9; // rbp
  UINT lbStyle; // r14d
  ULONG_PTR v11; // rcx
  ULONG_PTR lbHatch; // rsi
  void *v13; // rdi
  const BITMAPINFOHEADER *v14; // rdx
  HDC Pen; // rbp
  DWORD v16; // r8d
  const void *v17; // r9
  ULONG_PTR v19; // rcx
  LPVOID v20; // rax
  int v21; // [rsp+B0h] [rbp+8h] BYREF

  v21 = 0;
  if ( (iPenStyle & 0xF) == 7 )
  {
    v9 = pstyle;
    if ( !pstyle )
      goto LABEL_17;
  }
  else
  {
    if ( cStyle )
      goto LABEL_17;
    v9 = pstyle;
    if ( pstyle )
      goto LABEL_17;
  }
  lbStyle = plbrush->lbStyle;
  v11 = 0;
  lbHatch = 0;
  v13 = 0;
  if ( plbrush->lbStyle && lbStyle != 1 && lbStyle != 2 )
  {
    if ( lbStyle != 3 )
    {
      if ( lbStyle != 5 )
      {
        if ( lbStyle != 6 )
          goto LABEL_7;
        lbHatch = plbrush->lbHatch;
        v19 = lbHatch;
LABEL_21:
        v13 = (void *)pbmiConvertInfo(v19, plbrush->lbColor, &v21, 1);
        v11 = (ULONG_PTR)v13;
        goto LABEL_7;
      }
      v20 = GlobalLock((HGLOBAL)plbrush->lbHatch);
      lbHatch = (ULONG_PTR)v20;
      if ( v20 )
      {
        lbStyle = 6;
        v19 = (ULONG_PTR)v20;
        goto LABEL_21;
      }
      return 0;
    }
    v11 = plbrush->lbHatch;
    if ( v11 )
      goto LABEL_7;
LABEL_17:
    GdiSetLastError(87);
    return 0;
  }
  v11 = plbrush->lbHatch;
LABEL_7:
  Pen = (HDC)NtGdiExtCreatePen(
               iPenStyle,
               cWidth,
               lbStyle,
               plbrush->lbColor,
               plbrush->lbHatch,
               v11,
               cStyle,
               v9,
               v21,
               0,
               0);
  if ( plbrush->lbStyle == 5 )
    GlobalUnlock((HGLOBAL)plbrush->lbHatch);
  if ( v13 )
  {
    if ( v13 != (void *)lbHatch )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  }
  return (HPEN)GdiTrackHCreate(Pen, v14, v16, v17);
}

```

## disassembly

```asm
0x180025210  mov     rax, rsp
0x180025213  push    rbx
0x180025214  push    rbp
0x180025215  push    rsi
0x180025216  push    rdi
0x180025217  push    r12
0x180025219  push    r13
0x18002521b  push    r14
0x18002521d  push    r15
0x18002521f  sub     rsp, 68h
0x180025223  mov     dword ptr [rax+8], 0
0x18002522a  mov     r15d, r9d
0x18002522d  mov     eax, ecx
0x18002522f  mov     rbx, r8
0x180025232  and     eax, 0Fh
0x180025235  mov     r13d, edx
0x180025238  mov     r12d, ecx
0x18002523b  cmp     al, 7
0x18002523d  jnz     loc_18002530A
0x180025243  mov     rbp, [rsp+0A8h+pstyle]
0x18002524b  test    rbp, rbp
0x18002524e  jz      loc_180025320
0x180025254  mov     r14d, [r8]
0x180025257  xor     ecx, ecx
0x180025259  xor     esi, esi
0x18002525b  xor     edi, edi
0x18002525d  mov     eax, r14d
0x180025260  test    r14d, r14d
0x180025263  jz      short loc_18002526F
0x180025265  sub     eax, 1
0x180025268  jz      short loc_18002526F
0x18002526a  sub     eax, 1
0x18002526d  jnz     short loc_1800252EE
0x18002526f  mov     rcx, [r8+8]
0x180025273  mov     eax, [rsp+0A8h+arg_0]
0x18002527a  mov     r8d, r14d
0x18002527d  mov     r9d, [rbx+4]
0x180025281  mov     edx, r13d
0x180025284  mov     [rsp+0A8h+var_58], 0
0x18002528d  mov     [rsp+0A8h+var_60], 0
0x180025295  mov     [rsp+0A8h+var_68], eax
0x180025299  mov     rax, [rbx+8]
0x18002529d  mov     [rsp+0A8h+var_70], rbp
0x1800252a2  mov     [rsp+0A8h+var_78], r15d
0x1800252a7  mov     [rsp+0A8h+var_80], rcx
0x1800252ac  mov     ecx, r12d
0x1800252af  mov     [rsp+0A8h+var_88], rax
0x1800252b4  call    cs:__imp_NtGdiExtCreatePen
0x1800252ba  cmp     dword ptr [rbx], 5
0x1800252bd  mov     rbp, rax
0x1800252c0  jnz     short loc_1800252CC
0x1800252c2  mov     rcx, [rbx+8]; hMem
0x1800252c6  call    cs:__imp_GlobalUnlock
0x1800252cc  test    rdi, rdi
0x1800252cf  jnz     loc_18002537A
0x1800252d5  mov     rcx, rbp
0x1800252d8  call    GdiTrackHCreate
0x1800252dd  add     rsp, 68h
0x1800252e1  pop     r15
0x1800252e3  pop     r14
0x1800252e5  pop     r13
0x1800252e7  pop     r12
0x1800252e9  pop     rdi
0x1800252ea  pop     rsi
0x1800252eb  pop     rbp
0x1800252ec  pop     rbx
0x1800252ed  retn
0x1800252ee  sub     eax, 1
0x1800252f1  jz      short loc_18002536B
0x1800252f3  sub     eax, 2
0x1800252f6  jz      short loc_18002532F
0x1800252f8  cmp     eax, 1
0x1800252fb  jnz     loc_180025273
0x180025301  mov     rsi, [r8+8]
0x180025305  mov     rcx, rsi
0x180025308  jmp     short loc_18002534A
0x18002530a  test    r15d, r15d
0x18002530d  jnz     short loc_180025320
0x18002530f  mov     rbp, [rsp+0A8h+pstyle]
0x180025317  test    rbp, rbp
0x18002531a  jz      loc_180025254
0x180025320  mov     ecx, 57h ; 'W'
0x180025325  call    cs:__imp_GdiSetLastError
0x18002532b  xor     eax, eax
0x18002532d  jmp     short loc_1800252DD
0x18002532f  mov     rcx, [r8+8]; hMem
0x180025333  call    cs:__imp_GlobalLock
0x180025339  mov     rsi, rax
0x18002533c  test    rax, rax
0x18002533f  jz      short loc_18002532B
0x180025341  mov     r14d, 6
0x180025347  mov     rcx, rax
0x18002534a  mov     edx, [rbx+4]
0x18002534d  lea     r8, [rsp+0A8h+arg_0]
0x180025355  mov     r9d, 1
0x18002535b  call    pbmiConvertInfo
0x180025360  mov     rdi, rax
0x180025363  mov     rcx, rax
0x180025366  jmp     loc_180025273
0x18002536b  mov     rcx, [r8+8]
0x18002536f  test    rcx, rcx
0x180025372  jnz     loc_180025273
0x180025378  jmp     short loc_180025320
0x18002537a  cmp     rdi, rsi
0x18002537d  jz      loc_1800252D5
0x180025383  mov     rcx, gs:60h
0x18002538c  mov     r8, rdi; P
0x18002538f  xor     edx, edx; Flags
0x180025391  mov     rcx, [rcx+30h]; HeapHandle
0x180025395  call    cs:__imp_RtlFreeHeap
0x18002539b  jmp     loc_1800252D5
```
