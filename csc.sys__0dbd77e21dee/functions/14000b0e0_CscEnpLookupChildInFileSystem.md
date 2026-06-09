# CscEnpLookupChildInFileSystem

- ea: `0x14000b0e0`
- end: `0x14000b598`
- name: `CscEnpLookupChildInFileSystem`
- size: `1208`
- prototype: `__int64 __fastcall(unsigned __int64, struct _LIST_ENTRY *, _BYTE *, struct _UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140073330`

## callees

- `0x14000b0e0`
- `0x14000b5a0`
- `0x14000c5f8`
- `0x140010e20`
- `0x140012d20`
- `0x1400169d4`
- `0x140018930`
- `0x14002f010`
- `0x14002f0f0`
- `0x1400683ac`
- `0x14006d870`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b3d5`
- `ntoskrnl!KeInitializeEvent` at `0x14000b3d5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000b178`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000b178`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b26a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b4df`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b26a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b4df`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000b161`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000b161`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b412`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b43a`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b412`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000b43a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b2eb`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000b2eb`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000b52e`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000b52e`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000b48b`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000b48b`
- `ntoskrnl!IoGetStackLimits` at `0x14000b22a`
- `ntoskrnl!IoGetStackLimits` at `0x14000b22a`

## pseudocode

```c
__int64 __fastcall CscEnpLookupChildInFileSystem(
        unsigned __int64 a1,
        struct _LIST_ENTRY *a2,
        _BYTE *a3,
        struct _UNICODE_STRING **a4)
{
  struct _LIST_ENTRY *v4; // r14
  __int64 v8; // rax
  struct _LIST_ENTRY *v9; // rbx
  BOOLEAN v10; // r12
  struct _LIST_ENTRY *v11; // rax
  __int64 v12; // rdx
  int *v13; // rdi
  char v14; // r14
  int Blink; // ebx
  struct _UNICODE_STRING *v16; // rax
  NTSTATUS v18; // eax
  int v19; // ecx
  unsigned int v20; // ecx
  BOOLEAN v21; // r12
  __int64 v22; // rcx
  struct _UNICODE_STRING *v23; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  struct _KEVENT Parameter; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 HighLimit; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 LowLimit; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+C0h] [rbp-40h] BYREF

  v4 = *(struct _LIST_ENTRY **)(a1 + 144);
  v28 = a3;
  Handle = 0;
  v23 = 0;
  v32 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = *(struct _LIST_ENTRY **)(v8 + 24);
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&ClientContext, 0, sizeof(ClientContext));
  v10 = KeAreAllApcsDisabled();
  v11 = (struct _LIST_ENTRY *)ExAllocateFromPagedLookasideList(&Lookaside);
  v13 = (int *)v11;
  if ( !v11 )
  {
    Blink = -1073741670;
    goto LABEL_8;
  }
  *v11 = 0;
  v11[1] = 0;
  v11[2] = 0;
  v11[3] = 0;
  v11[4] = 0;
  v11[5] = 0;
  v11[6] = 0;
  v11[7] = 0;
  v11[8] = 0;
  v11[7].Blink = v9;
  v11[2].Blink = (struct _LIST_ENTRY *)&Handle;
  v11[3].Blink = v4;
  v11[4].Flink = a2;
  LODWORD(v11[4].Blink) = 1245592;
  HIDWORD(v11[5].Blink) = 7;
  LODWORD(v11[6].Flink) = 1;
  HIDWORD(v11[6].Flink) = 32;
  if ( v10 )
  {
    ClientSecurityQos.Length = 12;
    ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
    *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 257;
    Blink = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, &ClientContext);
    if ( Blink < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)Blink);
      }
      ExFreeToPagedLookasideList(&Lookaside, v13);
      goto LABEL_8;
    }
    *((_QWORD *)v13 + 17) = &ClientContext;
    v14 = 1;
    memset(&Parameter, 0, sizeof(Parameter));
    KeInitializeEvent(&Parameter, NotificationEvent, 0);
    *(_QWORD *)v13 = KeGetCurrentThread();
    *((_QWORD *)v13 + 2) = CscStorepLowIoCreateFilePostedRoutine;
    *((_QWORD *)v13 + 4) = &Parameter;
    *((_QWORD *)v13 + 1) = 0;
    v13[6] = -1;
    v21 = KeSetKernelStackSwapEnable(0);
    Blink = CscStorepLowIoPostWorkItemAndWait(v22, v13, &Parameter);
    if ( v21 )
      KeSetKernelStackSwapEnable(v21);
    if ( Blink >= 0 )
      Blink = v13[6];
  }
  else
  {
    Parameter.Header.WaitListHead.Flink = v11;
    Parameter.Header.WaitListHead.Blink = 0;
    *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoCreateFilePostedRoutine;
    HighLimit = 0;
    LowLimit = 0;
    v14 = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
    {
LABEL_4:
      Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
      goto LABEL_5;
    }
    v18 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v18);
      }
      goto LABEL_4;
    }
    Blink = (int)Parameter.Header.WaitListHead.Blink;
  }
