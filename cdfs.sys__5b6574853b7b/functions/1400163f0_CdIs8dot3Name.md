# CdIs8dot3Name

- ea: `0x1400163f0`
- end: `0x1400164d5`
- name: `CdIs8dot3Name`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140010f68`
- `0x140011744`
- `0x140012198`
- `0x14001233c`
- `0x1400135d0`

## callees

- `0x140002df0`
- `0x1400163f0`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToCountedOemString` at `0x1400164a2`
- `ntoskrnl!RtlUnicodeStringToCountedOemString` at `0x1400164a2`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x1400164c7`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x1400164c7`

## pseudocode

```c
BOOLEAN __fastcall CdIs8dot3Name(__int64 a1, _QWORD *a2)
{
  WCHAR *v2; // r8
  unsigned int v3; // ecx
  int v4; // r10d
  unsigned int v5; // r9d
  char v6; // dl
  struct _STRING DestinationString; // [rsp+20h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-40h] BYREF
  ANSI_STRING DbcsName; // [rsp+40h] [rbp-30h] BYREF
  char v11; // [rsp+50h] [rbp-20h] BYREF

  v2 = (WCHAR *)a2[1];
  v3 = (unsigned __int16)*a2;
  *(_QWORD *)&SourceString.Length = *a2;
  SourceString.Buffer = v2;
  DestinationString = 0;
  if ( (unsigned __int16)v3 <= 0x18u )
  {
    v4 = 0;
    v5 = 0;
    while ( *v2 != 32 )
    {
      if ( *v2 == 46 )
      {
        if ( v4 || v5 > 0x10 )
          return 0;
        v4 = 1;
        v6 = 1;
      }
      else
      {
        v6 = 0;
      }
      v5 += 2;
      if ( v5 >= v3 )
      {
        if ( v6 )
          SourceString.Length = v3 - 2;
        DestinationString.MaximumLength = 24;
        DestinationString.Buffer = &v11;
        if ( RtlUnicodeStringToCountedOemString(&DestinationString, &SourceString, 0) >= 0 )
        {
          DbcsName = DestinationString;
          return FsRtlIsFatDbcsLegal(&DbcsName, 0, 0, 0);
        }
        return 0;
      }
      ++v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400163f0  push    rbp
0x1400163f2  mov     rbp, rsp
0x1400163f5  sub     rsp, 70h
0x1400163f9  mov     rax, cs:__security_cookie
0x140016400  xor     rax, rsp
0x140016403  mov     [rbp+var_8], rax
0x140016407  mov     rax, [rdx]
0x14001640a  mov     r11d, 18h
0x140016410  mov     r8, [rdx+8]
0x140016414  xorps   xmm0, xmm0
0x140016417  movzx   ecx, ax
0x14001641a  mov     qword ptr [rbp+SourceString.Length], rax
0x14001641e  mov     [rbp+SourceString.Buffer], r8
0x140016422  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140016426  cmp     cx, r11w
0x14001642a  ja      short loc_140016465
0x14001642c  xor     r10d, r10d
0x14001642f  xor     r9d, r9d
0x140016432  jmp     short loc_14001645B
0x140016434  cmp     ax, 2Eh ; '.'
0x140016438  jnz     short loc_14001644C
0x14001643a  test    r10d, r10d
0x14001643d  jnz     short loc_140016465
0x14001643f  cmp     r9d, 10h
0x140016443  ja      short loc_140016465
0x140016445  inc     r10d
0x140016448  mov     dl, 1
0x14001644a  jmp     short loc_14001644E
0x14001644c  xor     dl, dl
0x14001644e  add     r9d, 2
0x140016452  cmp     r9d, ecx
0x140016455  jnb     short loc_14001647A
0x140016457  add     r8, 2
0x14001645b  movzx   eax, word ptr [r8]
0x14001645f  cmp     ax, 20h ; ' '
0x140016463  jnz     short loc_140016434
0x140016465  xor     al, al
0x140016467  mov     rcx, [rbp+var_8]
0x14001646b  xor     rcx, rsp; StackCookie
0x14001646e  call    __security_check_cookie
0x140016473  add     rsp, 70h
0x140016477  pop     rbp
0x140016478  retn
0x14001647a  test    dl, dl
0x14001647c  jz      short loc_14001648A
0x14001647e  mov     eax, 0FFFEh
0x140016483  add     cx, ax
0x140016486  mov     [rbp+SourceString.Length], cx
0x14001648a  lea     rax, [rbp+var_20]
0x14001648e  mov     [rbp+DestinationString.MaximumLength], r11w
0x140016493  xor     r8d, r8d; AllocateDestinationString
0x140016496  mov     [rbp+DestinationString.Buffer], rax
0x14001649a  lea     rdx, [rbp+SourceString]; SourceString
0x14001649e  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400164a2  call    cs:__imp_RtlUnicodeStringToCountedOemString
0x1400164a9  nop     dword ptr [rax+rax+00h]
0x1400164ae  test    eax, eax
0x1400164b0  js      short loc_140016465
0x1400164b2  movaps  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x1400164b6  lea     rcx, [rbp+DbcsName]; DbcsName
0x1400164ba  xor     r9d, r9d; LeadingBackslashPermissible
0x1400164bd  movdqa  xmmword ptr [rbp+DbcsName.Length], xmm0
0x1400164c2  xor     r8d, r8d; PathNamePermissible
0x1400164c5  xor     edx, edx; WildCardsPermissible
0x1400164c7  call    cs:__imp_FsRtlIsFatDbcsLegal
0x1400164ce  nop     dword ptr [rax+rax+00h]
0x1400164d3  jmp     short loc_140016467
```
