# CLine21DecDraw::CheckTTFont(void)

- ea: `0x180129bb8`
- end: `0x180129c88`
- name: `?CheckTTFont@CLine21DecDraw@@AEAAXXZ`
- size: `208`
- prototype: `void __fastcall(LPARAM lParam)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180129554`

## callees

- `0x180039250`
- `0x180129bb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180129bff`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180129bff`
- `KERNEL32!LeaveCriticalSection` at `0x180129c7c`
- `KERNEL32!EnterCriticalSection` at `0x180129bca`
- `KERNEL32!EnterCriticalSection` at `0x180129bca`
- `GDI32!DeleteDC` at `0x180129c5e`
- `GDI32!DeleteDC` at `0x180129c5e`
- `GDI32!CreateDCW` at `0x180129c22`
- `GDI32!CreateDCW` at `0x180129c22`
- `GDI32!EnumFontFamiliesExW` at `0x180129c4f`
- `GDI32!EnumFontFamiliesExW` at `0x180129c4f`

## pseudocode

```c
void __fastcall CLine21DecDraw::CheckTTFont(LPARAM lParam)
{
  HDC DCW; // rax
  HDC v3; // rdi

  EnterCriticalSection((LPCRITICAL_SECTION)lParam);
  *(_DWORD *)(lParam + 168) = 0;
  memset_0((void *)(lParam + 76), 0, 0x5Cu);
  _o_wcscpy_s(lParam + 104, 32, L"Lucida Console");
  *(_BYTE *)(lParam + 99) = 0;
  *(_BYTE *)(lParam + 103) = 0;
  DCW = CreateDCW(L"Display", 0, 0, 0);
  v3 = DCW;
  if ( DCW )
  {
    EnumFontFamiliesExW(DCW, (LPLOGFONTW)(lParam + 76), CLine21DecDraw::EnumFontProc, lParam, 0);
    DeleteDC(v3);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lParam);
}

```

## disassembly

```asm
0x180129bb8  mov     [rsp+arg_0], rbx
0x180129bbd  mov     [rsp+arg_8], rsi
0x180129bc2  push    rdi
0x180129bc3  sub     rsp, 30h
0x180129bc7  mov     rbx, rcx
0x180129bca  call    cs:__imp_EnterCriticalSection
0x180129bd1  nop     dword ptr [rax+rax+00h]
0x180129bd6  xor     edx, edx; Val
0x180129bd8  mov     dword ptr [rbx+0A8h], 0
0x180129be2  lea     rcx, [rbx+4Ch]; void *
0x180129be6  lea     r8d, [rdx+5Ch]; Size
0x180129bea  call    memset_0
0x180129bef  lea     rcx, [rbx+68h]
0x180129bf3  mov     edx, 20h ; ' '
0x180129bf8  lea     r8, aLucidaConsole; "Lucida Console"
0x180129bff  call    cs:__imp__o_wcscpy_s
0x180129c06  nop     dword ptr [rax+rax+00h]
0x180129c0b  xor     r9d, r9d; pdm
0x180129c0e  mov     byte ptr [rbx+63h], 0
0x180129c12  xor     r8d, r8d; pszPort
0x180129c15  mov     byte ptr [rbx+67h], 0
0x180129c19  xor     edx, edx; pwszDevice
0x180129c1b  lea     rcx, aDisplay_0; "Display"
0x180129c22  call    cs:__imp_CreateDCW
0x180129c29  nop     dword ptr [rax+rax+00h]
0x180129c2e  mov     rdi, rax
0x180129c31  test    rax, rax
0x180129c34  jz      short loc_180129C6A
0x180129c36  mov     r9, rbx; lParam
0x180129c39  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180129c41  lea     r8, ?EnumFontProc@CLine21DecDraw@@CAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICW@@H_J@Z; lpProc
0x180129c48  mov     rcx, rax; hdc
0x180129c4b  lea     rdx, [rbx+4Ch]; lpLogfont
0x180129c4f  call    cs:__imp_EnumFontFamiliesExW
0x180129c56  nop     dword ptr [rax+rax+00h]
0x180129c5b  mov     rcx, rdi; hdc
0x180129c5e  call    cs:__imp_DeleteDC
0x180129c65  nop     dword ptr [rax+rax+00h]
0x180129c6a  mov     rcx, rbx
0x180129c6d  mov     rbx, [rsp+38h+arg_0]
0x180129c72  mov     rsi, [rsp+38h+arg_8]
0x180129c77  add     rsp, 30h
0x180129c7b  pop     rdi
0x180129c7c  jmp     cs:__imp_LeaveCriticalSection
```
