# DllMain

- ea: `0x1801ed1ac`
- end: `0x1801ed218`
- name: `DllMain`
- size: `108`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180212304`

## callees

- `0x18017a5c4`
- `0x1801cd438`
- `0x1801de9dc`
- `0x1801deb24`
- `0x1801e9394`
- `0x1801ed1ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1801ed1be`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1801ed1be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ed202`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ed202`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  DWriteTraceLogging *v4; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp+20h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_DWriteModuleHandle = hinstDLL;
      DWriteTraceLogging::RegisterClientSideTraceLogging(v4);
      return FontFallbackDataInitialize();
    }
  }
  else
  {
    LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (struct Lock *)&RecentFontCache::globalLock_);
    List<RecentFontCache::FontList,RecentFontCache::FontInstance>::DeleteElements(&RecentFontCache::globalFonts_);
    ++RecentFontCache::globalInvalidCount_;
    LeaveCriticalSection(lpCriticalSection);
    TraceLoggingUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x1801ed1ac  push    rbx
0x1801ed1ae  sub     rsp, 20h
0x1801ed1b2  mov     rbx, rcx
0x1801ed1b5  test    edx, edx
0x1801ed1b7  jz      short loc_1801ED1DA
0x1801ed1b9  cmp     edx, 1
0x1801ed1bc  jnz     short loc_1801ED20D
0x1801ed1be  call    cs:__imp_DisableThreadLibraryCalls
0x1801ed1c4  mov     cs:?g_DWriteModuleHandle@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_DWriteModuleHandle
0x1801ed1cb  call    ?RegisterClientSideTraceLogging@DWriteTraceLogging@@YAXXZ; DWriteTraceLogging::RegisterClientSideTraceLogging(void)
0x1801ed1d0  call    ?FontFallbackDataInitialize@@YA_NXZ; FontFallbackDataInitialize(void)
0x1801ed1d5  movzx   eax, al
0x1801ed1d8  jmp     short loc_1801ED212
0x1801ed1da  lea     rdx, ?globalLock_@RecentFontCache@@0VLock@@A; struct Lock *
0x1801ed1e1  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x1801ed1e6  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1801ed1eb  lea     rcx, ?globalFonts_@RecentFontCache@@0VFontList@1@A; RecentFontCache::FontList RecentFontCache::globalFonts_
0x1801ed1f2  call    ?DeleteElements@?$List@VFontList@RecentFontCache@@UFontInstance@2@@@QEAAXXZ; List<RecentFontCache::FontList,RecentFontCache::FontInstance>::DeleteElements(void)
0x1801ed1f7  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1801ed1fc  inc     cs:?globalInvalidCount_@RecentFontCache@@0IA; uint RecentFontCache::globalInvalidCount_
0x1801ed202  call    cs:__imp_LeaveCriticalSection
0x1801ed208  call    TraceLoggingUnregister_EventUnregister
0x1801ed20d  mov     eax, 1
0x1801ed212  add     rsp, 20h
0x1801ed216  pop     rbx
0x1801ed217  retn
```
