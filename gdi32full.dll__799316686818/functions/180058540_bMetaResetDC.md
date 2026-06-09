# bMetaResetDC

- ea: `0x180058540`
- end: `0x1800586ec`
- name: `bMetaResetDC`
- size: `428`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005ec9c`

## callees

- `0x18001dc40`
- `0x180058540`
- `0x180059f00`
- `0x180067540`
- `0x180074fe0`
- `0x180086b50`
- `0x180086c80`

## import_xrefs

- `GDI32!MoveToEx` at `0x1800586d9`
- `GDI32!MoveToEx` at `0x1800586d9`
- `GDI32!SelectObject` at `0x180058579`
- `GDI32!SelectObject` at `0x18005859c`
- `GDI32!SelectObject` at `0x1800585bf`
- `GDI32!SelectObject` at `0x1800585e2`
- `GDI32!SelectObject` at `0x180058579`
- `GDI32!SelectObject` at `0x18005859c`
- `GDI32!SelectObject` at `0x1800585bf`
- `GDI32!SelectObject` at `0x1800585e2`
- `GDI32!SetBkMode` at `0x180058612`
- `GDI32!SetBkMode` at `0x180058612`
- `GDI32!SetPolyFillMode` at `0x180058620`
- `GDI32!SetPolyFillMode` at `0x180058620`
- `GDI32!SetStretchBltMode` at `0x18005863b`
- `GDI32!SetStretchBltMode` at `0x18005863b`
- `GDI32!SetTextAlign` at `0x180058646`
- `GDI32!SetTextAlign` at `0x180058646`
- `GDI32!SetTextColor` at `0x1800585fa`
- `GDI32!SetTextColor` at `0x1800585fa`
- `GDI32!pGdiSharedMemory` at `0x18005855c`
- `GDI32!pGdiSharedMemory` at `0x18005857f`
- `GDI32!pGdiSharedMemory` at `0x1800585a2`
- `GDI32!pGdiSharedMemory` at `0x1800585c5`
- `GDI32!SetMiterLimit` at `0x18005869c`
- `GDI32!SetMiterLimit` at `0x18005869c`
- `win32u!NtGdiGetAndSetDCDword` at `0x180058663`
- `win32u!NtGdiGetAndSetDCDword` at `0x1800586c8`
- `win32u!NtGdiGetAndSetDCDword` at `0x180058663`
- `win32u!NtGdiGetAndSetDCDword` at `0x1800586c8`

## pseudocode

```c
__int64 __fastcall bMetaResetDC(HDC hdc)
{
  void *v3; // rdx
  void *v4; // rdx
  void *v5; // rdx
  void *v6; // rdx
  int v7; // [rsp+38h] [rbp+10h] BYREF

  if ( gbDisableMetaFiles )
    return 1;
  v3 = *(void **)(pGdiSharedMemory + 1573040LL);
  if ( v3 )
  {
    SelectObject(hdc, v3);
    v4 = *(void **)(pGdiSharedMemory + 1573096LL);
    if ( v4 )
    {
      SelectObject(hdc, v4);
      v5 = *(void **)(pGdiSharedMemory + 1573152LL);
      if ( v5 )
      {
        SelectObject(hdc, v5);
        v6 = *(void **)(pGdiSharedMemory + 1573160LL);
        if ( v6 )
        {
          SelectObject(hdc, v6);
          SetBkColor(hdc, 0xFFFFFFu);
          SetTextColor(hdc, 0);
          SetTextCharacterExtra(hdc, 0);
          SetBkMode(hdc, 2);
          SetPolyFillMode(hdc, 1);
          SetROP2(hdc, 13);
          SetStretchBltMode(hdc, 1);
          SetTextAlign(hdc, 0);
          v7 = 0;
          if ( !(unsigned int)NtGdiGetAndSetDCDword(hdc, 7, 0, &v7) || v7 )
            SetMapperFlags(hdc, 0);
          SetBrushOrgEx(hdc, 0, 0, 0);
          SetMiterLimit(hdc, 10.0, 0);
          SetTextJustification(hdc, 0, 0);
          v7 = 0;
          NtGdiGetAndSetDCDword(hdc, 9, 1, &v7);
          MoveToEx(hdc, 0, 0, 0);
          return 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180058540  push    rbx
0x180058542  sub     rsp, 20h
0x180058546  cmp     cs:gbDisableMetaFiles, 0
0x18005854d  mov     rbx, rcx
0x180058550  jz      short loc_18005855C
0x180058552  mov     eax, 1
0x180058557  jmp     loc_1800586E6
0x18005855c  mov     rax, cs:__imp_pGdiSharedMemory
0x180058563  mov     rcx, [rax]
0x180058566  mov     rdx, [rcx+1800B0h]; h
0x18005856d  test    rdx, rdx
0x180058570  jz      loc_1800586E4
0x180058576  mov     rcx, rbx; hdc
0x180058579  call    cs:__imp_SelectObject
0x18005857f  mov     rax, cs:__imp_pGdiSharedMemory
0x180058586  mov     rcx, [rax]
0x180058589  mov     rdx, [rcx+1800E8h]; h
0x180058590  test    rdx, rdx
0x180058593  jz      loc_1800586E4
0x180058599  mov     rcx, rbx; hdc
0x18005859c  call    cs:__imp_SelectObject
0x1800585a2  mov     rax, cs:__imp_pGdiSharedMemory
0x1800585a9  mov     rcx, [rax]
0x1800585ac  mov     rdx, [rcx+180120h]; h
0x1800585b3  test    rdx, rdx
0x1800585b6  jz      loc_1800586E4
0x1800585bc  mov     rcx, rbx; hdc
0x1800585bf  call    cs:__imp_SelectObject
0x1800585c5  mov     rax, cs:__imp_pGdiSharedMemory
0x1800585cc  mov     rcx, [rax]
0x1800585cf  mov     rdx, [rcx+180128h]; h
0x1800585d6  test    rdx, rdx
0x1800585d9  jz      loc_1800586E4
0x1800585df  mov     rcx, rbx; hdc
0x1800585e2  call    cs:__imp_SelectObject
0x1800585e8  mov     edx, 0FFFFFFh; color
0x1800585ed  mov     rcx, rbx; hdc
0x1800585f0  call    SetBkColor
0x1800585f5  xor     edx, edx; color
0x1800585f7  mov     rcx, rbx; hdc
0x1800585fa  call    cs:__imp_SetTextColor
0x180058600  xor     edx, edx; extra
0x180058602  mov     rcx, rbx; hdc
0x180058605  call    SetTextCharacterExtra
0x18005860a  mov     edx, 2; mode
0x18005860f  mov     rcx, rbx; hdc
0x180058612  call    cs:__imp_SetBkMode
0x180058618  mov     edx, 1; mode
0x18005861d  mov     rcx, rbx; hdc
0x180058620  call    cs:__imp_SetPolyFillMode
0x180058626  mov     edx, 0Dh; rop2
0x18005862b  mov     rcx, rbx; hdc
0x18005862e  call    SetROP2
0x180058633  mov     edx, 1; mode
0x180058638  mov     rcx, rbx; hdc
0x18005863b  call    cs:__imp_SetStretchBltMode
0x180058641  xor     edx, edx; align
0x180058643  mov     rcx, rbx; hdc
0x180058646  call    cs:__imp_SetTextAlign
0x18005864c  xor     r8d, r8d
0x18005864f  mov     [rsp+28h+arg_8], 0
0x180058657  lea     r9, [rsp+28h+arg_8]
0x18005865c  mov     rcx, rbx
0x18005865f  lea     edx, [r8+7]
0x180058663  call    cs:__imp_NtGdiGetAndSetDCDword
0x180058669  test    eax, eax
0x18005866b  jz      short loc_180058674
0x18005866d  cmp     [rsp+28h+arg_8], 0
0x180058672  jz      short loc_18005867E
0x180058674  xor     edx, edx; flags
0x180058676  mov     rcx, rbx; hdc
0x180058679  call    SetMapperFlags
0x18005867e  xor     r9d, r9d; lppt
0x180058681  xor     r8d, r8d; y
0x180058684  xor     edx, edx; x
0x180058686  mov     rcx, rbx; hdc
0x180058689  call    SetBrushOrgEx
0x18005868e  movss   xmm1, cs:__real@41200000; limit
0x180058696  xor     r8d, r8d; old
0x180058699  mov     rcx, rbx; hdc
0x18005869c  call    cs:__imp_SetMiterLimit
0x1800586a2  xor     r8d, r8d; count
0x1800586a5  xor     edx, edx; extra
0x1800586a7  mov     rcx, rbx; hdc
0x1800586aa  call    SetTextJustification
0x1800586af  mov     edx, 9
0x1800586b4  mov     [rsp+28h+arg_8], 0
0x1800586bc  lea     r9, [rsp+28h+arg_8]
0x1800586c1  mov     rcx, rbx
0x1800586c4  lea     r8d, [rdx-8]
0x1800586c8  call    cs:__imp_NtGdiGetAndSetDCDword
0x1800586ce  xor     r9d, r9d; lppt
0x1800586d1  xor     r8d, r8d; y
0x1800586d4  xor     edx, edx; x
0x1800586d6  mov     rcx, rbx; hdc
0x1800586d9  call    cs:__imp_MoveToEx
0x1800586df  jmp     loc_180058552
0x1800586e4  xor     eax, eax
0x1800586e6  add     rsp, 20h
0x1800586ea  pop     rbx
0x1800586eb  retn
```
