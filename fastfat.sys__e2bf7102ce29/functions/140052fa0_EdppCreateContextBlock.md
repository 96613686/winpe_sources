# EdppCreateContextBlock

- ea: `0x140052fa0`
- end: `0x14005317b`
- name: `EdppCreateContextBlock`
- size: `475`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140050050`
- `0x1400535ac`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x140052fa0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400530a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400530f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053126`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053156`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400530a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400530f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053126`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053156`
- `ntoskrnl!ExAllocatePool2` at `0x14005304e`
- `ntoskrnl!ExAllocatePool2` at `0x14005304e`

## pseudocode

```c
char *__fastcall EdppCreateContextBlock(
        __int64 a1,
        const void **a2,
        _OWORD *a3,
        const void **a4,
        const void **a5,
        const void **a6)
{
  unsigned int v10; // r10d
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ebx
  char *Pool2; // rax
  char *v17; // rdi
  _QWORD *v18; // rbx
  const WCHAR *v19; // rbx

  v10 = *(unsigned __int16 *)a6 + 80;
  v11 = v10 + *(unsigned __int16 *)a2;
  if ( v11 < v10 )
    return 0;
  v12 = v11 + 4;
  if ( v11 + 4 < v11 )
    return 0;
  if ( a4 )
  {
    v13 = v12 + *(unsigned __int16 *)a4;
    if ( v13 < v12 )
      return 0;
    v12 = v13 + 2;
    if ( v13 + 2 < v13 )
      return 0;
  }
  if ( a5 )
  {
    v14 = v12 + *(unsigned __int16 *)a5;
    if ( v14 < v12 )
      return 0;
    v12 = v14 + 2;
    if ( v14 + 2 < v14 )
      return 0;
  }
  v15 = v12;
  Pool2 = (char *)ExAllocatePool2(a1, v12, 1836279365);
  v17 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, v15);
    if ( a3 )
      *((_OWORD *)v17 + 1) = *a3;
    v18 = v17 + 80;
    if ( a4 && *(_WORD *)a4 )
    {
      memmove(v17 + 80, a4[1], *(unsigned __int16 *)a4);
      RtlInitUnicodeString((PUNICODE_STRING)v17 + 2, (PCWSTR)v17 + 40);
      v18 = (_QWORD *)((char *)v18 + 2 * ((unsigned __int64)*(unsigned __int16 *)a4 >> 1) + 2);
    }
    if ( a5 )
    {
      if ( *(_WORD *)a5 )
      {
        memmove(v18, a5[1], *(unsigned __int16 *)a5);
        *v18 = 0x5C003F005C005CLL;
        RtlInitUnicodeString((PUNICODE_STRING)v17 + 3, (PCWSTR)v18);
        v18 = (_QWORD *)((char *)v18 + 2 * ((unsigned __int64)*(unsigned __int16 *)a5 >> 1) + 2);
      }
    }
    memmove(v18, a6[1], *(unsigned __int16 *)a6);
    RtlInitUnicodeString((PUNICODE_STRING)v17 + 4, (PCWSTR)v18);
    v19 = (const WCHAR *)v18 + ((unsigned __int64)*(unsigned __int16 *)a6 >> 1);
    memmove((void *)(v19 + 1), a2[1], *(unsigned __int16 *)a2);
    RtlInitUnicodeString((PUNICODE_STRING)v17, v19 + 1);
  }
  return v17;
}

