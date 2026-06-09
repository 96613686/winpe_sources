# DfscRmGetPathConsumed

- ea: `0x140027b74`
- end: `0x140027de8`
- name: `DfscRmGetPathConsumed`
- size: `628`
- prototype: `NTSTATUS __fastcall(__int64, USHORT *, struct _UNICODE_STRING *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001935c`
- `0x14002774c`

## callees

- `0x140002394`
- `0x140027b74`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140027bb1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027bc3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027bb1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027bc3`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c25`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c56`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c75`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c25`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c56`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027c75`

## pseudocode

```c
NTSTATUS __fastcall DfscRmGetPathConsumed(__int64 a1, USHORT *a2, struct _UNICODE_STRING *a3, char a4)
{
  bool v6; // r15
  USHORT *v9; // rbx
  NTSTATUS result; // eax
  __int16 v11; // di
  __int64 v12; // rdx
  PWSTR Buffer; // rcx
  USHORT Length; // dx
  struct _UNICODE_STRING *p_DestinationString; // r8
  unsigned __int16 v16; // ax
  struct _UNICODE_STRING v17; // xmm0
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF
  __int128 v20; // [rsp+40h] [rbp-18h]

  v6 = 0;
  DestinationString = 0;
  String1 = 0;
  v20 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&String1, 0);
  *(_WORD *)(a1 + 218) = 0;
  if ( a2[1] )
  {
    v9 = a2 + 4;
    if ( a2[4] != 1 )
    {
      if ( a2[4] == 2 )
      {
        v6 = *a2 == 0;
        result = RtlInitUnicodeStringEx(&DestinationString, (USHORT *)((char *)v9 + a2[12]));
        if ( result )
          return result;
        v12 = a2[13];
      }
      else
      {
        if ( (unsigned int)a2[4] - 3 >= 2 )
          return -1073741811;
        v11 = a2[7] & 2;
        v6 = v11 != 0;
        result = RtlInitUnicodeStringEx(&DestinationString, (USHORT *)((char *)v9 + a2[10]));
        if ( result )
          return result;
        if ( v11 )
          goto LABEL_12;
        v12 = a2[11];
      }
      result = RtlInitUnicodeStringEx(&String1, (USHORT *)((char *)v9 + v12));
      if ( result )
        return result;
LABEL_12:
      Buffer = DestinationString.Buffer;
      Length = DestinationString.Length;
      goto LABEL_14;
    }
  }
  Buffer = *(PWSTR *)(a1 + 192);
  DestinationString.Length = *a2;
  Length = DestinationString.Length;
  DestinationString.Buffer = Buffer;
  DestinationString.MaximumLength = DestinationString.Length + 2;
LABEL_14:
  if ( String1.Length > 2u && String1.Buffer && String1.Buffer[((unsigned __int64)String1.Length >> 1) - 1] == 92 )
    String1.Length -= 2;
  if ( Length > 2u && Buffer && Buffer[((unsigned __int64)Length >> 1) - 1] == 92 )
  {
    Length -= 2;
    DestinationString.Length = Length;
  }
  if ( v6 && !a4 )
  {
    if ( Length > 2u && Buffer && *Buffer == 92 )
    {
      Length -= 2;
      DestinationString.MaximumLength -= 2;
      DestinationString.Buffer = Buffer + 1;
      DestinationString.Length = Length;
    }
    p_DestinationString = &DestinationString;
    goto LABEL_36;
  }
  v16 = _mm_cvtsi128_si32(*(__m128i *)(a1 + 168));
  v20 = *(_OWORD *)(a1 + 168);
  if ( v16 >= 4u && **((_DWORD **)&v20 + 1) == 6029404 )
  {
    *((_QWORD *)&v20 + 1) += 2LL;
    WORD1(v20) -= 2;
    LOWORD(v20) = v16 - 2;
  }
  if ( (unsigned __int8)DfscPathPrefixMatch(&DestinationString) )
  {
    Length = DestinationString.Length;
    p_DestinationString = &DestinationString;
LABEL_36:
    v17 = *p_DestinationString;
    *(_WORD *)(a1 + 218) = *a2 != 0 ? Length : 0;
    result = 0;
    *a3 = v17;
    return result;
  }
  if ( (unsigned __int8)DfscPathPrefixMatch(&String1) )
  {
    Length = String1.Length;
    p_DestinationString = &String1;
    goto LABEL_36;
  }
  return -1073741629;
}

