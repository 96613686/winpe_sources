# CiIsTrustedLaunchPolicyEnabled

- ea: `0x180074d14`
- end: `0x180074e5d`
- name: `CiIsTrustedLaunchPolicyEnabled`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f96c`

## callees

- `0x180074d14`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180074d91`
- `ntoskrnl!ExAllocatePool2` at `0x180074d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x180074e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x180074e44`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180074d5b`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180074dd4`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180074d5b`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180074dd4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180074e0a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180074e28`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180074e0a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180074e28`

## pseudocode

```c
__int64 __fastcall CiIsTrustedLaunchPolicyEnabled(__int64 a1, _BYTE *a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 Pool2; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  _OWORD v10[3]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  v11 = 0;
  v10[0] = 0;
  v4 = SeQuerySecurityAttributesToken(a1, &qword_180030D18, 1, v10, 16, &v11);
  v5 = v4;
  if ( v4 == -1073741789 )
  {
    Pool2 = ExAllocatePool2(258, v11, 1668499779);
    v7 = Pool2;
    if ( Pool2 )
    {
      v5 = SeQuerySecurityAttributesToken(a1, &qword_180030D18, 1, Pool2, v11, &v11);
      if ( v5 >= 0 )
      {
        if ( *(_DWORD *)(v7 + 4) )
        {
          v8 = *(_QWORD *)(v7 + 8);
          if ( *(_DWORD *)(v8 + 24) )
          {
            if ( *(_WORD *)(v8 + 16) == 3
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v7 + 8), &stru_180030D28, 1u)
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v8 + 32), &stru_180030D48, 1u) )
            {
              *a2 = 1;
            }
          }
        }
      }
      ExFreePoolWithTag((PVOID)v7, 0x63734943u);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else if ( v4 == -1073741275 )
  {
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180074d14  push    rbx
0x180074d16  push    rsi
0x180074d17  push    rdi
0x180074d18  push    r14
0x180074d1a  sub     rsp, 48h
0x180074d1e  lea     rax, [rsp+68h+arg_8]
0x180074d23  mov     byte ptr [rdx], 0
0x180074d26  mov     r14, rdx
0x180074d29  mov     [rsp+68h+var_40], rax
0x180074d2e  xorps   xmm0, xmm0
0x180074d31  mov     [rsp+68h+var_48], 10h
0x180074d39  lea     r9, [rsp+68h+var_38]
0x180074d3e  mov     [rsp+68h+arg_8], 0
0x180074d46  mov     r8d, 1
0x180074d4c  lea     rdx, qword_180030D18
0x180074d53  mov     rsi, rcx
0x180074d56  movups  [rsp+68h+var_38], xmm0
0x180074d5b  call    cs:__imp_SeQuerySecurityAttributesToken
0x180074d62  nop     dword ptr [rax+rax+00h]
0x180074d67  mov     ebx, eax
0x180074d69  cmp     eax, 0C0000023h
0x180074d6e  jz      short loc_180074D82
0x180074d70  cmp     eax, 0C0000225h
0x180074d75  jnz     loc_180074E50
0x180074d7b  xor     ebx, ebx
0x180074d7d  jmp     loc_180074E50
0x180074d82  mov     edx, [rsp+68h+arg_8]
0x180074d86  mov     ecx, 102h
0x180074d8b  mov     r8d, 63734943h
0x180074d91  call    cs:__imp_ExAllocatePool2
0x180074d98  nop     dword ptr [rax+rax+00h]
0x180074d9d  mov     rdi, rax
0x180074da0  test    rax, rax
0x180074da3  jnz     short loc_180074DAF
0x180074da5  mov     ebx, 0C0000017h
0x180074daa  jmp     loc_180074E50
0x180074daf  lea     rax, [rsp+68h+arg_8]
0x180074db4  mov     r9, rdi
0x180074db7  mov     [rsp+68h+var_40], rax
0x180074dbc  lea     rdx, qword_180030D18
0x180074dc3  mov     eax, [rsp+68h+arg_8]
0x180074dc7  mov     r8d, 1
0x180074dcd  mov     rcx, rsi
0x180074dd0  mov     [rsp+68h+var_48], eax
0x180074dd4  call    cs:__imp_SeQuerySecurityAttributesToken
0x180074ddb  nop     dword ptr [rax+rax+00h]
0x180074de0  mov     ebx, eax
0x180074de2  test    eax, eax
0x180074de4  js      short loc_180074E3C
0x180074de6  cmp     dword ptr [rdi+4], 0
0x180074dea  jz      short loc_180074E3C
0x180074dec  mov     rsi, [rdi+8]
0x180074df0  cmp     dword ptr [rsi+18h], 0
0x180074df4  jbe     short loc_180074E3C
0x180074df6  cmp     word ptr [rsi+10h], 3
0x180074dfb  jnz     short loc_180074E3C
0x180074dfd  mov     r8b, 1; CaseInSensitive
0x180074e00  lea     rdx, stru_180030D28; String2
0x180074e07  mov     rcx, rsi; String1
0x180074e0a  call    cs:__imp_RtlEqualUnicodeString
0x180074e11  nop     dword ptr [rax+rax+00h]
0x180074e16  test    al, al
0x180074e18  jz      short loc_180074E3C
0x180074e1a  mov     rcx, [rsi+20h]; String1
0x180074e1e  lea     rdx, stru_180030D48; String2
0x180074e25  mov     r8b, 1; CaseInSensitive
0x180074e28  call    cs:__imp_RtlEqualUnicodeString
0x180074e2f  nop     dword ptr [rax+rax+00h]
0x180074e34  test    al, al
0x180074e36  jz      short loc_180074E3C
0x180074e38  mov     byte ptr [r14], 1
0x180074e3c  mov     edx, 63734943h; Tag
0x180074e41  mov     rcx, rdi; P
0x180074e44  call    cs:__imp_ExFreePoolWithTag
0x180074e4b  nop     dword ptr [rax+rax+00h]
0x180074e50  mov     eax, ebx
0x180074e52  add     rsp, 48h
0x180074e56  pop     r14
0x180074e58  pop     rdi
0x180074e59  pop     rsi
0x180074e5a  pop     rbx
0x180074e5b  retn
```
