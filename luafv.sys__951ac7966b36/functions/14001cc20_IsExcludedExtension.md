# IsExcludedExtension

- ea: `0x14001cc20`
- end: `0x14001cd5c`
- name: `IsExcludedExtension`
- size: `316`
- prototype: `char __fastcall(WCHAR *, unsigned int, _BYTE *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cb80`
- `0x140028f98`

## callees

- `0x14001cc20`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001cc65`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001cc65`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cd07`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cd07`

## pseudocode

```c
char __fastcall IsExcludedExtension(WCHAR *a1, unsigned int a2, _BYTE *a3, int *a4)
{
  int v4; // ebx
  unsigned int v7; // edi
  WCHAR *v8; // rsi
  WCHAR *v9; // r14
  unsigned __int64 v10; // r10
  int v11; // r9d
  int v12; // eax
  int v13; // edi
  __int64 v14; // rsi
  LONG v15; // eax
  int v17; // ecx
  unsigned __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+28h] [rbp-30h] BYREF

  v4 = 0;
  v7 = a2;
  v8 = a1;
  String2 = 0;
  if ( a2 > 4 )
  {
    String2.Buffer = a1;
    String2.Length = 2 * a2;
    String2.MaximumLength = 2 * a2;
    v13 = HIDWORD(qword_14000F2F0) - 1;
    while ( v13 >= v4 )
    {
      v14 = (v13 + v4) / 2;
      v15 = RtlCompareUnicodeString((PCUNICODE_STRING)(qword_14000F2E8 + 16 * v14), &String2, 1u);
      if ( !v15 )
      {
        if ( a3 )
        {
          *a3 = 0;
          *a4 = v14;
        }
        return 1;
      }
      v17 = v14 + 1;
      if ( v15 >= 0 )
        v17 = v4;
      v4 = v17;
      if ( v15 >= 0 )
        v13 = v14 - 1;
    }
  }
  else
  {
    v9 = (WCHAR *)&v18;
    v18 = 0;
    v10 = 0;
    if ( a2 )
    {
      do
      {
        *v9++ = RtlUpcaseUnicodeChar(*v8++);
        --v7;
      }
      while ( v7 );
      v10 = v18;
    }
    v11 = qword_14000F2F0 - 1;
    while ( v11 >= v4 )
    {
      v12 = (v11 + v4) / 2;
      if ( *(_QWORD *)(qword_14000F2E0 + 8LL * v12) == v10 )
      {
        if ( a3 )
        {
          *a3 = 1;
          *a4 = v12;
        }
        return 1;
      }
      if ( *(_QWORD *)(qword_14000F2E0 + 8LL * v12) >= v10 )
        v11 = v12 - 1;
      else
        v4 = v12 + 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001cc20  mov     [rsp+arg_8], rbx
0x14001cc25  mov     [rsp+arg_10], rbp
0x14001cc2a  push    rsi
0x14001cc2b  push    rdi
0x14001cc2c  push    r15
0x14001cc2e  sub     rsp, 40h
0x14001cc32  xor     ebx, ebx
0x14001cc34  xorps   xmm0, xmm0
0x14001cc37  mov     rbp, r9
0x14001cc3a  mov     r15, r8
0x14001cc3d  mov     edi, edx
0x14001cc3f  mov     rsi, rcx
0x14001cc42  movups  xmmword ptr [rsp+58h+String2.Length], xmm0
0x14001cc47  cmp     edx, 4
0x14001cc4a  ja      short loc_14001CCC8
0x14001cc4c  mov     [rsp+58h+arg_0], r14
0x14001cc51  lea     r14, [rsp+58h+var_38]
0x14001cc56  mov     [rsp+58h+var_38], rbx
0x14001cc5b  mov     r10d, ebx
0x14001cc5e  test    edx, edx
0x14001cc60  jz      short loc_14001CC87
0x14001cc62  movzx   ecx, word ptr [rsi]; SourceCharacter
0x14001cc65  call    cs:__imp_RtlUpcaseUnicodeChar
0x14001cc6c  nop     dword ptr [rax+rax+00h]
0x14001cc71  mov     [r14], ax
0x14001cc75  lea     r14, [r14+2]
0x14001cc79  lea     rsi, [rsi+2]
0x14001cc7d  add     edi, 0FFFFFFFFh
0x14001cc80  jnz     short loc_14001CC62
0x14001cc82  mov     r10, [rsp+58h+var_38]
0x14001cc87  mov     r9d, dword ptr cs:qword_14000F2F0
0x14001cc8e  mov     r14, [rsp+58h+arg_0]
0x14001cc93  dec     r9d
0x14001cc96  cmp     r9d, ebx
0x14001cc99  jl      loc_14001CD3F
0x14001cc9f  lea     eax, [r9+rbx]
0x14001cca3  test    eax, eax
0x14001cca5  jns     short loc_14001CCA9
0x14001cca7  inc     eax
0x14001cca9  mov     rcx, cs:qword_14000F2E0
0x14001ccb0  sar     eax, 1
0x14001ccb2  movsxd  rdx, eax
0x14001ccb5  cmp     [rcx+rdx*8], r10
0x14001ccb9  jz      short loc_14001CD24
0x14001ccbb  jnb     short loc_14001CCC2
0x14001ccbd  lea     ebx, [rax+1]
0x14001ccc0  jmp     short loc_14001CC96
0x14001ccc2  lea     r9d, [rax-1]
0x14001ccc6  jmp     short loc_14001CC96
0x14001ccc8  add     di, di
0x14001cccb  mov     [rsp+58h+String2.Buffer], rcx
0x14001ccd0  mov     [rsp+58h+String2.Length], di
0x14001ccd5  mov     [rsp+58h+String2.MaximumLength], di
0x14001ccda  mov     edi, dword ptr cs:qword_14000F2F0+4
0x14001cce0  dec     edi
0x14001cce2  cmp     edi, ebx
0x14001cce4  jl      short loc_14001CD3F
0x14001cce6  lea     eax, [rdi+rbx]
0x14001cce9  mov     r8b, 1; CaseInSensitive
0x14001ccec  cdq
0x14001cced  sub     eax, edx
0x14001ccef  lea     rdx, [rsp+58h+String2]; String2
0x14001ccf4  sar     eax, 1
0x14001ccf6  movsxd  rsi, eax
0x14001ccf9  mov     rcx, rsi
0x14001ccfc  shl     rcx, 4
0x14001cd00  add     rcx, cs:qword_14000F2E8; String1
0x14001cd07  call    cs:__imp_RtlCompareUnicodeString
0x14001cd0e  nop     dword ptr [rax+rax+00h]
0x14001cd13  test    eax, eax
0x14001cd15  jnz     short loc_14001CD43
0x14001cd17  test    r15, r15
0x14001cd1a  jz      short loc_14001CD29
0x14001cd1c  mov     [r15], al
0x14001cd1f  mov     [rbp+0], esi
0x14001cd22  jmp     short loc_14001CD29
0x14001cd24  test    r15, r15
0x14001cd27  jnz     short loc_14001CD53
0x14001cd29  mov     al, 1
0x14001cd2b  mov     rbx, [rsp+58h+arg_8]
0x14001cd30  mov     rbp, [rsp+58h+arg_10]
0x14001cd35  add     rsp, 40h
0x14001cd39  pop     r15
0x14001cd3b  pop     rdi
0x14001cd3c  pop     rsi
0x14001cd3d  retn
0x14001cd3f  xor     al, al
0x14001cd41  jmp     short loc_14001CD2B
0x14001cd43  lea     ecx, [rsi+1]
0x14001cd46  cmovns  ecx, ebx
0x14001cd49  mov     ebx, ecx
0x14001cd4b  lea     ecx, [rsi-1]
0x14001cd4e  cmovns  edi, ecx
0x14001cd51  jmp     short loc_14001CCE2
0x14001cd53  mov     byte ptr [r15], 1
0x14001cd57  mov     [rbp+0], eax
0x14001cd5a  jmp     short loc_14001CD29
```
