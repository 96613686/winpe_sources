# NlpPutString

- ea: `0x180018674`
- end: `0x1800186cd`
- name: `NlpPutString`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001844c`
- `0x180018514`
- `0x18001a470`
- `0x18004704c`

## callees

- `0x180018674`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18001869c`
- `ntdll!RtlCopyUnicodeString` at `0x18001869c`
- `ntdll!RtlInitUnicodeString` at `0x1800186c5`
- `ntdll!RtlInitUnicodeString` at `0x1800186c5`

## pseudocode

```c
void __fastcall NlpPutString(struct _UNICODE_STRING *a1, const UNICODE_STRING *a2, PWSTR *a3)
{
  PWSTR v5; // rax
  __int64 Length; // rcx

  if ( a2->Length )
  {
    a1->Buffer = *a3;
    a1->MaximumLength = a2->Length + 2;
    RtlCopyUnicodeString(a1, a2);
    v5 = *a3;
    Length = a2->Length;
    *(PWSTR)((char *)v5 + Length) = 0;
    *a3 = (PWSTR)((char *)v5 + Length + 2);
  }
  else
  {
    RtlInitUnicodeString(a1, 0);
  }
}

```

## disassembly

```asm
0x180018674  mov     [rsp+arg_0], rbx
0x180018679  push    rdi
0x18001867a  sub     rsp, 20h
0x18001867e  cmp     word ptr [rdx], 0
0x180018682  mov     rdi, r8
0x180018685  mov     rbx, rdx
0x180018688  jbe     short loc_1800186C3
0x18001868a  mov     rax, [r8]
0x18001868d  mov     [rcx+8], rax
0x180018691  movzx   eax, word ptr [rdx]
0x180018694  add     ax, 2
0x180018698  mov     [rcx+2], ax
0x18001869c  call    cs:__imp_RtlCopyUnicodeString
0x1800186a2  mov     rax, [rdi]
0x1800186a5  movzx   ecx, word ptr [rbx]; DestinationString
0x1800186a8  mov     word ptr [rcx+rax], 0
0x1800186ae  add     rax, 2
0x1800186b2  add     rax, rcx
0x1800186b5  mov     [rdi], rax
0x1800186b8  mov     rbx, [rsp+28h+arg_0]
0x1800186bd  add     rsp, 20h
0x1800186c1  pop     rdi
0x1800186c2  retn
0x1800186c3  xor     edx, edx; SourceString
0x1800186c5  call    cs:__imp_RtlInitUnicodeString
0x1800186cb  jmp     short loc_1800186B8
```
