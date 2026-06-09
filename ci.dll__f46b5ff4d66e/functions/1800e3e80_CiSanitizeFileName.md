# CiSanitizeFileName

- ea: `0x1800e3e80`
- end: `0x1800e4134`
- name: `CiSanitizeFileName`
- size: `692`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d774`
- `0x1800657b4`
- `0x180065f70`
- `0x180066074`
- `0x180067b4c`
- `0x1800683e0`
- `0x18006add4`
- `0x18006b3a0`
- `0x18006b7ac`
- `0x1800cc19c`
- `0x1800e6a8c`
- `0x1800e6c74`

## callees

- `0x180010554`
- `0x1800e3e80`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e405a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e405a`
- `ntoskrnl!ExAllocatePool2` at `0x1800e402d`
- `ntoskrnl!ExAllocatePool2` at `0x1800e402d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4109`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f0c`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f69`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f0c`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f69`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e3fb5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e3fb5`

## pseudocode

```c
__int64 __fastcall CiSanitizeFileName(unsigned __int16 *a1, struct _UNICODE_STRING *a2, _BYTE *a3)
{
  NTSTATUS v3; // edi
  UNICODE_STRING v4; // xmm1
  _BYTE *v5; // r15
  __int64 UnicodeSubstring; // rax
  __int64 v9; // rax
  WCHAR *v10; // rbx
  unsigned __int16 v11; // si
  char v12; // cl
  WCHAR *v13; // rdx
  unsigned int v14; // esi
  USHORT v15; // bx
  struct _UNICODE_STRING v16; // xmm0
  struct _UNICODE_STRING v17; // xmm0
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-39h] BYREF
  UNICODE_STRING v21; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-19h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-9h] BYREF
  UNICODE_STRING v24; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v25[2]; // [rsp+80h] [rbp+17h] BYREF
  UNICODE_STRING v26; // [rsp+90h] [rbp+27h] BYREF

  v22[0] = 1048590;
  v25[0] = 262146;
  v22[1] = L"\\Users\\";
  v3 = 0;
  v26 = 0;
  v25[1] = L"\\";
  v4 = *(UNICODE_STRING *)a1;
  v5 = a3;
  DestinationString = 0;
  String1 = 0;
  SourceString = 0;
  v21 = v4;
  while ( v21.Length > LOWORD(v22[0]) )
  {
    LOBYTE(a3) = 1;
    UnicodeSubstring = RtlFindUnicodeSubstring(&v21, v22, a3);
    if ( !UnicodeSubstring )
      break;
    v26.Buffer = v21.Buffer;
    String1.Buffer = (PWSTR)(UnicodeSubstring + 2 * ((unsigned __int64)LOWORD(v22[0]) >> 1));
    v26.Length = 2 * (String1.Buffer - v21.Buffer);
    v26.MaximumLength = v26.Length;
    String1.Length = v21.Length - v26.Length;
    String1.MaximumLength = v21.Length - v26.Length;
    v9 = RtlFindUnicodeSubstring(&String1, v25, 0);
    v10 = (WCHAR *)v9;
    if ( !v9 )
      break;
    String1.Length = 2 * ((signed __int64)(v9 - (unsigned __int64)String1.Buffer) >> 1);
    v11 = 0;
    String1.MaximumLength = String1.Length;
    while ( qword_1800305B0[2 * v11 + 1] )
    {
      if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&qword_1800305B0[2 * v11], 1u) )
      {
        v12 = 0;
        v24 = String1;
        goto LABEL_11;
      }
      ++v11;
    }
    v12 = 1;
    *(_DWORD *)(&v24.MaximumLength + 1) = 0;
    v24.Buffer = L"#";
    *(_DWORD *)&v24.Length = 262146;
LABEL_11:
    v13 = (WCHAR *)*((_QWORD *)a1 + 1);
    v14 = *a1;
    v21.Buffer = v10;
    v15 = 2 * (v10 - v13);
    v21.Length = v14 - v15;
    v21.MaximumLength = v14 - v15;
    if ( !DestinationString.Buffer )
    {
      if ( v12 )
      {
        DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v14, 1668499779);
        if ( !DestinationString.Buffer )
        {
          v3 = -1073741801;
          goto LABEL_26;
        }
        DestinationString.MaximumLength = v14;
        DestinationString.Length = 0;
        if ( SourceString.Buffer )
          RtlCopyUnicodeString(&DestinationString, &SourceString);
      }
      else
      {
        SourceString.Buffer = v13;
        SourceString.Length = v15;
        SourceString.MaximumLength = v15;
      }
      if ( !DestinationString.Buffer )
        continue;
    }
    v3 = RtlUnicodeStringCat(&DestinationString, &v26);
    if ( v3 < 0 )
      goto LABEL_26;
    v3 = RtlUnicodeStringCat(&DestinationString, &v24);
    if ( v3 < 0 )
      goto LABEL_26;
  }
  if ( !DestinationString.Buffer )
  {
    v16 = *(struct _UNICODE_STRING *)a1;
    *v5 = 0;
    *a2 = v16;
    return (unsigned int)v3;
  }
  String1 = v21;
  v3 = RtlUnicodeStringCat(&DestinationString, &String1);
  if ( v3 >= 0 )
  {
    v17 = DestinationString;
    *v5 = 1;
    DestinationString.Buffer = 0;
    *a2 = v17;
  }
