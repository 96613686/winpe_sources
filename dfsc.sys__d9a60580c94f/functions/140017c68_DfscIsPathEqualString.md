# DfscIsPathEqualString

- ea: `0x140017c68`
- end: `0x140017dbf`
- name: `DfscIsPathEqualString`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017dfc`
- `0x140026ac0`

## callees

- `0x140017c68`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140017da7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140017da7`

## pseudocode

```c
LONG __fastcall DfscIsPathEqualString(__m128i *a1, UNICODE_STRING *a2)
{
  UNICODE_STRING v2; // xmm0
  USHORT v3; // r9
  WCHAR *Buffer; // rdx
  USHORT MaximumLength; // ax
  USHORT Length; // cx
  WCHAR *v7; // r8
  USHORT v8; // ax
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-10h] BYREF

  v2 = *a2;
  v3 = _mm_cvtsi128_si32(*a1);
  String1 = (UNICODE_STRING)*a1;
  Buffer = String1.Buffer;
  String2 = v2;
  if ( v3 > 2u )
  {
    if ( String1.Buffer && *String1.Buffer == 92 )
    {
      Buffer = String1.Buffer + 1;
      v3 -= 2;
      ++String1.Buffer;
      MaximumLength = String1.MaximumLength - 2;
      String1.Length = v3;
      String1.MaximumLength -= 2;
    }
    else
    {
      MaximumLength = String1.MaximumLength;
    }
    if ( v3 > 2u && Buffer && *Buffer == 92 )
    {
      ++Buffer;
      v3 -= 2;
      String1.Buffer = Buffer;
      String1.MaximumLength = MaximumLength - 2;
      String1.Length = v3;
    }
  }
  Length = String2.Length;
  v7 = String2.Buffer;
  if ( String2.Length > 2u )
  {
    if ( String2.Buffer && *String2.Buffer == 92 )
    {
      v7 = String2.Buffer + 1;
      Length = String2.Length - 2;
      ++String2.Buffer;
      v8 = String2.MaximumLength - 2;
      String2.Length -= 2;
      String2.MaximumLength -= 2;
    }
    else
    {
      v8 = String2.MaximumLength;
    }
    if ( Length > 2u && v7 && *v7 == 92 )
    {
      ++v7;
      Length -= 2;
      String2.Buffer = v7;
      String2.MaximumLength = v8 - 2;
      String2.Length = Length;
    }
  }
  if ( v3 > 2u && Buffer && !Buffer[((unsigned __int64)v3 >> 1) - 1] )
    String1.Length = v3 - 2;
  if ( Length > 2u && v7 && !v7[((unsigned __int64)Length >> 1) - 1] )
    String2.Length = Length - 2;
  return RtlCompareUnicodeString(&String1, &String2, 1u);
}

```

## disassembly

