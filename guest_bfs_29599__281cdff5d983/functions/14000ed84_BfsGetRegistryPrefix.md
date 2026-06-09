# BfsGetRegistryPrefix

- ea: `0x14000ed84`
- end: `0x14000f0f9`
- name: `BfsGetRegistryPrefix`
- size: `885`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f304`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x140006eb0`
- `0x1400073e0`
- `0x1400092a4`
- `0x14000e9d8`
- `0x14000ed84`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000efbf`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000efbf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f0ae`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f0ae`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000efec`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000efec`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f007`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f007`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000f053`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000f053`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f06b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f083`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f06b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f083`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ee03`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ee60`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ee03`
- `ntoskrnl!SeQueryInformationToken` at `0x14000ee60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f0ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f0ba`

## pseudocode

```c
__int64 __fastcall BfsGetRegistryPrefix(PACCESS_TOKEN Token, _OWORD *a2, _OWORD *a3, int *a4)
{
  _WORD *v8; // rdi
  NTSTATUS v9; // eax
  int v10; // r8d
  int v11; // r9d
  NTSTATUS exists; // ebx
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int NotPresentPolicyEntryLocked; // eax
  PSID v18; // [rsp+20h] [rbp-E0h]
  NTSTATUS v19; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v20; // [rsp+48h] [rbp-B8h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+88h] [rbp-78h] BYREF
  NTSTATUS *v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  WCHAR SourceString[128]; // [rsp+C0h] [rbp-40h] BYREF

  P = 0;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  v23 = 256;
  v20 = 0;
  TokenInformation = 0;
  v8 = 0;
  UnicodeString = 0;
  v9 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  exists = v9;
  if ( v9 < 0 )
  {
    v13 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_28;
    v19 = v9;
    goto LABEL_4;
  }
  exists = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
  if ( exists < 0 )
  {
LABEL_6:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v19 = exists;
LABEL_4:
      v28 = 4;
      v27 = &v19;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, (int)v18, &v26);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  exists = BfsPolicyEntryExistsLocked(
             (int)gBfsFilterHandle,
             v14,
             (__int64)&gBfsPolicyTable,
             *(void **)TokenInformation,
             *(PSID *)P,
             *a4);
  if ( exists )
  {
    if ( exists != -1073741275 )
    {
      if ( exists < 0 )
        goto LABEL_6;
      goto LABEL_18;
    }
    NotPresentPolicyEntryLocked = BfsGetNotPresentPolicyEntryLocked(
                                    &gBfsPolicyTable,
                                    *(_QWORD *)TokenInformation,
                                    *(_QWORD *)P,
                                    &v20);
  }
  else
  {
    v18 = *(PSID *)P;
    NotPresentPolicyEntryLocked = BfsGetPolicyEntryLocked(
                                    gBfsFilterHandle,
                                    v15,
                                    &gBfsPolicyTable,
                                    *(_QWORD *)TokenInformation);
  }
  exists = NotPresentPolicyEntryLocked;
  if ( NotPresentPolicyEntryLocked < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v19 = NotPresentPolicyEntryLocked;
      v27 = &v19;
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, (int)v18, &v26);
    }
    v8 = v20;
    goto LABEL_28;
  }
  v8 = v20;
LABEL_18:
  if ( v8[56] && v8[64] )
    goto LABEL_27;
  if ( *a4 != 2 )
  {
    exists = -1073741267;
    goto LABEL_22;
  }
  exists = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)TokenInformation, 1u);
  if ( exists >= 0 )
  {
    LODWORD(v18) = 0;
    exists = RtlQueryPackageIdentity(Token, SourceString, &v23, 0);
    if ( exists >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      exists = BfsCalculateRegistryPrefix(&UnicodeString, &DestinationString, v8 + 56, v8 + 64);
      if ( exists >= 0 )
      {
LABEL_27:
        *a2 = *((_OWORD *)v8 + 7);
        *a3 = *((_OWORD *)v8 + 8);
        goto LABEL_28;
      }
    }
  }
LABEL_22:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v19 = exists;
    goto LABEL_4;
  }
LABEL_28:
  RtlFreeUnicodeString(&UnicodeString);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v8 )
  {
    if ( *a4 == 1 )
    {
      ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
      KeLeaveCriticalRegion();
      *a4 = 0;
    }
    BfsDereferencePolicyEntryEx(v8);
  }
  return (unsigned int)exists;
}

```

