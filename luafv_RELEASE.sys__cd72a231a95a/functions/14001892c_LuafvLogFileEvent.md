# LuafvLogFileEvent

- ea: `0x14001892c`
- end: `0x140018c8f`
- name: `LuafvLogFileEvent`
- size: `867`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, __int64, int, PCEVENT_DESCRIPTOR EventDescriptor, PEVENT_DATA_DESCRIPTOR, ULONG UserDataCount)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400161c0`
- `0x140016238`
- `0x1400162cc`
- `0x1400181a4`
- `0x1400184e0`
- `0x1400185bc`
- `0x140018630`
- `0x140018760`
- `0x140020400`

## callees

- `0x14001892c`
- `0x140018c98`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140018b39`
- `ntoskrnl!EtwWrite` at `0x140018b39`
- `ntoskrnl!RtlLengthSid` at `0x140018a42`
- `ntoskrnl!RtlLengthSid` at `0x140018a42`
- `ntoskrnl!SeQueryInformationToken` at `0x1400189f6`
- `ntoskrnl!SeQueryInformationToken` at `0x1400189f6`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001899a`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001899a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140018c32`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140018c32`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018bd5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b70`
- `FLTMGR!FltGetRequestorProcess` at `0x14001897e`
- `FLTMGR!FltGetRequestorProcess` at `0x14001897e`

## pseudocode

