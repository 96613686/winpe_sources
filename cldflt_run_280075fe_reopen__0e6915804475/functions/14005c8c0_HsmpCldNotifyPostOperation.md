# HsmpCldNotifyPostOperation

- ea: `0x14005c8c0`
- end: `0x14005cc9b`
- name: `HsmpCldNotifyPostOperation`
- size: `987`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140047b30`
- `0x140054910`
- `0x14005599c`
- `0x14005aaf0`
- `0x14006be80`

## callees

- `0x140003c50`
- `0x140006f40`
- `0x14000ac28`
- `0x14001e220`
- `0x14004c5e0`
- `0x14005c600`
- `0x14005c8c0`
- `0x14005ccb0`
- `0x14005f550`
- `0x140076734`
- `0x140076810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb22`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca43`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca43`
- `FLTMGR!FltGetStreamContext` at `0x14005c919`
- `FLTMGR!FltGetStreamContext` at `0x14005c919`
- `FLTMGR!FltDeleteContext` at `0x14005cc10`
- `FLTMGR!FltDeleteContext` at `0x14005cc10`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c952`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c952`
- `FLTMGR!FltReleaseContext` at `0x14005c976`
- `FLTMGR!FltReleaseContext` at `0x14005c9cf`
- `FLTMGR!FltReleaseContext` at `0x14005c9eb`
- `FLTMGR!FltReleaseContext` at `0x14005c976`
- `FLTMGR!FltReleaseContext` at `0x14005c9cf`
- `FLTMGR!FltReleaseContext` at `0x14005c9eb`

## pseudocode

```c
void __fastcall HsmpCldNotifyPostOperation(
        unsigned int a1,
        struct _FLT_CALLBACK_DATA *a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *StreamHandleContext; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PFILE_OBJECT TargetFileObject; // r12
  PFLT_INSTANCE TargetInstance; // r13
  struct _FLT_INSTANCE *v11; // rdi
  _QWORD *v12; // rbx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v14; // rcx
  _DWORD *Pool2; // rax
  void *v16; // rbp
  void *v17; // rdi
  __int64 v18; // rdx
  __int64 ProcessInfo; // rax
  __int64 v20; // r13
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // [rsp+50h] [rbp-68h]
  __int64 v24; // [rsp+58h] [rbp-60h]
  __int64 v25; // [rsp+60h] [rbp-58h]
  __int128 v26; // [rsp+68h] [rbp-50h] BYREF
  PFLT_CONTEXT Context; // [rsp+C8h] [rbp+10h] BYREF
  int v28; // [rsp+D0h] [rbp+18h]
  __int64 v29; // [rsp+D8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  StreamHandleContext = 0;
  Iopb = a2->Iopb;
  Context = 0;
  TargetFileObject = Iopb->TargetFileObject;
  TargetInstance = Iopb->TargetInstance;
  v26 = 0;
  v11 = Iopb->TargetInstance;
  FltGetStreamContext(v11, Iopb->TargetFileObject, &Context);
  v12 = Context;
  if ( !Context )
    goto LABEL_8;
  if ( (*((_DWORD *)Context + 7) & 1) != 0 )
  {
    if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*((_QWORD *)Context + 2) + 16LL) + 32LL) != v11 )
    {
      v14 = Context;
      goto LABEL_6;
    }
    RequestorProcess = FltGetRequestorProcess(a2);
    if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
    {
      v12 = Context;
      goto LABEL_7;
    }
  }
  else
  {
    if ( !Context )
      goto LABEL_8;
    FltDeleteContext(Context);
  }
  v14 = Context;
LABEL_6:
  FltReleaseContext(v14);
  v12 = 0;
  Context = 0;
