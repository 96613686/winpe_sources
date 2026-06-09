# _PictFreeLibraries(void)

- ea: `0x180025444`
- end: `0x180025521`
- name: `?_PictFreeLibraries@@YAJXZ`
- size: `221`
- prototype: `int __fastcall()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002503c`
- `0x180025144`

## callees

- `0x180025444`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002546d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002549e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002546d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002549e`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254c4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254dc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254f4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180025510`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254c4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254dc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800254f4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180025510`

## pseudocode

```c
__int64 __fastcall _PictFreeLibraries()
{
  if ( g_hURLMonDLL )
  {
    FreeLibrary(g_hURLMonDLL);
    g_hURLMonDLL = 0;
    g_fnCreateURLMoniker = 0;
    g_fnCreateAsyncBindCtx = 0;
    g_fnRegisterBindStatusCallback = 0;
    g_fnRevokeBindStatusCallback = 0;
  }
  if ( g_hFilterDLL )
  {
    FreeLibrary(g_hFilterDLL);
    g_hFilterDLL = 0;
    g_fnFilterCreateInstance = 0;
    if ( ITA_DCWAIT )
      GlobalDeleteAtom(ITA_DCWAIT);
    if ( ITA_DISPLAY )
      GlobalDeleteAtom(ITA_DISPLAY);
    if ( ITA_ABNORMAL )
      GlobalDeleteAtom(ITA_ABNORMAL);
    if ( ITA_FINISHED )
      GlobalDeleteAtom(ITA_FINISHED);
  }
  return 0;
}

```

## disassembly

```asm
0x180025444  push    rbx
0x180025446  sub     rsp, 20h
0x18002544a  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hLibModule
0x180025451  xor     ebx, ebx
0x180025453  test    rcx, rcx
0x180025456  jnz     short loc_18002546D
0x180025458  mov     rcx, cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002545f  test    rcx, rcx
0x180025462  jnz     short loc_18002549E
0x180025464  xor     eax, eax
0x180025466  add     rsp, 20h
0x18002546a  pop     rbx
0x18002546b  retn
0x18002546d  call    cs:__imp_FreeLibrary
0x180025474  nop     dword ptr [rax+rax+00h]
0x180025479  mov     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hURLMonDLL
0x180025480  mov     cs:?g_fnCreateURLMoniker@@3P6AJPEAUIMoniker@@PEBGPEAPEAU1@@ZEA, rbx; long (*g_fnCreateURLMoniker)(IMoniker *,ushort const *,IMoniker * *)
0x180025487  mov     cs:?g_fnCreateAsyncBindCtx@@3P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rbx; long (*g_fnCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x18002548e  mov     cs:?g_fnRegisterBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAPEAU2@K@ZEA, rbx; long (*g_fnRegisterBindStatusCallback)(IBindCtx *,IBindStatusCallback *,IBindStatusCallback * *,ulong)
0x180025495  mov     cs:?g_fnRevokeBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@@ZEA, rbx; long (*g_fnRevokeBindStatusCallback)(IBindCtx *,IBindStatusCallback *)
0x18002549c  jmp     short loc_180025458
0x18002549e  call    cs:__imp_FreeLibrary
0x1800254a5  nop     dword ptr [rax+rax+00h]
0x1800254aa  movzx   ecx, cs:?ITA_DCWAIT@@3GA; nAtom
0x1800254b1  mov     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hFilterDLL
0x1800254b8  mov     cs:?g_fnFilterCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA, rbx; long (*g_fnFilterCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800254bf  test    cx, cx
0x1800254c2  jz      short loc_1800254D0
0x1800254c4  call    cs:__imp_GlobalDeleteAtom
0x1800254cb  nop     dword ptr [rax+rax+00h]
0x1800254d0  movzx   ecx, cs:?ITA_DISPLAY@@3GA; nAtom
0x1800254d7  test    cx, cx
0x1800254da  jz      short loc_1800254E8
0x1800254dc  call    cs:__imp_GlobalDeleteAtom
0x1800254e3  nop     dword ptr [rax+rax+00h]
0x1800254e8  movzx   ecx, cs:?ITA_ABNORMAL@@3GA; nAtom
0x1800254ef  test    cx, cx
0x1800254f2  jz      short loc_180025500
0x1800254f4  call    cs:__imp_GlobalDeleteAtom
0x1800254fb  nop     dword ptr [rax+rax+00h]
0x180025500  movzx   ecx, cs:?ITA_FINISHED@@3GA; nAtom
0x180025507  test    cx, cx
0x18002550a  jz      loc_180025464
0x180025510  call    cs:__imp_GlobalDeleteAtom
0x180025517  nop     dword ptr [rax+rax+00h]
0x18002551c  jmp     loc_180025464
```
