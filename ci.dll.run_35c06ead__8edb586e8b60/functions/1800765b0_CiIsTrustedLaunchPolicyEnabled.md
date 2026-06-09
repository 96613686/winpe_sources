# CiIsTrustedLaunchPolicyEnabled

- ea: `0x1800765b0`
- end: `0x1800766f9`
- name: `CiIsTrustedLaunchPolicyEnabled`
- size: `329`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fffc`

## callees

- `0x1800765b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007662d`
- `ntoskrnl!ExAllocatePool2` at `0x18007662d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800766e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800766e0`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800765f7`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076670`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800765f7`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x180076670`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800766a6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800766c4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800766a6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800766c4`

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
  v4 = SeQuerySecurityAttributesToken(a1, &qword_180030DA8, 1, v10, 16, &v11);
  v5 = v4;
  if ( v4 == -1073741789 )
  {
    Pool2 = ExAllocatePool2(258, v11, 1668499779);
    v7 = Pool2;
    if ( Pool2 )
    {
      v5 = SeQuerySecurityAttributesToken(a1, &qword_180030DA8, 1, Pool2, v11, &v11);
      if ( v5 >= 0 )
      {
        if ( *(_DWORD *)(v7 + 4) )
        {
          v8 = *(_QWORD *)(v7 + 8);
          if ( *(_DWORD *)(v8 + 24) )
          {
            if ( *(_WORD *)(v8 + 16) == 3
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v7 + 8), &stru_180030DB8, 1u)
              && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v8 + 32), &stru_180030DC8, 1u) )
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
0x1800765b0  push    rbx
0x1800765b2  push    rsi
0x1800765b3  push    rdi
0x1800765b4  push    r14
0x1800765b6  sub     rsp, 48h
0x1800765ba  lea     rax, [rsp+68h+arg_8]
0x1800765bf  mov     byte ptr [rdx], 0
0x1800765c2  mov     r14, rdx
0x1800765c5  mov     [rsp+68h+var_40], rax
0x1800765ca  xorps   xmm0, xmm0
0x1800765cd  mov     [rsp+68h+var_48], 10h
0x1800765d5  lea     r9, [rsp+68h+var_38]
0x1800765da  mov     [rsp+68h+arg_8], 0
0x1800765e2  mov     r8d, 1
0x1800765e8  lea     rdx, qword_180030DA8
0x1800765ef  mov     rsi, rcx
0x1800765f2  movups  [rsp+68h+var_38], xmm0
0x1800765f7  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800765fe  nop     dword ptr [rax+rax+00h]
0x180076603  mov     ebx, eax
0x180076605  cmp     eax, 0C0000023h
0x18007660a  jz      short loc_18007661E
0x18007660c  cmp     eax, 0C0000225h
0x180076611  jnz     loc_1800766EC
0x180076617  xor     ebx, ebx
0x180076619  jmp     loc_1800766EC
0x18007661e  mov     edx, [rsp+68h+arg_8]
0x180076622  mov     ecx, 102h
0x180076627  mov     r8d, 63734943h
0x18007662d  call    cs:__imp_ExAllocatePool2
0x180076634  nop     dword ptr [rax+rax+00h]
0x180076639  mov     rdi, rax
0x18007663c  test    rax, rax
0x18007663f  jnz     short loc_18007664B
0x180076641  mov     ebx, 0C0000017h
0x180076646  jmp     loc_1800766EC
0x18007664b  lea     rax, [rsp+68h+arg_8]
0x180076650  mov     r9, rdi
0x180076653  mov     [rsp+68h+var_40], rax
0x180076658  lea     rdx, qword_180030DA8
0x18007665f  mov     eax, [rsp+68h+arg_8]
0x180076663  mov     r8d, 1
0x180076669  mov     rcx, rsi
0x18007666c  mov     [rsp+68h+var_48], eax
0x180076670  call    cs:__imp_SeQuerySecurityAttributesToken
0x180076677  nop     dword ptr [rax+rax+00h]
0x18007667c  mov     ebx, eax
0x18007667e  test    eax, eax
0x180076680  js      short loc_1800766D8
0x180076682  cmp     dword ptr [rdi+4], 0
0x180076686  jz      short loc_1800766D8
0x180076688  mov     rsi, [rdi+8]
0x18007668c  cmp     dword ptr [rsi+18h], 0
0x180076690  jbe     short loc_1800766D8
0x180076692  cmp     word ptr [rsi+10h], 3
0x180076697  jnz     short loc_1800766D8
0x180076699  mov     r8b, 1; CaseInSensitive
0x18007669c  lea     rdx, stru_180030DB8; String2
0x1800766a3  mov     rcx, rsi; String1
0x1800766a6  call    cs:__imp_RtlEqualUnicodeString
0x1800766ad  nop     dword ptr [rax+rax+00h]
0x1800766b2  test    al, al
0x1800766b4  jz      short loc_1800766D8
0x1800766b6  mov     rcx, [rsi+20h]; String1
0x1800766ba  lea     rdx, stru_180030DC8; String2
0x1800766c1  mov     r8b, 1; CaseInSensitive
0x1800766c4  call    cs:__imp_RtlEqualUnicodeString
0x1800766cb  nop     dword ptr [rax+rax+00h]
0x1800766d0  test    al, al
0x1800766d2  jz      short loc_1800766D8
0x1800766d4  mov     byte ptr [r14], 1
0x1800766d8  mov     edx, 63734943h; Tag
0x1800766dd  mov     rcx, rdi; P
0x1800766e0  call    cs:__imp_ExFreePoolWithTag
0x1800766e7  nop     dword ptr [rax+rax+00h]
0x1800766ec  mov     eax, ebx
0x1800766ee  add     rsp, 48h
0x1800766f2  pop     r14
0x1800766f4  pop     rdi
0x1800766f5  pop     rsi
0x1800766f6  pop     rbx
0x1800766f7  retn
```
