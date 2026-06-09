# CKsPin::Property_StreamMasterClock(_IRP *,KSIDENTIFIER *,void * *)

- ea: `0x1800604d0`
- end: `0x1800607b8`
- name: `?Property_StreamMasterClock@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAPEAX@Z`
- size: `744`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b7bc`
- `0x18000c058`
- `0x180051360`
- `0x1800604d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800606ff`
- `ntoskrnl!ObfDereferenceObject` at `0x180060767`
- `ntoskrnl!ObfDereferenceObject` at `0x1800606ff`
- `ntoskrnl!ObfDereferenceObject` at `0x180060767`
- `ntoskrnl!ExGetPreviousMode` at `0x180060650`
- `ntoskrnl!ExGetPreviousMode` at `0x180060650`
- `ntoskrnl!KeReleaseMutex` at `0x18006057d`
- `ntoskrnl!KeReleaseMutex` at `0x18006057d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006067f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006067f`
- `ntoskrnl!IoFileObjectType` at `0x18006065c`
- `ntoskrnl!KeResetEvent` at `0x180060726`
- `ntoskrnl!KeResetEvent` at `0x180060726`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006053a`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060754`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006053a`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060754`

## pseudocode

```c
__int64 __fastcall CKsPin::Property_StreamMasterClock(struct _IRP *a1, struct KSIDENTIFIER *a2, void **a3)
{
  struct KSIDENTIFIER *v4; // rdi
  __int64 v6; // rbx
  int v7; // edx
  int v8; // r8d
  _DWORD *v9; // rcx
  NTSTATUS v10; // edi
  KPROCESSOR_MODE PreviousMode; // al
  __int128 v13; // xmm1
  GUID InBuffer; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+54h] [rbp-2Ch]
  __int128 OutBuffer; // [rsp+58h] [rbp-28h] BYREF
  __int128 v18; // [rsp+68h] [rbp-18h]
  ULONG BytesReturned; // [rsp+B0h] [rbp+30h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+38h] BYREF

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      140,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  v6 = *(_QWORD *)(*(_QWORD *)a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  KeWaitForSingleObject(*(PVOID *)(v6 + 88), Executive, 0, 0, 0);
  if ( (v4->Flags & 1) != 0 )
  {
    v9 = *(_DWORD **)(v6 + 128);
    if ( *(_QWORD *)v9 && *(_QWORD *)(*(_QWORD *)v9 + 64LL) || (v9[26] & 0x400000) != 0 )
    {
      *a3 = 0;
      v10 = 0;
    }
    else
    {
      v10 = -1073741823;
    }
    goto LABEL_6;
  }
  if ( *(_DWORD *)(v6 + 248) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        141,
        (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
        *(_DWORD *)(v6 + 248));
    }
    v10 = -1073741436;
    goto LABEL_6;
  }
  Object = 0;
  OutBuffer = 0;
  v18 = 0;
  if ( *a3 )
  {
    PreviousMode = ExGetPreviousMode();
    v10 = ObReferenceObjectByHandle(*a3, 0x100001u, (POBJECT_TYPE)IoFileObjectType, PreviousMode, &Object, 0);
    if ( v10 < 0 )
      goto LABEL_6;
    InBuffer = GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000;
    v15 = 6;
    v16 = 1;
    BytesReturned = 0;
    v10 = KsSynchronousIoControlDevice(
            (PFILE_OBJECT)Object,
            0,
            0x2F0003u,
            &InBuffer,
            0x18u,
            &OutBuffer,
            0x20u,
            &BytesReturned);
    if ( v10 < 0 )
    {
LABEL_22:
      ObfDereferenceObject(Object);
      goto LABEL_6;
    }
    if ( BytesReturned != 32 )
    {
      v10 = -1073741306;
      goto LABEL_22;
    }
  }
  else
  {
    v10 = 0;
  }
  if ( *(_QWORD *)(v6 + 760) )
  {
    KeResetEvent((PRKEVENT)(v6 + 808));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 800), 0xFFFFFFFF) > 1 )
      KeWaitForSingleObject((PVOID)(v6 + 808), Suspended, 0, 0, 0);
    ObfDereferenceObject(*(PVOID *)(v6 + 760));
    *(_QWORD *)(v6 + 760) = 0;
  }
  if ( *a3 )
  {
    *(_QWORD *)(v6 + 760) = Object;
    v13 = v18;
    *(_OWORD *)(v6 + 768) = OutBuffer;
    *(_OWORD *)(v6 + 784) = v13;
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 800));
  }
