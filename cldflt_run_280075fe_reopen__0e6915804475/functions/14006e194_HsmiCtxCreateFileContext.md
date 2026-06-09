# HsmiCtxCreateFileContext

- ea: `0x14006e194`
- end: `0x14006e447`
- name: `HsmiCtxCreateFileContext`
- size: `691`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006df40`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14001e220`
- `0x14001e580`
- `0x14006e194`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006e253`
- `ntoskrnl!KeInitializeEvent` at `0x14006e2a8`
- `ntoskrnl!KeInitializeEvent` at `0x14006e253`
- `ntoskrnl!KeInitializeEvent` at `0x14006e2a8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006e28f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006e28f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006e267`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006e267`
- `FLTMGR!FltQueryInformationFile` at `0x14006e2e7`
- `FLTMGR!FltQueryInformationFile` at `0x14006e2e7`
- `FLTMGR!FltReferenceContext` at `0x14006e223`
- `FLTMGR!FltReferenceContext` at `0x14006e223`
- `FLTMGR!FltAllocateContext` at `0x14006e1e0`
- `FLTMGR!FltAllocateContext` at `0x14006e1e0`
- `FLTMGR!FltInitializePushLock` at `0x14006e237`
- `FLTMGR!FltInitializePushLock` at `0x14006e27b`
- `FLTMGR!FltInitializePushLock` at `0x14006e237`
- `FLTMGR!FltInitializePushLock` at `0x14006e27b`
- `FLTMGR!FltReleaseContext` at `0x14006e436`
- `FLTMGR!FltReleaseContext` at `0x14006e436`

## pseudocode

