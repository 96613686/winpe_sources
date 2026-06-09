# MsQuicRelease

- ea: `0x140025700`
- end: `0x14002577a`
- name: `MsQuicRelease`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140025660`
- `0x140028200`

## callees

- `0x140025700`
- `0x140025780`
- `0x1400337e4`
- `0x14003eb54`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140025704`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025704`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025719`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025719`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002575c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002575c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025768`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025768`

## string_xrefs

- `0x14003e7bc`: `MsQuicLib.OpenRefCount > 0`

## pseudocode

```c
void MsQuicRelease()
{
  __int64 v0; // rcx

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&PushLock, 0);
  if ( !word_14005C55A )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\library.c", 768, "MsQuicLib.OpenRefCount > 0");
    __int2c();
  }
  if ( (Microsoft_QuicEnableBits & 1) != 0 )
    McTemplateU0_EtwWriteTransfer(v0, QuicLibraryRelease);
  if ( !--word_14005C55A )
    MsQuicLibraryUninitialize();
  ExReleasePushLockExclusiveEx(&PushLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140025700  sub     rsp, 28h
0x140025704  call    cs:__imp_KeEnterCriticalRegion
0x14002570b  nop     dword ptr [rax+rax+00h]
0x140025710  xor     edx, edx
0x140025712  lea     rcx, PushLock
0x140025719  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140025720  nop     dword ptr [rax+rax+00h]
0x140025725  cmp     cs:word_14005C55A, 0
0x14002572d  jbe     loc_14003E7BC
0x140025733  test    cs:Microsoft_QuicEnableBits, 1
0x14002573a  jnz     loc_14003E7DB
0x140025740  mov     eax, 0FFFFh
0x140025745  add     cs:word_14005C55A, ax
0x14002574c  jnz     short loc_140025753
0x14002574e  call    MsQuicLibraryUninitialize
0x140025753  xor     edx, edx
0x140025755  lea     rcx, PushLock
0x14002575c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140025763  nop     dword ptr [rax+rax+00h]
0x140025768  call    cs:__imp_KeLeaveCriticalRegion
0x14002576f  nop     dword ptr [rax+rax+00h]
0x140025774  add     rsp, 28h
0x140025778  retn
0x14003e7bc  lea     r8, aMsquiclibOpenr_0; "MsQuicLib.OpenRefCount > 0"
0x14003e7c3  mov     edx, 300h
0x14003e7c8  lea     rcx, aCW1SMsquicSrcC_10; "C:\\__w\\1\\s\\msquic\\src\\core\\libra"...
0x14003e7cf  call    CxPlatLogAssert
0x14003e7d4  int     2Ch; Windows NT - assertion failure
0x14003e7d6  jmp     loc_140025733
0x14003e7db  lea     rdx, QuicLibraryRelease
0x14003e7e2  call    McTemplateU0_EtwWriteTransfer
0x14003e7e7  nop
0x14003e7e8  jmp     loc_140025740
```
