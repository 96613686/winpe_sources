# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140007c34`
- end: `0x140007c64`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000ac68`
- `0x14000ac7a`
- `0x14000ac90`
- `0x14000acbc`
- `0x14000acce`
- `0x14000ace0`
- `0x14000acf2`
- `0x14000ad57`

## callees

- `0x140007c34`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007c47`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007c47`

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
0x140007c34  push    rbx
0x140007c36  sub     rsp, 20h
0x140007c3a  cmp     qword ptr [rcx+18h], 8
0x140007c3f  mov     rbx, rcx
0x140007c42  jb      short loc_140007C4D
0x140007c44  mov     rcx, [rcx]
0x140007c47  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007c4d  xor     eax, eax
0x140007c4f  mov     qword ptr [rbx+18h], 7
0x140007c57  mov     [rbx+10h], rax
0x140007c5b  mov     [rbx], ax
0x140007c5e  add     rsp, 20h
0x140007c62  pop     rbx
0x140007c63  retn
```