```asm
0x140017c68  mov     [rsp-8+arg_0], rbx
0x140017c6d  push    rbp
0x140017c6e  mov     rbp, rsp
0x140017c71  sub     rsp, 40h
0x140017c75  movups  xmm1, xmmword ptr [rcx]
0x140017c78  xor     ebx, ebx
0x140017c7a  mov     r11d, 0FFFEh
0x140017c80  movups  xmm0, xmmword ptr [rdx]
0x140017c83  movd    r9d, xmm1
0x140017c88  lea     r10d, [rbx+2]
0x140017c8c  movups  xmmword ptr [rbp+String1.Length], xmm1
0x140017c90  mov     rdx, [rbp+String1.Buffer]
0x140017c94  movdqu  xmmword ptr [rbp+String2.Length], xmm0
0x140017c99  cmp     r9w, r10w
0x140017c9d  jbe     short loc_140017CF5
0x140017c9f  test    rdx, rdx
0x140017ca2  jz      short loc_140017CC8
0x140017ca4  cmp     word ptr [rdx], 5Ch ; '\'
0x140017ca8  jnz     short loc_140017CC8
0x140017caa  movzx   eax, [rbp+String1.MaximumLength]
0x140017cae  add     rdx, r10
0x140017cb1  add     r9w, r11w
0x140017cb5  mov     [rbp+String1.Buffer], rdx
0x140017cb9  add     ax, r11w
0x140017cbd  mov     [rbp+String1.Length], r9w
0x140017cc2  mov     [rbp+String1.MaximumLength], ax
0x140017cc6  jmp     short loc_140017CCC
0x140017cc8  movzx   eax, [rbp+String1.MaximumLength]
0x140017ccc  cmp     r9w, r10w
0x140017cd0  jbe     short loc_140017CF5
0x140017cd2  test    rdx, rdx
0x140017cd5  jz      short loc_140017CF5
0x140017cd7  cmp     word ptr [rdx], 5Ch ; '\'
0x140017cdb  jnz     short loc_140017CF5
0x140017cdd  add     rdx, r10
0x140017ce0  add     r9w, r11w
0x140017ce4  add     ax, r11w
0x140017ce8  mov     [rbp+String1.Buffer], rdx
0x140017cec  mov     [rbp+String1.MaximumLength], ax
0x140017cf0  mov     [rbp+String1.Length], r9w
0x140017cf5  movzx   ecx, [rbp+String2.Length]
0x140017cf9  mov     r8, [rbp+String2.Buffer]
0x140017cfd  cmp     cx, r10w
0x140017d01  jbe     short loc_140017D59
0x140017d03  test    r8, r8
0x140017d06  jz      short loc_140017D2C
0x140017d08  cmp     word ptr [r8], 5Ch ; '\'
0x140017d0d  jnz     short loc_140017D2C
0x140017d0f  movzx   eax, [rbp+String2.MaximumLength]
0x140017d13  add     r8, r10
0x140017d16  add     cx, r11w
0x140017d1a  mov     [rbp+String2.Buffer], r8
0x140017d1e  add     ax, r11w
0x140017d22  mov     [rbp+String2.Length], cx
0x140017d26  mov     [rbp+String2.MaximumLength], ax
0x140017d2a  jmp     short loc_140017D30
0x140017d2c  movzx   eax, [rbp+String2.MaximumLength]
0x140017d30  cmp     cx, r10w
0x140017d34  jbe     short loc_140017D59
0x140017d36  test    r8, r8
0x140017d39  jz      short loc_140017D59
0x140017d3b  cmp     word ptr [r8], 5Ch ; '\'
0x140017d40  jnz     short loc_140017D59
0x140017d42  add     r8, r10
0x140017d45  add     cx, r11w
0x140017d49  add     ax, r11w
0x140017d4d  mov     [rbp+String2.Buffer], r8
0x140017d51  mov     [rbp+String2.MaximumLength], ax
0x140017d55  mov     [rbp+String2.Length], cx
0x140017d59  cmp     r9w, r10w
0x140017d5d  jbe     short loc_140017D7B
0x140017d5f  test    rdx, rdx
0x140017d62  jz      short loc_140017D7B
0x140017d64  movzx   eax, r9w
0x140017d68  shr     rax, 1
0x140017d6b  cmp     [rdx+rax*2-2], bx
0x140017d70  jnz     short loc_140017D7B
0x140017d72  add     r9w, r11w
0x140017d76  mov     [rbp+String1.Length], r9w
0x140017d7b  cmp     cx, r10w
0x140017d7f  jbe     short loc_140017D9C
0x140017d81  test    r8, r8
0x140017d84  jz      short loc_140017D9C
0x140017d86  movzx   eax, cx
0x140017d89  shr     rax, 1
0x140017d8c  cmp     [r8+rax*2-2], bx
0x140017d92  jnz     short loc_140017D9C
0x140017d94  add     cx, r11w
0x140017d98  mov     [rbp+String2.Length], cx
0x140017d9c  mov     r8b, 1; CaseInSensitive
0x140017d9f  lea     rdx, [rbp+String2]; String2
0x140017da3  lea     rcx, [rbp+String1]; String1
0x140017da7  call    cs:__imp_RtlCompareUnicodeString
0x140017dae  nop     dword ptr [rax+rax+00h]
0x140017db3  mov     rbx, [rsp+40h+arg_0]
0x140017db8  add     rsp, 40h
0x140017dbc  pop     rbp
0x140017dbd  retn
```
