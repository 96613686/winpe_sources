# CscStorepLowIoOpenFileByFileId_Internal

- ea: `0x1400104ec`
- end: `0x140010877`
- name: `CscStorepLowIoOpenFileByFileId_Internal`
- size: `907`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140029444`
- `0x14002992c`
- `0x1400299b4`

## callees

- `0x14000c5f8`
- `0x14000e960`
- `0x1400104ec`
- `0x140012c20`
- `0x140018930`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400106cd`
- `ntoskrnl!KeInitializeEvent` at `0x1400106cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140010573`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140010573`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140010655`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140010655`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14001055d`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14001055d`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x140010706`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14001072c`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x140010706`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14001072c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140010631`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140010631`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140010815`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140010815`
- `ntoskrnl!SeCreateClientSecurity` at `0x14001077a`
- `ntoskrnl!SeCreateClientSecurity` at `0x14001077a`
- `ntoskrnl!IoGetStackLimits` at `0x1400105f8`
- `ntoskrnl!IoGetStackLimits` at `0x1400105f8`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoOpenFileByFileId_Internal(
        char a1,
        void **a2,
        void *a3,
        __int64 a4,
        ACCESS_MASK a5,
        ULONG a6,
        int a7)
{
  BOOLEAN v9; // r15
  PVOID v10; // rax
  PVOID v11; // rdi
  char v12; // r12
  NTSTATUS v13; // eax
  NTSTATUS Blink; // ebx
  BOOLEAN v16; // si
  __int64 v17; // rcx
  struct _KEVENT Parameter; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 HighLimit; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v21; // [rsp+98h] [rbp-68h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+B0h] [rbp-50h] BYREF
  struct _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+C0h] [rbp-40h] BYREF

  v22 = a4;
  *(_QWORD *)&v21.Length = 524296;
  v21.Buffer = (PWSTR)&v22;
  if ( a1 )
  {
    *(_QWORD *)&ClientSecurityQos.Length = 0;
    *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
    memset(&ClientContext, 0, sizeof(ClientContext));
    v9 = KeAreAllApcsDisabled();
    v10 = ExAllocateFromPagedLookasideList(&Lookaside);
    v11 = v10;
    if ( v10 )
    {
      v12 = 0;
      memset(v10, 0, 0x90u);
      *((_QWORD *)v11 + 5) = a2;
      *((_QWORD *)v11 + 8) = &v21;
      *((_DWORD *)v11 + 18) = a5;
      *((_DWORD *)v11 + 23) = a6;
      *((_QWORD *)v11 + 7) = a3;
      *((_DWORD *)v11 + 24) = 1;
      *((_DWORD *)v11 + 25) = a7 | 0x2000;
      if ( v9 )
      {
        ClientSecurityQos.Length = 12;
        ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
        *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 257;
        Blink = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, &ClientContext);
        if ( Blink >= 0 )
        {
          *((_QWORD *)v11 + 17) = &ClientContext;
          v12 = 1;
          memset(&Parameter, 0, sizeof(Parameter));
          KeInitializeEvent(&Parameter, NotificationEvent, 0);
          *(_QWORD *)v11 = KeGetCurrentThread();
          *((_QWORD *)v11 + 2) = CscStorepLowIoCreateFilePostedRoutine;
          *((_QWORD *)v11 + 4) = &Parameter;
          *((_QWORD *)v11 + 1) = 0;
          *((_DWORD *)v11 + 6) = -1;
          v16 = KeSetKernelStackSwapEnable(0);
          Blink = CscStorepLowIoPostWorkItemAndWait(v17, v11, &Parameter);
          if ( v16 )
            KeSetKernelStackSwapEnable(v16);
          if ( Blink >= 0 )
            Blink = *((_DWORD *)v11 + 6);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)Blink);
        }
      }
      else
      {
        Parameter.Header.WaitListHead.Blink = 0;
        *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoCreateFilePostedRoutine;
        Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v11;
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits(&LowLimit, &HighLimit);
        if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
        {
          Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
        }
        else
        {
          v13 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
          if ( v13 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
                (unsigned int)v13);
            }
            CscStorepLowIoPost_Callout(&Parameter);
          }
          Blink = (NTSTATUS)Parameter.Header.WaitListHead.Blink;
        }
      }
      ExFreeToPagedLookasideList(&Lookaside, v11);
      if ( v12 )
        SeDeleteClientSecurity(&ClientContext);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)CscStorepLowIoCreateFile(a2, a3, &v21, a5, 0, 0, a6, 1u, a7 | 0x2000u, 0, 0, 0, 0);
  }
  return (unsigned int)Blink;
}

