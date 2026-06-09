# KappxpNotifyPackagedFile

- ea: `0x18001fc94`
- end: `0x18001fe23`
- name: `KappxpNotifyPackagedFile`
- size: `399`
- prototype: `__int64 __fastcall(int, int, int, int, PEPROCESS Process, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007ddb4`

## callees

- `0x18001fc94`
- `0x1800203a0`
- `0x18002bef0`
- `0x18007dc4c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001fd72`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fd87`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fd72`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001fd87`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fda0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18001fda0`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fd0f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18001fd0f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fd3f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x18001fd3f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fd50`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18001fd50`

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
0x18001fc94  push    rbp
0x18001fc96  push    rbx
0x18001fc97  push    rsi
0x18001fc98  push    rdi
0x18001fc99  push    r12
0x18001fc9b  push    r14
0x18001fc9d  push    r15
0x18001fc9f  lea     rbp, [rsp-170h]
0x18001fca7  sub     rsp, 270h
0x18001fcae  mov     rax, cs:__security_cookie
0x18001fcb5  xor     rax, rsp
0x18001fcb8  mov     [rbp+1A0h+var_40], rax
0x18001fcbf  mov     rbx, [rbp+1A0h+Process]
0x18001fcc6  mov     eax, 100h
0x18001fccb  mov     rsi, [rbp+1A0h+arg_28]
0x18001fcd2  mov     r15, r8
0x18001fcd5  mov     r12, rdx
0x18001fcd8  mov     [rsp+2A0h+var_268], rax
0x18001fcdd  xorps   xmm0, xmm0
0x18001fce0  mov     [rsp+2A0h+var_270], rax
0x18001fce5  xorps   xmm1, xmm1
0x18001fce8  lea     r8, [rsp+2A0h+var_268]
0x18001fced  lea     rdx, [rsp+2A0h+SourceString]
0x18001fcf2  mov     r14d, r9d
0x18001fcf5  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x18001fcfa  movups  xmmword ptr [rsp+2A0h+String2.Length], xmm1
0x18001fcff  call    KappxDerivePackageFullNameFromPackageFile
0x18001fd04  test    eax, eax
0x18001fd06  js      loc_18001FE01
0x18001fd0c  mov     rcx, rbx; Process
0x18001fd0f  call    cs:__imp_PsReferencePrimaryToken
0x18001fd16  nop     dword ptr [rax+rax+00h]
0x18001fd1b  mov     [rsp+2A0h+var_278], 0
0x18001fd24  lea     r8, [rsp+2A0h+var_270]
0x18001fd29  mov     rcx, rax
0x18001fd2c  mov     [rsp+2A0h+var_280], 0
0x18001fd35  xor     r9d, r9d
0x18001fd38  lea     rdx, [rbp+1A0h+var_140]
0x18001fd3c  mov     rbx, rax
0x18001fd3f  call    cs:__imp_RtlQueryPackageIdentity
0x18001fd46  nop     dword ptr [rax+rax+00h]
0x18001fd4b  mov     rcx, rbx; PrimaryToken
0x18001fd4e  mov     edi, eax
0x18001fd50  call    cs:__imp_PsDereferencePrimaryToken
0x18001fd57  nop     dword ptr [rax+rax+00h]
0x18001fd5c  test    edi, edi
0x18001fd5e  js      short loc_18001FDB4
0x18001fd60  cmp     [rsp+2A0h+var_270], 0
0x18001fd66  jz      short loc_18001FDB4
0x18001fd68  lea     rdx, [rsp+2A0h+SourceString]; SourceString
0x18001fd6d  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x18001fd72  call    cs:__imp_RtlInitUnicodeString
0x18001fd79  nop     dword ptr [rax+rax+00h]
0x18001fd7e  lea     rdx, [rbp+1A0h+var_140]; SourceString
0x18001fd82  lea     rcx, [rsp+2A0h+String2]; DestinationString
0x18001fd87  call    cs:__imp_RtlInitUnicodeString
0x18001fd8e  nop     dword ptr [rax+rax+00h]
0x18001fd93  mov     r8b, 1; CaseInSensitive
0x18001fd96  lea     rdx, [rsp+2A0h+String2]; String2
0x18001fd9b  lea     rcx, [rsp+2A0h+DestinationString]; String1
0x18001fda0  call    cs:__imp_RtlEqualUnicodeString
0x18001fda7  nop     dword ptr [rax+rax+00h]
0x18001fdac  test    al, al
0x18001fdae  setz    r8b
0x18001fdb2  jmp     short loc_18001FDC3
0x18001fdb4  xor     r8b, r8b
0x18001fdb7  cmp     edi, 0C0000225h
0x18001fdbd  jz      short loc_18001FDC3
0x18001fdbf  test    edi, edi
0x18001fdc1  js      short loc_18001FDFF
0x18001fdc3  mov     al, r8b
0x18001fdc6  mov     dword ptr [rsp+2A0h+var_280], r14d
0x18001fdcb  neg     al
0x18001fdcd  lea     rcx, [rsp+2A0h+SourceString]
0x18001fdd2  lea     rax, [rsp+2A0h+SourceString]
0x18001fdd7  mov     r9, r15
0x18001fdda  sbb     rdx, rdx
0x18001fddd  and     rdx, rax
0x18001fde0  lea     rax, [rbp+1A0h+var_140]
0x18001fde4  test    r8b, r8b
0x18001fde7  mov     r8, r12
0x18001fdea  cmovnz  rcx, rax
0x18001fdee  call    KappxpStorePackageFileInformation
0x18001fdf3  mov     edi, eax
0x18001fdf5  test    eax, eax
0x18001fdf7  js      short loc_18001FDFF
0x18001fdf9  mov     dword ptr [rsi], 0C0000462h
0x18001fdff  mov     eax, edi
0x18001fe01  mov     rcx, [rbp+1A0h+var_40]
0x18001fe08  xor     rcx, rsp; StackCookie
0x18001fe0b  call    __security_check_cookie
0x18001fe10  add     rsp, 270h
0x18001fe17  pop     r15
0x18001fe19  pop     r14
0x18001fe1b  pop     r12
0x18001fe1d  pop     rdi
0x18001fe1e  pop     rsi
0x18001fe1f  pop     rbx
0x18001fe20  pop     rbp
0x18001fe21  retn
```
