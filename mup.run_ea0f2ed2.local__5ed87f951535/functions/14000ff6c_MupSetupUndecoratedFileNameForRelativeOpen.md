# MupSetupUndecoratedFileNameForRelativeOpen

- ea: `0x14000ff6c`
- end: `0x1400100c0`
- name: `MupSetupUndecoratedFileNameForRelativeOpen`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140019548`

## callees

- `0x14000ff6c`
- `0x14001e630`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001009a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001009a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001003d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001003d`
- `ntoskrnl!ExAllocatePool2` at `0x140010015`
- `ntoskrnl!ExAllocatePool2` at `0x140010015`

## pseudocode

```c
__int64 __fastcall MupSetupUndecoratedFileNameForRelativeOpen(__int64 a1)
{
  char v1; // r12
  __int64 v2; // r15
  __int64 v4; // rsi
  int v5; // r14d
  int v6; // edx
  __int16 v7; // r8
  unsigned int v8; // ebp
  unsigned int v9; // edi
  _WORD *v10; // rbx
  char v12; // [rsp+60h] [rbp+8h]
  __int64 Pool2; // [rsp+68h] [rbp+10h]
  unsigned __int16 *v14; // [rsp+70h] [rbp+18h]

  v1 = 0;
  v2 = *(_QWORD *)(a1 + 144);
  v12 = 0;
  v14 = (unsigned __int16 *)(*(_QWORD *)(a1 + 152) + 40LL);
  v4 = *v14 >> 1;
  v5 = *(unsigned __int16 *)(v2 + 88) >> 1;
  v6 = *v14 >> 1;
  if ( v5 && (_DWORD)v4 )
  {
    v7 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 152) + 48LL) + 2LL * (unsigned int)(v4 - 1));
    if ( **(_WORD **)(v2 + 96) == 58 )
    {
      if ( v7 == 92 )
      {
        v1 = 1;
        v6 = v4 - 1;
      }
    }
    else if ( v7 != 92 )
    {
      v12 = 1;
      v6 = v4 + 1;
    }
  }
  v8 = 2 * (v5 + v6);
  if ( v8 <= 0xFFFE )
  {
    Pool2 = ExAllocatePool2(258, v8, 1850111309);
    if ( Pool2 )
    {
      v10 = (_WORD *)(a1 + 40);
      v9 = 0;
      RtlInitUnicodeString((PUNICODE_STRING)(a1 + 40), 0);
      *(_QWORD *)(a1 + 88) = Pool2;
      *(_QWORD *)(a1 + 48) = Pool2;
      *(_WORD *)(a1 + 42) = v8;
      MupSaveUnstrippedFileName(a1, v14, 0);
      if ( v12 )
      {
        *(_WORD *)(*(_QWORD *)(a1 + 48) + 2 * v4) = 92;
        *v10 += 2;
      }
      else if ( v1 )
      {
        *v10 -= 2;
      }
      if ( v5 )
        return (unsigned int)RtlAppendUnicodeStringToString((PUNICODE_STRING)(a1 + 40), (PCUNICODE_STRING)(v2 + 88));
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v9;
}

```

## disassembly

