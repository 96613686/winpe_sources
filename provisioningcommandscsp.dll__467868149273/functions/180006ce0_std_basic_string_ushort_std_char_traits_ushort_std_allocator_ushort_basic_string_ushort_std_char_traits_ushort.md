# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180006ce0`
- end: `0x180006d17`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d572`
- `0x18000d584`
- `0x18000d5e2`
- `0x18000d5f4`
- `0x18000d85e`
- `0x18000db00`
- `0x18000db12`
- `0x18000db24`
- `0x18000db51`
- `0x18000db63`

## callees

- `0x180006ce0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006cf3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006cf3`

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
0x180006ce0  push    rbx
0x180006ce2  sub     rsp, 20h
0x180006ce6  cmp     qword ptr [rcx+18h], 8
0x180006ceb  mov     rbx, rcx
0x180006cee  jb      short loc_180006CFF
0x180006cf0  mov     rcx, [rcx]
0x180006cf3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006cfa  nop     dword ptr [rax+rax+00h]
0x180006cff  xor     eax, eax
0x180006d01  mov     qword ptr [rbx+18h], 7
0x180006d09  mov     [rbx+10h], rax
0x180006d0d  mov     [rbx], ax
0x180006d10  add     rsp, 20h
0x180006d14  pop     rbx
0x180006d15  retn
```
