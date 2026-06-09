# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x180023c10`
- end: `0x180023c60`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `80`
- prototype: `int(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016584`
- `0x180023c10`

## import_xrefs

- `msvcrt!fwrite` at `0x180023c32`
- `msvcrt!fwrite` at `0x180023c32`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(FILE **this, const void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // eax

  v6 = fwrite(a2, 1u, a3, this[3]);
  *a4 = v6;
  if ( v6 == a3 )
    return 0;
  else
    return Exit(-2147467259, 0);
}

```

## disassembly

```asm
0x180023c10  mov     [rsp+arg_0], rbx
0x180023c15  push    rdi
0x180023c16  sub     rsp, 20h
0x180023c1a  mov     rax, rdx
0x180023c1d  mov     edi, r8d
0x180023c20  mov     rbx, r9
0x180023c23  mov     r8d, r8d; ElementCount
0x180023c26  mov     r9, [rcx+18h]; Stream
0x180023c2a  mov     edx, 1; ElementSize
0x180023c2f  mov     rcx, rax; Buffer
0x180023c32  call    cs:__imp_fwrite
0x180023c39  nop     dword ptr [rax+rax+00h]
0x180023c3e  mov     [rbx], eax
0x180023c40  cmp     eax, edi
0x180023c42  jnz     short loc_180023C48
0x180023c44  xor     eax, eax
0x180023c46  jmp     short loc_180023C54
0x180023c48  xor     edx, edx; unsigned int
0x180023c4a  mov     ecx, 80004005h; int
0x180023c4f  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180023c54  mov     rbx, [rsp+28h+arg_0]
0x180023c59  add     rsp, 20h
0x180023c5d  pop     rdi
0x180023c5e  retn
```
