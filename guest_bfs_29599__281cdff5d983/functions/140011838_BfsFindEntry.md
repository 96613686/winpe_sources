# BfsFindEntry

- ea: `0x140011838`
- end: `0x140011936`
- name: `BfsFindEntry`
- size: `254`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140006fa4`
- `0x1400104ec`
- `0x14001093c`
- `0x140011194`
- `0x140012608`

## callees

- `0x140011838`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400118dd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400118dd`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001187e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001187e`
- `ntoskrnl!RtlFindSetBits` at `0x140011896`
- `ntoskrnl!RtlFindSetBits` at `0x140011903`
- `ntoskrnl!RtlFindSetBits` at `0x140011896`
- `ntoskrnl!RtlFindSetBits` at `0x140011903`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400118c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400118c6`

## pseudocode

```c
__int64 __fastcall BfsFindEntry(__int64 a1, const UNICODE_STRING *a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // r14
  ULONG SetBits; // edi
  __int64 v7; // rbx
  ULONG v8; // ebx
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  v4 = **(_QWORD ***)(a1 + 16);
LABEL_2:
  if ( v4 == *(_QWORD **)(a1 + 16) )
    return 0;
  v5 = v4[2];
  RtlInitializeBitMap(&BitMapHeader, (PULONG)(v5 + 15968), 0x1Eu);
  SetBits = RtlFindSetBits(&BitMapHeader, 1u, 0);
  while ( 1 )
  {
    if ( SetBits == -1 )
    {
LABEL_8:
      v4 = (_QWORD *)*v4;
      goto LABEL_2;
    }
    v7 = 532LL * SetBits;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v5 + v7 + 28));
    if ( RtlEqualUnicodeString(&DestinationString, a2, 1u) )
      return v7 + v5 + 8;
    if ( SetBits + 1 < 0x1E )
    {
      v8 = SetBits;
      SetBits = RtlFindSetBits(&BitMapHeader, 1u, SetBits + 1);
      if ( SetBits > v8 )
        continue;
    }
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x140011838  push    rbx
0x14001183a  push    rbp
0x14001183b  push    rsi
0x14001183c  push    rdi
0x14001183d  push    r14
0x14001183f  push    r15
0x140011841  sub     rsp, 48h
0x140011845  xor     eax, eax
0x140011847  mov     r15, rdx
0x14001184a  mov     qword ptr [rsp+78h+BitMapHeader+4], rax
0x14001184f  mov     rbp, rcx
0x140011852  mov     [rsp+20h], rax
0x140011857  mov     rax, [rcx+10h]
0x14001185b  mov     rsi, [rax]
0x14001185e  cmp     rsi, [rbp+10h]
0x140011862  jz      loc_140011926
0x140011868  mov     r14, [rsi+10h]
0x14001186c  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x140011871  mov     r8d, 1Eh; SizeOfBitMap
0x140011877  lea     rdx, [r14+3E60h]; BitMapBuffer
0x14001187e  call    cs:__imp_RtlInitializeBitMap
0x140011885  nop     dword ptr [rax+rax+00h]
0x14001188a  xor     r8d, r8d; HintIndex
0x14001188d  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x140011892  lea     edx, [r8+1]; NumberToFind
0x140011896  call    cs:__imp_RtlFindSetBits
0x14001189d  nop     dword ptr [rax+rax+00h]
0x1400118a2  mov     edi, eax
0x1400118a4  cmp     edi, 0FFFFFFFFh
0x1400118a7  jz      short loc_140011915
0x1400118a9  mov     ecx, edi
0x1400118ab  xorps   xmm0, xmm0
0x1400118ae  imul    rbx, rcx, 214h
0x1400118b5  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1400118ba  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400118bf  lea     rdx, [rbx+1Ch]
0x1400118c3  add     rdx, r14; SourceString
0x1400118c6  call    cs:__imp_RtlInitUnicodeString
0x1400118cd  nop     dword ptr [rax+rax+00h]
0x1400118d2  mov     r8b, 1; CaseInSensitive
0x1400118d5  lea     rcx, [rsp+78h+DestinationString]; String1
0x1400118da  mov     rdx, r15; String2
0x1400118dd  call    cs:__imp_RtlEqualUnicodeString
0x1400118e4  nop     dword ptr [rax+rax+00h]
0x1400118e9  test    al, al
0x1400118eb  jnz     short loc_14001191D
0x1400118ed  lea     r8d, [rdi+1]; HintIndex
0x1400118f1  cmp     r8d, 1Eh
0x1400118f5  jnb     short loc_140011915
0x1400118f7  mov     edx, 1; NumberToFind
0x1400118fc  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x140011901  mov     ebx, edi
0x140011903  call    cs:__imp_RtlFindSetBits
0x14001190a  nop     dword ptr [rax+rax+00h]
0x14001190f  mov     edi, eax
0x140011911  cmp     eax, ebx
0x140011913  ja      short loc_1400118A4
0x140011915  mov     rsi, [rsi]
0x140011918  jmp     loc_14001185E
0x14001191d  lea     rax, [r14+8]
0x140011921  add     rax, rbx
0x140011924  jmp     short loc_140011928
0x140011926  xor     eax, eax
0x140011928  add     rsp, 48h
0x14001192c  pop     r15
0x14001192e  pop     r14
0x140011930  pop     rdi
0x140011931  pop     rsi
0x140011932  pop     rbp
0x140011933  pop     rbx
0x140011934  retn
```
