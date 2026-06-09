# CdLookupNextPathEntry

- ea: `0x140016998`
- end: `0x140016a18`
- name: `CdLookupNextPathEntry`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000dc38`
- `0x1400166ac`

## callees

- `0x140016998`
- `0x140016a8c`
- `0x140016c58`

## pseudocode

```c
char __fastcall CdLookupNextPathEntry(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v6; // eax

  *(_DWORD *)(a2 + 24) += a3[3];
  v6 = *(_DWORD *)(a2 + 24);
  if ( *(_BYTE *)(a2 + 29) )
  {
    if ( v6 >= *(_DWORD *)(a2 + 12) )
      return 0;
  }
  else if ( v6 >= 0x800 )
  {
    CdMapPathTableBlock(
      2048,
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 88LL),
      (union _LARGE_INTEGER)(unsigned int)(*(_DWORD *)(a2 + 8) + 2048),
      a2);
    *(_DWORD *)(a2 + 24) -= 2048;
  }
  return CdUpdatePathEntryFromRawPathEntry(a1, *a3 + 1, 1, a2, (__int64)a3);
}

```

## disassembly

```asm
0x140016998  mov     [rsp+arg_0], rbx
0x14001699d  mov     [rsp+arg_8], rsi
0x1400169a2  push    rdi
0x1400169a3  sub     rsp, 30h
0x1400169a7  mov     eax, [r8+0Ch]
0x1400169ab  mov     rdi, r8
0x1400169ae  add     [rdx+18h], eax
0x1400169b1  mov     rbx, rdx
0x1400169b4  cmp     byte ptr [rdx+1Dh], 0
0x1400169b8  mov     rsi, rcx
0x1400169bb  mov     eax, [rdx+18h]
0x1400169be  jz      short loc_1400169C9
0x1400169c0  cmp     eax, [rdx+0Ch]
0x1400169c3  jb      short loc_1400169F0
0x1400169c5  xor     al, al
0x1400169c7  jmp     short loc_140016A07
0x1400169c9  mov     ecx, 800h
0x1400169ce  cmp     eax, ecx
0x1400169d0  jb      short loc_1400169F0
0x1400169d2  mov     r8d, [rdx+8]
0x1400169d6  mov     r9, rbx
0x1400169d9  mov     rdx, [rsi+10h]
0x1400169dd  add     r8d, ecx
0x1400169e0  mov     rdx, [rdx+58h]
0x1400169e4  call    CdMapPathTableBlock
0x1400169e9  add     dword ptr [rbx+18h], 0FFFFF800h
0x1400169f0  mov     edx, [rdi]
0x1400169f2  mov     r9, rbx
0x1400169f5  inc     edx
0x1400169f7  mov     [rsp+38h+var_18], rdi
0x1400169fc  mov     r8b, 1
0x1400169ff  mov     rcx, rsi
0x140016a02  call    CdUpdatePathEntryFromRawPathEntry
0x140016a07  mov     rbx, [rsp+38h+arg_0]
0x140016a0c  mov     rsi, [rsp+38h+arg_8]
0x140016a11  add     rsp, 30h
0x140016a15  pop     rdi
0x140016a16  retn
```
