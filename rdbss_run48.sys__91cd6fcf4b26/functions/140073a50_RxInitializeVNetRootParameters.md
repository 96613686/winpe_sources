# RxInitializeVNetRootParameters

- ea: `0x140073a50`
- end: `0x140073cef`
- name: `RxInitializeVNetRootParameters`
- size: `671`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, LUID *LogonId, PULONG SessionId, PUNICODE_STRING *UserNamePtr, PUNICODE_STRING *UserDomainNamePtr, PUNICODE_STRING *PasswordPtr, PULONG Flags)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140078a90`
- `0x140078fe0`

## callees

- `0x140012820`
- `0x140016e20`
- `0x140017310`
- `0x140073a50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140073b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073c1f`
- `ntoskrnl!SeQueryInformationToken` at `0x140073abe`
- `ntoskrnl!SeQueryInformationToken` at `0x140073abe`
- `ntoskrnl!SeLockSubjectContext` at `0x140073a93`
- `ntoskrnl!SeLockSubjectContext` at `0x140073a93`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140073b17`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140073b77`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140073b17`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140073b77`
- `ntoskrnl!RtlCopySid` at `0x140073af5`
- `ntoskrnl!RtlCopySid` at `0x140073af5`

## pseudocode

```c
NTSTATUS __stdcall RxInitializeVNetRootParameters(
        PRX_CONTEXT RxContext,
        LUID *LogonId,
        PULONG SessionId,
        PUNICODE_STRING *UserNamePtr,
        PUNICODE_STRING *UserDomainNamePtr,
        PUNICODE_STRING *PasswordPtr,
        PULONG Flags)
{
  char RealDevice; // al
  __int64 v10; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v11; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  int v13; // ebp
  ULONG v14; // ecx
  PSZ FileName; // rcx
  int v16; // ebx
  char v17; // al
  PVOID TokenInformation; // [rsp+50h] [rbp+8h] BYREF

  RealDevice = (char)RxContext->RealDevice;
  if ( RealDevice )
  {
    if ( (RealDevice == 6 || RealDevice == 12 && BYTE1(RxContext->RealDevice) == 1)
      && *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) )
    {
      v11 = (struct _SECURITY_SUBJECT_CONTEXT *)((char *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 40);
      goto LABEL_4;
    }
LABEL_32:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, 3221225485LL);
    }
    v13 = -1073741811;
    v16 = 3702;
    goto LABEL_15;
  }
  v10 = *((_QWORD *)&RxContext->9 + 18);
  if ( !v10 )
    goto LABEL_32;
  v11 = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v10 + 8) + 32LL);
LABEL_4:
  SeLockSubjectContext(v11);
  ClientToken = v11->ClientToken;
  if ( !v11->ClientToken )
    ClientToken = v11->PrimaryToken;
  TokenInformation = 0;
  v13 = SeQueryInformationToken(ClientToken, TokenUser, &TokenInformation);
  if ( v13 >= 0 )
  {
    v14 = 4 * *(unsigned __int8 *)(*(_QWORD *)TokenInformation + 1LL) + 8;
    if ( v14 <= 0x44 )
    {
      RtlCopySid(v14, &LogonId[14], *(PSID *)TokenInformation);
      ExFreePoolWithTag(TokenInformation, 0);
      SeUnlockSubjectContext(v11);
      FileName = RxContext->TrackerHistory[6].FileName;
      v16 = 0;
      *(_OWORD *)&LogonId[9].LowPart = *(_OWORD *)&RxContext->TrackerHistory[5].AcquireRelease;
      *(_OWORD *)&LogonId[11].LowPart = *(_OWORD *)&RxContext->TrackerHistory[5].Flags;
      LogonId[13] = (LUID)RxContext->TrackerHistory[6].FileName;
      if ( FileName )
        RxReferenceCredential();
      v17 = BYTE5(RxContext->TrackerHistory[4].FileName);
      if ( (v17 & 8) != 0 && (v17 & 0x20) == 0 )
      {
        LogonId[23].LowPart = *((_DWORD *)RxContext->TrackerHistory[1].FileName + 2);
        LogonId[23].HighPart = *((_DWORD *)&RxContext->9 + 35) & 0xA;
      }
      LogonId[7].LowPart &= ~0x20u;
      goto LABEL_15;
    }
    v13 = -2147483643;
    ExFreePoolWithTag(TokenInformation, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids,
      (unsigned int)v13);
  }
  SeUnlockSubjectContext(v11);
  v16 = 3716;
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      (unsigned int)v13,
      v16);
  }
  return v13;
}

