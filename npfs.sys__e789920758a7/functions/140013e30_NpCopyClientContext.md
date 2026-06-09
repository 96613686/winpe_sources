# NpCopyClientContext

- ea: `0x140013e30`
- end: `0x140013eb5`
- name: `NpCopyClientContext`
- size: `133`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d314`
- `0x14000e1b0`

## callees

- `0x14000fb00`
- `0x140013e30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e93`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140013e82`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140013e82`

## pseudocode

```c
void __fastcall NpCopyClientContext(__int64 a1, void *a2)
{
  char *v3; // rsi

  if ( a2 )
  {
    v3 = *(char **)(a1 + 264);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SeDeleteClientSecurity(*(_QWORD *)(a1 + 264));
      ExFreePoolWithTag(v3, 0);
    }
    if ( *(_QWORD *)(a1 + 264) == -1 )
      NpFreeClientSecurityContext(a2);
    else
      *(_QWORD *)(a1 + 264) = a2;
  }
}

```

## disassembly

```asm
0x140013e30  test    rdx, rdx
0x140013e33  jnz     short loc_140013E37
0x140013e35  retn
0x140013e37  mov     [rsp+arg_8], rbx
0x140013e3c  push    rdi
0x140013e3d  sub     rsp, 20h
0x140013e41  mov     [rsp+28h+arg_0], rsi
0x140013e46  mov     rbx, rdx
0x140013e49  mov     rsi, [rcx+108h]
0x140013e50  mov     rdi, rcx
0x140013e53  lea     rax, [rsi-1]
0x140013e57  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013e5b  jbe     short loc_140013E7F
0x140013e5d  cmp     qword ptr [rdi+108h], 0FFFFFFFFFFFFFFFFh
0x140013e65  mov     rsi, [rsp+28h+arg_0]
0x140013e6a  jz      short loc_140013EA1
0x140013e6c  mov     [rdi+108h], rbx
0x140013e73  mov     rbx, [rsp+28h+arg_8]
0x140013e78  add     rsp, 20h
0x140013e7c  pop     rdi
0x140013e7d  retn
0x140013e7f  mov     rcx, rsi
0x140013e82  call    cs:__imp_SeDeleteClientSecurity
0x140013e89  nop     dword ptr [rax+rax+00h]
0x140013e8e  xor     edx, edx; Tag
0x140013e90  mov     rcx, rsi; P
0x140013e93  call    cs:__imp_ExFreePoolWithTag
0x140013e9a  nop     dword ptr [rax+rax+00h]
0x140013e9f  jmp     short loc_140013E5D
0x140013ea1  mov     rcx, rbx; P
0x140013ea4  call    NpFreeClientSecurityContext
0x140013ea9  mov     rbx, [rsp+28h+arg_8]
0x140013eae  add     rsp, 20h
0x140013eb2  pop     rdi
0x140013eb3  retn
```
