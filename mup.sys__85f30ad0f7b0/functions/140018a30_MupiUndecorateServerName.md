# MupiUndecorateServerName

- ea: `0x140018a30`
- end: `0x140018c08`
- name: `MupiUndecorateServerName`
- size: `472`
- prototype: `unsigned __int16 __fastcall(UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140017f50`
- `0x140018570`
- `0x1400189b0`
- `0x14001a920`

## callees

- `0x1400056c0`
- `0x140018a30`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140018b1c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018b1c`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018a79`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018a79`

## pseudocode

```c
unsigned __int16 __fastcall MupiUndecorateServerName(UNICODE_STRING *a1)
{
  __int64 Length; // rax
  USHORT v3; // ax
  unsigned __int16 result; // ax
  unsigned __int16 v5; // r8
  PWSTR Buffer; // rcx
  unsigned __int16 v7; // dx
  unsigned int v8; // ecx
  unsigned __int16 v9; // si
  __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  UNICODE_STRING String2; // [rsp+20h] [rbp-18h] BYREF

  Length = a1->Length;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  if ( (unsigned int)Length >= 0xE )
  {
    *(_DWORD *)&String2.Length = 917518;
    String2.Buffer = (PWSTR)((char *)a1->Buffer + Length - 14);
    if ( RtlEqualUnicodeString(&String2, &MupiServerNameDecoration_NOCSC, 1u) )
      a1->Length -= 14;
  }
  String2 = *a1;
  v3 = String2.Length;
  while ( v3 >= 8u )
  {
    if ( RtlPrefixUnicodeString(&MupiServerNameDecoration_SSL, &String2, 1u) )
    {
      if ( String2.Buffer )
      {
        v7 = LOWORD(String2.Buffer) - LOWORD(a1->Buffer);
        v8 = a1->Length;
        if ( v7 <= (unsigned __int16)v8 )
        {
          v9 = 8;
          if ( (unsigned int)v7 + 8 > v8 )
            v9 = v8 - v7;
          if ( v8 + (unsigned __int16)MupiEmptyUnicodeString - v9 <= a1->MaximumLength )
          {
            v10 = v7;
            memmove(
              (char *)a1->Buffer + v7 + (unsigned __int64)(unsigned __int16)MupiEmptyUnicodeString,
              (char *)a1->Buffer + v7 + (unsigned __int64)v9,
              (int)(v8 - v9 - v7));
            memmove((char *)a1->Buffer + v10, 0, (unsigned __int16)MupiEmptyUnicodeString);
            a1->Length += MupiEmptyUnicodeString - v9;
            v11 = a1->Length;
            if ( a1->MaximumLength - v11 >= 2 )
              a1->Buffer[v11 >> 1] = 0;
          }
        }
      }
      break;
    }
    ++String2.Buffer;
    v3 = String2.Length - 2;
    String2.MaximumLength -= 2;
    String2.Length -= 2;
  }
  result = 0;
  v5 = a1->Length >> 1;
  if ( v5 )
  {
    do
    {
      Buffer = a1->Buffer;
      if ( Buffer[result] == 64 )
        Buffer[result] = 58;
      ++result;
    }
    while ( result < v5 );
  }
  return result;
}

