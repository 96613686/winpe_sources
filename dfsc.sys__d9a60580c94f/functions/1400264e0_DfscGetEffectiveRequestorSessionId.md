# DfscGetEffectiveRequestorSessionId

- ea: `0x1400264e0`
- end: `0x140026606`
- name: `DfscGetEffectiveRequestorSessionId`
- size: `294`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000141c`
- `0x14001338c`
- `0x140017a64`

## callees

- `0x1400027f8`
- `0x1400042c8`
- `0x1400264e0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140026529`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140026529`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026586`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026586`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140026549`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140026549`

## pseudocode

```c
__int64 __fastcall DfscGetEffectiveRequestorSessionId(__int64 a1, ULONG *a2)
{
  __int64 v2; // r8
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  __int64 v6; // rdx
  NTSTATUS SessionIdToken; // edi
  __int64 v8; // r8
  __int64 v10; // rbx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 184);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( (!*(_BYTE *)v2 || *(_BYTE *)v2 == 1 || *(_BYTE *)v2 == 19) && (v10 = *(_QWORD *)(v2 + 8)) != 0 )
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v10 + 8) + 32LL);
  }
  else
  {
    SeCaptureSubjectContext(&SubjectContext);
    p_SubjectContext = &SubjectContext;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  SessionIdToken = SeQuerySessionIdToken(ClientToken, a2);
  if ( SessionIdToken < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        (unsigned int)SessionIdToken);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, v6, v8, *a2);
  }
  if ( p_SubjectContext == &SubjectContext )
    SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)SessionIdToken;
}

```

## disassembly

```asm
0x1400264e0  mov     [rsp+arg_0], rbx
0x1400264e5  mov     [rsp+arg_8], rsi
0x1400264ea  push    rdi
0x1400264eb  sub     rsp, 40h
0x1400264ef  mov     r8, [rcx+0B8h]
0x1400264f6  xorps   xmm0, xmm0
0x1400264f9  movups  xmmword ptr [rsp+48h+SubjectContext.ClientToken], xmm0
0x1400264fe  mov     rsi, rdx
0x140026501  movups  xmmword ptr [rsp+48h+SubjectContext.PrimaryToken], xmm0
0x140026506  movzx   eax, byte ptr [r8]
0x14002650a  test    eax, eax
0x14002650c  jz      loc_1400265A5
0x140026512  sub     eax, 1
0x140026515  jz      loc_1400265A5
0x14002651b  cmp     eax, 12h
0x14002651e  jz      loc_1400265A5
0x140026524  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140026529  call    cs:__imp_SeCaptureSubjectContext
0x140026530  nop     dword ptr [rax+rax+00h]
0x140026535  lea     rbx, [rsp+48h+SubjectContext]
0x14002653a  mov     rcx, [rbx]
0x14002653d  test    rcx, rcx
0x140026540  jnz     short loc_140026546
0x140026542  mov     rcx, [rbx+10h]; Token
0x140026546  mov     rdx, rsi; SessionId
0x140026549  call    cs:__imp_SeQuerySessionIdToken
0x140026550  nop     dword ptr [rax+rax+00h]
0x140026555  mov     edi, eax
0x140026557  test    eax, eax
0x140026559  js      short loc_1400265BF
0x14002655b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026562  lea     rax, WPP_GLOBAL_Control
0x140026569  cmp     rcx, rax
0x14002656c  jz      short loc_140026577
0x14002656e  test    dword ptr [rcx+2Ch], 400000h
0x140026575  jnz     short loc_1400265F5
0x140026577  lea     rax, [rsp+48h+SubjectContext]
0x14002657c  cmp     rbx, rax
0x14002657f  jnz     short loc_140026592
0x140026581  lea     rcx, [rsp+48h+SubjectContext]; SubjectContext
0x140026586  call    cs:__imp_SeReleaseSubjectContext
0x14002658d  nop     dword ptr [rax+rax+00h]
0x140026592  mov     rbx, [rsp+48h+arg_0]
0x140026597  mov     eax, edi
0x140026599  mov     rsi, [rsp+48h+arg_8]
0x14002659e  add     rsp, 40h
0x1400265a2  pop     rdi
0x1400265a3  retn
0x1400265a5  mov     rbx, [r8+8]
0x1400265a9  test    rbx, rbx
0x1400265ac  jz      loc_140026524
0x1400265b2  mov     rbx, [rbx+8]
0x1400265b6  add     rbx, 20h ; ' '
0x1400265ba  jmp     loc_14002653A
0x1400265bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265c6  lea     rax, WPP_GLOBAL_Control
0x1400265cd  cmp     rcx, rax
0x1400265d0  jz      short loc_140026577
0x1400265d2  test    dword ptr [rcx+2Ch], 100000h
0x1400265d9  jz      short loc_140026577
0x1400265db  mov     rcx, [rcx+18h]
0x1400265df  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400265e6  mov     edx, 23h ; '#'
0x1400265eb  mov     r9d, edi
0x1400265ee  call    WPP_SF_D
0x1400265f3  jmp     short loc_140026577
0x1400265f5  mov     r9d, [rsi]
0x1400265f8  mov     rcx, [rcx+18h]
0x1400265fc  call    WPP_SF_l
0x140026601  jmp     loc_140026577
```