```c
__int64 __fastcall HsmiCtxCreateFileContext(
        struct _FLT_INSTANCE **Context,
        PFILE_OBJECT FileObject,
        __int64 a3,
        PFLT_CONTEXT *a4)
{
  __int64 InformationFile; // rbx
  struct _FLT_INSTANCE *v9; // rcx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  _QWORD FileInformation[3]; // [rsp+40h] [rbp-18h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+A8h] [rbp+50h] BYREF

  *a4 = 0;
  Contexta = 0;
  InformationFile = (unsigned int)FltAllocateContext(Filter, 4u, 0xF0u, (POOL_TYPE)512, &Contexta);
  HsmDbgBreakOnStatus(InformationFile);
  if ( (int)InformationFile < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_8;
    }
    v12 = 14;
    goto LABEL_19;
  }
  memset(Contexta, 0, 0xF0u);
  *(_DWORD *)Contexta = 1665561416;
  *((_QWORD *)Contexta + 2) = Context;
  FltReferenceContext(Context);
  FltInitializePushLock((PULONG_PTR)Contexta + 3);
  KeInitializeEvent((PRKEVENT)Contexta + 4, SynchronizationEvent, 1u);
  ExInitializeResourceLite((PERESOURCE)((char *)Contexta + 120));
  FltInitializePushLock((PULONG_PTR)Contexta + 6);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)Contexta + 7);
  KeInitializeEvent((PRKEVENT)((char *)Contexta + 64), NotificationEvent, 1u);
  if ( (FileObject->Flags & 0x400000) == 0 )
  {
    v9 = Context[4];
    FileInformation[0] = 0;
    InformationFile = (unsigned int)FltQueryInformationFile(
                                      v9,
                                      FileObject,
                                      FileInformation,
                                      8u,
                                      FileInternalInformation,
                                      0);
    HsmDbgBreakOnStatus(InformationFile);
    if ( (int)InformationFile >= 0 )
    {
      *((_QWORD *)Contexta + 4) = FileInformation[0];
      goto LABEL_5;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_8;
    }
    v12 = 15;
LABEL_19:
    WPP_SF_qqd(v11->AttachedDevice, v12, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, Context, FileObject);
    goto LABEL_8;
  }
LABEL_5:
  if ( qword_1400296F8
    && (LODWORD(InformationFile) = qword_1400296F8(Contexta, Context[2], a3, (char *)Contexta + 8),
        HsmDbgBreakOnStatus((unsigned int)InformationFile),
        (int)InformationFile < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        Context,
        FileObject,
        Contexta,
        InformationFile);
    }
  }
  else
  {
    *a4 = Contexta;
    Contexta = 0;
  }
LABEL_8:
  if ( Contexta )
    FltReleaseContext(Contexta);
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x14006e194  push    rbp
0x14006e196  push    rbx
0x14006e197  push    rsi
0x14006e198  push    rdi
0x14006e199  push    r14
0x14006e19b  push    r15
0x14006e19d  mov     rbp, rsp
0x14006e1a0  sub     rsp, 58h
0x14006e1a4  mov     qword ptr [r9], 0
0x14006e1ab  lea     rax, [rbp+Context]
0x14006e1af  mov     r14, r9
0x14006e1b2  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x14006e1b7  mov     r15, r8
0x14006e1ba  mov     [rbp+Context], 0
0x14006e1c2  mov     rsi, rdx
0x14006e1c5  mov     rdi, rcx
0x14006e1c8  mov     rcx, cs:Filter; Filter
0x14006e1cf  mov     edx, 4; ContextType
0x14006e1d4  mov     r9d, 200h; PoolType
0x14006e1da  mov     r8d, 0F0h; ContextSize
0x14006e1e0  call    cs:__imp_FltAllocateContext
0x14006e1e7  nop     dword ptr [rax+rax+00h]
0x14006e1ec  mov     ecx, eax
0x14006e1ee  mov     ebx, eax
0x14006e1f0  call    HsmDbgBreakOnStatus
0x14006e1f5  test    ebx, ebx
0x14006e1f7  js      loc_14006E36D
0x14006e1fd  mov     rcx, [rbp+Context]; void *
0x14006e201  xor     edx, edx; Val
0x14006e203  mov     r8d, 0F0h; Size
0x14006e209  call    memset
0x14006e20e  mov     rax, [rbp+Context]
0x14006e212  mov     rcx, rdi; Context
0x14006e215  mov     dword ptr [rax], 63467348h
0x14006e21b  mov     rax, [rbp+Context]
0x14006e21f  mov     [rax+10h], rdi
0x14006e223  call    cs:__imp_FltReferenceContext
0x14006e22a  nop     dword ptr [rax+rax+00h]
0x14006e22f  mov     rcx, [rbp+Context]
0x14006e233  add     rcx, 18h; PushLock
0x14006e237  call    cs:__imp_FltInitializePushLock
0x14006e23e  nop     dword ptr [rax+rax+00h]
0x14006e243  mov     rcx, [rbp+Context]
0x14006e247  mov     r8b, 1; State
0x14006e24a  add     rcx, 60h ; '`'; Event
0x14006e24e  mov     edx, 1; Type
0x14006e253  call    cs:__imp_KeInitializeEvent
0x14006e25a  nop     dword ptr [rax+rax+00h]
0x14006e25f  mov     rcx, [rbp+Context]
0x14006e263  add     rcx, 78h ; 'x'; Resource
0x14006e267  call    cs:__imp_ExInitializeResourceLite
0x14006e26e  nop     dword ptr [rax+rax+00h]
0x14006e273  mov     rcx, [rbp+Context]
0x14006e277  add     rcx, 30h ; '0'; PushLock
0x14006e27b  call    cs:__imp_FltInitializePushLock
0x14006e282  nop     dword ptr [rax+rax+00h]
0x14006e287  mov     rcx, [rbp+Context]
0x14006e28b  add     rcx, 38h ; '8'; RunRef
0x14006e28f  call    cs:__imp_ExInitializeRundownProtection
0x14006e296  nop     dword ptr [rax+rax+00h]
0x14006e29b  mov     rcx, [rbp+Context]
0x14006e29f  mov     r8b, 1; State
0x14006e2a2  add     rcx, 40h ; '@'; Event
0x14006e2a6  xor     edx, edx; Type
0x14006e2a8  call    cs:__imp_KeInitializeEvent
0x14006e2af  nop     dword ptr [rax+rax+00h]
0x14006e2b4  test    dword ptr [rsi+50h], 400000h
0x14006e2bb  jnz     short loc_14006E310
0x14006e2bd  mov     rcx, [rdi+20h]; Instance
0x14006e2c1  lea     r8, [rbp+FileInformation]; FileInformation
0x14006e2c5  mov     [rsp+58h+LengthReturned], 0; LengthReturned
0x14006e2ce  mov     r9d, 8; Length
0x14006e2d4  mov     rdx, rsi; FileObject
0x14006e2d7  mov     dword ptr [rsp+58h+ReturnedContext], 6; FileInformationClass
0x14006e2df  mov     [rbp+FileInformation], 0
0x14006e2e7  call    cs:__imp_FltQueryInformationFile
0x14006e2ee  nop     dword ptr [rax+rax+00h]
0x14006e2f3  mov     ecx, eax
0x14006e2f5  mov     ebx, eax
0x14006e2f7  call    HsmDbgBreakOnStatus
0x14006e2fc  test    ebx, ebx
0x14006e2fe  js      loc_14006E395
0x14006e304  mov     rcx, [rbp+Context]
0x14006e308  mov     rax, [rbp+FileInformation]
0x14006e30c  mov     [rcx+20h], rax
0x14006e310  mov     rax, cs:qword_1400296F8
0x14006e317  test    rax, rax
0x14006e31a  jz      short loc_14006E341
0x14006e31c  mov     rcx, [rbp+Context]
0x14006e320  mov     r8, r15
0x14006e323  mov     rdx, [rdi+10h]
0x14006e327  lea     r9, [rcx+8]
0x14006e32b  call    _guard_dispatch_icall
0x14006e330  mov     ecx, eax
0x14006e332  mov     ebx, eax
0x14006e334  call    HsmDbgBreakOnStatus
0x14006e339  test    ebx, ebx
0x14006e33b  js      loc_14006E3DB
0x14006e341  mov     rax, [rbp+Context]
0x14006e345  mov     [r14], rax
0x14006e348  mov     [rbp+Context], 0
0x14006e350  mov     rcx, [rbp+Context]; Context
0x14006e354  test    rcx, rcx
0x14006e357  jnz     loc_14006E436
0x14006e35d  mov     eax, ebx
0x14006e35f  add     rsp, 58h
0x14006e363  pop     r15
0x14006e365  pop     r14
0x14006e367  pop     rdi
0x14006e368  pop     rsi
0x14006e369  pop     rbx
0x14006e36a  pop     rbp
0x14006e36b  retn
0x14006e36d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e374  lea     rax, WPP_GLOBAL_Control
0x14006e37b  cmp     rcx, rax
0x14006e37e  jz      short loc_14006E350
0x14006e380  mov     edx, [rcx+2Ch]
0x14006e383  test    dl, 1
0x14006e386  jz      short loc_14006E350
0x14006e388  cmp     byte ptr [rcx+29h], 2
0x14006e38c  jb      short loc_14006E350
0x14006e38e  mov     edx, 0Eh
0x14006e393  jmp     short loc_14006E3BA
0x14006e395  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e39c  lea     rax, WPP_GLOBAL_Control
0x14006e3a3  cmp     rcx, rax
0x14006e3a6  jz      short loc_14006E350
0x14006e3a8  mov     eax, [rcx+2Ch]
0x14006e3ab  test    al, 1
0x14006e3ad  jz      short loc_14006E350
0x14006e3af  cmp     byte ptr [rcx+29h], 2
0x14006e3b3  jb      short loc_14006E350
0x14006e3b5  mov     edx, 0Fh
0x14006e3ba  mov     rcx, [rcx+18h]
0x14006e3be  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e3c5  mov     dword ptr [rsp+58h+LengthReturned], ebx
0x14006e3c9  mov     r9, rdi
0x14006e3cc  mov     [rsp+58h+ReturnedContext], rsi
0x14006e3d1  call    WPP_SF_qqd
0x14006e3d6  jmp     loc_14006E350
0x14006e3db  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e3e2  lea     rax, WPP_GLOBAL_Control
0x14006e3e9  cmp     rcx, rax
0x14006e3ec  jz      loc_14006E350
0x14006e3f2  mov     eax, [rcx+2Ch]
0x14006e3f5  test    al, 1
0x14006e3f7  jz      loc_14006E350
0x14006e3fd  cmp     byte ptr [rcx+29h], 2
0x14006e401  jb      loc_14006E350
0x14006e407  mov     rax, [rbp+Context]
0x14006e40b  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e412  mov     rcx, [rcx+18h]
0x14006e416  mov     edx, 10h
0x14006e41b  mov     [rsp+58h+var_28], ebx
0x14006e41f  mov     r9, rdi
0x14006e422  mov     [rsp+58h+LengthReturned], rax
0x14006e427  mov     [rsp+58h+ReturnedContext], rsi
0x14006e42c  call    WPP_SF_qqqd
0x14006e431  jmp     loc_14006E350
0x14006e436  call    cs:__imp_FltReleaseContext
0x14006e43d  nop     dword ptr [rax+rax+00h]
0x14006e442  jmp     loc_14006E35D
```