LABEL_26:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x63734943u);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800e3e80  mov     [rsp-8+arg_8], rbx
0x1800e3e85  mov     [rsp-8+arg_10], rsi
0x1800e3e8a  push    rbp
0x1800e3e8b  push    rdi
0x1800e3e8c  push    r12
0x1800e3e8e  push    r14
0x1800e3e90  push    r15
0x1800e3e92  lea     rbp, [rsp-37h]
0x1800e3e97  sub     rsp, 0A0h
0x1800e3e9e  xorps   xmm0, xmm0
0x1800e3ea1  mov     [rbp+57h+var_70], 10000Eh
0x1800e3ea9  lea     rax, aUsers; "\\Users\\"
0x1800e3eb0  mov     [rbp+57h+var_40], 40002h
0x1800e3eb8  xorps   xmm1, xmm1
0x1800e3ebb  mov     [rbp+57h+var_68], rax
0x1800e3ebf  lea     rax, asc_1800332C8; "\\"
0x1800e3ec6  xor     edi, edi
0x1800e3ec8  movups  xmmword ptr [rbp+57h+var_30.Length], xmm1
0x1800e3ecc  mov     [rbp+57h+var_38], rax
0x1800e3ed0  xor     eax, eax
0x1800e3ed2  movups  xmm1, xmmword ptr [rcx]
0x1800e3ed5  mov     [rbp+57h+arg_0], rax
0x1800e3ed9  mov     r15, r8
0x1800e3edc  mov     r12, rdx
0x1800e3edf  mov     r14, rcx
0x1800e3ee2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800e3ee6  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e3eea  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1800e3eee  movdqu  [rbp+57h+var_80], xmm1
0x1800e3ef3  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e3ef7  cmp     word ptr [rbp+57h+var_80], ax
0x1800e3efb  jbe     loc_1800E40B2
0x1800e3f01  mov     r8b, 1
0x1800e3f04  lea     rdx, [rbp+57h+var_70]
0x1800e3f08  lea     rcx, [rbp+57h+var_80]
0x1800e3f0c  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e3f13  nop     dword ptr [rax+rax+00h]
0x1800e3f18  mov     rcx, rax
0x1800e3f1b  test    rax, rax
0x1800e3f1e  jz      loc_1800E40B2
0x1800e3f24  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e3f28  xor     r8d, r8d
0x1800e3f2b  shr     rax, 1
0x1800e3f2e  lea     rdx, [rcx+rax*2]
0x1800e3f32  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800e3f36  mov     rcx, rdx
0x1800e3f39  mov     [rbp+57h+var_30.Buffer], rax
0x1800e3f3d  sub     rcx, rax
0x1800e3f40  mov     [rbp+57h+String1.Buffer], rdx
0x1800e3f44  movzx   eax, word ptr [rbp+57h+var_80]
0x1800e3f48  lea     rdx, [rbp+57h+var_40]
0x1800e3f4c  sar     rcx, 1
0x1800e3f4f  add     cx, cx
0x1800e3f52  sub     ax, cx
0x1800e3f55  mov     [rbp+57h+var_30.Length], cx
0x1800e3f59  mov     [rbp+57h+var_30.MaximumLength], cx
0x1800e3f5d  lea     rcx, [rbp+57h+String1]
0x1800e3f61  mov     [rbp+57h+String1.Length], ax
0x1800e3f65  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e3f69  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e3f70  nop     dword ptr [rax+rax+00h]
0x1800e3f75  mov     rbx, rax
0x1800e3f78  test    rax, rax
0x1800e3f7b  jz      loc_1800E40B2
0x1800e3f81  sub     rax, [rbp+57h+String1.Buffer]
0x1800e3f85  sar     rax, 1
0x1800e3f88  add     ax, ax
0x1800e3f8b  mov     [rbp+57h+String1.Length], ax
0x1800e3f8f  xor     esi, esi
0x1800e3f91  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e3f95  movzx   eax, si
0x1800e3f98  lea     rcx, qword_1800305B0
0x1800e3f9f  add     rax, rax
0x1800e3fa2  cmp     qword ptr [rcx+rax*8+8], 0
0x1800e3fa8  jz      short loc_1800E3FD7
0x1800e3faa  lea     rdx, [rcx+rax*8]; String2
0x1800e3fae  mov     r8b, 1; CaseInSensitive
0x1800e3fb1  lea     rcx, [rbp+57h+String1]; String1
0x1800e3fb5  call    cs:__imp_RtlEqualUnicodeString
0x1800e3fbc  nop     dword ptr [rax+rax+00h]
0x1800e3fc1  test    al, al
0x1800e3fc3  jnz     short loc_1800E3FCA
0x1800e3fc5  inc     si
0x1800e3fc8  jmp     short loc_1800E3F95
0x1800e3fca  movaps  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x1800e3fce  xor     cl, cl
0x1800e3fd0  movdqa  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x1800e3fd5  jmp     short loc_1800E3FF2
0x1800e3fd7  mov     rax, [rbp+57h+arg_0]
0x1800e3fdb  mov     cl, 1
0x1800e3fdd  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800e3fe0  lea     rax, asc_180035458; "#"
0x1800e3fe7  mov     [rbp+57h+var_50.Buffer], rax
0x1800e3feb  mov     dword ptr [rbp+57h+var_50.Length], 40002h
0x1800e3ff2  mov     rdx, [r14+8]
0x1800e3ff6  movzx   esi, word ptr [r14]
0x1800e3ffa  mov     qword ptr [rbp+57h+var_80+8], rbx
0x1800e3ffe  movzx   eax, si
0x1800e4001  sub     rbx, rdx
0x1800e4004  sar     rbx, 1
0x1800e4007  add     bx, bx
0x1800e400a  sub     ax, bx
0x1800e400d  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4012  mov     word ptr [rbp+57h+var_80], ax
0x1800e4016  mov     word ptr [rbp+57h+var_80+2], ax
0x1800e401a  jnz     short loc_1800E407F
0x1800e401c  test    cl, cl
0x1800e401e  jz      short loc_1800E4068
0x1800e4020  mov     edx, esi
0x1800e4022  mov     ecx, 100h
0x1800e4027  mov     r8d, 63734943h
0x1800e402d  call    cs:__imp_ExAllocatePool2
0x1800e4034  nop     dword ptr [rax+rax+00h]
0x1800e4039  mov     [rbp+57h+DestinationString.Buffer], rax
0x1800e403d  test    rax, rax
0x1800e4040  jz      short loc_1800E40AB
0x1800e4042  xor     eax, eax
0x1800e4044  mov     [rbp+57h+DestinationString.MaximumLength], si
0x1800e4048  mov     [rbp+57h+DestinationString.Length], ax
0x1800e404c  cmp     [rbp+57h+SourceString.Buffer], rax
0x1800e4050  jz      short loc_1800E4074
0x1800e4052  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800e4056  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e405a  call    cs:__imp_RtlCopyUnicodeString
0x1800e4061  nop     dword ptr [rax+rax+00h]
0x1800e4066  jmp     short loc_1800E4074
0x1800e4068  mov     [rbp+57h+SourceString.Buffer], rdx
0x1800e406c  mov     [rbp+57h+SourceString.Length], bx
0x1800e4070  mov     [rbp+57h+SourceString.MaximumLength], bx
0x1800e4074  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4079  jz      loc_1800E3EF3
0x1800e407f  lea     rdx, [rbp+57h+var_30]; SourceString
0x1800e4083  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e4087  call    RtlUnicodeStringCat
0x1800e408c  mov     edi, eax
0x1800e408e  test    eax, eax
0x1800e4090  js      short loc_1800E40FB
0x1800e4092  lea     rdx, [rbp+57h+var_50]; SourceString
0x1800e4096  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e409a  call    RtlUnicodeStringCat
0x1800e409f  mov     edi, eax
0x1800e40a1  test    eax, eax
0x1800e40a3  jns     loc_1800E3EF3
0x1800e40a9  jmp     short loc_1800E40FB
0x1800e40ab  mov     edi, 0C0000017h
0x1800e40b0  jmp     short loc_1800E40FB
0x1800e40b2  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e40b7  jnz     short loc_1800E40C9
0x1800e40b9  movups  xmm0, xmmword ptr [r14]
0x1800e40bd  mov     byte ptr [r15], 0
0x1800e40c1  movdqu  xmmword ptr [r12], xmm0
0x1800e40c7  jmp     short loc_1800E4115
0x1800e40c9  movaps  xmm0, [rbp+57h+var_80]
0x1800e40cd  lea     rdx, [rbp+57h+String1]; SourceString
0x1800e40d1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e40d5  movdqa  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e40da  call    RtlUnicodeStringCat
0x1800e40df  mov     edi, eax
0x1800e40e1  test    eax, eax
0x1800e40e3  js      short loc_1800E40FB
0x1800e40e5  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1800e40e9  mov     byte ptr [r15], 1
0x1800e40ed  mov     [rbp+57h+DestinationString.Buffer], 0
0x1800e40f5  movdqu  xmmword ptr [r12], xmm0
0x1800e40fb  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1800e40ff  test    rcx, rcx
0x1800e4102  jz      short loc_1800E4115
0x1800e4104  mov     edx, 63734943h; Tag
0x1800e4109  call    cs:__imp_ExFreePoolWithTag
0x1800e4110  nop     dword ptr [rax+rax+00h]
0x1800e4115  lea     r11, [rsp+0C0h+var_20]
0x1800e411d  mov     eax, edi
0x1800e411f  mov     rbx, [r11+38h]
0x1800e4123  mov     rsi, [r11+40h]
0x1800e4127  mov     rsp, r11
0x1800e412a  pop     r15
0x1800e412c  pop     r14
0x1800e412e  pop     r12
0x1800e4130  pop     rdi
0x1800e4131  pop     rbp
0x1800e4132  retn
```
