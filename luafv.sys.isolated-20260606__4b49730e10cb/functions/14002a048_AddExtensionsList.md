# AddExtensionsList

- ea: `0x14002a048`
- end: `0x14002a154`
- name: `AddExtensionsList`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140029b30`

## callees

- `0x14002a048`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14002a10f`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14002a10f`

## pseudocode

```c
__int16 __fastcall AddExtensionsList(
        unsigned __int16 *a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        unsigned int *a5,
        _WORD **a6)
{
  int v7; // eax
  WCHAR *v9; // rbx
  bool v10; // zf
  _WORD *i; // rsi
  __int64 v12; // rdi
  __int64 v13; // rcx
  _WORD *v14; // r14
  int v15; // edx
  __int64 v16; // rax
  __int64 v18; // [rsp+78h] [rbp+10h]

  v18 = a2;
  v7 = *a1 >> 1;
  if ( !v7 )
    return v7;
  v9 = (WCHAR *)*((_QWORD *)a1 + 1);
  if ( v7 == 1 )
  {
    v10 = *v9 == 0;
    goto LABEL_7;
  }
  if ( v7 != 2 || *v9 )
  {
LABEL_8:
    while ( 1 )
    {
      for ( i = v9 + 1; *i; ++i )
        ;
      v12 = i - v9;
      if ( (unsigned int)v12 > 4 )
        break;
      v13 = (unsigned int)*a3;
      LOWORD(v7) = v13 + 1;
      *a3 = v13 + 1;
      v14 = (_WORD *)(a2 + 8 * v13);
      if ( (_DWORD)v12 )
        goto LABEL_15;
LABEL_17:
      v9 = i + 1;
      if ( !i[1] )
        return v7;
    }
    v14 = *a6;
    v15 = *a5;
    v16 = *a5;
    *a6 += (unsigned int)v12;
    v16 *= 2;
    *(_WORD *)(a4 + 8 * v16) = 2 * v12;
    *(_WORD *)(a4 + 8 * v16 + 2) = 2 * v12;
    *(_QWORD *)(a4 + 8 * v16 + 8) = v14;
    *a5 = v15 + 1;
    do
    {
LABEL_15:
      LOWORD(v7) = RtlUpcaseUnicodeChar(*v9);
      *v14 = v7;
      ++v9;
      ++v14;
      LODWORD(v12) = v12 - 1;
    }
    while ( (_DWORD)v12 );
    a2 = v18;
    goto LABEL_17;
  }
  v10 = v9[1] == 0;
LABEL_7:
  if ( !v10 )
    goto LABEL_8;
  return v7;
}

```

## disassembly

```asm
0x14002a048  mov     [rsp+arg_8], rdx
0x14002a04d  push    rbx
0x14002a04e  push    rbp
0x14002a04f  push    rsi
0x14002a050  push    rdi
0x14002a051  push    r12
0x14002a053  push    r13
0x14002a055  push    r14
0x14002a057  push    r15
0x14002a059  sub     rsp, 28h
0x14002a05d  movzx   eax, word ptr [rcx]
0x14002a060  mov     r13, r9
0x14002a063  shr     eax, 1
0x14002a065  mov     r15, r8
0x14002a068  jz      loc_14002A142
0x14002a06e  mov     rbx, [rcx+8]
0x14002a072  xor     r8d, r8d
0x14002a075  cmp     eax, 1
0x14002a078  jnz     short loc_14002A080
0x14002a07a  cmp     [rbx], r8w
0x14002a07e  jmp     short loc_14002A090
0x14002a080  cmp     eax, 2
0x14002a083  jnz     short loc_14002A096
0x14002a085  cmp     [rbx], r8w
0x14002a089  jnz     short loc_14002A096
0x14002a08b  cmp     [rbx+2], r8w
0x14002a090  jz      loc_14002A142
0x14002a096  mov     rbp, [rsp+68h+arg_28]
0x14002a09e  mov     r12, [rsp+68h+arg_20]
0x14002a0a6  lea     rsi, [rbx+2]
0x14002a0aa  jmp     short loc_14002A0B0
0x14002a0ac  add     rsi, 2
0x14002a0b0  cmp     [rsi], r8w
0x14002a0b4  jnz     short loc_14002A0AC
0x14002a0b6  mov     rdi, rsi
0x14002a0b9  sub     rdi, rbx
0x14002a0bc  sar     rdi, 1
0x14002a0bf  cmp     edi, 4
0x14002a0c2  ja      short loc_14002A0D7
0x14002a0c4  mov     ecx, [r15]
0x14002a0c7  lea     eax, [rcx+1]
0x14002a0ca  mov     [r15], eax
0x14002a0cd  lea     r14, [rdx+rcx*8]
0x14002a0d1  test    edi, edi
0x14002a0d3  jnz     short loc_14002A10C
0x14002a0d5  jmp     short loc_14002A134
0x14002a0d7  mov     r14, [rbp+0]
0x14002a0db  mov     edx, [r12]
0x14002a0df  mov     eax, edi
0x14002a0e1  lea     rcx, [r14+rax*2]
0x14002a0e5  mov     eax, edx
0x14002a0e7  mov     [rbp+0], rcx
0x14002a0eb  movzx   ecx, di
0x14002a0ee  add     cx, cx
0x14002a0f1  add     rax, rax
0x14002a0f4  mov     [r13+rax*8+0], cx
0x14002a0fa  mov     [r13+rax*8+2], cx
0x14002a100  mov     [r13+rax*8+8], r14
0x14002a105  lea     eax, [rdx+1]
0x14002a108  mov     [r12], eax
0x14002a10c  movzx   ecx, word ptr [rbx]; SourceCharacter
0x14002a10f  call    cs:__imp_RtlUpcaseUnicodeChar
0x14002a116  nop     dword ptr [rax+rax+00h]
0x14002a11b  mov     [r14], ax
0x14002a11f  lea     rbx, [rbx+2]
0x14002a123  lea     r14, [r14+2]
0x14002a127  add     edi, 0FFFFFFFFh
0x14002a12a  jnz     short loc_14002A10C
0x14002a12c  mov     rdx, [rsp+68h+arg_8]
0x14002a131  xor     r8d, r8d
0x14002a134  lea     rbx, [rsi+2]
0x14002a138  cmp     [rbx], r8w
0x14002a13c  jnz     loc_14002A0A6
0x14002a142  add     rsp, 28h
0x14002a146  pop     r15
0x14002a148  pop     r14
0x14002a14a  pop     r13
0x14002a14c  pop     r12
0x14002a14e  pop     rdi
0x14002a14f  pop     rsi
0x14002a150  pop     rbp
0x14002a151  pop     rbx
0x14002a152  retn
```
