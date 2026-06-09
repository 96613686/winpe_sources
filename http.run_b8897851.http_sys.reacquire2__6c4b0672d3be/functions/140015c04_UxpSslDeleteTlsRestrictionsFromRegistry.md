# UxpSslDeleteTlsRestrictionsFromRegistry

- ea: `0x140015c04`
- end: `0x140015e1e`
- name: `UxpSslDeleteTlsRestrictionsFromRegistry`
- size: `538`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400153d8`
- `0x140015b5c`

## callees

- `0x140015c04`
- `0x14009def0`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140015d03`
- `ntoskrnl!ZwOpenKey` at `0x140015d03`
- `ntoskrnl!ZwEnumerateKey` at `0x140171c87`
- `ntoskrnl!ZwEnumerateKey` at `0x140171dca`
- `ntoskrnl!ZwEnumerateKey` at `0x140171c87`
- `ntoskrnl!ZwEnumerateKey` at `0x140171dca`
- `ntoskrnl!ZwDeleteKey` at `0x140171d27`
- `ntoskrnl!ZwDeleteKey` at `0x140171e6e`
- `ntoskrnl!ZwDeleteKey` at `0x140171ea7`
- `ntoskrnl!ZwDeleteKey` at `0x140171ef0`
- `ntoskrnl!ZwDeleteKey` at `0x140171f28`
- `ntoskrnl!ZwDeleteKey` at `0x140171f74`
- `ntoskrnl!ZwDeleteKey` at `0x140171d27`
- `ntoskrnl!ZwDeleteKey` at `0x140171e6e`
- `ntoskrnl!ZwDeleteKey` at `0x140171ea7`
- `ntoskrnl!ZwDeleteKey` at `0x140171ef0`
- `ntoskrnl!ZwDeleteKey` at `0x140171f28`
- `ntoskrnl!ZwDeleteKey` at `0x140171f74`
- `ntoskrnl!ZwClose` at `0x140015d61`
- `ntoskrnl!ZwClose` at `0x140015da2`
- `ntoskrnl!ZwClose` at `0x140015db3`
- `ntoskrnl!ZwClose` at `0x140015dc7`
- `ntoskrnl!ZwClose` at `0x140015ddb`
- `ntoskrnl!ZwClose` at `0x140015def`
- `ntoskrnl!ZwClose` at `0x140171d40`
- `ntoskrnl!ZwClose` at `0x140171e87`
- `ntoskrnl!ZwClose` at `0x140171ec0`
- `ntoskrnl!ZwClose` at `0x140171f09`
- `ntoskrnl!ZwClose` at `0x140171f41`
- `ntoskrnl!ZwClose` at `0x140171f8d`
- `ntoskrnl!ZwClose` at `0x140015d61`
- `ntoskrnl!ZwClose` at `0x140015da2`
- `ntoskrnl!ZwClose` at `0x140015db3`
- `ntoskrnl!ZwClose` at `0x140015dc7`
- `ntoskrnl!ZwClose` at `0x140015ddb`
- `ntoskrnl!ZwClose` at `0x140015def`
- `ntoskrnl!ZwClose` at `0x140171d40`
- `ntoskrnl!ZwClose` at `0x140171e87`
- `ntoskrnl!ZwClose` at `0x140171ec0`
- `ntoskrnl!ZwClose` at `0x140171f09`
- `ntoskrnl!ZwClose` at `0x140171f41`
- `ntoskrnl!ZwClose` at `0x140171f8d`
- `ntoskrnl!ExAllocatePool3` at `0x140015c76`
- `ntoskrnl!ExAllocatePool3` at `0x140015c76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d24`

## pseudocode

