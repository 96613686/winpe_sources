# IsSpoolerServiceProcess

- ea: `0x140008c78`
- end: `0x14000908b`
- name: `IsSpoolerServiceProcess`
- size: `1043`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000890c`

## callees

- `0x1400020b4`
- `0x1400020e4`
- `0x140002304`
- `0x140008810`
- `0x140008c78`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008d34`
- `ntoskrnl!ExAllocatePool2` at `0x140008dbd`
- `ntoskrnl!ExAllocatePool2` at `0x140008d34`
- `ntoskrnl!ExAllocatePool2` at `0x140008dbd`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000900a`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000900a`
- `ntoskrnl!SeQueryInformationToken` at `0x140008e34`
- `ntoskrnl!SeQueryInformationToken` at `0x140008f43`
- `ntoskrnl!SeQueryInformationToken` at `0x140008e34`
- `ntoskrnl!SeQueryInformationToken` at `0x140008f43`
- `ntoskrnl!IoGetCurrentProcess` at `0x140008cb4`
- `ntoskrnl!IoGetCurrentProcess` at `0x140008cb4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008d12`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008d12`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140008cc3`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140008cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ffb`
- `ntoskrnl!RtlEqualSid` at `0x140008ef2`
- `ntoskrnl!RtlEqualSid` at `0x140008f12`
- `ntoskrnl!RtlEqualSid` at `0x140008f69`
- `ntoskrnl!RtlEqualSid` at `0x140008ef2`
- `ntoskrnl!RtlEqualSid` at `0x140008f12`
- `ntoskrnl!RtlEqualSid` at `0x140008f69`

## pseudocode

```c
__int64 __fastcall IsSpoolerServiceProcess(_BYTE *a1)
{
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v4; // r13
  __int64 v5; // rdi
  void *Pool2; // rax
  __int64 v7; // r8
  void *v8; // r12
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // edi
  void *v12; // rax
  NTSTATUS v13; // eax
  unsigned int i; // r14d
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // [rsp+20h] [rbp-20h]
  __int64 v18; // [rsp+28h] [rbp-18h]
  unsigned __int64 v19; // [rsp+30h] [rbp-10h]
  PVOID TokenInformation; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF
  PSID Sid2; // [rsp+90h] [rbp+50h]

  TokenInformation = 0;
  P = 0;
  if ( !a1 )
    return 3221225485LL;
  *a1 = 0;
  CurrentProcess = IoGetCurrentProcess();
  v4 = PsReferencePrimaryToken(CurrentProcess);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
    return 3221225473LL;
  }
  v5 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(256, v5, 1114662002);
  Sid2 = Pool2;
  if ( !Pool2 )
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_13;
    v10 = 22;
LABEL_12:
    WPP_SF_L(v9->AttachedDevice, v10, v7, (unsigned int)v5, v17, v18, v19);
LABEL_13:
    v11 = -1073741670;
    goto LABEL_42;
  }
  v17 = 0xEB83221F00000050uLL;
  v18 = 0x546B16CF63A193E8LL;
  v19 = 0xEA46A3CAE04E4C2BuLL;
  InitializeServiceSid(Pool2);
  v12 = (void *)ExAllocatePool2(256, v5, 1114662002);
  v8 = v12;
  if ( !v12 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_13;
    v10 = 23;
    goto LABEL_12;
  }
  InitializeServiceSid(v12);
  v13 = SeQueryInformationToken(v4, TokenGroups, &TokenInformation);
  v11 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_decc11c9483a3275477ae1b226799886_Traceguids,
        (unsigned int)v13);
    goto LABEL_42;
  }
  if ( !TokenInformation )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
    v11 = -1073741823;
    goto LABEL_42;
  }
  for ( i = 0; i < *(_DWORD *)TokenInformation; ++i )
  {
    if ( (*((_DWORD *)TokenInformation + 4 * i + 4) & 4) != 0 )
    {
      if ( RtlEqualSid(*((PSID *)TokenInformation + 2 * i + 1), Sid2) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v16 = 26;
          goto LABEL_40;
        }
LABEL_41:
        *a1 = 1;
        goto LABEL_42;
      }
      if ( RtlEqualSid(*((PSID *)TokenInformation + 2 * i + 1), v8) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
        *a1 = 1;
        break;
      }
    }
  }
  if ( *a1 )
    goto LABEL_42;
  v11 = SeQueryInformationToken(v4, TokenPrimaryGroup, &P);
  if ( v11 < 0 )
    goto LABEL_42;
  if ( P )
  {
    if ( *(_QWORD *)P && RtlEqualSid(*(PSID *)P, v8) )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v16 = 28;
LABEL_40:
        WPP_SF_(v15->AttachedDevice, v16, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
      }
      goto LABEL_41;
    }
