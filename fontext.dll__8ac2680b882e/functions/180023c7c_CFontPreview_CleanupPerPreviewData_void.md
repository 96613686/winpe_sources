# CFontPreview::CleanupPerPreviewData(void)

- ea: `0x180023c7c`
- end: `0x180023d8d`
- name: `?CleanupPerPreviewData@CFontPreview@@AEAAXXZ`
- size: `273`
- prototype: `void __fastcall(CFontPreview *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023b44`
- `0x180024570`
- `0x180024b80`

## callees

- `0x1800139f4`
- `0x180023c7c`
- `0x18002536c`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180023d22`
- `SHELL32!__imp_ILFree` at `0x180023d22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023d10`
- `GDI32!DeleteObject` at `0x180023d3c`
- `GDI32!DeleteObject` at `0x180023d3c`
- `GDI32!RemoveFontResourceExW` at `0x180023cea`
- `GDI32!RemoveFontResourceExW` at `0x180023cea`
- `USER32!DestroyWindow` at `0x180023c94`
- `USER32!DestroyWindow` at `0x180023c94`
- `UxTheme!BufferedPaintUnInit` at `0x180023c85`
- `UxTheme!BufferedPaintUnInit` at `0x180023c85`

## pseudocode

```c
void __fastcall CFontPreview::CleanupPerPreviewData(CFontPreview *this)
{
  HWND v2; // rcx
  const unsigned __int16 *v3; // rdx
  const WCHAR *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  ITEMIDLIST *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  BufferedPaintUnInit();
  v2 = (HWND)*((_QWORD *)this + 11);
  if ( v2 )
  {
    DestroyWindow(v2);
    *((_QWORD *)this + 11) = 0;
  }
  IsolationAwareUnregisterClassW();
  v3 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( v3 && !PathIsInFontsDirectory(0, v3) && !PathIsInFontsDirectory(1, *((const unsigned __int16 **)this + 7)) )
  {
    if ( !*((_DWORD *)this + 60) || (v4 = (const WCHAR *)*((_QWORD *)this + 8)) == 0 )
      v4 = (const WCHAR *)*((_QWORD *)this + 7);
    RemoveFontResourceExW(v4, 0x10u, 0);
  }
  v5 = (void *)*((_QWORD *)this + 7);
  *((_DWORD *)this + 60) = 0;
  CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = 0;
  CoTaskMemFree(v6);
  v7 = (ITEMIDLIST *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 8) = 0;
  ILFree(v7);
  v8 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 15) = 0;
  if ( v8 )
  {
    DeleteObject(v8);
    *((_QWORD *)this + 17) = 0;
  }
  v9 = *((_QWORD *)this + 14);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 14) = 0;
  }
  v10 = *((_QWORD *)this + 9);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x180023c7c  push    rbx
0x180023c7e  sub     rsp, 20h
0x180023c82  mov     rbx, rcx
0x180023c85  call    cs:__imp_BufferedPaintUnInit
0x180023c8b  mov     rcx, [rbx+58h]; hWnd
0x180023c8f  test    rcx, rcx
0x180023c92  jz      short loc_180023CA2
0x180023c94  call    cs:__imp_DestroyWindow
0x180023c9a  mov     qword ptr [rbx+58h], 0
0x180023ca2  call    IsolationAwareUnregisterClassW
0x180023ca7  mov     rdx, [rbx+38h]; unsigned __int16 *
0x180023cab  test    rdx, rdx
0x180023cae  jz      short loc_180023CF0
0x180023cb0  xor     ecx, ecx; int
0x180023cb2  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180023cb7  test    al, al
0x180023cb9  jnz     short loc_180023CF0
0x180023cbb  mov     rdx, [rbx+38h]; unsigned __int16 *
0x180023cbf  mov     ecx, 1; int
0x180023cc4  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180023cc9  test    al, al
0x180023ccb  jnz     short loc_180023CF0
0x180023ccd  cmp     dword ptr [rbx+0F0h], 0
0x180023cd4  jz      short loc_180023CDF
0x180023cd6  mov     rcx, [rbx+40h]
0x180023cda  test    rcx, rcx
0x180023cdd  jnz     short loc_180023CE3
0x180023cdf  mov     rcx, [rbx+38h]; name
0x180023ce3  xor     r8d, r8d; pdv
0x180023ce6  lea     edx, [r8+10h]; fl
0x180023cea  call    cs:__imp_RemoveFontResourceExW
0x180023cf0  mov     rcx, [rbx+38h]; pv
0x180023cf4  mov     dword ptr [rbx+0F0h], 0
0x180023cfe  call    cs:__imp_CoTaskMemFree
0x180023d04  mov     rcx, [rbx+40h]; pv
0x180023d08  mov     qword ptr [rbx+38h], 0
0x180023d10  call    cs:__imp_CoTaskMemFree
0x180023d16  mov     rcx, [rbx+78h]; pidl
0x180023d1a  mov     qword ptr [rbx+40h], 0
0x180023d22  call    cs:__imp_ILFree
0x180023d28  mov     rcx, [rbx+88h]; ho
0x180023d2f  mov     qword ptr [rbx+78h], 0
0x180023d37  test    rcx, rcx
0x180023d3a  jz      short loc_180023D4D
0x180023d3c  call    cs:__imp_DeleteObject
0x180023d42  mov     qword ptr [rbx+88h], 0
0x180023d4d  mov     rcx, [rbx+70h]
0x180023d51  test    rcx, rcx
0x180023d54  jz      short loc_180023D6A
0x180023d56  mov     rax, [rcx]
0x180023d59  mov     rax, [rax+10h]
0x180023d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d62  mov     qword ptr [rbx+70h], 0
0x180023d6a  mov     rcx, [rbx+48h]
0x180023d6e  test    rcx, rcx
0x180023d71  jz      short loc_180023D87
0x180023d73  mov     rax, [rcx]
0x180023d76  mov     rax, [rax+10h]
0x180023d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d7f  mov     qword ptr [rbx+48h], 0
0x180023d87  add     rsp, 20h
0x180023d8b  pop     rbx
0x180023d8c  retn
```
