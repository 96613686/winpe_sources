# GenerateHmacShaHash

- ea: `0x140015a4c`
- end: `0x140015d69`
- name: `GenerateHmacShaHash`
- size: `797`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, PUCHAR, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400159a4`
- `0x1400159f8`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140015a4c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015bb9`
- `ntoskrnl!ExAllocatePool2` at `0x140015bb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d49`
- `ksecdd!BCryptGetProperty` at `0x140015a99`
- `ksecdd!BCryptGetProperty` at `0x140015b0c`
- `ksecdd!BCryptGetProperty` at `0x140015a99`
- `ksecdd!BCryptGetProperty` at `0x140015b0c`
- `ksecdd!BCryptCreateHash` at `0x140015c30`
- `ksecdd!BCryptCreateHash` at `0x140015c30`
- `ksecdd!BCryptHashData` at `0x140015c9b`
- `ksecdd!BCryptHashData` at `0x140015c9b`
- `ksecdd!BCryptDestroyHash` at `0x140015d35`
- `ksecdd!BCryptDestroyHash` at `0x140015d35`
- `ksecdd!BCryptFinishHash` at `0x140015ce5`
- `ksecdd!BCryptFinishHash` at `0x140015ce5`

## pseudocode

```c
__int64 __fastcall GenerateHmacShaHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR a6,
        _WORD *a7)
{
  NTSTATUS Property; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ecx
  unsigned int v15; // eax
  UCHAR *Pool2; // rax
  UCHAR *v17; // rsi
  PDEVICE_OBJECT v18; // r10
  __int64 v19; // rdx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  UCHAR v23[8]; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF

  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v23 = 0;
  pcbResult = 0;
  phHash = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_7;
    }
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v13 = 10;
LABEL_6:
    WPP_SF_d(AttachedDevice, v13, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
LABEL_7:
    *a7 = 0;
    return (unsigned int)Property;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v23, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_7;
    }
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v13 = 11;
    goto LABEL_6;
  }
  v14 = *(_DWORD *)v23;
  v15 = (unsigned __int16)*a7;
  *a7 = *(_WORD *)v23;
  if ( v15 < v14 )
  {
    Property = -1073741789;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
    return (unsigned int)Property;
  }
  Pool2 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)pbOutput, 1869112915);
  v17 = Pool2;
  if ( Pool2 )
  {
    Property = BCryptCreateHash(hAlgorithm, &phHash, Pool2, *(ULONG *)pbOutput, pbSecret, cbSecret, 0);
    if ( Property < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
      }
      goto LABEL_41;
    }
    Property = BCryptHashData(phHash, pbInput, cbInput, 0);
    if ( Property >= 0 )
    {
      Property = BCryptFinishHash(phHash, a6, (unsigned __int16)*a7, 0);
      if ( Property >= 0 )
        goto LABEL_40;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_40;
      }
      v19 = 16;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_40;
      }
      v19 = 15;
    }
    WPP_SF_d(v18->AttachedDevice, v19, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
LABEL_40:
    BCryptDestroyHash(phHash);
LABEL_41:
    ExFreePoolWithTag(v17, 0x6F686653u);
    return (unsigned int)Property;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140015a4c  push    rbp
0x140015a4e  push    rbx
0x140015a4f  push    rsi
0x140015a50  push    rdi
0x140015a51  push    r12
0x140015a53  push    r13
0x140015a55  push    r14
0x140015a57  push    r15
0x140015a59  mov     rbp, rsp
0x140015a5c  sub     rsp, 68h
0x140015a60  xor     edi, edi
0x140015a62  lea     rax, [rbp+var_24]
0x140015a66  mov     r15, r9
0x140015a69  mov     [rsp+68h+dwFlags], edi; dwFlags
0x140015a6d  mov     r12d, r8d
0x140015a70  mov     dword ptr [rbp+pbOutput], edi
0x140015a73  mov     r13, rdx
0x140015a76  mov     dword ptr [rbp+var_20], edi
0x140015a79  lea     esi, [rdi+4]
0x140015a7c  mov     [rbp+var_24], edi
0x140015a7f  mov     r9d, esi; cbOutput
0x140015a82  mov     [rbp+phHash], rdi
0x140015a86  lea     r8, [rbp+pbOutput]; pbOutput
0x140015a8a  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140015a8f  lea     rdx, pszProperty; "ObjectLength"
0x140015a96  mov     r14, rcx
0x140015a99  call    cs:__imp_BCryptGetProperty
0x140015aa0  nop     dword ptr [rax+rax+00h]
0x140015aa5  mov     ebx, eax
0x140015aa7  test    eax, eax
0x140015aa9  jns     short loc_140015AEE
0x140015aab  mov     rax, cs:WPP_GLOBAL_Control
0x140015ab2  lea     rcx, WPP_GLOBAL_Control
0x140015ab9  cmp     rax, rcx
0x140015abc  jz      short loc_140015AE2
0x140015abe  mov     edx, [rax+2Ch]
0x140015ac1  test    sil, dl
0x140015ac4  jz      short loc_140015AE2
0x140015ac6  cmp     byte ptr [rax+29h], 1
0x140015aca  jb      short loc_140015AE2
0x140015acc  mov     rcx, [rax+18h]
0x140015ad0  lea     edx, [rdi+0Ah]
0x140015ad3  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015ada  mov     r9d, ebx
0x140015add  call    WPP_SF_d
0x140015ae2  mov     rax, [rbp+arg_30]
0x140015ae6  mov     [rax], di
0x140015ae9  jmp     loc_140015D55
0x140015aee  lea     rax, [rbp+var_24]
0x140015af2  mov     [rsp+68h+dwFlags], edi; dwFlags
0x140015af6  mov     r9d, esi; cbOutput
0x140015af9  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140015afe  lea     r8, [rbp+var_20]; pbOutput
0x140015b02  mov     rcx, r14; hObject
0x140015b05  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140015b0c  call    cs:__imp_BCryptGetProperty
0x140015b13  nop     dword ptr [rax+rax+00h]
0x140015b18  mov     ebx, eax
0x140015b1a  test    eax, eax
0x140015b1c  jns     short loc_140015B4C
0x140015b1e  mov     r10, cs:WPP_GLOBAL_Control
0x140015b25  lea     rcx, WPP_GLOBAL_Control
0x140015b2c  cmp     r10, rcx
0x140015b2f  jz      short loc_140015AE2
0x140015b31  mov     eax, [r10+2Ch]
0x140015b35  test    sil, al
0x140015b38  jz      short loc_140015AE2
0x140015b3a  cmp     byte ptr [r10+29h], 1
0x140015b3f  jb      short loc_140015AE2
0x140015b41  mov     rcx, [r10+18h]
0x140015b45  mov     edx, 0Bh
0x140015b4a  jmp     short loc_140015AD3
0x140015b4c  mov     rdi, [rbp+arg_30]
0x140015b50  mov     ecx, dword ptr [rbp+var_20]
0x140015b53  movzx   eax, word ptr [rdi]
0x140015b56  mov     [rdi], cx
0x140015b59  cmp     eax, ecx
0x140015b5b  jnb     short loc_140015BAB
0x140015b5d  mov     ebx, 0C0000023h
0x140015b62  mov     r9, cs:WPP_GLOBAL_Control
0x140015b69  lea     rcx, WPP_GLOBAL_Control
0x140015b70  cmp     r9, rcx
0x140015b73  jz      loc_140015D55
0x140015b79  mov     eax, [r9+2Ch]
0x140015b7d  test    sil, al
0x140015b80  jz      loc_140015D55
0x140015b86  cmp     byte ptr [r9+29h], 1
0x140015b8b  jb      loc_140015D55
0x140015b91  mov     rcx, [r9+18h]
0x140015b95  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015b9c  mov     edx, 0Ch
0x140015ba1  call    WPP_SF_
0x140015ba6  jmp     loc_140015D55
0x140015bab  mov     edx, dword ptr [rbp+pbOutput]
0x140015bae  mov     ecx, 40h ; '@'
0x140015bb3  mov     r8d, 6F686653h
0x140015bb9  call    cs:__imp_ExAllocatePool2
0x140015bc0  nop     dword ptr [rax+rax+00h]
0x140015bc5  mov     rsi, rax
0x140015bc8  test    rax, rax
0x140015bcb  jnz     short loc_140015C10
0x140015bcd  mov     r10, cs:WPP_GLOBAL_Control
0x140015bd4  lea     rcx, WPP_GLOBAL_Control
0x140015bdb  cmp     r10, rcx
0x140015bde  jz      short loc_140015C06
0x140015be0  mov     eax, [r10+2Ch]
0x140015be4  test    al, 4
0x140015be6  jz      short loc_140015C06
0x140015be8  cmp     byte ptr [r10+29h], 1
0x140015bed  jb      short loc_140015C06
0x140015bef  mov     r9d, dword ptr [rbp+pbOutput]
0x140015bf3  lea     edx, [rsi+0Dh]
0x140015bf6  mov     rcx, [r10+18h]
0x140015bfa  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015c01  call    WPP_SF_d
0x140015c06  mov     ebx, 0C000009Ah
0x140015c0b  jmp     loc_140015D55
0x140015c10  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x140015c14  lea     rdx, [rbp+phHash]; phHash
0x140015c18  mov     [rsp+68h+var_38], 0; dwFlags
0x140015c20  mov     r8, rsi; pbHashObject
0x140015c23  mov     [rsp+68h+dwFlags], r12d; cbSecret
0x140015c28  mov     rcx, r14; hAlgorithm
0x140015c2b  mov     [rsp+68h+pcbResult], r13; pbSecret
0x140015c30  call    cs:__imp_BCryptCreateHash
0x140015c37  nop     dword ptr [rax+rax+00h]
0x140015c3c  mov     ebx, eax
0x140015c3e  test    eax, eax
0x140015c40  jns     short loc_140015C8D
0x140015c42  mov     r10, cs:WPP_GLOBAL_Control
0x140015c49  lea     rcx, WPP_GLOBAL_Control
0x140015c50  cmp     r10, rcx
0x140015c53  jz      loc_140015D41
0x140015c59  mov     eax, [r10+2Ch]
0x140015c5d  test    al, 4
0x140015c5f  jz      loc_140015D41
0x140015c65  cmp     byte ptr [r10+29h], 1
0x140015c6a  jb      loc_140015D41
0x140015c70  mov     rcx, [r10+18h]
0x140015c74  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015c7b  mov     edx, 0Eh
0x140015c80  mov     r9d, ebx
0x140015c83  call    WPP_SF_d
0x140015c88  jmp     loc_140015D41
0x140015c8d  mov     r8d, [rbp+cbInput]; cbInput
0x140015c91  xor     r9d, r9d; dwFlags
0x140015c94  mov     rcx, [rbp+phHash]; hHash
0x140015c98  mov     rdx, r15; pbInput
0x140015c9b  call    cs:__imp_BCryptHashData
0x140015ca2  nop     dword ptr [rax+rax+00h]
0x140015ca7  mov     ebx, eax
0x140015ca9  test    eax, eax
0x140015cab  jns     short loc_140015CD6
0x140015cad  mov     r10, cs:WPP_GLOBAL_Control
0x140015cb4  lea     rcx, WPP_GLOBAL_Control
0x140015cbb  cmp     r10, rcx
0x140015cbe  jz      short loc_140015D31
0x140015cc0  mov     eax, [r10+2Ch]
0x140015cc4  test    al, 4
0x140015cc6  jz      short loc_140015D31
0x140015cc8  cmp     byte ptr [r10+29h], 1
0x140015ccd  jb      short loc_140015D31
0x140015ccf  mov     edx, 0Fh
0x140015cd4  jmp     short loc_140015D1E
0x140015cd6  movzx   r8d, word ptr [rdi]; cbOutput
0x140015cda  xor     r9d, r9d; dwFlags
0x140015cdd  mov     rdx, [rbp+arg_28]; pbOutput
0x140015ce1  mov     rcx, [rbp+phHash]; hHash
0x140015ce5  call    cs:__imp_BCryptFinishHash
0x140015cec  nop     dword ptr [rax+rax+00h]
0x140015cf1  mov     ebx, eax
0x140015cf3  test    eax, eax
0x140015cf5  jns     short loc_140015D31
0x140015cf7  mov     r10, cs:WPP_GLOBAL_Control
0x140015cfe  lea     rcx, WPP_GLOBAL_Control
0x140015d05  cmp     r10, rcx
0x140015d08  jz      short loc_140015D31
0x140015d0a  mov     eax, [r10+2Ch]
0x140015d0e  test    al, 4
0x140015d10  jz      short loc_140015D31
0x140015d12  cmp     byte ptr [r10+29h], 1
0x140015d17  jb      short loc_140015D31
0x140015d19  mov     edx, 10h
0x140015d1e  mov     rcx, [r10+18h]
0x140015d22  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015d29  mov     r9d, ebx
0x140015d2c  call    WPP_SF_d
0x140015d31  mov     rcx, [rbp+phHash]; hHash
0x140015d35  call    cs:__imp_BCryptDestroyHash
0x140015d3c  nop     dword ptr [rax+rax+00h]
0x140015d41  mov     edx, 6F686653h; Tag
0x140015d46  mov     rcx, rsi; P
0x140015d49  call    cs:__imp_ExFreePoolWithTag
0x140015d50  nop     dword ptr [rax+rax+00h]
0x140015d55  mov     eax, ebx
0x140015d57  add     rsp, 68h
0x140015d5b  pop     r15
0x140015d5d  pop     r14
0x140015d5f  pop     r13
0x140015d61  pop     r12
0x140015d63  pop     rdi
0x140015d64  pop     rsi
0x140015d65  pop     rbx
0x140015d66  pop     rbp
0x140015d67  retn
```
