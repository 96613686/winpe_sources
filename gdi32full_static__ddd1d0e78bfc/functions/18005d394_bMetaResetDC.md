# bMetaResetDC

- ea: `0x18005d394`
- end: `0x18005d58f`
- name: `bMetaResetDC`
- size: `507`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180062a84`

## callees

- `0x18001e920`
- `0x18005d394`
- `0x18005dfc0`
- `0x18006bcb0`
- `0x180079940`
- `0x18008bf10`
- `0x18008c060`

## import_xrefs

- `GDI32!MoveToEx` at `0x18005d575`
- `GDI32!MoveToEx` at `0x18005d575`
- `GDI32!SelectObject` at `0x18005d3cd`
- `GDI32!SelectObject` at `0x18005d3f6`
- `GDI32!SelectObject` at `0x18005d41f`
- `GDI32!SelectObject` at `0x18005d448`
- `GDI32!SelectObject` at `0x18005d3cd`
- `GDI32!SelectObject` at `0x18005d3f6`
- `GDI32!SelectObject` at `0x18005d41f`
- `GDI32!SelectObject` at `0x18005d448`
- `GDI32!SetBkMode` at `0x18005d484`
- `GDI32!SetBkMode` at `0x18005d484`
- `GDI32!SetPolyFillMode` at `0x18005d498`
- `GDI32!SetPolyFillMode` at `0x18005d498`
- `GDI32!SetStretchBltMode` at `0x18005d4b9`
- `GDI32!SetStretchBltMode` at `0x18005d4b9`
- `GDI32!SetTextAlign` at `0x18005d4ca`
- `GDI32!SetTextAlign` at `0x18005d4ca`
- `GDI32!SetTextColor` at `0x18005d466`
- `GDI32!SetTextColor` at `0x18005d466`
- `GDI32!pGdiSharedMemory` at `0x18005d3b0`
- `GDI32!pGdiSharedMemory` at `0x18005d3d9`
- `GDI32!pGdiSharedMemory` at `0x18005d402`
- `GDI32!pGdiSharedMemory` at `0x18005d42b`
- `GDI32!SetMiterLimit` at `0x18005d52c`
- `GDI32!SetMiterLimit` at `0x18005d52c`
- `win32u!NtGdiGetAndSetDCDword` at `0x18005d4ed`
- `win32u!NtGdiGetAndSetDCDword` at `0x18005d55e`
- `win32u!NtGdiGetAndSetDCDword` at `0x18005d4ed`
- `win32u!NtGdiGetAndSetDCDword` at `0x18005d55e`

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
0x18005d394  push    rbx
0x18005d396  sub     rsp, 20h
0x18005d39a  cmp     cs:gbDisableMetaFiles, 0
0x18005d3a1  mov     rbx, rcx
0x18005d3a4  jz      short loc_18005D3B0
0x18005d3a6  mov     eax, 1
0x18005d3ab  jmp     loc_18005D588
0x18005d3b0  mov     rax, cs:__imp_pGdiSharedMemory
0x18005d3b7  mov     rcx, [rax]
0x18005d3ba  mov     rdx, [rcx+1800B0h]; h
0x18005d3c1  test    rdx, rdx
0x18005d3c4  jz      loc_18005D586
0x18005d3ca  mov     rcx, rbx; hdc
0x18005d3cd  call    cs:__imp_SelectObject
0x18005d3d4  nop     dword ptr [rax+rax+00h]
0x18005d3d9  mov     rax, cs:__imp_pGdiSharedMemory
0x18005d3e0  mov     rcx, [rax]
0x18005d3e3  mov     rdx, [rcx+1800E8h]; h
0x18005d3ea  test    rdx, rdx
0x18005d3ed  jz      loc_18005D586
0x18005d3f3  mov     rcx, rbx; hdc
0x18005d3f6  call    cs:__imp_SelectObject
0x18005d3fd  nop     dword ptr [rax+rax+00h]
0x18005d402  mov     rax, cs:__imp_pGdiSharedMemory
0x18005d409  mov     rcx, [rax]
0x18005d40c  mov     rdx, [rcx+180120h]; h
0x18005d413  test    rdx, rdx
0x18005d416  jz      loc_18005D586
0x18005d41c  mov     rcx, rbx; hdc
0x18005d41f  call    cs:__imp_SelectObject
0x18005d426  nop     dword ptr [rax+rax+00h]
0x18005d42b  mov     rax, cs:__imp_pGdiSharedMemory
0x18005d432  mov     rcx, [rax]
0x18005d435  mov     rdx, [rcx+180128h]; h
0x18005d43c  test    rdx, rdx
0x18005d43f  jz      loc_18005D586
0x18005d445  mov     rcx, rbx; hdc
0x18005d448  call    cs:__imp_SelectObject
0x18005d44f  nop     dword ptr [rax+rax+00h]
0x18005d454  mov     edx, 0FFFFFFh; color
0x18005d459  mov     rcx, rbx; hdc
0x18005d45c  call    SetBkColor
0x18005d461  xor     edx, edx; color
0x18005d463  mov     rcx, rbx; hdc
0x18005d466  call    cs:__imp_SetTextColor
0x18005d46d  nop     dword ptr [rax+rax+00h]
0x18005d472  xor     edx, edx; extra
0x18005d474  mov     rcx, rbx; hdc
0x18005d477  call    SetTextCharacterExtra
0x18005d47c  mov     edx, 2; mode
0x18005d481  mov     rcx, rbx; hdc
0x18005d484  call    cs:__imp_SetBkMode
0x18005d48b  nop     dword ptr [rax+rax+00h]
0x18005d490  mov     edx, 1; mode
0x18005d495  mov     rcx, rbx; hdc
0x18005d498  call    cs:__imp_SetPolyFillMode
0x18005d49f  nop     dword ptr [rax+rax+00h]
0x18005d4a4  mov     edx, 0Dh; rop2
0x18005d4a9  mov     rcx, rbx; hdc
0x18005d4ac  call    SetROP2
0x18005d4b1  mov     edx, 1; mode
0x18005d4b6  mov     rcx, rbx; hdc
0x18005d4b9  call    cs:__imp_SetStretchBltMode
0x18005d4c0  nop     dword ptr [rax+rax+00h]
0x18005d4c5  xor     edx, edx; align
0x18005d4c7  mov     rcx, rbx; hdc
0x18005d4ca  call    cs:__imp_SetTextAlign
0x18005d4d1  nop     dword ptr [rax+rax+00h]
0x18005d4d6  xor     r8d, r8d
0x18005d4d9  mov     [rsp+28h+arg_8], 0
0x18005d4e1  lea     r9, [rsp+28h+arg_8]
0x18005d4e6  mov     rcx, rbx
0x18005d4e9  lea     edx, [r8+7]
0x18005d4ed  call    cs:__imp_NtGdiGetAndSetDCDword
0x18005d4f4  nop     dword ptr [rax+rax+00h]
0x18005d4f9  test    eax, eax
0x18005d4fb  jz      short loc_18005D504
0x18005d4fd  cmp     [rsp+28h+arg_8], 0
0x18005d502  jz      short loc_18005D50E
0x18005d504  xor     edx, edx; flags
0x18005d506  mov     rcx, rbx; hdc
0x18005d509  call    SetMapperFlags
0x18005d50e  xor     r9d, r9d; lppt
0x18005d511  xor     r8d, r8d; y
0x18005d514  xor     edx, edx; x
0x18005d516  mov     rcx, rbx; hdc
0x18005d519  call    SetBrushOrgEx
0x18005d51e  movss   xmm1, cs:__real@41200000; limit
0x18005d526  xor     r8d, r8d; old
0x18005d529  mov     rcx, rbx; hdc
0x18005d52c  call    cs:__imp_SetMiterLimit
0x18005d533  nop     dword ptr [rax+rax+00h]
0x18005d538  xor     r8d, r8d; count
0x18005d53b  xor     edx, edx; extra
0x18005d53d  mov     rcx, rbx; hdc
0x18005d540  call    SetTextJustification
0x18005d545  mov     edx, 9
0x18005d54a  mov     [rsp+28h+arg_8], 0
0x18005d552  lea     r9, [rsp+28h+arg_8]
0x18005d557  mov     rcx, rbx
0x18005d55a  lea     r8d, [rdx-8]
0x18005d55e  call    cs:__imp_NtGdiGetAndSetDCDword
0x18005d565  nop     dword ptr [rax+rax+00h]
0x18005d56a  xor     r9d, r9d; lppt
0x18005d56d  xor     r8d, r8d; y
0x18005d570  xor     edx, edx; x
0x18005d572  mov     rcx, rbx; hdc
0x18005d575  call    cs:__imp_MoveToEx
0x18005d57c  nop     dword ptr [rax+rax+00h]
0x18005d581  jmp     loc_18005D3A6
0x18005d586  xor     eax, eax
0x18005d588  add     rsp, 20h
0x18005d58c  pop     rbx
0x18005d58d  retn
```