```

## disassembly

```asm
0x140027b74  push    rbp
0x140027b76  push    rbx
0x140027b77  push    rsi
0x140027b78  push    rdi
0x140027b79  push    r12
0x140027b7b  push    r13
0x140027b7d  push    r14
0x140027b7f  push    r15
0x140027b81  mov     rbp, rsp
0x140027b84  sub     rsp, 58h
0x140027b88  xorps   xmm0, xmm0
0x140027b8b  mov     rsi, rdx
0x140027b8e  mov     r14, rcx
0x140027b91  xorps   xmm1, xmm1
0x140027b94  xor     edi, edi
0x140027b96  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027b9a  xor     edx, edx; SourceString
0x140027b9c  mov     r15b, dil
0x140027b9f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140027ba3  mov     r12b, r9b
0x140027ba6  mov     r13, r8
0x140027ba9  movups  xmmword ptr [rbp+String1.Length], xmm1
0x140027bad  movups  [rbp+var_18], xmm0
0x140027bb1  call    cs:__imp_RtlInitUnicodeString
0x140027bb8  nop     dword ptr [rax+rax+00h]
0x140027bbd  xor     edx, edx; SourceString
0x140027bbf  lea     rcx, [rbp+String1]; DestinationString
0x140027bc3  call    cs:__imp_RtlInitUnicodeString
0x140027bca  nop     dword ptr [rax+rax+00h]
0x140027bcf  mov     [r14+0DAh], di
0x140027bd7  lea     r11d, [rdi+2]
0x140027bdb  cmp     [rsi+2], di
0x140027bdf  jz      loc_140027C99
0x140027be5  lea     rbx, [rsi+8]
0x140027be9  movzx   ecx, word ptr [rbx]
0x140027bec  sub     ecx, 1
0x140027bef  jz      loc_140027C99
0x140027bf5  sub     ecx, 1
0x140027bf8  jz      short loc_140027C44
0x140027bfa  sub     ecx, 1
0x140027bfd  jz      short loc_140027C0E
0x140027bff  cmp     ecx, 1
0x140027c02  jz      short loc_140027C0E
0x140027c04  mov     eax, 0C000000Dh
0x140027c09  jmp     loc_140027DD6
0x140027c0e  movzx   edi, word ptr [rbx+6]
0x140027c12  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027c16  movzx   edx, word ptr [rbx+0Ch]
0x140027c1a  and     di, r11w
0x140027c1e  setnz   r15b
0x140027c22  add     rdx, rbx; SourceString
0x140027c25  call    cs:__imp_RtlInitUnicodeStringEx
0x140027c2c  nop     dword ptr [rax+rax+00h]
0x140027c31  test    eax, eax
0x140027c33  jnz     loc_140027DD6
0x140027c39  test    di, di
0x140027c3c  jnz     short loc_140027C89
0x140027c3e  movzx   edx, word ptr [rbx+0Eh]
0x140027c42  jmp     short loc_140027C6E
0x140027c44  cmp     [rsi], di
0x140027c47  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027c4b  movzx   edx, word ptr [rbx+10h]
0x140027c4f  setz    r15b
0x140027c53  add     rdx, rbx; SourceString
0x140027c56  call    cs:__imp_RtlInitUnicodeStringEx
0x140027c5d  nop     dword ptr [rax+rax+00h]
0x140027c62  test    eax, eax
0x140027c64  jnz     loc_140027DD6
0x140027c6a  movzx   edx, word ptr [rbx+12h]
0x140027c6e  add     rdx, rbx; SourceString
0x140027c71  lea     rcx, [rbp+String1]; DestinationString
0x140027c75  call    cs:__imp_RtlInitUnicodeStringEx
0x140027c7c  nop     dword ptr [rax+rax+00h]
0x140027c81  test    eax, eax
0x140027c83  jnz     loc_140027DD6
0x140027c89  mov     rcx, [rbp+DestinationString.Buffer]
0x140027c8d  mov     r11d, 2
0x140027c93  movzx   edx, [rbp+DestinationString.Length]
0x140027c97  jmp     short loc_140027CB3
0x140027c99  movzx   edx, word ptr [rsi]
0x140027c9c  mov     rcx, [r14+0C0h]
0x140027ca3  mov     [rbp+DestinationString.Length], dx
0x140027ca7  mov     [rbp+DestinationString.Buffer], rcx
0x140027cab  lea     eax, [r11+rdx]
0x140027caf  mov     [rbp+DestinationString.MaximumLength], ax
0x140027cb3  movzx   r8d, [rbp+String1.Length]
0x140027cb8  mov     bx, 5Ch ; '\'
0x140027cbc  mov     r10d, 0FFFEh
0x140027cc2  cmp     r8w, r11w
0x140027cc6  jbe     short loc_140027CE8
0x140027cc8  mov     r9, [rbp+String1.Buffer]
0x140027ccc  test    r9, r9
0x140027ccf  jz      short loc_140027CE8
0x140027cd1  mov     eax, r8d
0x140027cd4  shr     rax, 1
0x140027cd7  cmp     [r9+rax*2-2], bx
0x140027cdd  jnz     short loc_140027CE8
0x140027cdf  add     r8w, r10w
0x140027ce3  mov     [rbp+String1.Length], r8w
0x140027ce8  cmp     dx, r11w
0x140027cec  jbe     short loc_140027D08
0x140027cee  test    rcx, rcx
0x140027cf1  jz      short loc_140027D08
0x140027cf3  movzx   eax, dx
0x140027cf6  shr     rax, 1
0x140027cf9  cmp     [rcx+rax*2-2], bx
0x140027cfe  jnz     short loc_140027D08
0x140027d00  add     dx, r10w
0x140027d04  mov     [rbp+DestinationString.Length], dx
0x140027d08  test    r15b, r15b
0x140027d0b  jz      short loc_140027D3C
0x140027d0d  test    r12b, r12b
0x140027d10  jnz     short loc_140027D3C
0x140027d12  cmp     dx, r11w
0x140027d16  jbe     short loc_140027D36
0x140027d18  test    rcx, rcx
0x140027d1b  jz      short loc_140027D36
0x140027d1d  cmp     [rcx], bx
0x140027d20  jnz     short loc_140027D36
0x140027d22  add     rcx, r11
0x140027d25  add     dx, r10w
0x140027d29  add     [rbp+DestinationString.MaximumLength], r10w
0x140027d2e  mov     [rbp+DestinationString.Buffer], rcx
0x140027d32  mov     [rbp+DestinationString.Length], dx
0x140027d36  lea     r8, [rbp+DestinationString]
0x140027d3a  jmp     short loc_140027DAF
0x140027d3c  movups  xmm0, xmmword ptr [r14+0A8h]
0x140027d44  movd    eax, xmm0
0x140027d48  movups  [rbp+var_18], xmm0
0x140027d4c  cmp     ax, 4
0x140027d50  jb      short loc_140027D7B
0x140027d52  mov     rcx, qword ptr [rbp+var_18+8]
0x140027d56  cmp     [rcx], bx
0x140027d59  jnz     short loc_140027D7B
0x140027d5b  add     rcx, 2
0x140027d5f  cmp     [rcx], bx
0x140027d62  jnz     short loc_140027D7B
0x140027d64  cmp     ax, r11w
0x140027d68  jbe     short loc_140027D7B
0x140027d6a  add     ax, r10w
0x140027d6e  mov     qword ptr [rbp+var_18+8], rcx
0x140027d72  add     word ptr [rbp+var_18+2], r10w
0x140027d77  mov     word ptr [rbp+var_18], ax
0x140027d7b  lea     rdx, [rbp+var_18]
0x140027d7f  lea     rcx, [rbp+DestinationString]; String1
0x140027d83  call    DfscPathPrefixMatch
0x140027d88  test    al, al
0x140027d8a  jz      short loc_140027D96
0x140027d8c  movzx   edx, [rbp+DestinationString.Length]
0x140027d90  lea     r8, [rbp+DestinationString]
0x140027d94  jmp     short loc_140027DAF
0x140027d96  lea     rdx, [rbp+var_18]
0x140027d9a  lea     rcx, [rbp+String1]; String1
0x140027d9e  call    DfscPathPrefixMatch
0x140027da3  test    al, al
0x140027da5  jz      short loc_140027DD1
0x140027da7  movzx   edx, [rbp+String1.Length]
0x140027dab  lea     r8, [rbp+String1]
0x140027daf  movzx   eax, word ptr [rsi]
0x140027db2  movups  xmm0, xmmword ptr [r8]
0x140027db6  neg     ax
0x140027db9  sbb     cx, cx
0x140027dbc  and     cx, dx
0x140027dbf  mov     [r14+0DAh], cx
0x140027dc7  xor     eax, eax
0x140027dc9  movdqu  xmmword ptr [r13+0], xmm0
0x140027dcf  jmp     short loc_140027DD6
0x140027dd1  mov     eax, 0C00000C3h
0x140027dd6  add     rsp, 58h
0x140027dda  pop     r15
0x140027ddc  pop     r14
0x140027dde  pop     r13
0x140027de0  pop     r12
0x140027de2  pop     rdi
0x140027de3  pop     rsi
0x140027de4  pop     rbx
0x140027de5  pop     rbp
0x140027de6  retn
```
