# CClfsManagedLogClient::Initialize(_FILE_OBJECT *,void *,CClfsManagedLog *)

- ea: `0x14006fe80`
- end: `0x14006ffa7`
- name: `?Initialize@CClfsManagedLogClient@@UEAAJPEAU_FILE_OBJECT@@PEAXPEAVCClfsManagedLog@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CClfsManagedLogClient *__hidden this, PLOG_FILE_OBJECT plfoLog, void *, struct CClfsManagedLog *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400521c0`
- `0x14006fde0`

## callees

- `0x140017e40`
- `0x140017f20`
- `0x140059b80`
- `0x14006fe80`
- `0x14006ffb0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14006fecf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006fecf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006ff14`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006ff14`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14006ff01`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x14006ff01`

## pseudocode

```c
NTSTATUS __fastcall CClfsManagedLogClient::Initialize(
        CClfsManagedLogClient *this,
        PLOG_FILE_OBJECT plfoLog,
        void *a3,
        struct CClfsManagedLog *a4)
{
  NTSTATUS v7; // r14d
  NTSTATUS result; // eax
  NTSTATUS v9; // edi
  _BYTE pinfoBuffer[4]; // [rsp+30h] [rbp-40h] BYREF
  ULONG pcbInfoBuffer; // [rsp+34h] [rbp-3Ch] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+38h] [rbp-38h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+58h] [rbp-18h] BYREF

  pinfoBuffer[0] = 0;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  pcbInfoBuffer = 1;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  ClientSecurityQos.Length = 12;
  ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
  *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
  v7 = SeCreateClientSecurityFromSubjectContext(
         &SubjectContext,
         &ClientSecurityQos,
         0,
         (PSECURITY_CLIENT_CONTEXT)((char *)this + 128));
  SeReleaseSubjectContext(&SubjectContext);
  if ( v7 < 0 )
    return v7;
  *((_BYTE *)this + 200) = 1;
  result = ClfsQueryLogFileInformation(plfoLog, ClfsLogStreamIdentifierInformation, 0, 0, pinfoBuffer, &pcbInfoBuffer);
  if ( result >= 0 )
  {
    *((_BYTE *)this + 104) = pinfoBuffer[0];
    *((_QWORD *)this + 11) = plfoLog;
    result = CClfsManagedLogClient::InstallLogObserver(this);
    v9 = result;
    if ( result >= 0 )
    {
      *((_QWORD *)this + 12) = a4;
      (**(void (__fastcall ***)(struct CClfsManagedLog *))a4)(a4);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14006fe80  mov     [rsp-18h+arg_10], rbx
0x14006fe85  mov     [rsp-18h+arg_18], rsi
0x14006fe8a  push    rbp
0x14006fe8b  push    rdi
0x14006fe8c  push    r14
0x14006fe8e  mov     rbp, rsp
0x14006fe91  sub     rsp, 70h
0x14006fe95  mov     rax, cs:__security_cookie
0x14006fe9c  xor     rax, rsp
0x14006fe9f  mov     [rbp+var_8], rax
0x14006fea3  xor     eax, eax
0x14006fea5  mov     [rbp+var_40], 0
0x14006fea9  xorps   xmm0, xmm0
0x14006feac  mov     qword ptr [rbp+ClientSecurityQos.Length], rax
0x14006feb0  mov     rbx, rcx
0x14006feb3  mov     dword ptr [rbp+ClientSecurityQos.ContextTrackingMode], eax
0x14006feb6  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14006feba  mov     [rbp+var_3C], 1
0x14006fec1  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14006fec5  mov     rsi, r9
0x14006fec8  mov     rdi, rdx
0x14006fecb  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14006fecf  call    cs:__imp_SeCaptureSubjectContext
0x14006fed6  nop     dword ptr [rax+rax+00h]
0x14006fedb  lea     r9, [rbx+80h]; ClientContext
0x14006fee2  mov     [rbp+ClientSecurityQos.Length], 0Ch
0x14006fee9  xor     r8d, r8d; ServerIsRemote
0x14006feec  mov     [rbp+ClientSecurityQos.ImpersonationLevel], 2
0x14006fef3  lea     rdx, [rbp+ClientSecurityQos]; ClientSecurityQos
0x14006fef7  mov     word ptr [rbp+ClientSecurityQos.ContextTrackingMode], 1
0x14006fefd  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14006ff01  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x14006ff08  nop     dword ptr [rax+rax+00h]
0x14006ff0d  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14006ff11  mov     r14d, eax
0x14006ff14  call    cs:__imp_SeReleaseSubjectContext
0x14006ff1b  nop     dword ptr [rax+rax+00h]
0x14006ff20  test    r14d, r14d
0x14006ff23  js      short loc_14006FFA2
0x14006ff25  xor     r9d, r9d; cbinfoInputBuffer
0x14006ff28  mov     byte ptr [rbx+0C8h], 1
0x14006ff2f  lea     rax, [rbp+var_3C]
0x14006ff33  xor     r8d, r8d; pinfoInputBuffer
0x14006ff36  mov     [rsp+70h+pcbInfoBuffer], rax; pcbInfoBuffer
0x14006ff3b  mov     rcx, rdi; plfoLog
0x14006ff3e  lea     rax, [rbp+var_40]
0x14006ff42  lea     edx, [r9+3]; eInformationClass
0x14006ff46  mov     [rsp+70h+pinfoBuffer], rax; pinfoBuffer
0x14006ff4b  call    ClfsQueryLogFileInformation
0x14006ff50  test    eax, eax
0x14006ff52  js      short loc_14006FF80
0x14006ff54  mov     al, [rbp+var_40]
0x14006ff57  mov     rcx, rbx; this
0x14006ff5a  mov     [rbx+68h], al
0x14006ff5d  mov     [rbx+58h], rdi
0x14006ff61  call    ?InstallLogObserver@CClfsManagedLogClient@@AEAAJXZ; CClfsManagedLogClient::InstallLogObserver(void)
0x14006ff66  mov     edi, eax
0x14006ff68  test    eax, eax
0x14006ff6a  js      short loc_14006FF80
0x14006ff6c  mov     [rbx+60h], rsi
0x14006ff70  mov     rcx, rsi
0x14006ff73  mov     rax, [rsi]
0x14006ff76  mov     rax, [rax]
0x14006ff79  call    _guard_dispatch_icall
0x14006ff7e  mov     eax, edi
0x14006ff80  mov     rcx, [rbp+var_8]
0x14006ff84  xor     rcx, rsp; StackCookie
0x14006ff87  call    __security_check_cookie
0x14006ff8c  lea     r11, [rsp+70h+var_s0]
0x14006ff91  mov     rbx, [r11+30h]
0x14006ff95  mov     rsi, [r11+38h]
0x14006ff99  mov     rsp, r11
0x14006ff9c  pop     r14
0x14006ff9e  pop     rdi
0x14006ff9f  pop     rbp
0x14006ffa0  retn
0x14006ffa2  mov     eax, r14d
0x14006ffa5  jmp     short loc_14006FF80
```
