# TextFileLogger::Unlock(void)

- ea: `0x180013c78`
- end: `0x180013cd0`
- name: `?Unlock@TextFileLogger@@AEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(TextFileLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013428`

## callees

- `0x180011828`
- `0x180013c78`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180013cbc`
- `IisRTL!PuDbgPrint` at `0x180013cbc`

## string_xrefs

- `0x180013cb5`: `inetsrv\iis\mb\config\src\inc\TextFileLogger.h`

## pseudocode

```c
__int64 __fastcall TextFileLogger::Unlock(TextFileLogger *this)
{
  if ( !CSafeAutoCriticalSection::Unlock((CSafeAutoCriticalSection *)&TextFileLogger::_cs) )
    return 0;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\config\\src\\inc\\TextFileLogger.h",
      245,
      "TextFileLogger::Unlock",
      "Could not unlock critical section\n");
  return 2147942414LL;
}

```

## disassembly

```asm
0x180013c78  sub     rsp, 38h
0x180013c7c  lea     rcx, ?_cs@TextFileLogger@@0VCSafeAutoCriticalSection@@A; this
0x180013c83  call    ?Unlock@CSafeAutoCriticalSection@@QEAAKXZ; CSafeAutoCriticalSection::Unlock(void)
0x180013c88  test    eax, eax
0x180013c8a  jz      short loc_180013CC9
0x180013c8c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013c93  jz      short loc_180013CC2
0x180013c95  mov     rcx, cs:g_pDebug
0x180013c9c  lea     rax, aCouldNotUnlock; "Could not unlock critical section\n"
0x180013ca3  lea     r9, aTextfilelogger_1; "TextFileLogger::Unlock"
0x180013caa  mov     [rsp+38h+var_18], rax
0x180013caf  mov     r8d, 0F5h
0x180013cb5  lea     rdx, aInetsrvIisMbCo_8; "inetsrv\\iis\\mb\\config\\src\\inc\\Tex"...
0x180013cbc  call    cs:__imp_PuDbgPrint
0x180013cc2  mov     eax, 8007000Eh
0x180013cc7  jmp     short loc_180013CCB
0x180013cc9  xor     eax, eax
0x180013ccb  add     rsp, 38h
0x180013ccf  retn
```
