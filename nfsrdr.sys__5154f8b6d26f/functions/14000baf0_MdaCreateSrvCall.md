# MdaCreateSrvCall

- ea: `0x14000baf0`
- end: `0x14000bc72`
- name: `MdaCreateSrvCall`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000baf0`
- `0x1400159cc`
- `0x1400159fc`
- `0x14003abe0`

## import_xrefs

- `ntoskrnl!ZwQueryLicenseValue` at `0x14000bb8b`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14000bb8b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bb5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bb5a`
- `rdbss!RxLogEventDirect` at `0x14000bbeb`
- `rdbss!RxLogEventDirect` at `0x14000bbeb`
- `rdbss!RxDispatchToWorkerThread` at `0x14000bbb8`
- `rdbss!RxDispatchToWorkerThread` at `0x14000bbb8`

## pseudocode

```c
__int64 __fastcall MdaCreateSrvCall(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  void (__fastcall *v5)(__int64); // rax
  int v7; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF
  int v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF

  DestinationString = 0;
  v7 = 0;
  v10 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"nfs-clientcore-enabled");
  if ( (int)ZwQueryLicenseValue(&DestinationString, &v7, &v9, 4, &v10) >= 0 && v9 )
  {
    v4 = RxDispatchToWorkerThread(
           *(PRDBSS_DEVICE_OBJECT *)(a1 + 48),
           DelayedWorkQueue,
           MdaCommonCreateSrvCall,
           (PVOID)a2);
    if ( !v4 )
      return 259;
  }
  else
  {
    v4 = -1073741206;
    RxLogEventDirect(*(PRDBSS_DEVICE_OBJECT *)(a1 + 48), 0, 0xC0004001, -1073741206, 0x16Bu);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  }
  v5 = *(void (__fastcall **)(__int64))(a2 + 272);
  *(_DWORD *)(a2 + 280) = v4;
  v5(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x14000baf0  push    rbp
0x14000baf2  push    rsi
0x14000baf3  push    rdi
0x14000baf4  sub     rsp, 50h
0x14000baf8  xor     eax, eax
0x14000bafa  xorps   xmm0, xmm0
0x14000bafd  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14000bb02  mov     [rsp+68h+var_38], eax
0x14000bb06  mov     rdi, rdx
0x14000bb09  mov     [rsp+68h+arg_18], eax
0x14000bb10  mov     rsi, rcx
0x14000bb13  mov     [rsp+68h+arg_10], eax
0x14000bb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb21  lea     rbp, WPP_GLOBAL_Control
0x14000bb28  cmp     rcx, rbp
0x14000bb2b  jz      short loc_14000BB49
0x14000bb2d  mov     eax, [rcx+2Ch]
0x14000bb30  test    al, 8
0x14000bb32  jz      short loc_14000BB49
0x14000bb34  mov     rcx, [rcx+18h]
0x14000bb38  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000bb3f  mov     edx, 0Ch
0x14000bb44  call    WPP_SF_
0x14000bb49  lea     rdx, SourceString; "nfs-clientcore-enabled"
0x14000bb50  mov     [rsp+68h+arg_0], rbx
0x14000bb55  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000bb5a  call    cs:__imp_RtlInitUnicodeString
0x14000bb61  nop     dword ptr [rax+rax+00h]
0x14000bb66  lea     rax, [rsp+68h+arg_18]
0x14000bb6e  mov     r9d, 4
0x14000bb74  lea     r8, [rsp+68h+arg_10]
0x14000bb7c  mov     qword ptr [rsp+68h+Line], rax
0x14000bb81  lea     rdx, [rsp+68h+var_38]
0x14000bb86  lea     rcx, [rsp+68h+DestinationString]
0x14000bb8b  call    cs:__imp_ZwQueryLicenseValue
0x14000bb92  nop     dword ptr [rax+rax+00h]
0x14000bb97  test    eax, eax
0x14000bb99  js      short loc_14000BBCF
0x14000bb9b  cmp     [rsp+68h+arg_10], 0
0x14000bba3  jz      short loc_14000BBCF
0x14000bba5  mov     rcx, [rsi+30h]; pMRxDeviceObject
0x14000bba9  lea     r8, MdaCommonCreateSrvCall; Routine
0x14000bbb0  mov     r9, rdi; pContext
0x14000bbb3  mov     edx, 1; WorkQueueType
0x14000bbb8  call    cs:__imp_RxDispatchToWorkerThread
0x14000bbbf  nop     dword ptr [rax+rax+00h]
0x14000bbc4  mov     ebx, eax
0x14000bbc6  test    eax, eax
0x14000bbc8  jnz     short loc_14000BC1F
0x14000bbca  jmp     loc_14000BC5F
0x14000bbcf  mov     rcx, [rsi+30h]; DeviceObject
0x14000bbd3  mov     ebx, 0C000026Ah
0x14000bbd8  mov     r9d, ebx; Status
0x14000bbdb  mov     [rsp+68h+Line], 16Bh; Line
0x14000bbe3  xor     edx, edx; OriginatorId
0x14000bbe5  mov     r8d, 0C0004001h; EventId
0x14000bbeb  call    cs:__imp_RxLogEventDirect
0x14000bbf2  nop     dword ptr [rax+rax+00h]
0x14000bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbfe  cmp     rcx, rbp
0x14000bc01  jz      short loc_14000BC1F
0x14000bc03  mov     eax, [rcx+2Ch]
0x14000bc06  test    al, 1
0x14000bc08  jz      short loc_14000BC1F
0x14000bc0a  mov     rcx, [rcx+18h]
0x14000bc0e  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000bc15  mov     edx, 0Dh
0x14000bc1a  call    WPP_SF_
0x14000bc1f  mov     rax, [rdi+110h]
0x14000bc26  mov     rcx, rdi
0x14000bc29  mov     [rdi+118h], ebx
0x14000bc2f  call    _guard_dispatch_icall
0x14000bc34  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc3b  cmp     rcx, rbp
0x14000bc3e  jz      short loc_14000BC5F
0x14000bc40  mov     eax, [rcx+2Ch]
0x14000bc43  test    al, 8
0x14000bc45  jz      short loc_14000BC5F
0x14000bc47  mov     rcx, [rcx+18h]
0x14000bc4b  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000bc52  mov     edx, 0Eh
0x14000bc57  mov     r9d, ebx
0x14000bc5a  call    WPP_SF_d
0x14000bc5f  mov     rbx, [rsp+68h+arg_0]
0x14000bc64  mov     eax, 103h
0x14000bc69  add     rsp, 50h
0x14000bc6d  pop     rdi
0x14000bc6e  pop     rsi
0x14000bc6f  pop     rbp
0x14000bc70  retn
```
