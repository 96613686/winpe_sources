# UxpSslDeleteTlsRestrictionsFromRegistry

- ea: `0x1c009f8f8`
- end: `0x1c009fdc3`
- name: `UxpSslDeleteTlsRestrictionsFromRegistry`
- size: `1227`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1c001b13c`
- `0x1c0133298`

## callees

- `0x1c009f008`
- `0x1c009f8f8`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1c009fa7a`
- `ntoskrnl!ZwEnumerateKey` at `0x1c009fbbe`
- `ntoskrnl!ZwEnumerateKey` at `0x1c009fa7a`
- `ntoskrnl!ZwEnumerateKey` at `0x1c009fbbe`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fb20`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fc64`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fc9f`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fcf1`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fd31`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fd7d`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fb20`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fc64`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fc9f`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fcf1`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fd31`
- `ntoskrnl!ZwDeleteKey` at `0x1c009fd7d`
- `ntoskrnl!ZwClose` at `0x1c009f9c3`
- `ntoskrnl!ZwClose` at `0x1c009f9d7`
- `ntoskrnl!ZwClose` at `0x1c009f9eb`
- `ntoskrnl!ZwClose` at `0x1c009f9ff`
- `ntoskrnl!ZwClose` at `0x1c009fa13`
- `ntoskrnl!ZwClose` at `0x1c009fa27`
- `ntoskrnl!ZwClose` at `0x1c009fb39`
- `ntoskrnl!ZwClose` at `0x1c009fc7d`
- `ntoskrnl!ZwClose` at `0x1c009fcb8`
- `ntoskrnl!ZwClose` at `0x1c009fd0a`
- `ntoskrnl!ZwClose` at `0x1c009fd4a`
- `ntoskrnl!ZwClose` at `0x1c009fd96`
- `ntoskrnl!ZwClose` at `0x1c009f9c3`
- `ntoskrnl!ZwClose` at `0x1c009f9d7`
- `ntoskrnl!ZwClose` at `0x1c009f9eb`
- `ntoskrnl!ZwClose` at `0x1c009f9ff`
- `ntoskrnl!ZwClose` at `0x1c009fa13`
- `ntoskrnl!ZwClose` at `0x1c009fa27`
- `ntoskrnl!ZwClose` at `0x1c009fb39`
- `ntoskrnl!ZwClose` at `0x1c009fc7d`
- `ntoskrnl!ZwClose` at `0x1c009fcb8`
- `ntoskrnl!ZwClose` at `0x1c009fd0a`
- `ntoskrnl!ZwClose` at `0x1c009fd4a`
- `ntoskrnl!ZwClose` at `0x1c009fd96`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c009f94e`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c009f94e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009f9af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009f9af`

## pseudocode

```c
__int64 __fastcall UxpSslDeleteTlsRestrictionsFromRegistry(__int64 a1)
{
  HANDLE v2; // r15
  HANDLE v3; // r14
  HANDLE v4; // rsi
  HANDLE v5; // r12
  HANDLE v6; // r13
  NTSTATUS v7; // ebx
  int v8; // eax
  HANDLE v9; // rdi
  NTSTATUS v11; // eax
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  int v15; // eax
  NTSTATUS v16; // eax
  int v17; // eax
  int v18; // eax
  ULONG Length; // [rsp+20h] [rbp-40h]
  ULONG Lengtha; // [rsp+20h] [rbp-40h]
  ULONG Lengthb; // [rsp+20h] [rbp-40h]
  ULONG Lengthc; // [rsp+20h] [rbp-40h]
  ULONG Lengthd; // [rsp+20h] [rbp-40h]
  HANDLE KeyHandle; // [rsp+30h] [rbp-30h] BYREF
  HANDLE v25; // [rsp+38h] [rbp-28h] BYREF
  HANDLE v26; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v27; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+50h] [rbp-10h]
  HANDLE Handle; // [rsp+58h] [rbp-8h] BYREF
  ULONG ResultLength; // [rsp+A8h] [rbp+48h] BYREF
  HANDLE v31; // [rsp+B0h] [rbp+50h] BYREF
  int v32; // [rsp+B8h] [rbp+58h]

  ResultLength = 0;
  Handle = 0;
  v31 = 0;
  KeyHandle = 0;
  v2 = 0;
  v27 = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v6 = 0;
  P = ExAllocatePoolWithTagPriority(PagedPool, 0x220u, 0x44526C55u, LowPoolPriority);
  if ( !P )
    return (unsigned int)-1073741670;
  v8 = UxOpenKey(a1, L"TlsRestrictions", 30, 131097, 0, &Handle);
  v7 = v8;
  if ( v8 == -1073741772 )
  {
    v7 = 0;
LABEL_5:
    v9 = Handle;
    goto LABEL_6;
  }
  if ( v8 < 0 )
    goto LABEL_5;
  v32 = 0;
  v9 = Handle;
  while ( 1 )
  {
    v11 = ZwEnumerateKey(v9, 0, KeyBasicInformation, P, 0x220u, &ResultLength);
    v7 = v11;
    if ( v11 == -2147483622 )
    {
LABEL_54:
      v7 = ZwDeleteKey(v9);
      if ( v7 >= 0 )
      {
        v7 = ZwClose(v9);
        if ( v7 >= 0 )
          v9 = 0;
      }
      goto LABEL_6;
    }
    if ( v11 < 0 )
      goto LABEL_6;
    LOBYTE(Length) = 0;
    v12 = *((unsigned __int16 *)P + 6);
    Handle = (char *)P + 16;
    v13 = UxOpenKey(v9, (char *)P + 16, v12, 131097, Length, &v31);
    v2 = v31;
    if ( v13 != -1073741772 )
      break;
LABEL_53:
    if ( (unsigned int)++v32 >= 4 )
      goto LABEL_54;
  }
  LOBYTE(Lengtha) = 0;
  v14 = UxOpenKey(v31, L"AlpnIds", 14, 131097, Lengtha, &KeyHandle);
  v3 = KeyHandle;
  v7 = v14;
  if ( v14 != -1073741772 )
  {
    if ( v14 < 0 )
      goto LABEL_6;
    v7 = ZwDeleteKey(KeyHandle);
    if ( v7 < 0 )
      goto LABEL_6;
    v7 = ZwClose(v3);
    if ( v7 < 0 )
      goto LABEL_6;
    v3 = 0;
    KeyHandle = 0;
  }
  LOBYTE(Lengthb) = 0;
  v15 = UxOpenKey(v2, L"CryptoSettings", 28, 131097, Lengthb, &v27);
  v7 = v15;
  if ( v15 == -1073741772 )
  {
    v4 = v27;
LABEL_50:
    v7 = ZwDeleteKey(v2);
    if ( v7 < 0 )
      goto LABEL_6;
    v7 = ZwClose(v2);
    if ( v7 < 0 )
      goto LABEL_6;
    v2 = 0;
    v31 = 0;
    goto LABEL_53;
  }
  if ( v15 < 0 )
  {
    v4 = v27;
  }
  else
  {
    LODWORD(v31) = 0;
    v4 = v27;
    do
    {
      v16 = ZwEnumerateKey(v4, 0, KeyBasicInformation, P, 0x220u, &ResultLength);
      v7 = v16;
      if ( v16 == -2147483622 )
        break;
      if ( v16 < 0 )
        goto LABEL_6;
      LOBYTE(Lengthc) = 0;
      v17 = UxOpenKey(v4, Handle, *((unsigned __int16 *)P + 6), 131097, Lengthc, &v26);
      v7 = v17;
      if ( v17 == -1073741772 )
      {
        v5 = v26;
      }
      else
      {
        if ( v17 < 0 )
        {
          v5 = v26;
          goto LABEL_6;
        }
        LOBYTE(Lengthd) = 0;
        v5 = v26;
        v18 = UxOpenKey(v26, L"ChainingModes", 26, 131097, Lengthd, &v25);
        v6 = v25;
        v7 = v18;
        if ( v18 != -1073741772 )
        {
          if ( v18 < 0 )
            goto LABEL_6;
          v7 = ZwDeleteKey(v25);
          if ( v7 < 0 )
            goto LABEL_6;
          v7 = ZwClose(v6);
          if ( v7 < 0 )
            goto LABEL_6;
          v6 = 0;
          v25 = 0;
        }
        v7 = ZwDeleteKey(v5);
        if ( v7 < 0 )
          goto LABEL_6;
        v7 = ZwClose(v5);
        if ( v7 < 0 )
          goto LABEL_6;
        v5 = 0;
        v26 = 0;
      }
      LODWORD(v31) = (_DWORD)v31 + 1;
    }
    while ( (unsigned int)v31 < 8 );
    v7 = ZwDeleteKey(v4);
    if ( v7 >= 0 )
    {
      v7 = ZwClose(v4);
      if ( v7 >= 0 )
      {
        v4 = 0;
        v27 = 0;
        goto LABEL_50;
      }
    }
  }
