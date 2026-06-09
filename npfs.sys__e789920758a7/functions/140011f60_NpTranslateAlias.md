# NpTranslateAlias

- ea: `0x140011f60`
- end: `0x140012177`
- name: `NpTranslateAlias`
- size: `535`
- prototype: `NTSTATUS __fastcall(__m128i *, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f610`
- `0x140011490`
- `0x140011aa0`

## callees

- `0x140001e10`
- `0x140011f60`
- `0x140012180`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012077`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012150`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012077`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012150`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400120bc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400120bc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140011ffd`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140011ffd`

## pseudocode

```c
NTSTATUS __fastcall NpTranslateAlias(__m128i *a1, __int64 a2, _DWORD *a3)
{
  UNICODE_STRING v6; // xmm0
  USHORT Length; // cx
  char v8; // si
  unsigned int v9; // edi
  __int64 i; // rbx
  unsigned int v11; // eax
  NTSTATUS result; // eax
  char v13; // cl
  PWSTR Buffer; // r8
  __int64 v15; // rax
  WCHAR v16; // dx
  UNICODE_STRING String2; // [rsp+20h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-68h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-58h] BYREF
  char v20; // [rsp+50h] [rbp-48h] BYREF

  *(_QWORD *)&String1.Length = 917516;
  DestinationString = 0;
  String1.Buffer = L"LOCAL\\";
  *a3 = 0;
  v6 = (UNICODE_STRING)*a1;
  Length = _mm_cvtsi128_si32(*a1);
  String2 = v6;
  if ( Length >= 2u && *String2.Buffer == 92 )
  {
    Length -= 2;
    String2.MaximumLength -= 2;
    v8 = 1;
    ++String2.Buffer;
    String2.Length = Length;
  }
  else
  {
    v8 = 0;
  }
  if ( Length )
  {
    if ( a2 && Length > 0xCu )
    {
      if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
        return NpTranslateContainerLocalAlias(a1, a2, a3);
      Length = String2.Length;
    }
    v9 = Length + 2;
    if ( (unsigned int)Length - 8 <= 8 )
    {
      i = NpAliasListByLength[((unsigned __int64)v9 - 10) >> 1];
      if ( i )
      {
LABEL_16:
        if ( Length <= 0x12u )
        {
          DestinationString.MaximumLength = 18;
          DestinationString.Buffer = (PWSTR)&v20;
          RtlUpcaseUnicodeString(&DestinationString, &String2, 0);
          v13 = 0;
        }
        else
        {
          result = RtlUpcaseUnicodeString(&DestinationString, &String2, 1u);
          if ( result < 0 )
            return result;
          v13 = 1;
        }
LABEL_19:
        Buffer = DestinationString.Buffer;
        v15 = *(_QWORD *)(i + 24);
        while ( 1 )
        {
          v16 = *(_WORD *)(v15 + 2);
          v15 += 2;
          if ( !v16 )
            break;
          if ( *Buffer < v16 )
            goto LABEL_23;
          if ( *Buffer > v16 )
          {
            i = *(_QWORD *)i;
            if ( !i || *(unsigned __int16 *)(i + 16) != v9 )
              goto LABEL_23;
            goto LABEL_19;
          }
          ++Buffer;
        }
        *a1 = *(__m128i *)*(_QWORD *)(i + 8);
        if ( !v8 )
        {
          a1->m128i_i16[0] -= 2;
          a1->m128i_i16[1] -= 2;
          a1->m128i_i64[1] += 2;
        }
LABEL_23:
        if ( v13 )
          RtlFreeUnicodeString(&DestinationString);
      }
    }
    else
    {
      for ( i = NpAliasList; i; i = *(_QWORD *)i )
      {
        v11 = *(unsigned __int16 *)(i + 16);
        if ( v11 > v9 )
          break;
        if ( v11 == v9 )
          goto LABEL_16;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140011f60  push    rbx
0x140011f62  push    rbp
0x140011f63  push    rsi
0x140011f64  push    rdi
0x140011f65  push    r14
0x140011f67  sub     rsp, 70h
0x140011f6b  mov     rax, cs:__security_cookie
0x140011f72  xor     rax, rsp
0x140011f75  mov     [rsp+98h+var_30], rax
0x140011f7a  mov     rdi, r8
0x140011f7d  mov     qword ptr [rsp+98h+String1.Length], 0E000Ch
0x140011f86  xorps   xmm0, xmm0
0x140011f89  lea     rax, aLocal; "LOCAL\\"
0x140011f90  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140011f95  mov     rbp, rcx
0x140011f98  mov     [rsp+98h+String1.Buffer], rax
0x140011f9d  mov     dword ptr [rdi], 0
0x140011fa3  mov     rbx, rdx
0x140011fa6  movups  xmm0, xmmword ptr [rcx]
0x140011fa9  mov     r8d, 0Ch
0x140011faf  mov     r14d, 0FFFEh
0x140011fb5  movd    ecx, xmm0
0x140011fb9  movups  xmmword ptr [rsp+98h+String2.Length], xmm0
0x140011fbe  cmp     cx, 2
0x140011fc2  jb      short loc_140011FD7
0x140011fc4  mov     rax, [rsp+98h+String2.Buffer]
0x140011fc9  mov     edx, 5Ch ; '\'
0x140011fce  cmp     dx, [rax]
0x140011fd1  jz      loc_1400120E3
0x140011fd7  xor     sil, sil
0x140011fda  xor     eax, eax
0x140011fdc  cmp     ax, cx
0x140011fdf  jz      loc_1400120C8
0x140011fe5  test    rbx, rbx
0x140011fe8  jz      short loc_140012016
0x140011fea  cmp     r8w, cx
0x140011fee  jnb     short loc_140012016
0x140011ff0  mov     r8b, 1; CaseInSensitive
0x140011ff3  lea     rdx, [rsp+98h+String2]; String2
0x140011ff8  lea     rcx, [rsp+98h+String1]; String1
0x140011ffd  call    cs:__imp_RtlPrefixUnicodeString
0x140012004  nop     dword ptr [rax+rax+00h]
0x140012009  test    al, al
0x14001200b  jnz     loc_140012103
0x140012011  movzx   ecx, [rsp+98h+String2.Length]
0x140012016  movzx   edi, cx
0x140012019  add     edi, 2
0x14001201c  lea     eax, [rdi-0Ah]
0x14001201f  cmp     eax, 8
0x140012022  jbe     short loc_140012047
0x140012024  mov     rbx, cs:NpAliasList
0x14001202b  test    rbx, rbx
0x14001202e  jz      loc_1400120C8
0x140012034  movzx   eax, word ptr [rbx+10h]
0x140012038  cmp     eax, edi
0x14001203a  ja      loc_1400120C8
0x140012040  jz      short loc_140012060
0x140012042  mov     rbx, [rbx]
0x140012045  jmp     short loc_14001202B
0x140012047  mov     ebx, edi
0x140012049  lea     rax, NpAliasListByLength
0x140012050  sub     rbx, 0Ah
0x140012054  shr     rbx, 1
0x140012057  mov     rbx, [rax+rbx*8]
0x14001205b  test    rbx, rbx
0x14001205e  jz      short loc_1400120C8
0x140012060  cmp     cx, 12h
0x140012064  lea     rdx, [rsp+98h+String2]; SourceString
0x140012069  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14001206e  jbe     loc_140012139
0x140012074  mov     r8b, 1; AllocateDestinationString
0x140012077  call    cs:__imp_RtlUpcaseUnicodeString
0x14001207e  nop     dword ptr [rax+rax+00h]
0x140012083  test    eax, eax
0x140012085  js      short loc_1400120CA
0x140012087  mov     cl, 1
0x140012089  mov     r8, [rsp+98h+DestinationString.Buffer]
0x14001208e  mov     rax, [rbx+18h]
0x140012092  movzx   edx, word ptr [rax+2]
0x140012096  add     rax, 2
0x14001209a  test    dx, dx
0x14001209d  jnz     short loc_140012113
0x14001209f  mov     rax, [rbx+8]
0x1400120a3  movups  xmm0, xmmword ptr [rax]
0x1400120a6  movups  xmmword ptr [rbp+0], xmm0
0x1400120aa  test    sil, sil
0x1400120ad  jz      loc_140012163
0x1400120b3  test    cl, cl
0x1400120b5  jz      short loc_1400120C8
0x1400120b7  lea     rcx, [rsp+98h+DestinationString]; UnicodeString
0x1400120bc  call    cs:__imp_RtlFreeUnicodeString
0x1400120c3  nop     dword ptr [rax+rax+00h]
0x1400120c8  xor     eax, eax
0x1400120ca  mov     rcx, [rsp+98h+var_30]
0x1400120cf  xor     rcx, rsp; StackCookie
0x1400120d2  call    __security_check_cookie
0x1400120d7  add     rsp, 70h
0x1400120db  pop     r14
0x1400120dd  pop     rdi
0x1400120de  pop     rsi
0x1400120df  pop     rbp
0x1400120e0  pop     rbx
0x1400120e1  retn
0x1400120e3  add     rax, 2
0x1400120e7  add     cx, r14w
0x1400120eb  add     [rsp+98h+String2.MaximumLength], r14w
0x1400120f1  mov     sil, 1
0x1400120f4  mov     [rsp+98h+String2.Buffer], rax
0x1400120f9  mov     [rsp+98h+String2.Length], cx
0x1400120fe  jmp     loc_140011FDA
0x140012103  mov     r8, rdi
0x140012106  mov     rdx, rbx
0x140012109  mov     rcx, rbp
0x14001210c  call    NpTranslateContainerLocalAlias
0x140012111  jmp     short loc_1400120CA
0x140012113  cmp     [r8], dx
0x140012117  jb      short loc_1400120B3
0x140012119  jbe     short loc_140012130
0x14001211b  mov     rbx, [rbx]
0x14001211e  test    rbx, rbx
0x140012121  jz      short loc_1400120B3
0x140012123  movzx   eax, word ptr [rbx+10h]
0x140012127  cmp     eax, edi
0x140012129  jnz     short loc_1400120B3
0x14001212b  jmp     loc_140012089
0x140012130  add     r8, 2
0x140012134  jmp     loc_140012092
0x140012139  mov     eax, 12h
0x14001213e  xor     r8d, r8d; AllocateDestinationString
0x140012141  mov     [rsp+98h+DestinationString.MaximumLength], ax
0x140012146  lea     rax, [rsp+98h+var_48]
0x14001214b  mov     [rsp+98h+DestinationString.Buffer], rax
0x140012150  call    cs:__imp_RtlUpcaseUnicodeString
0x140012157  nop     dword ptr [rax+rax+00h]
0x14001215c  xor     cl, cl
0x14001215e  jmp     loc_140012089
0x140012163  add     [rbp+0], r14w
0x140012168  add     [rbp+2], r14w
0x14001216d  add     qword ptr [rbp+8], 2
0x140012172  jmp     loc_1400120B3
```
