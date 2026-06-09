# CdLookupPathEntry

- ea: `0x140016a20`
- end: `0x140016a85`
- name: `CdLookupPathEntry`
- size: `101`
- prototype: `__int64 __fastcall(__int64, int, int, char, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000dc38`
- `0x1400135d0`
- `0x1400166ac`

## callees

- `0x140016a8c`
- `0x140016c58`

## pseudocode

```c
__int64 __fastcall CdLookupPathEntry(__int64 a1, int a2, int a3, char a4, __int64 a5)
{
  int v8; // esi
  int v9; // r8d

  v8 = a1;
  CdMapPathTableBlock(a1, *(_QWORD *)(*(_QWORD *)(a1 + 16) + 88LL), a2 & 0xFFFFF800, a5);
  LOBYTE(v9) = a4;
  *(_DWORD *)(a5 + 24) = a2 - *(_DWORD *)(a5 + 8);
  return CdUpdatePathEntryFromRawPathEntry(v8, a3, v9, a5, a5 + 32);
}

```

## disassembly

```asm
0x140016a20  push    rbx
0x140016a22  push    rbp
0x140016a23  push    rsi
0x140016a24  push    rdi
0x140016a25  push    r14
0x140016a27  sub     rsp, 30h
0x140016a2b  mov     rbx, [rsp+58h+arg_20]
0x140016a33  mov     r14d, r8d
0x140016a36  mov     r8d, edx
0x140016a39  mov     edi, edx
0x140016a3b  mov     rdx, [rcx+10h]
0x140016a3f  mov     eax, 0FFFFF800h
0x140016a44  mov     bpl, r9b
0x140016a47  and     r8, rax
0x140016a4a  mov     r9, rbx
0x140016a4d  mov     rsi, rcx
0x140016a50  mov     rdx, [rdx+58h]
0x140016a54  call    CdMapPathTableBlock
0x140016a59  sub     edi, [rbx+8]
0x140016a5c  lea     rax, [rbx+20h]
0x140016a60  mov     r9, rbx
0x140016a63  mov     [rsp+58h+var_38], rax
0x140016a68  mov     r8b, bpl
0x140016a6b  mov     [rbx+18h], edi
0x140016a6e  mov     edx, r14d
0x140016a71  mov     rcx, rsi
0x140016a74  call    CdUpdatePathEntryFromRawPathEntry
0x140016a79  add     rsp, 30h
0x140016a7d  pop     r14
0x140016a7f  pop     rdi
0x140016a80  pop     rsi
0x140016a81  pop     rbp
0x140016a82  pop     rbx
0x140016a83  retn
```
