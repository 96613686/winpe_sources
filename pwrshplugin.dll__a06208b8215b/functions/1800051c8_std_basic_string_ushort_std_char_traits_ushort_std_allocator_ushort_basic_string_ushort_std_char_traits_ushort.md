# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800051c8`
- end: `0x1800051f8`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009af7`
- `0x18000a092`
- `0x18000a0a4`
- `0x18000a0b6`

## callees

- `0x1800051c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800051db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800051db`

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
0x1800051c8  push    rbx
0x1800051ca  sub     rsp, 20h
0x1800051ce  cmp     qword ptr [rcx+18h], 8
0x1800051d3  mov     rbx, rcx
0x1800051d6  jb      short loc_1800051E1
0x1800051d8  mov     rcx, [rcx]
0x1800051db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800051e1  xor     eax, eax
0x1800051e3  mov     qword ptr [rbx+18h], 7
0x1800051eb  mov     [rbx+10h], rax
0x1800051ef  mov     [rbx], ax
0x1800051f2  add     rsp, 20h
0x1800051f6  pop     rbx
0x1800051f7  retn
```
