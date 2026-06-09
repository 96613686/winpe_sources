# SysInfo::Uninit(SysInfo *,bool)

- ea: `0x18001ff60`
- end: `0x18002002d`
- name: `?Uninit@SysInfo@@SAXPEAU1@_N@Z`
- size: `205`
- prototype: `void __fastcall(SysInfo *bIsDynamicUnload, bool psys)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fb94`

## callees

- `0x18001ff60`
- `0x180020034`
- `0x1800ce010`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001fff4`
- `GDI32!DeleteDC` at `0x18001fff4`
- `GDI32!DeleteObject` at `0x18001ffdc`
- `GDI32!DeleteObject` at `0x18001ffe4`
- `GDI32!DeleteObject` at `0x18001ffec`
- `GDI32!DeleteObject` at `0x18001ffdc`
- `GDI32!DeleteObject` at `0x18001ffe4`
- `GDI32!DeleteObject` at `0x18001ffec`
- `GDI32!SelectObject` at `0x18001ffd4`
- `GDI32!SelectObject` at `0x18001ffd4`

## pseudocode

```c
void __fastcall SysInfo::Uninit(SysInfo *bIsDynamicUnload, bool psys)
{
  if ( g_sys.m_hbmpStock )
    SelectObject(g_sys.m_hdc, g_sys.m_hbmpStock);
  if ( g_sys.m_hbmpColor )
    DeleteObject(g_sys.m_hbmpColor);
  if ( g_sys.m_hpalDefault )
    DeleteObject(g_sys.m_hpalDefault);
  if ( g_sys.m_hpalRainbow )
    DeleteObject(g_sys.m_hpalRainbow);
  if ( g_sys.m_hdc )
    DeleteDC(g_sys.m_hdc);
  if ( g_sys.m_pstg )
  {
    if ( psys )
      ((void (*)(void))g_sys.m_pstg->lpVtbl->Release)();
    g_sys.m_pstg = 0;
    g_sys.m_cStreams = 0;
    g_sys.m_stmixNext = 1;
  }
  OaDeleteCriticalSection(&g_sys.m_critDCBusy);
  OaDeleteCriticalSection(&g_sys.m_critMemberBusy);
}

```

## disassembly

```asm
0x18001ff60  push    rbx
0x18001ff62  sub     rsp, 20h
0x18001ff66  mov     bl, bIsDynamicUnload
0x18001ff68  mov     rdx, cs:?g_sys@@3USysInfo@@A.m_hbmpStock; h
0x18001ff6f  test    rdx, rdx
0x18001ff72  jnz     short loc_18001FFCD
0x18001ff74  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hbmpColor; ho
0x18001ff7b  test    rcx, rcx
0x18001ff7e  jnz     short loc_18001FFDC
0x18001ff80  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hpalDefault; ho
0x18001ff87  test    rcx, rcx
0x18001ff8a  jnz     short loc_18001FFE4
0x18001ff8c  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hpalRainbow; ho
0x18001ff93  test    rcx, rcx
0x18001ff96  jnz     short loc_18001FFEC
0x18001ff98  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hdc; hdc
0x18001ff9f  test    rcx, rcx
0x18001ffa2  jnz     short loc_18001FFF4
0x18001ffa4  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_pstg; SysInfo g_sys ...
0x18001ffab  test    rcx, rcx
0x18001ffae  jnz     short loc_18001FFFC
0x18001ffb0  lea     rcx, ?g_sys@@3USysInfo@@A.m_critDCBusy; pCs
0x18001ffb7  call    OaDeleteCriticalSection
0x18001ffbc  lea     rcx, ?g_sys@@3USysInfo@@A.m_critMemberBusy; SysInfo g_sys ...
0x18001ffc3  add     rsp, 20h
0x18001ffc7  pop     rbx
0x18001ffc8  jmp     OaDeleteCriticalSection
0x18001ffcd  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hdc; hdc
0x18001ffd4  call    cs:__imp_SelectObject
0x18001ffda  jmp     short loc_18001FF74
0x18001ffdc  call    cs:__imp_DeleteObject
0x18001ffe2  jmp     short loc_18001FF80
0x18001ffe4  call    cs:__imp_DeleteObject
0x18001ffea  jmp     short loc_18001FF8C
0x18001ffec  call    cs:__imp_DeleteObject
0x18001fff2  jmp     short loc_18001FF98
0x18001fff4  call    cs:__imp_DeleteDC
0x18001fffa  jmp     short loc_18001FFA4
0x18001fffc  test    bl, bl
0x18001fffe  jz      short loc_18002000C
0x180020000  mov     rax, [rcx]
0x180020003  mov     rax, [rax+10h]
0x180020007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002000c  mov     cs:?g_sys@@3USysInfo@@A.m_pstg, 0; SysInfo g_sys ...
0x180020017  mov     cs:?g_sys@@3USysInfo@@A.m_cStreams, 0; SysInfo g_sys ...
0x180020021  mov     cs:?g_sys@@3USysInfo@@A.m_stmixNext, 1; SysInfo g_sys ...
0x18002002b  jmp     short loc_18001FFB0
```
