# BasicSimpleString<wchar_t>::Copy(wchar_t const *)

- ea: `0x1800056cc`
- end: `0x1800056ea`
- name: `?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005410`
- `0x180013090`
- `0x180015980`
- `0x18001acdc`
- `0x18001b14c`
- `0x18001fdf4`
- `0x180034230`

## callees

- `0x180005698`
- `0x1800056cc`
- `0x180009c40`

## pseudocode

```c
__int64 __fastcall BasicSimpleString<wchar_t>::Copy(__int64 a1)
{
  __int64 v1; // rax

  if ( a1 )
    v1 = std::_WChar_traits<wchar_t>::length(a1);
  else
    v1 = 0;
  return BasicSimpleString<wchar_t>::Copy(a1, v1);
}

```

## disassembly

```asm
0x1800056cc  sub     rsp, 28h
0x1800056d0  test    rcx, rcx
0x1800056d3  jz      short loc_1800056DC
0x1800056d5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800056da  jmp     short loc_1800056DE
0x1800056dc  xor     eax, eax
0x1800056de  mov     rdx, rax
0x1800056e1  add     rsp, 28h
0x1800056e5  jmp     ?Copy@?$BasicSimpleString@_W@@CAPEA_WPEB_W_K@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *,unsigned __int64)
```
