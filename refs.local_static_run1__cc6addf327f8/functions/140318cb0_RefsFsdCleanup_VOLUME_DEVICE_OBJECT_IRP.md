# RefsFsdCleanup(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x140318cb0`
- end: `0x140319009`
- name: `?RefsFsdCleanup@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `857`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050b60`
- `0x140075660`
- `0x14009a130`
- `0x1400a069c`
- `0x1400cee08`
- `0x1401f3fb0`
- `0x140297bc8`
- `0x140318cb0`
- `0x140319010`
- `0x14033a7a8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140318fd7`
- `ntoskrnl!IofCompleteRequest` at `0x140318fd7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140318d90`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140318d90`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140318e1c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140318e1c`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140318e38`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140318e38`
- `ntoskrnl!IoGetStackLimits` at `0x140318e7d`
- `ntoskrnl!IoGetStackLimits` at `0x140318e7d`
- `ntoskrnl!IoClearActivityIdThread` at `0x140318ffb`
- `ntoskrnl!IoClearActivityIdThread` at `0x140318ffb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140318f8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140318f8e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140318f14`
- `ntoskrnl!KeWaitForSingleObject` at `0x140318f14`
- `ntoskrnl!KeInitializeEvent` at `0x140318e10`
- `ntoskrnl!KeInitializeEvent` at `0x140318e10`
- `HAL!KeQueryPerformanceCounter` at `0x140318dbd`
- `HAL!KeQueryPerformanceCounter` at `0x140318dbd`

## pseudocode

```c
__int64 __fastcall RefsFsdCleanup(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _TOP_LEVEL_CONTEXT *v3; // rbx
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  int v6; // r15d
  int v7; // edx
  unsigned int v8; // eax
  int v10; // [rsp+3Ch] [rbp-3DCh]
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-3D8h] BYREF
  unsigned __int64 LowLimit[2]; // [rsp+48h] [rbp-3D0h] BYREF
  __int64 v13; // [rsp+58h] [rbp-3C0h] BYREF
  struct _IRP *v14; // [rsp+60h] [rbp-3B8h]
  struct _KEVENT Event; // [rsp+70h] [rbp-3A8h] BYREF
  __int128 v16; // [rsp+88h] [rbp-390h] BYREF
  __int64 v17; // [rsp+98h] [rbp-380h]
  __int128 v18; // [rsp+A0h] [rbp-378h] BYREF
  _BYTE v19[4]; // [rsp+B0h] [rbp-368h] BYREF
  int v20; // [rsp+B4h] [rbp-364h]
  __int64 v21; // [rsp+B8h] [rbp-360h]
  __int16 v22; // [rsp+DAh] [rbp-33Eh]
  _BYTE *v23; // [rsp+E0h] [rbp-338h]
  __int64 v24; // [rsp+F0h] [rbp-328h]
  __int64 v25; // [rsp+118h] [rbp-300h]
  PVOID Object; // [rsp+148h] [rbp-2D0h]
  LARGE_INTEGER PerformanceCounter; // [rsp+360h] [rbp-B8h]
  int v28; // [rsp+36Ch] [rbp-ACh]
  _BYTE v29[32]; // [rsp+3D0h] [rbp-48h] BYREF

  LowLimit[1] = (unsigned __int64)a2;
  v14 = a2;
  v16 = 0;
  v17 = 0;
  memset(v29, 0, sizeof(v29));
  memset(&Event, 0, sizeof(Event));
  v18 = 0;
  v13 = 0;
  if ( *((_WORD *)a1 + 1) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  else
  {
    v3 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v16, 0, 0);
    v4 = RefsInitializeLocalIrpContext(a2, (struct _LARGE_IRP_CONTEXT *)v19);
    v5 = v4;
    if ( v4 < 0 )
    {
      RefsCompleteRequest(0, a2, v4);
    }
    else
    {
      v6 = 0;
      if ( !*((_QWORD *)v3 + 2) )
      {
        *((_DWORD *)v3 + 1) = 1397140410;
        *((_QWORD *)v3 + 2) = v19;
        v21 |= 0x100000uLL;
        IoSetTopLevelIrp((PIRP)v3);
      }
      v25 = *((_QWORD *)v3 + 2);
      if ( *(_BYTE *)(v24 + 10304) )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v28 = 24;
      }
      v23 = v29;
      v22 = 4;
      Object = &Event;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      KeEnterCriticalRegion();
      v10 = IoPropagateActivityIdToThread(a2, &v18, &v13);
      do
      {
        if ( v5 == -1073741432 )
        {
          RefsCheckpointForLogFileFull((struct _IRP_CONTEXT *)v19);
          if ( (unsigned int)++v6 >= 2 )
            v20 |= 0x10u;
        }
        else if ( v5 == 871 )
        {
          v14->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
          KeWaitForSingleObject(Object, Executive, 0, 0, 0);
        }
        RefsPreRequestProcessingExtend((struct _IRP_CONTEXT *)v19, v7);
        HighLimit = 0;
        LowLimit[0] = 0;
        IoGetStackLimits(LowLimit, &HighLimit);
        if ( (unsigned __int64)&LowLimit[-1] - LowLimit[0] <= 0x4800 )
          v8 = RefsCommonCleanupOnNewStack((struct _IRP_CONTEXT *)v19, a2);
        else
          v8 = RefsCommonCleanup((struct _IRP_CONTEXT *)v19, a2);
        v5 = v8;
      }
      while ( v8 == -1073741608 || v8 == -1073741400 || v8 == -1073741432 || v8 == 871 );
      if ( v10 >= 0 )
        IoClearActivityIdThread(v13);
      KeLeaveCriticalRegion();
    }
    return v5;
  }
}

```

