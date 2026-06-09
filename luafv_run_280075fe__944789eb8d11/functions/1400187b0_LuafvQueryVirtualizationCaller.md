# LuafvQueryVirtualizationCaller

- ea: `0x1400187b0`
- end: `0x140018975`
- name: `LuafvQueryVirtualizationCaller`
- size: `453`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018270`
- `0x140018700`
- `0x1400258a0`

## callees

- `0x140005f30`
- `0x1400187b0`
- `0x14001897c`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140018834`
- `ntoskrnl!SeQueryInformationToken` at `0x140018834`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001889d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001889d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400188b5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400188b5`

## pseudocode

```c
__int64 __fastcall LuafvQueryVirtualizationCaller(struct _FLT_CALLBACK_DATA *a1, char *a2, _DWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v8; // si
  PACCESS_TOKEN ClientToken; // rcx
  int v10; // r14d
  NTSTATUS v11; // ebx
  char v12; // dl
  PVOID TokenInformation; // [rsp+40h] [rbp-F8h] BYREF
  NTSTATUS v15; // [rsp+48h] [rbp-F0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-E8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+70h] [rbp-C8h] BYREF
  NTSTATUS *v18; // [rsp+E0h] [rbp-58h]
  __int64 v19; // [rsp+E8h] [rbp-50h]

  Iopb = a1->Iopb;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  LODWORD(TokenInformation) = 0;
  if ( Iopb->MajorFunction )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v8 = 1;
  }
  else
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 32LL);
    v8 = 0;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( p_SubjectContext->ClientToken )
  {
    v10 = 2;
  }
  else
  {
    ClientToken = p_SubjectContext->PrimaryToken;
    v10 = 1;
  }
  v11 = SeQueryInformationToken(ClientToken, TokenVirtualizationEnabled, &TokenInformation);
  if ( v8 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v11 < 0 )
  {
    v18 = &v15;
    v15 = v11;
    v19 = 4;
    LuafvLogFileEvent(a1, 0, 0, 0, &LuafvQueryVirtualizationFailed, &v17, 8u);
    return (unsigned int)v11;
  }
  v12 = 0;
  if ( (_DWORD)TokenInformation )
  {
    if ( a1->RequestorMode == 1 || (dword_14000F114 & 2) != 0 || (a1->Iopb->OperationFlags & 5) == 5 )
    {
      v12 = 1;
    }
    else
    {
      *a3 |= 1u;
      if ( (dword_14000F118 & 8) == 0 )
        goto LABEL_9;
    }
    if ( v10 != 1 && (dword_14000F114 & 4) == 0 )
    {
      v12 = 0;
      *a3 |= 2u;
    }
  }
LABEL_9:
  *a2 = v12;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400187b0  push    rbx
