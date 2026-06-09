# MupiUncHardeningRegistryParserCallback

- ea: `0x140015eb0`
- end: `0x140016095`
- name: `MupiUncHardeningRegistryParserCallback`
- size: `485`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, int, unsigned __int16 **, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004304`
- `0x1400043ec`
- `0x140015eb0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140015edb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f5b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f8e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015edb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f5b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015f8e`

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
0x140015eb0  push    rbx
0x140015eb2  push    rbp
0x140015eb3  push    rsi
0x140015eb4  push    rdi
0x140015eb5  push    r14
0x140015eb7  push    r15
0x140015eb9  sub     rsp, 68h
0x140015ebd  mov     rbp, [r9+18h]
0x140015ec1  mov     r15, r8
0x140015ec4  mov     ebx, edx
0x140015ec6  mov     edi, 1
0x140015ecb  mov     r8b, dil; CaseInSensitive
0x140015ece  lea     rdx, MupiUncHardeningProperty_RequireMutualAuthentication; String2
0x140015ed5  mov     rsi, r9
0x140015ed8  mov     r14, rcx
0x140015edb  call    cs:__imp_RtlEqualUnicodeString
0x140015ee2  nop     dword ptr [rax+rax+00h]
0x140015ee7  test    al, al
0x140015ee9  jz      short loc_140015F4E
0x140015eeb  test    ebx, ebx
0x140015eed  jz      short loc_140015F3C
0x140015eef  cmp     ebx, edi
0x140015ef1  jnz     loc_140016085
0x140015ef7  test    cs:Microsoft_Windows_NetworkProviderEnableBits, dil
0x140015efe  jz      loc_140016085
0x140015f04  mov     rax, [r15]
0x140015f07  movzx   edx, word ptr [r14]
0x140015f0b  movzx   ecx, word ptr [rax]
0x140015f0e  mov     rax, [rax+8]
0x140015f12  mov     [rsp+98h+var_48], rax
0x140015f17  mov     rax, [r14+8]
0x140015f1b  shr     cx, 1
0x140015f1e  shr     dx, 1
0x140015f21  mov     word ptr [rsp+98h+var_50], cx
0x140015f26  mov     [rsp+98h+var_58], rax
0x140015f2b  mov     [rsp+98h+var_60], dx
0x140015f30  lea     rdx, UncHardening_UnsupportedPropertyValue_StrValue_ExpectBoolValue
0x140015f37  jmp     loc_140016004
0x140015f3c  or      eax, 0FFFFFFFFh
0x140015f3f  cmp     qword ptr [r15], 0
0x140015f43  cmovle  edi, eax
0x140015f46  mov     [rbp+50h], edi
0x140015f49  jmp     loc_140016085
0x140015f4e  mov     r8b, dil; CaseInSensitive
0x140015f51  lea     rdx, MupiUncHardeningProperty_RequireIntegrity; String2
0x140015f58  mov     rcx, r14; String1
0x140015f5b  call    cs:__imp_RtlEqualUnicodeString
0x140015f62  nop     dword ptr [rax+rax+00h]
0x140015f67  test    al, al
0x140015f69  jz      short loc_140015F81
0x140015f6b  test    ebx, ebx
0x140015f6d  jnz     short loc_140015EEF
0x140015f6f  or      eax, 0FFFFFFFFh
0x140015f72  cmp     qword ptr [r15], 0
0x140015f76  cmovle  edi, eax
0x140015f79  mov     [rbp+54h], edi
0x140015f7c  jmp     loc_140016085
0x140015f81  mov     r8b, dil; CaseInSensitive
0x140015f84  lea     rdx, MupiUncHardeningProperty_RequirePrivacy; String2
0x140015f8b  mov     rcx, r14; String1
0x140015f8e  call    cs:__imp_RtlEqualUnicodeString
0x140015f95  nop     dword ptr [rax+rax+00h]
0x140015f9a  test    al, al
0x140015f9c  jz      short loc_140015FB8
0x140015f9e  test    ebx, ebx
0x140015fa0  jnz     loc_140015EEF
0x140015fa6  or      eax, 0FFFFFFFFh
0x140015fa9  cmp     qword ptr [r15], 0
0x140015fad  cmovle  edi, eax
0x140015fb0  mov     [rbp+58h], edi
0x140015fb3  jmp     loc_140016085
0x140015fb8  test    ebx, ebx
0x140015fba  jz      short loc_140016034
0x140015fbc  cmp     ebx, edi
0x140015fbe  jnz     loc_140016085
0x140015fc4  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x140015fcb  jz      loc_140016085
0x140015fd1  mov     rax, [r15]
0x140015fd4  movzx   edx, word ptr [r14]
0x140015fd8  movzx   ecx, word ptr [rax]
0x140015fdb  mov     rax, [rax+8]
0x140015fdf  mov     [rsp+98h+var_48], rax
0x140015fe4  mov     rax, [r14+8]
0x140015fe8  shr     cx, 1
0x140015feb  shr     dx, 1
0x140015fee  mov     word ptr [rsp+98h+var_50], cx
0x140015ff3  mov     [rsp+98h+var_58], rax
0x140015ff8  mov     [rsp+98h+var_60], dx
0x140015ffd  lea     rdx, UncHardening_UnsupportedProperty_StrValue
0x140016004  mov     r10, [rsi]
0x140016007  mov     rax, [rsi+8]
0x14001600b  mov     r8d, [rsi+10h]
0x14001600f  mov     [rsp+98h+var_68], rax
0x140016014  movzx   r9d, word ptr [r10]
0x140016018  mov     rax, [r10+8]
0x14001601c  shr     r8d, 1
0x14001601f  mov     [rsp+98h+var_70], r8d
0x140016024  shr     r9w, 1
0x140016028  mov     [rsp+98h+var_78], rax
0x14001602d  call    McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer
0x140016032  jmp     short loc_140016085
0x140016034  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x14001603b  jz      short loc_140016085
0x14001603d  mov     rax, [r15]
0x140016040  mov     r8, [rsi]
0x140016043  movzx   ecx, word ptr [r14]
0x140016047  mov     edx, [rsi+10h]
0x14001604a  mov     [rsp+98h+var_50], rax
0x14001604f  mov     rax, [r14+8]
0x140016053  movzx   r9d, word ptr [r8]
0x140016057  mov     [rsp+98h+var_58], rax
0x14001605c  mov     rax, [rsi+8]
0x140016060  shr     cx, 1
0x140016063  mov     [rsp+98h+var_60], cx
0x140016068  mov     [rsp+98h+var_68], rax
0x14001606d  mov     rax, [r8+8]
0x140016071  shr     edx, 1
0x140016073  mov     [rsp+98h+var_70], edx
0x140016077  shr     r9w, 1
0x14001607b  mov     [rsp+98h+var_78], rax
0x140016080  call    McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer
0x140016085  xor     eax, eax
0x140016087  add     rsp, 68h
0x14001608b  pop     r15
0x14001608d  pop     r14
0x14001608f  pop     rdi
0x140016090  pop     rsi
0x140016091  pop     rbp
0x140016092  pop     rbx
0x140016093  retn
```
