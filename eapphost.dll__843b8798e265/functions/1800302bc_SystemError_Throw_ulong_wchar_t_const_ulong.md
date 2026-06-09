# SystemError::Throw<ulong>(wchar_t const *,ulong)

- ea: `0x1800302bc`
- end: `0x1800302da`
- name: `??$Throw@K@SystemError@@SAXPEB_WK@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030ca8`

## callees

- `0x18002fef4`
- `0x1800302bc`

## string_xrefs

- `0x1800302cd`: `GetWindowsDirectory`

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
0x1800302bc  sub     rsp, 28h
0x1800302c0  test    edx, edx
0x1800302c2  jle     short loc_1800302CD
0x1800302c4  movzx   edx, dx
0x1800302c7  or      edx, 80070000h; int
0x1800302cd  lea     rcx, aGetwindowsdire; "GetWindowsDirectory"
0x1800302d4  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
