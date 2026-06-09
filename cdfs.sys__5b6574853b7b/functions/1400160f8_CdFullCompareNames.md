# CdFullCompareNames

- ea: `0x1400160f8`
- end: `0x140016176`
- name: `CdFullCompareNames`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017638`
- `0x1400178c8`

## callees

- `0x1400160f8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140016139`
- `ntoskrnl!RtlCompareMemory` at `0x140016139`

## pseudocode

```c
__int64 __fastcall CdFullCompareNames(__int64 a1, const void **a2, const void **a3)
{
  __int16 v3; // cx
  unsigned int v6; // edx
  unsigned int v7; // edi
  SIZE_T v8; // rbx
  SIZE_T v9; // rax

  v3 = *(_WORD *)a2;
  if ( *(_WORD *)a2 <= *(_WORD *)a3 )
  {
    v7 = -1;
    v6 = *(unsigned __int16 *)a2;
    if ( v3 == *(_WORD *)a3 )
      v7 = 0;
  }
  else
  {
    v6 = *(unsigned __int16 *)a3;
    v7 = 1;
  }
  v8 = v6;
  v9 = RtlCompareMemory(a2[1], a3[1], v6);
  if ( v9 >= v8 )
    return v7;
  else
    return *((_WORD *)a2[1] + (v9 >> 1)) < *((_WORD *)a3[1] + (v9 >> 1)) ? -1 : 1;
}

```

## disassembly

```asm
0x1400160f8  push    rbx
0x1400160fa  push    rsi
0x1400160fb  push    rdi
0x1400160fc  push    r14
0x1400160fe  sub     rsp, 28h
0x140016102  movzx   ecx, word ptr [rdx]
0x140016105  mov     rsi, r8
0x140016108  movzx   eax, word ptr [r8]
0x14001610c  mov     r14, rdx
0x14001610f  cmp     cx, ax
0x140016112  jbe     short loc_14001611D
0x140016114  mov     edx, eax
0x140016116  mov     edi, 1
0x14001611b  jmp     short loc_14001612C
0x14001611d  or      edi, 0FFFFFFFFh
0x140016120  xor     r8d, r8d
0x140016123  cmp     cx, ax
0x140016126  mov     edx, ecx
0x140016128  cmovz   edi, r8d
0x14001612c  mov     rcx, [r14+8]; Source1
0x140016130  mov     ebx, edx
0x140016132  mov     r8d, edx; Length
0x140016135  mov     rdx, [rsi+8]; Source2
0x140016139  call    cs:__imp_RtlCompareMemory
0x140016140  nop     dword ptr [rax+rax+00h]
0x140016145  mov     rdx, rax
0x140016148  cmp     rax, rbx
0x14001614b  jnb     short loc_140016169
0x14001614d  mov     rax, [rsi+8]
0x140016151  mov     rcx, [r14+8]
0x140016155  shr     rdx, 1
0x140016158  movzx   eax, word ptr [rax+rdx*2]
0x14001615c  cmp     [rcx+rdx*2], ax
0x140016160  sbb     eax, eax
0x140016162  and     eax, 0FFFFFFFEh
0x140016165  inc     eax
0x140016167  jmp     short loc_14001616B
0x140016169  mov     eax, edi
0x14001616b  add     rsp, 28h
0x14001616f  pop     r14
0x140016171  pop     rdi
0x140016172  pop     rsi
0x140016173  pop     rbx
0x140016174  retn
```
