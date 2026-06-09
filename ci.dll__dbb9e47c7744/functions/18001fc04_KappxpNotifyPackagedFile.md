# KappxpNotifyPackagedFile

- ea: `0x18001fc04`
- end: `0x18001fd93`
- name: `KappxpNotifyPackagedFile`
- size: `399`
- prototype: `__int64 __fastcall(int, int, int, int, PEPROCESS Process, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007f3e0`

## callees

- `0x18001fc04`
- `0x180020310`
- `0x18002bf20`
- `0x18007f278`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001fce2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fcf7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fce2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fcf7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fd10`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fd10`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fc7f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fc7f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fcaf`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fcaf`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fcc0`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fcc0`

## pseudocode

```c
__int64 __fastcall KappxpNotifyPackagedFile(__int64 a1, __int64 a2, __int64 a3, int a4, PEPROCESS Process, _DWORD *a6)
{
  __int64 result; // rax
  PACCESS_TOKEN v10; // rbx
  int v11; // edi
  bool v12; // r8
  WCHAR *v13; // rcx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SourceString[128]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v19[128]; // [rsp+160h] [rbp+60h] BYREF

  v15 = 256;
  v14 = 256;
  DestinationString = 0;
  String2 = 0;
  result = KappxDerivePackageFullNameFromPackageFile(a1, SourceString, &v15);
  if ( (int)result >= 0 )
  {
    v10 = PsReferencePrimaryToken(Process);
    v11 = RtlQueryPackageIdentity(v10, v19, &v14, 0, 0, 0);
    PsDereferencePrimaryToken(v10);
    if ( v11 >= 0 && v14 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      RtlInitUnicodeString(&String2, v19);
      v12 = RtlEqualUnicodeString(&DestinationString, &String2, 1u) == 0;
    }
    else
    {
      v12 = 0;
      if ( v11 != -1073741275 && v11 < 0 )
        return (unsigned int)v11;
    }
    v13 = SourceString;
    if ( v12 )
      v13 = v19;
    v11 = KappxpStorePackageFileInformation(v13, (unsigned __int64)SourceString & -(__int64)v12, a2, a3, a4);
    if ( v11 >= 0 )
      *a6 = -1073740702;
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x18001fc04  push    rbp
0x18001fc06  push    rbx
0x18001fc07  push    rsi
0x18001fc08  push    rdi
0x18001fc09  push    r12
0x18001fc0b  push    r14
0x18001fc0d  push    r15
0x18001fc0f  lea     rbp, [rsp-170h]
0x18001fc17  sub     rsp, 270h
0x18001fc1e  mov     rax, cs:__security_cookie
0x18001fc25  xor     rax, rsp
0x18001fc28  mov     [rbp+1A0h+var_40], rax
0x18001fc2f  mov     rbx, [rbp+1A0h+Process]
0x18001fc36  mov     eax, 100h
0x18001fc3b  mov     rsi, [rbp+1A0h+arg_28]
0x18001fc42  mov     r15, r8
0x18001fc45  mov     r12, rdx
0x18001fc48  mov     [rsp+2A0h+var_268], rax
0x18001fc4d  xorps   xmm0, xmm0
0x18001fc50  mov     [rsp+2A0h+var_270], rax
0x18001fc55  xorps   xmm1, xmm1
0x18001fc58  lea     r8, [rsp+2A0h+var_268]
0x18001fc5d  lea     rdx, [rsp+2A0h+SourceString]
0x18001fc62  mov     r14d, r9d
0x18001fc65  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x18001fc6a  movups  xmmword ptr [rsp+2A0h+String2.Length], xmm1
0x18001fc6f  call    KappxDerivePackageFullNameFromPackageFile
0x18001fc74  test    eax, eax
0x18001fc76  js      loc_18001FD71
0x18001fc7c  mov     rcx, rbx; Process
0x18001fc7f  call    cs:__imp_PsReferencePrimaryToken
0x18001fc86  nop     dword ptr [rax+rax+00h]
0x18001fc8b  mov     [rsp+2A0h+var_278], 0
0x18001fc94  lea     r8, [rsp+2A0h+var_270]
0x18001fc99  mov     rcx, rax
0x18001fc9c  mov     [rsp+2A0h+var_280], 0
0x18001fca5  xor     r9d, r9d
0x18001fca8  lea     rdx, [rbp+1A0h+var_140]
0x18001fcac  mov     rbx, rax
0x18001fcaf  call    cs:__imp_RtlQueryPackageIdentity
0x18001fcb6  nop     dword ptr [rax+rax+00h]
0x18001fcbb  mov     rcx, rbx; PrimaryToken
0x18001fcbe  mov     edi, eax
0x18001fcc0  call    cs:__imp_PsDereferencePrimaryToken
0x18001fcc7  nop     dword ptr [rax+rax+00h]
0x18001fccc  test    edi, edi
0x18001fcce  js      short loc_18001FD24
0x18001fcd0  cmp     [rsp+2A0h+var_270], 0
0x18001fcd6  jz      short loc_18001FD24
0x18001fcd8  lea     rdx, [rsp+2A0h+SourceString]; SourceString
0x18001fcdd  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x18001fce2  call    cs:__imp_RtlInitUnicodeString
0x18001fce9  nop     dword ptr [rax+rax+00h]
0x18001fcee  lea     rdx, [rbp+1A0h+var_140]; SourceString
0x18001fcf2  lea     rcx, [rsp+2A0h+String2]; DestinationString
0x18001fcf7  call    cs:__imp_RtlInitUnicodeString
0x18001fcfe  nop     dword ptr [rax+rax+00h]
0x18001fd03  mov     r8b, 1; CaseInSensitive
0x18001fd06  lea     rdx, [rsp+2A0h+String2]; String2
0x18001fd0b  lea     rcx, [rsp+2A0h+DestinationString]; String1
0x18001fd10  call    cs:__imp_RtlEqualUnicodeString
0x18001fd17  nop     dword ptr [rax+rax+00h]
0x18001fd1c  test    al, al
0x18001fd1e  setz    r8b
0x18001fd22  jmp     short loc_18001FD33
0x18001fd24  xor     r8b, r8b
0x18001fd27  cmp     edi, 0C0000225h
0x18001fd2d  jz      short loc_18001FD33
0x18001fd2f  test    edi, edi
0x18001fd31  js      short loc_18001FD6F
0x18001fd33  mov     al, r8b
0x18001fd36  mov     dword ptr [rsp+2A0h+var_280], r14d
0x18001fd3b  neg     al
0x18001fd3d  lea     rcx, [rsp+2A0h+SourceString]
0x18001fd42  lea     rax, [rsp+2A0h+SourceString]
0x18001fd47  mov     r9, r15
0x18001fd4a  sbb     rdx, rdx
0x18001fd4d  and     rdx, rax
0x18001fd50  lea     rax, [rbp+1A0h+var_140]
0x18001fd54  test    r8b, r8b
0x18001fd57  mov     r8, r12
0x18001fd5a  cmovnz  rcx, rax
0x18001fd5e  call    KappxpStorePackageFileInformation
0x18001fd63  mov     edi, eax
0x18001fd65  test    eax, eax
0x18001fd67  js      short loc_18001FD6F
0x18001fd69  mov     dword ptr [rsi], 0C0000462h
0x18001fd6f  mov     eax, edi
0x18001fd71  mov     rcx, [rbp+1A0h+var_40]
0x18001fd78  xor     rcx, rsp; StackCookie
0x18001fd7b  call    __security_check_cookie
0x18001fd80  add     rsp, 270h
0x18001fd87  pop     r15
0x18001fd89  pop     r14
0x18001fd8b  pop     r12
0x18001fd8d  pop     rdi
0x18001fd8e  pop     rsi
0x18001fd8f  pop     rbx
0x18001fd90  pop     rbp
0x18001fd91  retn
```
