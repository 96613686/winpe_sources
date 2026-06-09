# StSecpGetSidFromPackageFamilyName

- ea: `0x140011350`
- end: `0x1400113cd`
- name: `StSecpGetSidFromPackageFamilyName`
- size: `125`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000dd14`
- `0x140010f90`

## callees

- `0x140011350`
- `0x1400113e0`
- `0x140011810`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140011380`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140011380`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400113aa`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400113aa`

## pseudocode

```c
__int64 __fastcall StSecpGetSidFromPackageFamilyName(PCUNICODE_STRING SourceString, wchar_t **a2)
{
  int PackageSidFromPackageFamilyNameInRegistry; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  PackageSidFromPackageFamilyNameInRegistry = KappxGetPackageSidFromPackageFamilyNameInRegistry(SourceString, a2);
  if ( PackageSidFromPackageFamilyNameInRegistry == -1073741772 )
  {
    PackageSidFromPackageFamilyNameInRegistry = RtlDowncaseUnicodeString(&UnicodeString, SourceString, 1u);
    if ( PackageSidFromPackageFamilyNameInRegistry >= 0 )
      PackageSidFromPackageFamilyNameInRegistry = StSecpGetAppSid((PUCHAR *)&UnicodeString, (__int64)a2);
  }
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)PackageSidFromPackageFamilyNameInRegistry;
}

```

## disassembly

```asm
0x140011350  mov     [rsp+arg_0], rbx
0x140011355  mov     [rsp+arg_8], rsi
0x14001135a  push    rdi
0x14001135b  sub     rsp, 30h
0x14001135f  xorps   xmm0, xmm0
0x140011362  mov     rdi, rdx
0x140011365  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x14001136a  mov     rsi, rcx
0x14001136d  call    KappxGetPackageSidFromPackageFamilyNameInRegistry
0x140011372  mov     ebx, eax
0x140011374  cmp     eax, 0C0000034h
0x140011379  jz      short loc_14001139F
0x14001137b  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x140011380  call    cs:__imp_RtlFreeUnicodeString
0x140011387  nop     dword ptr [rax+rax+00h]
0x14001138c  mov     rsi, [rsp+38h+arg_8]
0x140011391  mov     eax, ebx
0x140011393  mov     rbx, [rsp+38h+arg_0]
0x140011398  add     rsp, 30h
0x14001139c  pop     rdi
0x14001139d  retn
0x14001139f  mov     r8b, 1; AllocateDestinationString
0x1400113a2  lea     rcx, [rsp+38h+UnicodeString]; DestinationString
0x1400113a7  mov     rdx, rsi; SourceString
0x1400113aa  call    cs:__imp_RtlDowncaseUnicodeString
0x1400113b1  nop     dword ptr [rax+rax+00h]
0x1400113b6  mov     ebx, eax
0x1400113b8  test    eax, eax
0x1400113ba  js      short loc_14001137B
0x1400113bc  mov     rdx, rdi
0x1400113bf  lea     rcx, [rsp+38h+UnicodeString]
0x1400113c4  call    StSecpGetAppSid
0x1400113c9  mov     ebx, eax
0x1400113cb  jmp     short loc_14001137B
```
