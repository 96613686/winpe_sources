# CiSanitizeFileName

- ea: `0x1800e43f0`
- end: `0x1800e46a4`
- name: `CiSanitizeFileName`
- size: `692`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18005dd74`
- `0x180066218`
- `0x1800669d4`
- `0x180066ad8`
- `0x1800685b0`
- `0x180068ec0`
- `0x1800697d0`
- `0x18006c1c4`
- `0x18006c790`
- `0x18006c8ec`
- `0x1800cd62c`
- `0x1800e79c8`
- `0x1800e7bb0`

## callees

- `0x1800104b4`
- `0x1800e43f0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e45ca`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800e45ca`
- `ntoskrnl!ExAllocatePool2` at `0x1800e459d`
- `ntoskrnl!ExAllocatePool2` at `0x1800e459d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4679`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4679`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e447c`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e44d9`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e447c`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800e44d9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e4525`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800e4525`

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
    while ( qword_180030620[2 * v11 + 1] )
    {
      if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&qword_180030620[2 * v11], 1u) )
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
0x1800e43f0  mov     [rsp-8+arg_8], rbx
0x1800e43f5  mov     [rsp-8+arg_10], rsi
0x1800e43fa  push    rbp
0x1800e43fb  push    rdi
0x1800e43fc  push    r12
0x1800e43fe  push    r14
0x1800e4400  push    r15
0x1800e4402  lea     rbp, [rsp-37h]
0x1800e4407  sub     rsp, 0A0h
0x1800e440e  xorps   xmm0, xmm0
0x1800e4411  mov     [rbp+57h+var_70], 10000Eh
0x1800e4419  lea     rax, aUsers; "\\Users\\"
0x1800e4420  mov     [rbp+57h+var_40], 40002h
0x1800e4428  xorps   xmm1, xmm1
0x1800e442b  mov     [rbp+57h+var_68], rax
0x1800e442f  lea     rax, asc_180033184; "\\"
0x1800e4436  xor     edi, edi
0x1800e4438  movups  xmmword ptr [rbp+57h+var_30.Length], xmm1
0x1800e443c  mov     [rbp+57h+var_38], rax
0x1800e4440  xor     eax, eax
0x1800e4442  movups  xmm1, xmmword ptr [rcx]
0x1800e4445  mov     [rbp+57h+arg_0], rax
0x1800e4449  mov     r15, r8
0x1800e444c  mov     r12, rdx
0x1800e444f  mov     r14, rcx
0x1800e4452  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800e4456  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e445a  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1800e445e  movdqu  [rbp+57h+var_80], xmm1
0x1800e4463  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e4467  cmp     word ptr [rbp+57h+var_80], ax
0x1800e446b  jbe     loc_1800E4622
0x1800e4471  mov     r8b, 1
0x1800e4474  lea     rdx, [rbp+57h+var_70]
0x1800e4478  lea     rcx, [rbp+57h+var_80]
0x1800e447c  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e4483  nop     dword ptr [rax+rax+00h]
0x1800e4488  mov     rcx, rax
0x1800e448b  test    rax, rax
0x1800e448e  jz      loc_1800E4622
0x1800e4494  movzx   eax, word ptr [rbp+57h+var_70]
0x1800e4498  xor     r8d, r8d
0x1800e449b  shr     rax, 1
0x1800e449e  lea     rdx, [rcx+rax*2]
0x1800e44a2  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800e44a6  mov     rcx, rdx
0x1800e44a9  mov     [rbp+57h+var_30.Buffer], rax
0x1800e44ad  sub     rcx, rax
0x1800e44b0  mov     [rbp+57h+String1.Buffer], rdx
0x1800e44b4  movzx   eax, word ptr [rbp+57h+var_80]
0x1800e44b8  lea     rdx, [rbp+57h+var_40]
0x1800e44bc  sar     rcx, 1
0x1800e44bf  add     cx, cx
0x1800e44c2  sub     ax, cx
0x1800e44c5  mov     [rbp+57h+var_30.Length], cx
0x1800e44c9  mov     [rbp+57h+var_30.MaximumLength], cx
0x1800e44cd  lea     rcx, [rbp+57h+String1]
0x1800e44d1  mov     [rbp+57h+String1.Length], ax
0x1800e44d5  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e44d9  call    cs:__imp_RtlFindUnicodeSubstring
0x1800e44e0  nop     dword ptr [rax+rax+00h]
0x1800e44e5  mov     rbx, rax
0x1800e44e8  test    rax, rax
0x1800e44eb  jz      loc_1800E4622
0x1800e44f1  sub     rax, [rbp+57h+String1.Buffer]
0x1800e44f5  sar     rax, 1
0x1800e44f8  add     ax, ax
0x1800e44fb  mov     [rbp+57h+String1.Length], ax
0x1800e44ff  xor     esi, esi
0x1800e4501  mov     [rbp+57h+String1.MaximumLength], ax
0x1800e4505  movzx   eax, si
0x1800e4508  lea     rcx, qword_180030620
0x1800e450f  add     rax, rax
0x1800e4512  cmp     qword ptr [rcx+rax*8+8], 0
0x1800e4518  jz      short loc_1800E4547
0x1800e451a  lea     rdx, [rcx+rax*8]; String2
0x1800e451e  mov     r8b, 1; CaseInSensitive
0x1800e4521  lea     rcx, [rbp+57h+String1]; String1
0x1800e4525  call    cs:__imp_RtlEqualUnicodeString
0x1800e452c  nop     dword ptr [rax+rax+00h]
0x1800e4531  test    al, al
0x1800e4533  jnz     short loc_1800E453A
0x1800e4535  inc     si
0x1800e4538  jmp     short loc_1800E4505
0x1800e453a  movaps  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x1800e453e  xor     cl, cl
0x1800e4540  movdqa  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x1800e4545  jmp     short loc_1800E4562
0x1800e4547  mov     rax, [rbp+57h+arg_0]
0x1800e454b  mov     cl, 1
0x1800e454d  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800e4550  lea     rax, asc_180035498; "#"
0x1800e4557  mov     [rbp+57h+var_50.Buffer], rax
0x1800e455b  mov     dword ptr [rbp+57h+var_50.Length], 40002h
0x1800e4562  mov     rdx, [r14+8]
0x1800e4566  movzx   esi, word ptr [r14]
0x1800e456a  mov     qword ptr [rbp+57h+var_80+8], rbx
0x1800e456e  movzx   eax, si
0x1800e4571  sub     rbx, rdx
0x1800e4574  sar     rbx, 1
0x1800e4577  add     bx, bx
0x1800e457a  sub     ax, bx
0x1800e457d  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4582  mov     word ptr [rbp+57h+var_80], ax
0x1800e4586  mov     word ptr [rbp+57h+var_80+2], ax
0x1800e458a  jnz     short loc_1800E45EF
0x1800e458c  test    cl, cl
0x1800e458e  jz      short loc_1800E45D8
0x1800e4590  mov     edx, esi
0x1800e4592  mov     ecx, 100h
0x1800e4597  mov     r8d, 63734943h
0x1800e459d  call    cs:__imp_ExAllocatePool2
0x1800e45a4  nop     dword ptr [rax+rax+00h]
0x1800e45a9  mov     [rbp+57h+DestinationString.Buffer], rax
0x1800e45ad  test    rax, rax
0x1800e45b0  jz      short loc_1800E461B
0x1800e45b2  xor     eax, eax
0x1800e45b4  mov     [rbp+57h+DestinationString.MaximumLength], si
0x1800e45b8  mov     [rbp+57h+DestinationString.Length], ax
0x1800e45bc  cmp     [rbp+57h+SourceString.Buffer], rax
0x1800e45c0  jz      short loc_1800E45E4
0x1800e45c2  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800e45c6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e45ca  call    cs:__imp_RtlCopyUnicodeString
0x1800e45d1  nop     dword ptr [rax+rax+00h]
0x1800e45d6  jmp     short loc_1800E45E4
0x1800e45d8  mov     [rbp+57h+SourceString.Buffer], rdx
0x1800e45dc  mov     [rbp+57h+SourceString.Length], bx
0x1800e45e0  mov     [rbp+57h+SourceString.MaximumLength], bx
0x1800e45e4  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e45e9  jz      loc_1800E4463
0x1800e45ef  lea     rdx, [rbp+57h+var_30]; SourceString
0x1800e45f3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e45f7  call    RtlUnicodeStringCat
0x1800e45fc  mov     edi, eax
0x1800e45fe  test    eax, eax
0x1800e4600  js      short loc_1800E466B
0x1800e4602  lea     rdx, [rbp+57h+var_50]; SourceString
0x1800e4606  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e460a  call    RtlUnicodeStringCat
0x1800e460f  mov     edi, eax
0x1800e4611  test    eax, eax
0x1800e4613  jns     loc_1800E4463
0x1800e4619  jmp     short loc_1800E466B
0x1800e461b  mov     edi, 0C0000017h
0x1800e4620  jmp     short loc_1800E466B
0x1800e4622  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800e4627  jnz     short loc_1800E4639
0x1800e4629  movups  xmm0, xmmword ptr [r14]
0x1800e462d  mov     byte ptr [r15], 0
0x1800e4631  movdqu  xmmword ptr [r12], xmm0
0x1800e4637  jmp     short loc_1800E4685
0x1800e4639  movaps  xmm0, [rbp+57h+var_80]
0x1800e463d  lea     rdx, [rbp+57h+String1]; SourceString
0x1800e4641  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800e4645  movdqa  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1800e464a  call    RtlUnicodeStringCat
0x1800e464f  mov     edi, eax
0x1800e4651  test    eax, eax
0x1800e4653  js      short loc_1800E466B
0x1800e4655  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1800e4659  mov     byte ptr [r15], 1
0x1800e465d  mov     [rbp+57h+DestinationString.Buffer], 0
0x1800e4665  movdqu  xmmword ptr [r12], xmm0
0x1800e466b  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1800e466f  test    rcx, rcx
0x1800e4672  jz      short loc_1800E4685
0x1800e4674  mov     edx, 63734943h; Tag
0x1800e4679  call    cs:__imp_ExFreePoolWithTag
0x1800e4680  nop     dword ptr [rax+rax+00h]
0x1800e4685  lea     r11, [rsp+0C0h+var_20]
0x1800e468d  mov     eax, edi
0x1800e468f  mov     rbx, [r11+38h]
0x1800e4693  mov     rsi, [r11+40h]
0x1800e4697  mov     rsp, r11
0x1800e469a  pop     r15
0x1800e469c  pop     r14
0x1800e469e  pop     r12
0x1800e46a0  pop     rdi
0x1800e46a1  pop     rbp
0x1800e46a2  retn
```
