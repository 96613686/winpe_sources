# LookupDnsSiteEntry

- ea: `0x140088b00`
- end: `0x140088dcf`
- name: `LookupDnsSiteEntry`
- size: `719`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140088dd8`

## callees

- `0x140010f94`
- `0x140039fa8`
- `0x140087f0c`
- `0x140088950`
- `0x140088b00`
- `0x14008a73c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140088cfb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140088cfb`
- `ntoskrnl!ExAllocatePool2` at `0x140088b95`
- `ntoskrnl!ExAllocatePool2` at `0x140088b95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088da8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088da8`
- `ntoskrnl!ZwEnumerateKey` at `0x140088b61`
- `ntoskrnl!ZwEnumerateKey` at `0x140088bc9`
- `ntoskrnl!ZwEnumerateKey` at `0x140088b61`
- `ntoskrnl!ZwEnumerateKey` at `0x140088bc9`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140088cba`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140088cba`

## pseudocode

```c
__int64 __fastcall LookupDnsSiteEntry(PCUNICODE_STRING String1, HANDLE KeyHandle, __int64 a3, int *a4)
{
  __int64 v5; // rbx
  ULONG v8; // r14d
  NTSTATUS v9; // eax
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  _WORD *v12; // rdx
  __int16 v13; // r8
  __int16 v14; // r9
  bool v15; // zf
  int v16; // esi
  BOOLEAN v17; // bl
  LONG v18; // ebx
  int v20; // [rsp+30h] [rbp-40h] BYREF
  __int128 v21; // [rsp+38h] [rbp-38h] BYREF
  _WORD v22[2]; // [rsp+48h] [rbp-28h] BYREF
  int v23; // [rsp+4Ch] [rbp-24h]
  _WORD *v24; // [rsp+50h] [rbp-20h]
  UNICODE_STRING String1a; // [rsp+58h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+C8h] [rbp+58h] BYREF

  v5 = a3;
  v8 = 0;
  v20 = 3;
  *a4 = 3;
  while ( 1 )
  {
    ResultLength = 0;
    v21 = 0;
    v9 = ZwEnumerateKey(KeyHandle, v8, KeyBasicInformation, 0, 0, &ResultLength);
    if ( v9 >= 0 || v9 != -1073741789 && v9 != -2147483643 )
    {
      v11 = 0;
LABEL_28:
      v16 = -1073741772;
      if ( !v11 )
        return (unsigned int)v16;
LABEL_29:
      ExFreePoolWithTag(v11, 0x7A4D6D53u);
      return (unsigned int)v16;
    }
    Pool2 = (_DWORD *)ExAllocatePool2(258, ResultLength, 2051894611);
    v11 = Pool2;
    if ( !Pool2 )
      break;
    if ( ZwEnumerateKey(KeyHandle, v8, KeyBasicInformation, Pool2, ResultLength, &ResultLength) < 0 )
      goto LABEL_28;
    if ( v11[3] < 2u )
    {
      ExFreePoolWithTag(v11, 0x7A4D6D53u);
      goto LABEL_21;
    }
    v12 = v11 + 4;
    *((_QWORD *)&v21 + 1) = v11 + 4;
    v13 = *((_WORD *)v11 + 6);
    LOWORD(v21) = v13;
    v14 = *((_WORD *)v11 + 6);
    WORD1(v21) = v14;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids, &v21);
      v12 = (_WORD *)*((_QWORD *)&v21 + 1);
      v14 = WORD1(v21);
      v13 = v21;
    }
    v15 = *v12 == 42;
    String1a = 0;
    if ( v15 )
    {
      v23 = 0;
      v22[0] = v13 - 2;
      v24 = v12 + 1;
      v22[1] = v14;
      v16 = BuildFullyQualifiedDomainName(v22, v5, &String1a);
      if ( v16 < 0 )
        goto LABEL_29;
      v17 = RtlSuffixUnicodeString(&String1a, String1, 1u);
      FreeUnicodeString(&String1a);
      if ( v17 )
        goto LABEL_19;
    }
    else
    {
      v16 = BuildFullyQualifiedDomainName(&v21, v5, &String1a);
      if ( v16 < 0 )
        goto LABEL_29;
      v18 = RtlCompareUnicodeString(String1, &String1a, 1u);
      FreeUnicodeString(&String1a);
      if ( !v18 )
      {
LABEL_19:
        if ( (int)RegQueryZoneFromKey(KeyHandle, &v21, &v20) >= 0 )
        {
          *a4 = v20;
          goto LABEL_29;
        }
      }
    }
    ExFreePoolWithTag(v11, 0x7A4D6D53u);
    v5 = a3;
LABEL_21:
    ++v8;
  }
  v16 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140088b00  mov     [rsp-38h+arg_0], rbx
