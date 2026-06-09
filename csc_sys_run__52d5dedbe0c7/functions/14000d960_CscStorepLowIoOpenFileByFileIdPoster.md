# CscStorepLowIoOpenFileByFileIdPoster

- ea: `0x14000d960`
- end: `0x14000dc93`
- name: `CscStorepLowIoOpenFileByFileIdPoster`
- size: `819`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140058d88`
- `0x140059188`
- `0x1400593dc`
- `0x14006c560`
- `0x140083780`

## callees

- `0x14000c5f8`
- `0x14000d960`
- `0x140018930`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000db29`
- `ntoskrnl!KeInitializeEvent` at `0x14000db29`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d9d6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d9d6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000da98`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000dc2c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000da98`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000dc2c`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d9bf`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d9bf`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000db62`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000db8a`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000db62`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000db8a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000dae8`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000dae8`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000dc82`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000dc82`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000dbd8`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000dbd8`
- `ntoskrnl!IoGetStackLimits` at `0x14000da5d`
- `ntoskrnl!IoGetStackLimits` at `0x14000da5d`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoOpenFileByFileIdPoster(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  BOOLEAN v9; // r15
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  char v12; // si
  int Blink; // edi
  NTSTATUS v15; // eax
  BOOLEAN v16; // r14
  __int64 v17; // rcx
  NTSTATUS v18; // eax
  struct _KEVENT Parameter; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 HighLimit; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v23; // [rsp+68h] [rbp-61h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+70h] [rbp-59h] BYREF
  struct _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+80h] [rbp-49h] BYREF

  v23 = a3;
  v22[1] = &v23;
  v22[0] = 524296;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&ClientContext, 0, sizeof(ClientContext));
  v9 = KeAreAllApcsDisabled();
  v10 = ExAllocateFromPagedLookasideList(&Lookaside);
  v11 = v10;
  if ( v10 )
  {
    memset(v10, 0, 0x90u);
    v11[5] = a1;
    v11[8] = v22;
    *((_DWORD *)v11 + 23) = a5;
    v11[7] = a2;
    *((_DWORD *)v11 + 18) = a4;
    *((_DWORD *)v11 + 24) = 1;
    *((_DWORD *)v11 + 25) = a6 | 0x2000;
    if ( v9 )
    {
      ClientSecurityQos.Length = 12;
      ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
      *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 257;
      v18 = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, &ClientContext);
      Blink = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)v18);
        }
        ExFreeToPagedLookasideList(&Lookaside, v11);
        return (unsigned int)Blink;
      }
      v11[17] = &ClientContext;
      v12 = 1;
      memset(&Parameter, 0, sizeof(Parameter));
      KeInitializeEvent(&Parameter, NotificationEvent, 0);
      *v11 = KeGetCurrentThread();
      v11[2] = CscStorepLowIoCreateFilePostedRoutine;
      v11[4] = &Parameter;
      v11[1] = 0;
      *((_DWORD *)v11 + 6) = -1;
      v16 = KeSetKernelStackSwapEnable(0);
      Blink = CscStorepLowIoPostWorkItemAndWait(v17, v11, &Parameter);
      if ( v16 )
        KeSetKernelStackSwapEnable(v16);
      if ( Blink >= 0 )
        Blink = *((_DWORD *)v11 + 6);
    }
    else
    {
      Parameter.Header.WaitListHead.Blink = 0;
      *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoCreateFilePostedRoutine;
      Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v11;
      v12 = 0;
      HighLimit = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
      {
LABEL_4:
        Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
        goto LABEL_5;
      }
      v15 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
            (unsigned int)v15);
        }
        goto LABEL_4;
      }
      Blink = (int)Parameter.Header.WaitListHead.Blink;
    }
LABEL_5:
    ExFreeToPagedLookasideList(&Lookaside, v11);
    if ( v12 )
      SeDeleteClientSecurity(&ClientContext);
    return (unsigned int)Blink;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000d960  push    rbp