```

## disassembly

```asm
0x140018a30  push    rdi
0x140018a32  sub     rsp, 30h
0x140018a36  movzx   eax, word ptr [rcx]
0x140018a39  mov     rdi, rcx
0x140018a3c  mov     [rsp+38h+arg_0], rbx
0x140018a41  mov     dword ptr [rsp+38h+String2+4], 0
0x140018a49  cmp     eax, 0Eh
0x140018a4c  jnb     loc_140018AF2
0x140018a52  movups  xmm0, xmmword ptr [rdi]
0x140018a55  mov     ebx, 0FFFEh
0x140018a5a  movups  xmmword ptr [rsp+20h], xmm0
0x140018a5f  movzx   eax, [rsp+38h+String2.Length]
0x140018a64  cmp     ax, 8
0x140018a68  jb      short loc_140018AB1
0x140018a6a  mov     r8b, 1; CaseInSensitive
0x140018a6d  lea     rdx, [rsp+38h+String2]; String2
0x140018a72  lea     rcx, MupiServerNameDecoration_SSL; String1
0x140018a79  call    cs:__imp_RtlPrefixUnicodeString
0x140018a80  nop     dword ptr [rax+rax+00h]
0x140018a85  test    al, al
0x140018a87  jnz     short loc_140018AA3
0x140018a89  movzx   eax, [rsp+38h+String2.Length]
0x140018a8e  add     [rsp+38h+String2.Buffer], 2
0x140018a94  add     ax, bx
0x140018a97  add     [rsp+38h+String2.MaximumLength], bx
0x140018a9c  mov     [rsp+38h+String2.Length], ax
0x140018aa1  jmp     short loc_140018A64
0x140018aa3  mov     rdx, [rsp+38h+String2.Buffer]
0x140018aa8  test    rdx, rdx
0x140018aab  jnz     loc_140018B3D
0x140018ab1  movzx   r8d, word ptr [rdi]
0x140018ab5  xor     eax, eax
0x140018ab7  mov     rbx, [rsp+38h+arg_0]
0x140018abc  xor     ecx, ecx
0x140018abe  shr     r8w, 1
0x140018ac2  cmp     cx, r8w
0x140018ac6  jnb     short loc_140018AEB
0x140018ac8  nop     dword ptr [rax+rax+00000000h]
0x140018ad0  mov     rcx, [rdi+8]
0x140018ad4  movzx   edx, ax
0x140018ad7  cmp     word ptr [rcx+rdx*2], 40h ; '@'
0x140018adc  jz      loc_140018BFD
0x140018ae2  inc     ax
0x140018ae5  cmp     ax, r8w
0x140018ae9  jb      short loc_140018AD0
0x140018aeb  add     rsp, 30h
0x140018aef  pop     rdi
0x140018af0  retn
0x140018af2  mov     rdx, rax
0x140018af5  mov     dword ptr [rsp+38h+String2.Length], 0E000Eh
0x140018afd  mov     rax, [rcx+8]
0x140018b01  mov     r8b, 1; CaseInSensitive
0x140018b04  add     rax, 0FFFFFFFFFFFFFFF2h
0x140018b08  lea     rcx, [rsp+38h+String2]; String1
0x140018b0d  add     rdx, rax
0x140018b10  mov     [rsp+38h+String2.Buffer], rdx
0x140018b15  lea     rdx, MupiServerNameDecoration_NOCSC; String2
0x140018b1c  call    cs:__imp_RtlEqualUnicodeString
0x140018b23  nop     dword ptr [rax+rax+00h]
0x140018b28  test    al, al
0x140018b2a  jz      loc_140018A52
0x140018b30  mov     eax, 0FFF2h
0x140018b35  add     [rdi], ax
0x140018b38  jmp     loc_140018A52
0x140018b3d  sub     dx, [rdi+8]
0x140018b41  movzx   ecx, word ptr [rdi]
0x140018b44  cmp     dx, cx
0x140018b47  ja      loc_140018AB1
0x140018b4d  movzx   r9d, dx
0x140018b51  mov     r8d, ecx
0x140018b54  mov     [rsp+38h+arg_8], rsi
0x140018b59  mov     esi, 8
0x140018b5e  lea     eax, [r9+8]
0x140018b62  cmp     eax, ecx
0x140018b64  jbe     short loc_140018B6C
0x140018b66  sub     cx, dx
0x140018b69  movzx   esi, cx
0x140018b6c  movzx   r11d, cs:MupiEmptyUnicodeString
0x140018b74  movzx   eax, word ptr [rdi+2]
0x140018b78  mov     ecx, r11d
0x140018b7b  movzx   r10d, si
0x140018b7f  sub     ecx, r10d
0x140018b82  add     ecx, r8d
0x140018b85  cmp     ecx, eax
0x140018b87  ja      short loc_140018BF3
0x140018b89  mov     rax, [rdi+8]
0x140018b8d  sub     r8d, r10d
0x140018b90  movzx   ebx, dx
0x140018b93  sub     r8d, r9d
0x140018b96  movzx   edx, si
0x140018b99  add     rdx, rbx
0x140018b9c  movsxd  r8, r8d; Size
0x140018b9f  add     rdx, rax; Src
0x140018ba2  lea     rcx, [rbx+r11]
0x140018ba6  add     rcx, rax; void *
0x140018ba9  call    memmove
0x140018bae  mov     rcx, [rdi+8]
0x140018bb2  movzx   r8d, cs:MupiEmptyUnicodeString; Size
0x140018bba  add     rcx, rbx; void *
0x140018bbd  mov     rdx, cs:Src; Src
0x140018bc4  call    memmove
0x140018bc9  movzx   eax, cs:MupiEmptyUnicodeString
0x140018bd0  sub     ax, si
0x140018bd3  add     [rdi], ax
0x140018bd6  movzx   edx, word ptr [rdi]
0x140018bd9  movzx   eax, word ptr [rdi+2]
0x140018bdd  sub     rax, rdx
0x140018be0  cmp     rax, 2
0x140018be4  jb      short loc_140018BF3
0x140018be6  mov     rcx, [rdi+8]
0x140018bea  shr     rdx, 1
0x140018bed  xor     eax, eax
0x140018bef  mov     [rcx+rdx*2], ax
0x140018bf3  mov     rsi, [rsp+38h+arg_8]
0x140018bf8  jmp     loc_140018AB1
0x140018bfd  mov     word ptr [rcx+rdx*2], 3Ah ; ':'
0x140018c03  jmp     loc_140018AE2
```
