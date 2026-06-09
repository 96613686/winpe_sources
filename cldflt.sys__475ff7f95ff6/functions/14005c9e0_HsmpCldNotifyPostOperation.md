# HsmpCldNotifyPostOperation

- ea: `0x14005c9e0`
- end: `0x14005cdbb`
- name: `HsmpCldNotifyPostOperation`
- size: `987`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140047c20`
- `0x140054a30`
- `0x140055abc`
- `0x14005ac10`
- `0x14006bfa0`

## callees

- `0x140003c50`
- `0x140006f40`
- `0x14000ac28`
- `0x14001e2a0`
- `0x14004c6d0`
- `0x14005c720`
- `0x14005c9e0`
- `0x14005cdd0`
- `0x14005f670`
- `0x14007686c`
- `0x140076948`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cc42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cc42`
- `ntoskrnl!ExAllocatePool2` at `0x14005cb63`
- `ntoskrnl!ExAllocatePool2` at `0x14005cb63`
- `FLTMGR!FltGetStreamContext` at `0x14005ca39`
- `FLTMGR!FltGetStreamContext` at `0x14005ca39`
- `FLTMGR!FltDeleteContext` at `0x14005cd30`
- `FLTMGR!FltDeleteContext` at `0x14005cd30`
- `FLTMGR!FltGetRequestorProcess` at `0x14005ca72`
- `FLTMGR!FltGetRequestorProcess` at `0x14005ca72`
- `FLTMGR!FltReleaseContext` at `0x14005ca96`
- `FLTMGR!FltReleaseContext` at `0x14005caef`
- `FLTMGR!FltReleaseContext` at `0x14005cb0b`
- `FLTMGR!FltReleaseContext` at `0x14005ca96`
- `FLTMGR!FltReleaseContext` at `0x14005caef`
- `FLTMGR!FltReleaseContext` at `0x14005cb0b`

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
  struct _FILE_OBJECT *TargetFileObject; // r12
  __int64 TargetInstance; // r13
  struct _FLT_INSTANCE *v11; // rdi
  _QWORD *v12; // rbx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v14; // rcx
  _DWORD *Pool2; // rax
  void *v16; // rbp
  void *v17; // rdi
  __int64 v18; // rdx
  __int64 ProcessInfo; // rax
  int v20; // r13d
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
  TargetInstance = (__int64)Iopb->TargetInstance;
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
        v20 = HsmiQueryFullFilePath(TargetInstance, v18, TargetFileObject, 0x101u, &v26);
        HsmDbgBreakOnStatus(v20);
        if ( v20 < 0 )
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
        HsmDbgBreakOnStatus(-1073741670);
        HsmDbgBreakOnStatus(-1073741670);
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
0x14005c9e0  mov     rax, rsp
0x14005c9e3  mov     [rax+20h], r9
0x14005c9e7  mov     [rax+18h], r8d
0x14005c9eb  push    rsi
0x14005c9ec  sub     rsp, 0B0h
0x14005c9f3  mov     [rax+8], rbx
0x14005c9f7  lea     r8, [rax+10h]; Context
0x14005c9fb  mov     [rax-18h], rdi
0x14005c9ff  xorps   xmm0, xmm0
0x14005ca02  mov     [rax-20h], r12
0x14005ca06  xor     esi, esi
0x14005ca08  mov     [rax-28h], r13
0x14005ca0c  mov     [rax-30h], r14
0x14005ca10  mov     r14, rdx
0x14005ca13  mov     rdx, [rdx+10h]
0x14005ca17  mov     [rax-38h], r15
0x14005ca1b  mov     r15d, ecx
0x14005ca1e  mov     [rax+10h], rsi
0x14005ca22  mov     r12, [rdx+8]
0x14005ca26  mov     r13, [rdx+10h]
0x14005ca2a  movups  xmmword ptr [rax-50h], xmm0
0x14005ca2e  mov     rdi, [rdx+10h]
0x14005ca32  mov     rdx, [rdx+8]; FileObject
0x14005ca36  mov     rcx, rdi; Instance
0x14005ca39  call    cs:__imp_FltGetStreamContext
0x14005ca40  nop     dword ptr [rax+rax+00h]
0x14005ca45  mov     rbx, [rsp+0B8h+Context]
0x14005ca4d  test    rbx, rbx
0x14005ca50  jz      short loc_14005CAB5
0x14005ca52  mov     eax, [rbx+1Ch]
0x14005ca55  test    al, 1
0x14005ca57  jz      loc_14005CD24
0x14005ca5d  mov     rax, [rbx+10h]
0x14005ca61  mov     rcx, [rax+10h]
0x14005ca65  cmp     [rcx+20h], rdi
0x14005ca69  jnz     loc_14005CD41
0x14005ca6f  mov     rcx, r14; CallbackData
0x14005ca72  call    cs:__imp_FltGetRequestorProcess
0x14005ca79  nop     dword ptr [rax+rax+00h]
0x14005ca7e  mov     rcx, rax
0x14005ca81  call    HsmOsIsPassThroughModeEnabled
0x14005ca86  test    al, al
0x14005ca88  jz      loc_14005CD49
0x14005ca8e  mov     rcx, [rsp+0B8h+Context]; Context
0x14005ca96  call    cs:__imp_FltReleaseContext
0x14005ca9d  nop     dword ptr [rax+rax+00h]
0x14005caa2  xor     ebx, ebx
0x14005caa4  mov     [rsp+0B8h+Context], rbx
0x14005caac  test    rbx, rbx
0x14005caaf  jnz     loc_14005CC6B
0x14005cab5  mov     rcx, [rsp+0B8h+P]; P
0x14005caba  mov     r15, [rsp+0B8h+var_38]
0x14005cac2  mov     r14, [rsp+0B8h+var_30]
0x14005caca  mov     r13, [rsp+0B8h+var_28]
0x14005cad2  mov     r12, [rsp+0B8h+var_20]
0x14005cada  mov     rdi, [rsp+0B8h+var_18]
0x14005cae2  test    rcx, rcx
0x14005cae5  jnz     short loc_14005CB21
0x14005cae7  test    rbx, rbx
0x14005caea  jz      short loc_14005CAFB
0x14005caec  mov     rcx, rbx; Context
0x14005caef  call    cs:__imp_FltReleaseContext
0x14005caf6  nop     dword ptr [rax+rax+00h]
0x14005cafb  mov     rbx, [rsp+0B8h+arg_0]
0x14005cb03  test    rsi, rsi
0x14005cb06  jz      short loc_14005CB17
0x14005cb08  mov     rcx, rsi; Context
0x14005cb0b  call    cs:__imp_FltReleaseContext
0x14005cb12  nop     dword ptr [rax+rax+00h]
0x14005cb17  add     rsp, 0B0h
0x14005cb1e  pop     rsi
0x14005cb1f  retn
0x14005cb21  mov     edx, 73557348h; Tag
0x14005cb26  call    cs:__imp_ExFreePoolWithTag
0x14005cb2d  nop     dword ptr [rax+rax+00h]
0x14005cb32  jmp     short loc_14005CAE7
0x14005cb34  mov     rdx, [r14+10h]
0x14005cb38  mov     rcx, r14; CallbackData
0x14005cb3b  mov     [rsp+0B8h+var_10], rbp
0x14005cb43  mov     r8, [rdx+8]; FileObject
0x14005cb47  mov     rdx, [rdx+10h]; Instance
0x14005cb4b  call    HsmpGetStreamHandleContext
0x14005cb50  mov     edx, 18h
0x14005cb55  mov     ecx, 100h
0x14005cb5a  mov     r8d, 69437348h
0x14005cb60  mov     rsi, rax
0x14005cb63  call    cs:__imp_ExAllocatePool2
0x14005cb6a  nop     dword ptr [rax+rax+00h]
0x14005cb6f  mov     rbp, rax
0x14005cb72  test    rax, rax
0x14005cb75  jz      loc_14005CCA7
0x14005cb7b  or      dword ptr [rax], 2
0x14005cb7e  mov     r9, rax
0x14005cb81  mov     r8, r14
0x14005cb84  mov     rdx, rbx
0x14005cb87  mov     rcx, rsi
0x14005cb8a  call    HsmpFillOutAttributionInformation
0x14005cb8f  xor     ecx, ecx
0x14005cb91  call    HsmDbgBreakOnStatus
0x14005cb96  test    rsi, rsi
0x14005cb99  jz      loc_14005CC5B
0x14005cb9f  xor     edi, edi
0x14005cba1  mov     rdx, r14
0x14005cba4  mov     rcx, rsi
0x14005cba7  call    HsmpCaptureProcessInfo
0x14005cbac  mov     rax, [rsi+48h]
0x14005cbb0  mov     [rsp+0B8h+var_60], rax
0x14005cbb5  mov     r9d, 101h
0x14005cbbb  lea     rax, [rsp+0B8h+var_50]
0x14005cbc0  mov     r8, r12
0x14005cbc3  mov     rcx, r13
0x14005cbc6  mov     [rsp+0B8h+var_98], rax
0x14005cbcb  call    HsmiQueryFullFilePath
0x14005cbd0  mov     ecx, eax
0x14005cbd2  mov     r13d, eax
0x14005cbd5  call    HsmDbgBreakOnStatus
0x14005cbda  test    r13d, r13d
0x14005cbdd  js      loc_14005CD56
0x14005cbe3  mov     rcx, [rsp+0B8h+var_60]
0x14005cbe8  lea     r9, [rsp+0B8h+var_50]
0x14005cbed  mov     rdx, [rsp+0B8h+arg_20]
0x14005cbf5  mov     rax, cs:qword_140029768
0x14005cbfc  mov     r8, [rbx+8]
0x14005cc00  mov     [rsp+0B8h+var_80], rcx
0x14005cc05  mov     rcx, [rsp+0B8h+arg_18]
0x14005cc0d  mov     [rsp+0B8h+var_88], rdx
0x14005cc12  mov     rdx, r14
0x14005cc15  mov     [rsp+0B8h+var_90], rcx
0x14005cc1a  mov     ecx, [rsp+0B8h+arg_10]
0x14005cc21  mov     dword ptr [rsp+0B8h+var_98], ecx
0x14005cc25  mov     ecx, r15d
0x14005cc28  call    _guard_dispatch_icall
0x14005cc2d  mov     rcx, rbp; P
0x14005cc30  call    HsmpCleanupAttributionInformation
0x14005cc35  test    rdi, rdi
0x14005cc38  jz      short loc_14005CC4E
0x14005cc3a  mov     edx, 69507348h; Tag
0x14005cc3f  mov     rcx, rdi; P
0x14005cc42  call    cs:__imp_ExFreePoolWithTag
0x14005cc49  nop     dword ptr [rax+rax+00h]
0x14005cc4e  mov     rbp, [rsp+0B8h+var_10]
0x14005cc56  jmp     loc_14005CAB5
0x14005cc5b  mov     rcx, rbp
0x14005cc5e  call    HsmpCreateProcessInfo
0x14005cc63  mov     rdi, rax
0x14005cc66  jmp     loc_14005CBB0
0x14005cc6b  mov     rax, [rbx+10h]
0x14005cc6f  xor     r9d, r9d
0x14005cc72  mov     rdx, [rbx+8]
0x14005cc76  mov     r8, r14
0x14005cc79  mov     ecx, r15d
0x14005cc7c  mov     rdi, [rax+10h]
0x14005cc80  mov     rax, [rax+20h]
0x14005cc84  mov     [rsp+0B8h+var_68], rax
0x14005cc89  mov     rax, cs:qword_140029758
0x14005cc90  mov     [rsp+0B8h+var_58], rdi
0x14005cc95  call    _guard_dispatch_icall
0x14005cc9a  test    al, al
0x14005cc9c  jz      loc_14005CAB5
0x14005cca2  jmp     loc_14005CB34
0x14005cca7  mov     ecx, 0C000009Ah
0x14005ccac  call    HsmDbgBreakOnStatus
0x14005ccb1  mov     ecx, 0C000009Ah
0x14005ccb6  call    HsmDbgBreakOnStatus
0x14005ccbb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ccc2  lea     rax, WPP_GLOBAL_Control
0x14005ccc9  cmp     rcx, rax
0x14005cccc  jz      short loc_14005CC4E
0x14005ccce  mov     eax, [rcx+2Ch]
0x14005ccd1  test    al, 1
0x14005ccd3  jz      loc_14005CC4E
0x14005ccd9  cmp     byte ptr [rcx+29h], 2
0x14005ccdd  jb      loc_14005CC4E
0x14005cce3  mov     rax, [rsp+0B8h+var_68]
0x14005cce8  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005ccef  mov     rcx, [rcx+18h]
0x14005ccf3  mov     edx, 43h ; 'C'
0x14005ccf8  mov     dword ptr [rsp+0B8h+var_80], 0C000009Ah
0x14005cd00  mov     r9, rdi
0x14005cd03  mov     [rsp+0B8h+var_88], rax
0x14005cd08  mov     [rsp+0B8h+var_90], r12
0x14005cd0d  mov     [rsp+0B8h+var_98], rbx
0x14005cd12  call    WPP_SF_qqiqd
0x14005cd17  mov     rbp, [rsp+0B8h+var_10]
0x14005cd1f  jmp     loc_14005CAB5
0x14005cd24  test    rbx, rbx
0x14005cd27  jz      loc_14005CAB5
0x14005cd2d  mov     rcx, rbx; Context
0x14005cd30  call    cs:__imp_FltDeleteContext
0x14005cd37  nop     dword ptr [rax+rax+00h]
0x14005cd3c  jmp     loc_14005CA8E
0x14005cd41  mov     rcx, rbx
0x14005cd44  jmp     loc_14005CA96
0x14005cd49  mov     rbx, [rsp+0B8h+Context]
0x14005cd51  jmp     loc_14005CAAC
0x14005cd56  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd5d  lea     rax, WPP_GLOBAL_Control
0x14005cd64  cmp     rcx, rax
0x14005cd67  jz      loc_14005CC2D
0x14005cd6d  mov     edx, [rcx+2Ch]
0x14005cd70  test    dl, 1
0x14005cd73  jz      loc_14005CC2D
0x14005cd79  cmp     byte ptr [rcx+29h], 3
0x14005cd7d  jb      loc_14005CC2D
0x14005cd83  mov     rax, [rsp+0B8h+var_68]
0x14005cd88  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005cd8f  mov     r9, [rsp+0B8h+var_58]
0x14005cd94  mov     edx, 44h ; 'D'
0x14005cd99  mov     rcx, [rcx+18h]
0x14005cd9d  mov     dword ptr [rsp+0B8h+var_80], r13d
0x14005cda2  mov     [rsp+0B8h+var_88], rax
0x14005cda7  mov     [rsp+0B8h+var_90], r12
0x14005cdac  mov     [rsp+0B8h+var_98], rbx
0x14005cdb1  call    WPP_SF_qqiqd
0x14005cdb6  jmp     loc_14005CC2D
```
