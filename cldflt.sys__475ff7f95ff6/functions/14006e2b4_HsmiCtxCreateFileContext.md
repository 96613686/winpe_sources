# HsmiCtxCreateFileContext

- ea: `0x14006e2b4`
- end: `0x14006e567`
- name: `HsmiCtxCreateFileContext`
- size: `691`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE **Context, PFILE_OBJECT FileObject, __int64, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006e060`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14001e2a0`
- `0x14001e600`
- `0x14006e2b4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006e373`
- `ntoskrnl!KeInitializeEvent` at `0x14006e3c8`
- `ntoskrnl!KeInitializeEvent` at `0x14006e373`
- `ntoskrnl!KeInitializeEvent` at `0x14006e3c8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006e3af`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006e3af`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006e387`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006e387`
- `FLTMGR!FltQueryInformationFile` at `0x14006e407`
- `FLTMGR!FltQueryInformationFile` at `0x14006e407`
- `FLTMGR!FltReferenceContext` at `0x14006e343`
- `FLTMGR!FltReferenceContext` at `0x14006e343`
- `FLTMGR!FltAllocateContext` at `0x14006e300`
- `FLTMGR!FltAllocateContext` at `0x14006e300`
- `FLTMGR!FltInitializePushLock` at `0x14006e357`
- `FLTMGR!FltInitializePushLock` at `0x14006e39b`
- `FLTMGR!FltInitializePushLock` at `0x14006e357`
- `FLTMGR!FltInitializePushLock` at `0x14006e39b`
- `FLTMGR!FltReleaseContext` at `0x14006e556`
- `FLTMGR!FltReleaseContext` at `0x14006e556`

## pseudocode

```c
__int64 __fastcall HsmiCtxCreateFileContext(
        struct _FLT_INSTANCE **Context,
        PFILE_OBJECT FileObject,
        __int64 a3,
        PFLT_CONTEXT *a4)
{
  NTSTATUS InformationFile; // ebx
  struct _FLT_INSTANCE *v9; // rcx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  _QWORD FileInformation[3]; // [rsp+40h] [rbp-18h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+A8h] [rbp+50h] BYREF

  *a4 = 0;
  Contexta = 0;
  InformationFile = FltAllocateContext(Filter, 4u, 0xF0u, (POOL_TYPE)512, &Contexta);
  HsmDbgBreakOnStatus(InformationFile);
  if ( InformationFile < 0 )
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
    InformationFile = FltQueryInformationFile(v9, FileObject, FileInformation, 8u, FileInternalInformation, 0);
    HsmDbgBreakOnStatus(InformationFile);
    if ( InformationFile >= 0 )
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
    WPP_SF_qqd(
      v11->AttachedDevice,
      v12,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      Context,
      FileObject,
      InformationFile);
    goto LABEL_8;
  }
