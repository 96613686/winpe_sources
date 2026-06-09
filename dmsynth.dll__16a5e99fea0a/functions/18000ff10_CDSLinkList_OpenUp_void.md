# CDSLinkList::OpenUp(void)

- ea: `0x18000ff10`
- end: `0x18000ff67`
- name: `?OpenUp@CDSLinkList@@QEAAHXZ`
- size: `87`
- prototype: `__int64 __fastcall(CDSLinkList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed30`

## callees

- `0x18000ff10`
- `0x180011cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ff4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ff4f`

## pseudocode

```c
__int64 __fastcall CDSLinkList::OpenUp(CDSLinkList *this)
{
  if ( !dword_18001E5C8 )
  {
    dword_18001E5C8 = 1;
    if ( !GetRegValueDword((const char *)this, "DSLResolution", (BYTE *)&dword_18001E614) )
      dword_18001E614 = 20;
    try
    {
      InitializeCriticalSection(&CriticalSection);
    }
    catch ( ... )
    {
      dword_18001E5C8 = 0;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000ff10  sub     rsp, 28h
0x18000ff14  cmp     cs:dword_18001E5C8, 0
0x18000ff1b  jnz     short loc_18000FF56
0x18000ff1d  mov     cs:dword_18001E5C8, 1
0x18000ff27  lea     r8, dword_18001E614; unsigned int *
0x18000ff2e  lea     rdx, aDslresolution; "DSLResolution"
0x18000ff35  call    ?GetRegValueDword@@YAHPEBD0PEAK@Z; GetRegValueDword(char const *,char const *,ulong *)
0x18000ff3a  test    eax, eax
0x18000ff3c  jnz     short loc_18000FF48
0x18000ff3e  mov     cs:dword_18001E614, 14h
0x18000ff48  lea     rcx, CriticalSection; lpCriticalSection
0x18000ff4f  call    cs:__imp_InitializeCriticalSection
0x18000ff55  nop
0x18000ff56  mov     eax, 1
0x18000ff5b  add     rsp, 28h
0x18000ff5f  retn
0x18000ff60  xor     eax, eax
0x18000ff62  add     rsp, 28h
0x18000ff66  retn
```
