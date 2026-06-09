# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140003938`
- end: `0x140003968`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000e3cf`
- `0x14000ebc7`
- `0x14000ebd9`
- `0x14000ebfd`
- `0x14000ec52`
- `0x14000ec64`
- `0x14000ecd2`
- `0x14000ece4`
- `0x14000ed08`
- `0x14000ed1e`
- `0x14000ed34`
- `0x14000ed76`
- `0x14000ed9e`
- `0x14000ee6c`

## callees

- `0x140003938`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000394b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000394b`

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
0x140003938  push    rbx
0x14000393a  sub     rsp, 20h
0x14000393e  cmp     qword ptr [rcx+18h], 8
0x140003943  mov     rbx, rcx
0x140003946  jb      short loc_140003951
0x140003948  mov     rcx, [rcx]
0x14000394b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003951  xor     eax, eax
0x140003953  mov     qword ptr [rbx+18h], 7
0x14000395b  mov     [rbx+10h], rax
0x14000395f  mov     [rbx], ax
0x140003962  add     rsp, 20h
0x140003966  pop     rbx
0x140003967  retn
```
