# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010db`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adf0`
- `0x18001eae0`
- `0x18001ed20`
- `0x18002bc3c`

## callees

- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010b9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010b9`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
  v15 = 4;
  v13 = 4;
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
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-47h]
0x18000100f  sub     rsp, 0A0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+47h+var_10], rax
0x180001024  mov     rax, [rbp+47h+arg_28]
0x180001028  mov     r10, rcx
0x18000102b  mov     [rbp+47h+var_20], rax
0x18000102f  lea     rcx, [rdx+0Bh]
0x180001033  mov     rax, [rbp+47h+arg_20]
0x180001037  mov     r8d, 4
0x18000103d  mov     [rbp+47h+var_30], rax
0x180001041  xor     r9d, r9d; RelatedActivityId
0x180001044  movzx   eax, byte ptr [rdx]
0x180001047  shl     eax, 18h
0x18000104a  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x18000104d  movzx   eax, word ptr [rdx+1]
0x180001051  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180001054  mov     rax, [rdx+3]
0x180001058  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18000105c  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180001060  mov     rax, [r10+8]
0x180001064  mov     [rbp+47h+var_50.Ptr], rax
0x180001068  mov     [rbp+47h+var_18], r8
0x18000106c  mov     [rbp+47h+var_28], r8
0x180001070  movzx   eax, word ptr [rax]
0x180001073  mov     [rbp+47h+var_50.Size], eax
0x180001076  movzx   eax, word ptr [rcx]
0x180001079  mov     [rbp+47h+var_38], eax
0x18000107c  lea     rax, _TraceLoggingMetadataEnd
0x180001083  mov     [rbp+47h+var_40], rcx
0x180001087  lea     rcx, _TraceLoggingMetadata
0x18000108e  sub     eax, ecx
0x180001090  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x180001097  mov     [rbp+47h+var_34], 1
0x18000109e  mov     [rbp+47h+var_70], eax
0x1800010a1  mov     eax, [rbp+47h+var_70]
0x1800010a4  mov     rcx, [r10+20h]; RegHandle
0x1800010a8  lea     rax, [rbp+47h+var_50]
0x1800010ac  mov     [rsp+0A0h+UserData], rax; UserData
0x1800010b1  mov     [rsp+0A0h+UserDataCount], r8d; UserDataCount
0x1800010b6  xor     r8d, r8d; ActivityId
0x1800010b9  call    cs:__imp_EventWriteTransfer
0x1800010c0  nop     dword ptr [rax+rax+00h]
0x1800010c5  mov     rcx, [rbp+47h+var_10]
0x1800010c9  xor     rcx, rsp; StackCookie
0x1800010cc  call    __security_check_cookie
0x1800010d1  add     rsp, 0A0h
0x1800010d8  pop     rbp
0x1800010d9  retn
```