## disassembly

```asm
0x14000ed84  push    rbp
0x14000ed86  push    rbx
0x14000ed87  push    rsi
0x14000ed88  push    rdi
0x14000ed89  push    r12
0x14000ed8b  push    r13
0x14000ed8d  push    r14
0x14000ed8f  push    r15
0x14000ed91  lea     rbp, [rsp-0D8h]
0x14000ed99  sub     rsp, 1D8h
0x14000eda0  mov     rax, cs:__security_cookie
0x14000eda7  xor     rax, rsp
0x14000edaa  mov     [rbp+110h+var_50], rax
0x14000edb1  mov     r13, r8
0x14000edb4  mov     r12, rdx
0x14000edb7  mov     r15, rcx
0x14000edba  xorps   xmm0, xmm0
0x14000edbd  mov     ebx, 100h
0x14000edc2  lea     rcx, [rbp+110h+SourceString]; void *
0x14000edc6  xor     esi, esi
0x14000edc8  mov     r8d, ebx; Size
0x14000edcb  xor     edx, edx; Val
0x14000edcd  mov     [rsp+210h+P], rsi
0x14000edd2  mov     r14, r9
0x14000edd5  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x14000edda  call    memset
0x14000eddf  xorps   xmm0, xmm0
0x14000ede2  mov     [rsp+210h+var_1B0], rbx
0x14000ede7  lea     r8, [rsp+210h+TokenInformation]; TokenInformation
0x14000edec  mov     [rsp+210h+var_1C8], rsi
0x14000edf1  lea     edx, [rsi+1]; TokenInformationClass
0x14000edf4  mov     [rsp+210h+TokenInformation], rsi
0x14000edf9  mov     rcx, r15; Token
0x14000edfc  mov     edi, esi
0x14000edfe  movups  xmmword ptr [rsp+210h+UnicodeString.Length], xmm0
0x14000ee03  call    cs:__imp_SeQueryInformationToken
0x14000ee0a  nop     dword ptr [rax+rax+00h]
0x14000ee0f  mov     ebx, eax
0x14000ee11  test    eax, eax
0x14000ee13  jns     short loc_14000EE53
0x14000ee15  mov     ecx, cs:dword_140019000; int
0x14000ee1b  cmp     ecx, 3
0x14000ee1e  jbe     loc_14000F04E
0x14000ee24  mov     [rsp+210h+var_1D0], eax
0x14000ee28  lea     rax, [rsp+210h+var_1D0]
0x14000ee2d  mov     [rbp+110h+var_160], 4
0x14000ee35  mov     [rbp+110h+var_168], rax
0x14000ee39  lea     rdx, byte_140016D91; int
0x14000ee40  lea     rax, [rbp+110h+var_188]
0x14000ee44  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ee49  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ee4e  jmp     loc_14000F04E
0x14000ee53  lea     r8, [rsp+210h+P]; TokenInformation
0x14000ee58  mov     edx, 1Fh; TokenInformationClass
0x14000ee5d  mov     rcx, r15; Token
0x14000ee60  call    cs:__imp_SeQueryInformationToken
0x14000ee67  nop     dword ptr [rax+rax+00h]
0x14000ee6c  mov     ebx, eax
0x14000ee6e  test    eax, eax
0x14000ee70  jns     short loc_14000EE87
0x14000ee72  mov     eax, cs:dword_140019000
0x14000ee78  cmp     eax, 3
0x14000ee7b  jbe     loc_14000F04E
0x14000ee81  mov     [rsp+210h+var_1D0], ebx
0x14000ee85  jmp     short loc_14000EE28
0x14000ee87  mov     eax, [r14]
0x14000ee8a  lea     r8, gBfsPolicyTable
0x14000ee91  mov     r9, [rsp+210h+TokenInformation]
0x14000ee96  mov     dword ptr [rsp+210h+var_1E8], eax
0x14000ee9a  mov     rax, [rsp+210h+P]
0x14000ee9f  mov     r9, [r9]
0x14000eea2  mov     rcx, [rax]
0x14000eea5  mov     qword ptr [rsp+210h+var_1F0], rcx
0x14000eeaa  mov     rcx, cs:gBfsFilterHandle
0x14000eeb1  call    BfsPolicyEntryExistsLocked
0x14000eeb6  mov     ebx, eax
0x14000eeb8  test    eax, eax
0x14000eeba  jnz     short loc_14000EF38
0x14000eebc  mov     r9, [rsp+210h+TokenInformation]
0x14000eec1  lea     rax, [rsp+210h+var_1C8]
0x14000eec6  mov     [rsp+210h+var_1E0], rax
0x14000eecb  lea     r8, gBfsPolicyTable
0x14000eed2  mov     rax, [rsp+210h+P]
0x14000eed7  mov     [rsp+210h+var_1E8], r14
0x14000eedc  mov     r9, [r9]
0x14000eedf  mov     rcx, [rax]
0x14000eee2  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x14000eee7  mov     rcx, cs:gBfsFilterHandle
0x14000eeee  call    BfsGetPolicyEntryLocked
0x14000eef3  mov     ebx, eax
0x14000eef5  test    eax, eax
0x14000eef7  jns     short loc_14000EF63
0x14000eef9  mov     eax, cs:dword_140019000
0x14000eeff  cmp     eax, 3
0x14000ef02  jbe     short loc_14000EF2E
0x14000ef04  lea     rax, [rsp+210h+var_1D0]
0x14000ef09  mov     [rsp+210h+var_1D0], ebx
0x14000ef0d  mov     [rbp+110h+var_168], rax
0x14000ef11  lea     rdx, byte_140016D91; int
0x14000ef18  lea     rax, [rbp+110h+var_188]
0x14000ef1c  mov     [rbp+110h+var_160], 4
0x14000ef24  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ef29  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ef2e  mov     rdi, [rsp+210h+var_1C8]
0x14000ef33  jmp     loc_14000F04E
0x14000ef38  cmp     ebx, 0C0000225h
0x14000ef3e  jnz     short loc_14000EF6A
0x14000ef40  mov     r8, [rsp+210h+P]
0x14000ef45  lea     r9, [rsp+210h+var_1C8]
0x14000ef4a  mov     rdx, [rsp+210h+TokenInformation]
0x14000ef4f  lea     rcx, gBfsPolicyTable
0x14000ef56  mov     r8, [r8]
0x14000ef59  mov     rdx, [rdx]
0x14000ef5c  call    BfsGetNotPresentPolicyEntryLocked
0x14000ef61  jmp     short loc_14000EEF3
0x14000ef63  mov     rdi, [rsp+210h+var_1C8]
0x14000ef68  jmp     short loc_14000EF72
0x14000ef6a  test    ebx, ebx
0x14000ef6c  js      loc_14000EE72
0x14000ef72  lea     rsi, [rdi+70h]
0x14000ef76  xor     eax, eax
0x14000ef78  cmp     [rsi], ax
0x14000ef7b  jz      short loc_14000EF8A
0x14000ef7d  cmp     [rdi+80h], ax
0x14000ef84  jnz     loc_14000F036
0x14000ef8a  cmp     dword ptr [r14], 2
0x14000ef8e  jz      short loc_14000EFAF
0x14000ef90  mov     ebx, 0C000022Dh
0x14000ef95  mov     eax, cs:dword_140019000
0x14000ef9b  cmp     eax, 3
0x14000ef9e  jbe     loc_14000F04C
0x14000efa4  mov     [rsp+210h+var_1D0], ebx
0x14000efa8  xor     esi, esi
0x14000efaa  jmp     loc_14000EE28
0x14000efaf  mov     rdx, [rsp+210h+TokenInformation]
0x14000efb4  lea     rcx, [rsp+210h+UnicodeString]; UnicodeString
0x14000efb9  mov     r8b, 1; AllocateDestinationString
0x14000efbc  mov     rdx, [rdx]; Sid
0x14000efbf  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000efc6  nop     dword ptr [rax+rax+00h]
0x14000efcb  mov     ebx, eax
0x14000efcd  xor     eax, eax
0x14000efcf  test    ebx, ebx
0x14000efd1  js      short loc_14000EF95
0x14000efd3  mov     [rsp+210h+var_1E8], rax
0x14000efd8  lea     r8, [rsp+210h+var_1B0]
0x14000efdd  xor     r9d, r9d
0x14000efe0  mov     qword ptr [rsp+210h+var_1F0], rax
0x14000efe5  lea     rdx, [rbp+110h+SourceString]
0x14000efe9  mov     rcx, r15
0x14000efec  call    cs:__imp_RtlQueryPackageIdentity
0x14000eff3  nop     dword ptr [rax+rax+00h]
0x14000eff8  mov     ebx, eax
0x14000effa  test    eax, eax
0x14000effc  js      short loc_14000EF95
0x14000effe  lea     rdx, [rbp+110h+SourceString]; SourceString
0x14000f002  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x14000f007  call    cs:__imp_RtlInitUnicodeString
0x14000f00e  nop     dword ptr [rax+rax+00h]
0x14000f013  lea     r9, [rdi+80h]
0x14000f01a  mov     r8, rsi
0x14000f01d  lea     rdx, [rsp+210h+DestinationString]
0x14000f022  lea     rcx, [rsp+210h+UnicodeString]
0x14000f027  call    BfsCalculateRegistryPrefix
0x14000f02c  mov     ebx, eax
0x14000f02e  test    eax, eax
0x14000f030  js      loc_14000EF95
0x14000f036  movups  xmm0, xmmword ptr [rsi]
0x14000f039  movdqu  xmmword ptr [r12], xmm0
0x14000f03f  movups  xmm1, xmmword ptr [rdi+80h]
0x14000f046  movdqu  xmmword ptr [r13+0], xmm1
0x14000f04c  xor     esi, esi
0x14000f04e  lea     rcx, [rsp+210h+UnicodeString]; UnicodeString
0x14000f053  call    cs:__imp_RtlFreeUnicodeString
0x14000f05a  nop     dword ptr [rax+rax+00h]
0x14000f05f  mov     rcx, [rsp+210h+TokenInformation]; P
0x14000f064  test    rcx, rcx
0x14000f067  jz      short loc_14000F077
0x14000f069  xor     edx, edx; Tag
0x14000f06b  call    cs:__imp_ExFreePoolWithTag
0x14000f072  nop     dword ptr [rax+rax+00h]
0x14000f077  mov     rcx, [rsp+210h+P]; P
0x14000f07c  test    rcx, rcx
0x14000f07f  jz      short loc_14000F08F
0x14000f081  xor     edx, edx; Tag
0x14000f083  call    cs:__imp_ExFreePoolWithTag
0x14000f08a  nop     dword ptr [rax+rax+00h]
0x14000f08f  test    rdi, rdi
0x14000f092  jz      short loc_14000F0D3
0x14000f094  mov     eax, [r14]
0x14000f097  cmp     eax, 2
0x14000f09a  jnz     short loc_14000F0A0
0x14000f09c  mov     dl, 1
0x14000f09e  jmp     short loc_14000F0CB
0x14000f0a0  cmp     eax, 1
0x14000f0a3  jnz     short loc_14000F0C9
0x14000f0a5  xor     edx, edx
0x14000f0a7  lea     rcx, gBfsPolicyTable
0x14000f0ae  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f0b5  nop     dword ptr [rax+rax+00h]
0x14000f0ba  call    cs:__imp_KeLeaveCriticalRegion
0x14000f0c1  nop     dword ptr [rax+rax+00h]
0x14000f0c6  mov     [r14], esi
0x14000f0c9  xor     edx, edx
0x14000f0cb  mov     rcx, rdi; P
0x14000f0ce  call    BfsDereferencePolicyEntryEx
0x14000f0d3  mov     eax, ebx
0x14000f0d5  mov     rcx, [rbp+110h+var_50]
0x14000f0dc  xor     rcx, rsp; StackCookie
0x14000f0df  call    __security_check_cookie
0x14000f0e4  add     rsp, 1D8h
0x14000f0eb  pop     r15
0x14000f0ed  pop     r14
0x14000f0ef  pop     r13
0x14000f0f1  pop     r12
0x14000f0f3  pop     rdi
0x14000f0f4  pop     rsi
0x14000f0f5  pop     rbx
0x14000f0f6  pop     rbp
0x14000f0f7  retn
```
