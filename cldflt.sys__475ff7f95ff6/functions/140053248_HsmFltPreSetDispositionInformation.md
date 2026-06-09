# HsmFltPreSetDispositionInformation

- ea: `0x140053248`
- end: `0x1400537f8`
- name: `HsmFltPreSetDispositionInformation`
- size: `1456`
- prototype: `__int64 __fastcall(struct _KEVENT *Context, struct _KEVENT *, _DWORD *, struct _FLT_CALLBACK_DATA *, PFLT_INSTANCE Instance, struct _KEVENT **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400526d0`

## callees

- `0x140003c50`
- `0x140006f40`
- `0x14000ac28`
- `0x140051da0`
- `0x1400521f0`
- `0x140053248`
- `0x140054b24`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400532e3`
- `ntoskrnl!KeClearEvent` at `0x1400532e3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005375c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005375c`
- `ntoskrnl!KeInitializeEvent` at `0x1400533ff`
- `ntoskrnl!KeInitializeEvent` at `0x1400533ff`
- `ntoskrnl!KeSetEvent` at `0x1400536dd`
- `ntoskrnl!KeSetEvent` at `0x1400536dd`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400534f0`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400534f0`
- `FLTMGR!FltReferenceContext` at `0x140053344`
- `FLTMGR!FltReferenceContext` at `0x140053344`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140053313`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005343f`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400535c1`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140053313`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005343f`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x1400535c1`
- `FLTMGR!FltDeleteContext` at `0x14005368a`
- `FLTMGR!FltDeleteContext` at `0x14005368a`
- `FLTMGR!FltCancelIo` at `0x14005373b`
- `FLTMGR!FltCancelIo` at `0x14005373b`
- `FLTMGR!FltGetRequestorProcess` at `0x140053551`
- `FLTMGR!FltGetRequestorProcess` at `0x140053551`
- `FLTMGR!FltReleasePushLockEx` at `0x1400532fb`
- `FLTMGR!FltReleasePushLockEx` at `0x1400536ee`
- `FLTMGR!FltReleasePushLockEx` at `0x1400532fb`
- `FLTMGR!FltReleasePushLockEx` at `0x1400536ee`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400532d3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140053717`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400532d3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140053717`
- `FLTMGR!FltReleaseContext` at `0x140053537`
- `FLTMGR!FltReleaseContext` at `0x140053571`
- `FLTMGR!FltReleaseContext` at `0x14005369a`
- `FLTMGR!FltReleaseContext` at `0x1400537da`
- `FLTMGR!FltReleaseContext` at `0x140053537`
- `FLTMGR!FltReleaseContext` at `0x140053571`
- `FLTMGR!FltReleaseContext` at `0x14005369a`
- `FLTMGR!FltReleaseContext` at `0x1400537da`

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
  NTSTATUS v13; // r12d
  NTSTATUS v14; // r13d
  struct _KEVENT *v15; // r15
  PFLT_IO_PARAMETER_BLOCK v16; // r8
  UCHAR MajorFunction; // r11
  ULONG v18; // eax
  PVOID *p_EaBuffer; // rdx
  bool v20; // zf
  ULONG v21; // eax
  unsigned int v22; // r15d
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
  v13 = 0;
  FileObject = (struct _FILE_OBJECT *)*((_QWORD *)Instance + 4);
  Instance = (PFLT_INSTANCE)*((_QWORD *)Instance + 3);
  if ( a2 && (a2[1].Header.SignalState & 1) != 0 )
  {
    v29 = FltCancellableWaitForSingleObject(&a2->Header.WaitListHead.Blink[6], 0, a4);
    HsmDbgBreakOnStatus(v29);
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
                  HsmpCldNotifyPreOperation(4, a4, v22, 0, HsmiDeleteOnCloseNotificationCallback, a4);
                  v13 = FltCancellableWaitForSingleObject(&Event, 0, a4);
                  HsmDbgBreakOnStatus(v13);
                  if ( v13 == -1073741749 || v13 == -1073741536 )
                  {
                    FltCancelIo(a4);
                    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                  }
                  a4->QueueContext[0] = 0;
                  if ( v13 < 0 )
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
  HsmDbgBreakOnStatus(v14);
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
  if ( v13 < 0 )
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
0x140053248  mov     [rsp-38h+arg_0], rbx
0x14005324d  mov     [rsp-38h+arg_8], rdx
0x140053252  push    rbp
0x140053253  push    rsi
0x140053254  push    rdi
0x140053255  push    r12
0x140053257  push    r13
0x140053259  push    r14
0x14005325b  push    r15
0x14005325d  mov     rbp, rsp
0x140053260  sub     rsp, 70h
0x140053264  mov     rbx, r9
0x140053267  mov     rdi, r8
0x14005326a  mov     r13, rdx
0x14005326d  mov     r14, rcx
0x140053270  mov     esi, 1
0x140053275  test    r9, r9
0x140053278  jz      loc_1400534B2
0x14005327e  mov     r8, [r9+10h]
0x140053282  mov     r9b, [r8+4]
0x140053286  cmp     r9b, 6
0x14005328a  jnz     loc_1400534B2
0x140053290  mov     eax, [r8+20h]
0x140053294  cmp     eax, 0Dh
0x140053297  jnz     loc_1400533A8
0x14005329d  mov     rax, [r8+38h]
0x1400532a1  cmp     byte ptr [rax], 0
0x1400532a4  jz      loc_1400533C6
0x1400532aa  mov     rax, [rbp+Instance]
0x1400532ae  xor     r12d, r12d
0x1400532b1  mov     rcx, [rax+18h]
0x1400532b5  mov     rax, [rax+20h]
0x1400532b9  mov     [rbp+FileObject], rax
0x1400532bd  mov     [rbp+Instance], rcx
0x1400532c1  test    r13, r13
0x1400532c4  jnz     loc_1400535A8
0x1400532ca  lea     r15, [r14+70h]
0x1400532ce  xor     edx, edx
0x1400532d0  mov     rcx, r15
0x1400532d3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400532da  nop     dword ptr [rax+rax+00h]
0x1400532df  lea     rcx, [r14+78h]; Event
0x1400532e3  call    cs:__imp_KeClearEvent
0x1400532ea  nop     dword ptr [rax+rax+00h]
0x1400532ef  add     [r14+0A8h], esi
0x1400532f6  xor     edx, edx
0x1400532f8  mov     rcx, r15
0x1400532fb  call    cs:__imp_FltReleasePushLockEx
0x140053302  nop     dword ptr [rax+rax+00h]
0x140053307  lea     rcx, [r14+90h]; Object
0x14005330e  mov     r8, rbx; CallbackData
0x140053311  xor     edx, edx; Timeout
0x140053313  call    cs:__imp_FltCancellableWaitForSingleObject
0x14005331a  nop     dword ptr [rax+rax+00h]
0x14005331f  mov     ecx, eax
0x140053321  mov     r13d, eax
0x140053324  call    HsmDbgBreakOnStatus
0x140053329  test    r13d, r13d
0x14005332c  js      loc_140053712
0x140053332  test    r14, r14
0x140053335  jz      loc_140053705
0x14005333b  mov     r13, r14
0x14005333e  mov     r15, r14
0x140053341  mov     rcx, r15; Context
0x140053344  call    cs:__imp_FltReferenceContext
0x14005334b  nop     dword ptr [rax+rax+00h]
0x140053350  mov     [rbp+var_28], r13
0x140053354  test    rdi, rdi
0x140053357  jz      loc_1400534E0
0x14005335d  mov     byte ptr [rbp+Instance], r12b
0x140053361  mov     r10d, [rdi+28h]
0x140053365  mov     r9d, r10d
0x140053368  mov     r8, [rbx+10h]
0x14005336c  shr     r9d, 0Bh
0x140053370  and     r9d, esi
0x140053373  mov     r11b, [r8+4]
0x140053377  cmp     r11b, 6
0x14005337b  jnz     loc_1400535E8
0x140053381  mov     eax, [r8+20h]
0x140053385  lea     rdx, [r8+38h]
0x140053389  cmp     eax, 0Dh
0x14005338c  jz      loc_140053649
0x140053392  cmp     eax, 40h ; '@'
0x140053395  jnz     loc_1400535E8
0x14005339b  mov     rax, [rdx]
0x14005339e  mov     ecx, [rax]
0x1400533a0  test    sil, cl
0x1400533a3  jmp     loc_14005364F
0x1400533a8  cmp     eax, 40h ; '@'
0x1400533ab  jnz     short loc_1400533C6
0x1400533ad  mov     rax, [r8+38h]
0x1400533b1  mov     ecx, [rax]
0x1400533b3  test    sil, cl
0x1400533b6  jnz     loc_1400532AA
0x1400533bc  cmp     r9b, 6
0x1400533c0  jnz     loc_1400534B2
0x1400533c6  mov     eax, [r8+20h]
0x1400533ca  cmp     eax, 0Dh
0x1400533cd  jnz     loc_1400536B1
0x1400533d3  mov     rax, [r8+38h]
0x1400533d7  cmp     byte ptr [rax], 0
0x1400533da  jz      loc_1400532AA
0x1400533e0  jmp     loc_1400534B2
0x1400533e5  or      r15d, 10h
0x1400533e9  xorps   xmm0, xmm0
0x1400533ec  lea     rcx, [rbp+Event]; Event
0x1400533f0  xor     eax, eax
0x1400533f2  xor     r8d, r8d; State
0x1400533f5  mov     edx, esi; Type
0x1400533f7  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1400533fb  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1400533ff  call    cs:__imp_KeInitializeEvent
0x140053406  nop     dword ptr [rax+rax+00h]
0x14005340b  xor     r9d, r9d
0x14005340e  mov     [rsp+70h+var_48], rbx
0x140053413  lea     rax, [rbp+Event]
0x140053417  mov     r8d, r15d
0x14005341a  mov     [rbx+40h], rax
0x14005341e  mov     rdx, rbx
0x140053421  lea     rax, HsmiDeleteOnCloseNotificationCallback
0x140053428  lea     ecx, [r9+4]
0x14005342c  mov     [rsp+70h+Timeout], rax
0x140053431  call    HsmpCldNotifyPreOperation
0x140053436  mov     r8, rbx; CallbackData
0x140053439  lea     rcx, [rbp+Event]; Object
0x14005343d  xor     edx, edx; Timeout
0x14005343f  call    cs:__imp_FltCancellableWaitForSingleObject
0x140053446  nop     dword ptr [rax+rax+00h]
0x14005344b  mov     ecx, eax
0x14005344d  mov     r12d, eax
0x140053450  call    HsmDbgBreakOnStatus
0x140053455  cmp     r12d, 0C000004Bh
0x14005345c  jz      loc_140053738
0x140053462  cmp     r12d, 0C0000120h
0x140053469  jz      loc_140053738
0x14005346f  mov     qword ptr [rbx+40h], 0
0x140053477  test    r12d, r12d
0x14005347a  js      loc_14005376D
0x140053480  mov     r9, [rbp+arg_28]
0x140053484  lea     r8, [rbp+var_28]
0x140053488  mov     edx, [rbx+18h]
0x14005348b  mov     rcx, rbx
0x14005348e  call    HsmiInfoPrepareForPostSetDispostionInformation
0x140053493  mov     r13, [rbp+var_28]
0x140053497  mov     esi, eax
0x140053499  mov     cl, byte ptr [rbp+Instance]
0x14005349c  test    cl, cl
0x14005349e  jnz     loc_1400537D7
0x1400534a4  test    r13, r13
0x1400534a7  jnz     loc_1400537EB
0x1400534ad  test    r12d, r12d
0x1400534b0  js      short loc_1400534CD
0x1400534b2  mov     rbx, [rsp+70h+arg_0]
0x1400534ba  mov     eax, esi
0x1400534bc  add     rsp, 70h
0x1400534c0  pop     r15
0x1400534c2  pop     r14
0x1400534c4  pop     r13
0x1400534c6  pop     r12
0x1400534c8  pop     rdi
0x1400534c9  pop     rsi
0x1400534ca  pop     rbp
0x1400534cb  retn
0x1400534cd  mov     esi, 4
0x1400534d2  mov     [rbx+18h], r12d
0x1400534d6  mov     qword ptr [rbx+20h], 0
0x1400534de  jmp     short loc_1400534B2
0x1400534e0  mov     rdx, [rbp+FileObject]; FileObject
0x1400534e4  lea     r8, [rbp+Context]; Context
0x1400534e8  mov     rcx, [rbp+Instance]; Instance
0x1400534ec  mov     [rbp+Context], r12
0x1400534f0  call    cs:__imp_FltGetStreamHandleContext
0x1400534f7  nop     dword ptr [rax+rax+00h]
0x1400534fc  mov     rdi, [rbp+Context]
0x140053500  test    rdi, rdi
0x140053503  jz      loc_140053591
0x140053509  mov     rax, [rdi+10h]
0x14005350d  mov     ecx, [rax+1Ch]
0x140053510  test    sil, cl
0x140053513  jz      loc_14005367E
0x140053519  test    rdi, rdi
0x14005351c  jz      short loc_140053591
0x14005351e  mov     rax, [rdi+10h]
0x140053522  mov     rcx, [rax+10h]
0x140053526  mov     rax, [rcx+10h]
0x14005352a  mov     rcx, [rbp+Instance]
0x14005352e  cmp     [rax+20h], rcx
0x140053532  jz      short loc_140053549
0x140053534  mov     rcx, rdi; Context
0x140053537  call    cs:__imp_FltReleaseContext
0x14005353e  nop     dword ptr [rax+rax+00h]
0x140053543  xor     edi, edi
0x140053545  mov     [rbp+Context], rdi
0x140053549  test    rdi, rdi
0x14005354c  jz      short loc_140053591
0x14005354e  mov     rcx, rbx; CallbackData
0x140053551  call    cs:__imp_FltGetRequestorProcess
0x140053558  nop     dword ptr [rax+rax+00h]
0x14005355d  mov     rcx, rax
0x140053560  call    HsmOsIsPassThroughModeEnabled
0x140053565  test    al, al
0x140053567  jz      loc_14005372F
0x14005356d  mov     rcx, [rbp+Context]; Context
0x140053571  call    cs:__imp_FltReleaseContext
0x140053578  nop     dword ptr [rax+rax+00h]
0x14005357d  xor     edi, edi
0x14005357f  mov     [rbp+Context], rdi
0x140053583  test    rdi, rdi
0x140053586  jz      short loc_140053591
0x140053588  mov     byte ptr [rbp+Instance], sil
0x14005358c  jmp     loc_140053361
0x140053591  xor     cl, cl
0x140053593  mov     rax, [rbp+arg_28]
0x140053597  xor     esi, esi
0x140053599  mov     rdi, [rbp+arg_8]
0x14005359d  xor     r13d, r13d
0x1400535a0  mov     [rax], r15
0x1400535a3  jmp     loc_14005349C
0x1400535a8  mov     eax, [rdx+1Ch]
0x1400535ab  test    sil, al
0x1400535ae  jz      loc_1400532CA
0x1400535b4  mov     rcx, [rdx+10h]
0x1400535b8  mov     r8, rbx; CallbackData
0x1400535bb  add     rcx, 60h ; '`'; Object
0x1400535bf  xor     edx, edx; Timeout
0x1400535c1  call    cs:__imp_FltCancellableWaitForSingleObject
0x1400535c8  nop     dword ptr [rax+rax+00h]
0x1400535cd  mov     ecx, eax
0x1400535cf  mov     r15d, eax
0x1400535d2  call    HsmDbgBreakOnStatus
0x1400535d7  test    r15d, r15d
0x1400535da  js      loc_1400536CE
0x1400535e0  mov     r15, r13
0x1400535e3  jmp     loc_140053341
0x1400535e8  xor     eax, eax
0x1400535ea  lea     rdx, [r8+38h]
0x1400535ee  cmp     r9d, eax
0x1400535f1  jz      loc_1400537CF
0x1400535f7  xor     r15d, r15d
0x1400535fa  cmp     r11b, 6
0x1400535fe  jnz     short loc_14005361A
0x140053600  mov     eax, [r8+20h]
0x140053604  cmp     eax, 0Dh
0x140053607  jnz     short loc_14005366D
0x140053609  mov     rax, [rdx]
0x14005360c  cmp     [rax], r12b
0x14005360f  jz      short loc_14005361A
0x140053611  bts     r10d, 0Bh
0x140053616  mov     [rdi+28h], r10d
0x14005361a  mov     rax, [rbx+10h]
0x14005361e  cmp     byte ptr [rax+4], 6
0x140053622  jnz     short loc_140053635
0x140053624  mov     ecx, [rax+20h]
0x140053627  cmp     ecx, 0Dh
0x14005362a  jnz     short loc_140053655
0x14005362c  mov     rax, [rax+38h]
0x140053630  cmp     [rax], r12b
0x140053633  jz      short loc_140053665
0x140053635  mov     rdi, [rbp+arg_8]
0x140053639  mov     eax, [rdi+1Ch]
0x14005363c  test    al, 2
0x14005363e  jnz     loc_1400533E5
0x140053644  jmp     loc_1400533E9
0x140053649  mov     rax, [rdx]
0x14005364c  cmp     [rax], r12b
0x14005364f  jz      short loc_1400535E8
0x140053651  mov     eax, esi
0x140053653  jmp     short loc_1400535EE
0x140053655  cmp     ecx, 40h ; '@'
0x140053658  jnz     short loc_140053635
0x14005365a  mov     rax, [rax+38h]
0x14005365e  mov     ecx, [rax]
0x140053660  test    sil, cl
0x140053663  jnz     short loc_140053635
0x140053665  mov     r15d, 80h
0x14005366b  jmp     short loc_140053635
0x14005366d  cmp     eax, 40h ; '@'
0x140053670  jnz     short loc_14005361A
0x140053672  mov     rax, [rdx]
0x140053675  mov     ecx, [rax]
0x140053677  test    sil, cl
0x14005367a  jz      short loc_14005361A
0x14005367c  jmp     short loc_140053611
0x14005367e  test    rdi, rdi
0x140053681  jz      loc_140053591
0x140053687  mov     rcx, rdi; Context
0x14005368a  call    cs:__imp_FltDeleteContext
0x140053691  nop     dword ptr [rax+rax+00h]
0x140053696  mov     rcx, [rbp+Context]; Context
0x14005369a  call    cs:__imp_FltReleaseContext
0x1400536a1  nop     dword ptr [rax+rax+00h]
0x1400536a6  xor     edi, edi
0x1400536a8  mov     [rbp+Context], rdi
0x1400536ac  jmp     loc_140053519
0x1400536b1  cmp     eax, 40h ; '@'
0x1400536b4  jnz     loc_1400534B2
0x1400536ba  mov     rax, [r8+38h]
0x1400536be  mov     ecx, [rax]
0x1400536c0  test    sil, cl
0x1400536c3  jnz     loc_1400534B2
  ... truncated ...
```