LABEL_7:
  if ( v12 )
  {
    v21 = v12[2];
    v22 = *(_QWORD *)(v21 + 16);
    v23 = *(_QWORD *)(v21 + 32);
    v25 = v22;
    if ( (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, struct _FLT_CALLBACK_DATA *, _QWORD))qword_140029758)(
                            a1,
                            v12[1],
                            a2,
                            0) )
    {
      StreamHandleContext = (_QWORD *)HsmpGetStreamHandleContext(
                                        a2,
                                        a2->Iopb->TargetInstance,
                                        a2->Iopb->TargetFileObject);
      Pool2 = (_DWORD *)ExAllocatePool2(256, 24, 1766028104);
      v16 = Pool2;
      if ( Pool2 )
      {
        *Pool2 |= 2u;
        HsmpFillOutAttributionInformation(StreamHandleContext, v12, a2, Pool2);
        HsmDbgBreakOnStatus(0);
        if ( StreamHandleContext )
        {
          v17 = 0;
          HsmpCaptureProcessInfo(StreamHandleContext, a2);
          ProcessInfo = StreamHandleContext[9];
        }
        else
        {
          ProcessInfo = HsmpCreateProcessInfo(v16);
          v17 = (void *)ProcessInfo;
        }
        v24 = ProcessInfo;
        v20 = (unsigned int)HsmiQueryFullFilePath(TargetInstance, v18, TargetFileObject, 257, &v26);
        HsmDbgBreakOnStatus(v20);
        if ( (int)v20 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qqiqd(
              WPP_GLOBAL_Control->AttachedDevice,
              68,
              WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
              v25,
              v12,
              TargetFileObject,
              v23,
              v20);
          }
        }
        else
        {
          ((void (__fastcall *)(_QWORD, struct _FLT_CALLBACK_DATA *, _QWORD, __int128 *, int, __int64, __int64, __int64))qword_140029768)(
            a1,
            a2,
            v12[1],
            &v26,
            v28,
            v29,
            a5,
            v24);
        }
        HsmpCleanupAttributionInformation(v16);
        if ( v17 )
          ExFreePoolWithTag(v17, 0x69507348u);
      }
      else
      {
        HsmDbgBreakOnStatus(3221225626LL);
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqiqd(
            WPP_GLOBAL_Control->AttachedDevice,
            67,
            WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
            v22,
            v12,
            TargetFileObject,
            v23,
            -1073741670);
        }
      }
    }
  }
LABEL_8:
  if ( *((_QWORD *)&v26 + 1) )
    ExFreePoolWithTag(*((PVOID *)&v26 + 1), 0x73557348u);
  if ( v12 )
    FltReleaseContext(v12);
  if ( StreamHandleContext )
    FltReleaseContext(StreamHandleContext);
}

