# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002ffc`
- end: `0x18000302c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b030`
- `0x18000b2e2`
- `0x18000b2f4`
- `0x18000b306`
- `0x18000b318`
- `0x18000b37e`
- `0x18000b424`
- `0x18000b465`
- `0x18000b4d1`

## callees

- `0x180002ffc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000300f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000300f`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 24) >= 8u )
    operator delete(*(void **)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180002ffc  push    rbx
0x180002ffe  sub     rsp, 20h
0x180003002  cmp     qword ptr [rcx+18h], 8
0x180003007  mov     rbx, rcx
0x18000300a  jb      short loc_180003015
0x18000300c  mov     rcx, [rcx]
0x18000300f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003015  xor     eax, eax
0x180003017  mov     qword ptr [rbx+18h], 7
0x18000301f  mov     [rbx+10h], rax
0x180003023  mov     [rbx], ax
0x180003026  add     rsp, 20h
0x18000302a  pop     rbx
0x18000302b  retn
```
