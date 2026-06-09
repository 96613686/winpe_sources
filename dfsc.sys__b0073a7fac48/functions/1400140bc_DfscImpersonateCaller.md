# DfscImpersonateCaller

- ea: `0x1400140bc`
- end: `0x1400141f4`
- name: `DfscImpersonateCaller`
- size: `312`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001338c`
- `0x14002545c`

## callees

- `0x140005f70`
- `0x140006380`
- `0x1400140bc`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x1400141c0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400141c0`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140014150`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140014150`
- `ntoskrnl!IoThreadToProcess` at `0x14001413a`
- `ntoskrnl!IoThreadToProcess` at `0x14001413a`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14001417f`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14001417f`
- `ntoskrnl!SeImpersonateClientEx` at `0x140014197`
- `ntoskrnl!SeImpersonateClientEx` at `0x140014197`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400141b0`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400141b0`

## pseudocode

```c
__int64 __fastcall DfscImpersonateCaller(__int64 a1, _BYTE *a2)
{
  struct _KTHREAD *v4; // rcx
  struct _KTHREAD *v5; // rbx
  struct _KPROCESS *v6; // rax
  NTSTATUS v7; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-39h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+40h] [rbp-19h] BYREF
  _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+50h] [rbp-9h] BYREF

  memset(&ClientContext, 0, 0x44u);
  *a2 = 0;
  v4 = *(struct _KTHREAD **)(a1 + 152);
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( !v4 || v4 == KeGetCurrentThread() )
    return 0;
  v5 = *(struct _KTHREAD **)(a1 + 152);
  v6 = IoThreadToProcess(v4);
  SeCaptureSubjectContextEx(v5, v6, &SubjectContext);
  ClientSecurityQos.Length = 12;
  ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
  *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
  v7 = SeCreateClientSecurityFromSubjectContext(&SubjectContext, &ClientSecurityQos, 0, &ClientContext);
  if ( v7 >= 0 )
  {
    v7 = SeImpersonateClientEx(&ClientContext, 0);
    if ( v7 >= 0 )
      *a2 = 1;
    SeDeleteClientSecurity(&ClientContext);
  }
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400140bc  mov     [rsp-8+arg_10], rbx
0x1400140c1  mov     [rsp-8+arg_18], rdi
0x1400140c6  push    rbp
0x1400140c7  lea     rbp, [rsp-57h]
0x1400140cc  sub     rsp, 0B0h
0x1400140d3  mov     rax, cs:__security_cookie
0x1400140da  xor     rax, rsp
0x1400140dd  mov     [rbp+57h+var_10], rax
0x1400140e1  xor     eax, eax
0x1400140e3  mov     rdi, rdx
0x1400140e6  mov     rbx, rcx
0x1400140e9  mov     dword ptr [rbp+57h+ClientContext+0Ch], eax
0x1400140ec  xor     edx, edx; Val
0x1400140ee  lea     rcx, [rbp+57h+ClientContext]; void *
0x1400140f2  lea     r8d, [rax+44h]; Size
0x1400140f6  call    memset
0x1400140fb  xor     eax, eax
0x1400140fd  xorps   xmm0, xmm0
0x140014100  mov     [rdi], al
0x140014102  mov     rcx, [rbx+98h]; Thread
0x140014109  mov     qword ptr [rbp+57h+ClientSecurityQos.Length], rax
0x14001410d  mov     dword ptr [rbp+57h+ClientSecurityQos.ContextTrackingMode], eax
0x140014110  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140014114  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140014118  test    rcx, rcx
0x14001411b  jz      loc_1400141D0
0x140014121  mov     rax, gs:188h
0x14001412a  cmp     rcx, rax
0x14001412d  jz      loc_1400141D0
0x140014133  mov     rbx, [rbx+98h]
0x14001413a  call    cs:__imp_IoThreadToProcess
0x140014141  nop     dword ptr [rax+rax+00h]
0x140014146  lea     r8, [rbp+57h+SubjectContext]; SubjectContext
0x14001414a  mov     rcx, rbx; Thread
0x14001414d  mov     rdx, rax; Process
0x140014150  call    cs:__imp_SeCaptureSubjectContextEx
0x140014157  nop     dword ptr [rax+rax+00h]
0x14001415c  lea     r9, [rbp+57h+ClientContext]; ClientContext
0x140014160  mov     [rbp+57h+ClientSecurityQos.Length], 0Ch
0x140014167  xor     r8d, r8d; ServerIsRemote
0x14001416a  mov     [rbp+57h+ClientSecurityQos.ImpersonationLevel], 2
0x140014171  lea     rdx, [rbp+57h+ClientSecurityQos]; ClientSecurityQos
0x140014175  mov     word ptr [rbp+57h+ClientSecurityQos.ContextTrackingMode], 1
0x14001417b  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14001417f  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x140014186  nop     dword ptr [rax+rax+00h]
0x14001418b  mov     ebx, eax
0x14001418d  test    eax, eax
0x14001418f  js      short loc_1400141BC
0x140014191  xor     edx, edx; ServerThread
0x140014193  lea     rcx, [rbp+57h+ClientContext]; ClientContext
0x140014197  call    cs:__imp_SeImpersonateClientEx
0x14001419e  nop     dword ptr [rax+rax+00h]
0x1400141a3  mov     ebx, eax
0x1400141a5  test    eax, eax
0x1400141a7  js      short loc_1400141AC
0x1400141a9  mov     byte ptr [rdi], 1
0x1400141ac  lea     rcx, [rbp+57h+ClientContext]
0x1400141b0  call    cs:__imp_SeDeleteClientSecurity
0x1400141b7  nop     dword ptr [rax+rax+00h]
0x1400141bc  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400141c0  call    cs:__imp_SeReleaseSubjectContext
0x1400141c7  nop     dword ptr [rax+rax+00h]
0x1400141cc  mov     eax, ebx
0x1400141ce  jmp     short loc_1400141D2
0x1400141d0  xor     eax, eax
0x1400141d2  mov     rcx, [rbp+57h+var_10]
0x1400141d6  xor     rcx, rsp; StackCookie
0x1400141d9  call    __security_check_cookie
0x1400141de  lea     r11, [rsp+0B0h+var_s0]
0x1400141e6  mov     rbx, [r11+20h]
0x1400141ea  mov     rdi, [r11+28h]
0x1400141ee  mov     rsp, r11
0x1400141f1  pop     rbp
0x1400141f2  retn
```
