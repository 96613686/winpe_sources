# BfsGetEntryBlock

- ea: `0x140011a24`
- end: `0x140011b15`
- name: `BfsGetEntryBlock`
- size: `241`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400104ec`
- `0x140011194`
- `0x140012608`

## callees

- `0x140011a24`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x140011a87`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011a87`
- `ntoskrnl!RtlFindSetBits` at `0x140011a9f`
- `ntoskrnl!RtlFindSetBits` at `0x140011adb`
- `ntoskrnl!RtlFindSetBits` at `0x140011a9f`
- `ntoskrnl!RtlFindSetBits` at `0x140011adb`

## pseudocode

```c
__int64 __fastcall BfsGetEntryBlock(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  __int64 **v4; // rax
  __int64 *i; // rdi
  __int64 v10; // rsi
  ULONG SetBits; // eax
  ULONG v12; // ebx
  __int64 result; // rax
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-48h] BYREF

  v4 = *(__int64 ***)(a1 + 16);
  *a3 = 0;
  *a4 = 0;
  for ( i = *v4; i != *(__int64 **)(a1 + 16); i = (__int64 *)*i )
  {
    v10 = i[2];
    if ( v10 )
    {
      LODWORD(BitMapHeader.Buffer) = 0;
      *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
      RtlInitializeBitMap(&BitMapHeader, (PULONG)(v10 + 15968), 0x1Eu);
      SetBits = RtlFindSetBits(&BitMapHeader, 1u, 0);
      while ( SetBits != -1 )
      {
        if ( a2 == v10 + 532LL * SetBits + 8 )
        {
          *a4 = *((_DWORD *)i + 6);
          result = 0;
          *a3 = v10;
          return result;
        }
        if ( SetBits + 1 < 0x1E )
        {
          v12 = SetBits;
          SetBits = RtlFindSetBits(&BitMapHeader, 1u, SetBits + 1);
          if ( SetBits > v12 )
            continue;
        }
        break;
      }
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140011a24  push    rbx
0x140011a26  push    rbp
0x140011a27  push    rsi
0x140011a28  push    rdi
0x140011a29  push    r12
0x140011a2b  push    r14
0x140011a2d  push    r15
0x140011a2f  sub     rsp, 30h
0x140011a33  mov     rax, [rcx+10h]
0x140011a37  mov     r14, r9
0x140011a3a  mov     r15, r8
0x140011a3d  mov     qword ptr [r8], 0
0x140011a44  mov     r12, rdx
0x140011a47  mov     dword ptr [r9], 0
0x140011a4e  mov     rbp, rcx
0x140011a51  mov     rdi, [rax]
0x140011a54  cmp     rdi, [rbp+10h]
0x140011a58  jz      loc_140011B00
0x140011a5e  mov     rsi, [rdi+10h]
0x140011a62  test    rsi, rsi
0x140011a65  jz      loc_140011AEB
0x140011a6b  xor     eax, eax
0x140011a6d  lea     rdx, [rsi+3E60h]; BitMapBuffer
0x140011a74  mov     qword ptr [rsp+68h+BitMapHeader+4], rax
0x140011a79  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011a7e  mov     qword ptr [rsp+68h+BitMapHeader.SizeOfBitMap], rax
0x140011a83  lea     r8d, [rax+1Eh]; SizeOfBitMap
0x140011a87  call    cs:__imp_RtlInitializeBitMap
0x140011a8e  nop     dword ptr [rax+rax+00h]
0x140011a93  xor     r8d, r8d; HintIndex
0x140011a96  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011a9b  lea     edx, [r8+1]; NumberToFind
0x140011a9f  call    cs:__imp_RtlFindSetBits
0x140011aa6  nop     dword ptr [rax+rax+00h]
0x140011aab  cmp     eax, 0FFFFFFFFh
0x140011aae  jz      short loc_140011AEB
0x140011ab0  mov     ecx, eax
0x140011ab2  imul    rcx, 214h
0x140011ab9  add     rcx, 8
0x140011abd  add     rcx, rsi
0x140011ac0  cmp     r12, rcx
0x140011ac3  jz      short loc_140011AF3
0x140011ac5  lea     r8d, [rax+1]; HintIndex
0x140011ac9  cmp     r8d, 1Eh
0x140011acd  jnb     short loc_140011AEB
0x140011acf  mov     edx, 1; NumberToFind
0x140011ad4  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011ad9  mov     ebx, eax
0x140011adb  call    cs:__imp_RtlFindSetBits
0x140011ae2  nop     dword ptr [rax+rax+00h]
0x140011ae7  cmp     eax, ebx
0x140011ae9  ja      short loc_140011AAB
0x140011aeb  mov     rdi, [rdi]
0x140011aee  jmp     loc_140011A54
0x140011af3  mov     eax, [rdi+18h]
0x140011af6  mov     [r14], eax
0x140011af9  xor     eax, eax
0x140011afb  mov     [r15], rsi
0x140011afe  jmp     short loc_140011B05
0x140011b00  mov     eax, 0C0000225h
0x140011b05  add     rsp, 30h
0x140011b09  pop     r15
0x140011b0b  pop     r14
0x140011b0d  pop     r12
0x140011b0f  pop     rdi
0x140011b10  pop     rsi
0x140011b11  pop     rbp
0x140011b12  pop     rbx
0x140011b13  retn
```
