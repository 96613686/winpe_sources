# DDMServiceStopComplete(void *)

- ea: `0x18001b0c0`
- end: `0x18001b286`
- name: `?DDMServiceStopComplete@@YAXPEAX@Z`
- size: `454`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b290`
- `0x18001b2c0`

## callees

- `0x180007c0c`
- `0x18001b0c0`
- `0x18003c2c8`
- `0x18003d278`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001b259`
- `KERNEL32!SetEvent` at `0x18001b259`
- `rasman!RasSendNotification` at `0x18001b242`
- `rasman!RasSendNotification` at `0x18001b242`

## string_xrefs

- `0x18001b127`: `ServiceStopComplete: There are devices pending close`
- `0x18001b1c0`: `ServiceStopComplete: ALL devices closed`

## pseudocode

```c
void __fastcall DDMServiceStopComplete(void *a1)
{
  DdmDeviceTable *Instance; // rax
  __int64 v2; // r8
  __int64 v3; // rax
  __int64 v4; // rax
  void **v5; // [rsp+30h] [rbp-D0h] BYREF
  int v6; // [rsp+38h] [rbp-C8h]
  _DWORD v7[920]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+EA0h] [rbp+DA0h] BYREF
  const wchar_t *v9; // [rsp+EB0h] [rbp+DB0h]
  int v10; // [rsp+EB8h] [rbp+DB8h]
  int v11; // [rsp+EBCh] [rbp+DBCh]

  v5 = &DeviceIsClosed::`vftable';
  v6 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&v5, 1, 0);
  if ( v6 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( aServicestopcom_0[v3] );
      v9 = L"ServiceStopComplete: There are devices pending close";
      v10 = 2 * v3 + 2;
      v11 = 0;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v2,
        2u,
        &v8);
    }
    (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800CF670 + 16LL))(
      qword_1800CF670,
      DDMServiceStopCompleteCallBack,
      0,
      0);
  }
  else if ( (unsigned int)_InterlockedIncrement(&dword_1800CF680) <= 1 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( aServicestopcom[v4] );
      v9 = L"ServiceStopComplete: ALL devices closed";
      v10 = 2 * v4 + 2;
      v11 = 0;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v2,
        2u,
        &v8);
    }
    memset_0(v7, 0, sizeof(v7));
    v7[0] = 0x20000;
    v7[2] = 1;
    v7[3] = 2;
    RasSendNotification(v7);
    SetEvent(gblSupervisorEvents[1]);
  }
}

