# DetermineLogType(ushort const *)

- ea: `0x18001f278`
- end: `0x18001f2d4`
- name: `?DetermineLogType@@YA?AW4EVENTLOGTYPE@@PEBG@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007f70`
- `0x180016084`

## callees

- `0x18001f278`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001f288`
- `msvcrt!_wcsicmp` at `0x18001f2a3`
- `msvcrt!_wcsicmp` at `0x18001f2be`
- `msvcrt!_wcsicmp` at `0x18001f288`
- `msvcrt!_wcsicmp` at `0x18001f2a3`
- `msvcrt!_wcsicmp` at `0x18001f2be`

## string_xrefs

- `0x18001f2b4`: `security`

## pseudocode

```c
__int64 __fastcall DetermineLogType(const wchar_t *a1)
{
  if ( !_wcsicmp(a1, L"application") )
    return 103;
  if ( _wcsicmp(a1, L"system") )
    return _wcsicmp(a1, L"security") != 0 ? 104 : 102;
  return 101;
}

```

## disassembly

```asm
0x18001f278  push    rbx
0x18001f27a  sub     rsp, 20h
0x18001f27e  lea     rdx, aApplication; "application"
0x18001f285  mov     rbx, rcx
0x18001f288  call    cs:__imp__wcsicmp
0x18001f28e  test    eax, eax
0x18001f290  jnz     short loc_18001F299
0x18001f292  mov     eax, 67h ; 'g'
0x18001f297  jmp     short loc_18001F2CE
0x18001f299  lea     rdx, aSystem; "system"
0x18001f2a0  mov     rcx, rbx; String1
0x18001f2a3  call    cs:__imp__wcsicmp
0x18001f2a9  test    eax, eax
0x18001f2ab  jnz     short loc_18001F2B4
0x18001f2ad  mov     eax, 65h ; 'e'
0x18001f2b2  jmp     short loc_18001F2CE
0x18001f2b4  lea     rdx, aSecurity_0; "security"
0x18001f2bb  mov     rcx, rbx; String1
0x18001f2be  call    cs:__imp__wcsicmp
0x18001f2c4  neg     eax
0x18001f2c6  sbb     eax, eax
0x18001f2c8  and     eax, 2
0x18001f2cb  add     eax, 66h ; 'f'
0x18001f2ce  add     rsp, 20h
0x18001f2d2  pop     rbx
0x18001f2d3  retn
```
