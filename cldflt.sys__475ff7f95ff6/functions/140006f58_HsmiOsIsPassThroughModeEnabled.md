# HsmiOsIsPassThroughModeEnabled

- ea: `0x140006f58`
- end: `0x1400071a3`
- name: `HsmiOsIsPassThroughModeEnabled`
- size: `587`
- prototype: `char __fastcall(struct _KPROCESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006f40`

## callees

- `0x140006f58`
- `0x1400071b0`
- `0x14001e1c0`
- `0x140037154`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x140006fbd`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140006fd1`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000708a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140006fbd`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140006fd1`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000708a`
- `ntoskrnl!PsGetProcessPeb` at `0x140007050`
- `ntoskrnl!PsGetProcessPeb` at `0x140007064`
- `ntoskrnl!PsGetProcessPeb` at `0x1400070be`
- `ntoskrnl!PsGetProcessPeb` at `0x140007050`
- `ntoskrnl!PsGetProcessPeb` at `0x140007064`
- `ntoskrnl!PsGetProcessPeb` at `0x1400070be`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000717c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000717c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000707b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000709b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400070af`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400070cf`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000707b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000709b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400070af`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400070cf`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140007162`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140007162`
- `ntoskrnl!SeLockSubjectContext` at `0x140007111`
- `ntoskrnl!SeLockSubjectContext` at `0x140007111`
- `ntoskrnl!SePrivilegeCheck` at `0x140007146`
- `ntoskrnl!SePrivilegeCheck` at `0x140007146`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140007192`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140007192`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400070fd`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400070fd`

## pseudocode

```c
char __fastcall HsmiOsIsPassThroughModeEnabled(struct _KPROCESS *a1)
{
  __int64 v2; // rcx
  char v3; // si
  __int64 ProcessWow64Process; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  char v7; // bl
  char v8; // di
  __int64 v10; // rcx
  __int64 CurrentProcess; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+28h] [rbp-80h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+48h] [rbp-60h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+78h] [rbp-30h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v3 = HsmiOsStackAttachProcess(a1, &ApcState);
  if ( !a1 )
  {
    CurrentProcess = PsGetCurrentProcess(v2);
    if ( PsGetProcessWow64Process(CurrentProcess) )
    {
      v5 = PsGetCurrentProcess(v12);
      goto LABEL_3;
    }
    v13 = PsGetCurrentProcess(v12);
    if ( PsGetProcessPeb(v13) )
    {
      v10 = PsGetCurrentProcess(v14);
      goto LABEL_17;
    }
LABEL_22:
    v6 = 0;
    goto LABEL_4;
  }
  ProcessWow64Process = PsGetProcessWow64Process(a1);
  v5 = (__int64)a1;
  if ( !ProcessWow64Process )
  {
    if ( PsGetProcessPeb(a1) )
    {
      v10 = (__int64)a1;
LABEL_17:
      v6 = PsGetProcessPeb(v10) + 1960;
      goto LABEL_4;
    }
    goto LABEL_22;
  }
LABEL_3:
  v6 = PsGetProcessWow64Process(v5) + 1120;
LABEL_4:
  v7 = v6 && (RtlReadULongFromUser(v6) & 0x100) != 0;
  v8 = 0;
  if ( v7 )
  {
    memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
    SeCaptureSubjectContext(&SubjectContext);
    v8 = 1;
    SeLockSubjectContext(&SubjectContext);
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    v7 = SePrivilegeCheck(&RequiredPrivileges, &SubjectContext, 1) != 0 ? v7 : 0;
  }
  if ( v8 )
  {
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
  }
  if ( v3 )
    KeUnstackDetachProcess(&ApcState);
  return v7;
}

