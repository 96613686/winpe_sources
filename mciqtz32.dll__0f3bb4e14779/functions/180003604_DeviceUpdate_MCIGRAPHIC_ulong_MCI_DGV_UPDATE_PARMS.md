# DeviceUpdate(_MCIGRAPHIC *,ulong,MCI_DGV_UPDATE_PARMS *)

- ea: `0x180003604`
- end: `0x180003842`
- name: `?DeviceUpdate@@YAKPEAU_MCIGRAPHIC@@KPEAUMCI_DGV_UPDATE_PARMS@@@Z`
- size: `574`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned int, struct MCI_DGV_UPDATE_PARMS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18000485c`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001e7c`
- `0x180001ef4`
- `0x180002254`
- `0x180002b00`
- `0x180003604`
- `0x18000415c`
- `0x180007010`

## import_xrefs

- `USER32!WindowFromDC` at `0x18000363e`
- `USER32!WindowFromDC` at `0x18000363e`
- `GDI32!SelectPalette` at `0x180003771`
- `GDI32!SelectPalette` at `0x180003802`
- `GDI32!SelectPalette` at `0x180003771`
- `GDI32!SelectPalette` at `0x180003802`
- `GDI32!GetStockObject` at `0x1800037ef`
- `GDI32!GetStockObject` at `0x1800037ef`
- `GDI32!StretchDIBits` at `0x1800037d7`
- `GDI32!StretchDIBits` at `0x1800037d7`
- `GDI32!RealizePalette` at `0x18000377b`
- `GDI32!RealizePalette` at `0x18000377b`

## pseudocode

```c
unsigned int __fastcall DeviceUpdate(struct _MCIGRAPHIC *a1, int a2, struct MCI_DGV_UPDATE_PARMS *a3)
{
  int v3; // edi
  unsigned __int64 v6; // r8
  __int64 v7; // rcx
  BITMAPINFO *v8; // rax
  BITMAPINFO *lpbmi; // rbx
  HPALETTE StockObject; // rax
  _DWORD v12[10]; // [rsp+70h] [rbp-28h] BYREF
  int v13; // [rsp+A0h] [rbp+8h] BYREF
  HPALETTE hPal; // [rsp+B8h] [rbp+20h] BYREF

  v3 = 0;
  if ( *((_QWORD *)a1 + 21) && (a2 & 0x60000) == 0x20000 && !WindowFromDC(a3->hDC) )
  {
    v13 = 0;
    DevicePause(a1, 2u, v6);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 152LL))(*((_QWORD *)a1 + 22), 0);
    LODWORD(hPal) = CurrentPosition(a1);
    PutSelection(a1, (unsigned int *)&hPal, 0);
    v7 = *((_QWORD *)a1 + 19);
    v12[0] = 0;
    (*(void (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v7 + 80LL))(v7, 0xFFFFFFFFLL, v12);
    v3 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(**((_QWORD **)a1 + 21) + 288LL))(
           *((_QWORD *)a1 + 21),
           &v13,
           0);
    if ( v13 > 0 && v3 >= 0 )
    {
      v8 = (BITMAPINFO *)operator new[](v13);
      lpbmi = v8;
      if ( v8 )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, int *, BITMAPINFO *))(**((_QWORD **)a1 + 21) + 288LL))(
               *((_QWORD *)a1 + 21),
               &v13,
               v8);
        if ( v3 >= 0 )
        {
          hPal = 0;
          DeviceGetPalette(a1, (unsigned __int64 *)&hPal);
          if ( hPal )
          {
            SelectPalette(a3->hDC, hPal, 1);
            RealizePalette(a3->hDC);
          }
          v3 = StretchDIBits(
                 a3->hDC,
                 0,
                 0,
                 lpbmi->bmiHeader.biWidth,
                 lpbmi->bmiHeader.biHeight,
                 0,
                 0,
                 lpbmi->bmiHeader.biWidth,
                 lpbmi->bmiHeader.biHeight,
                 (char *)&lpbmi->bmiHeader.biSize + 4 * lpbmi->bmiHeader.biClrUsed + lpbmi->bmiHeader.biSize,
                 lpbmi,
                 0,
                 0xCC0020u);
          if ( hPal )
          {
            StockObject = (HPALETTE)GetStockObject(15);
            SelectPalette(a3->hDC, StockObject, 1);
          }
        }
      }
      else
      {
        v3 = -2147024882;
      }
      operator delete[](lpbmi);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 152LL))(*((_QWORD *)a1 + 22), 0xFFFFFFFFLL);
  }
  return CheckResult(v3);
}

```

