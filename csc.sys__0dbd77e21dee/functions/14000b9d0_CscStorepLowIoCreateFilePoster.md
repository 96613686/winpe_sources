# CscStorepLowIoCreateFilePoster

- ea: `0x14000b9d0`
- end: `0x14000bd46`
- name: `CscStorepLowIoCreateFilePoster`
- size: `886`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, int, struct _LIST_ENTRY *, int, int, int, int, struct _LIST_ENTRY *, int, struct _LIST_ENTRY *, struct _LIST_ENTRY *)`
- caller_count: `15`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000a884`
- `0x14000b810`
- `0x140016758`
- `0x140017f10`
- `0x14002a8b4`
- `0x1400487a8`
- `0x140049a6c`
- `0x140054964`
- `0x1400570c0`
- `0x140059edc`
- `0x14005dc84`
- `0x14005f70c`
- `0x14005f838`
- `0x140089e98`
- `0x14008c4d0`

## callees

- `0x14000b9d0`
- `0x14000c5f8`
- `0x140018930`
- `0x14002f010`
- `0x14002f0f0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000bbda`
- `ntoskrnl!KeInitializeEvent` at `0x14000bbda`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000ba38`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000ba38`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000bb49`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000bcdf`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000bb49`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000bcdf`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000ba21`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000ba21`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000bc15`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000bc3d`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000bc15`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000bc3d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000bb99`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000bb99`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000bd35`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000bd35`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000bc8b`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000bc8b`
- `ntoskrnl!IoGetStackLimits` at `0x14000bb0e`
- `ntoskrnl!IoGetStackLimits` at `0x14000bb0e`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoCreateFilePoster(
        struct _LIST_ENTRY *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        int a4,
        struct _LIST_ENTRY *a5,
        int a6,
        int a7,
        int a8,
        int a9,
        struct _LIST_ENTRY *a10,
        int a11,
        struct _LIST_ENTRY *a12,
        struct _LIST_ENTRY *a13)
{
  BOOLEAN v17; // r12
  struct _LIST_ENTRY *v18; // rax
  int *v19; // rbx
  char v20; // si
  int Blink; // edi
  NTSTATUS v23; // eax
  BOOLEAN v24; // r14
  __int64 v25; // rcx
  NTSTATUS v26; // eax
  struct _KEVENT Parameter; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 HighLimit; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-79h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+58h] [rbp-71h] BYREF
  struct _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+70h] [rbp-59h] BYREF

  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&ClientContext, 0, sizeof(ClientContext));
  v17 = KeAreAllApcsDisabled();
  v18 = (struct _LIST_ENTRY *)ExAllocateFromPagedLookasideList(&Lookaside);
  v19 = (int *)v18;
  if ( v18 )
  {
    *v18 = 0;
    v18[1] = 0;
    v18[2] = 0;
    v18[3] = 0;
    v18[4] = 0;
    v18[5] = 0;
    v18[6] = 0;
    v18[7] = 0;
    v18[8] = 0;
    v18[2].Blink = a1;
    v18[3].Blink = a2;
    v18[4].Flink = a3;
    LODWORD(v18[4].Blink) = a4;
    v18[5].Flink = a5;
    LODWORD(v18[5].Blink) = a6;
    HIDWORD(v18[5].Blink) = a7;
    LODWORD(v18[6].Flink) = a8;
    HIDWORD(v18[6].Flink) = a9;
    v18[6].Blink = a10;
    LODWORD(v18[7].Flink) = a11;
    v18[7].Blink = a12;
    v18[8].Flink = a13;
    if ( v17 )
    {
      ClientSecurityQos.Length = 12;
      ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
      *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 257;
      v26 = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, &ClientContext);
      Blink = v26;
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)v26);
        }
        ExFreeToPagedLookasideList(&Lookaside, v19);
        return (unsigned int)Blink;
      }
      *((_QWORD *)v19 + 17) = &ClientContext;
      v20 = 1;
      memset(&Parameter, 0, sizeof(Parameter));
      KeInitializeEvent(&Parameter, NotificationEvent, 0);
      *(_QWORD *)v19 = KeGetCurrentThread();
      *((_QWORD *)v19 + 1) = 0;
      *((_QWORD *)v19 + 2) = CscStorepLowIoCreateFilePostedRoutine;
      *((_QWORD *)v19 + 4) = &Parameter;
      v19[6] = -1;
      v24 = KeSetKernelStackSwapEnable(0);
      Blink = CscStorepLowIoPostWorkItemAndWait(v25, v19, &Parameter);
      if ( v24 )
        KeSetKernelStackSwapEnable(v24);
      if ( Blink >= 0 )
        Blink = v19[6];
    }
    else
    {
      Parameter.Header.WaitListHead.Flink = v18;
      Parameter.Header.WaitListHead.Blink = 0;
      *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoCreateFilePostedRoutine;
      HighLimit = 0;
      LowLimit = 0;
      v20 = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
      {
LABEL_4:
        Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
        goto LABEL_5;
      }
      v23 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
      if ( v23 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)v23);
        }
        goto LABEL_4;
      }
      Blink = (int)Parameter.Header.WaitListHead.Blink;
    }
LABEL_5:
    ExFreeToPagedLookasideList(&Lookaside, v19);
    if ( v20 )
      SeDeleteClientSecurity(&ClientContext);
    return (unsigned int)Blink;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000b9d0  push    rbp
0x14000b9d2  push    rbx
0x14000b9d3  push    rsi
0x14000b9d4  push    rdi
0x14000b9d5  push    r12
0x14000b9d7  push    r14
0x14000b9d9  push    r15
0x14000b9db  lea     rbp, [rsp-7]
0x14000b9e0  sub     rsp, 0D0h
0x14000b9e7  mov     rax, cs:__security_cookie
0x14000b9ee  xor     rax, rsp
0x14000b9f1  mov     [rbp+37h+var_40], rax
0x14000b9f5  xorps   xmm0, xmm0
0x14000b9f8  xor     eax, eax
0x14000b9fa  mov     qword ptr [rbp+37h+ClientSecurityQos.Length], rax
0x14000b9fe  mov     edi, r9d
0x14000ba01  mov     dword ptr [rbp+37h+ClientSecurityQos.ContextTrackingMode], eax
0x14000ba04  mov     rsi, r8
0x14000ba07  movups  xmmword ptr [rbp+37h+ClientContext.SecurityQos.Length], xmm0
0x14000ba0b  mov     qword ptr [rbp+37h+ClientContext.ClientTokenControl.TokenSource.SourceIdentifier.HighPart], rax
0x14000ba0f  mov     r14, rdx
0x14000ba12  movups  xmmword ptr [rbp+37h+ClientContext.ClientToken], xmm0
0x14000ba16  mov     r15, rcx
0x14000ba19  movups  xmmword ptr [rbp+37h+ClientContext.ClientTokenControl.TokenId.HighPart], xmm0
0x14000ba1d  movups  xmmword ptr [rbp+37h+ClientContext.ClientTokenControl.ModifiedId.HighPart], xmm0
0x14000ba21  call    cs:__imp_KeAreAllApcsDisabled
0x14000ba28  nop     dword ptr [rax+rax+00h]
0x14000ba2d  lea     rcx, Lookaside; Lookaside
0x14000ba34  movzx   r12d, al
0x14000ba38  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000ba3f  nop     dword ptr [rax+rax+00h]
0x14000ba44  mov     rbx, rax
0x14000ba47  test    rax, rax
0x14000ba4a  jz      loc_14000BC59
0x14000ba50  xorps   xmm0, xmm0
0x14000ba53  movups  xmmword ptr [rax], xmm0
0x14000ba56  movups  xmmword ptr [rax+10h], xmm0
0x14000ba5a  movups  xmmword ptr [rax+20h], xmm0
0x14000ba5e  movups  xmmword ptr [rax+30h], xmm0
0x14000ba62  movups  xmmword ptr [rax+40h], xmm0
0x14000ba66  movups  xmmword ptr [rax+50h], xmm0
0x14000ba6a  movups  xmmword ptr [rax+60h], xmm0
0x14000ba6e  movups  xmmword ptr [rax+70h], xmm0
0x14000ba72  movups  xmmword ptr [rax+80h], xmm0
0x14000ba79  mov     [rax+28h], r15
0x14000ba7d  mov     [rax+38h], r14
0x14000ba81  mov     [rax+40h], rsi
0x14000ba85  mov     [rax+48h], edi
0x14000ba88  mov     rax, [rbp+37h+arg_20]
0x14000ba8c  mov     [rbx+50h], rax
0x14000ba90  mov     eax, [rbp+37h+arg_28]
0x14000ba93  mov     [rbx+58h], eax
0x14000ba96  mov     eax, [rbp+37h+arg_30]
0x14000ba99  mov     [rbx+5Ch], eax
0x14000ba9c  mov     eax, [rbp+37h+arg_38]
0x14000ba9f  mov     [rbx+60h], eax
0x14000baa2  mov     eax, [rbp+37h+arg_40]
0x14000baa8  mov     [rbx+64h], eax
0x14000baab  mov     rax, [rbp+37h+arg_48]
0x14000bab2  mov     [rbx+68h], rax
0x14000bab6  mov     eax, [rbp+37h+arg_50]
0x14000babc  mov     [rbx+70h], eax
0x14000babf  mov     rax, [rbp+37h+arg_58]
0x14000bac6  mov     [rbx+78h], rax
0x14000baca  mov     rax, [rbp+37h+arg_60]
0x14000bad1  mov     [rbx+80h], rax
0x14000bad8  test    r12b, r12b
0x14000badb  jnz     loc_14000BC63
0x14000bae1  xor     edi, edi
0x14000bae3  mov     qword ptr [rsp+100h+Parameter+8], rbx
0x14000bae8  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000baef  mov     [rsp+100h+var_C0], rdi
0x14000baf4  lea     rdx, [rsp+100h+HighLimit]; HighLimit
0x14000baf9  mov     qword ptr [rsp+100h+Parameter], rax
0x14000bafe  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x14000bb02  mov     [rsp+100h+HighLimit], rdi
0x14000bb07  mov     [rbp+37h+LowLimit], rdi
0x14000bb0b  xor     sil, sil
0x14000bb0e  call    cs:__imp_IoGetStackLimits
0x14000bb15  nop     dword ptr [rax+rax+00h]
0x14000bb1a  mov     eax, cs:dword_14003BD20
0x14000bb20  lea     rcx, [rsp+100h+HighLimit]
0x14000bb25  sub     rcx, [rbp+37h+LowLimit]
0x14000bb29  cmp     rcx, rax
0x14000bb2c  jb      short loc_14000BB7F
0x14000bb2e  mov     rcx, qword ptr [rsp+100h+Parameter+8]
0x14000bb33  mov     rax, qword ptr [rsp+100h+Parameter]
0x14000bb38  call    _guard_dispatch_icall
0x14000bb3d  mov     edi, eax
0x14000bb3f  mov     rdx, rbx; Entry
0x14000bb42  lea     rcx, Lookaside; Lookaside
0x14000bb49  call    cs:__imp_ExFreeToPagedLookasideList
0x14000bb50  nop     dword ptr [rax+rax+00h]
0x14000bb55  test    sil, sil
0x14000bb58  jnz     loc_14000BD31
0x14000bb5e  mov     eax, edi
0x14000bb60  mov     rcx, [rbp+37h+var_40]
0x14000bb64  xor     rcx, rsp; StackCookie
0x14000bb67  call    __security_check_cookie
0x14000bb6c  add     rsp, 0D0h
0x14000bb73  pop     r15
0x14000bb75  pop     r14
0x14000bb77  pop     r12
0x14000bb79  pop     rdi
0x14000bb7a  pop     rsi
0x14000bb7b  pop     rbx
0x14000bb7c  pop     rbp
0x14000bb7d  retn
0x14000bb7f  xor     r9d, r9d; Wait
0x14000bb82  mov     [rsp+100h+Context], rdi; Context
0x14000bb87  mov     r8d, 6000h; Size
0x14000bb8d  lea     rdx, [rsp+100h+Parameter]; Parameter
0x14000bb92  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000bb99  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000bba0  nop     dword ptr [rax+rax+00h]
0x14000bba5  test    eax, eax
0x14000bba7  js      loc_14000BCF0
0x14000bbad  mov     edi, dword ptr [rsp+100h+var_C0]
0x14000bbb1  jmp     short loc_14000BB3F
0x14000bbb3  lea     rax, [rbp+37h+ClientContext]
0x14000bbb7  xorps   xmm0, xmm0
0x14000bbba  mov     [rbx+88h], rax
0x14000bbc1  lea     rcx, [rsp+100h+Parameter]; Event
0x14000bbc6  xor     eax, eax
0x14000bbc8  xor     r8d, r8d; State
0x14000bbcb  xor     edx, edx; Type
0x14000bbcd  mov     [rsp+100h+var_C0], rax
0x14000bbd2  mov     sil, 1
0x14000bbd5  movups  [rsp+100h+Parameter], xmm0
0x14000bbda  call    cs:__imp_KeInitializeEvent
0x14000bbe1  nop     dword ptr [rax+rax+00h]
0x14000bbe6  mov     rax, gs:188h
0x14000bbef  xor     edi, edi
0x14000bbf1  mov     [rbx], rax
0x14000bbf4  xor     ecx, ecx; Enable
0x14000bbf6  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000bbfd  mov     [rbx+8], rdi
0x14000bc01  mov     [rbx+10h], rax
0x14000bc05  lea     rax, [rsp+100h+Parameter]
0x14000bc0a  mov     [rbx+20h], rax
0x14000bc0e  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x14000bc15  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000bc1c  nop     dword ptr [rax+rax+00h]
0x14000bc21  lea     r8, [rsp+100h+Parameter]
0x14000bc26  mov     rdx, rbx
0x14000bc29  movzx   r14d, al
0x14000bc2d  call    CscStorepLowIoPostWorkItemAndWait
0x14000bc32  mov     edi, eax
0x14000bc34  test    r14b, r14b
0x14000bc37  jz      short loc_14000BC49
0x14000bc39  movzx   ecx, r14b; Enable
0x14000bc3d  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000bc44  nop     dword ptr [rax+rax+00h]
0x14000bc49  test    edi, edi
0x14000bc4b  js      loc_14000BB3F
0x14000bc51  mov     edi, [rbx+18h]
0x14000bc54  jmp     loc_14000BB3F
0x14000bc59  mov     eax, 0C000009Ah
0x14000bc5e  jmp     loc_14000BB60
0x14000bc63  mov     [rbp+37h+ClientSecurityQos.Length], 0Ch
0x14000bc6a  lea     r9, [rbp+37h+ClientContext]; ClientContext
0x14000bc6e  mov     [rbp+37h+ClientSecurityQos.ImpersonationLevel], 2
0x14000bc75  lea     rdx, [rbp+37h+ClientSecurityQos]; ClientSecurityQos
0x14000bc79  mov     word ptr [rbp+37h+ClientSecurityQos.ContextTrackingMode], 101h
0x14000bc7f  xor     r8d, r8d; RemoteSession
0x14000bc82  mov     rcx, gs:188h; ClientThread
0x14000bc8b  call    cs:__imp_SeCreateClientSecurity
0x14000bc92  nop     dword ptr [rax+rax+00h]
0x14000bc97  mov     edi, eax
0x14000bc99  test    eax, eax
0x14000bc9b  jns     loc_14000BBB3
0x14000bca1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bca8  lea     rdx, WPP_GLOBAL_Control
0x14000bcaf  cmp     rcx, rdx
0x14000bcb2  jz      short loc_14000BCD5
0x14000bcb4  test    dword ptr [rcx+2Ch], 20000h
0x14000bcbb  jz      short loc_14000BCD5
0x14000bcbd  mov     rcx, [rcx+18h]
0x14000bcc1  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000bcc8  mov     edx, 11h
0x14000bccd  mov     r9d, eax
0x14000bcd0  call    WPP_SF_d
0x14000bcd5  mov     rdx, rbx; Entry
0x14000bcd8  lea     rcx, Lookaside; Lookaside
0x14000bcdf  call    cs:__imp_ExFreeToPagedLookasideList
0x14000bce6  nop     dword ptr [rax+rax+00h]
0x14000bceb  jmp     loc_14000BB5E
0x14000bcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcf7  lea     rdx, WPP_GLOBAL_Control
0x14000bcfe  cmp     rcx, rdx
0x14000bd01  jz      loc_14000BB2E
0x14000bd07  test    dword ptr [rcx+2Ch], 40000h
0x14000bd0e  jz      loc_14000BB2E
0x14000bd14  mov     rcx, [rcx+18h]
0x14000bd18  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000bd1f  mov     edx, 0Bh
0x14000bd24  mov     r9d, eax
0x14000bd27  call    WPP_SF_d
0x14000bd2c  jmp     loc_14000BB2E
0x14000bd31  lea     rcx, [rbp+37h+ClientContext]
0x14000bd35  call    cs:__imp_SeDeleteClientSecurity
0x14000bd3c  nop     dword ptr [rax+rax+00h]
0x14000bd41  jmp     loc_14000BB5E
```