```asm
0x14000ff6c  mov     [rsp+arg_18], rbx
0x14000ff71  push    rbp
0x14000ff72  push    rsi
0x14000ff73  push    rdi
0x14000ff74  push    r12
0x14000ff76  push    r13
0x14000ff78  push    r14
0x14000ff7a  push    r15
0x14000ff7c  sub     rsp, 20h
0x14000ff80  mov     rax, [rcx+98h]
0x14000ff87  xor     r12b, r12b
0x14000ff8a  mov     r15, [rcx+90h]
0x14000ff91  add     rax, 28h ; '('
0x14000ff95  mov     r13, rcx
0x14000ff98  mov     [rsp+58h+arg_0], 0
0x14000ff9d  mov     [rsp+58h+arg_10], rax
0x14000ffa2  mov     r10d, 5Ch ; '\'
0x14000ffa8  movzx   esi, word ptr [rax]
0x14000ffab  movzx   r14d, word ptr [r15+58h]
0x14000ffb0  shr     esi, 1
0x14000ffb2  shr     r14d, 1
0x14000ffb5  mov     edx, esi
0x14000ffb7  jz      short loc_14000FFF0
0x14000ffb9  test    esi, esi
0x14000ffbb  jz      short loc_14000FFF0
0x14000ffbd  mov     rax, [rax+8]
0x14000ffc1  lea     r9d, [rsi-1]
0x14000ffc5  movzx   r8d, word ptr [rax+r9*2]
0x14000ffca  mov     rax, [r15+60h]
0x14000ffce  cmp     word ptr [rax], 3Ah ; ':'
0x14000ffd2  jz      short loc_14000FFE4
0x14000ffd4  cmp     r8w, r10w
0x14000ffd8  jz      short loc_14000FFF0
0x14000ffda  mov     [rsp+58h+arg_0], 1
0x14000ffdf  lea     edx, [rsi+1]
0x14000ffe2  jmp     short loc_14000FFF0
0x14000ffe4  cmp     r8w, r10w
0x14000ffe8  jnz     short loc_14000FFF0
0x14000ffea  mov     r12b, 1
0x14000ffed  mov     edx, r9d
0x14000fff0  lea     ebp, [r14+rdx]
0x14000fff4  add     ebp, ebp
0x14000fff6  cmp     ebp, 0FFFEh
0x14000fffc  jbe     short loc_140010008
0x14000fffe  mov     edi, 0C000000Dh
0x140010003  jmp     loc_1400100A8
0x140010008  mov     edx, ebp
0x14001000a  mov     ecx, 102h
0x14001000f  mov     r8d, 6E46754Dh
0x140010015  call    cs:__imp_ExAllocatePool2
0x14001001c  nop     dword ptr [rax+rax+00h]
0x140010021  mov     [rsp+58h+arg_8], rax
0x140010026  test    rax, rax
0x140010029  jnz     short loc_140010032
0x14001002b  mov     edi, 0C000009Ah
0x140010030  jmp     short loc_1400100A8
0x140010032  lea     rbx, [r13+28h]
0x140010036  xor     edx, edx; SourceString
0x140010038  mov     rcx, rbx; DestinationString
0x14001003b  xor     edi, edi
0x14001003d  call    cs:__imp_RtlInitUnicodeString
0x140010044  nop     dword ptr [rax+rax+00h]
0x140010049  mov     rax, [rsp+58h+arg_8]
0x14001004e  xor     r8d, r8d
0x140010051  mov     rdx, [rsp+58h+arg_10]
0x140010056  mov     rcx, r13
0x140010059  mov     [r13+58h], rax
0x14001005d  mov     [rbx+8], rax
0x140010061  mov     [rbx+2], bp
0x140010065  call    MupSaveUnstrippedFileName
0x14001006a  cmp     [rsp+58h+arg_0], dil
0x14001006f  jz      short loc_140010081
0x140010071  mov     rax, [rbx+8]
0x140010075  mov     word ptr [rax+rsi*2], 5Ch ; '\'
0x14001007b  add     word ptr [rbx], 2
0x14001007f  jmp     short loc_14001008E
0x140010081  test    r12b, r12b
0x140010084  jz      short loc_14001008E
0x140010086  mov     eax, 0FFFEh
0x14001008b  add     [rbx], ax
0x14001008e  test    r14d, r14d
0x140010091  jz      short loc_1400100A8
0x140010093  lea     rdx, [r15+58h]; Source
0x140010097  mov     rcx, rbx; Destination
0x14001009a  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400100a1  nop     dword ptr [rax+rax+00h]
0x1400100a6  mov     edi, eax
0x1400100a8  mov     rbx, [rsp+58h+arg_18]
0x1400100ad  mov     eax, edi
0x1400100af  add     rsp, 20h
0x1400100b3  pop     r15
0x1400100b5  pop     r14
0x1400100b7  pop     r13
0x1400100b9  pop     r12
0x1400100bb  pop     rdi
0x1400100bc  pop     rsi
0x1400100bd  pop     rbp
0x1400100be  retn
```
