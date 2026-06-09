# ExtCreatePen

- ea: `0x180030750`
- end: `0x180030907`
- name: `ExtCreatePen`
- size: `439`
- prototype: `HPEN __stdcall(DWORD iPenStyle, DWORD cWidth, const LOGBRUSH *plbrush, DWORD cStyle, const DWORD *pstyle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800323b0`

## callees

- `0x18002fda0`
- `0x180030750`
- `0x180036734`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180030810`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180030810`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003088e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003088e`
- `GDI32!GdiSetLastError` at `0x18003087a`
- `GDI32!GdiSetLastError` at `0x18003087a`
- `ntdll!RtlFreeHeap` at `0x1800308f6`
- `ntdll!RtlFreeHeap` at `0x1800308f6`
- `win32u!NtGdiExtCreatePen` at `0x1800307f8`
- `win32u!NtGdiExtCreatePen` at `0x1800307f8`

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
0x180030750  mov     rax, rsp
0x180030753  push    rbx
0x180030754  push    rbp
0x180030755  push    rsi
0x180030756  push    rdi
0x180030757  push    r12
0x180030759  push    r13
0x18003075b  push    r14
0x18003075d  push    r15
0x18003075f  sub     rsp, 68h
0x180030763  mov     dword ptr [rax+8], 0
0x18003076a  mov     r15d, r9d
0x18003076d  mov     eax, ecx
0x18003076f  mov     rbx, r8
0x180030772  and     eax, 0Fh
0x180030775  mov     r13d, edx
0x180030778  mov     r12d, ecx
0x18003077b  cmp     al, 7
0x18003077d  jnz     loc_18003085F
0x180030783  mov     rbp, [rsp+0A8h+pstyle]
0x18003078b  test    rbp, rbp
0x18003078e  jz      loc_180030875
0x180030794  mov     r14d, [r8]
0x180030797  xor     ecx, ecx
0x180030799  xor     esi, esi
0x18003079b  xor     edi, edi
0x18003079d  mov     eax, r14d
0x1800307a0  test    r14d, r14d
0x1800307a3  jz      short loc_1800307B3
0x1800307a5  sub     eax, 1
0x1800307a8  jz      short loc_1800307B3
0x1800307aa  sub     eax, 1
0x1800307ad  jnz     loc_18003083F
0x1800307b3  mov     rcx, [r8+8]
0x1800307b7  mov     eax, [rsp+0A8h+arg_0]
0x1800307be  mov     r8d, r14d
0x1800307c1  mov     r9d, [rbx+4]
0x1800307c5  mov     edx, r13d
0x1800307c8  mov     [rsp+0A8h+var_58], 0
0x1800307d1  mov     [rsp+0A8h+var_60], 0
0x1800307d9  mov     [rsp+0A8h+var_68], eax
0x1800307dd  mov     rax, [rbx+8]
0x1800307e1  mov     [rsp+0A8h+var_70], rbp
0x1800307e6  mov     [rsp+0A8h+var_78], r15d
0x1800307eb  mov     [rsp+0A8h+var_80], rcx
0x1800307f0  mov     ecx, r12d
0x1800307f3  mov     [rsp+0A8h+var_88], rax
0x1800307f8  call    cs:__imp_NtGdiExtCreatePen
0x1800307ff  nop     dword ptr [rax+rax+00h]
0x180030804  cmp     dword ptr [rbx], 5
0x180030807  mov     rbp, rax
0x18003080a  jnz     short loc_18003081C
0x18003080c  mov     rcx, [rbx+8]; hMem
0x180030810  call    cs:__imp_GlobalUnlock
0x180030817  nop     dword ptr [rax+rax+00h]
0x18003081c  test    rdi, rdi
0x18003081f  jnz     loc_1800308DB
0x180030825  mov     rcx, rbp
0x180030828  call    GdiTrackHCreate
0x18003082d  add     rsp, 68h
0x180030831  pop     r15
0x180030833  pop     r14
0x180030835  pop     r13
0x180030837  pop     r12
0x180030839  pop     rdi
0x18003083a  pop     rsi
0x18003083b  pop     rbp
0x18003083c  pop     rbx
0x18003083d  retn
0x18003083f  sub     eax, 1
0x180030842  jz      loc_1800308CC
0x180030848  sub     eax, 2
0x18003084b  jz      short loc_18003088A
0x18003084d  cmp     eax, 1
0x180030850  jnz     loc_1800307B7
0x180030856  mov     rsi, [r8+8]
0x18003085a  mov     rcx, rsi
0x18003085d  jmp     short loc_1800308AB
0x18003085f  test    r15d, r15d
0x180030862  jnz     short loc_180030875
0x180030864  mov     rbp, [rsp+0A8h+pstyle]
0x18003086c  test    rbp, rbp
0x18003086f  jz      loc_180030794
0x180030875  mov     ecx, 57h ; 'W'
0x18003087a  call    cs:__imp_GdiSetLastError
0x180030881  nop     dword ptr [rax+rax+00h]
0x180030886  xor     eax, eax
0x180030888  jmp     short loc_18003082D
0x18003088a  mov     rcx, [r8+8]; hMem
0x18003088e  call    cs:__imp_GlobalLock
0x180030895  nop     dword ptr [rax+rax+00h]
0x18003089a  mov     rsi, rax
0x18003089d  test    rax, rax
0x1800308a0  jz      short loc_180030886
0x1800308a2  mov     r14d, 6
0x1800308a8  mov     rcx, rax
0x1800308ab  mov     edx, [rbx+4]
0x1800308ae  lea     r8, [rsp+0A8h+arg_0]
0x1800308b6  mov     r9d, 1
0x1800308bc  call    pbmiConvertInfo
0x1800308c1  mov     rdi, rax
0x1800308c4  mov     rcx, rax
0x1800308c7  jmp     loc_1800307B7
0x1800308cc  mov     rcx, [r8+8]
0x1800308d0  test    rcx, rcx
0x1800308d3  jnz     loc_1800307B7
0x1800308d9  jmp     short loc_180030875
0x1800308db  cmp     rdi, rsi
0x1800308de  jz      loc_180030825
0x1800308e4  mov     rcx, gs:60h
0x1800308ed  mov     r8, rdi; P
0x1800308f0  xor     edx, edx; Flags
0x1800308f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800308f6  call    cs:__imp_RtlFreeHeap
0x1800308fd  nop     dword ptr [rax+rax+00h]
0x180030902  jmp     loc_180030825
```
