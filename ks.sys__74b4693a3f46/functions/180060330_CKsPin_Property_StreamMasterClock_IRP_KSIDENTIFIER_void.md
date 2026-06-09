# CKsPin::Property_StreamMasterClock(_IRP *,KSIDENTIFIER *,void * *)

- ea: `0x180060330`
- end: `0x180060618`
- name: `?Property_StreamMasterClock@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAPEAX@Z`
- size: `744`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b7bc`
- `0x18000c058`
- `0x1800511c0`
- `0x180060330`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18006055f`
- `ntoskrnl!ObfDereferenceObject` at `0x1800605c7`
- `ntoskrnl!ObfDereferenceObject` at `0x18006055f`
- `ntoskrnl!ObfDereferenceObject` at `0x1800605c7`
- `ntoskrnl!ExGetPreviousMode` at `0x1800604b0`
- `ntoskrnl!ExGetPreviousMode` at `0x1800604b0`
- `ntoskrnl!KeReleaseMutex` at `0x1800603dd`
- `ntoskrnl!KeReleaseMutex` at `0x1800603dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800604df`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800604df`
- `ntoskrnl!IoFileObjectType` at `0x1800604bc`
- `ntoskrnl!KeResetEvent` at `0x180060586`
- `ntoskrnl!KeResetEvent` at `0x180060586`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006039a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800605b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006039a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800605b4`

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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
0x180060330  mov     [rsp-28h+arg_10], rbx
0x180060335  mov     [rsp-28h+arg_18], rsi
0x18006033a  push    rbp
0x18006033b  push    rdi
0x18006033c  push    r13
0x18006033e  push    r14
0x180060340  push    r15
0x180060342  mov     rbp, rsp
0x180060345  sub     rsp, 80h
0x18006034c  mov     rsi, r8
0x18006034f  mov     rdi, rdx
0x180060352  mov     rbx, rcx
0x180060355  lea     r14, WPP_RECORDER_INITIALIZED
0x18006035c  xor     r15d, r15d
0x18006035f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180060366  lea     r13, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18006036d  jnz     loc_180060408
0x180060373  mov     rax, [rbx+0B8h]
0x18006037a  xor     r9d, r9d; Alertable
0x18006037d  xor     r8d, r8d; WaitMode
0x180060380  mov     [rsp+80h+Timeout], r15; Timeout
0x180060385  xor     edx, edx; WaitReason
0x180060387  mov     rcx, [rax+30h]
0x18006038b  mov     rax, [rcx+18h]
0x18006038f  mov     rcx, [rax]
0x180060392  mov     rbx, [rcx+70h]
0x180060396  mov     rcx, [rbx+58h]; Object
0x18006039a  call    cs:__imp_KeWaitForSingleObject
0x1800603a1  nop     dword ptr [rax+rax+00h]
0x1800603a6  mov     eax, [rdi+14h]
0x1800603a9  test    al, 1
0x1800603ab  jz      loc_18006043B
0x1800603b1  mov     rcx, [rbx+80h]
0x1800603b8  mov     rax, [rcx]
0x1800603bb  test    rax, rax
0x1800603be  jnz     loc_180060455
0x1800603c4  test    dword ptr [rcx+68h], 400000h
0x1800603cb  jz      loc_180060464
0x1800603d1  mov     [rsi], r15
0x1800603d4  mov     edi, r15d
0x1800603d7  mov     rcx, [rbx+58h]; Mutex
0x1800603db  xor     edx, edx; Wait
0x1800603dd  call    cs:__imp_KeReleaseMutex
0x1800603e4  nop     dword ptr [rax+rax+00h]
0x1800603e9  lea     r11, [rsp+80h+var_s0]
0x1800603f1  mov     eax, edi
0x1800603f3  mov     rbx, [r11+40h]
0x1800603f7  mov     rsi, [r11+48h]
0x1800603fb  mov     rsp, r11
0x1800603fe  pop     r15
0x180060400  pop     r14
0x180060402  pop     r13
0x180060404  pop     rdi
0x180060405  pop     rbp
0x180060406  retn
0x180060408  mov     rcx, cs:WPP_GLOBAL_Control
0x18006040f  cmp     [rcx+48h], r15w
0x180060414  jz      loc_180060373
0x18006041a  mov     rcx, [rcx+40h]
0x18006041e  mov     r9d, 8Ch
0x180060424  mov     r8d, 1
0x18006042a  mov     [rsp+80h+Timeout], r13
0x18006042f  mov     dl, 5
0x180060431  call    WPP_RECORDER_SF_
0x180060436  jmp     loc_180060373
0x18006043b  mov     eax, [rbx+0F8h]
0x180060441  test    eax, eax
0x180060443  jz      short loc_180060498
0x180060445  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18006044c  jnz     short loc_18006046E
0x18006044e  mov     edi, 0C0000184h
0x180060453  jmp     short loc_1800603D7
0x180060455  cmp     [rax+40h], r15
0x180060459  jnz     loc_1800603D1
0x18006045f  jmp     loc_1800603C4
0x180060464  mov     edi, 0C0000001h
0x180060469  jmp     loc_1800603D7
0x18006046e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060475  cmp     [rcx+48h], r15w
0x18006047a  jz      short loc_18006044E
0x18006047c  mov     rcx, [rcx+40h]
0x180060480  mov     r9d, 8Dh
0x180060486  mov     dword ptr [rsp+80h+HandleInformation], eax
0x18006048a  mov     dl, 5
0x18006048c  mov     [rsp+80h+Timeout], r13
0x180060491  call    WPP_RECORDER_SF_d
0x180060496  jmp     short loc_18006044E
0x180060498  xorps   xmm0, xmm0
0x18006049b  mov     [rbp+Object], r15
0x18006049f  movups  [rbp+OutBuffer], xmm0
0x1800604a3  movups  [rbp+var_18], xmm0
0x1800604a7  cmp     [rsi], r15
0x1800604aa  jz      loc_180060570
0x1800604b0  call    cs:__imp_ExGetPreviousMode
0x1800604b7  nop     dword ptr [rax+rax+00h]
0x1800604bc  mov     r8, cs:__imp_IoFileObjectType
0x1800604c3  lea     rcx, [rbp+Object]
0x1800604c7  mov     [rsp+80h+HandleInformation], r15; HandleInformation
0x1800604cc  mov     r9b, al; AccessMode
0x1800604cf  mov     [rsp+80h+Timeout], rcx; Object
0x1800604d4  mov     edx, 100001h; DesiredAccess
0x1800604d9  mov     rcx, [rsi]; Handle
0x1800604dc  mov     r8, [r8]; ObjectType
0x1800604df  call    cs:__imp_ObReferenceObjectByHandle
0x1800604e6  nop     dword ptr [rax+rax+00h]
0x1800604eb  mov     edi, eax
0x1800604ed  test    eax, eax
0x1800604ef  js      loc_1800603D7
0x1800604f5  movups  xmm0, xmmword ptr cs:_GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000.Data1
0x1800604fc  mov     rcx, [rbp+Object]; FileObject
0x180060500  lea     rax, [rbp+arg_0]
0x180060504  mov     [rsp+80h+BytesReturned], rax; BytesReturned
0x180060509  lea     r9, [rbp+InBuffer]; InBuffer
0x18006050d  lea     rax, [rbp+OutBuffer]
0x180060511  mov     [rsp+80h+OutSize], 20h ; ' '; OutSize
0x180060519  mov     [rsp+80h+HandleInformation], rax; OutBuffer
0x18006051e  xor     edx, edx; RequestorMode
0x180060520  mov     r8d, 2F0003h; IoControl
0x180060526  mov     dword ptr [rsp+80h+Timeout], 18h; InSize
0x18006052e  movdqu  [rbp+InBuffer], xmm0
0x180060533  mov     [rbp+var_30], 6
0x18006053a  mov     [rbp+var_2C], 1
0x180060541  mov     [rbp+arg_0], r15d
0x180060545  call    KsSynchronousIoControlDevice
0x18006054a  mov     edi, eax
0x18006054c  test    eax, eax
0x18006054e  js      short loc_18006055B
0x180060550  cmp     [rbp+arg_0], 20h ; ' '
0x180060554  jz      short loc_180060573
0x180060556  mov     edi, 0C0000206h
0x18006055b  mov     rcx, [rbp+Object]; Object
0x18006055f  call    cs:__imp_ObfDereferenceObject
0x180060566  nop     dword ptr [rax+rax+00h]
0x18006056b  jmp     loc_1800603D7
0x180060570  mov     edi, r15d
0x180060573  cmp     [rbx+2F8h], r15
0x18006057a  jz      short loc_1800605DA
0x18006057c  lea     r14, [rbx+328h]
0x180060583  mov     rcx, r14; Event
0x180060586  call    cs:__imp_KeResetEvent
0x18006058d  nop     dword ptr [rax+rax+00h]
0x180060592  or      eax, 0FFFFFFFFh
0x180060595  lock xadd [rbx+320h], eax
0x18006059d  sub     eax, 1
0x1800605a0  jle     short loc_1800605C0
0x1800605a2  xor     r9d, r9d; Alertable
0x1800605a5  mov     [rsp+80h+Timeout], r15; Timeout
0x1800605aa  xor     r8d, r8d; WaitMode
0x1800605ad  mov     rcx, r14; Object
0x1800605b0  lea     edx, [r9+5]; WaitReason
0x1800605b4  call    cs:__imp_KeWaitForSingleObject
0x1800605bb  nop     dword ptr [rax+rax+00h]
0x1800605c0  mov     rcx, [rbx+2F8h]; Object
0x1800605c7  call    cs:__imp_ObfDereferenceObject
0x1800605ce  nop     dword ptr [rax+rax+00h]
0x1800605d3  mov     [rbx+2F8h], r15
0x1800605da  cmp     [rsi], r15
0x1800605dd  jz      loc_1800603D7
0x1800605e3  mov     rax, [rbp+Object]
0x1800605e7  mov     [rbx+2F8h], rax
0x1800605ee  movups  xmm0, [rbp+OutBuffer]
0x1800605f2  movups  xmm1, [rbp+var_18]
0x1800605f6  movups  xmmword ptr [rbx+300h], xmm0
0x1800605fd  movups  xmmword ptr [rbx+310h], xmm1
0x180060604  test    edi, edi
0x180060606  js      loc_1800603D7
0x18006060c  lock inc dword ptr [rbx+320h]
0x180060613  jmp     loc_1800603D7
```
