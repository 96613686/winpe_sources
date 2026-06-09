# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x18004adb0`
- end: `0x18004aea8`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `248`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001008`
- `0x1800010c0`
- `0x180001240`

## callees

- `0x18004adb0`
- `0x18004aeb0`

## import_xrefs

- `ADVAPI32!EventWriteEx` at `0x18004ae97`
- `ADVAPI32!EventWriteEx` at `0x18004ae97`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004ae56`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004ae56`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_BrowserWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONG v7; // ebx
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-38h] BYREF

  v7 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v11;
  UserData->Reserved = 2;
  UserData[1].Size = *v11;
  UserData[1].Reserved = 1;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL)
    && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
  {
    v7 = 2;
  }
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v7, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18004adb0  push    rbx
0x18004adb2  push    rbp
0x18004adb3  push    rsi
0x18004adb4  push    rdi
0x18004adb5  push    r14
0x18004adb7  sub     rsp, 50h
0x18004adbb  movzx   eax, byte ptr [rdx]
0x18004adbe  mov     rsi, rcx
0x18004adc1  mov     rdi, [rsp+78h+arg_28]
0x18004adc9  xor     ebx, ebx
0x18004adcb  shl     eax, 18h
0x18004adce  mov     rbp, r9
0x18004add1  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x18004add5  mov     r14, r8
0x18004add8  movzx   eax, word ptr [rdx+1]
0x18004addc  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x18004ade0  mov     rax, [rdx+3]
0x18004ade4  add     rdx, 0Bh
0x18004ade8  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x18004aded  mov     rax, [rcx+8]
0x18004adf1  mov     [rdi], rax
0x18004adf4  mov     rax, [rcx+8]
0x18004adf8  movzx   ecx, word ptr [rax]
0x18004adfb  mov     [rdi+8], ecx
0x18004adfe  lea     rcx, _TraceLoggingMetadata
0x18004ae05  mov     [rdi+10h], rdx
0x18004ae09  mov     dword ptr [rdi+0Ch], 2
0x18004ae10  movzx   eax, word ptr [rdx]
0x18004ae13  mov     [rdi+18h], eax
0x18004ae16  lea     rax, _TraceLoggingMetadataEnd
0x18004ae1d  sub     eax, ecx
0x18004ae1f  mov     dword ptr [rdi+1Ch], 1
0x18004ae26  mov     ecx, cs:_tls_index
0x18004ae2c  mov     dword ptr [rsp+78h+arg_28], eax
0x18004ae33  mov     eax, dword ptr [rsp+78h+arg_28]
0x18004ae3a  mov     rax, gs:58h
0x18004ae43  mov     edx, 8
0x18004ae48  mov     rax, [rax+rcx*8]
0x18004ae4c  cmp     [rdx+rax], bl
0x18004ae4f  jnz     short loc_18004AE6E
0x18004ae51  mov     ecx, 20000019h
0x18004ae56  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004ae5c  test    al, al
0x18004ae5e  jz      short loc_18004AE69
0x18004ae60  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x18004ae65  test    al, al
0x18004ae67  jz      short loc_18004AE6E
0x18004ae69  mov     ebx, 2
0x18004ae6e  mov     eax, [rsp+78h+arg_20]
0x18004ae75  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x18004ae7a  mov     rcx, [rsi+20h]; RegHandle
0x18004ae7e  mov     r9d, ebx; Flags
0x18004ae81  mov     [rsp+78h+UserData], rdi; UserData
0x18004ae86  xor     r8d, r8d; Filter
0x18004ae89  mov     [rsp+78h+UserDataCount], eax; UserDataCount
0x18004ae8d  mov     [rsp+78h+RelatedActivityId], rbp; RelatedActivityId
0x18004ae92  mov     [rsp+78h+ActivityId], r14; ActivityId
0x18004ae97  call    cs:__imp_EventWriteEx
0x18004ae9d  add     rsp, 50h
0x18004aea1  pop     r14
0x18004aea3  pop     rdi
0x18004aea4  pop     rsi
0x18004aea5  pop     rbp
0x18004aea6  pop     rbx
0x18004aea7  retn
```
