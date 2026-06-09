# Pku2uDeleteKernelContext

- ea: `0x140021d20`
- end: `0x140021daa`
- name: `Pku2uDeleteKernelContext`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007008`
- `0x140021d20`
- `0x140029d94`
- `0x140029f3c`

## string_xrefs

- `0x140021d39`: `Pku2uDeleteKernelContext called\n`

## pseudocode

```c
__int64 __fastcall Pku2uDeleteKernelContext(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rdi
  __int64 v4; // rax
  int v6; // ebx

  v2 = a2;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uDeleteKernelContext called\n");
  LOBYTE(a2) = 1;
  v4 = Pku2uReferenceContext(a1, a2);
  if ( v4 )
  {
    *v2 = *(_QWORD *)(v4 + 48);
    v6 = *(_DWORD *)(v4 + 104) & 0x100;
    Pku2uDereferenceContext((PVOID)v4);
    return v6 != 0 ? 0x90323 : 0;
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(2, "Failed to reference context 0x%x by lsa handle\n", a1);
    *v2 = a1;
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x140021d20  mov     [rsp+arg_0], rbx
0x140021d25  push    rdi
0x140021d26  sub     rsp, 20h
0x140021d2a  cmp     cs:KsecInfoLevel, 0
0x140021d31  mov     rdi, rdx
0x140021d34  mov     rbx, rcx
0x140021d37  jz      short loc_140021D4A
0x140021d39  lea     rdx, aPku2udeleteker; "Pku2uDeleteKernelContext called\n"
0x140021d40  mov     ecx, 4
0x140021d45  call    KsecDebugOut
0x140021d4a  mov     dl, 1
0x140021d4c  mov     rcx, rbx
0x140021d4f  call    Pku2uReferenceContext
0x140021d54  mov     rcx, rax; P
0x140021d57  test    rax, rax
0x140021d5a  jnz     short loc_140021D80
0x140021d5c  cmp     cs:KsecInfoLevel, eax
0x140021d62  jz      short loc_140021D76
0x140021d64  mov     r8, rbx
0x140021d67  lea     rdx, aFailedToRefere; "Failed to reference context 0x%x by lsa"...
0x140021d6e  lea     ecx, [rax+2]
0x140021d71  call    KsecDebugOut
0x140021d76  mov     [rdi], rbx
0x140021d79  mov     eax, 0C0000008h
0x140021d7e  jmp     short loc_140021D9E
0x140021d80  mov     rax, [rax+30h]
0x140021d84  mov     [rdi], rax
0x140021d87  mov     ebx, [rcx+68h]
0x140021d8a  and     ebx, 100h
0x140021d90  call    Pku2uDereferenceContext
0x140021d95  neg     ebx
0x140021d97  sbb     eax, eax
0x140021d99  and     eax, 90323h
0x140021d9e  mov     rbx, [rsp+28h+arg_0]
0x140021da3  add     rsp, 20h
0x140021da7  pop     rdi
0x140021da8  retn
```
