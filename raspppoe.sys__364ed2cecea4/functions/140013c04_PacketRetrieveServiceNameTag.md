# PacketRetrieveServiceNameTag

- ea: `0x140013c04`
- end: `0x140013c87`
- name: `PacketRetrieveServiceNameTag`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140016534`

## callees

- `0x140013c04`
- `0x140014370`

## pseudocode

```c
__int64 __fastcall PacketRetrieveServiceNameTag(__int64 a1, _WORD *a2, __int64 *a3, unsigned __int16 a4, __int64 a5)
{
  __int64 result; // rax

  if ( a4 || a5 )
    return RetrieveTag(
             a1,
             257,
             (_DWORD)a2,
             (_DWORD)a3,
             a4,
             a5,
             *(_DWORD *)(a1 + 120) - a4 - a5 + (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(a1 + 112) + 18LL), 8),
             0);
  *a2 = *(_WORD *)(a1 + 16);
  result = *(_QWORD *)(a1 + 24);
  *a3 = result;
  return result;
}

```

## disassembly

```asm
0x140013c04  mov     [rsp+arg_0], rbx
0x140013c09  push    rdi
0x140013c0a  sub     rsp, 40h
0x140013c0e  mov     r11, [rsp+48h+arg_20]
0x140013c13  xor     edi, edi
0x140013c15  mov     rbx, rdx
0x140013c18  mov     r10, rcx
0x140013c1b  test    r9w, r9w
0x140013c1f  jnz     short loc_140013C36
0x140013c21  test    r11, r11
0x140013c24  jnz     short loc_140013C36
0x140013c26  movzx   eax, word ptr [rcx+10h]
0x140013c2a  mov     [rdx], ax
0x140013c2d  mov     rax, [rcx+18h]
0x140013c31  mov     [r8], rax
0x140013c34  jmp     short loc_140013C7B
0x140013c36  mov     rax, [rcx+70h]
0x140013c3a  mov     [rsp+48h+var_10], dil
0x140013c3f  movzx   ecx, word ptr [rax+12h]
0x140013c43  ror     cx, 8
0x140013c47  movzx   edx, cx
0x140013c4a  mov     ecx, [r10+78h]
0x140013c4e  movzx   eax, r9w
0x140013c52  sub     ecx, eax
0x140013c54  sub     ecx, r11d
0x140013c57  add     edx, ecx
0x140013c59  mov     rcx, r10
0x140013c5c  mov     [rsp+48h+var_18], edx
0x140013c60  mov     edx, 101h
0x140013c65  mov     [rsp+48h+var_20], r11
0x140013c6a  mov     [rsp+48h+var_28], r9w
0x140013c70  mov     r9, r8
0x140013c73  mov     r8, rbx
0x140013c76  call    RetrieveTag
0x140013c7b  mov     rbx, [rsp+48h+arg_0]
0x140013c80  add     rsp, 40h
0x140013c84  pop     rdi
0x140013c85  retn
```
