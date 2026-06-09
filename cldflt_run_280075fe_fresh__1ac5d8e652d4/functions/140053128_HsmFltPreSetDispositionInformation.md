# HsmFltPreSetDispositionInformation

- ea: `0x140053128`
- end: `0x1400536d8`
- name: `HsmFltPreSetDispositionInformation`
- size: `1456`
- prototype: `__int64 __usercall@<rax>(PFLT_CONTEXT Context@<rcx>, PFLT_INSTANCE Instance, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400525b0`

## callees

- `0x140003c50`
- `0x140006f40`
- `0x14000ac28`
- `0x140051c80`
- `0x1400520d0`
- `0x140053128`
- `0x140054a04`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400531c3`
- `ntoskrnl!KeClearEvent` at `0x1400531c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005363c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005363c`
- `ntoskrnl!KeInitializeEvent` at `0x1400532df`
- `ntoskrnl!KeInitializeEvent` at `0x1400532df`
- `ntoskrnl!KeSetEvent` at `0x1400535bd`
- `ntoskrnl!KeSetEvent` at `0x1400535bd`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400533d0`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400533d0`
- `FLTMGR!FltReferenceContext` at `0x140053224`
- `FLTMGR!FltReferenceContext` at `0x140053224`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400531f3`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005331f`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400534a1`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400531f3`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005331f`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400534a1`
- `FLTMGR!FltDeleteContext` at `0x14005356a`
- `FLTMGR!FltDeleteContext` at `0x14005356a`
- `FLTMGR!FltCancelIo` at `0x14005361b`
- `FLTMGR!FltCancelIo` at `0x14005361b`
- `FLTMGR!FltGetRequestorProcess` at `0x140053431`
- `FLTMGR!FltGetRequestorProcess` at `0x140053431`
- `FLTMGR!FltReleasePushLockEx` at `0x1400531db`
- `FLTMGR!FltReleasePushLockEx` at `0x1400535ce`
- `FLTMGR!FltReleasePushLockEx` at `0x1400531db`
- `FLTMGR!FltReleasePushLockEx` at `0x1400535ce`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400531b3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400535f7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400531b3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400535f7`
- `FLTMGR!FltReleaseContext` at `0x140053417`
- `FLTMGR!FltReleaseContext` at `0x140053451`
- `FLTMGR!FltReleaseContext` at `0x14005357a`
- `FLTMGR!FltReleaseContext` at `0x1400536ba`
- `FLTMGR!FltReleaseContext` at `0x140053417`
- `FLTMGR!FltReleaseContext` at `0x140053451`
- `FLTMGR!FltReleaseContext` at `0x14005357a`
- `FLTMGR!FltReleaseContext` at `0x1400536ba`

## pseudocode

