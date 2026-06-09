# SymbolicLinkNamesFromUniqueIdCount

- ea: `0x140019270`
- end: `0x1400192ea`
- name: `SymbolicLinkNamesFromUniqueIdCount`
- size: `122`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int, const void *, unsigned int, unsigned __int16 *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140019270`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400192d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400192d5`
- `ntoskrnl!RtlCompareMemory` at `0x1400192b7`
- `ntoskrnl!RtlCompareMemory` at `0x1400192b7`

## pseudocode

```c
__int64 __fastcall SymbolicLinkNamesFromUniqueIdCount(
        PCWSTR SourceString,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        _DWORD *a6)
{
  bool v6; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v6 = *SourceString == 35;
  DestinationString = 0;
  if ( !v6 && a2 == 3 && *a5 == a4 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ++*a6;
  }
  return 0;
}

```

## disassembly

```asm
0x140019270  push    rbx
0x140019272  sub     rsp, 30h
0x140019276  cmp     word ptr [rcx], 23h ; '#'
0x14001927a  xorps   xmm0, xmm0
0x14001927d  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140019282  mov     r10, r8
0x140019285  mov     rbx, rcx
0x140019288  jz      short loc_14001929C
0x14001928a  cmp     edx, 3
0x14001928d  jnz     short loc_14001929C
0x14001928f  mov     rcx, [rsp+38h+arg_20]
0x140019294  movzx   eax, word ptr [rcx]
0x140019297  cmp     eax, r9d
0x14001929a  jz      short loc_1400192A5
0x14001929c  xor     eax, eax
0x14001929e  add     rsp, 30h
0x1400192a2  pop     rbx
0x1400192a3  retn
0x1400192a5  mov     [rsp+38h+arg_0], rdi
0x1400192aa  add     rcx, 2; Source1
0x1400192ae  mov     r8d, r9d; Length
0x1400192b1  mov     rdx, r10; Source2
0x1400192b4  mov     edi, r9d
0x1400192b7  call    cs:__imp_RtlCompareMemory
0x1400192be  nop     dword ptr [rax+rax+00h]
0x1400192c3  cmp     rax, rdi
0x1400192c6  mov     rdi, [rsp+38h+arg_0]
0x1400192cb  jnz     short loc_14001929C
0x1400192cd  mov     rdx, rbx; SourceString
0x1400192d0  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400192d5  call    cs:__imp_RtlInitUnicodeString
0x1400192dc  nop     dword ptr [rax+rax+00h]
0x1400192e1  mov     rax, [rsp+38h+arg_28]
0x1400192e6  inc     dword ptr [rax]
0x1400192e8  jmp     short loc_14001929C
```
