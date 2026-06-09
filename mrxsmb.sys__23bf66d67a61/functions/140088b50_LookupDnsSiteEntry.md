# LookupDnsSiteEntry

- ea: `0x140088b50`
- end: `0x140088e1f`
- name: `LookupDnsSiteEntry`
- size: `719`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140088e28`

## callees

- `0x140010f94`
- `0x140039fa8`
- `0x140087f5c`
- `0x1400889a0`
- `0x140088b50`
- `0x14008a78c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140088d4b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140088d4b`
- `ntoskrnl!ExAllocatePool2` at `0x140088be5`
- `ntoskrnl!ExAllocatePool2` at `0x140088be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088df8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088df8`
- `ntoskrnl!ZwEnumerateKey` at `0x140088bb1`
- `ntoskrnl!ZwEnumerateKey` at `0x140088c19`
- `ntoskrnl!ZwEnumerateKey` at `0x140088bb1`
- `ntoskrnl!ZwEnumerateKey` at `0x140088c19`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140088d0a`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140088d0a`

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
0x140088b50  mov     [rsp-38h+arg_0], rbx
0x140088b55  mov     [rsp-38h+arg_10], r8
0x140088b5a  push    rbp
0x140088b5b  push    rsi
0x140088b5c  push    rdi
0x140088b5d  push    r12
0x140088b5f  push    r13
0x140088b61  push    r14
0x140088b63  push    r15
0x140088b65  mov     rbp, rsp
0x140088b68  sub     rsp, 70h
0x140088b6c  xor     esi, esi
0x140088b6e  mov     r12, r9
0x140088b71  mov     rbx, r8
0x140088b74  mov     r15, rdx
0x140088b77  mov     r13, rcx
0x140088b7a  xor     r14d, r14d
0x140088b7d  lea     eax, [rsi+3]
0x140088b80  mov     [rbp+var_40], eax
0x140088b83  mov     [r9], eax
0x140088b86  lea     rax, [rbp+arg_18]
0x140088b8a  mov     [rbp+arg_18], 0
0x140088b91  xorps   xmm0, xmm0
0x140088b94  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140088b99  xor     r9d, r9d; KeyInformation
0x140088b9c  mov     [rsp+70h+Length], 0; Length
0x140088ba4  xor     r8d, r8d; KeyInformationClass
0x140088ba7  mov     edx, r14d; Index
0x140088baa  mov     rcx, r15; KeyHandle
0x140088bad  movups  [rbp+var_38], xmm0
0x140088bb1  call    cs:__imp_ZwEnumerateKey
0x140088bb8  nop     dword ptr [rax+rax+00h]
0x140088bbd  test    eax, eax
0x140088bbf  jns     loc_140088DDF
0x140088bc5  cmp     eax, 0C0000023h
0x140088bca  jz      short loc_140088BD7
0x140088bcc  cmp     eax, 80000005h
0x140088bd1  jnz     loc_140088DDF
0x140088bd7  mov     edx, [rbp+arg_18]
0x140088bda  mov     ecx, 102h
0x140088bdf  mov     r8d, 7A4D6D53h
0x140088be5  call    cs:__imp_ExAllocatePool2
0x140088bec  nop     dword ptr [rax+rax+00h]
0x140088bf1  mov     rdi, rax
0x140088bf4  test    rax, rax
0x140088bf7  jz      loc_140088DA3
0x140088bfd  lea     rax, [rbp+arg_18]
0x140088c01  mov     r9, rdi; KeyInformation
0x140088c04  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140088c09  xor     r8d, r8d; KeyInformationClass
0x140088c0c  mov     eax, [rbp+arg_18]
0x140088c0f  mov     edx, r14d; Index
0x140088c12  mov     rcx, r15; KeyHandle
0x140088c15  mov     [rsp+70h+Length], eax; Length
0x140088c19  call    cs:__imp_ZwEnumerateKey
0x140088c20  nop     dword ptr [rax+rax+00h]
0x140088c25  test    eax, eax
0x140088c27  js      loc_140088DE1
0x140088c2d  mov     r10d, 2
0x140088c33  cmp     [rdi+0Ch], r10d
0x140088c37  jnb     short loc_140088C52
0x140088c39  mov     edx, 7A4D6D53h; Tag
0x140088c3e  mov     rcx, rdi; P
0x140088c41  call    cs:__imp_ExFreePoolWithTag
0x140088c48  nop     dword ptr [rax+rax+00h]
0x140088c4d  jmp     loc_140088D92
0x140088c52  lea     rdx, [rdi+10h]
0x140088c56  mov     qword ptr [rbp+var_38+8], rdx
0x140088c5a  movzx   r8d, word ptr [rdi+0Ch]
0x140088c5f  mov     word ptr [rbp+var_38], r8w
0x140088c64  movzx   r9d, word ptr [rdi+0Ch]
0x140088c69  mov     word ptr [rbp+var_38+2], r9w
0x140088c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140088c75  lea     rax, WPP_GLOBAL_Control
0x140088c7c  cmp     rcx, rax
0x140088c7f  jz      short loc_140088CBC
0x140088c81  mov     eax, [rcx+2Ch]
0x140088c84  test    r10b, al
0x140088c87  jz      short loc_140088CBC
0x140088c89  cmp     [rcx+29h], r10b
0x140088c8d  jb      short loc_140088CBC
0x140088c8f  mov     rcx, [rcx+18h]
0x140088c93  lea     r9, [rbp+var_38]
0x140088c97  mov     edx, 26h ; '&'
0x140088c9c  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140088ca3  call    WPP_SF_Z
0x140088ca8  mov     rdx, qword ptr [rbp+var_38+8]
0x140088cac  mov     r10d, 2
0x140088cb2  movzx   r9d, word ptr [rbp+var_38+2]
0x140088cb7  movzx   r8d, word ptr [rbp+var_38]
0x140088cbc  cmp     word ptr [rdx], 2Ah ; '*'
0x140088cc0  xorps   xmm0, xmm0
0x140088cc3  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140088cc7  jnz     short loc_140088D27
0x140088cc9  sub     r8w, r10w
0x140088ccd  mov     [rbp+var_24], 0
0x140088cd4  lea     rax, [rdx+2]
0x140088cd8  mov     [rbp+var_28], r8w
0x140088cdd  lea     r8, [rbp+String1]
0x140088ce1  mov     [rbp+var_20], rax
0x140088ce5  mov     rdx, rbx
0x140088ce8  mov     [rbp+var_26], r9w
0x140088ced  lea     rcx, [rbp+var_28]
0x140088cf1  call    BuildFullyQualifiedDomainName
0x140088cf6  mov     esi, eax
0x140088cf8  test    eax, eax
0x140088cfa  js      loc_140088DF0
0x140088d00  mov     r8b, 1; CaseInSensitive
0x140088d03  lea     rcx, [rbp+String1]; String1
0x140088d07  mov     rdx, r13; String2
0x140088d0a  call    cs:__imp_RtlSuffixUnicodeString
0x140088d11  nop     dword ptr [rax+rax+00h]
0x140088d16  lea     rcx, [rbp+String1]
0x140088d1a  mov     bl, al
0x140088d1c  call    FreeUnicodeString
0x140088d21  test    bl, bl
0x140088d23  jz      short loc_140088D7A
0x140088d25  jmp     short loc_140088D66
0x140088d27  lea     r8, [rbp+String1]
0x140088d2b  mov     rdx, rbx
0x140088d2e  lea     rcx, [rbp+var_38]
0x140088d32  call    BuildFullyQualifiedDomainName
0x140088d37  mov     esi, eax
0x140088d39  test    eax, eax
0x140088d3b  js      loc_140088DF0
0x140088d41  mov     r8b, 1; CaseInSensitive
0x140088d44  lea     rdx, [rbp+String1]; String2
0x140088d48  mov     rcx, r13; String1
0x140088d4b  call    cs:__imp_RtlCompareUnicodeString
0x140088d52  nop     dword ptr [rax+rax+00h]
0x140088d57  lea     rcx, [rbp+String1]
0x140088d5b  mov     ebx, eax
0x140088d5d  call    FreeUnicodeString
0x140088d62  test    ebx, ebx
0x140088d64  jnz     short loc_140088D7A
0x140088d66  lea     r8, [rbp+var_40]
0x140088d6a  mov     rcx, r15
0x140088d6d  lea     rdx, [rbp+var_38]
0x140088d71  call    RegQueryZoneFromKey
0x140088d76  test    eax, eax
0x140088d78  jns     short loc_140088D9A
0x140088d7a  mov     edx, 7A4D6D53h; Tag
0x140088d7f  mov     rcx, rdi; P
0x140088d82  call    cs:__imp_ExFreePoolWithTag
0x140088d89  nop     dword ptr [rax+rax+00h]
0x140088d8e  mov     rbx, [rbp+arg_10]
0x140088d92  inc     r14d
0x140088d95  jmp     loc_140088B86
0x140088d9a  mov     eax, [rbp+var_40]
0x140088d9d  mov     [r12], eax
0x140088da1  jmp     short loc_140088DF0
0x140088da3  mov     esi, 0C000009Ah
0x140088da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140088daf  lea     rax, WPP_GLOBAL_Control
0x140088db6  cmp     rcx, rax
0x140088db9  jz      short loc_140088E04
0x140088dbb  mov     eax, [rcx+2Ch]
0x140088dbe  test    al, 1
0x140088dc0  jz      short loc_140088E04
0x140088dc2  cmp     byte ptr [rcx+29h], 1
0x140088dc6  jb      short loc_140088E04
0x140088dc8  mov     rcx, [rcx+18h]
0x140088dcc  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140088dd3  mov     edx, 25h ; '%'
0x140088dd8  call    WPP_SF_
0x140088ddd  jmp     short loc_140088E04
0x140088ddf  xor     edi, edi
0x140088de1  test    esi, esi
0x140088de3  mov     eax, 0C0000034h
0x140088de8  cmovns  esi, eax
0x140088deb  test    rdi, rdi
0x140088dee  jz      short loc_140088E04
0x140088df0  mov     edx, 7A4D6D53h; Tag
0x140088df5  mov     rcx, rdi; P
0x140088df8  call    cs:__imp_ExFreePoolWithTag
0x140088dff  nop     dword ptr [rax+rax+00h]
0x140088e04  mov     rbx, [rsp+70h+arg_0]
0x140088e0c  mov     eax, esi
0x140088e0e  add     rsp, 70h
0x140088e12  pop     r15
0x140088e14  pop     r14
0x140088e16  pop     r13
0x140088e18  pop     r12
0x140088e1a  pop     rdi
0x140088e1b  pop     rsi
0x140088e1c  pop     rbp
0x140088e1d  retn
```