```

## disassembly

```asm
0x18001b0c0  mov     [rsp-8+arg_0], rdi
0x18001b0c5  push    rbp
0x18001b0c6  lea     rbp, [rsp-0DD0h]
0x18001b0ce  sub     rsp, 0ED0h
0x18001b0d5  mov     rax, cs:__security_cookie
0x18001b0dc  xor     rax, rsp
0x18001b0df  mov     [rbp+0DD0h+var_10], rax
0x18001b0e6  xor     edi, edi
0x18001b0e8  lea     rax, ??_7DeviceIsClosed@@6B@; const DeviceIsClosed::`vftable'
0x18001b0ef  mov     [rsp+0ED0h+var_EA0], rax
0x18001b0f4  mov     [rsp+0ED0h+var_E98], edi
0x18001b0f8  lea     ecx, [rdi+11h]; unsigned int
0x18001b0fb  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001b100  xor     r9d, r9d; void *
0x18001b103  lea     r8d, [rdi+1]; int
0x18001b107  lea     rdx, [rsp+0ED0h+var_EA0]; struct DdmDeviceVisitor *
0x18001b10c  mov     rcx, rax; this
0x18001b10f  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x18001b114  cmp     [rsp+0ED0h+var_E98], edi
0x18001b118  jz      loc_18001B19F
0x18001b11e  test    cs:byte_1800CF404, 10h
0x18001b125  jz      short loc_18001B17A
0x18001b127  lea     rcx, aServicestopcom_0; "ServiceStopComplete: There are devices "...
0x18001b12e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b132  inc     rax
0x18001b135  cmp     [rcx+rax*2], di
0x18001b139  jnz     short loc_18001B132
0x18001b13b  lea     eax, ds:2[rax*2]
0x18001b142  mov     [rbp+0DD0h+var_20], rcx
0x18001b149  mov     [rbp+0DD0h+var_18], eax
0x18001b14f  lea     rdx, RasDdmTraceInfo
0x18001b156  lea     rax, [rbp+0DD0h+var_30]
0x18001b15d  mov     [rbp+0DD0h+var_14], edi
0x18001b163  mov     r9d, 2
0x18001b169  mov     [rsp+0ED0h+var_EB0], rax
0x18001b16e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b175  call    McGenEventWrite_EventWriteTransfer
0x18001b17a  mov     rcx, cs:qword_1800CF670
0x18001b181  lea     rdx, ?DDMServiceStopCompleteCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DDMServiceStopCompleteCallBack(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18001b188  xor     r9d, r9d
0x18001b18b  xor     r8d, r8d
0x18001b18e  mov     rax, [rcx]
0x18001b191  mov     rax, [rax+10h]
0x18001b195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b19a  jmp     loc_18001B265
0x18001b19f  mov     eax, 1
0x18001b1a4  lock xadd cs:dword_1800CF680, eax
0x18001b1ac  inc     eax
0x18001b1ae  cmp     eax, 1
0x18001b1b1  ja      loc_18001B265
0x18001b1b7  test    cs:byte_1800CF404, 10h
0x18001b1be  jz      short loc_18001B213
0x18001b1c0  lea     rcx, aServicestopcom; "ServiceStopComplete: ALL devices closed"
0x18001b1c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b1cb  inc     rax
0x18001b1ce  cmp     [rcx+rax*2], di
0x18001b1d2  jnz     short loc_18001B1CB
0x18001b1d4  lea     eax, ds:2[rax*2]
0x18001b1db  mov     [rbp+0DD0h+var_20], rcx
0x18001b1e2  mov     [rbp+0DD0h+var_18], eax
0x18001b1e8  lea     rdx, RasDdmTraceInfo
0x18001b1ef  lea     rax, [rbp+0DD0h+var_30]
0x18001b1f6  mov     [rbp+0DD0h+var_14], edi
0x18001b1fc  mov     r9d, 2
0x18001b202  mov     [rsp+0ED0h+var_EB0], rax
0x18001b207  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b20e  call    McGenEventWrite_EventWriteTransfer
0x18001b213  xor     edx, edx; Val
0x18001b215  lea     rcx, [rsp+0ED0h+var_E90]; void *
0x18001b21a  mov     r8d, 0E60h; Size
0x18001b220  call    memset_0
0x18001b225  lea     rcx, [rsp+0ED0h+var_E90]
0x18001b22a  mov     [rsp+0ED0h+var_E90], 20000h
0x18001b232  mov     [rsp+0ED0h+var_E88], 1
0x18001b23a  mov     [rsp+0ED0h+var_E84], 2
0x18001b242  call    cs:__imp_RasSendNotification
0x18001b249  nop     dword ptr [rax+rax+00h]
0x18001b24e  mov     rcx, cs:gblSupervisorEvents
0x18001b255  mov     rcx, [rcx+8]; hEvent
0x18001b259  call    cs:__imp_SetEvent
0x18001b260  nop     dword ptr [rax+rax+00h]
0x18001b265  mov     rcx, [rbp+0DD0h+var_10]
0x18001b26c  xor     rcx, rsp; StackCookie
0x18001b26f  call    __security_check_cookie
0x18001b274  mov     rdi, [rsp+0ED0h+arg_0]
0x18001b27c  add     rsp, 0ED0h
0x18001b283  pop     rbp
0x18001b284  retn
```
