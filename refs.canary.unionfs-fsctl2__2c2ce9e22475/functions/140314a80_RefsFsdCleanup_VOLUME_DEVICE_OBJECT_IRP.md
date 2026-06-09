# RefsFsdCleanup(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x140314a80`
- end: `0x140314dd9`
- name: `?RefsFsdCleanup@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `857`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140039b20`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x14007dd30`
- `0x1400a648c`
- `0x1400c8660`
- `0x1401e9ce0`
- `0x140290c34`
- `0x140314a80`
- `0x140314de0`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140314da7`
- `ntoskrnl!IofCompleteRequest` at `0x140314da7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140314b60`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140314b60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140314bec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140314bec`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140314c08`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140314c08`
- `ntoskrnl!IoGetStackLimits` at `0x140314c4d`
- `ntoskrnl!IoGetStackLimits` at `0x140314c4d`
- `ntoskrnl!IoClearActivityIdThread` at `0x140314dcb`
- `ntoskrnl!IoClearActivityIdThread` at `0x140314dcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140314d5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140314d5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140314ce4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140314ce4`
- `ntoskrnl!KeInitializeEvent` at `0x140314be0`
- `ntoskrnl!KeInitializeEvent` at `0x140314be0`
- `HAL!KeQueryPerformanceCounter` at `0x140314b8d`
- `HAL!KeQueryPerformanceCounter` at `0x140314b8d`

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
      if ( *(_BYTE *)(v24 + 10496) )
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
0x140314a80  mov     r11, rsp
0x140314a83  mov     [r11+8], rbx
0x140314a87  mov     [r11+18h], rsi
0x140314a8b  push    rdi
0x140314a8c  push    r14
0x140314a8e  push    r15
0x140314a90  sub     rsp, 400h
0x140314a97  mov     rax, cs:__security_cookie
0x140314a9e  xor     rax, rsp
0x140314aa1  mov     [rsp+418h+var_28], rax
0x140314aa9  mov     rsi, rdx
0x140314aac  mov     [rsp+418h+var_3C8], rdx
0x140314ab1  mov     [rsp+418h+var_3B8], rdx
0x140314ab6  xorps   xmm0, xmm0
0x140314ab9  xor     eax, eax
0x140314abb  movups  [rsp+418h+var_390], xmm0
0x140314ac3  mov     [r11-380h], rax
0x140314aca  xorps   xmm1, xmm1
0x140314acd  movups  xmmword ptr [r11-48h], xmm1
0x140314ad2  movups  xmmword ptr [r11-38h], xmm1
0x140314ad7  movups  xmmword ptr [rsp+418h+Event.Header], xmm0
0x140314adc  mov     [r11-398h], rax
0x140314ae3  movups  [rsp+418h+var_378], xmm0
0x140314aeb  xor     r14d, r14d
0x140314aee  mov     [rsp+418h+var_3C0], r14
0x140314af3  mov     eax, 150h
0x140314af8  cmp     [rcx+2], ax
0x140314afc  jz      loc_140314D96
0x140314b02  xor     r8d, r8d; unsigned __int8
0x140314b05  xor     edx, edx; unsigned __int8
0x140314b07  lea     rcx, [r11-390h]; struct _TOP_LEVEL_CONTEXT *
0x140314b0e  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x140314b13  mov     rbx, rax
0x140314b16  lea     rdx, [rsp+418h+var_368]; struct _LARGE_IRP_CONTEXT *
0x140314b1e  mov     rcx, rsi; struct _IRP *
0x140314b21  call    ?RefsInitializeLocalIrpContext@@YAJPEAU_IRP@@PEAU_LARGE_IRP_CONTEXT@@@Z; RefsInitializeLocalIrpContext(_IRP *,_LARGE_IRP_CONTEXT *)
0x140314b26  mov     edi, eax
0x140314b28  test    eax, eax
0x140314b2a  js      loc_140314DB7
0x140314b30  mov     r15d, r14d
0x140314b33  mov     [rsp+418h+var_3E4], r14d
0x140314b38  cmp     [rbx+10h], r14
0x140314b3c  jnz     short loc_140314B6C
0x140314b3e  mov     dword ptr [rbx+4], 5346ABBAh
0x140314b45  lea     rax, [rsp+418h+var_368]
0x140314b4d  mov     [rbx+10h], rax
0x140314b51  or      [rsp+418h+var_360], 100000h
0x140314b5d  mov     rcx, rbx; Irp
0x140314b60  call    cs:__imp_IoSetTopLevelIrp
0x140314b67  nop     dword ptr [rax+rax+00h]
0x140314b6c  mov     rax, [rbx+10h]
0x140314b70  mov     [rsp+418h+var_300], rax
0x140314b78  mov     rax, [rsp+418h+var_328]
0x140314b80  movzx   ecx, byte ptr [rax+2900h]
0x140314b87  test    cl, cl
0x140314b89  jz      short loc_140314BAC
0x140314b8b  xor     ecx, ecx; PerformanceFrequency
0x140314b8d  call    cs:__imp_KeQueryPerformanceCounter
0x140314b94  nop     dword ptr [rax+rax+00h]
0x140314b99  mov     [rsp+418h+var_B8], rax
0x140314ba1  mov     [rsp+418h+var_AC], 18h
0x140314bac  lea     rax, [rsp+418h+var_48]
0x140314bb4  mov     [rsp+418h+var_338], rax
0x140314bbc  mov     eax, 4
0x140314bc1  mov     [rsp+418h+var_33E], ax
0x140314bc9  lea     rax, [rsp+418h+Event]
0x140314bce  mov     [rsp+418h+Object], rax
0x140314bd6  xor     r8d, r8d; State
0x140314bd9  xor     edx, edx; Type
0x140314bdb  lea     rcx, [rsp+418h+Event]; Event
0x140314be0  call    cs:__imp_KeInitializeEvent
0x140314be7  nop     dword ptr [rax+rax+00h]
0x140314bec  call    cs:__imp_KeEnterCriticalRegion
0x140314bf3  nop     dword ptr [rax+rax+00h]
0x140314bf8  lea     r8, [rsp+418h+var_3C0]
0x140314bfd  lea     rdx, [rsp+418h+var_378]
0x140314c05  mov     rcx, rsi
0x140314c08  call    cs:__imp_IoPropagateActivityIdToThread
0x140314c0f  nop     dword ptr [rax+rax+00h]
0x140314c14  mov     [rsp+418h+var_3DC], eax
0x140314c18  cmp     edi, 0C0000188h
0x140314c1e  jz      short loc_140314C84
0x140314c20  cmp     edi, 367h
0x140314c26  jz      loc_140314CBF
0x140314c2c  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140314c34  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140314c39  mov     [rsp+418h+HighLimit], r14
0x140314c3e  mov     [rsp+418h+LowLimit], r14
0x140314c43  lea     rdx, [rsp+418h+HighLimit]; HighLimit
0x140314c48  lea     rcx, [rsp+418h+LowLimit]; LowLimit
0x140314c4d  call    cs:__imp_IoGetStackLimits
0x140314c54  nop     dword ptr [rax+rax+00h]
0x140314c59  lea     rax, [rsp+418h+HighLimit]
0x140314c5e  sub     rax, [rsp+418h+LowLimit]
0x140314c63  mov     rdx, rsi; Irp
0x140314c66  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140314c6e  cmp     rax, 4800h
0x140314c74  jbe     short loc_140314C7D
0x140314c76  call    ?RefsCommonCleanup@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonCleanup(_IRP_CONTEXT *,_IRP *)
0x140314c7b  jmp     short loc_140314CF9
0x140314c7d  call    ?RefsCommonCleanupOnNewStack@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonCleanupOnNewStack(_IRP_CONTEXT *,_IRP *)
0x140314c82  jmp     short loc_140314CF9
0x140314c84  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140314c8c  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140314c91  jmp     short loc_140314CA0
0x140314c93  xor     r14d, r14d
0x140314c96  mov     r15d, [rsp+418h+var_3E4]
0x140314c9b  mov     rsi, [rsp+418h+var_3C8]
0x140314ca0  inc     r15d
0x140314ca3  mov     [rsp+418h+var_3E4], r15d
0x140314ca8  cmp     r15d, 2
0x140314cac  jb      loc_140314C2C
0x140314cb2  or      [rsp+418h+var_364], 10h
0x140314cba  jmp     loc_140314C2C
0x140314cbf  mov     rax, [rsp+418h+var_3B8]
0x140314cc4  mov     rcx, [rax+0B8h]
0x140314ccb  and     byte ptr [rcx+3], 0FEh
0x140314ccf  mov     [rsp+418h+Timeout], r14; Timeout
0x140314cd4  xor     r9d, r9d; Alertable
0x140314cd7  xor     r8d, r8d; WaitMode
0x140314cda  xor     edx, edx; WaitReason
0x140314cdc  mov     rcx, [rsp+418h+Object]; Object
0x140314ce4  call    cs:__imp_KeWaitForSingleObject
0x140314ceb  nop     dword ptr [rax+rax+00h]
0x140314cf0  mov     [rsp+418h+var_3E8], eax
0x140314cf4  jmp     loc_140314C2C
0x140314cf9  mov     [rsp+418h+var_3E8], eax
0x140314cfd  mov     edi, eax
0x140314cff  jmp     short loc_140314D27
0x140314d01  mov     r8d, eax; int
0x140314d04  mov     rsi, [rsp+418h+var_3C8]
0x140314d09  mov     rdx, rsi; struct _IRP *
0x140314d0c  lea     rcx, [rsp+418h+var_368]; struct _IRP_CONTEXT *
0x140314d14  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140314d19  mov     edi, eax
0x140314d1b  mov     [rsp+418h+var_3E8], eax
0x140314d1f  xor     r14d, r14d
0x140314d22  mov     r15d, [rsp+418h+var_3E4]
0x140314d27  cmp     edi, 0C00000D8h
0x140314d2d  jz      loc_140314C18
0x140314d33  cmp     edi, 0C00001A8h
0x140314d39  jz      loc_140314C18
0x140314d3f  cmp     edi, 0C0000188h
0x140314d45  jz      loc_140314C18
0x140314d4b  cmp     edi, 367h
0x140314d51  jz      loc_140314C18
0x140314d57  cmp     [rsp+418h+var_3DC], 0
0x140314d5c  jge     short loc_140314DC6
0x140314d5e  call    cs:__imp_KeLeaveCriticalRegion
0x140314d65  nop     dword ptr [rax+rax+00h]
0x140314d6a  mov     eax, edi
0x140314d6c  mov     rcx, [rsp+418h+var_28]
0x140314d74  xor     rcx, rsp; StackCookie
0x140314d77  call    __security_check_cookie
0x140314d7c  lea     r11, [rsp+418h+var_18]
0x140314d84  mov     rbx, [r11+20h]
0x140314d88  mov     rsi, [r11+30h]
0x140314d8c  mov     rsp, r11
0x140314d8f  pop     r15
0x140314d91  pop     r14
0x140314d93  pop     rdi
0x140314d94  retn
0x140314d96  mov     [rdx+30h], r14d
0x140314d9a  mov     qword ptr [rdx+38h], 1
0x140314da2  mov     dl, 1; PriorityBoost
0x140314da4  mov     rcx, rsi; Irp
0x140314da7  call    cs:__imp_IofCompleteRequest
0x140314dae  nop     dword ptr [rax+rax+00h]
0x140314db3  xor     eax, eax
0x140314db5  jmp     short loc_140314D6C
0x140314db7  mov     r8d, edi; Status
0x140314dba  mov     rdx, rsi; Irp
0x140314dbd  xor     ecx, ecx; struct _IRP_CONTEXT *
0x140314dbf  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140314dc4  jmp     short loc_140314D6A
0x140314dc6  mov     rcx, [rsp+418h+var_3C0]
0x140314dcb  call    cs:__imp_IoClearActivityIdThread
0x140314dd2  nop     dword ptr [rax+rax+00h]
0x140314dd7  jmp     short loc_140314D5E
0x140340260  push    rbp
0x140340262  sub     rsp, 30h
0x140340266  mov     rbp, rdx
0x140340269  mov     r8, rcx
0x14034026c  lea     rcx, [rbp+0B0h]
0x140340273  call    RefsFsdCleanupLffExceptionFilter
0x140340278  nop
0x140340279  add     rsp, 30h
0x14034027d  pop     rbp
0x14034027e  retn
0x140340280  push    rbp
0x140340282  sub     rsp, 30h
0x140340286  mov     rbp, rdx
0x140340289  mov     [rbp+68h], rcx
0x14034028d  mov     rdx, [rbp+68h]; struct _EXCEPTION_POINTERS *
0x140340291  lea     rcx, [rbp+0B0h]; struct _IRP_CONTEXT *
0x140340298  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x14034029d  mov     [rbp+38h], eax
0x1403402a0  mov     eax, [rbp+38h]
0x1403402a3  add     rsp, 30h
0x1403402a7  pop     rbp
0x1403402a8  retn
```
