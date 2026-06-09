# MupiUncHardeningRegistryParserCallback

- ea: `0x140015e60`
- end: `0x140016045`
- name: `MupiUncHardeningRegistryParserCallback`
- size: `485`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004304`
- `0x1400043ec`
- `0x140015e60`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140015e8b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f0b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f3e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015e8b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f0b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f3e`

## pseudocode

```c
__int64 __fastcall MupiUncHardeningRegistryParserCallback(
        PCUNICODE_STRING String1,
        int a2,
        unsigned __int16 **a3,
        __int64 a4)
{
  _DWORD *v4; // rbp
  int v7; // edi
  int v10; // ecx
  int v11; // ecx

  v4 = *(_DWORD **)(a4 + 24);
  v7 = 1;
  if ( RtlEqualUnicodeString(String1, &MupiUncHardeningProperty_RequireMutualAuthentication, 1u) )
  {
    if ( a2 )
    {
LABEL_3:
      if ( a2 == 1 && (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
      {
        v10 = **a3;
        LOWORD(v10) = (unsigned __int16)v10 >> 1;
        McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer(
          v10,
          (unsigned int)UncHardening_UnsupportedPropertyValue_StrValue_ExpectBoolValue,
          *(_DWORD *)(a4 + 16) >> 1,
          **(_WORD **)a4 >> 1,
          *(_QWORD *)(*(_QWORD *)a4 + 8LL),
          *(_DWORD *)(a4 + 16) >> 1,
          *(_QWORD *)(a4 + 8),
          String1->Length >> 1,
          (__int64)String1->Buffer,
          v10,
          *((_QWORD *)*a3 + 1));
      }
      return 0;
    }
    if ( (__int64)*a3 <= 0 )
      v7 = -1;
    v4[20] = v7;
  }
  else if ( RtlEqualUnicodeString(String1, &MupiUncHardeningProperty_RequireIntegrity, 1u) )
  {
    if ( a2 )
      goto LABEL_3;
    if ( (__int64)*a3 <= 0 )
      v7 = -1;
    v4[21] = v7;
  }
  else if ( RtlEqualUnicodeString(String1, &MupiUncHardeningProperty_RequirePrivacy, 1u) )
  {
    if ( a2 )
      goto LABEL_3;
    if ( (__int64)*a3 <= 0 )
      v7 = -1;
    v4[22] = v7;
  }
  else if ( a2 )
  {
    if ( a2 == 1 && (Microsoft_Windows_NetworkProviderEnableBits & 2) != 0 )
    {
      v11 = **a3;
      LOWORD(v11) = (unsigned __int16)v11 >> 1;
      McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer(
        v11,
        (unsigned int)UncHardening_UnsupportedProperty_StrValue,
        *(_DWORD *)(a4 + 16) >> 1,
        **(_WORD **)a4 >> 1,
        *(_QWORD *)(*(_QWORD *)a4 + 8LL),
        *(_DWORD *)(a4 + 16) >> 1,
        *(_QWORD *)(a4 + 8),
        String1->Length >> 1,
        (__int64)String1->Buffer,
        v11,
        *((_QWORD *)*a3 + 1));
    }
  }
  else if ( (Microsoft_Windows_NetworkProviderEnableBits & 2) != 0 )
  {
    McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer(
      String1->Length >> 1,
      *(_DWORD *)(a4 + 16) >> 1,
      *(_QWORD *)a4,
      **(_WORD **)a4 >> 1,
      *(_QWORD *)(*(_QWORD *)a4 + 8LL),
      *(_DWORD *)(a4 + 16) >> 1,
      *(_QWORD *)(a4 + 8),
      String1->Length >> 1,
      (__int64)String1->Buffer,
      (char)*a3);
  }
  return 0;
}

```

## disassembly

