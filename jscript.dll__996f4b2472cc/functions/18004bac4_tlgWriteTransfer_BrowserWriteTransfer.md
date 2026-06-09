# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x18004bac4`
- end: `0x18004bbc9`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `261`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001008`
- `0x1800010c0`
- `0x180001240`

## callees

- `0x18004bac4`
- `0x18004bbd0`

## import_xrefs

- `ADVAPI32!EventWriteEx` at `0x18004bbb1`
- `ADVAPI32!EventWriteEx` at `0x18004bbb1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bb6a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bb6a`

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
0x18004bac4  push    rbx
0x18004bac6  push    rbp
0x18004bac7  push    rsi
0x18004bac8  push    rdi
0x18004bac9  push    r14
0x18004bacb  sub     rsp, 50h
0x18004bacf  movzx   eax, byte ptr [rdx]
0x18004bad2  mov     rsi, rcx
0x18004bad5  mov     rdi, [rsp+78h+arg_28]
0x18004badd  xor     ebx, ebx
0x18004badf  shl     eax, 18h
0x18004bae2  mov     rbp, r9
0x18004bae5  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x18004bae9  mov     r14, r8
0x18004baec  movzx   eax, word ptr [rdx+1]
0x18004baf0  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x18004baf4  mov     rax, [rdx+3]
0x18004baf8  add     rdx, 0Bh
0x18004bafc  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x18004bb01  mov     rax, [rcx+8]
0x18004bb05  mov     [rdi], rax
0x18004bb08  mov     rax, [rcx+8]
0x18004bb0c  movzx   ecx, word ptr [rax]
0x18004bb0f  mov     [rdi+8], ecx
0x18004bb12  lea     rcx, _TraceLoggingMetadata
0x18004bb19  mov     [rdi+10h], rdx
0x18004bb1d  mov     dword ptr [rdi+0Ch], 2
0x18004bb24  movzx   eax, word ptr [rdx]
0x18004bb27  mov     [rdi+18h], eax
0x18004bb2a  lea     rax, _TraceLoggingMetadataEnd
0x18004bb31  sub     eax, ecx
0x18004bb33  mov     dword ptr [rdi+1Ch], 1
0x18004bb3a  mov     ecx, cs:_tls_index
0x18004bb40  mov     dword ptr [rsp+78h+arg_28], eax
0x18004bb47  mov     eax, dword ptr [rsp+78h+arg_28]
0x18004bb4e  mov     rax, gs:58h
0x18004bb57  mov     edx, 8
0x18004bb5c  mov     rax, [rax+rcx*8]
0x18004bb60  cmp     [rdx+rax], bl
0x18004bb63  jnz     short loc_18004BB88
0x18004bb65  mov     ecx, 20000019h
0x18004bb6a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004bb71  nop     dword ptr [rax+rax+00h]
0x18004bb76  test    al, al
0x18004bb78  jz      short loc_18004BB83
0x18004bb7a  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x18004bb7f  test    al, al
0x18004bb81  jz      short loc_18004BB88
0x18004bb83  mov     ebx, 2
0x18004bb88  mov     eax, [rsp+78h+arg_20]
0x18004bb8f  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x18004bb94  mov     rcx, [rsi+20h]; RegHandle
0x18004bb98  mov     r9d, ebx; Flags
0x18004bb9b  mov     [rsp+78h+UserData], rdi; UserData
0x18004bba0  xor     r8d, r8d; Filter
0x18004bba3  mov     [rsp+78h+UserDataCount], eax; UserDataCount
0x18004bba7  mov     [rsp+78h+RelatedActivityId], rbp; RelatedActivityId
0x18004bbac  mov     [rsp+78h+ActivityId], r14; ActivityId
0x18004bbb1  call    cs:__imp_EventWriteEx
0x18004bbb8  nop     dword ptr [rax+rax+00h]
0x18004bbbd  add     rsp, 50h
0x18004bbc1  pop     r14
0x18004bbc3  pop     rdi
0x18004bbc4  pop     rsi
0x18004bbc5  pop     rbp
0x18004bbc6  pop     rbx
0x18004bbc7  retn
```