```

## disassembly

```asm
0x140006f58  mov     [rsp+arg_8], rbx
0x140006f5d  mov     [rsp+arg_10], rsi
0x140006f62  push    rdi
0x140006f63  sub     rsp, 0A0h
0x140006f6a  mov     rax, cs:__security_cookie
0x140006f71  xor     rax, rsp
0x140006f74  mov     [rsp+0A8h+var_18], rax
0x140006f7c  mov     rbx, rcx
0x140006f7f  xorps   xmm0, xmm0
0x140006f82  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink], xmm0
0x140006f87  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink+10h], xmm0
0x140006f8c  movups  xmmword ptr [rsp+0A8h+ApcState.Process], xmm0
0x140006f91  movups  xmmword ptr [rsp+0A8h+SubjectContext.ClientToken], xmm0
0x140006f96  movups  xmmword ptr [rsp+0A8h+SubjectContext.PrimaryToken], xmm0
0x140006f9b  mov     [rsp+0A8h+var_88], 0
0x140006fa0  lea     rdx, [rsp+0A8h+ApcState]; ApcState
0x140006fa5  call    HsmiOsStackAttachProcess
0x140006faa  mov     sil, al
0x140006fad  mov     [rsp+0A8h+var_87], al
0x140006fb1  test    rbx, rbx
0x140006fb4  jz      loc_14000707B
0x140006fba  mov     rcx, rbx
0x140006fbd  call    cs:__imp_PsGetProcessWow64Process
0x140006fc4  nop     dword ptr [rax+rax+00h]
0x140006fc9  mov     rcx, rbx
0x140006fcc  test    rax, rax
0x140006fcf  jz      short loc_140007050
0x140006fd1  call    cs:__imp_PsGetProcessWow64Process
0x140006fd8  nop     dword ptr [rax+rax+00h]
0x140006fdd  add     rax, 460h
0x140006fe3  test    rax, rax
0x140006fe6  jnz     short loc_140006FEC
0x140006fe8  xor     bl, bl
0x140006fea  jmp     short loc_140006FFC
0x140006fec  mov     rcx, rax
0x140006fef  call    RtlReadULongFromUser
0x140006ff4  bt      eax, 8
0x140006ff8  jnb     short loc_140006FE8
0x140006ffa  mov     bl, 1
0x140006ffc  mov     [rsp+0A8h+var_88], bl
0x140007000  jmp     short loc_14000700B
0x140007002  mov     bl, [rsp+0A8h+var_88]
0x140007006  mov     sil, [rsp+0A8h+var_87]
0x14000700b  xor     dil, dil
0x14000700e  test    bl, bl
0x140007010  jnz     loc_1400070E7
0x140007016  test    dil, dil
0x140007019  jnz     loc_14000715D
0x14000701f  test    sil, sil
0x140007022  jnz     loc_14000718D
0x140007028  mov     al, bl
0x14000702a  mov     rcx, [rsp+0A8h+var_18]
0x140007032  xor     rcx, rsp; StackCookie
0x140007035  call    __security_check_cookie
0x14000703a  lea     r11, [rsp+0A8h+var_8]
0x140007042  mov     rbx, [r11+18h]
0x140007046  mov     rsi, [r11+20h]
0x14000704a  mov     rsp, r11
0x14000704d  pop     rdi
0x14000704e  retn
0x140007050  call    cs:__imp_PsGetProcessPeb
0x140007057  nop     dword ptr [rax+rax+00h]
0x14000705c  test    rax, rax
0x14000705f  jz      short loc_1400070E0
0x140007061  mov     rcx, rbx
0x140007064  call    cs:__imp_PsGetProcessPeb
0x14000706b  nop     dword ptr [rax+rax+00h]
0x140007070  add     rax, 7A8h
0x140007076  jmp     loc_140006FE3
0x14000707b  call    cs:__imp_PsGetCurrentProcess
0x140007082  nop     dword ptr [rax+rax+00h]
0x140007087  mov     rcx, rax
0x14000708a  call    cs:__imp_PsGetProcessWow64Process
0x140007091  nop     dword ptr [rax+rax+00h]
0x140007096  test    rax, rax
0x140007099  jz      short loc_1400070AF
0x14000709b  call    cs:__imp_PsGetCurrentProcess
0x1400070a2  nop     dword ptr [rax+rax+00h]
0x1400070a7  mov     rcx, rax
0x1400070aa  jmp     loc_140006FD1
0x1400070af  call    cs:__imp_PsGetCurrentProcess
0x1400070b6  nop     dword ptr [rax+rax+00h]
0x1400070bb  mov     rcx, rax
0x1400070be  call    cs:__imp_PsGetProcessPeb
0x1400070c5  nop     dword ptr [rax+rax+00h]
0x1400070ca  test    rax, rax
0x1400070cd  jz      short loc_1400070E0
0x1400070cf  call    cs:__imp_PsGetCurrentProcess
0x1400070d6  nop     dword ptr [rax+rax+00h]
0x1400070db  mov     rcx, rax
0x1400070de  jmp     short loc_140007064
0x1400070e0  xor     eax, eax
0x1400070e2  jmp     loc_140006FE3
0x1400070e7  xorps   xmm0, xmm0
0x1400070ea  xor     eax, eax
0x1400070ec  movups  xmmword ptr [rsp+0A8h+RequiredPrivileges.PrivilegeCount], xmm0
0x1400070f1  mov     [rsp+0A8h+RequiredPrivileges.Privilege.Attributes], eax
0x1400070f8  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x1400070fd  call    cs:__imp_SeCaptureSubjectContext
0x140007104  nop     dword ptr [rax+rax+00h]
0x140007109  mov     dil, 1
0x14000710c  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x140007111  call    cs:__imp_SeLockSubjectContext
0x140007118  nop     dword ptr [rax+rax+00h]
0x14000711d  mov     [rsp+0A8h+RequiredPrivileges.PrivilegeCount], 1
0x140007125  mov     [rsp+0A8h+RequiredPrivileges.Control], 1
0x14000712d  mov     qword ptr [rsp+0A8h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x140007139  mov     r8b, dil; AccessMode
0x14000713c  lea     rdx, [rsp+0A8h+SubjectContext]; SubjectSecurityContext
0x140007141  lea     rcx, [rsp+0A8h+RequiredPrivileges]; RequiredPrivileges
0x140007146  call    cs:__imp_SePrivilegeCheck
0x14000714d  nop     dword ptr [rax+rax+00h]
0x140007152  neg     al
0x140007154  sbb     cl, cl
0x140007156  and     bl, cl
0x140007158  jmp     loc_140007016
0x14000715d  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x140007162  call    cs:__imp_SeUnlockSubjectContext
0x140007169  nop     dword ptr [rax+rax+00h]
0x14000716e  test    dil, dil
0x140007171  jz      loc_14000701F
0x140007177  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x14000717c  call    cs:__imp_SeReleaseSubjectContext
0x140007183  nop     dword ptr [rax+rax+00h]
0x140007188  jmp     loc_14000701F
0x14000718d  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x140007192  call    cs:__imp_KeUnstackDetachProcess
0x140007199  nop     dword ptr [rax+rax+00h]
0x14000719e  jmp     loc_140007028
```
