# SystemError::Throw<ulong>(wchar_t const *,ulong)

- ea: `0x180011c0c`
- end: `0x180011c2a`
- name: `??$Throw@K@SystemError@@SAXPEB_WK@Z`
- size: `30`
- prototype: `void __fastcall __noreturn(__int64, signed int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011d8c`

## callees

- `0x180011c0c`
- `0x180012a70`

## string_xrefs

- `0x180011c1d`: `GetWindowsDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn SystemError::Throw<unsigned long>(__int64 a1, signed int a2)
{
  if ( a2 > 0 )
    a2 = (unsigned __int16)a2 | 0x80070000;
  SystemError::ThrowHelper(L"GetWindowsDirectory", a2);
}

```

## disassembly

```asm
0x180011c0c  sub     rsp, 28h
0x180011c10  test    edx, edx
0x180011c12  jle     short loc_180011C1D
0x180011c14  movzx   edx, dx
0x180011c17  or      edx, 80070000h; int
0x180011c1d  lea     rcx, aGetwindowsdire; "GetWindowsDirectory"
0x180011c24  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