```asm
0x140015e60  push    rbx
0x140015e62  push    rbp
0x140015e63  push    rsi
0x140015e64  push    rdi
0x140015e65  push    r14
0x140015e67  push    r15
0x140015e69  sub     rsp, 68h
0x140015e6d  mov     rbp, [r9+18h]
0x140015e71  mov     r15, r8
0x140015e74  mov     ebx, edx
0x140015e76  mov     edi, 1
0x140015e7b  mov     r8b, dil; CaseInSensitive
0x140015e7e  lea     rdx, MupiUncHardeningProperty_RequireMutualAuthentication; String2
0x140015e85  mov     rsi, r9
0x140015e88  mov     r14, rcx
0x140015e8b  call    cs:__imp_RtlEqualUnicodeString
0x140015e92  nop     dword ptr [rax+rax+00h]
0x140015e97  test    al, al
0x140015e99  jz      short loc_140015EFE
0x140015e9b  test    ebx, ebx
0x140015e9d  jz      short loc_140015EEC
0x140015e9f  cmp     ebx, edi
0x140015ea1  jnz     loc_140016035
0x140015ea7  test    cs:Microsoft_Windows_NetworkProviderEnableBits, dil
0x140015eae  jz      loc_140016035
0x140015eb4  mov     rax, [r15]
0x140015eb7  movzx   edx, word ptr [r14]
0x140015ebb  movzx   ecx, word ptr [rax]
0x140015ebe  mov     rax, [rax+8]
0x140015ec2  mov     [rsp+98h+var_48], rax
0x140015ec7  mov     rax, [r14+8]
0x140015ecb  shr     cx, 1
0x140015ece  shr     dx, 1
0x140015ed1  mov     word ptr [rsp+98h+var_50], cx
0x140015ed6  mov     [rsp+98h+var_58], rax
0x140015edb  mov     [rsp+98h+var_60], dx
0x140015ee0  lea     rdx, UncHardening_UnsupportedPropertyValue_StrValue_ExpectBoolValue
0x140015ee7  jmp     loc_140015FB4
0x140015eec  or      eax, 0FFFFFFFFh
0x140015eef  cmp     qword ptr [r15], 0
0x140015ef3  cmovle  edi, eax
0x140015ef6  mov     [rbp+50h], edi
0x140015ef9  jmp     loc_140016035
0x140015efe  mov     r8b, dil; CaseInSensitive
0x140015f01  lea     rdx, MupiUncHardeningProperty_RequireIntegrity; String2
0x140015f08  mov     rcx, r14; String1
0x140015f0b  call    cs:__imp_RtlEqualUnicodeString
0x140015f12  nop     dword ptr [rax+rax+00h]
0x140015f17  test    al, al
0x140015f19  jz      short loc_140015F31
0x140015f1b  test    ebx, ebx
0x140015f1d  jnz     short loc_140015E9F
0x140015f1f  or      eax, 0FFFFFFFFh
0x140015f22  cmp     qword ptr [r15], 0
0x140015f26  cmovle  edi, eax
0x140015f29  mov     [rbp+54h], edi
0x140015f2c  jmp     loc_140016035
0x140015f31  mov     r8b, dil; CaseInSensitive
0x140015f34  lea     rdx, MupiUncHardeningProperty_RequirePrivacy; String2
0x140015f3b  mov     rcx, r14; String1
0x140015f3e  call    cs:__imp_RtlEqualUnicodeString
0x140015f45  nop     dword ptr [rax+rax+00h]
0x140015f4a  test    al, al
0x140015f4c  jz      short loc_140015F68
0x140015f4e  test    ebx, ebx
0x140015f50  jnz     loc_140015E9F
0x140015f56  or      eax, 0FFFFFFFFh
0x140015f59  cmp     qword ptr [r15], 0
0x140015f5d  cmovle  edi, eax
0x140015f60  mov     [rbp+58h], edi
0x140015f63  jmp     loc_140016035
0x140015f68  test    ebx, ebx
0x140015f6a  jz      short loc_140015FE4
0x140015f6c  cmp     ebx, edi
0x140015f6e  jnz     loc_140016035
0x140015f74  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x140015f7b  jz      loc_140016035
0x140015f81  mov     rax, [r15]
0x140015f84  movzx   edx, word ptr [r14]
0x140015f88  movzx   ecx, word ptr [rax]
0x140015f8b  mov     rax, [rax+8]
0x140015f8f  mov     [rsp+98h+var_48], rax
0x140015f94  mov     rax, [r14+8]
0x140015f98  shr     cx, 1
0x140015f9b  shr     dx, 1
0x140015f9e  mov     word ptr [rsp+98h+var_50], cx
0x140015fa3  mov     [rsp+98h+var_58], rax
0x140015fa8  mov     [rsp+98h+var_60], dx
0x140015fad  lea     rdx, UncHardening_UnsupportedProperty_StrValue
0x140015fb4  mov     r10, [rsi]
0x140015fb7  mov     rax, [rsi+8]
0x140015fbb  mov     r8d, [rsi+10h]
0x140015fbf  mov     [rsp+98h+var_68], rax
0x140015fc4  movzx   r9d, word ptr [r10]
0x140015fc8  mov     rax, [r10+8]
0x140015fcc  shr     r8d, 1
0x140015fcf  mov     [rsp+98h+var_70], r8d
0x140015fd4  shr     r9w, 1
0x140015fd8  mov     [rsp+98h+var_78], rax
0x140015fdd  call    McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer
0x140015fe2  jmp     short loc_140016035
0x140015fe4  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x140015feb  jz      short loc_140016035
0x140015fed  mov     rax, [r15]
0x140015ff0  mov     r8, [rsi]
0x140015ff3  movzx   ecx, word ptr [r14]
0x140015ff7  mov     edx, [rsi+10h]
0x140015ffa  mov     [rsp+98h+var_50], rax
0x140015fff  mov     rax, [r14+8]
0x140016003  movzx   r9d, word ptr [r8]
0x140016007  mov     [rsp+98h+var_58], rax
0x14001600c  mov     rax, [rsi+8]
0x140016010  shr     cx, 1
0x140016013  mov     [rsp+98h+var_60], cx
0x140016018  mov     [rsp+98h+var_68], rax
0x14001601d  mov     rax, [r8+8]
0x140016021  shr     edx, 1
0x140016023  mov     [rsp+98h+var_70], edx
0x140016027  shr     r9w, 1
0x14001602b  mov     [rsp+98h+var_78], rax
0x140016030  call    McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer
0x140016035  xor     eax, eax
0x140016037  add     rsp, 68h
0x14001603b  pop     r15
0x14001603d  pop     r14
0x14001603f  pop     rdi
0x140016040  pop     rsi
0x140016041  pop     rbp
0x140016042  pop     rbx
0x140016043  retn
```
