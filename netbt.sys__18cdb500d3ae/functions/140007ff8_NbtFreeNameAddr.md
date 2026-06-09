# NbtFreeNameAddr

- ea: `0x140007ff8`
- end: `0x140008109`
- name: `NbtFreeNameAddr`
- size: `273`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140004038`
- `0x140007df8`
- `0x140007ed8`
- `0x140009600`
- `0x140009ee0`
- `0x14000c570`
- `0x14000e408`
- `0x140014df8`
- `0x14001570c`
- `0x140017214`
- `0x140017a3c`
- `0x140017d80`
- `0x14001b7d0`
- `0x14001d580`
- `0x140022d04`
- `0x140025260`

## callees

- `0x140007ff8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008049`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008063`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008049`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008063`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400080e5`

## pseudocode

```c
void __fastcall NbtFreeNameAddr(unsigned __int16 *P)
{
  void *v2; // rcx
  void *v3; // rcx
  unsigned int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( *((_DWORD *)P + 4) == -87097344 )
  {
    if ( P[65] == 516 )
    {
      v6 = (void *)*((_QWORD *)P + 5);
      if ( v6 )
        ExFreePoolWithTag(v6, 0);
    }
    if ( *((_QWORD *)P + 3) )
    {
      for ( i = 0; i < P[64]; ++i )
      {
        v5 = *(void **)(*((_QWORD *)P + 3) + 16LL * i + 8);
        if ( v5 )
          ExFreePoolWithTag(v5, 0);
      }
      ExFreePoolWithTag(*((PVOID *)P + 3), 0);
    }
  }
  v2 = (void *)*((_QWORD *)P + 6);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = (void *)*((_QWORD *)P + 18);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *((_QWORD *)P + 18) = 0;
    *((_DWORD *)P + 34) = 0;
  }
  *((_DWORD *)P + 4) += 10;
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140007ff8  mov     [rsp+arg_0], rbx
0x140007ffd  push    rdi
0x140007ffe  sub     rsp, 20h
0x140008002  cmp     dword ptr [rcx+10h], 0FACF0000h
0x140008009  mov     rbx, rcx
0x14000800c  jnz     short loc_140008027
0x14000800e  mov     eax, 204h
0x140008013  cmp     [rcx+82h], ax
0x14000801a  jz      loc_1400080C3
0x140008020  cmp     qword ptr [rbx+18h], 0
0x140008025  jnz     short loc_140008071
0x140008027  mov     rcx, [rbx+30h]; P
0x14000802b  test    rcx, rcx
0x14000802e  jnz     short loc_140008061
0x140008030  mov     rcx, [rbx+90h]; P
0x140008037  test    rcx, rcx
0x14000803a  jnz     loc_1400080E3
0x140008040  add     dword ptr [rbx+10h], 0Ah
0x140008044  xor     edx, edx; Tag
0x140008046  mov     rcx, rbx; P
0x140008049  call    cs:__imp_ExFreePoolWithTag
0x140008050  nop     dword ptr [rax+rax+00h]
0x140008055  mov     rbx, [rsp+28h+arg_0]
0x14000805a  add     rsp, 20h
0x14000805e  pop     rdi
0x14000805f  retn
0x140008061  xor     edx, edx; Tag
0x140008063  call    cs:__imp_ExFreePoolWithTag
0x14000806a  nop     dword ptr [rax+rax+00h]
0x14000806f  jmp     short loc_140008030
0x140008071  xor     edi, edi
0x140008073  xor     eax, eax
0x140008075  cmp     ax, [rbx+80h]
0x14000807c  jnb     short loc_1400080AC
0x14000807e  mov     rax, [rbx+18h]
0x140008082  mov     ecx, edi
0x140008084  add     rcx, rcx
0x140008087  mov     rcx, [rax+rcx*8+8]; P
0x14000808c  test    rcx, rcx
0x14000808f  jz      short loc_14000809F
0x140008091  xor     edx, edx; Tag
0x140008093  call    cs:__imp_ExFreePoolWithTag
0x14000809a  nop     dword ptr [rax+rax+00h]
0x14000809f  movzx   eax, word ptr [rbx+80h]
0x1400080a6  inc     edi
0x1400080a8  cmp     edi, eax
0x1400080aa  jb      short loc_14000807E
0x1400080ac  mov     rcx, [rbx+18h]; P
0x1400080b0  xor     edx, edx; Tag
0x1400080b2  call    cs:__imp_ExFreePoolWithTag
0x1400080b9  nop     dword ptr [rax+rax+00h]
0x1400080be  jmp     loc_140008027
0x1400080c3  mov     rcx, [rcx+28h]; P
0x1400080c7  test    rcx, rcx
0x1400080ca  jz      loc_140008020
0x1400080d0  xor     edx, edx; Tag
0x1400080d2  call    cs:__imp_ExFreePoolWithTag
0x1400080d9  nop     dword ptr [rax+rax+00h]
0x1400080de  jmp     loc_140008020
0x1400080e3  xor     edx, edx; Tag
0x1400080e5  call    cs:__imp_ExFreePoolWithTag
0x1400080ec  nop     dword ptr [rax+rax+00h]
0x1400080f1  xor     eax, eax
0x1400080f3  mov     qword ptr [rbx+90h], 0
0x1400080fe  mov     [rbx+88h], eax
0x140008104  jmp     loc_140008040
```
