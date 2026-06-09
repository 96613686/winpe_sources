# SystemError::Throw<ulong>(wchar_t const *,ulong)

- ea: `0x18002f184`
- end: `0x18002f1a2`
- name: `??$Throw@K@SystemError@@SAXPEB_WK@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002faa0`

## callees

- `0x18002edf4`
- `0x18002f184`

## string_xrefs

- `0x18002f195`: `GetWindowsDirectory`

## pseudocode

```c
void __fastcall __noreturn SystemError::Throw<unsigned long>(__int64 a1, signed int a2)
{
  if ( a2 > 0 )
    a2 = (unsigned __int16)a2 | 0x80070000;
  SystemError::ThrowHelper(L"GetWindowsDirectory", a2);
}

```

## disassembly

```asm
0x18002f184  sub     rsp, 28h
0x18002f188  test    edx, edx
0x18002f18a  jle     short loc_18002F195
0x18002f18c  movzx   edx, dx
0x18002f18f  or      edx, 80070000h; int
0x18002f195  lea     rcx, aGetwindowsdire; "GetWindowsDirectory"
0x18002f19c  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