## disassembly

```asm
0x180003604  mov     [rsp+arg_8], rbx
0x180003609  push    rbp
0x18000360a  push    rsi
0x18000360b  push    rdi
0x18000360c  sub     rsp, 80h
0x180003613  xor     edi, edi
0x180003615  mov     rsi, r8
0x180003618  mov     rbp, rcx
0x18000361b  cmp     [rcx+0A8h], rdi
0x180003622  jz      loc_180003829
0x180003628  and     edx, 60000h
0x18000362e  cmp     edx, 20000h
0x180003634  jnz     loc_180003829
0x18000363a  mov     rcx, [r8+18h]; hDC
0x18000363e  call    cs:__imp_WindowFromDC
0x180003644  test    rax, rax
0x180003647  jnz     loc_180003829
0x18000364d  lea     edx, [rdi+2]; unsigned int
0x180003650  mov     [rsp+98h+arg_0], edi
0x180003657  mov     rcx, rbp; struct _MCIGRAPHIC *
0x18000365a  call    ?DevicePause@@YAKPEAU_MCIGRAPHIC@@K_K@Z; DevicePause(_MCIGRAPHIC *,ulong,unsigned __int64)
0x18000365f  mov     rcx, [rbp+0B0h]
0x180003666  xor     edx, edx
0x180003668  mov     rax, [rcx]
0x18000366b  mov     rax, [rax+98h]
0x180003672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003677  mov     rcx, rbp; struct _MCIGRAPHIC *
0x18000367a  call    ?CurrentPosition@@YAKPEAU_MCIGRAPHIC@@@Z; CurrentPosition(_MCIGRAPHIC *)
0x18000367f  xor     r8d, r8d; unsigned int *
0x180003682  mov     dword ptr [rsp+98h+hPal], eax
0x180003689  lea     rdx, [rsp+98h+hPal]; unsigned int *
0x180003691  mov     rcx, rbp; struct _MCIGRAPHIC *
0x180003694  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x180003699  mov     rcx, [rbp+98h]
0x1800036a0  lea     r8, [rsp+98h+var_28]
0x1800036a5  mov     [rsp+98h+var_28], edi
0x1800036a9  or      edx, 0FFFFFFFFh
0x1800036ac  mov     rax, [rcx]
0x1800036af  mov     rax, [rax+50h]
0x1800036b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b8  mov     rcx, [rbp+0A8h]
0x1800036bf  lea     rdx, [rsp+98h+arg_0]
0x1800036c7  xor     r8d, r8d
0x1800036ca  mov     rax, [rcx]
0x1800036cd  mov     rax, [rax+120h]
0x1800036d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d9  mov     edi, eax
0x1800036db  movsxd  rax, [rsp+98h+arg_0]
0x1800036e3  test    eax, eax
0x1800036e5  jle     loc_180003810
0x1800036eb  test    edi, edi
0x1800036ed  js      loc_180003810
0x1800036f3  mov     rcx, rax; unsigned __int64
0x1800036f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800036fb  mov     rbx, rax
0x1800036fe  test    rax, rax
0x180003701  jnz     short loc_18000370D
0x180003703  mov     edi, 8007000Eh
0x180003708  jmp     loc_180003808
0x18000370d  mov     rcx, [rbp+0A8h]
0x180003714  lea     rdx, [rsp+98h+arg_0]
0x18000371c  mov     r8, rbx
0x18000371f  mov     rax, [rcx]
0x180003722  mov     rax, [rax+120h]
0x180003729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372e  mov     edi, eax
0x180003730  test    eax, eax
0x180003732  js      loc_180003808
0x180003738  lea     rdx, [rsp+98h+hPal]; unsigned __int64 *
0x180003740  mov     [rsp+98h+hPal], 0
0x18000374c  mov     rcx, rbp; struct _MCIGRAPHIC *
0x18000374f  call    ?DeviceGetPalette@@YAKPEAU_MCIGRAPHIC@@PEA_K@Z; DeviceGetPalette(_MCIGRAPHIC *,unsigned __int64 *)
0x180003754  cmp     [rsp+98h+hPal], 0
0x18000375d  jz      short loc_180003781
0x18000375f  mov     rdx, [rsp+98h+hPal]; hPal
0x180003767  mov     r8d, 1; bForceBkgd
0x18000376d  mov     rcx, [rsi+18h]; hdc
0x180003771  call    cs:__imp_SelectPalette
0x180003777  mov     rcx, [rsi+18h]; hdc
0x18000377b  call    cs:__imp_RealizePalette
0x180003781  mov     edx, [rbx+20h]
0x180003784  xor     r8d, r8d; yDest
0x180003787  mov     r10d, [rbx+8]
0x18000378b  mov     ecx, [rbx]
0x18000378d  mov     r9d, [rbx+4]; DestWidth
0x180003791  add     rcx, rbx
0x180003794  mov     [rsp+98h+rop], 0CC0020h; rop
0x18000379c  mov     [rsp+98h+iUsage], 0; iUsage
0x1800037a4  mov     [rsp+98h+lpbmi], rbx; lpbmi
0x1800037a9  lea     rax, [rcx+rdx*4]
0x1800037ad  mov     rcx, [rsi+18h]; hdc
0x1800037b1  mov     [rsp+98h+lpBits], rax; lpBits
0x1800037b6  xor     edx, edx; xDest
0x1800037b8  mov     [rsp+98h+SrcHeight], r10d; SrcHeight
0x1800037bd  mov     [rsp+98h+SrcWidth], r9d; SrcWidth
0x1800037c2  mov     [rsp+98h+ySrc], 0; ySrc
0x1800037ca  mov     [rsp+98h+xSrc], 0; xSrc
0x1800037d2  mov     [rsp+98h+DestHeight], r10d; DestHeight
0x1800037d7  call    cs:__imp_StretchDIBits
0x1800037dd  cmp     [rsp+98h+hPal], 0
0x1800037e6  mov     edi, eax
0x1800037e8  jz      short loc_180003808
0x1800037ea  mov     ecx, 0Fh; i
0x1800037ef  call    cs:__imp_GetStockObject
0x1800037f5  mov     rcx, [rsi+18h]; hdc
0x1800037f9  mov     r8d, 1; bForceBkgd
0x1800037ff  mov     rdx, rax; hPal
0x180003802  call    cs:__imp_SelectPalette
0x180003808  mov     rcx, rbx; void *
0x18000380b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003810  mov     rcx, [rbp+0B0h]
0x180003817  or      edx, 0FFFFFFFFh
0x18000381a  mov     rax, [rcx]
0x18000381d  mov     rax, [rax+98h]
0x180003824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003829  mov     ecx, edi; int
0x18000382b  mov     rbx, [rsp+98h+arg_8]
0x180003833  add     rsp, 80h
0x18000383a  pop     rdi
0x18000383b  pop     rsi
0x18000383c  pop     rbp
0x18000383d  jmp     ?CheckResult@@YAKJ@Z; CheckResult(long)
```