```c
__int64 __fastcall LuafvLogFileEvent(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
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
  PWSTR Buffer; // rax
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
              FileName = *(UNICODE_STRING *)(a2 + 16);
            }
            else
            {
              FileName = v20->TargetFileObject->FileName;
              v21 = LuafvSupplyFullPath((__int64)a1, &FileName);
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
            Buffer = FileName.Buffer;
            *(_QWORD *)&UserData[3].Size = 2;
            UserData[4].Ptr = (ULONGLONG)Buffer;
            UserData[4].Size = FileName.Length;
            UserData[4].Reserved = 0;
            UserData[5].Ptr = (ULONGLONG)&v36;
            v29 = pImageFileName;
            *(_QWORD *)&UserData[5].Size = 2;
            LODWORD(v27) = v29->Length;
            UserData[6].Ptr = (ULONGLONG)v29->Buffer;
            UserData[6].Size = v27;
            UserData[6].Reserved = 0;
            v11 = EtwWrite(qword_14000EAE0, EventDescriptor, 0, v24, UserData);
            ExFreePoolWithTag(TokenInformation, 0);
            if ( v22 )
              LuafvFreePool(FileName.Buffer);
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
0x14001892c  mov     [rsp-28h+arg_0], rbx
0x140018931  mov     [rsp-28h+arg_8], rsi
0x140018936  mov     [rsp-28h+arg_18], r9d
0x14001893b  push    rbp
0x14001893c  push    rdi
0x14001893d  push    r12
0x14001893f  push    r14
0x140018941  push    r15
0x140018943  mov     rbp, rsp
0x140018946  sub     rsp, 80h
0x14001894d  xor     eax, eax
0x14001894f  mov     [rbp+pImageFileName], 0
0x140018957  xorps   xmm0, xmm0
0x14001895a  mov     [rbp+var_4C], ax
0x14001895e  movups  [rbp+var_30], xmm0
0x140018962  mov     [rbp+var_50], ax
0x140018966  mov     rdi, r8
0x140018969  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14001896d  mov     [rbp+TokenInformation], rax
0x140018971  mov     r12, rdx
0x140018974  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140018978  mov     [rbp+var_48], eax
0x14001897b  mov     rsi, rcx
0x14001897e  call    cs:__imp_FltGetRequestorProcess
0x140018985  nop     dword ptr [rax+rax+00h]
0x14001898a  test    rax, rax
0x14001898d  jz      loc_140018C24
0x140018993  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x140018997  mov     rcx, rax; Process
0x14001899a  call    cs:__imp_SeLocateProcessImageName
0x1400189a1  nop     dword ptr [rax+rax+00h]
0x1400189a6  mov     ebx, eax
0x1400189a8  test    eax, eax
0x1400189aa  js      loc_140018B7C
0x1400189b0  mov     rax, [rbp+pImageFileName]
0x1400189b4  movzx   ecx, word ptr [rax]
0x1400189b7  mov     rax, [rsi+10h]
0x1400189bb  shr     cx, 1
0x1400189be  mov     [rbp+var_4C], cx
0x1400189c2  cmp     byte ptr [rax+4], 0
0x1400189c6  jnz     loc_140018BCD
0x1400189cc  mov     rax, [rax+18h]
0x1400189d0  mov     rbx, [rax+8]
0x1400189d4  add     rbx, 20h ; ' '
0x1400189d8  xor     r14b, r14b
0x1400189db  mov     rcx, [rbx]; Token
0x1400189de  test    rcx, rcx
0x1400189e1  jz      loc_140018B9B
0x1400189e7  mov     r15d, 2
0x1400189ed  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400189f1  mov     edx, 1; TokenInformationClass
0x1400189f6  call    cs:__imp_SeQueryInformationToken
0x1400189fd  nop     dword ptr [rax+rax+00h]
0x140018a02  mov     ebx, eax
0x140018a04  test    r14b, r14b
0x140018a07  jnz     loc_140018C2E
0x140018a0d  mov     eax, [rbp+arg_18]
0x140018a10  mov     r14d, 4
0x140018a16  test    rdi, rdi
0x140018a19  jnz     loc_140018BFC
0x140018a1f  cmp     byte ptr [rsi+50h], 1
0x140018a23  jnz     loc_140018C63
0x140018a29  cmp     r15d, 1
0x140018a2d  jnz     loc_140018C6E
0x140018a33  test    ebx, ebx
0x140018a35  js      loc_140018B67
0x140018a3b  mov     rcx, [rbp+TokenInformation]
0x140018a3f  mov     rcx, [rcx]; Sid
0x140018a42  call    cs:__imp_RtlLengthSid
0x140018a49  nop     dword ptr [rax+rax+00h]
0x140018a4e  mov     [rbp+var_48], eax
0x140018a51  mov     r8d, eax
0x140018a54  test    rdi, rdi
0x140018a57  jnz     loc_140018BAA
0x140018a5d  mov     ecx, [rbp+arg_18]
0x140018a60  mov     rdx, [rsi+10h]
0x140018a64  test    [rdx+6], r14b
0x140018a68  jnz     loc_140018C84
0x140018a6e  test    r12, r12
0x140018a71  jnz     loc_140018BE9
0x140018a77  mov     rax, [rdx+8]
0x140018a7b  mov     rcx, rsi
0x140018a7e  lea     rdx, [rbp+var_30]
0x140018a82  movups  xmm0, xmmword ptr [rax+58h]
0x140018a86  movdqu  [rbp+var_30], xmm0
0x140018a8b  call    LuafvSupplyFullPath
0x140018a90  mov     r8d, [rbp+var_48]
0x140018a94  mov     dil, al
0x140018a97  mov     rdx, [rbp+arg_28]
0x140018a9b  lea     rax, [rbp+arg_18]
0x140018a9f  movzx   ecx, word ptr [rbp+var_30]
0x140018aa3  mov     r9d, [rbp+UserDataCount]; UserDataCount
0x140018aa7  shr     cx, 1
0x140018aaa  mov     [rdx], rax
0x140018aad  lea     rax, [rbp+var_48]
0x140018ab1  mov     [rdx+8], r14
0x140018ab5  mov     [rdx+10h], rax
0x140018ab9  mov     rax, [rbp+TokenInformation]
0x140018abd  mov     [rdx+18h], r14
0x140018ac1  mov     [rbp+var_50], cx
0x140018ac5  mov     [rsp+80h+UserData], rdx; UserData
0x140018aca  mov     rcx, [rax]
0x140018acd  lea     rax, [rbp+var_50]
0x140018ad1  mov     [rdx+28h], r8d
0x140018ad5  xor     r8d, r8d; ActivityId
0x140018ad8  mov     [rdx+20h], rcx
0x140018adc  mov     dword ptr [rdx+2Ch], 0
0x140018ae3  mov     [rdx+30h], rax
0x140018ae7  mov     rax, qword ptr [rbp+var_30+8]
0x140018aeb  mov     qword ptr [rdx+38h], 2
0x140018af3  mov     [rdx+40h], rax
0x140018af7  movzx   eax, word ptr [rbp+var_30]
0x140018afb  mov     [rdx+48h], eax
0x140018afe  lea     rax, [rbp+var_4C]
0x140018b02  mov     dword ptr [rdx+4Ch], 0
0x140018b09  mov     [rdx+50h], rax
0x140018b0d  mov     rax, [rbp+pImageFileName]
0x140018b11  mov     qword ptr [rdx+58h], 2
0x140018b19  movzx   ecx, word ptr [rax]
0x140018b1c  mov     rax, [rax+8]
0x140018b20  mov     [rdx+60h], rax
0x140018b24  mov     [rdx+68h], ecx
0x140018b27  mov     dword ptr [rdx+6Ch], 0
0x140018b2e  mov     rdx, [rbp+EventDescriptor]; EventDescriptor
0x140018b32  mov     rcx, cs:qword_14000EAE0; RegHandle
0x140018b39  call    cs:__imp_EtwWrite
0x140018b40  nop     dword ptr [rax+rax+00h]
0x140018b45  mov     rcx, [rbp+TokenInformation]; P
0x140018b49  xor     edx, edx; Tag
0x140018b4b  mov     ebx, eax
0x140018b4d  call    cs:__imp_ExFreePoolWithTag
0x140018b54  nop     dword ptr [rax+rax+00h]
0x140018b59  test    dil, dil
0x140018b5c  jz      short loc_140018B67
0x140018b5e  mov     rcx, qword ptr [rbp+var_30+8]
0x140018b62  call    LuafvFreePool
0x140018b67  mov     rcx, [rbp+pImageFileName]; P
0x140018b6b  mov     edx, 61506553h; Tag
0x140018b70  call    cs:__imp_ExFreePoolWithTag
0x140018b77  nop     dword ptr [rax+rax+00h]
0x140018b7c  mov     eax, ebx
0x140018b7e  lea     r11, [rsp+80h+var_s0]
0x140018b86  mov     rbx, [r11+30h]
0x140018b8a  mov     rsi, [r11+38h]
0x140018b8e  mov     rsp, r11
0x140018b91  pop     r15
0x140018b93  pop     r14
0x140018b95  pop     r12
0x140018b97  pop     rdi
0x140018b98  pop     rbp
0x140018b99  retn
0x140018b9b  mov     rcx, [rbx+10h]
0x140018b9f  mov     r15d, 1
0x140018ba5  jmp     loc_1400189ED
0x140018baa  mov     ecx, [rdi+28h]
0x140018bad  test    cl, 1
0x140018bb0  jnz     loc_140018C79
0x140018bb6  test    cl, 40h
0x140018bb9  jz      loc_140018A5D
0x140018bbf  mov     ecx, [rbp+arg_18]
0x140018bc2  or      ecx, 8
0x140018bc5  mov     [rbp+arg_18], ecx
0x140018bc8  jmp     loc_140018A60
0x140018bcd  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140018bd1  lea     rbx, [rbp+SubjectContext]
0x140018bd5  call    cs:__imp_SeCaptureSubjectContext
0x140018bdc  nop     dword ptr [rax+rax+00h]
0x140018be1  mov     r14b, 1
0x140018be4  jmp     loc_1400189DB
0x140018be9  movups  xmm0, xmmword ptr [r12+10h]
0x140018bef  xor     dil, dil
0x140018bf2  movdqu  [rbp+var_30], xmm0
0x140018bf7  jmp     loc_140018A97
0x140018bfc  mov     cl, [rdi+35h]
0x140018bff  test    cl, 1
0x140018c02  jnz     short loc_140018C43
0x140018c04  test    cl, 2
0x140018c07  jnz     short loc_140018C4B
0x140018c09  mov     dl, [rdi+34h]
0x140018c0c  test    dl, dl
0x140018c0e  js      short loc_140018C53
0x140018c10  test    r14b, cl
0x140018c13  jnz     short loc_140018C5B
0x140018c15  test    dl, 40h
0x140018c18  jz      loc_140018A33
0x140018c1e  bts     eax, 7
0x140018c22  jmp     short loc_140018C71
0x140018c24  mov     eax, 0C000071Ch
0x140018c29  jmp     loc_140018B7E
0x140018c2e  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140018c32  call    cs:__imp_SeReleaseSubjectContext
0x140018c39  nop     dword ptr [rax+rax+00h]
0x140018c3e  jmp     loc_140018A0D
0x140018c43  or      eax, 1
0x140018c46  mov     [rbp+arg_18], eax
0x140018c49  jmp     short loc_140018C04
0x140018c4b  or      eax, 2
0x140018c4e  mov     [rbp+arg_18], eax
0x140018c51  jmp     short loc_140018C09
0x140018c53  or      eax, 10h
0x140018c56  mov     [rbp+arg_18], eax
0x140018c59  jmp     short loc_140018C10
0x140018c5b  or      eax, 20h
0x140018c5e  mov     [rbp+arg_18], eax
0x140018c61  jmp     short loc_140018C15
0x140018c63  or      eax, 1
0x140018c66  mov     [rbp+arg_18], eax
0x140018c69  jmp     loc_140018A29
0x140018c6e  or      eax, 2
0x140018c71  mov     [rbp+arg_18], eax
0x140018c74  jmp     loc_140018A33
0x140018c79  mov     ecx, [rbp+arg_18]
0x140018c7c  or      ecx, r14d
0x140018c7f  jmp     loc_140018BC5
0x140018c84  or      ecx, 40h
0x140018c87  mov     [rbp+arg_18], ecx
0x140018c8a  jmp     loc_140018A6E
```
