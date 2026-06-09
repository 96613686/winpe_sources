# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18001fb80`
- end: `0x18001fc50`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `208`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009810`
- `0x1800446f0`
- `0x180048f38`
- `0x180049924`
- `0x18004ba30`

## callees

- `0x18002e5f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc35`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc35`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+6Ch] [rbp+13h]
  __int64 v12; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+78h] [rbp+1Fh]
  __int64 v14; // [rsp+80h] [rbp+27h]
  __int64 v15; // [rsp+88h] [rbp+2Fh]

  v14 = a6;
  v12 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v13 = 4;
  v15 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v10 = *(unsigned __int16 *)(a2 + 11);
  v9 = a2 + 11;
  UserData.Reserved = 2;
  v11 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x18001fb80  push    rbp
0x18001fb82  lea     rbp, [rsp-47h]
0x18001fb87  sub     rsp, 0A0h
0x18001fb8e  mov     rax, cs:__security_cookie
0x18001fb95  xor     rax, rsp
0x18001fb98  mov     [rbp+47h+var_10], rax
0x18001fb9c  mov     rax, [rbp+47h+arg_28]
0x18001fba0  mov     r10, rcx
0x18001fba3  mov     [rbp+47h+var_20], rax
0x18001fba7  lea     rcx, [rdx+0Bh]
0x18001fbab  mov     rax, [rbp+47h+arg_20]
0x18001fbaf  mov     r8d, 4
0x18001fbb5  mov     [rbp+47h+var_30], rax
0x18001fbb9  xor     r9d, r9d; RelatedActivityId
0x18001fbbc  movzx   eax, byte ptr [rdx]
0x18001fbbf  shl     eax, 18h
0x18001fbc2  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x18001fbc5  movzx   eax, word ptr [rdx+1]
0x18001fbc9  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18001fbcc  mov     rax, [rdx+3]
0x18001fbd0  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18001fbd4  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x18001fbd8  mov     rax, [r10+8]
0x18001fbdc  mov     [rbp+47h+var_50.Ptr], rax
0x18001fbe0  mov     [rbp+47h+var_28], r8
0x18001fbe4  mov     [rbp+47h+var_18], 8
0x18001fbec  movzx   eax, word ptr [rax]
0x18001fbef  mov     [rbp+47h+var_50.Size], eax
0x18001fbf2  movzx   eax, word ptr [rcx]
0x18001fbf5  mov     [rbp+47h+var_38], eax
0x18001fbf8  lea     rax, _TraceLoggingMetadataEnd
0x18001fbff  mov     [rbp+47h+var_40], rcx
0x18001fc03  lea     rcx, _TraceLoggingMetadata
0x18001fc0a  sub     eax, ecx
0x18001fc0c  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x18001fc13  mov     [rbp+47h+var_34], 1
0x18001fc1a  mov     [rbp+47h+var_70], eax
0x18001fc1d  mov     eax, [rbp+47h+var_70]
0x18001fc20  mov     rcx, [r10+20h]; RegHandle
0x18001fc24  lea     rax, [rbp+47h+var_50]
0x18001fc28  mov     [rsp+0A0h+UserData], rax; UserData
0x18001fc2d  mov     [rsp+0A0h+UserDataCount], r8d; UserDataCount
0x18001fc32  xor     r8d, r8d; ActivityId
0x18001fc35  call    cs:__imp_EventWriteTransfer
0x18001fc3b  mov     rcx, [rbp+47h+var_10]
0x18001fc3f  xor     rcx, rsp; StackCookie
0x18001fc42  call    __security_check_cookie
0x18001fc47  add     rsp, 0A0h
0x18001fc4e  pop     rbp
0x18001fc4f  retn
```