0x1400187b2  push    rbp
0x1400187b3  push    rdi
0x1400187b4  push    r12
0x1400187b6  push    r15
0x1400187b8  sub     rsp, 110h
0x1400187bf  mov     rax, cs:__security_cookie
0x1400187c6  xor     rax, rsp
0x1400187c9  mov     [rsp+138h+var_48], rax
0x1400187d1  mov     rbx, [rcx+10h]
0x1400187d5  xorps   xmm0, xmm0
0x1400187d8  xor     r12d, r12d
0x1400187db  mov     [rsp+138h+var_30], rsi
0x1400187e3  movups  xmmword ptr [rsp+138h+SubjectContext.ClientToken], xmm0
0x1400187e8  mov     dword ptr [rsp+138h+TokenInformation], r12d
0x1400187ed  mov     r15, r8
0x1400187f0  movups  xmmword ptr [rsp+138h+SubjectContext.PrimaryToken], xmm0
0x1400187f5  mov     rdi, rdx
0x1400187f8  mov     rbp, rcx
0x1400187fb  cmp     [rbx+4], r12b
0x1400187ff  jnz     loc_1400188AB
0x140018805  mov     rbx, [rbx+18h]
0x140018809  mov     rbx, [rbx+8]
0x14001880d  add     rbx, 20h ; ' '
0x140018811  xor     sil, sil
0x140018814  mov     rcx, [rbx]; Token
0x140018817  mov     [rsp+138h+var_38], r14
0x14001881f  test    rcx, rcx
0x140018822  jz      short loc_14001888C
0x140018824  mov     r14d, 2
0x14001882a  lea     r8, [rsp+138h+TokenInformation]; TokenInformation
0x14001882f  mov     edx, 18h; TokenInformationClass
0x140018834  call    cs:__imp_SeQueryInformationToken
0x14001883b  nop     dword ptr [rax+rax+00h]
0x140018840  test    sil, sil
0x140018843  mov     rsi, [rsp+138h+var_30]
0x14001884b  mov     ebx, eax
0x14001884d  jnz     short loc_140018898
0x14001884f  test    ebx, ebx
0x140018851  js      loc_1400188F0
0x140018857  xor     dl, dl
0x140018859  cmp     dword ptr [rsp+138h+TokenInformation], r12d
0x14001885e  jnz     short loc_1400188C9
0x140018860  mov     [rdi], dl
0x140018862  mov     r14, [rsp+138h+var_38]
0x14001886a  mov     eax, ebx
0x14001886c  mov     rcx, [rsp+138h+var_48]
0x140018874  xor     rcx, rsp; StackCookie
0x140018877  call    __security_check_cookie
0x14001887c  add     rsp, 110h
0x140018883  pop     r15
0x140018885  pop     r12
0x140018887  pop     rdi
0x140018888  pop     rbp
0x140018889  pop     rbx
0x14001888a  retn
0x14001888c  mov     rcx, [rbx+10h]
0x140018890  mov     r14d, 1
0x140018896  jmp     short loc_14001882A
0x140018898  lea     rcx, [rsp+138h+SubjectContext]; SubjectContext
0x14001889d  call    cs:__imp_SeReleaseSubjectContext
0x1400188a4  nop     dword ptr [rax+rax+00h]
0x1400188a9  jmp     short loc_14001884F
0x1400188ab  lea     rcx, [rsp+138h+SubjectContext]; SubjectContext
0x1400188b0  lea     rbx, [rsp+138h+SubjectContext]
0x1400188b5  call    cs:__imp_SeCaptureSubjectContext
0x1400188bc  nop     dword ptr [rax+rax+00h]
0x1400188c1  mov     sil, 1
0x1400188c4  jmp     loc_140018814
0x1400188c9  cmp     byte ptr [rbp+50h], 1
0x1400188cd  jnz     short loc_140018940
0x1400188cf  mov     dl, 1
0x1400188d1  cmp     r14d, 1
0x1400188d5  jz      short loc_140018860
0x1400188d7  mov     eax, cs:dword_14000F114
0x1400188dd  test    al, 4
0x1400188df  jnz     loc_140018860
0x1400188e5  xor     dl, dl
0x1400188e7  or      dword ptr [r15], 2
0x1400188eb  jmp     loc_140018860
0x1400188f0  lea     rax, [rsp+138h+var_F0]
0x1400188f5  mov     [rsp+138h+UserDataCount], 8; UserDataCount
0x1400188fd  mov     [rsp+138h+var_58], rax
0x140018905  xor     r9d, r9d; int
0x140018908  lea     rax, [rsp+138h+var_C8]
0x14001890d  mov     [rsp+138h+var_F0], ebx
0x140018911  mov     [rsp+138h+var_110], rax; PEVENT_DATA_DESCRIPTOR
0x140018916  xor     r8d, r8d; int
0x140018919  lea     rax, LuafvQueryVirtualizationFailed
0x140018920  mov     [rsp+138h+var_50], 4
0x14001892c  xor     edx, edx; int
0x14001892e  mov     [rsp+138h+EventDescriptor], rax; EventDescriptor
0x140018933  mov     rcx, rbp; int
0x140018936  call    LuafvLogFileEvent
0x14001893b  jmp     loc_140018862
0x140018940  mov     eax, cs:dword_14000F114
0x140018946  test    al, 2
0x140018948  jnz     short loc_1400188CF
0x14001894a  mov     rax, [rbp+10h]
0x14001894e  movzx   ecx, byte ptr [rax+6]
0x140018952  and     cl, 5
0x140018955  cmp     cl, 5
0x140018958  jz      loc_1400188CF
0x14001895e  or      dword ptr [r15], 1
0x140018962  mov     eax, cs:dword_14000F118
0x140018968  test    al, 8
0x14001896a  jz      loc_140018860
0x140018970  jmp     loc_1400188D1
```
