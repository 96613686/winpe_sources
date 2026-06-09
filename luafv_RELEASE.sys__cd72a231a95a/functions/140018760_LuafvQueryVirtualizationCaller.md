# LuafvQueryVirtualizationCaller

- ea: `0x140018760`
- end: `0x140018925`
- name: `LuafvQueryVirtualizationCaller`
- size: `453`
- prototype: `__int64 __fastcall(__int64, char *, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018220`
- `0x1400186b0`
- `0x140025820`

## callees

- `0x140005bb0`
- `0x140018760`
- `0x14001892c`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1400187e4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400187e4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001884d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001884d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018865`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140018865`

## pseudocode

```c
__int64 __fastcall LuafvQueryVirtualizationCaller(__int64 a1, char *a2, _DWORD *a3)
{
  __int64 v3; // rbx
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

  v3 = *(_QWORD *)(a1 + 16);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  LODWORD(TokenInformation) = 0;
  if ( *(_BYTE *)(v3 + 4) )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v8 = 1;
  }
  else
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL) + 32LL);
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
    if ( *(_BYTE *)(a1 + 80) == 1 || (dword_14000EAD4 & 2) != 0 || (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 6LL) & 5) == 5 )
    {
      v12 = 1;
    }
    else
    {
      *a3 |= 1u;
      if ( (dword_14000EAD8 & 8) == 0 )
        goto LABEL_9;
    }
    if ( v10 != 1 && (dword_14000EAD4 & 4) == 0 )
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
0x140018760  push    rbx
0x140018762  push    rbp
0x140018763  push    rdi
0x140018764  push    r12
0x140018766  push    r15
0x140018768  sub     rsp, 110h
0x14001876f  mov     rax, cs:__security_cookie
0x140018776  xor     rax, rsp
0x140018779  mov     [rsp+138h+var_48], rax
0x140018781  mov     rbx, [rcx+10h]
0x140018785  xorps   xmm0, xmm0
0x140018788  xor     r12d, r12d
0x14001878b  mov     [rsp+138h+var_30], rsi
0x140018793  movups  xmmword ptr [rsp+138h+SubjectContext.ClientToken], xmm0
0x140018798  mov     dword ptr [rsp+138h+TokenInformation], r12d
0x14001879d  mov     r15, r8
0x1400187a0  movups  xmmword ptr [rsp+138h+SubjectContext.PrimaryToken], xmm0
0x1400187a5  mov     rdi, rdx
0x1400187a8  mov     rbp, rcx
0x1400187ab  cmp     [rbx+4], r12b
0x1400187af  jnz     loc_14001885B
0x1400187b5  mov     rbx, [rbx+18h]
0x1400187b9  mov     rbx, [rbx+8]
0x1400187bd  add     rbx, 20h ; ' '
0x1400187c1  xor     sil, sil
0x1400187c4  mov     rcx, [rbx]; Token
0x1400187c7  mov     [rsp+138h+var_38], r14
0x1400187cf  test    rcx, rcx
0x1400187d2  jz      short loc_14001883C
0x1400187d4  mov     r14d, 2
0x1400187da  lea     r8, [rsp+138h+TokenInformation]; TokenInformation
0x1400187df  mov     edx, 18h; TokenInformationClass
0x1400187e4  call    cs:__imp_SeQueryInformationToken
0x1400187eb  nop     dword ptr [rax+rax+00h]
0x1400187f0  test    sil, sil
0x1400187f3  mov     rsi, [rsp+138h+var_30]
0x1400187fb  mov     ebx, eax
0x1400187fd  jnz     short loc_140018848
0x1400187ff  test    ebx, ebx
0x140018801  js      loc_1400188A0
0x140018807  xor     dl, dl
0x140018809  cmp     dword ptr [rsp+138h+TokenInformation], r12d
0x14001880e  jnz     short loc_140018879
0x140018810  mov     [rdi], dl
0x140018812  mov     r14, [rsp+138h+var_38]
0x14001881a  mov     eax, ebx
0x14001881c  mov     rcx, [rsp+138h+var_48]
0x140018824  xor     rcx, rsp; StackCookie
0x140018827  call    __security_check_cookie
0x14001882c  add     rsp, 110h
0x140018833  pop     r15
0x140018835  pop     r12
0x140018837  pop     rdi
0x140018838  pop     rbp
0x140018839  pop     rbx
0x14001883a  retn
0x14001883c  mov     rcx, [rbx+10h]
0x140018840  mov     r14d, 1
0x140018846  jmp     short loc_1400187DA
0x140018848  lea     rcx, [rsp+138h+SubjectContext]; SubjectContext
0x14001884d  call    cs:__imp_SeReleaseSubjectContext
0x140018854  nop     dword ptr [rax+rax+00h]
0x140018859  jmp     short loc_1400187FF
0x14001885b  lea     rcx, [rsp+138h+SubjectContext]; SubjectContext
0x140018860  lea     rbx, [rsp+138h+SubjectContext]
0x140018865  call    cs:__imp_SeCaptureSubjectContext
0x14001886c  nop     dword ptr [rax+rax+00h]
0x140018871  mov     sil, 1
0x140018874  jmp     loc_1400187C4
0x140018879  cmp     byte ptr [rbp+50h], 1
0x14001887d  jnz     short loc_1400188F0
0x14001887f  mov     dl, 1
0x140018881  cmp     r14d, 1
0x140018885  jz      short loc_140018810
0x140018887  mov     eax, cs:dword_14000EAD4
0x14001888d  test    al, 4
0x14001888f  jnz     loc_140018810
0x140018895  xor     dl, dl
0x140018897  or      dword ptr [r15], 2
0x14001889b  jmp     loc_140018810
0x1400188a0  lea     rax, [rsp+138h+var_F0]
0x1400188a5  mov     [rsp+138h+UserDataCount], 8; UserDataCount
0x1400188ad  mov     [rsp+138h+var_58], rax
0x1400188b5  xor     r9d, r9d; int
0x1400188b8  lea     rax, [rsp+138h+var_C8]
0x1400188bd  mov     [rsp+138h+var_F0], ebx
0x1400188c1  mov     [rsp+138h+var_110], rax; PEVENT_DATA_DESCRIPTOR
0x1400188c6  xor     r8d, r8d; int
0x1400188c9  lea     rax, LuafvQueryVirtualizationFailed
0x1400188d0  mov     [rsp+138h+var_50], 4
0x1400188dc  xor     edx, edx; int
0x1400188de  mov     [rsp+138h+EventDescriptor], rax; EventDescriptor
0x1400188e3  mov     rcx, rbp; int
0x1400188e6  call    LuafvLogFileEvent
0x1400188eb  jmp     loc_140018812
0x1400188f0  mov     eax, cs:dword_14000EAD4
0x1400188f6  test    al, 2
0x1400188f8  jnz     short loc_14001887F
0x1400188fa  mov     rax, [rbp+10h]
0x1400188fe  movzx   ecx, byte ptr [rax+6]
0x140018902  and     cl, 5
0x140018905  cmp     cl, 5
0x140018908  jz      loc_14001887F
0x14001890e  or      dword ptr [r15], 1
0x140018912  mov     eax, cs:dword_14000EAD8
0x140018918  test    al, 8
0x14001891a  jz      loc_140018810
0x140018920  jmp     loc_140018881
```
