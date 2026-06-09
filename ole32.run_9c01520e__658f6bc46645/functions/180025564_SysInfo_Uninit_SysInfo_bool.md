# SysInfo::Uninit(SysInfo *,bool)

- ea: `0x180025564`
- end: `0x18002564c`
- name: `?Uninit@SysInfo@@SAXPEAU1@_N@Z`
- size: `232`
- prototype: `void __fastcall(SysInfo *bIsDynamicUnload, bool psys)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025144`

## callees

- `0x180025528`
- `0x180025564`
- `0x1800d8010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180025610`
- `GDI32!DeleteDC` at `0x180025610`
- `GDI32!DeleteObject` at `0x1800255e6`
- `GDI32!DeleteObject` at `0x1800255f4`
- `GDI32!DeleteObject` at `0x180025602`
- `GDI32!DeleteObject` at `0x1800255e6`
- `GDI32!DeleteObject` at `0x1800255f4`
- `GDI32!DeleteObject` at `0x180025602`
- `GDI32!SelectObject` at `0x1800255d8`
- `GDI32!SelectObject` at `0x1800255d8`

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
0x180025564  push    rbx
0x180025566  sub     rsp, 20h
0x18002556a  mov     bl, bIsDynamicUnload
0x18002556c  mov     rdx, cs:?g_sys@@3USysInfo@@A.m_hbmpStock; h
0x180025573  test    rdx, rdx
0x180025576  jnz     short loc_1800255D1
0x180025578  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hbmpColor; ho
0x18002557f  test    rcx, rcx
0x180025582  jnz     short loc_1800255E6
0x180025584  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hpalDefault; ho
0x18002558b  test    rcx, rcx
0x18002558e  jnz     short loc_1800255F4
0x180025590  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hpalRainbow; ho
0x180025597  test    rcx, rcx
0x18002559a  jnz     short loc_180025602
0x18002559c  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hdc; hdc
0x1800255a3  test    rcx, rcx
0x1800255a6  jnz     short loc_180025610
0x1800255a8  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_pstg; SysInfo g_sys ...
0x1800255af  test    rcx, rcx
0x1800255b2  jnz     short loc_18002561E
0x1800255b4  lea     rcx, ?g_sys@@3USysInfo@@A.m_critDCBusy; pCs
0x1800255bb  call    OaDeleteCriticalSection
0x1800255c0  lea     rcx, ?g_sys@@3USysInfo@@A.m_critMemberBusy; SysInfo g_sys ...
0x1800255c7  add     rsp, 20h
0x1800255cb  pop     rbx
0x1800255cc  jmp     OaDeleteCriticalSection
0x1800255d1  mov     rcx, cs:?g_sys@@3USysInfo@@A.m_hdc; hdc
0x1800255d8  call    cs:__imp_SelectObject
0x1800255df  nop     dword ptr [rax+rax+00h]
0x1800255e4  jmp     short loc_180025578
0x1800255e6  call    cs:__imp_DeleteObject
0x1800255ed  nop     dword ptr [rax+rax+00h]
0x1800255f2  jmp     short loc_180025584
0x1800255f4  call    cs:__imp_DeleteObject
0x1800255fb  nop     dword ptr [rax+rax+00h]
0x180025600  jmp     short loc_180025590
0x180025602  call    cs:__imp_DeleteObject
0x180025609  nop     dword ptr [rax+rax+00h]
0x18002560e  jmp     short loc_18002559C
0x180025610  call    cs:__imp_DeleteDC
0x180025617  nop     dword ptr [rax+rax+00h]
0x18002561c  jmp     short loc_1800255A8
0x18002561e  test    bl, bl
0x180025620  jz      short loc_18002562E
0x180025622  mov     rax, [rcx]
0x180025625  mov     rax, [rax+10h]
0x180025629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002562e  and     cs:?g_sys@@3USysInfo@@A.m_pstg, 0; SysInfo g_sys ...
0x180025636  and     cs:?g_sys@@3USysInfo@@A.m_cStreams, 0; SysInfo g_sys ...
0x18002563d  mov     cs:?g_sys@@3USysInfo@@A.m_stmixNext, 1; SysInfo g_sys ...
0x180025647  jmp     loc_1800255B4
```