## disassembly

```asm
0x140318cb0  mov     r11, rsp
0x140318cb3  mov     [r11+8], rbx
0x140318cb7  mov     [r11+18h], rsi
0x140318cbb  push    rdi
0x140318cbc  push    r14
0x140318cbe  push    r15
0x140318cc0  sub     rsp, 400h
0x140318cc7  mov     rax, cs:__security_cookie
0x140318cce  xor     rax, rsp
0x140318cd1  mov     [rsp+418h+var_28], rax
0x140318cd9  mov     rsi, rdx
0x140318cdc  mov     [rsp+418h+var_3C8], rdx
0x140318ce1  mov     [rsp+418h+var_3B8], rdx
0x140318ce6  xorps   xmm0, xmm0
0x140318ce9  xor     eax, eax
0x140318ceb  movups  [rsp+418h+var_390], xmm0
0x140318cf3  mov     [r11-380h], rax
0x140318cfa  xorps   xmm1, xmm1
0x140318cfd  movups  xmmword ptr [r11-48h], xmm1
0x140318d02  movups  xmmword ptr [r11-38h], xmm1
0x140318d07  movups  xmmword ptr [rsp+418h+Event.Header], xmm0
0x140318d0c  mov     [r11-398h], rax
0x140318d13  movups  [rsp+418h+var_378], xmm0
0x140318d1b  xor     r14d, r14d
0x140318d1e  mov     [rsp+418h+var_3C0], r14
0x140318d23  mov     eax, 150h
0x140318d28  cmp     [rcx+2], ax
0x140318d2c  jz      loc_140318FC6
0x140318d32  xor     r8d, r8d; unsigned __int8
0x140318d35  xor     edx, edx; unsigned __int8
0x140318d37  lea     rcx, [r11-390h]; struct _TOP_LEVEL_CONTEXT *
0x140318d3e  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x140318d43  mov     rbx, rax
0x140318d46  lea     rdx, [rsp+418h+var_368]; struct _LARGE_IRP_CONTEXT *
0x140318d4e  mov     rcx, rsi; struct _IRP *
0x140318d51  call    ?RefsInitializeLocalIrpContext@@YAJPEAU_IRP@@PEAU_LARGE_IRP_CONTEXT@@@Z; RefsInitializeLocalIrpContext(_IRP *,_LARGE_IRP_CONTEXT *)
0x140318d56  mov     edi, eax
0x140318d58  test    eax, eax
0x140318d5a  js      loc_140318FE7
0x140318d60  mov     r15d, r14d
0x140318d63  mov     [rsp+418h+var_3E4], r14d
0x140318d68  cmp     [rbx+10h], r14
0x140318d6c  jnz     short loc_140318D9C
0x140318d6e  mov     dword ptr [rbx+4], 5346ABBAh
0x140318d75  lea     rax, [rsp+418h+var_368]
0x140318d7d  mov     [rbx+10h], rax
0x140318d81  or      [rsp+418h+var_360], 100000h
0x140318d8d  mov     rcx, rbx; Irp
0x140318d90  call    cs:__imp_IoSetTopLevelIrp
0x140318d97  nop     dword ptr [rax+rax+00h]
0x140318d9c  mov     rax, [rbx+10h]
0x140318da0  mov     [rsp+418h+var_300], rax
0x140318da8  mov     rax, [rsp+418h+var_328]
0x140318db0  movzx   ecx, byte ptr [rax+2840h]
0x140318db7  test    cl, cl
0x140318db9  jz      short loc_140318DDC
0x140318dbb  xor     ecx, ecx; PerformanceFrequency
0x140318dbd  call    cs:__imp_KeQueryPerformanceCounter
0x140318dc4  nop     dword ptr [rax+rax+00h]
0x140318dc9  mov     [rsp+418h+var_B8], rax
0x140318dd1  mov     [rsp+418h+var_AC], 18h
0x140318ddc  lea     rax, [rsp+418h+var_48]
0x140318de4  mov     [rsp+418h+var_338], rax
0x140318dec  mov     eax, 4
0x140318df1  mov     [rsp+418h+var_33E], ax
0x140318df9  lea     rax, [rsp+418h+Event]
0x140318dfe  mov     [rsp+418h+Object], rax
0x140318e06  xor     r8d, r8d; State
0x140318e09  xor     edx, edx; Type
0x140318e0b  lea     rcx, [rsp+418h+Event]; Event
0x140318e10  call    cs:__imp_KeInitializeEvent
0x140318e17  nop     dword ptr [rax+rax+00h]
0x140318e1c  call    cs:__imp_KeEnterCriticalRegion
0x140318e23  nop     dword ptr [rax+rax+00h]
0x140318e28  lea     r8, [rsp+418h+var_3C0]
0x140318e2d  lea     rdx, [rsp+418h+var_378]
0x140318e35  mov     rcx, rsi
0x140318e38  call    cs:__imp_IoPropagateActivityIdToThread
0x140318e3f  nop     dword ptr [rax+rax+00h]
0x140318e44  mov     [rsp+418h+var_3DC], eax
0x140318e48  cmp     edi, 0C0000188h
0x140318e4e  jz      short loc_140318EB4
0x140318e50  cmp     edi, 367h
0x140318e56  jz      loc_140318EEF
0x140318e5c  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140318e64  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140318e69  mov     [rsp+418h+HighLimit], r14
0x140318e6e  mov     [rsp+418h+LowLimit], r14
0x140318e73  lea     rdx, [rsp+418h+HighLimit]; HighLimit
0x140318e78  lea     rcx, [rsp+418h+LowLimit]; LowLimit
0x140318e7d  call    cs:__imp_IoGetStackLimits
0x140318e84  nop     dword ptr [rax+rax+00h]
0x140318e89  lea     rax, [rsp+418h+HighLimit]
0x140318e8e  sub     rax, [rsp+418h+LowLimit]
0x140318e93  mov     rdx, rsi; Irp
0x140318e96  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140318e9e  cmp     rax, 4800h
0x140318ea4  jbe     short loc_140318EAD
0x140318ea6  call    ?RefsCommonCleanup@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonCleanup(_IRP_CONTEXT *,_IRP *)
0x140318eab  jmp     short loc_140318F29
0x140318ead  call    ?RefsCommonCleanupOnNewStack@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonCleanupOnNewStack(_IRP_CONTEXT *,_IRP *)
0x140318eb2  jmp     short loc_140318F29
0x140318eb4  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140318ebc  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140318ec1  jmp     short loc_140318ED0
0x140318ec3  xor     r14d, r14d
0x140318ec6  mov     r15d, [rsp+418h+var_3E4]
0x140318ecb  mov     rsi, [rsp+418h+var_3C8]
0x140318ed0  inc     r15d
0x140318ed3  mov     [rsp+418h+var_3E4], r15d
0x140318ed8  cmp     r15d, 2
0x140318edc  jb      loc_140318E5C
0x140318ee2  or      [rsp+418h+var_364], 10h
0x140318eea  jmp     loc_140318E5C
0x140318eef  mov     rax, [rsp+418h+var_3B8]
0x140318ef4  mov     rcx, [rax+0B8h]
0x140318efb  and     byte ptr [rcx+3], 0FEh
0x140318eff  mov     [rsp+418h+Timeout], r14; Timeout
0x140318f04  xor     r9d, r9d; Alertable
0x140318f07  xor     r8d, r8d; WaitMode
0x140318f0a  xor     edx, edx; WaitReason
0x140318f0c  mov     rcx, [rsp+418h+Object]; Object
0x140318f14  call    cs:__imp_KeWaitForSingleObject
0x140318f1b  nop     dword ptr [rax+rax+00h]
0x140318f20  mov     [rsp+418h+var_3E8], eax
0x140318f24  jmp     loc_140318E5C
0x140318f29  mov     [rsp+418h+var_3E8], eax
0x140318f2d  mov     edi, eax
0x140318f2f  jmp     short loc_140318F57
0x140318f31  mov     r8d, eax; int
0x140318f34  mov     rsi, [rsp+418h+var_3C8]
0x140318f39  mov     rdx, rsi; struct _IRP *
0x140318f3c  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140318f44  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140318f49  mov     edi, eax
0x140318f4b  mov     [rsp+418h+var_3E8], eax
0x140318f4f  xor     r14d, r14d
0x140318f52  mov     r15d, [rsp+418h+var_3E4]
0x140318f57  cmp     edi, 0C00000D8h
0x140318f5d  jz      loc_140318E48
0x140318f63  cmp     edi, 0C00001A8h
0x140318f69  jz      loc_140318E48
0x140318f6f  cmp     edi, 0C0000188h
0x140318f75  jz      loc_140318E48
0x140318f7b  cmp     edi, 367h
0x140318f81  jz      loc_140318E48
0x140318f87  cmp     [rsp+418h+var_3DC], 0
0x140318f8c  jge     short loc_140318FF6
0x140318f8e  call    cs:__imp_KeLeaveCriticalRegion
0x140318f95  nop     dword ptr [rax+rax+00h]
0x140318f9a  mov     eax, edi
0x140318f9c  mov     rcx, [rsp+418h+var_28]
0x140318fa4  xor     rcx, rsp; StackCookie
0x140318fa7  call    __security_check_cookie
0x140318fac  lea     r11, [rsp+418h+var_18]
0x140318fb4  mov     rbx, [r11+20h]
0x140318fb8  mov     rsi, [r11+30h]
0x140318fbc  mov     rsp, r11
0x140318fbf  pop     r15
0x140318fc1  pop     r14
0x140318fc3  pop     rdi
0x140318fc4  retn
0x140318fc6  mov     [rdx+30h], r14d
0x140318fca  mov     qword ptr [rdx+38h], 1
0x140318fd2  mov     dl, 1; PriorityBoost
0x140318fd4  mov     rcx, rsi; Irp
0x140318fd7  call    cs:__imp_IofCompleteRequest
0x140318fde  nop     dword ptr [rax+rax+00h]
0x140318fe3  xor     eax, eax
0x140318fe5  jmp     short loc_140318F9C
0x140318fe7  mov     r8d, edi; Status
0x140318fea  mov     rdx, rsi; Irp
0x140318fed  xor     ecx, ecx; struct _IRP_CONTEXT *
0x140318fef  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140318ff4  jmp     short loc_140318F9A
0x140318ff6  mov     rcx, [rsp+418h+var_3C0]
0x140318ffb  call    cs:__imp_IoClearActivityIdThread
0x140319002  nop     dword ptr [rax+rax+00h]
0x140319007  jmp     short loc_140318F8E
0x140343270  push    rbp
0x140343272  sub     rsp, 30h
0x140343276  mov     rbp, rdx
0x140343279  mov     r8, rcx
0x14034327c  lea     rcx, [rbp+0B0h]
0x140343283  call    RefsFsdCleanupLffExceptionFilter
0x140343288  nop
0x140343289  add     rsp, 30h
0x14034328d  pop     rbp
0x14034328e  retn
0x140343290  push    rbp
0x140343292  sub     rsp, 30h
0x140343296  mov     rbp, rdx
0x140343299  mov     [rbp+68h], rcx
0x14034329d  mov     rdx, [rbp+68h]; struct _EXCEPTION_POINTERS *
0x1403432a1  lea     rcx, [rbp+0B0h]; struct _IRP_CONTEXT *
0x1403432a8  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x1403432ad  mov     [rbp+38h], eax
0x1403432b0  mov     eax, [rbp+38h]
0x1403432b3  add     rsp, 30h
0x1403432b7  pop     rbp
0x1403432b8  retn
```
