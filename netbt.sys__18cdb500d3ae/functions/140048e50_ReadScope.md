# ReadScope

- ea: `0x140048e50`
- end: `0x140049025`
- name: `ReadScope`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004aaf4`

## callees

- `0x140028040`
- `0x140031140`
- `0x140048e50`
- `0x14004902c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048f64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049014`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049014`
- `ntoskrnl!ExAllocatePool2` at `0x140048ef1`
- `ntoskrnl!ExAllocatePool2` at `0x140048fdf`
- `ntoskrnl!ExAllocatePool2` at `0x140048ef1`
- `ntoskrnl!ExAllocatePool2` at `0x140048fdf`

## pseudocode

```c
void __fastcall ReadScope(__int64 a1, void *a2)
{
  _BYTE *v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 Pool2; // rax
  unsigned __int8 *v7; // r14
  unsigned __int8 *v8; // rbx
  __int16 v9; // dx
  unsigned __int8 *v10; // rcx
  unsigned __int8 v11; // al
  void *v12; // rcx
  void *v13; // rcx
  _BYTE *v14; // rax

  if ( (int)NTReadIniString(a2) < 0 )
    goto LABEL_2;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_BYTE *)v5 );
  if ( !v5 || MEMORY[0] == 42 )
    goto LABEL_21;
  do
    ++v4;
  while ( *(_BYTE *)v4 );
  if ( (unsigned int)v4 <= 0xFF )
  {
    Pool2 = ExAllocatePool2(64, (unsigned int)(v4 + 2), 842031694);
    v7 = (unsigned __int8 *)Pool2;
    if ( Pool2 )
    {
      v8 = (unsigned __int8 *)(Pool2 + 1);
      memmove((void *)(Pool2 + 1), 0, (unsigned int)v4);
      v9 = 2;
      v10 = v7;
      v7[(unsigned int)(v4 + 1)] = 0;
      while ( *v8 )
      {
        if ( *v8 == 46 )
        {
          v11 = (_BYTE)v8 - (_BYTE)v10 - 1;
          *v10 = v11;
          if ( v11 > 0x3Fu )
          {
            NbtLogEvent(2147487965LL, 0, 260);
LABEL_20:
            ExFreePoolWithTag(v7, 0);
            goto LABEL_21;
          }
          if ( (_BYTE)v8 - (_BYTE)v10 == 1 )
            goto LABEL_20;
          v10 = v8;
        }
        ++v8;
        ++v9;
      }
      *v10 = (_BYTE)v8 - (_BYTE)v10 - 1;
      v12 = *(void **)(a1 + 416);
      *(_QWORD *)(a1 + 416) = v7;
      *(_WORD *)(a1 + 412) = v9;
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
      v13 = 0;
      goto LABEL_29;
    }
LABEL_21:
    ExFreePoolWithTag(0, 0);
    goto LABEL_2;
  }
  NbtLogEvent(2147487965LL, 0, 261);
LABEL_2:
  v3 = *(_BYTE **)(a1 + 416);
  if ( !v3 || *v3 )
  {
    v14 = (_BYTE *)ExAllocatePool2(64, 1, 858808910);
    if ( v14 )
    {
      *v14 = 0;
      *(_WORD *)(a1 + 412) = 1;
      *(_QWORD *)(a1 + 416) = v14;
      if ( v3 )
      {
        v13 = v3;
LABEL_29:
        ExFreePoolWithTag(v13, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x140048e50  push    rbx
0x140048e52  push    rbp
0x140048e53  push    rsi
0x140048e54  push    rdi
0x140048e55  push    r12
0x140048e57  push    r14
0x140048e59  sub     rsp, 28h
0x140048e5d  mov     rbp, rcx
0x140048e60  mov     [rsp+58h+Src], 0
0x140048e69  mov     rcx, rdx; KeyHandle
0x140048e6c  lea     r8, [rsp+58h+Src]
0x140048e71  call    NTReadIniString
0x140048e76  mov     r12d, 1
0x140048e7c  test    eax, eax
0x140048e7e  jns     short loc_140048EA7
0x140048e80  mov     rbx, [rbp+1A0h]
0x140048e87  test    rbx, rbx
0x140048e8a  jz      loc_140048FD1
0x140048e90  cmp     byte ptr [rbx], 0
0x140048e93  jnz     loc_140048FD1
0x140048e99  add     rsp, 28h
0x140048e9d  pop     r14
0x140048e9f  pop     r12
0x140048ea1  pop     rdi
0x140048ea2  pop     rsi
0x140048ea3  pop     rbp
0x140048ea4  pop     rbx
0x140048ea5  retn
0x140048ea7  mov     rsi, [rsp+58h+Src]
0x140048eac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140048eb0  mov     rax, rdi
0x140048eb3  inc     rax
0x140048eb6  cmp     byte ptr [rsi+rax], 0
0x140048eba  jnz     short loc_140048EB3
0x140048ebc  test    rax, rax
0x140048ebf  jz      loc_140048F70
0x140048ec5  cmp     byte ptr [rsi], 2Ah ; '*'
0x140048ec8  jz      loc_140048F70
0x140048ece  inc     rdi
0x140048ed1  cmp     byte ptr [rsi+rdi], 0
0x140048ed5  jnz     short loc_140048ECE
0x140048ed7  cmp     edi, 0FFh
0x140048edd  ja      loc_140048FBA
0x140048ee3  lea     edx, [rdi+2]
0x140048ee6  mov     ecx, 40h ; '@'
0x140048eeb  mov     r8d, 3230624Eh
0x140048ef1  call    cs:__imp_ExAllocatePool2
0x140048ef8  nop     dword ptr [rax+rax+00h]
0x140048efd  mov     r14, rax
0x140048f00  test    rax, rax
0x140048f03  jz      short loc_140048F70
0x140048f05  lea     rbx, [rax+1]
0x140048f09  mov     r8d, edi; Size
0x140048f0c  mov     rcx, rbx; void *
0x140048f0f  mov     rdx, rsi; Src
0x140048f12  call    memmove
0x140048f17  lea     eax, [rdi+1]
0x140048f1a  mov     edx, 2
0x140048f1f  mov     rcx, r14
0x140048f22  mov     byte ptr [rax+r14], 0
0x140048f27  mov     al, [rbx]
0x140048f29  test    al, al
0x140048f2b  jz      short loc_140048F86
0x140048f2d  cmp     al, 2Eh ; '.'
0x140048f2f  jnz     short loc_140048F45
0x140048f31  mov     al, bl
0x140048f33  sub     al, cl
0x140048f35  sub     al, r12b
0x140048f38  mov     [rcx], al
0x140048f3a  cmp     al, 3Fh ; '?'
0x140048f3c  ja      short loc_140048F4D
0x140048f3e  test    al, al
0x140048f40  jz      short loc_140048F5F
0x140048f42  mov     rcx, rbx
0x140048f45  add     rbx, r12
0x140048f48  add     edx, r12d
0x140048f4b  jmp     short loc_140048F27
0x140048f4d  xor     edx, edx
0x140048f4f  mov     ecx, 800010DDh
0x140048f54  mov     r8d, 104h
0x140048f5a  call    NbtLogEvent
0x140048f5f  xor     edx, edx; Tag
0x140048f61  mov     rcx, r14; P
0x140048f64  call    cs:__imp_ExFreePoolWithTag
0x140048f6b  nop     dword ptr [rax+rax+00h]
0x140048f70  xor     edx, edx; Tag
0x140048f72  mov     rcx, rsi; P
0x140048f75  call    cs:__imp_ExFreePoolWithTag
0x140048f7c  nop     dword ptr [rax+rax+00h]
0x140048f81  jmp     loc_140048E80
0x140048f86  sub     bl, cl
0x140048f88  sub     bl, r12b
0x140048f8b  mov     [rcx], bl
0x140048f8d  mov     rcx, [rbp+1A0h]; P
0x140048f94  mov     [rbp+1A0h], r14
0x140048f9b  mov     [rbp+19Ch], dx
0x140048fa2  test    rcx, rcx
0x140048fa5  jz      short loc_140048FB5
0x140048fa7  xor     edx, edx; Tag
0x140048fa9  call    cs:__imp_ExFreePoolWithTag
0x140048fb0  nop     dword ptr [rax+rax+00h]
0x140048fb5  mov     rcx, rsi
0x140048fb8  jmp     short loc_140049012
0x140048fba  xor     edx, edx
0x140048fbc  mov     ecx, 800010DDh
0x140048fc1  mov     r8d, 105h
0x140048fc7  call    NbtLogEvent
0x140048fcc  jmp     loc_140048E80
0x140048fd1  mov     r8d, 3330624Eh
0x140048fd7  mov     rdx, r12
0x140048fda  mov     ecx, 40h ; '@'
0x140048fdf  call    cs:__imp_ExAllocatePool2
0x140048fe6  nop     dword ptr [rax+rax+00h]
0x140048feb  test    rax, rax
0x140048fee  jz      loc_140048E99
0x140048ff4  mov     byte ptr [rax], 0
0x140048ff7  mov     [rbp+19Ch], r12w
0x140048fff  mov     [rbp+1A0h], rax
0x140049006  test    rbx, rbx
0x140049009  jz      loc_140048E99
0x14004900f  mov     rcx, rbx; P
0x140049012  xor     edx, edx; Tag
0x140049014  call    cs:__imp_ExFreePoolWithTag
0x14004901b  nop     dword ptr [rax+rax+00h]
0x140049020  jmp     loc_140048E99
```