0x140088b05  mov     [rsp-38h+arg_10], r8
0x140088b0a  push    rbp
0x140088b0b  push    rsi
0x140088b0c  push    rdi
0x140088b0d  push    r12
0x140088b0f  push    r13
0x140088b11  push    r14
0x140088b13  push    r15
0x140088b15  mov     rbp, rsp
0x140088b18  sub     rsp, 70h
0x140088b1c  xor     esi, esi
0x140088b1e  mov     r12, r9
0x140088b21  mov     rbx, r8
0x140088b24  mov     r15, rdx
0x140088b27  mov     r13, rcx
0x140088b2a  xor     r14d, r14d
0x140088b2d  lea     eax, [rsi+3]
0x140088b30  mov     [rbp+var_40], eax
0x140088b33  mov     [r9], eax
0x140088b36  lea     rax, [rbp+arg_18]
0x140088b3a  mov     [rbp+arg_18], 0
0x140088b41  xorps   xmm0, xmm0
0x140088b44  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140088b49  xor     r9d, r9d; KeyInformation
0x140088b4c  mov     [rsp+70h+Length], 0; Length
0x140088b54  xor     r8d, r8d; KeyInformationClass
0x140088b57  mov     edx, r14d; Index
0x140088b5a  mov     rcx, r15; KeyHandle
0x140088b5d  movups  [rbp+var_38], xmm0
0x140088b61  call    cs:__imp_ZwEnumerateKey
0x140088b68  nop     dword ptr [rax+rax+00h]
0x140088b6d  test    eax, eax
0x140088b6f  jns     loc_140088D8F
0x140088b75  cmp     eax, 0C0000023h
0x140088b7a  jz      short loc_140088B87
0x140088b7c  cmp     eax, 80000005h
0x140088b81  jnz     loc_140088D8F
0x140088b87  mov     edx, [rbp+arg_18]
0x140088b8a  mov     ecx, 102h
0x140088b8f  mov     r8d, 7A4D6D53h
0x140088b95  call    cs:__imp_ExAllocatePool2
0x140088b9c  nop     dword ptr [rax+rax+00h]
0x140088ba1  mov     rdi, rax
0x140088ba4  test    rax, rax
0x140088ba7  jz      loc_140088D53
0x140088bad  lea     rax, [rbp+arg_18]
0x140088bb1  mov     r9, rdi; KeyInformation
0x140088bb4  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140088bb9  xor     r8d, r8d; KeyInformationClass
0x140088bbc  mov     eax, [rbp+arg_18]
0x140088bbf  mov     edx, r14d; Index
0x140088bc2  mov     rcx, r15; KeyHandle
0x140088bc5  mov     [rsp+70h+Length], eax; Length
0x140088bc9  call    cs:__imp_ZwEnumerateKey
0x140088bd0  nop     dword ptr [rax+rax+00h]
0x140088bd5  test    eax, eax
0x140088bd7  js      loc_140088D91
0x140088bdd  mov     r10d, 2
0x140088be3  cmp     [rdi+0Ch], r10d
0x140088be7  jnb     short loc_140088C02
0x140088be9  mov     edx, 7A4D6D53h; Tag
0x140088bee  mov     rcx, rdi; P
0x140088bf1  call    cs:__imp_ExFreePoolWithTag
0x140088bf8  nop     dword ptr [rax+rax+00h]
0x140088bfd  jmp     loc_140088D42
0x140088c02  lea     rdx, [rdi+10h]
0x140088c06  mov     qword ptr [rbp+var_38+8], rdx
0x140088c0a  movzx   r8d, word ptr [rdi+0Ch]
0x140088c0f  mov     word ptr [rbp+var_38], r8w
0x140088c14  movzx   r9d, word ptr [rdi+0Ch]
0x140088c19  mov     word ptr [rbp+var_38+2], r9w
0x140088c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140088c25  lea     rax, WPP_GLOBAL_Control
0x140088c2c  cmp     rcx, rax
0x140088c2f  jz      short loc_140088C6C
0x140088c31  mov     eax, [rcx+2Ch]
0x140088c34  test    r10b, al
0x140088c37  jz      short loc_140088C6C
0x140088c39  cmp     [rcx+29h], r10b
0x140088c3d  jb      short loc_140088C6C
0x140088c3f  mov     rcx, [rcx+18h]
0x140088c43  lea     r9, [rbp+var_38]
0x140088c47  mov     edx, 26h ; '&'
0x140088c4c  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140088c53  call    WPP_SF_Z
0x140088c58  mov     rdx, qword ptr [rbp+var_38+8]
0x140088c5c  mov     r10d, 2
0x140088c62  movzx   r9d, word ptr [rbp+var_38+2]
0x140088c67  movzx   r8d, word ptr [rbp+var_38]
0x140088c6c  cmp     word ptr [rdx], 2Ah ; '*'
0x140088c70  xorps   xmm0, xmm0
0x140088c73  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140088c77  jnz     short loc_140088CD7
0x140088c79  sub     r8w, r10w
0x140088c7d  mov     [rbp+var_24], 0
0x140088c84  lea     rax, [rdx+2]
0x140088c88  mov     [rbp+var_28], r8w
0x140088c8d  lea     r8, [rbp+String1]
0x140088c91  mov     [rbp+var_20], rax
0x140088c95  mov     rdx, rbx
0x140088c98  mov     [rbp+var_26], r9w
0x140088c9d  lea     rcx, [rbp+var_28]
0x140088ca1  call    BuildFullyQualifiedDomainName
0x140088ca6  mov     esi, eax
0x140088ca8  test    eax, eax
0x140088caa  js      loc_140088DA0
0x140088cb0  mov     r8b, 1; CaseInSensitive
0x140088cb3  lea     rcx, [rbp+String1]; String1
0x140088cb7  mov     rdx, r13; String2
0x140088cba  call    cs:__imp_RtlSuffixUnicodeString
0x140088cc1  nop     dword ptr [rax+rax+00h]
0x140088cc6  lea     rcx, [rbp+String1]
0x140088cca  mov     bl, al
0x140088ccc  call    FreeUnicodeString
0x140088cd1  test    bl, bl
0x140088cd3  jz      short loc_140088D2A
0x140088cd5  jmp     short loc_140088D16
0x140088cd7  lea     r8, [rbp+String1]
0x140088cdb  mov     rdx, rbx
0x140088cde  lea     rcx, [rbp+var_38]
0x140088ce2  call    BuildFullyQualifiedDomainName
0x140088ce7  mov     esi, eax
0x140088ce9  test    eax, eax
0x140088ceb  js      loc_140088DA0
0x140088cf1  mov     r8b, 1; CaseInSensitive
0x140088cf4  lea     rdx, [rbp+String1]; String2
0x140088cf8  mov     rcx, r13; String1
0x140088cfb  call    cs:__imp_RtlCompareUnicodeString
0x140088d02  nop     dword ptr [rax+rax+00h]
0x140088d07  lea     rcx, [rbp+String1]
0x140088d0b  mov     ebx, eax
0x140088d0d  call    FreeUnicodeString
0x140088d12  test    ebx, ebx
0x140088d14  jnz     short loc_140088D2A
0x140088d16  lea     r8, [rbp+var_40]
0x140088d1a  mov     rcx, r15
0x140088d1d  lea     rdx, [rbp+var_38]
0x140088d21  call    RegQueryZoneFromKey
0x140088d26  test    eax, eax
0x140088d28  jns     short loc_140088D4A
0x140088d2a  mov     edx, 7A4D6D53h; Tag
0x140088d2f  mov     rcx, rdi; P
0x140088d32  call    cs:__imp_ExFreePoolWithTag
0x140088d39  nop     dword ptr [rax+rax+00h]
0x140088d3e  mov     rbx, [rbp+arg_10]
0x140088d42  inc     r14d
0x140088d45  jmp     loc_140088B36
0x140088d4a  mov     eax, [rbp+var_40]
0x140088d4d  mov     [r12], eax
0x140088d51  jmp     short loc_140088DA0
0x140088d53  mov     esi, 0C000009Ah
0x140088d58  mov     rcx, cs:WPP_GLOBAL_Control
0x140088d5f  lea     rax, WPP_GLOBAL_Control
0x140088d66  cmp     rcx, rax
0x140088d69  jz      short loc_140088DB4
0x140088d6b  mov     eax, [rcx+2Ch]
0x140088d6e  test    al, 1
0x140088d70  jz      short loc_140088DB4
0x140088d72  cmp     byte ptr [rcx+29h], 1
0x140088d76  jb      short loc_140088DB4
0x140088d78  mov     rcx, [rcx+18h]
0x140088d7c  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140088d83  mov     edx, 25h ; '%'
0x140088d88  call    WPP_SF_
0x140088d8d  jmp     short loc_140088DB4
0x140088d8f  xor     edi, edi
0x140088d91  test    esi, esi
0x140088d93  mov     eax, 0C0000034h
0x140088d98  cmovns  esi, eax
0x140088d9b  test    rdi, rdi
0x140088d9e  jz      short loc_140088DB4
0x140088da0  mov     edx, 7A4D6D53h; Tag
0x140088da5  mov     rcx, rdi; P
0x140088da8  call    cs:__imp_ExFreePoolWithTag
0x140088daf  nop     dword ptr [rax+rax+00h]
0x140088db4  mov     rbx, [rsp+70h+arg_0]
0x140088dbc  mov     eax, esi
0x140088dbe  add     rsp, 70h
0x140088dc2  pop     r15
0x140088dc4  pop     r14
0x140088dc6  pop     r13
0x140088dc8  pop     r12
0x140088dca  pop     rdi
0x140088dcb  pop     rsi
0x140088dcc  pop     rbp
0x140088dcd  retn
```