LABEL_5:
  ExFreeToPagedLookasideList(&Lookaside, v13);
  if ( v14 )
    SeDeleteClientSecurity(&ClientContext);
  if ( Blink >= 0 )
  {
    Blink = CscStorepLowIoDisableImplicitTimeUpdates(Handle);
    if ( Blink < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
      }
    }
    else
    {
      *(_QWORD *)&v30 = Handle;
      v31 = 0;
      v32 = 0;
      v29 = a1;
      *((_QWORD *)&v30 + 1) = a2;
      Blink = CscEnpCreateEntry(&v23, v28, (PWSTR *)&v29);
      if ( Blink >= 0 )
      {
        Handle = 0;
        v19 = *(_DWORD *)&v23[12].Length;
        if ( (v19 & 0x100000) != 0 || (*(_DWORD *)(a1 + 192) & 0x20000) != 0 )
          v20 = v19 | 0x20000;
        else
          v20 = v19 & 0xFFFDFFFF;
        *(_DWORD *)&v23[12].Length = v20;
        Blink = CscEnpQuotaRecoverEntry(v23);
        if ( Blink >= 0 )
          goto LABEL_19;
      }
    }
  }
LABEL_8:
  if ( Handle )
    CscStorepLowIoClose(Handle);
  v16 = v23;
  if ( v23 )
  {
    LOBYTE(v12) = 1;
    CscEnpDereferenceEntryEx((__int64)&v23, v12);
LABEL_19:
    v16 = v23;
  }
  *a4 = v16;
  return (unsigned int)Blink;
}