0x14000d962  push    rbx
0x14000d963  push    rsi
0x14000d964  push    rdi
0x14000d965  push    r12
0x14000d967  push    r14
0x14000d969  push    r15
0x14000d96b  lea     rbp, [rsp-17h]
0x14000d970  sub     rsp, 0E0h
0x14000d977  mov     rax, cs:__security_cookie
0x14000d97e  xor     rax, rsp
0x14000d981  mov     [rbp+47h+var_40], rax
0x14000d985  lea     rax, [rbp+47h+var_A8]
0x14000d989  mov     [rbp+47h+var_A8], r8
0x14000d98d  mov     [rbp+47h+var_B0], rax
0x14000d991  mov     rsi, rdx
0x14000d994  xor     eax, eax
0x14000d996  mov     [rbp+47h+var_B8], 80008h
0x14000d99e  mov     rdi, rcx
0x14000d9a1  mov     qword ptr [rbp+47h+ClientSecurityQos.Length], rax
0x14000d9a5  xor     edx, edx; Val
0x14000d9a7  mov     dword ptr [rbp+47h+ClientSecurityQos.ContextTrackingMode], eax
0x14000d9aa  mov     r8d, 48h ; 'H'; Size
0x14000d9b0  lea     rcx, [rbp+47h+ClientContext]; void *
0x14000d9b4  mov     r14d, r9d
0x14000d9b7  xor     r12d, r12d
0x14000d9ba  call    memset
0x14000d9bf  call    cs:__imp_KeAreAllApcsDisabled
0x14000d9c6  nop     dword ptr [rax+rax+00h]
0x14000d9cb  lea     rcx, Lookaside; Lookaside
0x14000d9d2  movzx   r15d, al
0x14000d9d6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000d9dd  nop     dword ptr [rax+rax+00h]
0x14000d9e2  mov     rbx, rax
0x14000d9e5  test    rax, rax
0x14000d9e8  jz      loc_14000DBA6
0x14000d9ee  xor     edx, edx; Val
0x14000d9f0  mov     r8d, 90h; Size
0x14000d9f6  mov     rcx, rax; void *
0x14000d9f9  call    memset
0x14000d9fe  lea     rax, [rbp+47h+var_B8]
0x14000da02  mov     [rbx+28h], rdi
0x14000da06  mov     [rbx+40h], rax
0x14000da0a  mov     eax, [rbp+47h+arg_20]
0x14000da0d  mov     [rbx+5Ch], eax
0x14000da10  mov     eax, [rbp+47h+arg_28]
0x14000da13  bts     eax, 0Dh
0x14000da17  mov     [rbx+38h], rsi
0x14000da1b  mov     [rbx+48h], r14d
0x14000da1f  mov     dword ptr [rbx+60h], 1
0x14000da26  mov     [rbx+64h], eax
0x14000da29  test    r15b, r15b
0x14000da2c  jnz     loc_14000DBB0
0x14000da32  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000da39  mov     [rsp+110h+var_D0], r12
0x14000da3e  lea     rdx, [rsp+110h+HighLimit]; HighLimit
0x14000da43  mov     qword ptr [rsp+110h+Parameter], rax
0x14000da48  lea     rcx, [rbp+47h+LowLimit]; LowLimit
0x14000da4c  mov     qword ptr [rsp+110h+Parameter+8], rbx
0x14000da51  xor     sil, sil
0x14000da54  mov     [rsp+110h+HighLimit], r12
0x14000da59  mov     [rbp+47h+LowLimit], r12
0x14000da5d  call    cs:__imp_IoGetStackLimits
0x14000da64  nop     dword ptr [rax+rax+00h]
0x14000da69  mov     eax, cs:dword_14003BD20
0x14000da6f  lea     rcx, [rsp+110h+HighLimit]
0x14000da74  sub     rcx, [rbp+47h+LowLimit]
0x14000da78  cmp     rcx, rax
0x14000da7b  jb      short loc_14000DACE
0x14000da7d  mov     rcx, qword ptr [rsp+110h+Parameter+8]
0x14000da82  mov     rax, qword ptr [rsp+110h+Parameter]
0x14000da87  call    _guard_dispatch_icall
0x14000da8c  mov     edi, eax
0x14000da8e  mov     rdx, rbx; Entry
0x14000da91  lea     rcx, Lookaside; Lookaside
0x14000da98  call    cs:__imp_ExFreeToPagedLookasideList
0x14000da9f  nop     dword ptr [rax+rax+00h]
0x14000daa4  test    sil, sil
0x14000daa7  jnz     loc_14000DC7E
0x14000daad  mov     eax, edi
0x14000daaf  mov     rcx, [rbp+47h+var_40]
0x14000dab3  xor     rcx, rsp; StackCookie
0x14000dab6  call    __security_check_cookie
0x14000dabb  add     rsp, 0E0h
0x14000dac2  pop     r15
0x14000dac4  pop     r14
0x14000dac6  pop     r12
0x14000dac8  pop     rdi
0x14000dac9  pop     rsi
0x14000daca  pop     rbx
0x14000dacb  pop     rbp
0x14000dacc  retn
0x14000dace  xor     r9d, r9d; Wait
0x14000dad1  mov     [rsp+110h+Context], r12; Context
0x14000dad6  mov     r8d, 6000h; Size
0x14000dadc  lea     rdx, [rsp+110h+Parameter]; Parameter
0x14000dae1  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000dae8  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000daef  nop     dword ptr [rax+rax+00h]
0x14000daf4  test    eax, eax
0x14000daf6  js      loc_14000DC3D
0x14000dafc  mov     edi, dword ptr [rsp+110h+var_D0]
0x14000db00  jmp     short loc_14000DA8E
0x14000db02  lea     rax, [rbp+47h+ClientContext]
0x14000db06  xorps   xmm0, xmm0
0x14000db09  mov     [rbx+88h], rax
0x14000db10  lea     rcx, [rsp+110h+Parameter]; Event
0x14000db15  xor     eax, eax
0x14000db17  xor     r8d, r8d; State
0x14000db1a  xor     edx, edx; Type
0x14000db1c  mov     [rsp+110h+var_D0], rax
0x14000db21  mov     sil, 1
0x14000db24  movups  [rsp+110h+Parameter], xmm0
0x14000db29  call    cs:__imp_KeInitializeEvent
0x14000db30  nop     dword ptr [rax+rax+00h]
0x14000db35  mov     rax, gs:188h
0x14000db3e  xor     ecx, ecx; Enable
0x14000db40  mov     [rbx], rax
0x14000db43  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000db4a  mov     [rbx+10h], rax
0x14000db4e  lea     rax, [rsp+110h+Parameter]
0x14000db53  mov     [rbx+20h], rax
0x14000db57  mov     [rbx+8], r12
0x14000db5b  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x14000db62  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000db69  nop     dword ptr [rax+rax+00h]
0x14000db6e  lea     r8, [rsp+110h+Parameter]
0x14000db73  mov     rdx, rbx
0x14000db76  movzx   r14d, al
0x14000db7a  call    CscStorepLowIoPostWorkItemAndWait
0x14000db7f  mov     edi, eax
0x14000db81  test    r14b, r14b
0x14000db84  jz      short loc_14000DB96
0x14000db86  movzx   ecx, r14b; Enable
0x14000db8a  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000db91  nop     dword ptr [rax+rax+00h]
0x14000db96  test    edi, edi
0x14000db98  js      loc_14000DA8E
0x14000db9e  mov     edi, [rbx+18h]
0x14000dba1  jmp     loc_14000DA8E
0x14000dba6  mov     eax, 0C000009Ah
0x14000dbab  jmp     loc_14000DAAF
0x14000dbb0  mov     [rbp+47h+ClientSecurityQos.Length], 0Ch
0x14000dbb7  lea     r9, [rbp+47h+ClientContext]; ClientContext
0x14000dbbb  mov     [rbp+47h+ClientSecurityQos.ImpersonationLevel], 2
0x14000dbc2  lea     rdx, [rbp+47h+ClientSecurityQos]; ClientSecurityQos
0x14000dbc6  mov     word ptr [rbp+47h+ClientSecurityQos.ContextTrackingMode], 101h
0x14000dbcc  xor     r8d, r8d; RemoteSession
0x14000dbcf  mov     rcx, gs:188h; ClientThread
0x14000dbd8  call    cs:__imp_SeCreateClientSecurity
0x14000dbdf  nop     dword ptr [rax+rax+00h]
0x14000dbe4  mov     edi, eax
0x14000dbe6  test    eax, eax
0x14000dbe8  jns     loc_14000DB02
0x14000dbee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbf5  lea     rdx, WPP_GLOBAL_Control
0x14000dbfc  cmp     rcx, rdx
0x14000dbff  jz      short loc_14000DC22
0x14000dc01  test    dword ptr [rcx+2Ch], 20000h
0x14000dc08  jz      short loc_14000DC22
0x14000dc0a  mov     rcx, [rcx+18h]
0x14000dc0e  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000dc15  mov     edx, 11h
0x14000dc1a  mov     r9d, eax
0x14000dc1d  call    WPP_SF_d
0x14000dc22  mov     rdx, rbx; Entry
0x14000dc25  lea     rcx, Lookaside; Lookaside
0x14000dc2c  call    cs:__imp_ExFreeToPagedLookasideList
0x14000dc33  nop     dword ptr [rax+rax+00h]
0x14000dc38  jmp     loc_14000DAAD
0x14000dc3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc44  lea     rdx, WPP_GLOBAL_Control
0x14000dc4b  cmp     rcx, rdx
0x14000dc4e  jz      loc_14000DA7D
0x14000dc54  test    dword ptr [rcx+2Ch], 40000h
0x14000dc5b  jz      loc_14000DA7D
0x14000dc61  mov     rcx, [rcx+18h]
0x14000dc65  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000dc6c  mov     edx, 0Bh
0x14000dc71  mov     r9d, eax
0x14000dc74  call    WPP_SF_d
0x14000dc79  jmp     loc_14000DA7D
0x14000dc7e  lea     rcx, [rbp+47h+ClientContext]
0x14000dc82  call    cs:__imp_SeDeleteClientSecurity
0x14000dc89  nop     dword ptr [rax+rax+00h]
0x14000dc8e  jmp     loc_14000DAAD
```
