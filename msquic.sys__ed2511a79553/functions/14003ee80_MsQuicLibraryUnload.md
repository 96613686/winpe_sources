# MsQuicLibraryUnload

- ea: `0x14003ee80`
- end: `0x14003ef22`
- name: `MsQuicLibraryUnload`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140025660`
- `0x140028200`
- `0x140063360`
- `0x14006503c`

## callees

- `0x1400337e4`
- `0x14003ee80`
- `0x14006324c`

## string_xrefs

- `0x14003eed6`: `MsQuicLib.OpenRefCount == 0`

## pseudocode

```c
signed __int16 MsQuicLibraryUnload()
{
  signed __int16 result; // ax

  if ( (MsQuicLib & 1) == 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\library.c", 83, "MsQuicLib.Loaded");
    __int2c();
  }
  result = _InterlockedDecrement16(&word_14005C558);
  if ( !result )
  {
    if ( (MsQuicLib & 0x20) != 0 )
    {
      if ( word_14005C55A )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\library.c", 85, "MsQuicLib.OpenRefCount == 0");
        __int2c();
      }
      if ( (MsQuicLib & 0x20) != 0 )
      {
        if ( byte_14005C491 )
        {
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\library.c", 86, "!MsQuicLib.InUse");
          __int2c();
        }
      }
    }
    MsQuicLib &= ~1u;
    return CxPlatSystemUnload();
  }
  return result;
}

```

## disassembly

```asm
0x14003ee80  sub     rsp, 28h
0x14003ee84  test    cs:MsQuicLib, 1
0x14003ee8b  jnz     short loc_14003EEA7
0x14003ee8d  lea     r8, aMsquiclibLoade; "MsQuicLib.Loaded"
0x14003ee94  mov     edx, 53h ; 'S'
0x14003ee99  lea     rcx, aCW1SMsquicSrcC_10; "C:\\__w\\1\\s\\msquic\\src\\core\\libra"...
0x14003eea0  call    CxPlatLogAssert
0x14003eea5  int     2Ch; Windows NT - assertion failure
0x14003eea7  or      ecx, 0FFFFFFFFh
0x14003eeaa  mov     eax, ecx
0x14003eeac  lock xadd cs:word_14005C558, ax
0x14003eeb5  add     ax, cx
0x14003eeb8  jnz     short loc_14003EF1C
0x14003eeba  test    cs:MsQuicLib, 20h
0x14003eec1  jz      short loc_14003EF10
0x14003eec3  cmp     cs:word_14005C55A, ax
0x14003eeca  jz      short loc_14003EEE4
0x14003eecc  lea     edx, [rcx+56h]
0x14003eecf  lea     rcx, aCW1SMsquicSrcC_10; "C:\\__w\\1\\s\\msquic\\src\\core\\libra"...
0x14003eed6  lea     r8, aMsquiclibOpenr; "MsQuicLib.OpenRefCount == 0"
0x14003eedd  call    CxPlatLogAssert
0x14003eee2  int     2Ch; Windows NT - assertion failure
0x14003eee4  test    cs:MsQuicLib, 20h
0x14003eeeb  jz      short loc_14003EF10
0x14003eeed  cmp     cs:byte_14005C491, 0
0x14003eef4  jz      short loc_14003EF10
0x14003eef6  lea     r8, aMsquiclibInuse; "!MsQuicLib.InUse"
0x14003eefd  mov     edx, 56h ; 'V'
0x14003ef02  lea     rcx, aCW1SMsquicSrcC_10; "C:\\__w\\1\\s\\msquic\\src\\core\\libra"...
0x14003ef09  call    CxPlatLogAssert
0x14003ef0e  int     2Ch; Windows NT - assertion failure
0x14003ef10  and     cs:MsQuicLib, 0FEh
0x14003ef17  call    CxPlatSystemUnload
0x14003ef1c  add     rsp, 28h
0x14003ef20  retn
```