```

## disassembly

```asm
0x14000b0e0  push    rbp
0x14000b0e2  push    rbx
0x14000b0e3  push    rsi
0x14000b0e4  push    rdi
0x14000b0e5  push    r12
0x14000b0e7  push    r13
0x14000b0e9  push    r14
0x14000b0eb  push    r15
0x14000b0ed  lea     rbp, [rsp-28h]
0x14000b0f2  sub     rsp, 128h
0x14000b0f9  mov     rax, cs:__security_cookie
0x14000b100  xor     rax, rsp
0x14000b103  mov     [rbp+60h+var_50], rax
0x14000b107  mov     r14, [rcx+90h]
0x14000b10e  xorps   xmm0, xmm0
0x14000b111  xor     eax, eax
0x14000b113  mov     [rsp+160h+var_F8], r8
0x14000b118  mov     [rsp+160h+Handle], rax
0x14000b11d  mov     rsi, r9
0x14000b120  mov     [rsp+160h+var_130], rax
0x14000b125  mov     r13, rdx
0x14000b128  mov     [rbp+60h+var_C0], rax
0x14000b12c  mov     r15, rcx
0x14000b12f  mov     rax, [rcx+8]
0x14000b133  movups  [rsp+160h+var_F0], xmm0
0x14000b138  movups  [rbp+60h+var_E0], xmm0
0x14000b13c  movups  [rbp+60h+var_D0], xmm0
0x14000b140  mov     rbx, [rax+18h]
0x14000b144  xor     eax, eax
0x14000b146  mov     qword ptr [rbp+60h+ClientSecurityQos.Length], rax
0x14000b14a  mov     dword ptr [rbp+60h+ClientSecurityQos.ContextTrackingMode], eax
0x14000b14d  mov     qword ptr [rbp+60h+ClientContext.ClientTokenControl.TokenSource.SourceIdentifier.HighPart], rax
0x14000b151  movups  xmmword ptr [rbp+60h+ClientContext.SecurityQos.Length], xmm0
0x14000b155  movups  xmmword ptr [rbp+60h+ClientContext.ClientToken], xmm0
0x14000b159  movups  xmmword ptr [rbp+60h+ClientContext.ClientTokenControl.TokenId.HighPart], xmm0
0x14000b15d  movups  xmmword ptr [rbp+60h+ClientContext.ClientTokenControl.ModifiedId.HighPart], xmm0
0x14000b161  call    cs:__imp_KeAreAllApcsDisabled
0x14000b168  nop     dword ptr [rax+rax+00h]
0x14000b16d  lea     rcx, Lookaside; Lookaside
0x14000b174  movzx   r12d, al
0x14000b178  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000b17f  nop     dword ptr [rax+rax+00h]
0x14000b184  mov     rdi, rax
0x14000b187  test    rax, rax
0x14000b18a  jz      loc_14000B459
0x14000b190  xorps   xmm0, xmm0
0x14000b193  movups  xmmword ptr [rax], xmm0
0x14000b196  movups  xmmword ptr [rax+10h], xmm0
0x14000b19a  movups  xmmword ptr [rax+20h], xmm0
0x14000b19e  movups  xmmword ptr [rax+30h], xmm0
0x14000b1a2  movups  xmmword ptr [rax+40h], xmm0
0x14000b1a6  movups  xmmword ptr [rax+50h], xmm0
0x14000b1aa  movups  xmmword ptr [rax+60h], xmm0
0x14000b1ae  movups  xmmword ptr [rax+70h], xmm0
0x14000b1b2  movups  xmmword ptr [rax+80h], xmm0
0x14000b1b9  mov     [rdi+78h], rbx
0x14000b1bd  lea     rax, [rsp+160h+Handle]
0x14000b1c2  mov     [rdi+28h], rax
0x14000b1c6  lea     rbx, WPP_GLOBAL_Control
0x14000b1cd  mov     [rdi+38h], r14
0x14000b1d1  mov     [rdi+40h], r13
0x14000b1d5  mov     dword ptr [rdi+48h], 130198h
0x14000b1dc  mov     dword ptr [rdi+5Ch], 7
0x14000b1e3  mov     dword ptr [rdi+60h], 1
0x14000b1ea  mov     dword ptr [rdi+64h], 20h ; ' '
0x14000b1f1  test    r12b, r12b
0x14000b1f4  jnz     loc_14000B463
0x14000b1fa  xor     r12d, r12d
0x14000b1fd  mov     qword ptr [rsp+160h+Parameter+8], rdi
0x14000b202  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000b209  mov     [rsp+160h+var_110], r12
0x14000b20e  lea     rdx, [rsp+160h+HighLimit]; HighLimit
0x14000b213  mov     qword ptr [rsp+160h+Parameter], rax
0x14000b218  lea     rcx, [rsp+160h+LowLimit]; LowLimit
0x14000b21d  mov     [rsp+160h+HighLimit], r12
0x14000b222  mov     [rsp+160h+LowLimit], r12
0x14000b227  xor     r14b, r14b
0x14000b22a  call    cs:__imp_IoGetStackLimits
0x14000b231  nop     dword ptr [rax+rax+00h]
0x14000b236  mov     eax, cs:dword_14003BD20
0x14000b23c  lea     rcx, [rsp+160h+HighLimit]
0x14000b241  sub     rcx, [rsp+160h+LowLimit]
0x14000b246  cmp     rcx, rax
0x14000b249  jb      loc_14000B2D1
0x14000b24f  mov     rcx, qword ptr [rsp+160h+Parameter+8]
0x14000b254  mov     rax, qword ptr [rsp+160h+Parameter]
0x14000b259  call    _guard_dispatch_icall
0x14000b25e  mov     ebx, eax
0x14000b260  mov     rdx, rdi; Entry
0x14000b263  lea     rcx, Lookaside; Lookaside
0x14000b26a  call    cs:__imp_ExFreeToPagedLookasideList
0x14000b271  nop     dword ptr [rax+rax+00h]
0x14000b276  test    r14b, r14b
0x14000b279  jnz     loc_14000B52A
0x14000b27f  test    ebx, ebx
0x14000b281  jns     loc_14000B308
0x14000b287  mov     rcx, [rsp+160h+Handle]; Handle
0x14000b28c  test    rcx, rcx
0x14000b28f  jnz     loc_14000B57D
0x14000b295  test    ebx, ebx
0x14000b297  jns     loc_14000B391
0x14000b29d  mov     rax, [rsp+160h+var_130]
0x14000b2a2  test    rax, rax
0x14000b2a5  jnz     loc_14000B587
0x14000b2ab  mov     [rsi], rax
0x14000b2ae  mov     eax, ebx
0x14000b2b0  mov     rcx, [rbp+60h+var_50]
0x14000b2b4  xor     rcx, rsp; StackCookie
0x14000b2b7  call    __security_check_cookie
0x14000b2bc  add     rsp, 128h
0x14000b2c3  pop     r15
0x14000b2c5  pop     r14
0x14000b2c7  pop     r13
0x14000b2c9  pop     r12
0x14000b2cb  pop     rdi
0x14000b2cc  pop     rsi
0x14000b2cd  pop     rbx
0x14000b2ce  pop     rbp
0x14000b2cf  retn
0x14000b2d1  xor     r9d, r9d; Wait
0x14000b2d4  mov     [rsp+160h+Context], r12; Context
0x14000b2d9  mov     r8d, 6000h; Size
0x14000b2df  lea     rdx, [rsp+160h+Parameter]; Parameter
0x14000b2e4  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000b2eb  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000b2f2  nop     dword ptr [rax+rax+00h]
0x14000b2f7  test    eax, eax
0x14000b2f9  js      loc_14000B4F0
0x14000b2ff  mov     ebx, dword ptr [rsp+160h+var_110]
0x14000b303  jmp     loc_14000B260
0x14000b308  mov     rcx, [rsp+160h+Handle]
0x14000b30d  call    CscStorepLowIoDisableImplicitTimeUpdates
0x14000b312  mov     ebx, eax
0x14000b314  test    eax, eax
0x14000b316  js      loc_14000B53F
0x14000b31c  mov     rax, [rsp+160h+Handle]
0x14000b321  lea     r8, [rsp+160h+var_F0]
0x14000b326  mov     rdx, [rsp+160h+var_F8]
0x14000b32b  lea     rcx, [rsp+160h+var_130]
0x14000b330  xorps   xmm0, xmm0
0x14000b333  mov     qword ptr [rbp+60h+var_E0], rax
0x14000b337  movdqu  [rbp+60h+var_D0], xmm0
0x14000b33c  mov     qword ptr [rsp+160h+var_F0+8], r12
0x14000b341  mov     [rbp+60h+var_C0], r12
0x14000b345  mov     qword ptr [rsp+160h+var_F0], r15
0x14000b34a  mov     qword ptr [rbp+60h+var_E0+8], r13
0x14000b34e  call    CscEnpCreateEntry
0x14000b353  mov     ebx, eax
0x14000b355  test    eax, eax
0x14000b357  js      loc_14000B287
0x14000b35d  mov     rdx, [rsp+160h+var_130]
0x14000b362  mov     [rsp+160h+Handle], r12
0x14000b367  mov     ecx, [rdx+0C0h]
0x14000b36d  bt      ecx, 14h
0x14000b371  jnb     short loc_14000B39B
0x14000b373  bts     ecx, 11h
0x14000b377  mov     [rdx+0C0h], ecx
0x14000b37d  mov     rcx, [rsp+160h+var_130]
0x14000b382  call    CscEnpQuotaRecoverEntry
0x14000b387  mov     ebx, eax
0x14000b389  test    eax, eax
0x14000b38b  js      loc_14000B287
0x14000b391  mov     rax, [rsp+160h+var_130]
0x14000b396  jmp     loc_14000B2AB
0x14000b39b  test    dword ptr [r15+0C0h], 20000h
0x14000b3a6  jnz     short loc_14000B373
0x14000b3a8  btr     ecx, 11h
0x14000b3ac  jmp     short loc_14000B377
0x14000b3ae  lea     rax, [rbp+60h+ClientContext]
0x14000b3b2  xorps   xmm0, xmm0
0x14000b3b5  mov     [rdi+88h], rax
0x14000b3bc  lea     rcx, [rsp+160h+Parameter]; Event
0x14000b3c1  xor     eax, eax
0x14000b3c3  xor     r8d, r8d; State
0x14000b3c6  xor     edx, edx; Type
0x14000b3c8  mov     [rsp+160h+var_110], rax
0x14000b3cd  mov     r14b, 1
0x14000b3d0  movups  [rsp+160h+Parameter], xmm0
0x14000b3d5  call    cs:__imp_KeInitializeEvent
0x14000b3dc  nop     dword ptr [rax+rax+00h]
0x14000b3e1  mov     rax, gs:188h
0x14000b3ea  xor     ecx, ecx; Enable
0x14000b3ec  mov     [rdi], rax
0x14000b3ef  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000b3f6  mov     [rdi+10h], rax
0x14000b3fa  lea     rax, [rsp+160h+Parameter]
0x14000b3ff  mov     [rdi+20h], rax
0x14000b403  mov     qword ptr [rdi+8], 0
0x14000b40b  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x14000b412  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000b419  nop     dword ptr [rax+rax+00h]
0x14000b41e  lea     r8, [rsp+160h+Parameter]
0x14000b423  mov     rdx, rdi
0x14000b426  movzx   r12d, al
0x14000b42a  call    CscStorepLowIoPostWorkItemAndWait
0x14000b42f  mov     ebx, eax
0x14000b431  test    r12b, r12b
0x14000b434  jz      short loc_14000B446
0x14000b436  movzx   ecx, r12b; Enable
0x14000b43a  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000b441  nop     dword ptr [rax+rax+00h]
0x14000b446  xor     r12d, r12d
0x14000b449  test    ebx, ebx
0x14000b44b  js      loc_14000B260
0x14000b451  mov     ebx, [rdi+18h]
0x14000b454  jmp     loc_14000B260
0x14000b459  mov     ebx, 0C000009Ah
0x14000b45e  jmp     loc_14000B287
0x14000b463  mov     [rbp+60h+ClientSecurityQos.Length], 0Ch
0x14000b46a  lea     r9, [rbp+60h+ClientContext]; ClientContext
0x14000b46e  mov     [rbp+60h+ClientSecurityQos.ImpersonationLevel], 2
0x14000b475  lea     rdx, [rbp+60h+ClientSecurityQos]; ClientSecurityQos
0x14000b479  mov     word ptr [rbp+60h+ClientSecurityQos.ContextTrackingMode], 101h
0x14000b47f  xor     r8d, r8d; RemoteSession
0x14000b482  mov     rcx, gs:188h; ClientThread
0x14000b48b  call    cs:__imp_SeCreateClientSecurity
0x14000b492  nop     dword ptr [rax+rax+00h]
0x14000b497  mov     ebx, eax
0x14000b499  test    eax, eax
0x14000b49b  jns     loc_14000B3AE
0x14000b4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4a8  lea     rax, WPP_GLOBAL_Control
0x14000b4af  cmp     rcx, rax
0x14000b4b2  jz      short loc_14000B4D5
0x14000b4b4  test    dword ptr [rcx+2Ch], 20000h
0x14000b4bb  jz      short loc_14000B4D5
0x14000b4bd  mov     rcx, [rcx+18h]
0x14000b4c1  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000b4c8  mov     edx, 11h
0x14000b4cd  mov     r9d, ebx
0x14000b4d0  call    WPP_SF_d
0x14000b4d5  mov     rdx, rdi; Entry
0x14000b4d8  lea     rcx, Lookaside; Lookaside
0x14000b4df  call    cs:__imp_ExFreeToPagedLookasideList
0x14000b4e6  nop     dword ptr [rax+rax+00h]
0x14000b4eb  jmp     loc_14000B287
0x14000b4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4f7  cmp     rcx, rbx
0x14000b4fa  jz      loc_14000B24F
0x14000b500  test    dword ptr [rcx+2Ch], 40000h
0x14000b507  jz      loc_14000B24F
0x14000b50d  mov     rcx, [rcx+18h]
0x14000b511  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000b518  mov     edx, 0Bh
0x14000b51d  mov     r9d, eax
0x14000b520  call    WPP_SF_d
0x14000b525  jmp     loc_14000B24F
0x14000b52a  lea     rcx, [rbp+60h+ClientContext]
0x14000b52e  call    cs:__imp_SeDeleteClientSecurity
0x14000b535  nop     dword ptr [rax+rax+00h]
0x14000b53a  jmp     loc_14000B27F
0x14000b53f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b546  lea     rax, WPP_GLOBAL_Control
0x14000b54d  cmp     rcx, rax
0x14000b550  jz      loc_14000B287
0x14000b556  test    dword ptr [rcx+2Ch], 10000h
0x14000b55d  jz      loc_14000B287
0x14000b563  mov     rcx, [rcx+18h]
0x14000b567  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000b56e  mov     edx, 23h ; '#'
0x14000b573  call    WPP_SF_
0x14000b578  jmp     loc_14000B287
0x14000b57d  call    CscStorepLowIoClose
0x14000b582  jmp     loc_14000B295
0x14000b587  mov     dl, 1
0x14000b589  lea     rcx, [rsp+160h+var_130]
0x14000b58e  call    CscEnpDereferenceEntryEx
0x14000b593  jmp     loc_14000B391
```