```

## disassembly

```asm
0x14005c8c0  mov     rax, rsp
0x14005c8c3  mov     [rax+20h], r9
0x14005c8c7  mov     [rax+18h], r8d
0x14005c8cb  push    rsi
0x14005c8cc  sub     rsp, 0B0h
0x14005c8d3  mov     [rax+8], rbx
0x14005c8d7  lea     r8, [rax+10h]; Context
0x14005c8db  mov     [rax-18h], rdi
0x14005c8df  xorps   xmm0, xmm0
0x14005c8e2  mov     [rax-20h], r12
0x14005c8e6  xor     esi, esi
0x14005c8e8  mov     [rax-28h], r13
0x14005c8ec  mov     [rax-30h], r14
0x14005c8f0  mov     r14, rdx
0x14005c8f3  mov     rdx, [rdx+10h]
0x14005c8f7  mov     [rax-38h], r15
0x14005c8fb  mov     r15d, ecx
0x14005c8fe  mov     [rax+10h], rsi
0x14005c902  mov     r12, [rdx+8]
0x14005c906  mov     r13, [rdx+10h]
0x14005c90a  movups  xmmword ptr [rax-50h], xmm0
0x14005c90e  mov     rdi, [rdx+10h]
0x14005c912  mov     rdx, [rdx+8]; FileObject
0x14005c916  mov     rcx, rdi; Instance
0x14005c919  call    cs:__imp_FltGetStreamContext
0x14005c920  nop     dword ptr [rax+rax+00h]
0x14005c925  mov     rbx, [rsp+0B8h+Context]
0x14005c92d  test    rbx, rbx
0x14005c930  jz      short loc_14005C995
0x14005c932  mov     eax, [rbx+1Ch]
0x14005c935  test    al, 1
0x14005c937  jz      loc_14005CC04
0x14005c93d  mov     rax, [rbx+10h]
0x14005c941  mov     rcx, [rax+10h]
0x14005c945  cmp     [rcx+20h], rdi
0x14005c949  jnz     loc_14005CC21
0x14005c94f  mov     rcx, r14; CallbackData
0x14005c952  call    cs:__imp_FltGetRequestorProcess
0x14005c959  nop     dword ptr [rax+rax+00h]
0x14005c95e  mov     rcx, rax
0x14005c961  call    HsmOsIsPassThroughModeEnabled
0x14005c966  test    al, al
0x14005c968  jz      loc_14005CC29
0x14005c96e  mov     rcx, [rsp+0B8h+Context]; Context
0x14005c976  call    cs:__imp_FltReleaseContext
0x14005c97d  nop     dword ptr [rax+rax+00h]
0x14005c982  xor     ebx, ebx
0x14005c984  mov     [rsp+0B8h+Context], rbx
0x14005c98c  test    rbx, rbx
0x14005c98f  jnz     loc_14005CB4B
0x14005c995  mov     rcx, [rsp+0B8h+P]; P
0x14005c99a  mov     r15, [rsp+0B8h+var_38]
0x14005c9a2  mov     r14, [rsp+0B8h+var_30]
0x14005c9aa  mov     r13, [rsp+0B8h+var_28]
0x14005c9b2  mov     r12, [rsp+0B8h+var_20]
0x14005c9ba  mov     rdi, [rsp+0B8h+var_18]
0x14005c9c2  test    rcx, rcx
0x14005c9c5  jnz     short loc_14005CA01
0x14005c9c7  test    rbx, rbx
0x14005c9ca  jz      short loc_14005C9DB
0x14005c9cc  mov     rcx, rbx; Context
0x14005c9cf  call    cs:__imp_FltReleaseContext
0x14005c9d6  nop     dword ptr [rax+rax+00h]
0x14005c9db  mov     rbx, [rsp+0B8h+arg_0]
0x14005c9e3  test    rsi, rsi
0x14005c9e6  jz      short loc_14005C9F7
0x14005c9e8  mov     rcx, rsi; Context
0x14005c9eb  call    cs:__imp_FltReleaseContext
0x14005c9f2  nop     dword ptr [rax+rax+00h]
0x14005c9f7  add     rsp, 0B0h
0x14005c9fe  pop     rsi
0x14005c9ff  retn
0x14005ca01  mov     edx, 73557348h; Tag
0x14005ca06  call    cs:__imp_ExFreePoolWithTag
0x14005ca0d  nop     dword ptr [rax+rax+00h]
0x14005ca12  jmp     short loc_14005C9C7
0x14005ca14  mov     rdx, [r14+10h]
0x14005ca18  mov     rcx, r14; CallbackData
0x14005ca1b  mov     [rsp+0B8h+var_10], rbp
0x14005ca23  mov     r8, [rdx+8]; FileObject
0x14005ca27  mov     rdx, [rdx+10h]; Instance
0x14005ca2b  call    HsmpGetStreamHandleContext
0x14005ca30  mov     edx, 18h
0x14005ca35  mov     ecx, 100h
0x14005ca3a  mov     r8d, 69437348h
0x14005ca40  mov     rsi, rax
0x14005ca43  call    cs:__imp_ExAllocatePool2
0x14005ca4a  nop     dword ptr [rax+rax+00h]
0x14005ca4f  mov     rbp, rax
0x14005ca52  test    rax, rax
0x14005ca55  jz      loc_14005CB87
0x14005ca5b  or      dword ptr [rax], 2
0x14005ca5e  mov     r9, rax
0x14005ca61  mov     r8, r14
0x14005ca64  mov     rdx, rbx
0x14005ca67  mov     rcx, rsi
0x14005ca6a  call    HsmpFillOutAttributionInformation
0x14005ca6f  xor     ecx, ecx
0x14005ca71  call    HsmDbgBreakOnStatus
0x14005ca76  test    rsi, rsi
0x14005ca79  jz      loc_14005CB3B
0x14005ca7f  xor     edi, edi
0x14005ca81  mov     rdx, r14
0x14005ca84  mov     rcx, rsi
0x14005ca87  call    HsmpCaptureProcessInfo
0x14005ca8c  mov     rax, [rsi+48h]
0x14005ca90  mov     [rsp+0B8h+var_60], rax
0x14005ca95  mov     r9d, 101h
0x14005ca9b  lea     rax, [rsp+0B8h+var_50]
0x14005caa0  mov     r8, r12
0x14005caa3  mov     rcx, r13
0x14005caa6  mov     [rsp+0B8h+var_98], rax
0x14005caab  call    HsmiQueryFullFilePath
0x14005cab0  mov     ecx, eax
0x14005cab2  mov     r13d, eax
0x14005cab5  call    HsmDbgBreakOnStatus
0x14005caba  test    r13d, r13d
0x14005cabd  js      loc_14005CC36
0x14005cac3  mov     rcx, [rsp+0B8h+var_60]
0x14005cac8  lea     r9, [rsp+0B8h+var_50]
0x14005cacd  mov     rdx, [rsp+0B8h+arg_20]
0x14005cad5  mov     rax, cs:qword_140029768
0x14005cadc  mov     r8, [rbx+8]
0x14005cae0  mov     [rsp+0B8h+var_80], rcx
0x14005cae5  mov     rcx, [rsp+0B8h+arg_18]
0x14005caed  mov     [rsp+0B8h+var_88], rdx
0x14005caf2  mov     rdx, r14
0x14005caf5  mov     [rsp+0B8h+var_90], rcx
0x14005cafa  mov     ecx, [rsp+0B8h+arg_10]
0x14005cb01  mov     dword ptr [rsp+0B8h+var_98], ecx
0x14005cb05  mov     ecx, r15d
0x14005cb08  call    _guard_dispatch_icall
0x14005cb0d  mov     rcx, rbp; P
0x14005cb10  call    HsmpCleanupAttributionInformation
0x14005cb15  test    rdi, rdi
0x14005cb18  jz      short loc_14005CB2E
0x14005cb1a  mov     edx, 69507348h; Tag
0x14005cb1f  mov     rcx, rdi; P
0x14005cb22  call    cs:__imp_ExFreePoolWithTag
0x14005cb29  nop     dword ptr [rax+rax+00h]
0x14005cb2e  mov     rbp, [rsp+0B8h+var_10]
0x14005cb36  jmp     loc_14005C995
0x14005cb3b  mov     rcx, rbp
0x14005cb3e  call    HsmpCreateProcessInfo
0x14005cb43  mov     rdi, rax
0x14005cb46  jmp     loc_14005CA90
0x14005cb4b  mov     rax, [rbx+10h]
0x14005cb4f  xor     r9d, r9d
0x14005cb52  mov     rdx, [rbx+8]
0x14005cb56  mov     r8, r14
0x14005cb59  mov     ecx, r15d
0x14005cb5c  mov     rdi, [rax+10h]
0x14005cb60  mov     rax, [rax+20h]
0x14005cb64  mov     [rsp+0B8h+var_68], rax
0x14005cb69  mov     rax, cs:qword_140029758
0x14005cb70  mov     [rsp+0B8h+var_58], rdi
0x14005cb75  call    _guard_dispatch_icall
0x14005cb7a  test    al, al
0x14005cb7c  jz      loc_14005C995
0x14005cb82  jmp     loc_14005CA14
0x14005cb87  mov     ecx, 0C000009Ah
0x14005cb8c  call    HsmDbgBreakOnStatus
0x14005cb91  mov     ecx, 0C000009Ah
0x14005cb96  call    HsmDbgBreakOnStatus
0x14005cb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cba2  lea     rax, WPP_GLOBAL_Control
0x14005cba9  cmp     rcx, rax
0x14005cbac  jz      short loc_14005CB2E
0x14005cbae  mov     eax, [rcx+2Ch]
0x14005cbb1  test    al, 1
0x14005cbb3  jz      loc_14005CB2E
0x14005cbb9  cmp     byte ptr [rcx+29h], 2
0x14005cbbd  jb      loc_14005CB2E
0x14005cbc3  mov     rax, [rsp+0B8h+var_68]
0x14005cbc8  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005cbcf  mov     rcx, [rcx+18h]
0x14005cbd3  mov     edx, 43h ; 'C'
0x14005cbd8  mov     dword ptr [rsp+0B8h+var_80], 0C000009Ah
0x14005cbe0  mov     r9, rdi
0x14005cbe3  mov     [rsp+0B8h+var_88], rax
0x14005cbe8  mov     [rsp+0B8h+var_90], r12
0x14005cbed  mov     [rsp+0B8h+var_98], rbx
0x14005cbf2  call    WPP_SF_qqiqd
0x14005cbf7  mov     rbp, [rsp+0B8h+var_10]
0x14005cbff  jmp     loc_14005C995
0x14005cc04  test    rbx, rbx
0x14005cc07  jz      loc_14005C995
0x14005cc0d  mov     rcx, rbx; Context
0x14005cc10  call    cs:__imp_FltDeleteContext
0x14005cc17  nop     dword ptr [rax+rax+00h]
0x14005cc1c  jmp     loc_14005C96E
0x14005cc21  mov     rcx, rbx
0x14005cc24  jmp     loc_14005C976
0x14005cc29  mov     rbx, [rsp+0B8h+Context]
0x14005cc31  jmp     loc_14005C98C
0x14005cc36  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc3d  lea     rax, WPP_GLOBAL_Control
0x14005cc44  cmp     rcx, rax
0x14005cc47  jz      loc_14005CB0D
0x14005cc4d  mov     edx, [rcx+2Ch]
0x14005cc50  test    dl, 1
0x14005cc53  jz      loc_14005CB0D
0x14005cc59  cmp     byte ptr [rcx+29h], 3
0x14005cc5d  jb      loc_14005CB0D
0x14005cc63  mov     rax, [rsp+0B8h+var_68]
0x14005cc68  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005cc6f  mov     r9, [rsp+0B8h+var_58]
0x14005cc74  mov     edx, 44h ; 'D'
0x14005cc79  mov     rcx, [rcx+18h]
0x14005cc7d  mov     dword ptr [rsp+0B8h+var_80], r13d
0x14005cc82  mov     [rsp+0B8h+var_88], rax
0x14005cc87  mov     [rsp+0B8h+var_90], r12
0x14005cc8c  mov     [rsp+0B8h+var_98], rbx
0x14005cc91  call    WPP_SF_qqiqd
0x14005cc96  jmp     loc_14005CB0D
```