```

## disassembly

```asm
0x1400104ec  mov     [rsp-8+arg_0], rbx
0x1400104f1  push    rbp
0x1400104f2  push    rsi
0x1400104f3  push    rdi
0x1400104f4  push    r12
0x1400104f6  push    r13
0x1400104f8  push    r14
0x1400104fa  push    r15
0x1400104fc  lea     rbp, [rsp-20h]
0x140010501  sub     rsp, 120h
0x140010508  mov     rax, cs:__security_cookie
0x14001050f  xor     rax, rsp
0x140010512  mov     [rbp+50h+var_40], rax
0x140010516  mov     ebx, [rbp+50h+arg_30]
0x14001051c  lea     rax, [rbp+50h+var_A8]
0x140010520  bts     ebx, 0Dh
0x140010524  mov     [rbp+50h+var_A8], r9
0x140010528  xor     r13d, r13d
0x14001052b  mov     [rbp+50h+var_B8], 80008h
0x140010533  mov     [rbp+50h+var_B0], rax
0x140010537  mov     r14, r8
0x14001053a  mov     rsi, rdx
0x14001053d  test    cl, cl
0x14001053f  jz      loc_140010826
0x140010545  xor     eax, eax
0x140010547  lea     r8d, [r13+48h]; Size
0x14001054b  xor     edx, edx; Val
0x14001054d  mov     qword ptr [rbp+50h+ClientSecurityQos.Length], rax
0x140010551  lea     rcx, [rbp+50h+ClientContext]; void *
0x140010555  mov     dword ptr [rbp+50h+ClientSecurityQos.ContextTrackingMode], eax
0x140010558  call    memset
0x14001055d  call    cs:__imp_KeAreAllApcsDisabled
0x140010564  nop     dword ptr [rax+rax+00h]
0x140010569  lea     rcx, Lookaside; Lookaside
0x140010570  mov     r15b, al
0x140010573  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001057a  nop     dword ptr [rax+rax+00h]
0x14001057f  mov     rdi, rax
0x140010582  test    rax, rax
0x140010585  jz      loc_140010748
0x14001058b  xor     edx, edx; Val
0x14001058d  mov     r8d, 90h; Size
0x140010593  mov     rcx, rax; void *
0x140010596  mov     r12b, r13b
0x140010599  call    memset
0x14001059e  mov     [rdi+28h], rsi
0x1400105a2  lea     rax, [rbp+50h+var_B8]
0x1400105a6  mov     [rdi+40h], rax
0x1400105aa  mov     eax, [rbp+50h+arg_20]
0x1400105b0  mov     [rdi+48h], eax
0x1400105b3  mov     eax, [rbp+50h+arg_28]
0x1400105b9  mov     [rdi+5Ch], eax
0x1400105bc  mov     [rdi+38h], r14
0x1400105c0  mov     dword ptr [rdi+60h], 1
0x1400105c7  mov     [rdi+64h], ebx
0x1400105ca  test    r15b, r15b
0x1400105cd  jnz     loc_140010752
0x1400105d3  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x1400105da  mov     [rbp+50h+var_D0], r13
0x1400105de  lea     rdx, [rbp+50h+HighLimit]; HighLimit
0x1400105e2  mov     qword ptr [rsp+150h+Parameter], rax
0x1400105e7  lea     rcx, [rbp+50h+LowLimit]; LowLimit
0x1400105eb  mov     qword ptr [rsp+150h+Parameter+8], rdi
0x1400105f0  mov     [rbp+50h+HighLimit], r13
0x1400105f4  mov     [rbp+50h+LowLimit], r13
0x1400105f8  call    cs:__imp_IoGetStackLimits
0x1400105ff  nop     dword ptr [rax+rax+00h]
0x140010604  mov     eax, cs:dword_14003BD20
0x14001060a  lea     rcx, [rbp+50h+HighLimit]
0x14001060e  sub     rcx, [rbp+50h+LowLimit]
0x140010612  cmp     rcx, rax
0x140010615  jnb     short loc_140010694
0x140010617  xor     r9d, r9d; Wait
0x14001061a  mov     [rsp+150h+Context], r13; Context
0x14001061f  mov     r8d, 6000h; Size
0x140010625  lea     rdx, [rsp+150h+Parameter]; Parameter
0x14001062a  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x140010631  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140010638  nop     dword ptr [rax+rax+00h]
0x14001063d  mov     r9d, eax
0x140010640  test    eax, eax
0x140010642  js      loc_1400107D1
0x140010648  mov     ebx, dword ptr [rbp+50h+var_D0]
0x14001064b  mov     rdx, rdi; Entry
0x14001064e  lea     rcx, Lookaside; Lookaside
0x140010655  call    cs:__imp_ExFreeToPagedLookasideList
0x14001065c  nop     dword ptr [rax+rax+00h]
0x140010661  test    r12b, r12b
0x140010664  jnz     loc_140010811
0x14001066a  mov     eax, ebx
0x14001066c  mov     rcx, [rbp+50h+var_40]
0x140010670  xor     rcx, rsp; StackCookie
0x140010673  call    __security_check_cookie
0x140010678  mov     rbx, [rsp+150h+arg_0]
0x140010680  add     rsp, 120h
0x140010687  pop     r15
0x140010689  pop     r14
0x14001068b  pop     r13
0x14001068d  pop     r12
0x14001068f  pop     rdi
0x140010690  pop     rsi
0x140010691  pop     rbp
0x140010692  retn
0x140010694  mov     rcx, qword ptr [rsp+150h+Parameter+8]
0x140010699  mov     rax, qword ptr [rsp+150h+Parameter]
0x14001069e  call    _guard_dispatch_icall
0x1400106a3  mov     ebx, eax
0x1400106a5  jmp     short loc_14001064B
0x1400106a7  lea     rax, [rbp+50h+ClientContext]
0x1400106ab  xorps   xmm0, xmm0
0x1400106ae  mov     [rdi+88h], rax
0x1400106b5  lea     rcx, [rsp+150h+Parameter]; Event
0x1400106ba  xor     eax, eax
0x1400106bc  xor     r8d, r8d; State
0x1400106bf  xor     edx, edx; Type
0x1400106c1  mov     [rbp+50h+var_D0], rax
0x1400106c5  mov     r12b, 1
0x1400106c8  movups  [rsp+150h+Parameter], xmm0
0x1400106cd  call    cs:__imp_KeInitializeEvent
0x1400106d4  nop     dword ptr [rax+rax+00h]
0x1400106d9  mov     rax, gs:188h
0x1400106e2  xor     ecx, ecx; Enable
0x1400106e4  mov     [rdi], rax
0x1400106e7  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x1400106ee  mov     [rdi+10h], rax
0x1400106f2  lea     rax, [rsp+150h+Parameter]
0x1400106f7  mov     [rdi+20h], rax
0x1400106fb  mov     [rdi+8], r13
0x1400106ff  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x140010706  call    cs:__imp_KeSetKernelStackSwapEnable
0x14001070d  nop     dword ptr [rax+rax+00h]
0x140010712  lea     r8, [rsp+150h+Parameter]
0x140010717  mov     rdx, rdi
0x14001071a  mov     sil, al
0x14001071d  call    CscStorepLowIoPostWorkItemAndWait
0x140010722  mov     ebx, eax
0x140010724  test    sil, sil
0x140010727  jz      short loc_140010738
0x140010729  mov     cl, sil; Enable
0x14001072c  call    cs:__imp_KeSetKernelStackSwapEnable
0x140010733  nop     dword ptr [rax+rax+00h]
0x140010738  test    ebx, ebx
0x14001073a  js      loc_14001064B
0x140010740  mov     ebx, [rdi+18h]
0x140010743  jmp     loc_14001064B
0x140010748  mov     ebx, 0C000009Ah
0x14001074d  jmp     loc_14001066A
0x140010752  mov     [rbp+50h+ClientSecurityQos.Length], 0Ch
0x140010759  lea     r9, [rbp+50h+ClientContext]; ClientContext
0x14001075d  mov     [rbp+50h+ClientSecurityQos.ImpersonationLevel], 2
0x140010764  lea     rdx, [rbp+50h+ClientSecurityQos]; ClientSecurityQos
0x140010768  mov     word ptr [rbp+50h+ClientSecurityQos.ContextTrackingMode], 101h
0x14001076e  xor     r8d, r8d; RemoteSession
0x140010771  mov     rcx, gs:188h; ClientThread
0x14001077a  call    cs:__imp_SeCreateClientSecurity
0x140010781  nop     dword ptr [rax+rax+00h]
0x140010786  mov     ebx, eax
0x140010788  test    eax, eax
0x14001078a  jns     loc_1400106A7
0x140010790  mov     rcx, cs:WPP_GLOBAL_Control
0x140010797  lea     rax, WPP_GLOBAL_Control
0x14001079e  cmp     rcx, rax
0x1400107a1  jz      loc_14001064B
0x1400107a7  test    dword ptr [rcx+2Ch], 20000h
0x1400107ae  jz      loc_14001064B
0x1400107b4  mov     rcx, [rcx+18h]
0x1400107b8  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x1400107bf  mov     edx, 11h
0x1400107c4  mov     r9d, ebx
0x1400107c7  call    WPP_SF_d
0x1400107cc  jmp     loc_14001064B
0x1400107d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107d8  lea     rax, WPP_GLOBAL_Control
0x1400107df  cmp     rcx, rax
0x1400107e2  jz      short loc_140010802
0x1400107e4  test    dword ptr [rcx+2Ch], 40000h
0x1400107eb  jz      short loc_140010802
0x1400107ed  mov     rcx, [rcx+18h]
0x1400107f1  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x1400107f8  mov     edx, 0Bh
0x1400107fd  call    WPP_SF_d
0x140010802  lea     rcx, [rsp+150h+Parameter]; Parameter
0x140010807  call    CscStorepLowIoPost_Callout
0x14001080c  jmp     loc_140010648
0x140010811  lea     rcx, [rbp+50h+ClientContext]
0x140010815  call    cs:__imp_SeDeleteClientSecurity
0x14001081c  nop     dword ptr [rax+rax+00h]
0x140010821  jmp     loc_14001066A
0x140010826  mov     eax, [rbp+50h+arg_28]
0x14001082c  lea     r8, [rbp+50h+var_B8]
0x140010830  mov     r9d, [rbp+50h+arg_20]
0x140010837  mov     rdx, r14
0x14001083a  mov     [rsp+150h+var_F0], r13
0x14001083f  mov     rcx, rsi
0x140010842  mov     [rsp+150h+var_F8], r13
0x140010847  mov     [rsp+150h+var_100], r13d
0x14001084c  mov     [rsp+150h+var_108], r13
0x140010851  mov     [rsp+150h+var_110], ebx
0x140010855  mov     [rsp+150h+var_118], 1
0x14001085d  mov     [rsp+150h+var_120], eax
0x140010861  mov     [rsp+150h+var_128], r13d
0x140010866  mov     [rsp+150h+Context], r13
0x14001086b  call    CscStorepLowIoCreateFile
0x140010870  mov     ebx, eax
0x140010872  jmp     loc_14001066A
```