```

## disassembly

```asm
0x140052fa0  push    rbx
0x140052fa2  push    rbp
0x140052fa3  push    rsi
0x140052fa4  push    rdi
0x140052fa5  push    r12
0x140052fa7  push    r13
0x140052fa9  push    r14
0x140052fab  push    r15
0x140052fad  sub     rsp, 28h
0x140052fb1  mov     r13, [rsp+68h+arg_28]
0x140052fb9  mov     r14, r9
0x140052fbc  mov     rbp, r8
0x140052fbf  mov     r15, rdx
0x140052fc2  mov     r11, rcx
0x140052fc5  movzx   r10d, word ptr [r13+0]
0x140052fca  add     r10d, 50h ; 'P'
0x140052fce  cmp     r10d, 50h ; 'P'
0x140052fd2  jb      loc_140053167
0x140052fd8  movzx   r9d, word ptr [rdx]
0x140052fdc  add     r9d, r10d
0x140052fdf  cmp     r9d, r10d
0x140052fe2  jb      loc_140053167
0x140052fe8  lea     r8d, [r9+4]
0x140052fec  cmp     r8d, r9d
0x140052fef  jb      loc_140053167
0x140052ff5  test    r14, r14
0x140052ff8  jz      short loc_140053017
0x140052ffa  movzx   ecx, word ptr [r14]
0x140052ffe  add     ecx, r8d
0x140053001  cmp     ecx, r8d
0x140053004  jb      loc_140053167
0x14005300a  lea     r8d, [rcx+2]
0x14005300e  cmp     r8d, ecx
0x140053011  jb      loc_140053167
0x140053017  mov     rsi, [rsp+68h+arg_20]
0x14005301f  test    rsi, rsi
0x140053022  jz      short loc_140053040
0x140053024  movzx   ecx, word ptr [rsi]
0x140053027  add     ecx, r8d
0x14005302a  cmp     ecx, r8d
0x14005302d  jb      loc_140053167
0x140053033  lea     r8d, [rcx+2]
0x140053037  cmp     r8d, ecx
0x14005303a  jb      loc_140053167
0x140053040  mov     ebx, r8d
0x140053043  mov     rcx, r11
0x140053046  mov     edx, ebx
0x140053048  mov     r8d, 6D736645h
0x14005304e  call    cs:__imp_ExAllocatePool2
0x140053055  nop     dword ptr [rax+rax+00h]
0x14005305a  mov     rdi, rax
0x14005305d  test    rax, rax
0x140053060  jz      loc_140053162
0x140053066  mov     r8d, ebx; Size
0x140053069  xor     edx, edx; Val
0x14005306b  mov     rcx, rax; void *
0x14005306e  call    memset
0x140053073  test    rbp, rbp
0x140053076  jz      short loc_140053081
0x140053078  movups  xmm0, xmmword ptr [rbp+0]
0x14005307c  movdqu  xmmword ptr [rdi+10h], xmm0
0x140053081  lea     rbx, [rdi+50h]
0x140053085  test    r14, r14
0x140053088  jz      short loc_1400530C4
0x14005308a  movzx   eax, word ptr [r14]
0x14005308e  test    ax, ax
0x140053091  jz      short loc_1400530C4
0x140053093  mov     rdx, [r14+8]; Src
0x140053097  mov     r8d, eax; Size
0x14005309a  mov     rcx, rbx; void *
0x14005309d  call    memmove
0x1400530a2  lea     rcx, [rdi+20h]; DestinationString
0x1400530a6  mov     rdx, rbx; SourceString
0x1400530a9  call    cs:__imp_RtlInitUnicodeString
0x1400530b0  nop     dword ptr [rax+rax+00h]
0x1400530b5  movzx   eax, word ptr [r14]
0x1400530b9  shr     rax, 1
0x1400530bc  lea     rbx, [rbx+rax*2]
0x1400530c0  add     rbx, 2
0x1400530c4  test    rsi, rsi
0x1400530c7  jz      short loc_14005310E
0x1400530c9  movzx   eax, word ptr [rsi]
0x1400530cc  test    ax, ax
0x1400530cf  jz      short loc_14005310E
0x1400530d1  mov     rdx, [rsi+8]; Src
0x1400530d5  mov     r8d, eax; Size
0x1400530d8  mov     rcx, rbx; void *
0x1400530db  call    memmove
0x1400530e0  mov     rax, 5C003F005C005Ch
0x1400530ea  lea     rcx, [rdi+30h]; DestinationString
0x1400530ee  mov     rdx, rbx; SourceString
0x1400530f1  mov     [rbx], rax
0x1400530f4  call    cs:__imp_RtlInitUnicodeString
0x1400530fb  nop     dword ptr [rax+rax+00h]
0x140053100  movzx   eax, word ptr [rsi]
0x140053103  shr     rax, 1
0x140053106  lea     rbx, [rbx+rax*2]
0x14005310a  add     rbx, 2
0x14005310e  movzx   r8d, word ptr [r13+0]; Size
0x140053113  mov     rcx, rbx; void *
0x140053116  mov     rdx, [r13+8]; Src
0x14005311a  call    memmove
0x14005311f  lea     rcx, [rdi+40h]; DestinationString
0x140053123  mov     rdx, rbx; SourceString
0x140053126  call    cs:__imp_RtlInitUnicodeString
0x14005312d  nop     dword ptr [rax+rax+00h]
0x140053132  movzx   eax, word ptr [r13+0]
0x140053137  movzx   r8d, word ptr [r15]; Size
0x14005313b  mov     rdx, [r15+8]; Src
0x14005313f  shr     rax, 1
0x140053142  lea     rbx, [rbx+rax*2]
0x140053146  lea     rcx, [rbx+2]; void *
0x14005314a  call    memmove
0x14005314f  lea     rdx, [rbx+2]; SourceString
0x140053153  mov     rcx, rdi; DestinationString
0x140053156  call    cs:__imp_RtlInitUnicodeString
0x14005315d  nop     dword ptr [rax+rax+00h]
0x140053162  mov     rax, rdi
0x140053165  jmp     short loc_140053169
0x140053167  xor     eax, eax
0x140053169  add     rsp, 28h
0x14005316d  pop     r15
0x14005316f  pop     r14
0x140053171  pop     r13
0x140053173  pop     r12
0x140053175  pop     rdi
0x140053176  pop     rsi
0x140053177  pop     rbp
0x140053178  pop     rbx
0x140053179  retn
```
