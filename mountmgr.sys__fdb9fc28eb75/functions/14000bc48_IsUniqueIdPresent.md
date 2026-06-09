# IsUniqueIdPresent

- ea: `0x14000bc48`
- end: `0x14000bca3`
- name: `IsUniqueIdPresent`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400119a0`

## callees

- `0x14000bc48`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000bc7d`
- `ntoskrnl!RtlCompareMemory` at `0x14000bc7d`

## pseudocode

```c
char __fastcall IsUniqueIdPresent(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  _WORD *v5; // rdx
  SIZE_T v6; // rbx

  v2 = (_QWORD *)(a1 + 16);
  for ( i = *(_QWORD **)(a1 + 16); i != v2; i = (_QWORD *)*i )
  {
    v5 = (_WORD *)i[12];
    if ( *(_WORD *)(a2 + 14) == *v5 )
    {
      v6 = *(unsigned __int16 *)(a2 + 14);
      if ( RtlCompareMemory((const void *)(a2 + *(unsigned __int16 *)(a2 + 12)), v5 + 1, v6) == v6 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000bc48  push    rbx
0x14000bc4a  push    rbp
0x14000bc4b  push    rsi
0x14000bc4c  push    rdi
0x14000bc4d  sub     rsp, 28h
0x14000bc51  lea     rsi, [rcx+10h]
0x14000bc55  mov     rbp, rdx
0x14000bc58  mov     rdi, [rsi]
0x14000bc5b  cmp     rdi, rsi
0x14000bc5e  jz      short loc_14000BC97
0x14000bc60  mov     rdx, [rdi+60h]
0x14000bc64  movzx   eax, word ptr [rbp+0Eh]
0x14000bc68  cmp     ax, [rdx]
0x14000bc6b  jnz     short loc_14000BC8E
0x14000bc6d  movzx   ecx, word ptr [rbp+0Ch]
0x14000bc71  add     rdx, 2; Source2
0x14000bc75  add     rcx, rbp; Source1
0x14000bc78  mov     r8d, eax; Length
0x14000bc7b  mov     ebx, eax
0x14000bc7d  call    cs:__imp_RtlCompareMemory
0x14000bc84  nop     dword ptr [rax+rax+00h]
0x14000bc89  cmp     rax, rbx
0x14000bc8c  jz      short loc_14000BC93
0x14000bc8e  mov     rdi, [rdi]
0x14000bc91  jmp     short loc_14000BC5B
0x14000bc93  mov     al, 1
0x14000bc95  jmp     short loc_14000BC99
0x14000bc97  xor     al, al
0x14000bc99  add     rsp, 28h
0x14000bc9d  pop     rdi
0x14000bc9e  pop     rsi
0x14000bc9f  pop     rbp
0x14000bca0  pop     rbx
0x14000bca1  retn
```