LABEL_5:
  if ( qword_1400296F8
    && (InformationFile = qword_1400296F8(Contexta, Context[2], a3, (char *)Contexta + 8),
        HsmDbgBreakOnStatus(InformationFile),
        InformationFile < 0) )
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
0x14006e2b4  push    rbp
0x14006e2b6  push    rbx
0x14006e2b7  push    rsi
0x14006e2b8  push    rdi
0x14006e2b9  push    r14
0x14006e2bb  push    r15
0x14006e2bd  mov     rbp, rsp
0x14006e2c0  sub     rsp, 58h
0x14006e2c4  mov     qword ptr [r9], 0
0x14006e2cb  lea     rax, [rbp+Context]
0x14006e2cf  mov     r14, r9
0x14006e2d2  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x14006e2d7  mov     r15, r8
0x14006e2da  mov     [rbp+Context], 0
0x14006e2e2  mov     rsi, rdx
0x14006e2e5  mov     rdi, rcx
0x14006e2e8  mov     rcx, cs:Filter; Filter
0x14006e2ef  mov     edx, 4; ContextType
0x14006e2f4  mov     r9d, 200h; PoolType
0x14006e2fa  mov     r8d, 0F0h; ContextSize
0x14006e300  call    cs:__imp_FltAllocateContext
0x14006e307  nop     dword ptr [rax+rax+00h]
0x14006e30c  mov     ecx, eax
0x14006e30e  mov     ebx, eax
0x14006e310  call    HsmDbgBreakOnStatus
0x14006e315  test    ebx, ebx
0x14006e317  js      loc_14006E48D
0x14006e31d  mov     rcx, [rbp+Context]; void *
0x14006e321  xor     edx, edx; Val
0x14006e323  mov     r8d, 0F0h; Size
0x14006e329  call    memset
0x14006e32e  mov     rax, [rbp+Context]
0x14006e332  mov     rcx, rdi; Context
0x14006e335  mov     dword ptr [rax], 63467348h
0x14006e33b  mov     rax, [rbp+Context]
0x14006e33f  mov     [rax+10h], rdi
0x14006e343  call    cs:__imp_FltReferenceContext
0x14006e34a  nop     dword ptr [rax+rax+00h]
0x14006e34f  mov     rcx, [rbp+Context]
0x14006e353  add     rcx, 18h; PushLock
0x14006e357  call    cs:__imp_FltInitializePushLock
0x14006e35e  nop     dword ptr [rax+rax+00h]
0x14006e363  mov     rcx, [rbp+Context]
0x14006e367  mov     r8b, 1; State
0x14006e36a  add     rcx, 60h ; '`'; Event
0x14006e36e  mov     edx, 1; Type
0x14006e373  call    cs:__imp_KeInitializeEvent
0x14006e37a  nop     dword ptr [rax+rax+00h]
0x14006e37f  mov     rcx, [rbp+Context]
0x14006e383  add     rcx, 78h ; 'x'; Resource
0x14006e387  call    cs:__imp_ExInitializeResourceLite
0x14006e38e  nop     dword ptr [rax+rax+00h]
0x14006e393  mov     rcx, [rbp+Context]
0x14006e397  add     rcx, 30h ; '0'; PushLock
0x14006e39b  call    cs:__imp_FltInitializePushLock
0x14006e3a2  nop     dword ptr [rax+rax+00h]
0x14006e3a7  mov     rcx, [rbp+Context]
0x14006e3ab  add     rcx, 38h ; '8'; RunRef
0x14006e3af  call    cs:__imp_ExInitializeRundownProtection
0x14006e3b6  nop     dword ptr [rax+rax+00h]
0x14006e3bb  mov     rcx, [rbp+Context]
0x14006e3bf  mov     r8b, 1; State
0x14006e3c2  add     rcx, 40h ; '@'; Event
0x14006e3c6  xor     edx, edx; Type
0x14006e3c8  call    cs:__imp_KeInitializeEvent
0x14006e3cf  nop     dword ptr [rax+rax+00h]
0x14006e3d4  test    dword ptr [rsi+50h], 400000h
0x14006e3db  jnz     short loc_14006E430
0x14006e3dd  mov     rcx, [rdi+20h]; Instance
0x14006e3e1  lea     r8, [rbp+FileInformation]; FileInformation
0x14006e3e5  mov     [rsp+58h+LengthReturned], 0; LengthReturned
0x14006e3ee  mov     r9d, 8; Length
0x14006e3f4  mov     rdx, rsi; FileObject
0x14006e3f7  mov     dword ptr [rsp+58h+ReturnedContext], 6; FileInformationClass
0x14006e3ff  mov     [rbp+FileInformation], 0
0x14006e407  call    cs:__imp_FltQueryInformationFile
0x14006e40e  nop     dword ptr [rax+rax+00h]
0x14006e413  mov     ecx, eax
0x14006e415  mov     ebx, eax
0x14006e417  call    HsmDbgBreakOnStatus
0x14006e41c  test    ebx, ebx
0x14006e41e  js      loc_14006E4B5
0x14006e424  mov     rcx, [rbp+Context]
0x14006e428  mov     rax, [rbp+FileInformation]
0x14006e42c  mov     [rcx+20h], rax
0x14006e430  mov     rax, cs:qword_1400296F8
0x14006e437  test    rax, rax
0x14006e43a  jz      short loc_14006E461
0x14006e43c  mov     rcx, [rbp+Context]
0x14006e440  mov     r8, r15
0x14006e443  mov     rdx, [rdi+10h]
0x14006e447  lea     r9, [rcx+8]
0x14006e44b  call    _guard_dispatch_icall
0x14006e450  mov     ecx, eax
0x14006e452  mov     ebx, eax
0x14006e454  call    HsmDbgBreakOnStatus
0x14006e459  test    ebx, ebx
0x14006e45b  js      loc_14006E4FB
0x14006e461  mov     rax, [rbp+Context]
0x14006e465  mov     [r14], rax
0x14006e468  mov     [rbp+Context], 0
0x14006e470  mov     rcx, [rbp+Context]; Context
0x14006e474  test    rcx, rcx
0x14006e477  jnz     loc_14006E556
0x14006e47d  mov     eax, ebx
0x14006e47f  add     rsp, 58h
0x14006e483  pop     r15
0x14006e485  pop     r14
0x14006e487  pop     rdi
0x14006e488  pop     rsi
0x14006e489  pop     rbx
0x14006e48a  pop     rbp
0x14006e48b  retn
0x14006e48d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e494  lea     rax, WPP_GLOBAL_Control
0x14006e49b  cmp     rcx, rax
0x14006e49e  jz      short loc_14006E470
0x14006e4a0  mov     edx, [rcx+2Ch]
0x14006e4a3  test    dl, 1
0x14006e4a6  jz      short loc_14006E470
0x14006e4a8  cmp     byte ptr [rcx+29h], 2
0x14006e4ac  jb      short loc_14006E470
0x14006e4ae  mov     edx, 0Eh
0x14006e4b3  jmp     short loc_14006E4DA
0x14006e4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e4bc  lea     rax, WPP_GLOBAL_Control
0x14006e4c3  cmp     rcx, rax
0x14006e4c6  jz      short loc_14006E470
0x14006e4c8  mov     eax, [rcx+2Ch]
0x14006e4cb  test    al, 1
0x14006e4cd  jz      short loc_14006E470
0x14006e4cf  cmp     byte ptr [rcx+29h], 2
0x14006e4d3  jb      short loc_14006E470
0x14006e4d5  mov     edx, 0Fh
0x14006e4da  mov     rcx, [rcx+18h]
0x14006e4de  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e4e5  mov     dword ptr [rsp+58h+LengthReturned], ebx
0x14006e4e9  mov     r9, rdi
0x14006e4ec  mov     [rsp+58h+ReturnedContext], rsi
0x14006e4f1  call    WPP_SF_qqd
0x14006e4f6  jmp     loc_14006E470
0x14006e4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e502  lea     rax, WPP_GLOBAL_Control
0x14006e509  cmp     rcx, rax
0x14006e50c  jz      loc_14006E470
0x14006e512  mov     eax, [rcx+2Ch]
0x14006e515  test    al, 1
0x14006e517  jz      loc_14006E470
0x14006e51d  cmp     byte ptr [rcx+29h], 2
0x14006e521  jb      loc_14006E470
0x14006e527  mov     rax, [rbp+Context]
0x14006e52b  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e532  mov     rcx, [rcx+18h]
0x14006e536  mov     edx, 10h
0x14006e53b  mov     [rsp+58h+var_28], ebx
0x14006e53f  mov     r9, rdi
0x14006e542  mov     [rsp+58h+LengthReturned], rax
0x14006e547  mov     [rsp+58h+ReturnedContext], rsi
0x14006e54c  call    WPP_SF_qqqd
0x14006e551  jmp     loc_14006E470
0x14006e556  call    cs:__imp_FltReleaseContext
0x14006e55d  nop     dword ptr [rax+rax+00h]
0x14006e562  jmp     loc_14006E47D
```
