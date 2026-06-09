# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x140001310`
- end: `0x140001401`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `241`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001008`
- `0x1400010d4`
- `0x14000244c`
- `0x140003fec`

## callees

- `0x140001310`
- `0x1400057f8`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteEx` at `0x1400013f0`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteEx` at `0x1400013f0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1400013af`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1400013af`

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
  if ( !*(_BYTE *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 1LL)
    && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
  {
    v7 = 2;
  }
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v7, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001310  push    rbx
0x140001312  push    rbp
0x140001313  push    rsi
0x140001314  push    rdi
0x140001315  push    r14
0x140001317  sub     rsp, 50h
0x14000131b  movzx   eax, byte ptr [rdx]
0x14000131e  mov     rsi, rcx
0x140001321  mov     rdi, [rsp+78h+arg_28]
0x140001329  xor     ebx, ebx
0x14000132b  shl     eax, 18h
0x14000132e  mov     rbp, r9
0x140001331  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x140001335  mov     r14, r8
0x140001338  movzx   eax, word ptr [rdx+1]
0x14000133c  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x140001340  mov     rax, [rdx+3]
0x140001344  add     rdx, 0Bh
0x140001348  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x14000134d  mov     rax, [rcx+8]
0x140001351  mov     [rdi], rax
0x140001354  mov     rax, [rcx+8]
0x140001358  movzx   ecx, word ptr [rax]
0x14000135b  mov     [rdi+8], ecx
0x14000135e  lea     rcx, _TraceLoggingMetadata
0x140001365  mov     [rdi+10h], rdx
0x140001369  mov     dword ptr [rdi+0Ch], 2
0x140001370  movzx   eax, word ptr [rdx]
0x140001373  mov     [rdi+18h], eax
0x140001376  lea     rax, _TraceLoggingMetadataEnd
0x14000137d  sub     eax, ecx
0x14000137f  mov     dword ptr [rdi+1Ch], 1
0x140001386  mov     dword ptr [rsp+78h+arg_28], eax
0x14000138d  mov     eax, dword ptr [rsp+78h+arg_28]
0x140001394  mov     rax, gs:58h
0x14000139d  mov     edx, 1
0x1400013a2  mov     rcx, [rax]
0x1400013a5  cmp     [rdx+rcx], bl
0x1400013a8  jnz     short loc_1400013C7
0x1400013aa  mov     ecx, 20000019h
0x1400013af  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1400013b5  test    al, al
0x1400013b7  jz      short loc_1400013C2
0x1400013b9  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x1400013be  test    al, al
0x1400013c0  jz      short loc_1400013C7
0x1400013c2  mov     ebx, 2
0x1400013c7  mov     eax, [rsp+78h+arg_20]
0x1400013ce  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x1400013d3  mov     rcx, [rsi+20h]; RegHandle
0x1400013d7  mov     r9d, ebx; Flags
0x1400013da  mov     [rsp+78h+UserData], rdi; UserData
0x1400013df  xor     r8d, r8d; Filter
0x1400013e2  mov     [rsp+78h+UserDataCount], eax; UserDataCount
0x1400013e6  mov     [rsp+78h+RelatedActivityId], rbp; RelatedActivityId
0x1400013eb  mov     [rsp+78h+ActivityId], r14; ActivityId
0x1400013f0  call    cs:__imp_EventWriteEx
0x1400013f6  add     rsp, 50h
0x1400013fa  pop     r14
0x1400013fc  pop     rdi
0x1400013fd  pop     rsi
0x1400013fe  pop     rbp
0x1400013ff  pop     rbx
0x140001400  retn
```
