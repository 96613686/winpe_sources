# StSecpGetParameterValue

- ea: `0x140010f90`
- end: `0x140011142`
- name: `StSecpGetParameterValue`
- size: `434`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010890`

## callees

- `0x14000dd14`
- `0x14000dd68`
- `0x140010f90`
- `0x140011150`
- `0x140011350`
- `0x140011a30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011131`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011131`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011013`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011058`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011097`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400110c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400110fa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011013`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011058`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011097`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400110c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400110fa`

## pseudocode

```c
__int64 __fastcall StSecpGetParameterValue(PCUNICODE_STRING String1, PCUNICODE_STRING SourceString, PVOID *a3)
{
  int SidFromUserName; // ebx
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING v9; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING v10; // [rsp+40h] [rbp-38h] BYREF
  UNICODE_STRING v11; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING v12; // [rsp+60h] [rbp-18h] BYREF
  PVOID P; // [rsp+B8h] [rbp+40h] BYREF

  *(_QWORD *)&String2.Length = 917516;
  String2.Buffer = L"<User>";
  *(_QWORD *)&v9.Length = 2621478;
  v9.Buffer = (PWSTR)L"<PackageFamilyName>";
  *(_QWORD *)&v11.Length = 2359330;
  v11.Buffer = (PWSTR)L"<PackageFullName>";
  *(_QWORD *)&v12.Length = 1572886;
  v12.Buffer = (PWSTR)L"<ProductId>";
  *(_QWORD *)&v10.Length = 3670070;
  v10.Buffer = L"<PackageFullNameRedirected>";
  P = 0;
  if ( !RtlCompareUnicodeString(String1, &String2, 1u) )
  {
    SidFromUserName = StSecpGetSidFromUserName(SourceString, &P);
    if ( SidFromUserName < 0 )
      goto LABEL_3;
LABEL_8:
    *a3 = P;
    return 0;
  }
  if ( !RtlCompareUnicodeString(String1, &v9, 1u) )
  {
    SidFromUserName = StSecpGetSidFromPackageFamilyName(SourceString);
    if ( SidFromUserName < 0 )
      goto LABEL_3;
    goto LABEL_8;
  }
  if ( !RtlCompareUnicodeString(String1, &v10, 1u) )
  {
    SidFromUserName = KappxGetSecurityDescriptorStringForPackageFullName(SourceString, &P);
    if ( SidFromUserName < 0 )
      goto LABEL_3;
    goto LABEL_8;
  }
  if ( !RtlCompareUnicodeString(String1, &v11, 1u) )
  {
    SidFromUserName = StSecpGetSidFromPackageFullName(SourceString, &P);
    if ( SidFromUserName < 0 )
      goto LABEL_3;
    goto LABEL_8;
  }
  if ( RtlCompareUnicodeString(String1, &v12, 1u) )
  {
    SidFromUserName = -1073741823;
    goto LABEL_3;
  }
  SidFromUserName = StSecpGetSidFromProductId(SourceString);
  if ( SidFromUserName >= 0 )
    goto LABEL_8;
LABEL_3:
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)SidFromUserName;
}