```

## disassembly

```asm
0x140073a50  push    rbx
0x140073a52  push    rbp
0x140073a53  sub     rsp, 38h
0x140073a57  movzx   eax, byte ptr [rcx+20h]
0x140073a5b  mov     [rsp+48h+arg_8], rsi
0x140073a60  mov     rsi, rdx
0x140073a63  mov     [rsp+48h+arg_10], rdi
0x140073a68  mov     rdi, rcx
0x140073a6b  mov     [rsp+48h+var_18], r14
0x140073a70  test    al, al
0x140073a72  jnz     loc_140073BDC
0x140073a78  mov     rbx, [rcx+220h]
0x140073a7f  test    rbx, rbx
0x140073a82  jz      loc_140073CA2
0x140073a88  mov     rbx, [rbx+8]
0x140073a8c  add     rbx, 20h ; ' '
0x140073a90  mov     rcx, rbx; SubjectContext
0x140073a93  call    cs:__imp_SeLockSubjectContext
0x140073a9a  nop     dword ptr [rax+rax+00h]
0x140073a9f  mov     rcx, [rbx]
0x140073aa2  test    rcx, rcx
0x140073aa5  jnz     short loc_140073AAB
0x140073aa7  mov     rcx, [rbx+10h]; Token
0x140073aab  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140073ab0  mov     [rsp+48h+TokenInformation], 0
0x140073ab9  mov     edx, 1; TokenInformationClass
0x140073abe  call    cs:__imp_SeQueryInformationToken
0x140073ac5  nop     dword ptr [rax+rax+00h]
0x140073aca  mov     ebp, eax
0x140073acc  test    eax, eax
0x140073ace  js      loc_140073C2B
0x140073ad4  mov     r9, [rsp+48h+TokenInformation]
0x140073ad9  mov     r8, [r9]; SourceSid
0x140073adc  movzx   eax, byte ptr [r8+1]
0x140073ae1  lea     ecx, ds:8[rax*4]; DestinationSidLength
0x140073ae8  cmp     ecx, 44h ; 'D'
0x140073aeb  ja      loc_140073C15
0x140073af1  lea     rdx, [rsi+70h]; DestinationSid
0x140073af5  call    cs:__imp_RtlCopySid
0x140073afc  nop     dword ptr [rax+rax+00h]
0x140073b01  mov     rcx, [rsp+48h+TokenInformation]; P
0x140073b06  xor     edx, edx; Tag
0x140073b08  call    cs:__imp_ExFreePoolWithTag
0x140073b0f  nop     dword ptr [rax+rax+00h]
0x140073b14  mov     rcx, rbx; SubjectContext
0x140073b17  call    cs:__imp_SeUnlockSubjectContext
0x140073b1e  nop     dword ptr [rax+rax+00h]
0x140073b23  lea     r14, WPP_GLOBAL_Control
0x140073b2a  movups  xmm0, xmmword ptr [rdi+2F8h]
0x140073b31  mov     rcx, [rdi+318h]
0x140073b38  xor     ebx, ebx
0x140073b3a  movups  xmmword ptr [rsi+48h], xmm0
0x140073b3e  movups  xmm1, xmmword ptr [rdi+308h]
0x140073b45  movups  xmmword ptr [rsi+58h], xmm1
0x140073b49  movsd   xmm0, qword ptr [rdi+318h]
0x140073b51  movsd   qword ptr [rsi+68h], xmm0
0x140073b56  test    rcx, rcx
0x140073b59  jnz     loc_140073C0B
0x140073b5f  movzx   eax, byte ptr [rdi+2EDh]
0x140073b66  test    al, 8
0x140073b68  jnz     loc_140073C76
0x140073b6e  and     dword ptr [rsi+38h], 0FFFFFFDFh
0x140073b72  jmp     short loc_140073B8C
0x140073b74  mov     rcx, rbx; SubjectContext
0x140073b77  call    cs:__imp_SeUnlockSubjectContext
0x140073b7e  nop     dword ptr [rax+rax+00h]
0x140073b83  test    ebp, ebp
0x140073b85  jns     short loc_140073B2A
0x140073b87  mov     ebx, 0E84h
0x140073b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b93  mov     rdi, [rsp+48h+arg_10]
0x140073b98  cmp     rcx, r14
0x140073b9b  mov     r14, [rsp+48h+var_18]
0x140073ba0  mov     rsi, [rsp+48h+arg_8]
0x140073ba5  jnz     short loc_140073BB1
0x140073ba7  mov     eax, ebp
0x140073ba9  add     rsp, 38h
0x140073bad  pop     rbp
0x140073bae  pop     rbx
0x140073baf  retn
0x140073bb1  mov     edx, [rcx+2Ch]
0x140073bb4  test    dl, dl
0x140073bb6  jns     short loc_140073BA7
0x140073bb8  cmp     byte ptr [rcx+29h], 2
0x140073bbc  jb      short loc_140073BA7
0x140073bbe  mov     rcx, [rcx+18h]
0x140073bc2  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140073bc9  mov     edx, 2Ch ; ','
0x140073bce  mov     [rsp+48h+var_28], ebx
0x140073bd2  mov     r9d, ebp
0x140073bd5  call    WPP_SF_Dd
0x140073bda  jmp     short loc_140073BA7
0x140073bdc  cmp     al, 6
0x140073bde  jz      short loc_140073BF2
0x140073be0  cmp     al, 0Ch
0x140073be2  jnz     loc_140073CA2
0x140073be8  cmp     byte ptr [rcx+21h], 1
0x140073bec  jnz     loc_140073CA2
0x140073bf2  cmp     byte ptr [rcx+1DEh], 0
0x140073bf9  jz      loc_140073CA2
0x140073bff  lea     rbx, [rcx+1E0h]
0x140073c06  jmp     loc_140073A90
0x140073c0b  call    RxReferenceCredential
0x140073c10  jmp     loc_140073B5F
0x140073c15  xor     edx, edx; Tag
0x140073c17  mov     rcx, r9; P
0x140073c1a  mov     ebp, 80000005h
0x140073c1f  call    cs:__imp_ExFreePoolWithTag
0x140073c26  nop     dword ptr [rax+rax+00h]
0x140073c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073c32  lea     r14, WPP_GLOBAL_Control
0x140073c39  cmp     rcx, r14
0x140073c3c  jz      loc_140073B74
0x140073c42  test    dword ptr [rcx+2Ch], 1000h
0x140073c49  jz      loc_140073B74
0x140073c4f  cmp     byte ptr [rcx+29h], 2
0x140073c53  jb      loc_140073B74
0x140073c59  mov     rcx, [rcx+18h]
0x140073c5d  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x140073c64  mov     edx, 10h
0x140073c69  mov     r9d, ebp
0x140073c6c  call    WPP_SF_d
0x140073c71  jmp     loc_140073B74
0x140073c76  test    al, 20h
0x140073c78  jnz     loc_140073B6E
0x140073c7e  mov     rax, [rdi+2A0h]
0x140073c85  mov     ecx, [rax+8]
0x140073c88  mov     [rsi+0B8h], ecx
0x140073c8e  mov     eax, [rdi+21Ch]
0x140073c94  and     eax, 0Ah
0x140073c97  mov     [rsi+0BCh], eax
0x140073c9d  jmp     loc_140073B6E
0x140073ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ca9  lea     r14, WPP_GLOBAL_Control
0x140073cb0  cmp     rcx, r14
0x140073cb3  jz      loc_14007F8E0
0x140073cb9  mov     eax, [rcx+2Ch]
0x140073cbc  test    al, 1
0x140073cbe  jz      loc_14007F8E0
0x140073cc4  cmp     byte ptr [rcx+29h], 1
0x140073cc8  jb      loc_14007F8E0
0x140073cce  mov     rcx, [rcx+18h]
0x140073cd2  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x140073cd9  mov     edx, 11h
0x140073cde  mov     r9d, 0C000000Dh
0x140073ce4  call    WPP_SF_d
0x140073ce9  nop
0x140073cea  jmp     loc_14007F8E0
0x14007f8e0  mov     ebp, 0C000000Dh
0x14007f8e5  mov     ebx, 0E76h
0x14007f8ea  jmp     loc_140073B8C
```