LABEL_6:
  ExFreePoolWithTag(P, 0);
  if ( v9 )
    ZwClose(v9);
  if ( v2 )
    ZwClose(v2);
  if ( v3 )
    ZwClose(v3);
  if ( v4 )
    ZwClose(v4);
  if ( v5 )
    ZwClose(v5);
  if ( v6 )
    ZwClose(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1c009f8f8  mov     [rsp-38h+arg_0], rbx
0x1c009f8fd  push    rbp
0x1c009f8fe  push    rsi
0x1c009f8ff  push    rdi
0x1c009f900  push    r12
0x1c009f902  push    r13
0x1c009f904  push    r14
0x1c009f906  push    r15
0x1c009f908  mov     rbp, rsp
0x1c009f90b  sub     rsp, 60h
0x1c009f90f  xor     edi, edi
0x1c009f911  mov     rbx, rcx
0x1c009f914  xor     r9d, r9d; Priority
0x1c009f917  mov     [rbp+arg_8], edi
0x1c009f91a  mov     edx, 220h; NumberOfBytes
0x1c009f91f  mov     [rbp+Handle], rdi
0x1c009f923  mov     r8d, 44526C55h; Tag
0x1c009f929  mov     [rbp+arg_10], rdi
0x1c009f92d  lea     ecx, [rdi+1]; PoolType
0x1c009f930  mov     [rbp+KeyHandle], rdi
0x1c009f934  mov     r15d, edi
0x1c009f937  mov     [rbp+var_18], rdi
0x1c009f93b  mov     r14d, edi
0x1c009f93e  mov     [rbp+var_20], rdi
0x1c009f942  mov     esi, edi
0x1c009f944  mov     [rbp+var_28], rdi
0x1c009f948  mov     r12d, edi
0x1c009f94b  mov     r13d, edi
0x1c009f94e  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c009f955  nop     dword ptr [rax+rax+00h]
0x1c009f95a  mov     [rbp+P], rax
0x1c009f95e  test    rax, rax
0x1c009f961  jnz     short loc_1C009F96D
0x1c009f963  mov     ebx, 0C000009Ah
0x1c009f968  jmp     loc_1C009FA33
0x1c009f96d  lea     rax, [rbp+Handle]
0x1c009f971  mov     r8d, 1Eh
0x1c009f977  mov     [rsp+60h+ResultLength], rax
0x1c009f97c  lea     rdx, aTlsrestriction; "TlsRestrictions"
0x1c009f983  mov     r9d, 20019h
0x1c009f989  mov     byte ptr [rsp+60h+Length], dil
0x1c009f98e  mov     rcx, rbx
0x1c009f991  call    UxOpenKey
0x1c009f996  mov     ebx, eax
0x1c009f998  cmp     eax, 0C0000034h
0x1c009f99d  jnz     loc_1C009FA4E
0x1c009f9a3  mov     ebx, edi
0x1c009f9a5  mov     rdi, [rbp+Handle]
0x1c009f9a9  mov     rcx, [rbp+P]; P
0x1c009f9ad  xor     edx, edx; Tag
0x1c009f9af  call    cs:__imp_ExFreePoolWithTag
0x1c009f9b6  nop     dword ptr [rax+rax+00h]
0x1c009f9bb  test    rdi, rdi
0x1c009f9be  jz      short loc_1C009F9CF
0x1c009f9c0  mov     rcx, rdi; Handle
0x1c009f9c3  call    cs:__imp_ZwClose
0x1c009f9ca  nop     dword ptr [rax+rax+00h]
0x1c009f9cf  test    r15, r15
0x1c009f9d2  jz      short loc_1C009F9E3
0x1c009f9d4  mov     rcx, r15; Handle
0x1c009f9d7  call    cs:__imp_ZwClose
0x1c009f9de  nop     dword ptr [rax+rax+00h]
0x1c009f9e3  test    r14, r14
0x1c009f9e6  jz      short loc_1C009F9F7
0x1c009f9e8  mov     rcx, r14; Handle
0x1c009f9eb  call    cs:__imp_ZwClose
0x1c009f9f2  nop     dword ptr [rax+rax+00h]
0x1c009f9f7  test    rsi, rsi
0x1c009f9fa  jz      short loc_1C009FA0B
0x1c009f9fc  mov     rcx, rsi; Handle
0x1c009f9ff  call    cs:__imp_ZwClose
0x1c009fa06  nop     dword ptr [rax+rax+00h]
0x1c009fa0b  test    r12, r12
0x1c009fa0e  jz      short loc_1C009FA1F
0x1c009fa10  mov     rcx, r12; Handle
0x1c009fa13  call    cs:__imp_ZwClose
0x1c009fa1a  nop     dword ptr [rax+rax+00h]
0x1c009fa1f  test    r13, r13
0x1c009fa22  jz      short loc_1C009FA33
0x1c009fa24  mov     rcx, r13; Handle
0x1c009fa27  call    cs:__imp_ZwClose
0x1c009fa2e  nop     dword ptr [rax+rax+00h]
0x1c009fa33  mov     eax, ebx
0x1c009fa35  mov     rbx, [rsp+60h+arg_0]
0x1c009fa3d  add     rsp, 60h
0x1c009fa41  pop     r15
0x1c009fa43  pop     r14
0x1c009fa45  pop     r13
0x1c009fa47  pop     r12
0x1c009fa49  pop     rdi
0x1c009fa4a  pop     rsi
0x1c009fa4b  pop     rbp
0x1c009fa4c  retn
0x1c009fa4e  test    eax, eax
0x1c009fa50  js      loc_1C009F9A5
0x1c009fa56  mov     [rbp+arg_18], edi
0x1c009fa59  mov     rdi, [rbp+Handle]
0x1c009fa5d  mov     r9, [rbp+P]; KeyInformation
0x1c009fa61  lea     rax, [rbp+arg_8]
0x1c009fa65  mov     [rsp+60h+ResultLength], rax; ResultLength
0x1c009fa6a  xor     r8d, r8d; KeyInformationClass
0x1c009fa6d  xor     edx, edx; Index
0x1c009fa6f  mov     [rsp+60h+Length], 220h; Length
0x1c009fa77  mov     rcx, rdi; KeyHandle
0x1c009fa7a  call    cs:__imp_ZwEnumerateKey
0x1c009fa81  nop     dword ptr [rax+rax+00h]
0x1c009fa86  mov     ebx, eax
0x1c009fa88  cmp     eax, 8000001Ah
0x1c009fa8d  jz      loc_1C009FD7A
0x1c009fa93  xor     r8d, r8d
0x1c009fa96  test    eax, eax
0x1c009fa98  js      loc_1C009F9A9
0x1c009fa9e  mov     rax, [rbp+P]
0x1c009faa2  lea     rdx, [rbp+arg_10]
0x1c009faa6  mov     [rsp+60h+ResultLength], rdx
0x1c009faab  mov     ebx, 20019h
0x1c009fab0  mov     byte ptr [rsp+60h+Length], r8b
0x1c009fab5  mov     r9d, ebx
0x1c009fab8  movzx   r8d, word ptr [rax+0Ch]
0x1c009fabd  lea     rcx, [rax+10h]
0x1c009fac1  mov     [rbp+Handle], rcx
0x1c009fac5  mov     rdx, rcx
0x1c009fac8  mov     rcx, rdi
0x1c009facb  call    UxOpenKey
0x1c009fad0  mov     r15, [rbp+arg_10]
0x1c009fad4  cmp     eax, 0C0000034h
0x1c009fad9  jz      loc_1C009FD69
0x1c009fadf  lea     rax, [rbp+KeyHandle]
0x1c009fae3  xor     r14d, r14d
0x1c009fae6  mov     [rsp+60h+ResultLength], rax
0x1c009faeb  lea     rdx, aAlpnids; "AlpnIds"
0x1c009faf2  mov     r8d, 0Eh
0x1c009faf8  mov     byte ptr [rsp+60h+Length], r14b
0x1c009fafd  mov     r9d, ebx
0x1c009fb00  mov     rcx, r15
0x1c009fb03  call    UxOpenKey
0x1c009fb08  mov     r14, [rbp+KeyHandle]
0x1c009fb0c  mov     ebx, eax
0x1c009fb0e  cmp     eax, 0C0000034h
0x1c009fb13  jz      short loc_1C009FB5A
0x1c009fb15  test    eax, eax
0x1c009fb17  js      loc_1C009F9A9
0x1c009fb1d  mov     rcx, r14; KeyHandle
0x1c009fb20  call    cs:__imp_ZwDeleteKey
0x1c009fb27  nop     dword ptr [rax+rax+00h]
0x1c009fb2c  mov     ebx, eax
0x1c009fb2e  test    eax, eax
0x1c009fb30  js      loc_1C009F9A9
0x1c009fb36  mov     rcx, r14; Handle
0x1c009fb39  call    cs:__imp_ZwClose
0x1c009fb40  nop     dword ptr [rax+rax+00h]
0x1c009fb45  mov     ebx, eax
0x1c009fb47  test    eax, eax
0x1c009fb49  js      loc_1C009F9A9
0x1c009fb4f  xor     esi, esi
0x1c009fb51  mov     r14d, esi
0x1c009fb54  mov     [rbp+KeyHandle], rsi
0x1c009fb58  jmp     short loc_1C009FB5C
0x1c009fb5a  xor     esi, esi
0x1c009fb5c  lea     rax, [rbp+var_18]
0x1c009fb60  mov     r8d, 1Ch
0x1c009fb66  mov     [rsp+60h+ResultLength], rax
0x1c009fb6b  lea     rdx, aCryptosettings; "CryptoSettings"
0x1c009fb72  mov     r9d, 20019h
0x1c009fb78  mov     byte ptr [rsp+60h+Length], sil
0x1c009fb7d  mov     rcx, r15
0x1c009fb80  call    UxOpenKey
0x1c009fb85  mov     ebx, eax
0x1c009fb87  cmp     eax, 0C0000034h
0x1c009fb8c  jz      loc_1C009FD2A
0x1c009fb92  test    eax, eax
0x1c009fb94  js      loc_1C009FDBA
0x1c009fb9a  mov     dword ptr [rbp+arg_10], esi
0x1c009fb9d  mov     rsi, [rbp+var_18]
0x1c009fba1  mov     r9, [rbp+P]; KeyInformation
0x1c009fba5  lea     rax, [rbp+arg_8]
0x1c009fba9  mov     [rsp+60h+ResultLength], rax; ResultLength
0x1c009fbae  xor     r8d, r8d; KeyInformationClass
0x1c009fbb1  xor     edx, edx; Index
0x1c009fbb3  mov     [rsp+60h+Length], 220h; Length
0x1c009fbbb  mov     rcx, rsi; KeyHandle
0x1c009fbbe  call    cs:__imp_ZwEnumerateKey
0x1c009fbc5  nop     dword ptr [rax+rax+00h]
0x1c009fbca  mov     ebx, eax
0x1c009fbcc  cmp     eax, 8000001Ah
0x1c009fbd1  jz      loc_1C009FCEE
0x1c009fbd7  test    eax, eax
0x1c009fbd9  js      loc_1C009F9A9
0x1c009fbdf  mov     rdx, [rbp+Handle]
0x1c009fbe3  lea     rax, [rbp+var_20]
0x1c009fbe7  mov     [rsp+60h+ResultLength], rax
0x1c009fbec  xor     r12d, r12d
0x1c009fbef  mov     rax, [rbp+P]
0x1c009fbf3  mov     r9d, 20019h
0x1c009fbf9  mov     rcx, rsi
0x1c009fbfc  mov     byte ptr [rsp+60h+Length], r12b
0x1c009fc01  movzx   r8d, word ptr [rax+0Ch]
0x1c009fc06  call    UxOpenKey
0x1c009fc0b  mov     ebx, eax
0x1c009fc0d  cmp     eax, 0C0000034h
0x1c009fc12  jz      loc_1C009FCD9
0x1c009fc18  test    eax, eax
0x1c009fc1a  js      loc_1C009FDB1
0x1c009fc20  lea     rax, [rbp+var_28]
0x1c009fc24  mov     r9d, 20019h
0x1c009fc2a  mov     [rsp+60h+ResultLength], rax
0x1c009fc2f  lea     r8d, [r12+1Ah]
0x1c009fc34  mov     byte ptr [rsp+60h+Length], r12b
0x1c009fc39  lea     rdx, aChainingmodes; "ChainingModes"
0x1c009fc40  mov     r12, [rbp+var_20]
0x1c009fc44  mov     rcx, r12
0x1c009fc47  call    UxOpenKey
0x1c009fc4c  mov     r13, [rbp+var_28]
0x1c009fc50  mov     ebx, eax
0x1c009fc52  cmp     eax, 0C0000034h
0x1c009fc57  jz      short loc_1C009FC9C
0x1c009fc59  test    eax, eax
0x1c009fc5b  js      loc_1C009F9A9
0x1c009fc61  mov     rcx, r13; KeyHandle
0x1c009fc64  call    cs:__imp_ZwDeleteKey
0x1c009fc6b  nop     dword ptr [rax+rax+00h]
0x1c009fc70  mov     ebx, eax
0x1c009fc72  test    eax, eax
0x1c009fc74  js      loc_1C009F9A9
0x1c009fc7a  mov     rcx, r13; Handle
0x1c009fc7d  call    cs:__imp_ZwClose
0x1c009fc84  nop     dword ptr [rax+rax+00h]
0x1c009fc89  mov     ebx, eax
0x1c009fc8b  xor     eax, eax
0x1c009fc8d  test    ebx, ebx
0x1c009fc8f  js      loc_1C009F9A9
0x1c009fc95  mov     r13d, eax
0x1c009fc98  mov     [rbp+var_28], rax
0x1c009fc9c  mov     rcx, r12; KeyHandle
0x1c009fc9f  call    cs:__imp_ZwDeleteKey
0x1c009fca6  nop     dword ptr [rax+rax+00h]
0x1c009fcab  mov     ebx, eax
0x1c009fcad  test    eax, eax
0x1c009fcaf  js      loc_1C009F9A9
0x1c009fcb5  mov     rcx, r12; Handle
0x1c009fcb8  call    cs:__imp_ZwClose
0x1c009fcbf  nop     dword ptr [rax+rax+00h]
0x1c009fcc4  mov     ebx, eax
0x1c009fcc6  xor     eax, eax
0x1c009fcc8  test    ebx, ebx
0x1c009fcca  js      loc_1C009F9A9
0x1c009fcd0  mov     r12d, eax
0x1c009fcd3  mov     [rbp+var_20], rax
0x1c009fcd7  jmp     short loc_1C009FCDD
0x1c009fcd9  mov     r12, [rbp+var_20]
0x1c009fcdd  mov     eax, dword ptr [rbp+arg_10]
0x1c009fce0  inc     eax
0x1c009fce2  mov     dword ptr [rbp+arg_10], eax
0x1c009fce5  cmp     eax, 8
0x1c009fce8  jb      loc_1C009FBA1
0x1c009fcee  mov     rcx, rsi; KeyHandle
0x1c009fcf1  call    cs:__imp_ZwDeleteKey
0x1c009fcf8  nop     dword ptr [rax+rax+00h]
0x1c009fcfd  mov     ebx, eax
0x1c009fcff  test    eax, eax
0x1c009fd01  js      loc_1C009F9A9
0x1c009fd07  mov     rcx, rsi; Handle
0x1c009fd0a  call    cs:__imp_ZwClose
0x1c009fd11  nop     dword ptr [rax+rax+00h]
0x1c009fd16  mov     ebx, eax
0x1c009fd18  xor     eax, eax
0x1c009fd1a  test    ebx, ebx
0x1c009fd1c  js      loc_1C009F9A9
0x1c009fd22  mov     esi, eax
0x1c009fd24  mov     [rbp+var_18], rax
0x1c009fd28  jmp     short loc_1C009FD2E
0x1c009fd2a  mov     rsi, [rbp+var_18]
0x1c009fd2e  mov     rcx, r15; KeyHandle
0x1c009fd31  call    cs:__imp_ZwDeleteKey
0x1c009fd38  nop     dword ptr [rax+rax+00h]
0x1c009fd3d  mov     ebx, eax
0x1c009fd3f  test    eax, eax
0x1c009fd41  js      loc_1C009F9A9
0x1c009fd47  mov     rcx, r15; Handle
0x1c009fd4a  call    cs:__imp_ZwClose
0x1c009fd51  nop     dword ptr [rax+rax+00h]
0x1c009fd56  mov     ebx, eax
0x1c009fd58  xor     eax, eax
0x1c009fd5a  test    ebx, ebx
0x1c009fd5c  js      loc_1C009F9A9
0x1c009fd62  mov     r15d, eax
0x1c009fd65  mov     [rbp+arg_10], rax
0x1c009fd69  mov     eax, [rbp+arg_18]
0x1c009fd6c  inc     eax
0x1c009fd6e  mov     [rbp+arg_18], eax
0x1c009fd71  cmp     eax, 4
0x1c009fd74  jb      loc_1C009FA5D
0x1c009fd7a  mov     rcx, rdi; KeyHandle
0x1c009fd7d  call    cs:__imp_ZwDeleteKey
0x1c009fd84  nop     dword ptr [rax+rax+00h]
0x1c009fd89  mov     ebx, eax
0x1c009fd8b  test    eax, eax
0x1c009fd8d  js      loc_1C009F9A9
0x1c009fd93  mov     rcx, rdi; Handle
0x1c009fd96  call    cs:__imp_ZwClose
  ... truncated ...
```