```

## disassembly

```asm
0x140010f90  push    rbp
0x140010f92  push    rbx
0x140010f93  push    rsi
0x140010f94  push    rdi
0x140010f95  mov     rbp, rsp
0x140010f98  sub     rsp, 78h
0x140010f9c  lea     rax, aUser; "<User>"
0x140010fa3  mov     qword ptr [rbp+String2.Length], 0E000Ch
0x140010fab  mov     [rbp+String2.Buffer], rax
0x140010faf  mov     rsi, r8
0x140010fb2  lea     rax, aPackagefamilyn; "<PackageFamilyName>"
0x140010fb9  mov     qword ptr [rbp+var_48.Length], 280026h
0x140010fc1  mov     [rbp+var_48.Buffer], rax
0x140010fc5  mov     rbx, rdx
0x140010fc8  lea     rax, aPackagefullnam_0; "<PackageFullName>"
0x140010fcf  mov     qword ptr [rbp+var_28.Length], 240022h
0x140010fd7  mov     [rbp+var_28.Buffer], rax
0x140010fdb  lea     rdx, [rbp+String2]; String2
0x140010fdf  lea     rax, aProductid; "<ProductId>"
0x140010fe6  mov     qword ptr [rbp+var_18.Length], 180016h
0x140010fee  mov     [rbp+var_18.Buffer], rax
0x140010ff2  mov     r8b, 1; CaseInSensitive
0x140010ff5  lea     rax, aPackagefullnam; "<PackageFullNameRedirected>"
0x140010ffc  mov     qword ptr [rbp+var_38.Length], 380036h
0x140011004  mov     [rbp+var_38.Buffer], rax
0x140011008  mov     rdi, rcx
0x14001100b  mov     [rbp+P], 0
0x140011013  call    cs:__imp_RtlCompareUnicodeString
0x14001101a  nop     dword ptr [rax+rax+00h]
0x14001101f  test    eax, eax
0x140011021  jnz     short loc_14001104E
0x140011023  lea     rdx, [rbp+P]
0x140011027  mov     rcx, rbx
0x14001102a  call    StSecpGetSidFromUserName
0x14001102f  mov     ebx, eax
0x140011031  test    eax, eax
0x140011033  jns     short loc_14001107A
0x140011035  mov     rcx, [rbp+P]; P
0x140011039  test    rcx, rcx
0x14001103c  jnz     loc_14001112F
0x140011042  mov     eax, ebx
0x140011044  add     rsp, 78h
0x140011048  pop     rdi
0x140011049  pop     rsi
0x14001104a  pop     rbx
0x14001104b  pop     rbp
0x14001104c  retn
0x14001104e  mov     r8b, 1; CaseInSensitive
0x140011051  lea     rdx, [rbp+var_48]; String2
0x140011055  mov     rcx, rdi; String1
0x140011058  call    cs:__imp_RtlCompareUnicodeString
0x14001105f  nop     dword ptr [rax+rax+00h]
0x140011064  test    eax, eax
0x140011066  jnz     short loc_14001108D
0x140011068  lea     rdx, [rbp+P]
0x14001106c  mov     rcx, rbx; SourceString
0x14001106f  call    StSecpGetSidFromPackageFamilyName
0x140011074  mov     ebx, eax
0x140011076  test    eax, eax
0x140011078  js      short loc_140011035
0x14001107a  mov     rax, [rbp+P]
0x14001107e  mov     [rsi], rax
0x140011081  xor     eax, eax
0x140011083  add     rsp, 78h
0x140011087  pop     rdi
0x140011088  pop     rsi
0x140011089  pop     rbx
0x14001108a  pop     rbp
0x14001108b  retn
0x14001108d  mov     r8b, 1; CaseInSensitive
0x140011090  lea     rdx, [rbp+var_38]; String2
0x140011094  mov     rcx, rdi; String1
0x140011097  call    cs:__imp_RtlCompareUnicodeString
0x14001109e  nop     dword ptr [rax+rax+00h]
0x1400110a3  test    eax, eax
0x1400110a5  jnz     short loc_1400110BE
0x1400110a7  lea     rdx, [rbp+P]
0x1400110ab  mov     rcx, rbx
0x1400110ae  call    KappxGetSecurityDescriptorStringForPackageFullName
0x1400110b3  mov     ebx, eax
0x1400110b5  test    eax, eax
0x1400110b7  jns     short loc_14001107A
0x1400110b9  jmp     loc_140011035
0x1400110be  mov     r8b, 1; CaseInSensitive
0x1400110c1  lea     rdx, [rbp+var_28]; String2
0x1400110c5  mov     rcx, rdi; String1
0x1400110c8  call    cs:__imp_RtlCompareUnicodeString
0x1400110cf  nop     dword ptr [rax+rax+00h]
0x1400110d4  test    eax, eax
0x1400110d6  jnz     short loc_1400110F0
0x1400110d8  lea     rdx, [rbp+P]
0x1400110dc  mov     rcx, rbx
0x1400110df  call    StSecpGetSidFromPackageFullName
0x1400110e4  mov     ebx, eax
0x1400110e6  test    eax, eax
0x1400110e8  js      loc_140011035
0x1400110ee  jmp     short loc_14001107A
0x1400110f0  mov     r8b, 1; CaseInSensitive
0x1400110f3  lea     rdx, [rbp+var_18]; String2
0x1400110f7  mov     rcx, rdi; String1
0x1400110fa  call    cs:__imp_RtlCompareUnicodeString
0x140011101  nop     dword ptr [rax+rax+00h]
0x140011106  test    eax, eax
0x140011108  jnz     short loc_140011125
0x14001110a  lea     rdx, [rbp+P]
0x14001110e  mov     rcx, rbx; SourceString
0x140011111  call    StSecpGetSidFromProductId
0x140011116  mov     ebx, eax
0x140011118  test    eax, eax
0x14001111a  js      loc_140011035
0x140011120  jmp     loc_14001107A
0x140011125  mov     ebx, 0C0000001h
0x14001112a  jmp     loc_140011035
0x14001112f  xor     edx, edx; Tag
0x140011131  call    cs:__imp_ExFreePoolWithTag
0x140011138  nop     dword ptr [rax+rax+00h]
0x14001113d  jmp     loc_140011042
```
