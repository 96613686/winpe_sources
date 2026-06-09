# MupiUndecorateServerName

- ea: `0x1400189e0`
- end: `0x140018bb8`
- name: `MupiUndecorateServerName`
- size: `472`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140017f00`
- `0x140018520`
- `0x140018960`
- `0x14001a8d0`

## callees

- `0x1400056c0`
- `0x1400189e0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140018acc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018acc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018a29`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018a29`

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
0x1400189e0  push    rdi
0x1400189e2  sub     rsp, 30h
0x1400189e6  movzx   eax, word ptr [rcx]
0x1400189e9  mov     rdi, rcx
0x1400189ec  mov     [rsp+38h+arg_0], rbx
0x1400189f1  mov     dword ptr [rsp+38h+String2+4], 0
0x1400189f9  cmp     eax, 0Eh
0x1400189fc  jnb     loc_140018AA2
0x140018a02  movups  xmm0, xmmword ptr [rdi]
0x140018a05  mov     ebx, 0FFFEh
0x140018a0a  movups  xmmword ptr [rsp+20h], xmm0
0x140018a0f  movzx   eax, [rsp+38h+String2.Length]
0x140018a14  cmp     ax, 8
0x140018a18  jb      short loc_140018A61
0x140018a1a  mov     r8b, 1; CaseInSensitive
0x140018a1d  lea     rdx, [rsp+38h+String2]; String2
0x140018a22  lea     rcx, MupiServerNameDecoration_SSL; String1
0x140018a29  call    cs:__imp_RtlPrefixUnicodeString
0x140018a30  nop     dword ptr [rax+rax+00h]
0x140018a35  test    al, al
0x140018a37  jnz     short loc_140018A53
0x140018a39  movzx   eax, [rsp+38h+String2.Length]
0x140018a3e  add     [rsp+38h+String2.Buffer], 2
0x140018a44  add     ax, bx
0x140018a47  add     [rsp+38h+String2.MaximumLength], bx
0x140018a4c  mov     [rsp+38h+String2.Length], ax
0x140018a51  jmp     short loc_140018A14
0x140018a53  mov     rdx, [rsp+38h+String2.Buffer]
0x140018a58  test    rdx, rdx
0x140018a5b  jnz     loc_140018AED
0x140018a61  movzx   r8d, word ptr [rdi]
0x140018a65  xor     eax, eax
0x140018a67  mov     rbx, [rsp+38h+arg_0]
0x140018a6c  xor     ecx, ecx
0x140018a6e  shr     r8w, 1
0x140018a72  cmp     cx, r8w
0x140018a76  jnb     short loc_140018A9B
0x140018a78  nop     dword ptr [rax+rax+00000000h]
0x140018a80  mov     rcx, [rdi+8]
0x140018a84  movzx   edx, ax
0x140018a87  cmp     word ptr [rcx+rdx*2], 40h ; '@'
0x140018a8c  jz      loc_140018BAD
0x140018a92  inc     ax
0x140018a95  cmp     ax, r8w
0x140018a99  jb      short loc_140018A80
0x140018a9b  add     rsp, 30h
0x140018a9f  pop     rdi
0x140018aa0  retn
0x140018aa2  mov     rdx, rax
0x140018aa5  mov     dword ptr [rsp+38h+String2.Length], 0E000Eh
0x140018aad  mov     rax, [rcx+8]
0x140018ab1  mov     r8b, 1; CaseInSensitive
0x140018ab4  add     rax, 0FFFFFFFFFFFFFFF2h
0x140018ab8  lea     rcx, [rsp+38h+String2]; String1
0x140018abd  add     rdx, rax
0x140018ac0  mov     [rsp+38h+String2.Buffer], rdx
0x140018ac5  lea     rdx, MupiServerNameDecoration_NOCSC; String2
0x140018acc  call    cs:__imp_RtlEqualUnicodeString
0x140018ad3  nop     dword ptr [rax+rax+00h]
0x140018ad8  test    al, al
0x140018ada  jz      loc_140018A02
0x140018ae0  mov     eax, 0FFF2h
0x140018ae5  add     [rdi], ax
0x140018ae8  jmp     loc_140018A02
0x140018aed  sub     dx, [rdi+8]
0x140018af1  movzx   ecx, word ptr [rdi]
0x140018af4  cmp     dx, cx
0x140018af7  ja      loc_140018A61
0x140018afd  movzx   r9d, dx
0x140018b01  mov     r8d, ecx
0x140018b04  mov     [rsp+38h+arg_8], rsi
0x140018b09  mov     esi, 8
0x140018b0e  lea     eax, [r9+8]
0x140018b12  cmp     eax, ecx
0x140018b14  jbe     short loc_140018B1C
0x140018b16  sub     cx, dx
0x140018b19  movzx   esi, cx
0x140018b1c  movzx   r11d, cs:MupiEmptyUnicodeString
0x140018b24  movzx   eax, word ptr [rdi+2]
0x140018b28  mov     ecx, r11d
0x140018b2b  movzx   r10d, si
0x140018b2f  sub     ecx, r10d
0x140018b32  add     ecx, r8d
0x140018b35  cmp     ecx, eax
0x140018b37  ja      short loc_140018BA3
0x140018b39  mov     rax, [rdi+8]
0x140018b3d  sub     r8d, r10d
0x140018b40  movzx   ebx, dx
0x140018b43  sub     r8d, r9d
0x140018b46  movzx   edx, si
0x140018b49  add     rdx, rbx
0x140018b4c  movsxd  r8, r8d; Size
0x140018b4f  add     rdx, rax; Src
0x140018b52  lea     rcx, [rbx+r11]
0x140018b56  add     rcx, rax; void *
0x140018b59  call    memmove
0x140018b5e  mov     rcx, [rdi+8]
0x140018b62  movzx   r8d, cs:MupiEmptyUnicodeString; Size
0x140018b6a  add     rcx, rbx; void *
0x140018b6d  mov     rdx, cs:Src; Src
0x140018b74  call    memmove
0x140018b79  movzx   eax, cs:MupiEmptyUnicodeString
0x140018b80  sub     ax, si
0x140018b83  add     [rdi], ax
0x140018b86  movzx   edx, word ptr [rdi]
0x140018b89  movzx   eax, word ptr [rdi+2]
0x140018b8d  sub     rax, rdx
0x140018b90  cmp     rax, 2
0x140018b94  jb      short loc_140018BA3
0x140018b96  mov     rcx, [rdi+8]
0x140018b9a  shr     rdx, 1
0x140018b9d  xor     eax, eax
0x140018b9f  mov     [rcx+rdx*2], ax
0x140018ba3  mov     rsi, [rsp+38h+arg_8]
0x140018ba8  jmp     loc_140018A61
0x140018bad  mov     word ptr [rcx+rdx*2], 3Ah ; ':'
0x140018bb3  jmp     loc_140018A92
```