LABEL_42:
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x42706472u);
  if ( Sid2 )
    ExFreePoolWithTag(Sid2, 0x42706472u);
  PsDereferencePrimaryToken(v4);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140008c78  mov     [rsp-38h+arg_18], rbx
0x140008c7d  push    rbp
0x140008c7e  push    rsi
0x140008c7f  push    rdi
0x140008c80  push    r12
0x140008c82  push    r13
0x140008c84  push    r14
0x140008c86  push    r15
0x140008c88  mov     rbp, rsp
0x140008c8b  sub     rsp, 40h
0x140008c8f  mov     [rbp+TokenInformation], 0
0x140008c97  mov     rsi, rcx
0x140008c9a  mov     [rbp+P], 0
0x140008ca2  test    rcx, rcx
0x140008ca5  jnz     short loc_140008CB1
0x140008ca7  mov     eax, 0C000000Dh
0x140008cac  jmp     loc_140009018
0x140008cb1  mov     byte ptr [rcx], 0
0x140008cb4  call    cs:__imp_IoGetCurrentProcess
0x140008cbb  nop     dword ptr [rax+rax+00h]
0x140008cc0  mov     rcx, rax; Process
0x140008cc3  call    cs:__imp_PsReferencePrimaryToken
0x140008cca  nop     dword ptr [rax+rax+00h]
0x140008ccf  mov     r13, rax
0x140008cd2  test    rax, rax
0x140008cd5  jnz     short loc_140008D0D
0x140008cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140008cde  lea     rbx, WPP_GLOBAL_Control
0x140008ce5  cmp     rcx, rbx
0x140008ce8  jz      short loc_140008D03
0x140008cea  cmp     byte ptr [rcx+29h], 2
0x140008cee  jb      short loc_140008D03
0x140008cf0  mov     rcx, [rcx+18h]
0x140008cf4  lea     edx, [rax+15h]
0x140008cf7  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008cfe  call    WPP_SF_
0x140008d03  mov     eax, 0C0000001h
0x140008d08  jmp     loc_140009018
0x140008d0d  mov     ecx, 6; SubAuthorityCount
0x140008d12  call    cs:__imp_RtlLengthRequiredSid
0x140008d19  nop     dword ptr [rax+rax+00h]
0x140008d1e  mov     r15d, 42706472h
0x140008d24  mov     r14d, 100h
0x140008d2a  mov     r8d, r15d
0x140008d2d  mov     edx, eax
0x140008d2f  mov     ecx, r14d
0x140008d32  mov     edi, eax
0x140008d34  call    cs:__imp_ExAllocatePool2
0x140008d3b  nop     dword ptr [rax+rax+00h]
0x140008d40  mov     [rbp+Sid2], rax
0x140008d44  test    rax, rax
0x140008d47  jnz     short loc_140008D7E
0x140008d49  xor     r12d, r12d
0x140008d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d53  lea     rbx, WPP_GLOBAL_Control
0x140008d5a  cmp     rcx, rbx
0x140008d5d  jz      short loc_140008D74
0x140008d5f  cmp     byte ptr [rcx+29h], 2
0x140008d63  jb      short loc_140008D74
0x140008d65  lea     edx, [rax+16h]
0x140008d68  mov     rcx, [rcx+18h]
0x140008d6c  mov     r9d, edi
0x140008d6f  call    WPP_SF_L
0x140008d74  mov     edi, 0C000009Ah
0x140008d79  jmp     loc_140008FA3
0x140008d7e  lea     rdx, [rbp+var_20]
0x140008d82  mov     [rbp+var_20], 50h ; 'P'
0x140008d89  mov     rcx, rax; Sid
0x140008d8c  mov     [rbp+var_1C], 0EB83221Fh
0x140008d93  mov     [rbp+var_18], 63A193E8h
0x140008d9a  mov     [rbp+var_14], 546B16CFh
0x140008da1  mov     [rbp+var_10], 0E04E4C2Bh
0x140008da8  mov     [rbp+var_C], 0EA46A3CAh
0x140008daf  call    InitializeServiceSid
0x140008db4  mov     r8d, r15d
0x140008db7  mov     rdx, rdi
0x140008dba  mov     rcx, r14
0x140008dbd  call    cs:__imp_ExAllocatePool2
0x140008dc4  nop     dword ptr [rax+rax+00h]
0x140008dc9  mov     r12, rax
0x140008dcc  test    rax, rax
0x140008dcf  jnz     short loc_140008DF2
0x140008dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140008dd8  lea     rbx, WPP_GLOBAL_Control
0x140008ddf  cmp     rcx, rbx
0x140008de2  jz      short loc_140008D74
0x140008de4  cmp     byte ptr [rcx+29h], 2
0x140008de8  jb      short loc_140008D74
0x140008dea  lea     edx, [rax+17h]
0x140008ded  jmp     loc_140008D68
0x140008df2  lea     rdx, [rbp+var_20]
0x140008df6  mov     [rbp+var_20], 63h ; 'c'
0x140008dfd  mov     rcx, r12; Sid
0x140008e00  mov     [rbp+var_1C], 0CE5DBACh
0x140008e07  mov     [rbp+var_18], 76F17EC4h
0x140008e0e  mov     [rbp+var_14], 0E5F30EDBh
0x140008e15  mov     [rbp+var_10], 8F58C130h
0x140008e1c  mov     [rbp+var_C], 9C65577Dh
0x140008e23  call    InitializeServiceSid
0x140008e28  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140008e2c  mov     edx, 2; TokenInformationClass
0x140008e31  mov     rcx, r13; Token
0x140008e34  call    cs:__imp_SeQueryInformationToken
0x140008e3b  nop     dword ptr [rax+rax+00h]
0x140008e40  mov     edi, eax
0x140008e42  test    eax, eax
0x140008e44  jns     short loc_140008E84
0x140008e46  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e4d  lea     rbx, WPP_GLOBAL_Control
0x140008e54  cmp     rcx, rbx
0x140008e57  jz      loc_140008FA3
0x140008e5d  cmp     byte ptr [rcx+29h], 2
0x140008e61  jb      loc_140008FA3
0x140008e67  mov     rcx, [rcx+18h]
0x140008e6b  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008e72  mov     edx, 18h
0x140008e77  mov     r9d, eax
0x140008e7a  call    WPP_SF_D
0x140008e7f  jmp     loc_140008FA3
0x140008e84  cmp     [rbp+TokenInformation], 0
0x140008e89  jnz     short loc_140008EC3
0x140008e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e92  lea     rbx, WPP_GLOBAL_Control
0x140008e99  cmp     rcx, rbx
0x140008e9c  jz      short loc_140008EB9
0x140008e9e  cmp     byte ptr [rcx+29h], 2
0x140008ea2  jb      short loc_140008EB9
0x140008ea4  mov     rcx, [rcx+18h]
0x140008ea8  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008eaf  mov     edx, 19h
0x140008eb4  call    WPP_SF_
0x140008eb9  mov     edi, 0C0000001h
0x140008ebe  jmp     loc_140008FA3
0x140008ec3  mov     rax, [rbp+TokenInformation]
0x140008ec7  lea     rbx, WPP_GLOBAL_Control
0x140008ece  xor     r14d, r14d
0x140008ed1  cmp     [rax], r14d
0x140008ed4  jbe     short loc_140008F32
0x140008ed6  mov     rcx, [rbp+TokenInformation]
0x140008eda  mov     r15d, r14d
0x140008edd  add     r15, r15
0x140008ee0  mov     eax, [rcx+r15*8+10h]
0x140008ee5  test    al, 4
0x140008ee7  jz      short loc_140008F26
0x140008ee9  mov     rdx, [rbp+Sid2]; Sid2
0x140008eed  mov     rcx, [rcx+r15*8+8]; Sid1
0x140008ef2  call    cs:__imp_RtlEqualSid
0x140008ef9  nop     dword ptr [rax+rax+00h]
0x140008efe  test    al, al
0x140008f00  jnz     loc_140009060
0x140008f06  mov     rcx, [rbp+TokenInformation]
0x140008f0a  mov     rdx, r12; Sid2
0x140008f0d  mov     rcx, [rcx+r15*8+8]; Sid1
0x140008f12  call    cs:__imp_RtlEqualSid
0x140008f19  nop     dword ptr [rax+rax+00h]
0x140008f1e  test    al, al
0x140008f20  jnz     loc_140009031
0x140008f26  mov     rax, [rbp+TokenInformation]
0x140008f2a  inc     r14d
0x140008f2d  cmp     r14d, [rax]
0x140008f30  jb      short loc_140008ED6
0x140008f32  cmp     byte ptr [rsi], 0
0x140008f35  jnz     short loc_140008FA3
0x140008f37  lea     r8, [rbp+P]; TokenInformation
0x140008f3b  mov     edx, 5; TokenInformationClass
0x140008f40  mov     rcx, r13; Token
0x140008f43  call    cs:__imp_SeQueryInformationToken
0x140008f4a  nop     dword ptr [rax+rax+00h]
0x140008f4f  mov     edi, eax
0x140008f51  test    eax, eax
0x140008f53  js      short loc_140008FA3
0x140008f55  mov     rcx, [rbp+P]
0x140008f59  test    rcx, rcx
0x140008f5c  jz      short loc_140008FBA
0x140008f5e  mov     rcx, [rcx]; Sid1
0x140008f61  test    rcx, rcx
0x140008f64  jz      short loc_140008FA3
0x140008f66  mov     rdx, r12; Sid2
0x140008f69  call    cs:__imp_RtlEqualSid
0x140008f70  nop     dword ptr [rax+rax+00h]
0x140008f75  test    al, al
0x140008f77  jz      short loc_140008FA3
0x140008f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f80  cmp     rcx, rbx
0x140008f83  jz      short loc_140008FA0
0x140008f85  cmp     byte ptr [rcx+29h], 4
0x140008f89  jb      short loc_140008FA0
0x140008f8b  mov     edx, 1Ch
0x140008f90  mov     rcx, [rcx+18h]
0x140008f94  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008f9b  call    WPP_SF_
0x140008fa0  mov     byte ptr [rsi], 1
0x140008fa3  mov     rcx, [rbp+P]; P
0x140008fa7  test    rcx, rcx
0x140008faa  jz      short loc_140008FBA
0x140008fac  xor     edx, edx; Tag
0x140008fae  call    cs:__imp_ExFreePoolWithTag
0x140008fb5  nop     dword ptr [rax+rax+00h]
0x140008fba  mov     rcx, [rbp+TokenInformation]; P
0x140008fbe  test    rcx, rcx
0x140008fc1  jz      short loc_140008FD1
0x140008fc3  xor     edx, edx; Tag
0x140008fc5  call    cs:__imp_ExFreePoolWithTag
0x140008fcc  nop     dword ptr [rax+rax+00h]
0x140008fd1  test    r12, r12
0x140008fd4  jz      short loc_140008FEA
0x140008fd6  mov     edx, 42706472h; Tag
0x140008fdb  mov     rcx, r12; P
0x140008fde  call    cs:__imp_ExFreePoolWithTag
0x140008fe5  nop     dword ptr [rax+rax+00h]
0x140008fea  mov     rax, [rbp+Sid2]
0x140008fee  test    rax, rax
0x140008ff1  jz      short loc_140009007
0x140008ff3  mov     edx, 42706472h; Tag
0x140008ff8  mov     rcx, rax; P
0x140008ffb  call    cs:__imp_ExFreePoolWithTag
0x140009002  nop     dword ptr [rax+rax+00h]
0x140009007  mov     rcx, r13; PrimaryToken
0x14000900a  call    cs:__imp_PsDereferencePrimaryToken
0x140009011  nop     dword ptr [rax+rax+00h]
0x140009016  mov     eax, edi
0x140009018  mov     rbx, [rsp+40h+arg_18]
0x140009020  add     rsp, 40h
0x140009024  pop     r15
0x140009026  pop     r14
0x140009028  pop     r13
0x14000902a  pop     r12
0x14000902c  pop     rdi
0x14000902d  pop     rsi
0x14000902e  pop     rbp
0x14000902f  retn
0x140009031  mov     rcx, cs:WPP_GLOBAL_Control
0x140009038  cmp     rcx, rbx
0x14000903b  jz      short loc_140009058
0x14000903d  cmp     byte ptr [rcx+29h], 4
0x140009041  jb      short loc_140009058
0x140009043  mov     rcx, [rcx+18h]
0x140009047  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x14000904e  mov     edx, 1Bh
0x140009053  call    WPP_SF_
0x140009058  mov     byte ptr [rsi], 1
0x14000905b  jmp     loc_140008F32
0x140009060  mov     rcx, cs:WPP_GLOBAL_Control
0x140009067  lea     rbx, WPP_GLOBAL_Control
0x14000906e  cmp     rcx, rbx
0x140009071  jz      loc_140008FA0
0x140009077  cmp     byte ptr [rcx+29h], 4
0x14000907b  jb      loc_140008FA0
0x140009081  mov     edx, 1Ah
0x140009086  jmp     loc_140008F90
```
