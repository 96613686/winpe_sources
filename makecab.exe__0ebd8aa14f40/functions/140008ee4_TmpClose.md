# TmpClose

- ea: `0x140008ee4`
- end: `0x140008f35`
- name: `TmpClose`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000acd8`
- `0x14000caac`
- `0x14000cb80`

## callees

- `0x140008620`
- `0x140008ee4`

## import_xrefs

- `msvcrt!fclose` at `0x140008efc`
- `msvcrt!fclose` at `0x140008efc`

## pseudocode

```c
__int64 __fastcall TmpClose(__int64 a1, __int64 a2)
{
  FILE *v4; // rcx

  v4 = *(FILE **)a1;
  if ( v4 )
  {
    if ( fclose(v4) == -1 )
    {
      ErrSet(a2, (int)"Cannot close %1", *(const char **)(a1 + 16));
      return 0;
    }
    *(_QWORD *)a1 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140008ee4  mov     [rsp+arg_0], rbx
0x140008ee9  push    rdi
0x140008eea  sub     rsp, 20h
0x140008eee  mov     rbx, rcx
0x140008ef1  mov     rdi, rdx
0x140008ef4  mov     rcx, [rcx]; Stream
0x140008ef7  test    rcx, rcx
0x140008efa  jz      short loc_140008F25
0x140008efc  call    cs:__imp_fclose
0x140008f02  cmp     eax, 0FFFFFFFFh
0x140008f05  jnz     short loc_140008F1E
0x140008f07  mov     r8, [rbx+10h]
0x140008f0b  lea     rdx, aCannotClose1; "Cannot close %1"
0x140008f12  mov     rcx, rdi
0x140008f15  call    ErrSet
0x140008f1a  xor     eax, eax
0x140008f1c  jmp     short loc_140008F2A
0x140008f1e  mov     qword ptr [rbx], 0
0x140008f25  mov     eax, 1
0x140008f2a  mov     rbx, [rsp+28h+arg_0]
0x140008f2f  add     rsp, 20h
0x140008f33  pop     rdi
0x140008f34  retn
```
