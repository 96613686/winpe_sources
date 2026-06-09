# MRxSmbFabricateAttributesOnNetRoot

- ea: `0x14002d060`
- end: `0x14002d1a5`
- name: `MRxSmbFabricateAttributesOnNetRoot`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002d7d0`

## callees

- `0x140016560`
- `0x1400166c0`
- `0x14002d060`

## import_xrefs

- `ntoskrnl!RtlOemStringToUnicodeString` at `0x14002d10d`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x14002d10d`
- `ntoskrnl!RtlCompareMemory` at `0x14002d14d`
- `ntoskrnl!RtlCompareMemory` at `0x14002d14d`

## pseudocode

```c
NTSTATUS __fastcall MRxSmbFabricateAttributesOnNetRoot(__int64 a1, __int64 a2)
{
  void *v2; // rsi
  unsigned __int8 v3; // al
  NTSTATUS result; // eax
  USHORT Length; // bx
  __int64 *i; // rsi
  SIZE_T v8; // rbx
  int v9; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  STRING SourceString; // [rsp+30h] [rbp-30h] BYREF
  _BYTE Source1[16]; // [rsp+40h] [rbp-20h] BYREF

  v2 = (void *)(a1 + 162);
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  v3 = *(_BYTE *)(a1 + 162);
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  if ( !v3 )
  {
    if ( *(int *)(a2 + 16) > 2 )
    {
      v3 = 7;
      *(_DWORD *)(a1 + 163) = 1313558101;
      *(_WORD *)(a1 + 167) = 22351;
      *(_BYTE *)(a1 + 169) = 78;
    }
    else
    {
      v3 = 3;
      *(_WORD *)(a1 + 163) = 16710;
      *(_BYTE *)(a1 + 165) = 84;
    }
  }
  SourceString.Length = v3;
  SourceString.MaximumLength = v3;
  *(_DWORD *)&DestinationString.Length = 0x100000;
  SourceString.Buffer = (PCHAR)(a1 + 163);
  DestinationString.Buffer = (PWSTR)Source1;
  result = RtlOemStringToUnicodeString(&DestinationString, &SourceString, 0);
  if ( !result )
  {
    Length = DestinationString.Length;
    memmove(v2, DestinationString.Buffer, DestinationString.Length);
    *(_WORD *)(a1 + 160) = Length;
    for ( i = &NativeFsNameTable; ; i += 2 )
    {
      v8 = *((unsigned __int8 *)i + 3);
      if ( RtlCompareMemory(Source1, (const void *)i[1], v8) == v8 )
        break;
      if ( *(_BYTE *)i )
      {
        *(_DWORD *)(a1 + 36) = 255;
        v9 = 0;
        goto LABEL_12;
      }
    }
    *(_DWORD *)(a1 + 36) = *((unsigned __int8 *)i + 1);
    v9 = *((unsigned __int8 *)i + 2);
LABEL_12:
    *(_DWORD *)(a1 + 32) = v9;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002d060  mov     [rsp-18h+arg_8], rbx
0x14002d065  mov     [rsp-18h+arg_10], rsi
0x14002d06a  push    rbp
0x14002d06b  push    rdi
0x14002d06c  push    r15
0x14002d06e  mov     rbp, rsp
0x14002d071  sub     rsp, 60h
0x14002d075  mov     rax, cs:__security_cookie
0x14002d07c  xor     rax, rsp
0x14002d07f  mov     [rbp+var_10], rax
0x14002d083  lea     rsi, [rcx+0A2h]
0x14002d08a  mov     dword ptr [rbp+DestinationString+4], 0
0x14002d091  mov     al, [rsi]
0x14002d093  mov     rdi, rcx
0x14002d096  mov     dword ptr [rbp+SourceString+4], 0
0x14002d09d  test    al, al
0x14002d09f  jnz     short loc_14002D0D7
0x14002d0a1  cmp     dword ptr [rdx+10h], 2
0x14002d0a5  jg      short loc_14002D0BB
0x14002d0a7  mov     al, 3
0x14002d0a9  mov     word ptr [rcx+0A3h], 4146h
0x14002d0b2  mov     byte ptr [rcx+0A5h], 54h ; 'T'
0x14002d0b9  jmp     short loc_14002D0D7
0x14002d0bb  mov     al, 7
0x14002d0bd  mov     dword ptr [rcx+0A3h], 4E4B4E55h
0x14002d0c7  mov     word ptr [rcx+0A7h], 574Fh
0x14002d0d0  mov     byte ptr [rcx+0A9h], 4Eh ; 'N'
0x14002d0d7  movzx   eax, al
0x14002d0da  lea     rdx, [rbp+SourceString]; SourceString
0x14002d0de  mov     [rbp+SourceString.Length], ax
0x14002d0e2  xor     r8d, r8d; AllocateDestinationString
0x14002d0e5  mov     [rbp+SourceString.MaximumLength], ax
0x14002d0e9  mov     r15d, 10h
0x14002d0ef  lea     rax, [rcx+0A3h]
0x14002d0f6  mov     dword ptr [rbp+DestinationString.Length], 100000h
0x14002d0fd  mov     [rbp+SourceString.Buffer], rax
0x14002d101  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002d105  lea     rax, [rbp+Source1]
0x14002d109  mov     [rbp+DestinationString.Buffer], rax
0x14002d10d  call    cs:__imp_RtlOemStringToUnicodeString
0x14002d114  nop     dword ptr [rax+rax+00h]
0x14002d119  test    eax, eax
0x14002d11b  jnz     short loc_14002D183
0x14002d11d  movzx   ebx, [rbp+DestinationString.Length]
0x14002d121  mov     rcx, rsi; void *
0x14002d124  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x14002d128  mov     r8d, ebx; Size
0x14002d12b  call    memmove
0x14002d130  mov     [rdi+0A0h], bx
0x14002d137  lea     rsi, NativeFsNameTable
0x14002d13e  movzx   ebx, byte ptr [rsi+3]
0x14002d142  lea     rcx, [rbp+Source1]; Source1
0x14002d146  mov     rdx, [rsi+8]; Source2
0x14002d14a  mov     r8d, ebx; Length
0x14002d14d  call    cs:__imp_RtlCompareMemory
0x14002d154  nop     dword ptr [rax+rax+00h]
0x14002d159  cmp     rax, rbx
0x14002d15c  jz      short loc_14002D173
0x14002d15e  cmp     byte ptr [rsi], 0
0x14002d161  jnz     short loc_14002D168
0x14002d163  add     rsi, r15
0x14002d166  jmp     short loc_14002D13E
0x14002d168  mov     dword ptr [rdi+24h], 0FFh
0x14002d16f  xor     eax, eax
0x14002d171  jmp     short loc_14002D17E
0x14002d173  movzx   eax, byte ptr [rsi+1]
0x14002d177  mov     [rdi+24h], eax
0x14002d17a  movzx   eax, byte ptr [rsi+2]
0x14002d17e  mov     [rdi+20h], eax
0x14002d181  xor     eax, eax
0x14002d183  mov     rcx, [rbp+var_10]
0x14002d187  xor     rcx, rsp; StackCookie
0x14002d18a  call    __security_check_cookie
0x14002d18f  lea     r11, [rsp+60h+var_s0]
0x14002d194  mov     rbx, [r11+28h]
0x14002d198  mov     rsi, [r11+30h]
0x14002d19c  mov     rsp, r11
0x14002d19f  pop     r15
0x14002d1a1  pop     rdi
0x14002d1a2  pop     rbp
0x14002d1a3  retn
```
