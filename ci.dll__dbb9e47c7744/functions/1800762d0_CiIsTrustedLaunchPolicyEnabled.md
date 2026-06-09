# CiIsTrustedLaunchPolicyEnabled

- ea: `0x1800762d0`
- end: `0x180076419`
- name: `CiIsTrustedLaunchPolicyEnabled`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006005c`

## callees

- `0x1800762d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007634d`
- `ntoskrnl!ExAllocatePool2` at `0x18007634d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076400`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076400`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076317`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076390`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076317`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076390`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800763c6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800763e4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800763c6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800763e4`

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
  v4 = SeQuerySecurityAttributesToken(a1, &qword_180030DC8, 1, v10, 16, &v11);
  v5 = v4;
  if ( v4 == -1073741789 )
  {
    Pool2 = ExAllocatePool2(258, v11, 1668499779);
    v7 = Pool2;
    if ( Pool2 )
    {
      v5 = SeQuerySecurityAttributesToken(a1, &qword_180030DC8, 1, Pool2, v11, &v11);
      if ( v5 >= 0 )
      {
        if ( *(_DWORD *)(v7 + 4) )
        {
          v8 = *(_QWORD *)(v7 + 8);
          if ( *(_DWORD *)(v8 + 24) )
          {
            if ( *(_WORD *)(v8 + 16) == 3
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v7 + 8), &stru_180030DD8, 1u)
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v8 + 32), &stru_180030DF8, 1u) )
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
0x1800762d0  push    rbx
0x1800762d2  push    rsi
0x1800762d3  push    rdi
0x1800762d4  push    r14
0x1800762d6  sub     rsp, 48h
0x1800762da  lea     rax, [rsp+68h+arg_8]
0x1800762df  mov     byte ptr [rdx], 0
0x1800762e2  mov     r14, rdx
0x1800762e5  mov     [rsp+68h+var_40], rax
0x1800762ea  xorps   xmm0, xmm0
0x1800762ed  mov     [rsp+68h+var_48], 10h
0x1800762f5  lea     r9, [rsp+68h+var_38]
0x1800762fa  mov     [rsp+68h+arg_8], 0
0x180076302  mov     r8d, 1
0x180076308  lea     rdx, qword_180030DC8
0x18007630f  mov     rsi, rcx
0x180076312  movups  [rsp+68h+var_38], xmm0
0x180076317  call    cs:__imp_SeQuerySecurityAttributesToken
0x18007631e  nop     dword ptr [rax+rax+00h]
0x180076323  mov     ebx, eax
0x180076325  cmp     eax, 0C0000023h
0x18007632a  jz      short loc_18007633E
0x18007632c  cmp     eax, 0C0000225h
0x180076331  jnz     loc_18007640C
0x180076337  xor     ebx, ebx
0x180076339  jmp     loc_18007640C
0x18007633e  mov     edx, [rsp+68h+arg_8]
0x180076342  mov     ecx, 102h
0x180076347  mov     r8d, 63734943h
0x18007634d  call    cs:__imp_ExAllocatePool2
0x180076354  nop     dword ptr [rax+rax+00h]
0x180076359  mov     rdi, rax
0x18007635c  test    rax, rax
0x18007635f  jnz     short loc_18007636B
0x180076361  mov     ebx, 0C0000017h
0x180076366  jmp     loc_18007640C
0x18007636b  lea     rax, [rsp+68h+arg_8]
0x180076370  mov     r9, rdi
0x180076373  mov     [rsp+68h+var_40], rax
0x180076378  lea     rdx, qword_180030DC8
0x18007637f  mov     eax, [rsp+68h+arg_8]
0x180076383  mov     r8d, 1
0x180076389  mov     rcx, rsi
0x18007638c  mov     [rsp+68h+var_48], eax
0x180076390  call    cs:__imp_SeQuerySecurityAttributesToken
0x180076397  nop     dword ptr [rax+rax+00h]
0x18007639c  mov     ebx, eax
0x18007639e  test    eax, eax
0x1800763a0  js      short loc_1800763F8
0x1800763a2  cmp     dword ptr [rdi+4], 0
0x1800763a6  jz      short loc_1800763F8
0x1800763a8  mov     rsi, [rdi+8]
0x1800763ac  cmp     dword ptr [rsi+18h], 0
0x1800763b0  jbe     short loc_1800763F8
0x1800763b2  cmp     word ptr [rsi+10h], 3
0x1800763b7  jnz     short loc_1800763F8
0x1800763b9  mov     r8b, 1; CaseInSensitive
0x1800763bc  lea     rdx, stru_180030DD8; String2
0x1800763c3  mov     rcx, rsi; String1
0x1800763c6  call    cs:__imp_RtlEqualUnicodeString
0x1800763cd  nop     dword ptr [rax+rax+00h]
0x1800763d2  test    al, al
0x1800763d4  jz      short loc_1800763F8
0x1800763d6  mov     rcx, [rsi+20h]; String1
0x1800763da  lea     rdx, stru_180030DF8; String2
0x1800763e1  mov     r8b, 1; CaseInSensitive
0x1800763e4  call    cs:__imp_RtlEqualUnicodeString
0x1800763eb  nop     dword ptr [rax+rax+00h]
0x1800763f0  test    al, al
0x1800763f2  jz      short loc_1800763F8
0x1800763f4  mov     byte ptr [r14], 1
0x1800763f8  mov     edx, 63734943h; Tag
0x1800763fd  mov     rcx, rdi; P
0x180076400  call    cs:__imp_ExFreePoolWithTag
0x180076407  nop     dword ptr [rax+rax+00h]
0x18007640c  mov     eax, ebx
0x18007640e  add     rsp, 48h
0x180076412  pop     r14
0x180076414  pop     rdi
0x180076415  pop     rsi
0x180076416  pop     rbx
0x180076417  retn
```
