# LuafvLogFileEvent

- ea: `0x14001897c`
- end: `0x140018cdf`
- name: `LuafvLogFileEvent`
- size: `867`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, UNICODE_STRING *, __int64, int, PCEVENT_DESCRIPTOR EventDescriptor, PEVENT_DATA_DESCRIPTOR, ULONG UserDataCount)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400161c0`
- `0x140016238`
- `0x1400162cc`
- `0x1400181f4`
- `0x140018530`
- `0x14001860c`
- `0x140018680`
- `0x1400187b0`
- `0x140020450`

## callees

- `0x14001897c`
- `0x140018ce8`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140018b89`
- `ntoskrnl!EtwWrite` at `0x140018b89`
- `ntoskrnl!RtlLengthSid` at `0x140018a92`
- `ntoskrnl!RtlLengthSid` at `0x140018a92`
- `ntoskrnl!SeQueryInformationToken` at `0x140018a46`
- `ntoskrnl!SeQueryInformationToken` at `0x140018a46`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400189ea`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400189ea`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140018c82`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140018c82`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018c25`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018c25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc0`
- `FLTMGR!FltGetRequestorProcess` at `0x1400189ce`
- `FLTMGR!FltGetRequestorProcess` at `0x1400189ce`

## pseudocode

```c
__int64 __fastcall LuafvLogFileEvent(
        struct _FLT_CALLBACK_DATA *a1,
        UNICODE_STRING *a2,
        __int64 a3,
        int a4,
        PCEVENT_DESCRIPTOR EventDescriptor,
        PEVENT_DATA_DESCRIPTOR a6,
        ULONG UserDataCount)
{
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS v11; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v14; // r14
  PACCESS_TOKEN ClientToken; // rcx
  int v16; // r15d
  int v17; // eax
  ULONG v18; // r8d
  int v19; // ecx
  PFLT_IO_PARAMETER_BLOCK v20; // rdx
  char v21; // al
  char v22; // di
  PEVENT_DATA_DESCRIPTOR UserData; // rdx
  ULONG v24; // r9d
  __int16 v25; // cx
  ULONGLONG *v26; // rax
  ULONGLONG v27; // rcx
  ULONGLONG Buffer; // rax
  PUNICODE_STRING v29; // rax
  int v31; // ecx
  char v32; // cl
  char v33; // dl
  int v34; // eax
  __int16 v35; // [rsp+30h] [rbp-50h] BYREF
  __int16 v36; // [rsp+34h] [rbp-4Ch] BYREF
  ULONG v37; // [rsp+38h] [rbp-48h] BYREF
  PVOID TokenInformation; // [rsp+40h] [rbp-40h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+48h] [rbp-38h] BYREF
  UNICODE_STRING FileName; // [rsp+50h] [rbp-30h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-20h] BYREF
  int v42; // [rsp+C8h] [rbp+48h] BYREF

  v42 = a4;
  pImageFileName = 0;
  v36 = 0;
  FileName = 0;
  v35 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformation = 0;
  v37 = 0;
  RequestorProcess = FltGetRequestorProcess(a1);
  if ( RequestorProcess )
  {
    v11 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
    if ( v11 < 0 )
      return (unsigned int)v11;
    Iopb = a1->Iopb;
    v36 = pImageFileName->Length >> 1;
    if ( Iopb->MajorFunction )
    {
      p_SubjectContext = &SubjectContext;
      SeCaptureSubjectContext(&SubjectContext);
      v14 = 1;
    }
    else
    {
      p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 32LL);
      v14 = 0;
    }
    ClientToken = p_SubjectContext->ClientToken;
    if ( p_SubjectContext->ClientToken )
    {
      v16 = 2;
    }
    else
    {
      ClientToken = p_SubjectContext->PrimaryToken;
      v16 = 1;
    }
    v11 = SeQueryInformationToken(ClientToken, TokenUser, &TokenInformation);
    if ( v14 )
      SeReleaseSubjectContext(&SubjectContext);
    v17 = v42;
    if ( a3 )
    {
      v32 = *(_BYTE *)(a3 + 53);
      if ( (v32 & 1) != 0 )
      {
        v17 = v42 | 1;
        v42 |= 1u;
      }
      if ( (v32 & 2) != 0 )
      {
        v17 |= 2u;
        v42 = v17;
      }
      v33 = *(_BYTE *)(a3 + 52);
      if ( v33 < 0 )
      {
        v17 |= 0x10u;
        v42 = v17;
      }
      if ( (v32 & 4) != 0 )
      {
        v17 |= 0x20u;
        v42 = v17;
      }
      if ( (v33 & 0x40) == 0 )
      {
LABEL_13:
        if ( v11 < 0 )
        {
LABEL_22:
          ExFreePoolWithTag(pImageFileName, 0x61506553u);
          return (unsigned int)v11;
        }
        v37 = RtlLengthSid(*(PSID *)TokenInformation);
        v18 = v37;
        if ( !a3 )
          goto LABEL_15;
        v31 = *(_DWORD *)(a3 + 40);
        if ( (v31 & 1) != 0 )
        {
          v19 = v42 | 4;
        }
        else
        {
          if ( (v31 & 0x40) == 0 )
          {
LABEL_15:
            v19 = v42;
LABEL_16:
            v20 = a1->Iopb;
            if ( (v20->OperationFlags & 4) != 0 )
              v42 = v19 | 0x40;
            if ( a2 )
            {
              v22 = 0;
              FileName = a2[1];
            }
            else
            {
              FileName = v20->TargetFileObject->FileName;
              v21 = LuafvSupplyFullPath(a1, &FileName, v37);
              v18 = v37;
              v22 = v21;
            }
            UserData = a6;
            v24 = UserDataCount;
            v25 = FileName.Length >> 1;
            a6->Ptr = (ULONGLONG)&v42;
            *(_QWORD *)&UserData->Size = 4;
            UserData[1].Ptr = (ULONGLONG)&v37;
            v26 = (ULONGLONG *)TokenInformation;
            *(_QWORD *)&UserData[1].Size = 4;
            v35 = v25;
            v27 = *v26;
            UserData[2].Size = v18;
            UserData[2].Ptr = v27;
            UserData[2].Reserved = 0;
            UserData[3].Ptr = (ULONGLONG)&v35;
            Buffer = (ULONGLONG)FileName.Buffer;
            *(_QWORD *)&UserData[3].Size = 2;
            UserData[4].Ptr = Buffer;
            UserData[4].Size = FileName.Length;
            UserData[4].Reserved = 0;
            UserData[5].Ptr = (ULONGLONG)&v36;
            v29 = pImageFileName;
            *(_QWORD *)&UserData[5].Size = 2;
            LODWORD(v27) = v29->Length;
            UserData[6].Ptr = (ULONGLONG)v29->Buffer;
            UserData[6].Size = v27;
            UserData[6].Reserved = 0;
            v11 = EtwWrite(qword_14000F120, EventDescriptor, 0, v24, UserData);
            ExFreePoolWithTag(TokenInformation, 0);
            if ( v22 )
              LuafvFreePool((__int64)FileName.Buffer);
            goto LABEL_22;
          }
          v19 = v42 | 8;
        }
        v42 = v19;
        goto LABEL_16;
      }
      v34 = v17 | 0x80;
    }
    else
    {
      if ( a1->RequestorMode != 1 )
      {
        v17 = v42 | 1;
        v42 |= 1u;
      }
      if ( v16 == 1 )
        goto LABEL_13;
      v34 = v17 | 2;
    }
    v42 = v34;
    goto LABEL_13;
  }
  return 3221227292LL;
}

```

