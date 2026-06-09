# Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)

- ea: `0x18001b3b8`
- end: `0x18001b3d8`
- name: `?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `32`
- prototype: `__int64 __fastcall(int, HSTRING, HSTRING *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bb64`
- `0x18001dd14`
- `0x18002ee48`
- `0x18002f144`
- `0x18002fb7c`

## callees

- `0x18001b3b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b3ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b3ca`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::FreeAndAssignOnSuccess(int a1, HSTRING a2, HSTRING *a3)
{
  HSTRING v4; // rcx

  if ( a1 >= 0 )
  {
    v4 = *a3;
    *a3 = a2;
    WindowsDeleteString(v4);
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18001b3b8  push    rbx
0x18001b3ba  sub     rsp, 20h
0x18001b3be  mov     ebx, ecx
0x18001b3c0  test    ecx, ecx
0x18001b3c2  js      short loc_18001B3D0
0x18001b3c4  mov     rcx, [r8]; string
0x18001b3c7  mov     [r8], rdx
0x18001b3ca  call    cs:__imp_WindowsDeleteString
0x18001b3d0  mov     eax, ebx
0x18001b3d2  add     rsp, 20h
0x18001b3d6  pop     rbx
0x18001b3d7  retn
```