LABEL_6:
  KeReleaseMutex(*(PRKMUTEX *)(v6 + 88), 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800604d0  mov     [rsp-28h+arg_10], rbx
0x1800604d5  mov     [rsp-28h+arg_18], rsi
0x1800604da  push    rbp
0x1800604db  push    rdi
0x1800604dc  push    r13
0x1800604de  push    r14
0x1800604e0  push    r15
0x1800604e2  mov     rbp, rsp
0x1800604e5  sub     rsp, 80h
0x1800604ec  mov     rsi, r8
0x1800604ef  mov     rdi, rdx
0x1800604f2  mov     rbx, rcx
0x1800604f5  lea     r14, WPP_RECORDER_INITIALIZED
0x1800604fc  xor     r15d, r15d
0x1800604ff  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180060506  lea     r13, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18006050d  jnz     loc_1800605A8
0x180060513  mov     rax, [rbx+0B8h]
0x18006051a  xor     r9d, r9d; Alertable
0x18006051d  xor     r8d, r8d; WaitMode
0x180060520  mov     [rsp+80h+Timeout], r15; Timeout
0x180060525  xor     edx, edx; WaitReason
0x180060527  mov     rcx, [rax+30h]
0x18006052b  mov     rax, [rcx+18h]
0x18006052f  mov     rcx, [rax]
0x180060532  mov     rbx, [rcx+70h]
0x180060536  mov     rcx, [rbx+58h]; Object
0x18006053a  call    cs:__imp_KeWaitForSingleObject
0x180060541  nop     dword ptr [rax+rax+00h]
0x180060546  mov     eax, [rdi+14h]
0x180060549  test    al, 1
0x18006054b  jz      loc_1800605DB
0x180060551  mov     rcx, [rbx+80h]
0x180060558  mov     rax, [rcx]
0x18006055b  test    rax, rax
0x18006055e  jnz     loc_1800605F5
0x180060564  test    dword ptr [rcx+68h], 400000h
0x18006056b  jz      loc_180060604
0x180060571  mov     [rsi], r15
0x180060574  mov     edi, r15d
0x180060577  mov     rcx, [rbx+58h]; Mutex
0x18006057b  xor     edx, edx; Wait
0x18006057d  call    cs:__imp_KeReleaseMutex
0x180060584  nop     dword ptr [rax+rax+00h]
0x180060589  lea     r11, [rsp+80h+var_s0]
0x180060591  mov     eax, edi
0x180060593  mov     rbx, [r11+40h]
0x180060597  mov     rsi, [r11+48h]
0x18006059b  mov     rsp, r11
0x18006059e  pop     r15
0x1800605a0  pop     r14
0x1800605a2  pop     r13
0x1800605a4  pop     rdi
0x1800605a5  pop     rbp
0x1800605a6  retn
0x1800605a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800605af  cmp     [rcx+48h], r15w
0x1800605b4  jz      loc_180060513
0x1800605ba  mov     rcx, [rcx+40h]
0x1800605be  mov     r9d, 8Ch
0x1800605c4  mov     r8d, 1
0x1800605ca  mov     [rsp+80h+Timeout], r13
0x1800605cf  mov     dl, 5
0x1800605d1  call    WPP_RECORDER_SF_
0x1800605d6  jmp     loc_180060513
0x1800605db  mov     eax, [rbx+0F8h]
0x1800605e1  test    eax, eax
0x1800605e3  jz      short loc_180060638
0x1800605e5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800605ec  jnz     short loc_18006060E
0x1800605ee  mov     edi, 0C0000184h
0x1800605f3  jmp     short loc_180060577
0x1800605f5  cmp     [rax+40h], r15
0x1800605f9  jnz     loc_180060571
0x1800605ff  jmp     loc_180060564
0x180060604  mov     edi, 0C0000001h
0x180060609  jmp     loc_180060577
0x18006060e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060615  cmp     [rcx+48h], r15w
0x18006061a  jz      short loc_1800605EE
0x18006061c  mov     rcx, [rcx+40h]
0x180060620  mov     r9d, 8Dh
0x180060626  mov     dword ptr [rsp+80h+HandleInformation], eax
0x18006062a  mov     dl, 5
0x18006062c  mov     [rsp+80h+Timeout], r13
0x180060631  call    WPP_RECORDER_SF_d
0x180060636  jmp     short loc_1800605EE
0x180060638  xorps   xmm0, xmm0
0x18006063b  mov     [rbp+Object], r15
0x18006063f  movups  [rbp+OutBuffer], xmm0
0x180060643  movups  [rbp+var_18], xmm0
0x180060647  cmp     [rsi], r15
0x18006064a  jz      loc_180060710
0x180060650  call    cs:__imp_ExGetPreviousMode
0x180060657  nop     dword ptr [rax+rax+00h]
0x18006065c  mov     r8, cs:__imp_IoFileObjectType
0x180060663  lea     rcx, [rbp+Object]
0x180060667  mov     [rsp+80h+HandleInformation], r15; HandleInformation
0x18006066c  mov     r9b, al; AccessMode
0x18006066f  mov     [rsp+80h+Timeout], rcx; Object
0x180060674  mov     edx, 100001h; DesiredAccess
0x180060679  mov     rcx, [rsi]; Handle
0x18006067c  mov     r8, [r8]; ObjectType
0x18006067f  call    cs:__imp_ObReferenceObjectByHandle
0x180060686  nop     dword ptr [rax+rax+00h]
0x18006068b  mov     edi, eax
0x18006068d  test    eax, eax
0x18006068f  js      loc_180060577
0x180060695  movups  xmm0, xmmword ptr cs:_GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000.Data1
0x18006069c  mov     rcx, [rbp+Object]; FileObject
0x1800606a0  lea     rax, [rbp+arg_0]
0x1800606a4  mov     [rsp+80h+BytesReturned], rax; BytesReturned
0x1800606a9  lea     r9, [rbp+InBuffer]; InBuffer
0x1800606ad  lea     rax, [rbp+OutBuffer]
0x1800606b1  mov     [rsp+80h+OutSize], 20h ; ' '; OutSize
0x1800606b9  mov     [rsp+80h+HandleInformation], rax; OutBuffer
0x1800606be  xor     edx, edx; RequestorMode
0x1800606c0  mov     r8d, 2F0003h; IoControl
0x1800606c6  mov     dword ptr [rsp+80h+Timeout], 18h; InSize
0x1800606ce  movdqu  [rbp+InBuffer], xmm0
0x1800606d3  mov     [rbp+var_30], 6
0x1800606da  mov     [rbp+var_2C], 1
0x1800606e1  mov     [rbp+arg_0], r15d
0x1800606e5  call    KsSynchronousIoControlDevice
0x1800606ea  mov     edi, eax
0x1800606ec  test    eax, eax
0x1800606ee  js      short loc_1800606FB
0x1800606f0  cmp     [rbp+arg_0], 20h ; ' '
0x1800606f4  jz      short loc_180060713
0x1800606f6  mov     edi, 0C0000206h
0x1800606fb  mov     rcx, [rbp+Object]; Object
0x1800606ff  call    cs:__imp_ObfDereferenceObject
0x180060706  nop     dword ptr [rax+rax+00h]
0x18006070b  jmp     loc_180060577
0x180060710  mov     edi, r15d
0x180060713  cmp     [rbx+2F8h], r15
0x18006071a  jz      short loc_18006077A
0x18006071c  lea     r14, [rbx+328h]
0x180060723  mov     rcx, r14; Event
0x180060726  call    cs:__imp_KeResetEvent
0x18006072d  nop     dword ptr [rax+rax+00h]
0x180060732  or      eax, 0FFFFFFFFh
0x180060735  lock xadd [rbx+320h], eax
0x18006073d  sub     eax, 1
0x180060740  jle     short loc_180060760
0x180060742  xor     r9d, r9d; Alertable
0x180060745  mov     [rsp+80h+Timeout], r15; Timeout
0x18006074a  xor     r8d, r8d; WaitMode
0x18006074d  mov     rcx, r14; Object
0x180060750  lea     edx, [r9+5]; WaitReason
0x180060754  call    cs:__imp_KeWaitForSingleObject
0x18006075b  nop     dword ptr [rax+rax+00h]
0x180060760  mov     rcx, [rbx+2F8h]; Object
0x180060767  call    cs:__imp_ObfDereferenceObject
0x18006076e  nop     dword ptr [rax+rax+00h]
0x180060773  mov     [rbx+2F8h], r15
0x18006077a  cmp     [rsi], r15
0x18006077d  jz      loc_180060577
0x180060783  mov     rax, [rbp+Object]
0x180060787  mov     [rbx+2F8h], rax
0x18006078e  movups  xmm0, [rbp+OutBuffer]
0x180060792  movups  xmm1, [rbp+var_18]
0x180060796  movups  xmmword ptr [rbx+300h], xmm0
0x18006079d  movups  xmmword ptr [rbx+310h], xmm1
0x1800607a4  test    edi, edi
0x1800607a6  js      loc_180060577
0x1800607ac  lock inc dword ptr [rbx+320h]
0x1800607b3  jmp     loc_180060577
```
