# FatCompareNames

- ea: `0x1400490a8`
- end: `0x140049126`
- name: `FatCompareNames`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400268c0`
- `0x14004912c`
- `0x1400491b4`

## callees

- `0x1400490a8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400490d7`
- `ntoskrnl!RtlCompareMemory` at `0x1400490d7`

## pseudocode

```c
__int64 __fastcall FatCompareNames(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v2; // eax
  SIZE_T v4; // r8
  const void *v6; // rdx
  const void *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // eax

  v2 = *a2;
  v4 = *a1;
  v6 = (const void *)*((_QWORD *)a2 + 1);
  v7 = (const void *)*((_QWORD *)a1 + 1);
  if ( (unsigned __int16)v4 >= (unsigned __int16)v2 )
    v4 = v2;
  v8 = v4;
  v9 = RtlCompareMemory(v7, v6, v4);
  if ( v9 < v8 )
    return *(_BYTE *)(v9 + *((_QWORD *)a1 + 1)) >= *(_BYTE *)(v9 + *((_QWORD *)a2 + 1));
  if ( *a2 <= *a1 )
    return 2 - (unsigned int)(*a2 < *a1);
  return 0;
}

```

## disassembly

```asm
0x1400490a8  mov     [rsp+arg_0], rbx
0x1400490ad  mov     [rsp+arg_8], rsi
0x1400490b2  push    rdi
0x1400490b3  sub     rsp, 20h
0x1400490b7  movzx   eax, word ptr [rdx]
0x1400490ba  mov     rdi, rdx
0x1400490bd  movzx   r8d, word ptr [rcx]
0x1400490c1  mov     rsi, rcx
0x1400490c4  mov     rdx, [rdx+8]; Source2
0x1400490c8  cmp     r8w, ax
0x1400490cc  mov     rcx, [rcx+8]; Source1
0x1400490d0  cmovnb  r8d, eax; Length
0x1400490d4  mov     ebx, r8d
0x1400490d7  call    cs:__imp_RtlCompareMemory
0x1400490de  nop     dword ptr [rax+rax+00h]
0x1400490e3  cmp     eax, ebx
0x1400490e5  jnb     short loc_140049101
0x1400490e7  mov     rcx, [rdi+8]
0x1400490eb  mov     rdx, [rsi+8]
0x1400490ef  mov     r8d, eax
0x1400490f2  xor     eax, eax
0x1400490f4  mov     cl, [r8+rcx]
0x1400490f8  cmp     [r8+rdx], cl
0x1400490fc  setnl   al
0x1400490ff  jmp     short loc_140049115
0x140049101  movzx   eax, word ptr [rdi]
0x140049104  movzx   ecx, word ptr [rsi]
0x140049107  cmp     ax, cx
0x14004910a  jbe     short loc_140049110
0x14004910c  xor     eax, eax
0x14004910e  jmp     short loc_140049115
0x140049110  sbb     eax, eax
0x140049112  add     eax, 2
0x140049115  mov     rbx, [rsp+28h+arg_0]
0x14004911a  mov     rsi, [rsp+28h+arg_8]
0x14004911f  add     rsp, 20h
0x140049123  pop     rdi
0x140049124  retn
```