```c
__int64 __fastcall HsmFltPreSetDispositionInformation(
        struct _KEVENT *Context,
        struct _KEVENT *a2,
        _DWORD *a3,
        struct _FLT_CALLBACK_DATA *a4,
        PFLT_INSTANCE Instance,
        struct _KEVENT **a6)
{
  struct _KEVENT *v8; // r13
  struct _KEVENT *v9; // r14
  unsigned int v10; // esi
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  ULONG Options; // eax
  __int64 v13; // r12
  NTSTATUS v14; // r13d
  struct _KEVENT *v15; // r15
  PFLT_IO_PARAMETER_BLOCK v16; // r8
  UCHAR MajorFunction; // r11
  ULONG v18; // eax
  PVOID *p_EaBuffer; // rdx
  bool v20; // zf
  ULONG v21; // eax
  int v22; // r15d
  unsigned int v23; // eax
  char v24; // cl
  _QWORD *v26; // rdi
  PEPROCESS RequestorProcess; // rax
  struct _KEVENT *v28; // rdi
  NTSTATUS v29; // r15d
  int v30; // eax
  ULONG v31; // eax
  PFLT_IO_PARAMETER_BLOCK v32; // rax
  ULONG v33; // ecx
  struct _FILE_OBJECT *FileObject; // [rsp+40h] [rbp-30h]
  PFLT_CONTEXT v35; // [rsp+48h] [rbp-28h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-20h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+C8h] [rbp+58h] BYREF

  v8 = a2;
  v9 = Context;
  v10 = 1;
  if ( !a4 )
    return v10;
  Iopb = a4->Iopb;
  if ( Iopb->MajorFunction != 6 )
    return v10;
  Options = Iopb->Parameters.Create.Options;
  if ( Options == 13 )
  {
    if ( *(_BYTE *)Iopb->Parameters.Create.EaBuffer )
      goto LABEL_5;
  }
  else if ( Options == 64 && (*(_DWORD *)Iopb->Parameters.Create.EaBuffer & 1) != 0 )
  {
    goto LABEL_5;
  }
  v21 = Iopb->Parameters.Create.Options;
  if ( v21 == 13 )
  {
    if ( *(_BYTE *)Iopb->Parameters.Create.EaBuffer )
      return v10;
  }
  else if ( v21 != 64 || (*(_DWORD *)Iopb->Parameters.Create.EaBuffer & 1) != 0 )
  {
    return v10;
  }
LABEL_5:
  LODWORD(v13) = 0;
  FileObject = (struct _FILE_OBJECT *)*((_QWORD *)Instance + 4);
  Instance = (PFLT_INSTANCE)*((_QWORD *)Instance + 3);
  if ( a2 && (a2[1].Header.SignalState & 1) != 0 )
  {
    v29 = FltCancellableWaitForSingleObject(&a2->Header.WaitListHead.Blink[6], 0, a4);
    HsmDbgBreakOnStatus((unsigned int)v29);
    if ( v29 >= 0 )
    {
      v15 = v8;
LABEL_9:
      FltReferenceContext(v15);
      v35 = v8;
      if ( a3 )
      {
        LOBYTE(Instance) = 0;
        goto LABEL_11;
      }
      Contexta = 0;
      FltGetStreamHandleContext(Instance, FileObject, &Contexta);
      v26 = Contexta;
      if ( Contexta )
      {
        if ( (*(_DWORD *)(*((_QWORD *)Contexta + 2) + 28LL) & 1) == 0 )
        {
          if ( !Contexta )
            goto LABEL_43;
          FltDeleteContext(Contexta);
          FltReleaseContext(Contexta);
          v26 = 0;
          Contexta = 0;
        }
        if ( v26 )
        {
          if ( *(PFLT_INSTANCE *)(*(_QWORD *)(*(_QWORD *)(v26[2] + 16LL) + 16LL) + 32LL) != Instance )
          {
            FltReleaseContext(v26);
            v26 = 0;
            Contexta = 0;
          }
          if ( v26 )
          {
            RequestorProcess = FltGetRequestorProcess(a4);
            if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
            {
              FltReleaseContext(Contexta);
              a3 = 0;
              Contexta = 0;
            }
            else
            {
              a3 = Contexta;
            }
            if ( a3 )
            {
              LOBYTE(Instance) = 1;
LABEL_11:
              v16 = a4->Iopb;
              MajorFunction = v16->MajorFunction;
              if ( MajorFunction == 6 )
              {
                v18 = v16->Parameters.Create.Options;
                p_EaBuffer = &v16->Parameters.Create.EaBuffer;
                if ( v18 == 13 )
                {
                  v20 = *(_BYTE *)*p_EaBuffer == 0;
                }
                else
                {
                  if ( v18 != 64 )
                    goto LABEL_48;
                  v20 = (*(_DWORD *)*p_EaBuffer & 1) == 0;
                }
                if ( !v20 )
                {
                  v30 = 1;
                  goto LABEL_49;
                }
              }
LABEL_48:
              v30 = 0;
              p_EaBuffer = &v16->Parameters.Create.EaBuffer;
LABEL_49:
              if ( ((a3[10] >> 11) & 1) != v30 )
              {
                v22 = 0;
                if ( MajorFunction != 6 )
                  goto LABEL_54;
                v31 = v16->Parameters.Create.Options;
                if ( v31 == 13 )
                {
                  if ( !*(_BYTE *)*p_EaBuffer )
                    goto LABEL_54;
                }
                else if ( v31 != 64 || (*(_DWORD *)*p_EaBuffer & 1) == 0 )
                {
LABEL_54:
                  v32 = a4->Iopb;
                  if ( v32->MajorFunction == 6 )
                  {
                    v33 = v32->Parameters.Create.Options;
                    if ( v33 == 13 )
                    {
                      if ( *(_BYTE *)v32->Parameters.Create.EaBuffer )
                        goto LABEL_57;
                    }
                    else if ( v33 != 64 || (*(_DWORD *)v32->Parameters.Create.EaBuffer & 1) != 0 )
                    {
                      goto LABEL_57;
                    }
                    v22 = 128;
                  }
LABEL_57:
                  v28 = a2;
                  if ( (a2[1].Header.SignalState & 2) != 0 )
                    v22 |= 0x10u;
                  memset(&Event, 0, sizeof(Event));
                  KeInitializeEvent(&Event, SynchronizationEvent, 0);
                  a4->QueueContext[0] = &Event;
                  HsmpCldNotifyPreOperation(
                    4u,
                    a4,
                    v22,
                    0,
                    (void (__fastcall *)(__int64, _QWORD, _QWORD))HsmiDeleteOnCloseNotificationCallback,
                    (__int64)a4);
                  v13 = (unsigned int)FltCancellableWaitForSingleObject(&Event, 0, a4);
                  HsmDbgBreakOnStatus(v13);
                  if ( (_DWORD)v13 == -1073741749 || (_DWORD)v13 == -1073741536 )
                  {
                    FltCancelIo(a4);
                    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                  }
                  a4->QueueContext[0] = 0;
                  if ( (int)v13 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_qqiqd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        62,
                        WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
                        a4,
                        v9,
                        FileObject,
                        a2->Header.WaitListHead.Blink[2].Flink,
                        v13);
                    }
                    a4->IoStatus.Status = v13;
                  }
                  else
                  {
                    v23 = HsmiInfoPrepareForPostSetDispostionInformation(
                            a4,
                            (unsigned int)a4->IoStatus.Status,
                            &v35,
                            a6);
                    v8 = (struct _KEVENT *)v35;
                    v10 = v23;
                  }
                  v24 = (char)Instance;
                  goto LABEL_26;
                }
                a3[10] |= 0x800u;
                goto LABEL_54;
              }
              v24 = (char)Instance;
LABEL_44:
              v10 = 0;
              v28 = a2;
              v8 = 0;
              *a6 = v15;
LABEL_26:
              if ( v24 )
                FltReleaseContext(v28);
              goto LABEL_28;
            }
          }
        }
      }
LABEL_43:
      v24 = 0;
      goto LABEL_44;
    }
    a4->IoStatus.Status = v29;
    goto LABEL_75;
  }
  FltAcquirePushLockExclusiveEx(&Context[4].Header.WaitListHead.Blink, 0);
  KeClearEvent(v9 + 5);
  ++v9[7].Header.LockNV;
  FltReleasePushLockEx(&v9[4].Header.WaitListHead.Blink, 0);
  v14 = FltCancellableWaitForSingleObject(&v9[6], 0, a4);
  HsmDbgBreakOnStatus((unsigned int)v14);
  if ( v14 < 0 )
  {
    FltAcquirePushLockExclusiveEx(&v9[4].Header.WaitListHead.Blink, 0);
    v20 = v9[7].Header.LockNV-- == 1;
    if ( v20 )
      KeSetEvent(v9 + 5, 0, 0);
    FltReleasePushLockEx(&v9[4].Header.WaitListHead.Blink, 0);
    a4->IoStatus.Status = v14;
LABEL_75:
    a4->IoStatus.Information = 0;
    v9 = 0;
    goto LABEL_76;
  }
  if ( v9 )
  {
    v8 = v9;
    v15 = v9;
    goto LABEL_9;
  }
LABEL_76:
  v8 = v9;
  v10 = 4;
LABEL_28:
  if ( v8 )
    HsmpReleaseFileNameLock(v8);
  if ( (int)v13 < 0 )
  {
    v10 = 4;
    a4->IoStatus.Status = v13;
    a4->IoStatus.Information = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x140053128  mov     [rsp-38h+arg_0], rbx
0x14005312d  mov     [rsp-38h+arg_8], rdx
0x140053132  push    rbp
0x140053133  push    rsi
0x140053134  push    rdi
0x140053135  push    r12
0x140053137  push    r13
0x140053139  push    r14
0x14005313b  push    r15
0x14005313d  mov     rbp, rsp
0x140053140  sub     rsp, 70h
0x140053144  mov     rbx, r9
0x140053147  mov     rdi, r8
0x14005314a  mov     r13, rdx
0x14005314d  mov     r14, rcx
0x140053150  mov     esi, 1
0x140053155  test    r9, r9
0x140053158  jz      loc_140053392
0x14005315e  mov     r8, [r9+10h]
0x140053162  mov     r9b, [r8+4]
0x140053166  cmp     r9b, 6
0x14005316a  jnz     loc_140053392
0x140053170  mov     eax, [r8+20h]
0x140053174  cmp     eax, 0Dh
0x140053177  jnz     loc_140053288
0x14005317d  mov     rax, [r8+38h]
0x140053181  cmp     byte ptr [rax], 0
0x140053184  jz      loc_1400532A6
0x14005318a  mov     rax, [rbp+Instance]
0x14005318e  xor     r12d, r12d
0x140053191  mov     rcx, [rax+18h]
0x140053195  mov     rax, [rax+20h]
0x140053199  mov     [rbp+FileObject], rax
0x14005319d  mov     [rbp+Instance], rcx
0x1400531a1  test    r13, r13
0x1400531a4  jnz     loc_140053488
0x1400531aa  lea     r15, [r14+70h]
0x1400531ae  xor     edx, edx
0x1400531b0  mov     rcx, r15
0x1400531b3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400531ba  nop     dword ptr [rax+rax+00h]
0x1400531bf  lea     rcx, [r14+78h]; Event
0x1400531c3  call    cs:__imp_KeClearEvent
0x1400531ca  nop     dword ptr [rax+rax+00h]
0x1400531cf  add     [r14+0A8h], esi
0x1400531d6  xor     edx, edx
0x1400531d8  mov     rcx, r15
0x1400531db  call    cs:__imp_FltReleasePushLockEx
0x1400531e2  nop     dword ptr [rax+rax+00h]
0x1400531e7  lea     rcx, [r14+90h]; Object
0x1400531ee  mov     r8, rbx; CallbackData
0x1400531f1  xor     edx, edx; Timeout
0x1400531f3  call    cs:__imp_FltCancellableWaitForSingleObject
0x1400531fa  nop     dword ptr [rax+rax+00h]
0x1400531ff  mov     ecx, eax
0x140053201  mov     r13d, eax
0x140053204  call    HsmDbgBreakOnStatus
0x140053209  test    r13d, r13d
0x14005320c  js      loc_1400535F2
0x140053212  test    r14, r14
0x140053215  jz      loc_1400535E5
0x14005321b  mov     r13, r14
0x14005321e  mov     r15, r14
0x140053221  mov     rcx, r15; Context
0x140053224  call    cs:__imp_FltReferenceContext
0x14005322b  nop     dword ptr [rax+rax+00h]
0x140053230  mov     [rbp+var_28], r13
0x140053234  test    rdi, rdi
0x140053237  jz      loc_1400533C0
0x14005323d  mov     byte ptr [rbp+Instance], r12b
0x140053241  mov     r10d, [rdi+28h]
0x140053245  mov     r9d, r10d
0x140053248  mov     r8, [rbx+10h]
0x14005324c  shr     r9d, 0Bh
0x140053250  and     r9d, esi
0x140053253  mov     r11b, [r8+4]
0x140053257  cmp     r11b, 6
0x14005325b  jnz     loc_1400534C8
0x140053261  mov     eax, [r8+20h]
0x140053265  lea     rdx, [r8+38h]
0x140053269  cmp     eax, 0Dh
0x14005326c  jz      loc_140053529
0x140053272  cmp     eax, 40h ; '@'
0x140053275  jnz     loc_1400534C8
0x14005327b  mov     rax, [rdx]
0x14005327e  mov     ecx, [rax]
0x140053280  test    sil, cl
0x140053283  jmp     loc_14005352F
0x140053288  cmp     eax, 40h ; '@'
0x14005328b  jnz     short loc_1400532A6
0x14005328d  mov     rax, [r8+38h]
0x140053291  mov     ecx, [rax]
0x140053293  test    sil, cl
0x140053296  jnz     loc_14005318A
0x14005329c  cmp     r9b, 6
0x1400532a0  jnz     loc_140053392
0x1400532a6  mov     eax, [r8+20h]
0x1400532aa  cmp     eax, 0Dh
0x1400532ad  jnz     loc_140053591
0x1400532b3  mov     rax, [r8+38h]
0x1400532b7  cmp     byte ptr [rax], 0
0x1400532ba  jz      loc_14005318A
0x1400532c0  jmp     loc_140053392
0x1400532c5  or      r15d, 10h
0x1400532c9  xorps   xmm0, xmm0
0x1400532cc  lea     rcx, [rbp+Event]; Event
0x1400532d0  xor     eax, eax
0x1400532d2  xor     r8d, r8d; State
0x1400532d5  mov     edx, esi; Type
0x1400532d7  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1400532db  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1400532df  call    cs:__imp_KeInitializeEvent
0x1400532e6  nop     dword ptr [rax+rax+00h]
0x1400532eb  xor     r9d, r9d
0x1400532ee  mov     [rsp+70h+var_48], rbx
0x1400532f3  lea     rax, [rbp+Event]
0x1400532f7  mov     r8d, r15d
0x1400532fa  mov     [rbx+40h], rax
0x1400532fe  mov     rdx, rbx
0x140053301  lea     rax, HsmiDeleteOnCloseNotificationCallback
0x140053308  lea     ecx, [r9+4]
0x14005330c  mov     [rsp+70h+Timeout], rax
0x140053311  call    HsmpCldNotifyPreOperation
0x140053316  mov     r8, rbx; CallbackData
0x140053319  lea     rcx, [rbp+Event]; Object
0x14005331d  xor     edx, edx; Timeout
0x14005331f  call    cs:__imp_FltCancellableWaitForSingleObject
0x140053326  nop     dword ptr [rax+rax+00h]
0x14005332b  mov     ecx, eax
0x14005332d  mov     r12d, eax
0x140053330  call    HsmDbgBreakOnStatus
0x140053335  cmp     r12d, 0C000004Bh
0x14005333c  jz      loc_140053618
0x140053342  cmp     r12d, 0C0000120h
0x140053349  jz      loc_140053618
0x14005334f  mov     qword ptr [rbx+40h], 0
0x140053357  test    r12d, r12d
0x14005335a  js      loc_14005364D
0x140053360  mov     r9, [rbp+arg_28]
0x140053364  lea     r8, [rbp+var_28]
0x140053368  mov     edx, [rbx+18h]
0x14005336b  mov     rcx, rbx
0x14005336e  call    HsmiInfoPrepareForPostSetDispostionInformation
0x140053373  mov     r13, [rbp+var_28]
0x140053377  mov     esi, eax
0x140053379  mov     cl, byte ptr [rbp+Instance]
0x14005337c  test    cl, cl
0x14005337e  jnz     loc_1400536B7
0x140053384  test    r13, r13
0x140053387  jnz     loc_1400536CB
0x14005338d  test    r12d, r12d
0x140053390  js      short loc_1400533AD
0x140053392  mov     rbx, [rsp+70h+arg_0]
0x14005339a  mov     eax, esi
0x14005339c  add     rsp, 70h
0x1400533a0  pop     r15
0x1400533a2  pop     r14
0x1400533a4  pop     r13
0x1400533a6  pop     r12
0x1400533a8  pop     rdi
0x1400533a9  pop     rsi
0x1400533aa  pop     rbp
0x1400533ab  retn
0x1400533ad  mov     esi, 4
0x1400533b2  mov     [rbx+18h], r12d
0x1400533b6  mov     qword ptr [rbx+20h], 0
0x1400533be  jmp     short loc_140053392
0x1400533c0  mov     rdx, [rbp+FileObject]; FileObject
0x1400533c4  lea     r8, [rbp+Context]; Context
0x1400533c8  mov     rcx, [rbp+Instance]; Instance
0x1400533cc  mov     [rbp+Context], r12
0x1400533d0  call    cs:__imp_FltGetStreamHandleContext
0x1400533d7  nop     dword ptr [rax+rax+00h]
0x1400533dc  mov     rdi, [rbp+Context]
0x1400533e0  test    rdi, rdi
0x1400533e3  jz      loc_140053471
0x1400533e9  mov     rax, [rdi+10h]
0x1400533ed  mov     ecx, [rax+1Ch]
0x1400533f0  test    sil, cl
0x1400533f3  jz      loc_14005355E
0x1400533f9  test    rdi, rdi
0x1400533fc  jz      short loc_140053471
0x1400533fe  mov     rax, [rdi+10h]
0x140053402  mov     rcx, [rax+10h]
0x140053406  mov     rax, [rcx+10h]
0x14005340a  mov     rcx, [rbp+Instance]
0x14005340e  cmp     [rax+20h], rcx
0x140053412  jz      short loc_140053429
0x140053414  mov     rcx, rdi; Context
0x140053417  call    cs:__imp_FltReleaseContext
0x14005341e  nop     dword ptr [rax+rax+00h]
0x140053423  xor     edi, edi
0x140053425  mov     [rbp+Context], rdi
0x140053429  test    rdi, rdi
0x14005342c  jz      short loc_140053471
0x14005342e  mov     rcx, rbx; CallbackData
0x140053431  call    cs:__imp_FltGetRequestorProcess
0x140053438  nop     dword ptr [rax+rax+00h]
0x14005343d  mov     rcx, rax
0x140053440  call    HsmOsIsPassThroughModeEnabled
0x140053445  test    al, al
0x140053447  jz      loc_14005360F
0x14005344d  mov     rcx, [rbp+Context]; Context
0x140053451  call    cs:__imp_FltReleaseContext
0x140053458  nop     dword ptr [rax+rax+00h]
0x14005345d  xor     edi, edi
0x14005345f  mov     [rbp+Context], rdi
0x140053463  test    rdi, rdi
0x140053466  jz      short loc_140053471
0x140053468  mov     byte ptr [rbp+Instance], sil
0x14005346c  jmp     loc_140053241
0x140053471  xor     cl, cl
0x140053473  mov     rax, [rbp+arg_28]
0x140053477  xor     esi, esi
0x140053479  mov     rdi, [rbp+arg_8]
0x14005347d  xor     r13d, r13d
0x140053480  mov     [rax], r15
0x140053483  jmp     loc_14005337C
0x140053488  mov     eax, [rdx+1Ch]
0x14005348b  test    sil, al
0x14005348e  jz      loc_1400531AA
0x140053494  mov     rcx, [rdx+10h]
0x140053498  mov     r8, rbx; CallbackData
0x14005349b  add     rcx, 60h ; '`'; Object
0x14005349f  xor     edx, edx; Timeout
0x1400534a1  call    cs:__imp_FltCancellableWaitForSingleObject
0x1400534a8  nop     dword ptr [rax+rax+00h]
0x1400534ad  mov     ecx, eax
0x1400534af  mov     r15d, eax
0x1400534b2  call    HsmDbgBreakOnStatus
0x1400534b7  test    r15d, r15d
0x1400534ba  js      loc_1400535AE
0x1400534c0  mov     r15, r13
0x1400534c3  jmp     loc_140053221
0x1400534c8  xor     eax, eax
0x1400534ca  lea     rdx, [r8+38h]
0x1400534ce  cmp     r9d, eax
0x1400534d1  jz      loc_1400536AF
0x1400534d7  xor     r15d, r15d
0x1400534da  cmp     r11b, 6
0x1400534de  jnz     short loc_1400534FA
0x1400534e0  mov     eax, [r8+20h]
0x1400534e4  cmp     eax, 0Dh
0x1400534e7  jnz     short loc_14005354D
0x1400534e9  mov     rax, [rdx]
0x1400534ec  cmp     [rax], r12b
0x1400534ef  jz      short loc_1400534FA
0x1400534f1  bts     r10d, 0Bh
0x1400534f6  mov     [rdi+28h], r10d
0x1400534fa  mov     rax, [rbx+10h]
0x1400534fe  cmp     byte ptr [rax+4], 6
0x140053502  jnz     short loc_140053515
0x140053504  mov     ecx, [rax+20h]
0x140053507  cmp     ecx, 0Dh
0x14005350a  jnz     short loc_140053535
0x14005350c  mov     rax, [rax+38h]
0x140053510  cmp     [rax], r12b
0x140053513  jz      short loc_140053545
0x140053515  mov     rdi, [rbp+arg_8]
0x140053519  mov     eax, [rdi+1Ch]
0x14005351c  test    al, 2
0x14005351e  jnz     loc_1400532C5
0x140053524  jmp     loc_1400532C9
0x140053529  mov     rax, [rdx]
0x14005352c  cmp     [rax], r12b
0x14005352f  jz      short loc_1400534C8
0x140053531  mov     eax, esi
0x140053533  jmp     short loc_1400534CE
0x140053535  cmp     ecx, 40h ; '@'
0x140053538  jnz     short loc_140053515
0x14005353a  mov     rax, [rax+38h]
0x14005353e  mov     ecx, [rax]
0x140053540  test    sil, cl
0x140053543  jnz     short loc_140053515
0x140053545  mov     r15d, 80h
0x14005354b  jmp     short loc_140053515
0x14005354d  cmp     eax, 40h ; '@'
0x140053550  jnz     short loc_1400534FA
0x140053552  mov     rax, [rdx]
0x140053555  mov     ecx, [rax]
0x140053557  test    sil, cl
0x14005355a  jz      short loc_1400534FA
0x14005355c  jmp     short loc_1400534F1
0x14005355e  test    rdi, rdi
0x140053561  jz      loc_140053471
0x140053567  mov     rcx, rdi; Context
0x14005356a  call    cs:__imp_FltDeleteContext
0x140053571  nop     dword ptr [rax+rax+00h]
0x140053576  mov     rcx, [rbp+Context]; Context
0x14005357a  call    cs:__imp_FltReleaseContext
0x140053581  nop     dword ptr [rax+rax+00h]
0x140053586  xor     edi, edi
0x140053588  mov     [rbp+Context], rdi
0x14005358c  jmp     loc_1400533F9
0x140053591  cmp     eax, 40h ; '@'
0x140053594  jnz     loc_140053392
0x14005359a  mov     rax, [r8+38h]
0x14005359e  mov     ecx, [rax]
0x1400535a0  test    sil, cl
0x1400535a3  jnz     loc_140053392
  ... truncated ...
```
