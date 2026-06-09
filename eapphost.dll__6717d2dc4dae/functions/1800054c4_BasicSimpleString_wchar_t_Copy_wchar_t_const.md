# BasicSimpleString<wchar_t>::Copy(wchar_t const *)

- ea: `0x1800054c4`
- end: `0x1800054e2`
- name: `?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z`
- size: `30`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800052c0`
- `0x180012900`
- `0x180015140`
- `0x18001a2f0`
- `0x18001a758`
- `0x18001f2b4`
- `0x180032e90`

## callees

- `0x180005490`
- `0x1800054c4`
- `0x180009844`

## pseudocode

```c
__int64 __fastcall BasicSimpleString<wchar_t>::Copy(void *a1)
{
  if ( a1 )
    std::_WChar_traits<wchar_t>::length();
  return BasicSimpleString<wchar_t>::Copy(a1);
}

```

## disassembly

```asm
0x1800054c4  sub     rsp, 28h
0x1800054c8  test    rcx, rcx
0x1800054cb  jz      short loc_1800054D4
0x1800054cd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800054d2  jmp     short loc_1800054D6
0x1800054d4  xor     eax, eax
0x1800054d6  mov     rdx, rax
0x1800054d9  add     rsp, 28h
0x1800054dd  jmp     ?Copy@?$BasicSimpleString@_W@@CAPEA_WPEB_W_K@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *,unsigned __int64)
```
