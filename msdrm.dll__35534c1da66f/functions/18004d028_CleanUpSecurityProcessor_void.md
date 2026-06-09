# CleanUpSecurityProcessor(void)

- ea: `0x18004d028`
- end: `0x18004d085`
- name: `?CleanUpSecurityProcessor@@YAXXZ`
- size: `93`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018d70`
- `0x18004d134`

## callees

- `0x18004d028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d056`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d03c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d03c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004d06f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004d06f`

## pseudocode

```c
void CleanUpSecurityProcessor(void)
{
  if ( byte_180084E30 )
  {
    EnterCriticalSection(&stru_180084E08);
    LeaveCriticalSection(&stru_180084E08);
    DeleteCriticalSection(&stru_180084E08);
    byte_180084E30 = 0;
  }
  if ( g_hSecurityProcessorInst )
  {
    FreeLibrary(g_hSecurityProcessorInst);
    g_hSecurityProcessorInst = 0;
  }
}

```

## disassembly

```asm
0x18004d028  sub     rsp, 28h
0x18004d02c  cmp     cs:byte_180084E30, 0
0x18004d033  jz      short loc_18004D063
0x18004d035  lea     rcx, stru_180084E08; lpCriticalSection
0x18004d03c  call    cs:__imp_EnterCriticalSection
0x18004d042  lea     rcx, stru_180084E08; lpCriticalSection
0x18004d049  call    cs:__imp_LeaveCriticalSection
0x18004d04f  lea     rcx, stru_180084E08; lpCriticalSection
0x18004d056  call    cs:__imp_DeleteCriticalSection
0x18004d05c  mov     cs:byte_180084E30, 0
0x18004d063  mov     rcx, cs:?g_hSecurityProcessorInst@@3PEAUHINSTANCE__@@EA; hLibModule
0x18004d06a  test    rcx, rcx
0x18004d06d  jz      short loc_18004D080
0x18004d06f  call    cs:__imp_FreeLibrary
0x18004d075  mov     cs:?g_hSecurityProcessorInst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hSecurityProcessorInst
0x18004d080  add     rsp, 28h
0x18004d084  retn
```