## disassembly

```asm
0x14001897c  mov     [rsp-28h+arg_0], rbx
0x140018981  mov     [rsp-28h+arg_8], rsi
0x140018986  mov     [rsp-28h+arg_18], r9d
0x14001898b  push    rbp
0x14001898c  push    rdi
0x14001898d  push    r12
0x14001898f  push    r14
0x140018991  push    r15
0x140018993  mov     rbp, rsp
0x140018996  sub     rsp, 80h
0x14001899d  xor     eax, eax
0x14001899f  mov     [rbp+pImageFileName], 0
0x1400189a7  xorps   xmm0, xmm0
0x1400189aa  mov     [rbp+var_4C], ax
0x1400189ae  movups  [rbp+var_30], xmm0
0x1400189b2  mov     [rbp+var_50], ax
0x1400189b6  mov     rdi, r8
0x1400189b9  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x1400189bd  mov     [rbp+TokenInformation], rax
0x1400189c1  mov     r12, rdx
0x1400189c4  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x1400189c8  mov     [rbp+var_48], eax
0x1400189cb  mov     rsi, rcx
0x1400189ce  call    cs:__imp_FltGetRequestorProcess
0x1400189d5  nop     dword ptr [rax+rax+00h]
0x1400189da  test    rax, rax
0x1400189dd  jz      loc_140018C74
0x1400189e3  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x1400189e7  mov     rcx, rax; Process
0x1400189ea  call    cs:__imp_SeLocateProcessImageName
0x1400189f1  nop     dword ptr [rax+rax+00h]
0x1400189f6  mov     ebx, eax
0x1400189f8  test    eax, eax
0x1400189fa  js      loc_140018BCC
0x140018a00  mov     rax, [rbp+pImageFileName]
0x140018a04  movzx   ecx, word ptr [rax]
0x140018a07  mov     rax, [rsi+10h]
0x140018a0b  shr     cx, 1
0x140018a0e  mov     [rbp+var_4C], cx
0x140018a12  cmp     byte ptr [rax+4], 0
0x140018a16  jnz     loc_140018C1D
0x140018a1c  mov     rax, [rax+18h]
0x140018a20  mov     rbx, [rax+8]
0x140018a24  add     rbx, 20h ; ' '
0x140018a28  xor     r14b, r14b
0x140018a2b  mov     rcx, [rbx]; Token
0x140018a2e  test    rcx, rcx
0x140018a31  jz      loc_140018BEB
0x140018a37  mov     r15d, 2
0x140018a3d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140018a41  mov     edx, 1; TokenInformationClass
0x140018a46  call    cs:__imp_SeQueryInformationToken
0x140018a4d  nop     dword ptr [rax+rax+00h]
0x140018a52  mov     ebx, eax
0x140018a54  test    r14b, r14b
0x140018a57  jnz     loc_140018C7E
0x140018a5d  mov     eax, [rbp+arg_18]
0x140018a60  mov     r14d, 4
0x140018a66  test    rdi, rdi
0x140018a69  jnz     loc_140018C4C
0x140018a6f  cmp     byte ptr [rsi+50h], 1
0x140018a73  jnz     loc_140018CB3
0x140018a79  cmp     r15d, 1
0x140018a7d  jnz     loc_140018CBE
0x140018a83  test    ebx, ebx
0x140018a85  js      loc_140018BB7
0x140018a8b  mov     rcx, [rbp+TokenInformation]
0x140018a8f  mov     rcx, [rcx]; Sid
0x140018a92  call    cs:__imp_RtlLengthSid
0x140018a99  nop     dword ptr [rax+rax+00h]
0x140018a9e  mov     [rbp+var_48], eax
0x140018aa1  mov     r8d, eax
0x140018aa4  test    rdi, rdi
0x140018aa7  jnz     loc_140018BFA
0x140018aad  mov     ecx, [rbp+arg_18]
0x140018ab0  mov     rdx, [rsi+10h]
0x140018ab4  test    [rdx+6], r14b
0x140018ab8  jnz     loc_140018CD4
0x140018abe  test    r12, r12
0x140018ac1  jnz     loc_140018C39
0x140018ac7  mov     rax, [rdx+8]
0x140018acb  mov     rcx, rsi
0x140018ace  lea     rdx, [rbp+var_30]
0x140018ad2  movups  xmm0, xmmword ptr [rax+58h]
0x140018ad6  movdqu  [rbp+var_30], xmm0
0x140018adb  call    LuafvSupplyFullPath
0x140018ae0  mov     r8d, [rbp+var_48]
0x140018ae4  mov     dil, al
0x140018ae7  mov     rdx, [rbp+arg_28]
0x140018aeb  lea     rax, [rbp+arg_18]
0x140018aef  movzx   ecx, word ptr [rbp+var_30]
0x140018af3  mov     r9d, [rbp+UserDataCount]; UserDataCount
0x140018af7  shr     cx, 1
0x140018afa  mov     [rdx], rax
0x140018afd  lea     rax, [rbp+var_48]
0x140018b01  mov     [rdx+8], r14
0x140018b05  mov     [rdx+10h], rax
0x140018b09  mov     rax, [rbp+TokenInformation]
0x140018b0d  mov     [rdx+18h], r14
0x140018b11  mov     [rbp+var_50], cx
0x140018b15  mov     [rsp+80h+UserData], rdx; UserData
0x140018b1a  mov     rcx, [rax]
0x140018b1d  lea     rax, [rbp+var_50]
0x140018b21  mov     [rdx+28h], r8d
0x140018b25  xor     r8d, r8d; ActivityId
0x140018b28  mov     [rdx+20h], rcx
0x140018b2c  mov     dword ptr [rdx+2Ch], 0
0x140018b33  mov     [rdx+30h], rax
0x140018b37  mov     rax, qword ptr [rbp+var_30+8]
0x140018b3b  mov     qword ptr [rdx+38h], 2
0x140018b43  mov     [rdx+40h], rax
0x140018b47  movzx   eax, word ptr [rbp+var_30]
0x140018b4b  mov     [rdx+48h], eax
0x140018b4e  lea     rax, [rbp+var_4C]
0x140018b52  mov     dword ptr [rdx+4Ch], 0
0x140018b59  mov     [rdx+50h], rax
0x140018b5d  mov     rax, [rbp+pImageFileName]
0x140018b61  mov     qword ptr [rdx+58h], 2
0x140018b69  movzx   ecx, word ptr [rax]
0x140018b6c  mov     rax, [rax+8]
0x140018b70  mov     [rdx+60h], rax
0x140018b74  mov     [rdx+68h], ecx
0x140018b77  mov     dword ptr [rdx+6Ch], 0
0x140018b7e  mov     rdx, [rbp+EventDescriptor]; EventDescriptor
0x140018b82  mov     rcx, cs:qword_14000F120; RegHandle
0x140018b89  call    cs:__imp_EtwWrite
0x140018b90  nop     dword ptr [rax+rax+00h]
0x140018b95  mov     rcx, [rbp+TokenInformation]; P
0x140018b99  xor     edx, edx; Tag
0x140018b9b  mov     ebx, eax
0x140018b9d  call    cs:__imp_ExFreePoolWithTag
0x140018ba4  nop     dword ptr [rax+rax+00h]
0x140018ba9  test    dil, dil
0x140018bac  jz      short loc_140018BB7
0x140018bae  mov     rcx, qword ptr [rbp+var_30+8]
0x140018bb2  call    LuafvFreePool
0x140018bb7  mov     rcx, [rbp+pImageFileName]; P
0x140018bbb  mov     edx, 61506553h; Tag
0x140018bc0  call    cs:__imp_ExFreePoolWithTag
0x140018bc7  nop     dword ptr [rax+rax+00h]
0x140018bcc  mov     eax, ebx
0x140018bce  lea     r11, [rsp+80h+var_s0]
0x140018bd6  mov     rbx, [r11+30h]
0x140018bda  mov     rsi, [r11+38h]
0x140018bde  mov     rsp, r11
0x140018be1  pop     r15
0x140018be3  pop     r14
0x140018be5  pop     r12
0x140018be7  pop     rdi
0x140018be8  pop     rbp
0x140018be9  retn
0x140018beb  mov     rcx, [rbx+10h]
0x140018bef  mov     r15d, 1
0x140018bf5  jmp     loc_140018A3D
0x140018bfa  mov     ecx, [rdi+28h]
0x140018bfd  test    cl, 1
0x140018c00  jnz     loc_140018CC9
0x140018c06  test    cl, 40h
0x140018c09  jz      loc_140018AAD
0x140018c0f  mov     ecx, [rbp+arg_18]
0x140018c12  or      ecx, 8
0x140018c15  mov     [rbp+arg_18], ecx
0x140018c18  jmp     loc_140018AB0
0x140018c1d  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140018c21  lea     rbx, [rbp+SubjectContext]
0x140018c25  call    cs:__imp_SeCaptureSubjectContext
0x140018c2c  nop     dword ptr [rax+rax+00h]
0x140018c31  mov     r14b, 1
0x140018c34  jmp     loc_140018A2B
0x140018c39  movups  xmm0, xmmword ptr [r12+10h]
0x140018c3f  xor     dil, dil
0x140018c42  movdqu  [rbp+var_30], xmm0
0x140018c47  jmp     loc_140018AE7
0x140018c4c  mov     cl, [rdi+35h]
0x140018c4f  test    cl, 1
0x140018c52  jnz     short loc_140018C93
0x140018c54  test    cl, 2
0x140018c57  jnz     short loc_140018C9B
0x140018c59  mov     dl, [rdi+34h]
0x140018c5c  test    dl, dl
0x140018c5e  js      short loc_140018CA3
0x140018c60  test    r14b, cl
0x140018c63  jnz     short loc_140018CAB
0x140018c65  test    dl, 40h
0x140018c68  jz      loc_140018A83
0x140018c6e  bts     eax, 7
0x140018c72  jmp     short loc_140018CC1
0x140018c74  mov     eax, 0C000071Ch
0x140018c79  jmp     loc_140018BCE
0x140018c7e  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140018c82  call    cs:__imp_SeReleaseSubjectContext
0x140018c89  nop     dword ptr [rax+rax+00h]
0x140018c8e  jmp     loc_140018A5D
0x140018c93  or      eax, 1
0x140018c96  mov     [rbp+arg_18], eax
0x140018c99  jmp     short loc_140018C54
0x140018c9b  or      eax, 2
0x140018c9e  mov     [rbp+arg_18], eax
0x140018ca1  jmp     short loc_140018C59
0x140018ca3  or      eax, 10h
0x140018ca6  mov     [rbp+arg_18], eax
0x140018ca9  jmp     short loc_140018C60
0x140018cab  or      eax, 20h
0x140018cae  mov     [rbp+arg_18], eax
0x140018cb1  jmp     short loc_140018C65
0x140018cb3  or      eax, 1
0x140018cb6  mov     [rbp+arg_18], eax
0x140018cb9  jmp     loc_140018A79
0x140018cbe  or      eax, 2
0x140018cc1  mov     [rbp+arg_18], eax
0x140018cc4  jmp     loc_140018A83
0x140018cc9  mov     ecx, [rbp+arg_18]
0x140018ccc  or      ecx, r14d
0x140018ccf  jmp     loc_140018C15
0x140018cd4  or      ecx, 40h
0x140018cd7  mov     [rbp+arg_18], ecx
0x140018cda  jmp     loc_140018ABE
```
