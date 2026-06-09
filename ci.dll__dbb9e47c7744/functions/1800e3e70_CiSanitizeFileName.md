# CiSanitizeFileName

- ea: `0x1800e3e70`
- end: `0x1800e4124`
- name: `CiSanitizeFileName`
- size: `692`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ddd4`
- `0x1800660a8`
- `0x180066864`
- `0x180066968`
- `0x180068440`
- `0x180068d50`
- `0x180069660`
- `0x18006c054`
- `0x18006c620`
- `0x18006c77c`
- `0x1800cd61c`
- `0x1800e7194`
- `0x1800e737c`

## callees

- `0x1800104a4`
- `0x1800e3e70`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e404a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e404a`
- `ntoskrnl!ExAllocatePool2` at `0x1800e401d`
- `ntoskrnl!ExAllocatePool2` at `0x1800e401d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e40f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e40f9`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3efc`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f59`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3efc`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e3f59`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e3fa5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e3fa5`

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
    while ( qword_180030650[2 * v11 + 1] )
    {
      if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&qword_180030650[2 * v11], 1u) )
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
0x1800e3e70  mov     [rsp-8+arg_8], rbx
0x1800e3e75  mov     [rsp-8+arg_10], rsi
0x1800e3e7a  push    rbp
0x1800e3e7b  push    rdi
0x1800e3e7c  push    r12
0x1800e3e7e  push    r14
0x1800e3e80  push    r15
0x1800e3e82  lea     rbp, [rsp-37h]
0x1800e3e87  sub     rsp, 0A0h
0x1800e3e8e  xorps   xmm0, xmm0
0x1800e3e91  mov     [rbp+57h+var_70], 10000Eh
0x1800e3e99  lea     rax, aUsers; "\\Users\\"
0x1800e3ea0  mov     [rbp+57h+var_40], 40002h
0x1800e3ea8  xorps   xmm1, xmm1
0x1800e3eab  mov     [rbp+57h+var_68], rax
0x1800e3eaf  lea     rax, asc_180033354; "\\"
0x1800e3eb6  xor     edi, edi
0x1800e3eb8  movups  xmmword ptr [rbp+57h+var_30.Length], xmm1
0x1800e3ebc  mov     [rbp+57h+var_38], rax
0x1800e3ec0  xor     eax, eax
0x1800e3ec2  movups  xmm1, xmmword ptr [rcx]
0x1800e3ec5  mov     [rbp+57h+arg_0], rax
0x1800e3ec9  mov     r15, r8
0x1800e3ecc  mov     r12, rdx
0x1800e3ecf  mov     r14, rcx
0x1800e3ed2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800e3ed6  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e3eda  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1800e3ede  movdqu  [rbp+57h+var_80], xmm1
0x1800e3ee3  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e3ee7  cmp     word ptr [rbp+57h+var_80], ax
0x1800e3eeb  jbe     loc_1800E40A2
0x1800e3ef1  mov     r8b, 1
0x1800e3ef4  lea     rdx, [rbp+57h+var_70]
0x1800e3ef8  lea     rcx, [rbp+57h+var_80]
0x1800e3efc  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e3f03  nop     dword ptr [rax+rax+00h]
0x1800e3f08  mov     rcx, rax
0x1800e3f0b  test    rax, rax
0x1800e3f0e  jz      loc_1800E40A2
0x1800e3f14  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e3f18  xor     r8d, r8d
0x1800e3f1b  shr     rax, 1
0x1800e3f1e  lea     rdx, [rcx+rax*2]
0x1800e3f22  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800e3f26  mov     rcx, rdx
0x1800e3f29  mov     [rbp+57h+var_30.Buffer], rax
0x1800e3f2d  sub     rcx, rax
0x1800e3f30  mov     [rbp+57h+String1.Buffer], rdx
0x1800e3f34  movzx   eax, word ptr [rbp+57h+var_80]
0x1800e3f38  lea     rdx, [rbp+57h+var_40]
0x1800e3f3c  sar     rcx, 1
0x1800e3f3f  add     cx, cx
0x1800e3f42  sub     ax, cx
0x1800e3f45  mov     [rbp+57h+var_30.Length], cx
0x1800e3f49  mov     [rbp+57h+var_30.MaximumLength], cx
0x1800e3f4d  lea     rcx, [rbp+57h+String1]
0x1800e3f51  mov     [rbp+57h+String1.Length], ax
0x1800e3f55  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e3f59  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e3f60  nop     dword ptr [rax+rax+00h]
0x1800e3f65  mov     rbx, rax
0x1800e3f68  test    rax, rax
0x1800e3f6b  jz      loc_1800E40A2
0x1800e3f71  sub     rax, [rbp+57h+String1.Buffer]
0x1800e3f75  sar     rax, 1
0x1800e3f78  add     ax, ax
0x1800e3f7b  mov     [rbp+57h+String1.Length], ax
0x1800e3f7f  xor     esi, esi
0x1800e3f81  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e3f85  movzx   eax, si
0x1800e3f88  lea     rcx, qword_180030650
0x1800e3f8f  add     rax, rax
0x1800e3f92  cmp     qword ptr [rcx+rax*8+8], 0
0x1800e3f98  jz      short loc_1800E3FC7
0x1800e3f9a  lea     rdx, [rcx+rax*8]; String2
0x1800e3f9e  mov     r8b, 1; CaseInSensitive
0x1800e3fa1  lea     rcx, [rbp+57h+String1]; String1
0x1800e3fa5  call    cs:__imp_RtlEqualUnicodeString
0x1800e3fac  nop     dword ptr [rax+rax+00h]
0x1800e3fb1  test    al, al
0x1800e3fb3  jnz     short loc_1800E3FBA
0x1800e3fb5  inc     si
0x1800e3fb8  jmp     short loc_1800E3F85
0x1800e3fba  movaps  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x1800e3fbe  xor     cl, cl
0x1800e3fc0  movdqa  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x1800e3fc5  jmp     short loc_1800E3FE2
0x1800e3fc7  mov     rax, [rbp+57h+arg_0]
0x1800e3fcb  mov     cl, 1
0x1800e3fcd  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800e3fd0  lea     rax, asc_18003561C; "#"
0x1800e3fd7  mov     [rbp+57h+var_50.Buffer], rax
0x1800e3fdb  mov     dword ptr [rbp+57h+var_50.Length], 40002h
0x1800e3fe2  mov     rdx, [r14+8]
0x1800e3fe6  movzx   esi, word ptr [r14]
0x1800e3fea  mov     qword ptr [rbp+57h+var_80+8], rbx
0x1800e3fee  movzx   eax, si
0x1800e3ff1  sub     rbx, rdx
0x1800e3ff4  sar     rbx, 1
0x1800e3ff7  add     bx, bx
0x1800e3ffa  sub     ax, bx
0x1800e3ffd  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4002  mov     word ptr [rbp+57h+var_80], ax
0x1800e4006  mov     word ptr [rbp+57h+var_80+2], ax
0x1800e400a  jnz     short loc_1800E406F
0x1800e400c  test    cl, cl
0x1800e400e  jz      short loc_1800E4058
0x1800e4010  mov     edx, esi
0x1800e4012  mov     ecx, 100h
0x1800e4017  mov     r8d, 63734943h
0x1800e401d  call    cs:__imp_ExAllocatePool2
0x1800e4024  nop     dword ptr [rax+rax+00h]
0x1800e4029  mov     [rbp+57h+DestinationString.Buffer], rax
0x1800e402d  test    rax, rax
0x1800e4030  jz      short loc_1800E409B
0x1800e4032  xor     eax, eax
0x1800e4034  mov     [rbp+57h+DestinationString.MaximumLength], si
0x1800e4038  mov     [rbp+57h+DestinationString.Length], ax
0x1800e403c  cmp     [rbp+57h+SourceString.Buffer], rax
0x1800e4040  jz      short loc_1800E4064
0x1800e4042  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800e4046  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e404a  call    cs:__imp_RtlCopyUnicodeString
0x1800e4051  nop     dword ptr [rax+rax+00h]
0x1800e4056  jmp     short loc_1800E4064
0x1800e4058  mov     [rbp+57h+SourceString.Buffer], rdx
0x1800e405c  mov     [rbp+57h+SourceString.Length], bx
0x1800e4060  mov     [rbp+57h+SourceString.MaximumLength], bx
0x1800e4064  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4069  jz      loc_1800E3EE3
0x1800e406f  lea     rdx, [rbp+57h+var_30]; SourceString
0x1800e4073  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e4077  call    RtlUnicodeStringCat
0x1800e407c  mov     edi, eax
0x1800e407e  test    eax, eax
0x1800e4080  js      short loc_1800E40EB
0x1800e4082  lea     rdx, [rbp+57h+var_50]; SourceString
0x1800e4086  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e408a  call    RtlUnicodeStringCat
0x1800e408f  mov     edi, eax
0x1800e4091  test    eax, eax
0x1800e4093  jns     loc_1800E3EE3
0x1800e4099  jmp     short loc_1800E40EB
0x1800e409b  mov     edi, 0C0000017h
0x1800e40a0  jmp     short loc_1800E40EB
0x1800e40a2  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e40a7  jnz     short loc_1800E40B9
0x1800e40a9  movups  xmm0, xmmword ptr [r14]
0x1800e40ad  mov     byte ptr [r15], 0
0x1800e40b1  movdqu  xmmword ptr [r12], xmm0
0x1800e40b7  jmp     short loc_1800E4105
0x1800e40b9  movaps  xmm0, [rbp+57h+var_80]
0x1800e40bd  lea     rdx, [rbp+57h+String1]; SourceString
0x1800e40c1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e40c5  movdqa  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e40ca  call    RtlUnicodeStringCat
0x1800e40cf  mov     edi, eax
0x1800e40d1  test    eax, eax
0x1800e40d3  js      short loc_1800E40EB
0x1800e40d5  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1800e40d9  mov     byte ptr [r15], 1
0x1800e40dd  mov     [rbp+57h+DestinationString.Buffer], 0
0x1800e40e5  movdqu  xmmword ptr [r12], xmm0
0x1800e40eb  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1800e40ef  test    rcx, rcx
0x1800e40f2  jz      short loc_1800E4105
0x1800e40f4  mov     edx, 63734943h; Tag
0x1800e40f9  call    cs:__imp_ExFreePoolWithTag
0x1800e4100  nop     dword ptr [rax+rax+00h]
0x1800e4105  lea     r11, [rsp+0C0h+var_20]
0x1800e410d  mov     eax, edi
0x1800e410f  mov     rbx, [r11+38h]
0x1800e4113  mov     rsi, [r11+40h]
0x1800e4117  mov     rsp, r11
0x1800e411a  pop     r15
0x1800e411c  pop     r14
0x1800e411e  pop     r12
0x1800e4120  pop     rdi
0x1800e4121  pop     rbp
0x1800e4122  retn
```
