# E2ETraceEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x140001d0c`
- end: `0x140001deb`
- name: `?E2ETraceEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001df4`
- `0x140001f7c`
- `0x140002094`

## callees

- `0x140001cd8`
- `0x140001d0c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001da2`
- `ntoskrnl!EtwWriteTransfer` at `0x140001da2`
- `ntoskrnl!EtwWrite` at `0x140001dcd`
- `ntoskrnl!EtwWrite` at `0x140001dcd`

## pseudocode

```c
__int64 __fastcall E2ETraceEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned int v6; // edi

  v6 = 0;
  if ( (unsigned int)E2ETraceEnabled(EventDescriptor) == 1 )
  {
    if ( RelatedActivityId
      && (RelatedActivityId->Data1
       || RelatedActivityId->Data2
       || RelatedActivityId->Data3
       || RelatedActivityId->Data4[0]
       || RelatedActivityId->Data4[1]
       || RelatedActivityId->Data4[2]
       || RelatedActivityId->Data4[3]
       || RelatedActivityId->Data4[4]
       || RelatedActivityId->Data4[5]
       || RelatedActivityId->Data4[6]
       || RelatedActivityId->Data4[7]) )
    {
      return (unsigned int)EtwWriteTransfer(
                             g_e2eTraceHandle,
                             EventDescriptor,
                             ActivityId,
                             RelatedActivityId,
                             UserDataCount,
                             UserData);
    }
    else
    {
      return (unsigned int)EtwWrite(g_e2eTraceHandle, EventDescriptor, ActivityId, UserDataCount, UserData);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140001d0c  push    rbx
0x140001d0e  push    rbp
0x140001d0f  push    rsi
0x140001d10  push    rdi
0x140001d11  push    r14
0x140001d13  push    r15
0x140001d15  sub     rsp, 38h
0x140001d19  xor     r15d, r15d
0x140001d1c  mov     ebp, r9d
0x140001d1f  mov     edi, r15d
0x140001d22  mov     rbx, r8
0x140001d25  mov     r14, rdx
0x140001d28  mov     rsi, rcx
0x140001d2b  call    ?E2ETraceEnabled@@YAHPEBU_EVENT_DESCRIPTOR@@@Z; E2ETraceEnabled(_EVENT_DESCRIPTOR const *)
0x140001d30  cmp     eax, 1
0x140001d33  jnz     loc_140001DDB
0x140001d39  test    rbx, rbx
0x140001d3c  jz      short loc_140001DB0
0x140001d3e  cmp     [rbx], r15d
0x140001d41  jnz     short loc_140001D81
0x140001d43  cmp     [rbx+4], r15w
0x140001d48  jnz     short loc_140001D81
0x140001d4a  cmp     [rbx+6], r15w
0x140001d4f  jnz     short loc_140001D81
0x140001d51  cmp     [rbx+8], r15b
0x140001d55  jnz     short loc_140001D81
0x140001d57  cmp     [rbx+9], r15b
0x140001d5b  jnz     short loc_140001D81
0x140001d5d  cmp     [rbx+0Ah], r15b
0x140001d61  jnz     short loc_140001D81
0x140001d63  cmp     [rbx+0Bh], r15b
0x140001d67  jnz     short loc_140001D81
0x140001d69  cmp     [rbx+0Ch], r15b
0x140001d6d  jnz     short loc_140001D81
0x140001d6f  cmp     [rbx+0Dh], r15b
0x140001d73  jnz     short loc_140001D81
0x140001d75  cmp     [rbx+0Eh], r15b
0x140001d79  jnz     short loc_140001D81
0x140001d7b  cmp     [rbx+0Fh], r15b
0x140001d7f  jz      short loc_140001DB0
0x140001d81  mov     rax, [rsp+68h+arg_20]
0x140001d89  mov     r9, rbx; RelatedActivityId
0x140001d8c  mov     rcx, cs:?g_e2eTraceHandle@@3_KA; RegHandle
0x140001d93  mov     r8, r14; ActivityId
0x140001d96  mov     [rsp+68h+UserData], rax; UserData
0x140001d9b  mov     rdx, rsi; EventDescriptor
0x140001d9e  mov     [rsp+68h+UserDataCount], ebp; UserDataCount
0x140001da2  call    cs:__imp_EtwWriteTransfer
0x140001da9  nop     dword ptr [rax+rax+00h]
0x140001dae  jmp     short loc_140001DD9
0x140001db0  mov     rax, [rsp+68h+arg_20]
0x140001db8  mov     r9d, ebp; UserDataCount
0x140001dbb  mov     rcx, cs:?g_e2eTraceHandle@@3_KA; RegHandle
0x140001dc2  mov     r8, r14; ActivityId
0x140001dc5  mov     rdx, rsi; EventDescriptor
0x140001dc8  mov     qword ptr [rsp+68h+UserDataCount], rax; UserData
0x140001dcd  call    cs:__imp_EtwWrite
0x140001dd4  nop     dword ptr [rax+rax+00h]
0x140001dd9  mov     edi, eax
0x140001ddb  mov     eax, edi
0x140001ddd  add     rsp, 38h
0x140001de1  pop     r15
0x140001de3  pop     r14
0x140001de5  pop     rdi
0x140001de6  pop     rsi
0x140001de7  pop     rbp
0x140001de8  pop     rbx
0x140001de9  retn
```
