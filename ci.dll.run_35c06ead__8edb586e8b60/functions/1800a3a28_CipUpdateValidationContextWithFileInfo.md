# CipUpdateValidationContextWithFileInfo

- ea: `0x1800a3a28`
- end: `0x1800a3cbc`
- name: `CipUpdateValidationContextWithFileInfo`
- size: `660`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000edb0`
- `0x180092710`
- `0x18009e170`

## callees

- `0x18007680c`
- `0x1800a3a28`
- `0x1800a3cc4`
- `0x1800a46e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3bce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3be6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3bfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3c16`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3bce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3be6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3bfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3c16`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3b75`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c3b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c65`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c8f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3b75`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c3b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c65`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3c8f`

## pseudocode

```c
__int64 __fastcall CipUpdateValidationContextWithFileInfo(__int64 a1, __int64 a2, void *a3, unsigned int a4)
{
  bool v4; // zf
  NTSTATUS updated; // ecx
  __int64 v11; // rax
  int v12; // [rsp+30h] [rbp-21h]
  UNICODE_STRING StringIn; // [rsp+50h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+Fh] BYREF
  UNICODE_STRING v15; // [rsp+70h] [rbp+1Fh] BYREF
  UNICODE_STRING v16; // [rsp+80h] [rbp+2Fh] BYREF
  __int64 v17; // [rsp+B0h] [rbp+5Fh] BYREF

  v4 = *(_QWORD *)(a1 + 816) == 0;
  v17 = 0;
  StringIn = 0;
  DestinationString = 0;
  v15 = 0;
  v16 = 0;
  if ( !v4 || (*(_DWORD *)(a1 + 2368) & 4) != 0 )
    return 0;
  if ( (g_CiPolicyState & 0x400000) != 0 && *(_DWORD *)(a1 + 3432) == 1 )
    CiHotpatchGetHotpatchSequenceFromImage();
  if ( !a2 )
    goto LABEL_9;
  if ( *(_DWORD *)(a1 + 2344) == 1 )
    *(_QWORD *)(a1 + 984) = a2;
  updated = CiUpdateValidationContextWithFilePath(a1);
  if ( updated >= 0 )
  {
LABEL_9:
    updated = SIPolicyGetOriginalFilenameAndVersionFromImageBase(
                a3,
                a4,
                (__int64)&v17,
                (__int64)&v16,
                v12,
                (__int64)&DestinationString,
                (__int64)&v15);
    if ( (unsigned int)(updated + 1073741687) <= 2 || updated == -1073741793 || updated == -1073741308 )
    {
      updated = -1073741275;
    }
    else if ( updated >= 0 )
    {
      goto LABEL_13;
    }
    if ( !StringIn.Buffer )
      goto LABEL_28;
    if ( updated == -1073741275 )
    {
LABEL_13:
      if ( StringIn.Buffer )
      {
LABEL_14:
        if ( !DestinationString.Buffer )
          RtlInitUnicodeString(&DestinationString, &word_1800499B4);
        if ( !v15.Buffer )
          RtlInitUnicodeString(&v15, &word_1800499B4);
        if ( !v16.Buffer )
          RtlInitUnicodeString(&v16, &word_1800499B4);
        updated = RtlDuplicateUnicodeString(0, &StringIn, (PUNICODE_STRING)(a1 + 744));
        if ( updated >= 0 )
        {
          *(_DWORD *)(a1 + 2368) |= 4u;
          updated = RtlDuplicateUnicodeString(0, &DestinationString, (PUNICODE_STRING)(a1 + 760));
          if ( updated >= 0 )
          {
            *(_DWORD *)(a1 + 2368) |= 8u;
            updated = RtlDuplicateUnicodeString(0, &v15, (PUNICODE_STRING)(a1 + 776));
            if ( updated >= 0 )
            {
              *(_DWORD *)(a1 + 2368) |= 0x10u;
              updated = RtlDuplicateUnicodeString(0, &v16, (PUNICODE_STRING)(a1 + 792));
              if ( updated >= 0 )
              {
                v11 = v17;
                *(_DWORD *)(a1 + 2368) |= 0x20u;
                *(_QWORD *)(a1 + 840) = v11;
              }
            }
          }
        }
        return (unsigned int)updated;
      }
LABEL_28:
      RtlInitUnicodeString(&StringIn, &word_1800499B4);
      goto LABEL_14;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800a3a28  mov     [rsp-8+arg_8], rbx
0x1800a3a2d  mov     [rsp-8+arg_10], rsi
0x1800a3a32  push    rbp
0x1800a3a33  push    rdi
0x1800a3a34  push    r14
0x1800a3a36  lea     rbp, [rsp-3Fh]
0x1800a3a3b  sub     rsp, 90h
0x1800a3a42  cmp     qword ptr [rcx+330h], 0
0x1800a3a4a  xorps   xmm0, xmm0
0x1800a3a4d  xorps   xmm1, xmm1
0x1800a3a50  mov     [rbp+4Fh+arg_0], 0
0x1800a3a58  movups  xmmword ptr [rbp+4Fh+StringIn.Length], xmm0
0x1800a3a5c  mov     esi, r9d
0x1800a3a5f  mov     r14, r8
0x1800a3a62  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x1800a3a66  mov     rdi, rdx
0x1800a3a69  mov     rbx, rcx
0x1800a3a6c  movups  xmmword ptr [rbp+4Fh+var_30.Length], xmm0
0x1800a3a70  movups  xmmword ptr [rbp+4Fh+var_20.Length], xmm1
0x1800a3a74  jz      short loc_1800A3A91
0x1800a3a76  xor     eax, eax
0x1800a3a78  lea     r11, [rsp+0A0h+var_10]
0x1800a3a80  mov     rbx, [r11+28h]
0x1800a3a84  mov     rsi, [r11+30h]
0x1800a3a88  mov     rsp, r11
0x1800a3a8b  pop     r14
0x1800a3a8d  pop     rdi
0x1800a3a8e  pop     rbp
0x1800a3a8f  retn
0x1800a3a91  mov     eax, [rcx+940h]
0x1800a3a97  test    al, 4
0x1800a3a99  jnz     short loc_1800A3A76
0x1800a3a9b  test    cs:g_CiPolicyState, 400000h
0x1800a3aa5  jnz     loc_1800A3B92
0x1800a3aab  test    rdi, rdi
0x1800a3aae  jz      short loc_1800A3ACF
0x1800a3ab0  cmp     dword ptr [rbx+928h], 1
0x1800a3ab7  jz      loc_1800A3BA9
0x1800a3abd  mov     rcx, rbx
0x1800a3ac0  call    CiUpdateValidationContextWithFilePath
0x1800a3ac5  mov     ecx, eax
0x1800a3ac7  test    eax, eax
0x1800a3ac9  js      loc_1800A3B8B
0x1800a3acf  mov     r8b, [rbp+4Fh+arg_20]
0x1800a3ad3  lea     rax, [rbp+4Fh+var_30]
0x1800a3ad7  mov     [rsp+0A0h+var_60], rax; __int64
0x1800a3adc  lea     r9, [rbp+4Fh+StringIn]
0x1800a3ae0  lea     rax, [rbp+4Fh+DestinationString]
0x1800a3ae4  mov     edx, esi; Size
0x1800a3ae6  mov     [rsp+0A0h+var_68], rax; __int64
0x1800a3aeb  mov     rcx, r14; BaseAddress
0x1800a3aee  lea     rax, [rbp+4Fh+var_20]
0x1800a3af2  mov     [rsp+0A0h+var_78], rax; __int64
0x1800a3af7  lea     rax, [rbp+4Fh+arg_0]
0x1800a3afb  mov     [rsp+0A0h+var_80], rax; __int64
0x1800a3b00  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a3b05  mov     rdx, [rbp+4Fh+StringIn.Buffer]
0x1800a3b09  lea     rdi, word_1800499B4
0x1800a3b10  mov     ecx, eax
0x1800a3b12  mov     r8d, 0C0000225h
0x1800a3b18  add     eax, 3FFFFF77h
0x1800a3b1d  cmp     eax, 2
0x1800a3b20  jbe     loc_1800A3BB5
0x1800a3b26  cmp     ecx, 0C000001Fh
0x1800a3b2c  jz      loc_1800A3BB5
0x1800a3b32  cmp     ecx, 0C0000204h
0x1800a3b38  jz      short loc_1800A3BB5
0x1800a3b3a  test    ecx, ecx
0x1800a3b3c  js      short loc_1800A3BB8
0x1800a3b3e  test    rdx, rdx
0x1800a3b41  jz      loc_1800A3BC7
0x1800a3b47  cmp     [rbp+4Fh+DestinationString.Buffer], 0
0x1800a3b4c  jz      loc_1800A3BDF
0x1800a3b52  cmp     [rbp+4Fh+var_30.Buffer], 0
0x1800a3b57  jz      loc_1800A3BF7
0x1800a3b5d  cmp     [rbp+4Fh+var_20.Buffer], 0
0x1800a3b62  jz      loc_1800A3C0F
0x1800a3b68  lea     r8, [rbx+2E8h]; StringOut
0x1800a3b6f  xor     ecx, ecx; Flags
0x1800a3b71  lea     rdx, [rbp+4Fh+StringIn]; StringIn
0x1800a3b75  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3b7c  nop     dword ptr [rax+rax+00h]
0x1800a3b81  mov     ecx, eax
0x1800a3b83  test    eax, eax
0x1800a3b85  jns     loc_1800A3C27
0x1800a3b8b  mov     eax, ecx
0x1800a3b8d  jmp     loc_1800A3A78
0x1800a3b92  cmp     dword ptr [rcx+0D68h], 1
0x1800a3b99  jnz     loc_1800A3AAB
0x1800a3b9f  call    CiHotpatchGetHotpatchSequenceFromImage
0x1800a3ba4  jmp     loc_1800A3AAB
0x1800a3ba9  mov     [rbx+3D8h], rdi
0x1800a3bb0  jmp     loc_1800A3ABD
0x1800a3bb5  mov     ecx, r8d
0x1800a3bb8  test    rdx, rdx
0x1800a3bbb  jz      short loc_1800A3BC7
0x1800a3bbd  cmp     ecx, r8d
0x1800a3bc0  jnz     short loc_1800A3B8B
0x1800a3bc2  jmp     loc_1800A3B3E
0x1800a3bc7  mov     rdx, rdi; SourceString
0x1800a3bca  lea     rcx, [rbp+4Fh+StringIn]; DestinationString
0x1800a3bce  call    cs:__imp_RtlInitUnicodeString
0x1800a3bd5  nop     dword ptr [rax+rax+00h]
0x1800a3bda  jmp     loc_1800A3B47
0x1800a3bdf  mov     rdx, rdi; SourceString
0x1800a3be2  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800a3be6  call    cs:__imp_RtlInitUnicodeString
0x1800a3bed  nop     dword ptr [rax+rax+00h]
0x1800a3bf2  jmp     loc_1800A3B52
0x1800a3bf7  mov     rdx, rdi; SourceString
0x1800a3bfa  lea     rcx, [rbp+4Fh+var_30]; DestinationString
0x1800a3bfe  call    cs:__imp_RtlInitUnicodeString
0x1800a3c05  nop     dword ptr [rax+rax+00h]
0x1800a3c0a  jmp     loc_1800A3B5D
0x1800a3c0f  mov     rdx, rdi; SourceString
0x1800a3c12  lea     rcx, [rbp+4Fh+var_20]; DestinationString
0x1800a3c16  call    cs:__imp_RtlInitUnicodeString
0x1800a3c1d  nop     dword ptr [rax+rax+00h]
0x1800a3c22  jmp     loc_1800A3B68
0x1800a3c27  or      dword ptr [rbx+940h], 4
0x1800a3c2e  lea     r8, [rbx+2F8h]; StringOut
0x1800a3c35  lea     rdx, [rbp+4Fh+DestinationString]; StringIn
0x1800a3c39  xor     ecx, ecx; Flags
0x1800a3c3b  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3c42  nop     dword ptr [rax+rax+00h]
0x1800a3c47  mov     ecx, eax
0x1800a3c49  test    eax, eax
0x1800a3c4b  js      loc_1800A3B8B
0x1800a3c51  or      dword ptr [rbx+940h], 8
0x1800a3c58  lea     r8, [rbx+308h]; StringOut
0x1800a3c5f  lea     rdx, [rbp+4Fh+var_30]; StringIn
0x1800a3c63  xor     ecx, ecx; Flags
0x1800a3c65  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3c6c  nop     dword ptr [rax+rax+00h]
0x1800a3c71  mov     ecx, eax
0x1800a3c73  test    eax, eax
0x1800a3c75  js      loc_1800A3B8B
0x1800a3c7b  or      dword ptr [rbx+940h], 10h
0x1800a3c82  lea     r8, [rbx+318h]; StringOut
0x1800a3c89  lea     rdx, [rbp+4Fh+var_20]; StringIn
0x1800a3c8d  xor     ecx, ecx; Flags
0x1800a3c8f  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3c96  nop     dword ptr [rax+rax+00h]
0x1800a3c9b  mov     ecx, eax
0x1800a3c9d  test    eax, eax
0x1800a3c9f  js      loc_1800A3B8B
0x1800a3ca5  mov     rax, [rbp+4Fh+arg_0]
0x1800a3ca9  or      dword ptr [rbx+940h], 20h
0x1800a3cb0  mov     [rbx+348h], rax
0x1800a3cb7  jmp     loc_1800A3B8B
```
