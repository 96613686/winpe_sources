# DDMServiceStopComplete(void *)

- ea: `0x18001a7b0`
- end: `0x18001a934`
- name: `?DDMServiceStopComplete@@YAXPEAX@Z`
- size: `388`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a940`
- `0x18001a968`

## callees

- `0x180007b7c`
- `0x18001a7b0`
- `0x18003a9dc`
- `0x18003b8f4`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001a916`
- `KERNEL32!SetEvent` at `0x18001a916`
- `rasman!RasSendNotification` at `0x18001a905`
- `rasman!RasSendNotification` at `0x18001a905`

## string_xrefs

- `0x18001a814`: `ServiceStopComplete: There are devices pending close`
- `0x18001a898`: `ServiceStopComplete: ALL devices closed`

## pseudocode

```c
void __fastcall DDMServiceStopComplete(void *a1)
{
  DdmDeviceTable *Instance; // rax
  __int64 v2; // r8
  void **v3; // [rsp+38h] [rbp-C8h] BYREF
  int v4; // [rsp+40h] [rbp-C0h]
  _DWORD v5[920]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+EB0h] [rbp+DB0h] BYREF
  const wchar_t *v7; // [rsp+EC0h] [rbp+DC0h]
  __int64 v8; // [rsp+EC8h] [rbp+DC8h]

  v4 = 0;
  v3 = &DeviceIsClosed::`vftable';
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&v3, 1, 0);
  if ( v4 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v8 = 106;
      v7 = L"ServiceStopComplete: There are devices pending close";
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v2,
        2u,
        &v6);
    }
    (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800C8670 + 16LL))(
      qword_1800C8670,
      DDMServiceStopCompleteCallBack,
      0,
      0);
  }
  else if ( (unsigned int)_InterlockedIncrement(&dword_1800C8680) <= 1 )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v8 = 80;
      v7 = L"ServiceStopComplete: ALL devices closed";
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v2,
        2u,
        &v6);
    }
    memset_0(v5, 0, sizeof(v5));
    v5[0] = 0x20000;
    v5[2] = 1;
    v5[3] = 2;
    RasSendNotification(v5);
    SetEvent(gblSupervisorEvents[1]);
  }
}

```

## disassembly

```asm
0x18001a7b0  push    rbp
0x18001a7b2  lea     rbp, [rsp-0DE0h]
0x18001a7ba  sub     rsp, 0EE0h
0x18001a7c1  mov     rax, cs:__security_cookie
0x18001a7c8  xor     rax, rsp
0x18001a7cb  mov     [rbp+0DE0h+var_10], rax
0x18001a7d2  lea     rax, ??_7DeviceIsClosed@@6B@; const DeviceIsClosed::`vftable'
0x18001a7d9  mov     [rsp+0EE0h+var_EA0], 0
0x18001a7e1  mov     ecx, 11h; unsigned int
0x18001a7e6  mov     [rsp+0EE0h+var_EA8], rax
0x18001a7eb  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001a7f0  xor     r9d, r9d; void *
0x18001a7f3  lea     rdx, [rsp+0EE0h+var_EA8]; struct DdmDeviceVisitor *
0x18001a7f8  mov     rcx, rax; this
0x18001a7fb  lea     r8d, [r9+1]; int
0x18001a7ff  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x18001a804  cmp     [rsp+0EE0h+var_EA0], 0
0x18001a809  jz      short loc_18001A877
0x18001a80b  test    cs:byte_1800C8404, 10h
0x18001a812  jz      short loc_18001A852
0x18001a814  lea     rax, aServicestopcom_0; "ServiceStopComplete: There are devices "...
0x18001a81b  mov     [rbp+0DE0h+var_18], 6Ah ; 'j'
0x18001a826  mov     [rbp+0DE0h+var_20], rax
0x18001a82d  lea     rdx, RasDdmTraceInfo
0x18001a834  lea     rax, [rbp+0DE0h+var_30]
0x18001a83b  mov     r9d, 2
0x18001a841  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001a848  mov     [rsp+0EE0h+var_EC0], rax
0x18001a84d  call    McGenEventWrite_EventWriteTransfer
0x18001a852  mov     rcx, cs:qword_1800C8670
0x18001a859  lea     rdx, ?DDMServiceStopCompleteCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DDMServiceStopCompleteCallBack(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18001a860  xor     r9d, r9d
0x18001a863  xor     r8d, r8d
0x18001a866  mov     rax, [rcx]
0x18001a869  mov     rax, [rax+10h]
0x18001a86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a872  jmp     loc_18001A91C
0x18001a877  mov     eax, 1
0x18001a87c  lock xadd cs:dword_1800C8680, eax
0x18001a884  inc     eax
0x18001a886  cmp     eax, 1
0x18001a889  ja      loc_18001A91C
0x18001a88f  test    cs:byte_1800C8404, 10h
0x18001a896  jz      short loc_18001A8D6
0x18001a898  lea     rax, aServicestopcom; "ServiceStopComplete: ALL devices closed"
0x18001a89f  mov     [rbp+0DE0h+var_18], 50h ; 'P'
0x18001a8aa  mov     [rbp+0DE0h+var_20], rax
0x18001a8b1  lea     rdx, RasDdmTraceInfo
0x18001a8b8  lea     rax, [rbp+0DE0h+var_30]
0x18001a8bf  mov     r9d, 2
0x18001a8c5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001a8cc  mov     [rsp+0EE0h+var_EC0], rax
0x18001a8d1  call    McGenEventWrite_EventWriteTransfer
0x18001a8d6  xor     edx, edx; Val
0x18001a8d8  lea     rcx, [rsp+0EE0h+var_E90]; void *
0x18001a8dd  mov     r8d, 0E60h; Size
0x18001a8e3  call    memset_0
0x18001a8e8  lea     rcx, [rsp+0EE0h+var_E90]
0x18001a8ed  mov     [rsp+0EE0h+var_E90], 20000h
0x18001a8f5  mov     [rsp+0EE0h+var_E88], 1
0x18001a8fd  mov     [rsp+0EE0h+var_E84], 2
0x18001a905  call    cs:__imp_RasSendNotification
0x18001a90b  mov     rcx, cs:gblSupervisorEvents
0x18001a912  mov     rcx, [rcx+8]; hEvent
0x18001a916  call    cs:__imp_SetEvent
0x18001a91c  mov     rcx, [rbp+0DE0h+var_10]
0x18001a923  xor     rcx, rsp; StackCookie
0x18001a926  call    __security_check_cookie
0x18001a92b  add     rsp, 0EE0h
0x18001a932  pop     rbp
0x18001a933  retn
```
