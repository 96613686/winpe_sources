# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800069c0`
- end: `0x1800069f0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ceac`
- `0x18000cebe`
- `0x18000cf1c`
- `0x18000cf2e`
- `0x18000d192`
- `0x18000d434`
- `0x18000d446`
- `0x18000d458`
- `0x18000d484`
- `0x18000d496`

## callees

- `0x1800069c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800069d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800069d3`

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
0x1800069c0  push    rbx
0x1800069c2  sub     rsp, 20h
0x1800069c6  cmp     qword ptr [rcx+18h], 8
0x1800069cb  mov     rbx, rcx
0x1800069ce  jb      short loc_1800069D9
0x1800069d0  mov     rcx, [rcx]
0x1800069d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800069d9  xor     eax, eax
0x1800069db  mov     qword ptr [rbx+18h], 7
0x1800069e3  mov     [rbx+10h], rax
0x1800069e7  mov     [rbx], ax
0x1800069ea  add     rsp, 20h
0x1800069ee  pop     rbx
0x1800069ef  retn
```
