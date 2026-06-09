# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000edb4`
- end: `0x14000edeb`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140015d69`
- `0x140015d8d`
- `0x140015e7f`
- `0x140015eb5`

## callees

- `0x14000edb4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000edc7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000edc7`

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
0x14000edb4  push    rbx
0x14000edb6  sub     rsp, 20h
0x14000edba  cmp     qword ptr [rcx+18h], 8
0x14000edbf  mov     rbx, rcx
0x14000edc2  jb      short loc_14000EDD3
0x14000edc4  mov     rcx, [rcx]
0x14000edc7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000edce  nop     dword ptr [rax+rax+00h]
0x14000edd3  xor     eax, eax
0x14000edd5  mov     qword ptr [rbx+18h], 7
0x14000eddd  mov     [rbx+10h], rax
0x14000ede1  mov     [rbx], ax
0x14000ede4  add     rsp, 20h
0x14000ede8  pop     rbx
0x14000ede9  retn
```