```c
__int64 __fastcall UxpSslDeleteTlsRestrictionsFromRegistry(void *a1)
{
  void *v1; // rsi
  HANDLE v3; // r15
  HANDLE v4; // r14
  HANDLE v5; // rdi
  HANDLE v6; // r12
  HANDLE v7; // r13
  NTSTATUS v8; // ebx
  NTSTATUS v10; // eax
  unsigned int v11; // eax
  NTSTATUS v12; // eax
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int i; // eax
  NTSTATUS v18; // eax
  int v19; // eax
  int v20; // eax
  ULONG Length; // [rsp+20h] [rbp-69h]
  ULONG Lengtha; // [rsp+20h] [rbp-69h]
  ULONG Lengthb; // [rsp+20h] [rbp-69h]
  ULONG Lengthc; // [rsp+20h] [rbp-69h]
  ULONG Lengthd; // [rsp+20h] [rbp-69h]
  HANDLE Handle; // [rsp+30h] [rbp-59h] BYREF
  HANDLE v27; // [rsp+38h] [rbp-51h] BYREF
  HANDLE v28; // [rsp+40h] [rbp-49h] BYREF
  HANDLE v29; // [rsp+48h] [rbp-41h] BYREF
  PVOID P; // [rsp+50h] [rbp-39h]
  void *KeyHandle; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v32[2]; // [rsp+60h] [rbp-29h] BYREF
  char *v33; // [rsp+70h] [rbp-19h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE v36; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v37; // [rsp+108h] [rbp+7Fh]

  v1 = 0;
  ResultLength = 0;
  v3 = 0;
  v36 = 0;
  v4 = 0;
  Handle = 0;
  v5 = 0;
  v29 = 0;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 38, WPP_b370fe665b8033233cc44e642047166f_Traceguids, a1);
  P = (PVOID)ExAllocatePool3(258, 544, 1146252373, UxLowPriorityPool, 1);
  if ( !P )
  {
    v8 = -1073741670;
    goto LABEL_5;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v32[1] = L"TlsRestrictions";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v32;
  v32[0] = 1966110;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( v10 == -1073741772 )
      v8 = 0;
    goto LABEL_11;
  }
  v1 = KeyHandle;
  v11 = 0;
  KeyHandle = 0;
  while ( 1 )
  {
    v37 = v11;
    if ( v11 >= 4
      || (v12 = ZwEnumerateKey(v1, 0, KeyBasicInformation, P, 0x220u, &ResultLength), v8 = v12, v12 == -2147483622) )
    {
      v8 = ZwDeleteKey(v1);
      if ( v8 >= 0 )
      {
        v8 = ZwClose(v1);
        if ( v8 >= 0 )
          v1 = 0;
      }
      goto LABEL_11;
    }
    if ( v12 < 0 )
      goto LABEL_11;
    LOBYTE(Length) = 0;
    v13 = *((unsigned __int16 *)P + 6);
    v33 = (char *)P + 16;
    v14 = UxOpenKey(v1, (char *)P + 16, v13, 131097, Length, &v36);
    v3 = v36;
    if ( v14 != -1073741772 )
      break;
LABEL_57:
    v11 = v37 + 1;
  }
  LOBYTE(Lengtha) = 0;
  v15 = UxOpenKey(v36, L"AlpnIds", 14, 131097, Lengtha, &Handle);
  v4 = Handle;
  v8 = v15;
  if ( v15 != -1073741772 )
  {
    if ( v15 < 0 )
      goto LABEL_11;
    v8 = ZwDeleteKey(Handle);
    if ( v8 < 0 )
      goto LABEL_11;
    v8 = ZwClose(v4);
    if ( v8 < 0 )
      goto LABEL_11;
    v4 = 0;
    Handle = 0;
  }
  LOBYTE(Lengthb) = 0;
  v16 = UxOpenKey(v3, L"CryptoSettings", 28, 131097, Lengthb, &v29);
  v5 = v29;
  v8 = v16;
  if ( v16 == -1073741772 )
  {
LABEL_54:
    v8 = ZwDeleteKey(v3);
    if ( v8 < 0 )
      goto LABEL_11;
    v8 = ZwClose(v3);
    if ( v8 < 0 )
      goto LABEL_11;
    v3 = 0;
    v36 = 0;
    goto LABEL_57;
  }
  if ( v16 >= 0 )
  {
    for ( i = 0; ; i = (_DWORD)v36 + 1 )
    {
      LODWORD(v36) = i;
      if ( i >= 8 )
        break;
      v18 = ZwEnumerateKey(v5, 0, KeyBasicInformation, P, 0x220u, &ResultLength);
      v8 = v18;
      if ( v18 == -2147483622 )
        break;
      if ( v18 < 0 )
        goto LABEL_11;
      LOBYTE(Lengthc) = 0;
      v19 = UxOpenKey(v5, v33, *((unsigned __int16 *)P + 6), 131097, Lengthc, &v28);
      v8 = v19;
      if ( v19 == -1073741772 )
      {
        v6 = v28;
      }
      else
      {
        if ( v19 < 0 )
        {
          v6 = v28;
          goto LABEL_11;
        }
        v6 = v28;
        LOBYTE(Lengthd) = 0;
        v20 = UxOpenKey(v28, L"ChainingModes", 26, 131097, Lengthd, &v27);
        v7 = v27;
        v8 = v20;
        if ( v20 != -1073741772 )
        {
          if ( v20 < 0 )
            goto LABEL_11;
          v8 = ZwDeleteKey(v27);
          if ( v8 < 0 )
            goto LABEL_11;
          v8 = ZwClose(v7);
          if ( v8 < 0 )
            goto LABEL_11;
          v7 = 0;
          v27 = 0;
        }
        v8 = ZwDeleteKey(v6);
        if ( v8 < 0 )
          goto LABEL_11;
        v8 = ZwClose(v6);
        if ( v8 < 0 )
          goto LABEL_11;
        v6 = 0;
        v28 = 0;
      }
    }
    v8 = ZwDeleteKey(v5);
    if ( v8 >= 0 )
    {
      v8 = ZwClose(v5);
      if ( v8 >= 0 )
      {
        v5 = 0;
        v29 = 0;
        goto LABEL_54;
      }
    }
  }
LABEL_11:
  ExFreePoolWithTag(P, 0);
  if ( v1 )
    ZwClose(v1);
  if ( v3 )
    ZwClose(v3);
  if ( v4 )
    ZwClose(v4);
  if ( v5 )
    ZwClose(v5);
  if ( v6 )
    ZwClose(v6);
  if ( v7 )
    ZwClose(v7);
LABEL_5:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 39, WPP_b370fe665b8033233cc44e642047166f_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140015c04  mov     [rsp-8+arg_0], rbx
0x140015c09  push    rbp
0x140015c0a  push    rsi
0x140015c0b  push    rdi
0x140015c0c  push    r12
0x140015c0e  push    r13
0x140015c10  push    r14
0x140015c12  push    r15
0x140015c14  lea     rbp, [rsp-27h]
0x140015c19  sub     rsp, 0B0h
0x140015c20  xor     esi, esi
0x140015c22  mov     rbx, rcx
0x140015c25  mov     [rbp+57h+arg_8], esi
0x140015c28  mov     r15d, esi
0x140015c2b  mov     [rbp+57h+arg_10], rsi
0x140015c2f  mov     r14d, esi
0x140015c32  mov     [rbp+57h+Handle], rsi
0x140015c36  mov     edi, esi
0x140015c38  mov     [rbp+57h+var_98], rsi
0x140015c3c  mov     r12d, esi
0x140015c3f  mov     [rbp+57h+var_A0], rsi
0x140015c43  mov     r13d, esi
0x140015c46  mov     [rbp+57h+var_A8], rsi
0x140015c4a  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140015c51  jnz     loc_140015D81
0x140015c57  lea     r9, UxLowPriorityPool
0x140015c5e  mov     [rsp+0E0h+Length], 1
0x140015c66  mov     edx, 220h
0x140015c6b  mov     ecx, 102h
0x140015c70  mov     r8d, 44526C55h
0x140015c76  call    cs:__imp_ExAllocatePool3
0x140015c7d  nop     dword ptr [rax+rax+00h]
0x140015c82  mov     [rbp+57h+P], rax
0x140015c86  test    rax, rax
0x140015c89  jnz     short loc_140015CBB
0x140015c8b  mov     ebx, 0C000009Ah
0x140015c90  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140015c97  jnz     loc_140015E00
0x140015c9d  mov     eax, ebx
0x140015c9f  mov     rbx, [rsp+0E0h+arg_0]
0x140015ca7  add     rsp, 0B0h
0x140015cae  pop     r15
0x140015cb0  pop     r14
0x140015cb2  pop     r13
0x140015cb4  pop     r12
0x140015cb6  pop     rdi
0x140015cb7  pop     rsi
0x140015cb8  pop     rbp
0x140015cb9  retn
0x140015cbb  lea     rax, aTlsrestriction; "TlsRestrictions"
0x140015cc2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140015cca  mov     [rbp+57h+var_78], rax
0x140015cce  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140015cd2  lea     rax, [rbp+57h+var_80]
0x140015cd6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140015cde  xorps   xmm0, xmm0
0x140015ce1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140015ce5  mov     edx, 20019h; DesiredAccess
0x140015cea  mov     [rbp+57h+var_80], 1E001Eh
0x140015cf2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140015cf6  mov     [rbp+57h+KeyHandle], rsi
0x140015cfa  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140015cfe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015d03  call    cs:__imp_ZwOpenKey
0x140015d0a  nop     dword ptr [rax+rax+00h]
0x140015d0f  mov     ebx, eax
0x140015d11  test    eax, eax
0x140015d13  jns     short loc_140015D72
0x140015d15  cmp     eax, 0C0000034h
0x140015d1a  jnz     short loc_140015D1E
0x140015d1c  mov     ebx, esi
0x140015d1e  mov     rcx, [rbp+57h+P]; P
0x140015d22  xor     edx, edx; Tag
0x140015d24  call    cs:__imp_ExFreePoolWithTag
0x140015d2b  nop     dword ptr [rax+rax+00h]
0x140015d30  test    rsi, rsi
0x140015d33  jnz     short loc_140015D9F
0x140015d35  test    r15, r15
0x140015d38  jnz     short loc_140015DB0
0x140015d3a  test    r14, r14
0x140015d3d  jnz     loc_140015DC4
0x140015d43  test    rdi, rdi
0x140015d46  jnz     loc_140015DD8
0x140015d4c  test    r12, r12
0x140015d4f  jnz     loc_140015DEC
0x140015d55  test    r13, r13
0x140015d58  jz      loc_140015C90
0x140015d5e  mov     rcx, r13; Handle
0x140015d61  call    cs:__imp_ZwClose
0x140015d68  nop     dword ptr [rax+rax+00h]
0x140015d6d  jmp     loc_140015C90
0x140015d72  mov     rsi, [rbp+57h+KeyHandle]
0x140015d76  xor     eax, eax
0x140015d78  mov     [rbp+57h+KeyHandle], rdi
0x140015d7c  jmp     loc_140171C5E
0x140015d81  mov     edx, 26h ; '&'
0x140015d86  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x140015d8d  mov     ecx, 411h
0x140015d92  mov     r9, rbx
0x140015d95  call    WPP_SF_q
0x140015d9a  jmp     loc_140015C57
0x140015d9f  mov     rcx, rsi; Handle
0x140015da2  call    cs:__imp_ZwClose
0x140015da9  nop     dword ptr [rax+rax+00h]
0x140015dae  jmp     short loc_140015D35
0x140015db0  mov     rcx, r15; Handle
0x140015db3  call    cs:__imp_ZwClose
0x140015dba  nop     dword ptr [rax+rax+00h]
0x140015dbf  jmp     loc_140015D3A
0x140015dc4  mov     rcx, r14; Handle
0x140015dc7  call    cs:__imp_ZwClose
0x140015dce  nop     dword ptr [rax+rax+00h]
0x140015dd3  jmp     loc_140015D43
0x140015dd8  mov     rcx, rdi; Handle
0x140015ddb  call    cs:__imp_ZwClose
0x140015de2  nop     dword ptr [rax+rax+00h]
0x140015de7  jmp     loc_140015D4C
0x140015dec  mov     rcx, r12; Handle
0x140015def  call    cs:__imp_ZwClose
0x140015df6  nop     dword ptr [rax+rax+00h]
0x140015dfb  jmp     loc_140015D55
0x140015e00  mov     edx, 27h ; '''
0x140015e05  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x140015e0c  mov     ecx, 411h
0x140015e11  mov     r9d, ebx
0x140015e14  call    WPP_SF_d
0x140015e19  jmp     loc_140015C9D
0x140171c5e  mov     [rbp+57h+arg_18], eax
0x140171c61  cmp     eax, 4
0x140171c64  jnb     loc_140171F71
0x140171c6a  mov     r9, [rbp+57h+P]; KeyInformation
0x140171c6e  lea     rax, [rbp+57h+arg_8]
0x140171c72  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140171c77  xor     r8d, r8d; KeyInformationClass
0x140171c7a  xor     edx, edx; Index
0x140171c7c  mov     [rsp+0E0h+Length], 220h; Length
0x140171c84  mov     rcx, rsi; KeyHandle
0x140171c87  call    cs:__imp_ZwEnumerateKey
0x140171c8e  nop     dword ptr [rax+rax+00h]
0x140171c93  mov     ebx, eax
0x140171c95  cmp     eax, 8000001Ah
0x140171c9a  jz      loc_140171F71
0x140171ca0  test    eax, eax
0x140171ca2  js      loc_140015D1E
0x140171ca8  mov     rax, [rbp+57h+P]
0x140171cac  lea     rdx, [rbp+57h+arg_10]
0x140171cb0  mov     [rsp+0E0h+ResultLength], rdx
0x140171cb5  mov     ebx, 20019h
0x140171cba  mov     r9d, ebx
0x140171cbd  mov     byte ptr [rsp+0E0h+Length], 0
0x140171cc2  movzx   r8d, word ptr [rax+0Ch]
0x140171cc7  lea     rcx, [rax+10h]
0x140171ccb  mov     [rbp+57h+var_70], rcx
0x140171ccf  mov     rdx, rcx
0x140171cd2  mov     rcx, rsi
0x140171cd5  call    UxOpenKey
0x140171cda  mov     r15, [rbp+57h+arg_10]
0x140171cde  cmp     eax, 0C0000034h
0x140171ce3  jz      loc_140171F5E
0x140171ce9  lea     rax, [rbp+57h+Handle]
0x140171ced  mov     r8d, 0Eh
0x140171cf3  mov     [rsp+0E0h+ResultLength], rax
0x140171cf8  lea     rdx, aAlpnids; "AlpnIds"
0x140171cff  mov     r9d, ebx
0x140171d02  mov     byte ptr [rsp+0E0h+Length], 0
0x140171d07  mov     rcx, r15
0x140171d0a  call    UxOpenKey
0x140171d0f  mov     r14, [rbp+57h+Handle]
0x140171d13  mov     ebx, eax
0x140171d15  cmp     eax, 0C0000034h
0x140171d1a  jz      short loc_140171D5D
0x140171d1c  test    eax, eax
0x140171d1e  js      loc_140015D1E
0x140171d24  mov     rcx, r14; KeyHandle
0x140171d27  call    cs:__imp_ZwDeleteKey
0x140171d2e  nop     dword ptr [rax+rax+00h]
0x140171d33  mov     ebx, eax
0x140171d35  test    eax, eax
0x140171d37  js      loc_140015D1E
0x140171d3d  mov     rcx, r14; Handle
0x140171d40  call    cs:__imp_ZwClose
0x140171d47  nop     dword ptr [rax+rax+00h]
0x140171d4c  mov     ebx, eax
0x140171d4e  test    eax, eax
0x140171d50  js      loc_140015D1E
0x140171d56  xor     r14d, r14d
0x140171d59  mov     [rbp+57h+Handle], r14
0x140171d5d  lea     rax, [rbp+57h+var_98]
0x140171d61  mov     r8d, 1Ch
0x140171d67  mov     [rsp+0E0h+ResultLength], rax
0x140171d6c  lea     rdx, aCryptosettings; "CryptoSettings"
0x140171d73  mov     r9d, 20019h
0x140171d79  mov     byte ptr [rsp+0E0h+Length], 0
0x140171d7e  mov     rcx, r15
0x140171d81  call    UxOpenKey
0x140171d86  mov     rdi, [rbp+57h+var_98]
0x140171d8a  mov     ebx, eax
0x140171d8c  cmp     eax, 0C0000034h
0x140171d91  jz      loc_140171F25
0x140171d97  test    eax, eax
0x140171d99  js      loc_140015D1E
0x140171d9f  xor     eax, eax
0x140171da1  mov     dword ptr [rbp+57h+arg_10], eax
0x140171da4  cmp     eax, 8
0x140171da7  jnb     loc_140171EED
0x140171dad  mov     r9, [rbp+57h+P]; KeyInformation
0x140171db1  lea     rax, [rbp+57h+arg_8]
0x140171db5  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140171dba  xor     r8d, r8d; KeyInformationClass
0x140171dbd  xor     edx, edx; Index
0x140171dbf  mov     [rsp+0E0h+Length], 220h; Length
0x140171dc7  mov     rcx, rdi; KeyHandle
0x140171dca  call    cs:__imp_ZwEnumerateKey
0x140171dd1  nop     dword ptr [rax+rax+00h]
0x140171dd6  mov     ebx, eax
0x140171dd8  cmp     eax, 8000001Ah
0x140171ddd  jz      loc_140171EED
0x140171de3  test    eax, eax
0x140171de5  js      loc_140015D1E
0x140171deb  mov     rdx, [rbp+57h+var_70]
0x140171def  lea     rax, [rbp+57h+var_A0]
0x140171df3  mov     [rsp+0E0h+ResultLength], rax
0x140171df8  mov     r12d, 20019h
0x140171dfe  mov     rax, [rbp+57h+P]
0x140171e02  mov     r9d, r12d
0x140171e05  mov     rcx, rdi
0x140171e08  mov     byte ptr [rsp+0E0h+Length], 0
0x140171e0d  movzx   r8d, word ptr [rax+0Ch]
0x140171e12  call    UxOpenKey
0x140171e17  mov     ebx, eax
0x140171e19  cmp     eax, 0C0000034h
0x140171e1e  jz      loc_140171EDF
0x140171e24  test    eax, eax
0x140171e26  js      loc_140171F68
0x140171e2c  mov     r9d, r12d
0x140171e2f  lea     rax, [rbp+57h+var_A8]
0x140171e33  mov     r12, [rbp+57h+var_A0]
0x140171e37  lea     rdx, aChainingmodes; "ChainingModes"
0x140171e3e  mov     [rsp+0E0h+ResultLength], rax
0x140171e43  mov     rcx, r12
0x140171e46  mov     r8d, 1Ah
0x140171e4c  mov     byte ptr [rsp+0E0h+Length], 0
0x140171e51  call    UxOpenKey
0x140171e56  mov     r13, [rbp+57h+var_A8]
0x140171e5a  mov     ebx, eax
0x140171e5c  cmp     eax, 0C0000034h
0x140171e61  jz      short loc_140171EA4
0x140171e63  test    eax, eax
0x140171e65  js      loc_140015D1E
0x140171e6b  mov     rcx, r13; KeyHandle
0x140171e6e  call    cs:__imp_ZwDeleteKey
0x140171e75  nop     dword ptr [rax+rax+00h]
0x140171e7a  mov     ebx, eax
0x140171e7c  test    eax, eax
0x140171e7e  js      loc_140015D1E
0x140171e84  mov     rcx, r13; Handle
0x140171e87  call    cs:__imp_ZwClose
0x140171e8e  nop     dword ptr [rax+rax+00h]
0x140171e93  mov     ebx, eax
0x140171e95  test    eax, eax
0x140171e97  js      loc_140015D1E
0x140171e9d  xor     r13d, r13d
0x140171ea0  mov     [rbp+57h+var_A8], r13
0x140171ea4  mov     rcx, r12; KeyHandle
0x140171ea7  call    cs:__imp_ZwDeleteKey
0x140171eae  nop     dword ptr [rax+rax+00h]
0x140171eb3  mov     ebx, eax
0x140171eb5  test    eax, eax
0x140171eb7  js      loc_140015D1E
0x140171ebd  mov     rcx, r12; Handle
0x140171ec0  call    cs:__imp_ZwClose
0x140171ec7  nop     dword ptr [rax+rax+00h]
0x140171ecc  mov     ebx, eax
0x140171ece  test    eax, eax
0x140171ed0  js      loc_140015D1E
0x140171ed6  xor     r12d, r12d
0x140171ed9  mov     [rbp+57h+var_A0], r12
0x140171edd  jmp     short loc_140171EE3
0x140171edf  mov     r12, [rbp+57h+var_A0]
0x140171ee3  mov     eax, dword ptr [rbp+57h+arg_10]
0x140171ee6  inc     eax
0x140171ee8  jmp     loc_140171DA1
0x140171eed  mov     rcx, rdi; KeyHandle
0x140171ef0  call    cs:__imp_ZwDeleteKey
0x140171ef7  nop     dword ptr [rax+rax+00h]
0x140171efc  mov     ebx, eax
0x140171efe  test    eax, eax
0x140171f00  js      loc_140015D1E
0x140171f06  mov     rcx, rdi; Handle
0x140171f09  call    cs:__imp_ZwClose
0x140171f10  nop     dword ptr [rax+rax+00h]
0x140171f15  mov     ebx, eax
0x140171f17  test    eax, eax
0x140171f19  js      loc_140015D1E
0x140171f1f  xor     edi, edi
0x140171f21  mov     [rbp+57h+var_98], rdi
0x140171f25  mov     rcx, r15; KeyHandle
0x140171f28  call    cs:__imp_ZwDeleteKey
0x140171f2f  nop     dword ptr [rax+rax+00h]
0x140171f34  mov     ebx, eax
  ... truncated ...
```
