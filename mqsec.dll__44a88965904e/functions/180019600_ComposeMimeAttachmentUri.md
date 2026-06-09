# ComposeMimeAttachmentUri

- ea: `0x180019600`
- end: `0x18001973d`
- name: `ComposeMimeAttachmentUri`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019750`

## callees

- `0x18000ae20`
- `0x18001722c`
- `0x180019c70`

## import_xrefs

- `msvcrt!free` at `0x18001971f`
- `msvcrt!free` at `0x18001971f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall ComposeMimeAttachmentUri(const char *a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rcx
  int v3; // edi
  int v4; // esi
  int v5; // ebp
  int v6; // r14d
  int v7; // r15d
  int v8; // r12d
  int v9; // r13d
  unsigned int v10; // eax
  int v12; // [rsp+90h] [rbp-68h]
  unsigned __int64 v13; // [rsp+98h] [rbp-60h]
  char *v14; // [rsp+A0h] [rbp-58h]
  int v17; // [rsp+110h] [rbp+18h]
  int v18; // [rsp+118h] [rbp+20h]

  v13 = mqstrlen(a1) + 41;
  v14 = (char *)MmAllocate((unsigned int)v13);
  v2 = a2;
  v3 = a2[15];
  v4 = a2[14];
  v5 = a2[13];
  v6 = a2[12];
  v7 = a2[11];
  v8 = a2[10];
  v9 = a2[9];
  LODWORD(a2) = a2[8];
  v17 = *((unsigned __int16 *)v2 + 3);
  v18 = *((unsigned __int16 *)v2 + 2);
  v12 = *(_DWORD *)v2;
  v10 = mqstrlen(a1);
  StringCchPrintfA(
    v14,
    v13,
    "%s%.*s%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    "cid:",
    v10,
    a1,
    v12,
    v18,
    v17,
    (_DWORD)a2,
    v9,
    v8,
    v7,
    v6,
    v5,
    v4,
    v3);
  free(0);
  return v14;
}

```

## disassembly

```asm
0x180019600  mov     [rsp+arg_8], rdx
0x180019605  mov     [rsp+arg_0], rcx
0x18001960a  push    rbx
0x18001960b  push    rbp
0x18001960c  push    rsi
0x18001960d  push    rdi
0x18001960e  push    r12
0x180019610  push    r13
0x180019612  push    r14
0x180019614  push    r15
0x180019616  sub     rsp, 0B8h
0x18001961d  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x180019622  add     eax, 29h ; ')'
0x180019625  mov     [rsp+0F8h+var_60], rax
0x18001962d  mov     ecx, eax; unsigned __int64
0x18001962f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180019634  mov     rbx, rax
0x180019637  mov     [rsp+0F8h+var_58], rax
0x18001963f  mov     rcx, [rsp+0F8h+arg_8]
0x180019647  movzx   edi, byte ptr [rcx+0Fh]
0x18001964b  movzx   esi, byte ptr [rcx+0Eh]
0x18001964f  movzx   ebp, byte ptr [rcx+0Dh]
0x180019653  movzx   r14d, byte ptr [rcx+0Ch]
0x180019658  movzx   r15d, byte ptr [rcx+0Bh]
0x18001965d  movzx   r12d, byte ptr [rcx+0Ah]
0x180019662  movzx   r13d, byte ptr [rcx+9]
0x180019667  movzx   eax, byte ptr [rcx+8]
0x18001966b  mov     dword ptr [rsp+0F8h+arg_8], eax
0x180019672  movzx   eax, word ptr [rcx+6]
0x180019676  mov     [rsp+0F8h+arg_10], eax
0x18001967d  movzx   eax, word ptr [rcx+4]
0x180019681  mov     [rsp+0F8h+arg_18], eax
0x180019688  mov     eax, [rcx]
0x18001968a  mov     [rsp+0F8h+var_68], eax
0x180019691  mov     rcx, [rsp+0F8h+arg_0]; char *
0x180019699  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x18001969e  mov     [rsp+0F8h+var_78], edi
0x1800196a5  mov     [rsp+0F8h+var_80], esi
0x1800196a9  mov     [rsp+0F8h+var_88], ebp
0x1800196ad  mov     [rsp+0F8h+var_90], r14d
0x1800196b2  mov     [rsp+0F8h+var_98], r15d
0x1800196b7  mov     [rsp+0F8h+var_A0], r12d
0x1800196bc  mov     [rsp+0F8h+var_A8], r13d
0x1800196c1  mov     ecx, dword ptr [rsp+0F8h+arg_8]
0x1800196c8  mov     [rsp+0F8h+var_B0], ecx
0x1800196cc  mov     ecx, [rsp+0F8h+arg_10]
0x1800196d3  mov     [rsp+0F8h+var_B8], ecx
0x1800196d7  mov     ecx, [rsp+0F8h+arg_18]
0x1800196de  mov     [rsp+0F8h+var_C0], ecx
0x1800196e2  mov     ecx, [rsp+0F8h+var_68]
0x1800196e9  mov     [rsp+0F8h+var_C8], ecx
0x1800196ed  mov     rcx, [rsp+0F8h+arg_0]
0x1800196f5  mov     [rsp+0F8h+var_D0], rcx
0x1800196fa  mov     [rsp+0F8h+var_D8], eax
0x1800196fe  lea     r9, aCid; "cid:"
0x180019705  lea     r8, aSS08x04x04x02x; "%s%.*s%08x-%04x-%04x-%02x%02x-%02x%02x%"...
0x18001970c  mov     rdx, [rsp+0F8h+var_60]; unsigned __int64
0x180019714  mov     rcx, rbx; char *
0x180019717  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001971c  nop
0x18001971d  xor     ecx, ecx; Block
0x18001971f  call    cs:__imp_free
0x180019725  nop
0x180019726  mov     rax, rbx
0x180019729  add     rsp, 0B8h
0x180019730  pop     r15
0x180019732  pop     r14
0x180019734  pop     r13
0x180019736  pop     r12
0x180019738  pop     rdi
0x180019739  pop     rsi
0x18001973a  pop     rbp
0x18001973b  pop     rbx
0x18001973c  retn
```
