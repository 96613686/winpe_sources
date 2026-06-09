# KappxpNotifyPackagedFile

- ea: `0x18001fcd4`
- end: `0x18001fe63`
- name: `KappxpNotifyPackagedFile`
- size: `399`
- prototype: `__int64 __fastcall(int, int, int, int, PEPROCESS Process, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007fdf4`

## callees

- `0x18001fcd4`
- `0x1800203e0`
- `0x18002c0d0`
- `0x18007fc8c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001fdb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fdc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fdb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fdc7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fde0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fde0`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fd4f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fd4f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fd7f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fd7f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fd90`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fd90`

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
0x18001fcd4  push    rbp
0x18001fcd6  push    rbx
0x18001fcd7  push    rsi
0x18001fcd8  push    rdi
0x18001fcd9  push    r12
0x18001fcdb  push    r14
0x18001fcdd  push    r15
0x18001fcdf  lea     rbp, [rsp-170h]
0x18001fce7  sub     rsp, 270h
0x18001fcee  mov     rax, cs:__security_cookie
0x18001fcf5  xor     rax, rsp
0x18001fcf8  mov     [rbp+1A0h+var_40], rax
0x18001fcff  mov     rbx, [rbp+1A0h+Process]
0x18001fd06  mov     eax, 100h
0x18001fd0b  mov     rsi, [rbp+1A0h+arg_28]
0x18001fd12  mov     r15, r8
0x18001fd15  mov     r12, rdx
0x18001fd18  mov     [rsp+2A0h+var_268], rax
0x18001fd1d  xorps   xmm0, xmm0
0x18001fd20  mov     [rsp+2A0h+var_270], rax
0x18001fd25  xorps   xmm1, xmm1
0x18001fd28  lea     r8, [rsp+2A0h+var_268]
0x18001fd2d  lea     rdx, [rsp+2A0h+SourceString]
0x18001fd32  mov     r14d, r9d
0x18001fd35  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x18001fd3a  movups  xmmword ptr [rsp+2A0h+String2.Length], xmm1
0x18001fd3f  call    KappxDerivePackageFullNameFromPackageFile
0x18001fd44  test    eax, eax
0x18001fd46  js      loc_18001FE41
0x18001fd4c  mov     rcx, rbx; Process
0x18001fd4f  call    cs:__imp_PsReferencePrimaryToken
0x18001fd56  nop     dword ptr [rax+rax+00h]
0x18001fd5b  mov     [rsp+2A0h+var_278], 0
0x18001fd64  lea     r8, [rsp+2A0h+var_270]
0x18001fd69  mov     rcx, rax
0x18001fd6c  mov     [rsp+2A0h+var_280], 0
0x18001fd75  xor     r9d, r9d
0x18001fd78  lea     rdx, [rbp+1A0h+var_140]
0x18001fd7c  mov     rbx, rax
0x18001fd7f  call    cs:__imp_RtlQueryPackageIdentity
0x18001fd86  nop     dword ptr [rax+rax+00h]
0x18001fd8b  mov     rcx, rbx; PrimaryToken
0x18001fd8e  mov     edi, eax
0x18001fd90  call    cs:__imp_PsDereferencePrimaryToken
0x18001fd97  nop     dword ptr [rax+rax+00h]
0x18001fd9c  test    edi, edi
0x18001fd9e  js      short loc_18001FDF4
0x18001fda0  cmp     [rsp+2A0h+var_270], 0
0x18001fda6  jz      short loc_18001FDF4
0x18001fda8  lea     rdx, [rsp+2A0h+SourceString]; SourceString
0x18001fdad  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x18001fdb2  call    cs:__imp_RtlInitUnicodeString
0x18001fdb9  nop     dword ptr [rax+rax+00h]
0x18001fdbe  lea     rdx, [rbp+1A0h+var_140]; SourceString
0x18001fdc2  lea     rcx, [rsp+2A0h+String2]; DestinationString
0x18001fdc7  call    cs:__imp_RtlInitUnicodeString
0x18001fdce  nop     dword ptr [rax+rax+00h]
0x18001fdd3  mov     r8b, 1; CaseInSensitive
0x18001fdd6  lea     rdx, [rsp+2A0h+String2]; String2
0x18001fddb  lea     rcx, [rsp+2A0h+DestinationString]; String1
0x18001fde0  call    cs:__imp_RtlEqualUnicodeString
0x18001fde7  nop     dword ptr [rax+rax+00h]
0x18001fdec  test    al, al
0x18001fdee  setz    r8b
0x18001fdf2  jmp     short loc_18001FE03
0x18001fdf4  xor     r8b, r8b
0x18001fdf7  cmp     edi, 0C0000225h
0x18001fdfd  jz      short loc_18001FE03
0x18001fdff  test    edi, edi
0x18001fe01  js      short loc_18001FE3F
0x18001fe03  mov     al, r8b
0x18001fe06  mov     dword ptr [rsp+2A0h+var_280], r14d
0x18001fe0b  neg     al
0x18001fe0d  lea     rcx, [rsp+2A0h+SourceString]
0x18001fe12  lea     rax, [rsp+2A0h+SourceString]
0x18001fe17  mov     r9, r15
0x18001fe1a  sbb     rdx, rdx
0x18001fe1d  and     rdx, rax
0x18001fe20  lea     rax, [rbp+1A0h+var_140]
0x18001fe24  test    r8b, r8b
0x18001fe27  mov     r8, r12
0x18001fe2a  cmovnz  rcx, rax
0x18001fe2e  call    KappxpStorePackageFileInformation
0x18001fe33  mov     edi, eax
0x18001fe35  test    eax, eax
0x18001fe37  js      short loc_18001FE3F
0x18001fe39  mov     dword ptr [rsi], 0C0000462h
0x18001fe3f  mov     eax, edi
0x18001fe41  mov     rcx, [rbp+1A0h+var_40]
0x18001fe48  xor     rcx, rsp; StackCookie
0x18001fe4b  call    __security_check_cookie
0x18001fe50  add     rsp, 270h
0x18001fe57  pop     r15
0x18001fe59  pop     r14
0x18001fe5b  pop     r12
0x18001fe5d  pop     rdi
0x18001fe5e  pop     rsi
0x18001fe5f  pop     rbx
0x18001fe60  pop     rbp
0x18001fe61  retn
```
