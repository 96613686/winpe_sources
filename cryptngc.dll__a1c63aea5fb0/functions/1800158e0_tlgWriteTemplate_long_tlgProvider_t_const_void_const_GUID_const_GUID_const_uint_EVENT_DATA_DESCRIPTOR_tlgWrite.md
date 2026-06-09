# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x1800158e0`
- end: `0x180015999`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `185`
- prototype: ``
- caller_count: `103`
- callee_count: `1`
- tags: ``

## callers

- `0x1800188e0`
- `0x18001a014`
- `0x18001c290`
- `0x18001de44`
- `0x18001df90`
- `0x18001e370`
- `0x18001e810`
- `0x18001ed50`
- `0x180020014`
- `0x1800201f8`
- `0x180020320`
- `0x1800213c4`
- `0x180021a80`
- `0x180023714`
- `0x180023e1c`
- `0x180024014`
- `0x180024494`
- `0x180024648`
- `0x1800247ec`
- `0x18002494c`
- `0x180025010`
- `0x18002541c`
- `0x1800254bc`
- `0x180029bc0`
- `0x180032cb0`
- `0x180033f60`
- `0x1800341d0`
- `0x1800345a8`
- `0x180034e70`
- `0x180034f30`
- `0x180035688`
- `0x180035bf8`
- `0x1800368c8`
- `0x180036be0`
- `0x180036d60`
- `0x180036ee0`
- `0x180037080`
- `0x1800371e0`
- `0x180037360`
- `0x1800374f0`
- `0x180037920`
- `0x180037b40`
- `0x180037ef0`
- `0x1800382e0`
- `0x180038470`
- `0x1800384e0`
- `0x1800387a0`
- `0x180038910`
- `0x180038a80`
- `0x180039108`

## callees

- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001597e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001597e`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int8 *v8; // [rsp+58h] [rbp-28h]
  int v9; // [rsp+60h] [rbp-20h]
  int v10; // [rsp+64h] [rbp-1Ch]
  __int64 v11; // [rsp+68h] [rbp-18h]
  __int64 v12; // [rsp+70h] [rbp-10h]

  v11 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v12 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v9 = *(unsigned __int16 *)(a2 + 11);
  v8 = a2 + 11;
  UserData.Reserved = 2;
  v10 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 3u, &UserData);
}

```

## disassembly

```asm
0x1800158e0  push    rbp
0x1800158e2  mov     rbp, rsp
0x1800158e5  sub     rsp, 80h
0x1800158ec  mov     rax, cs:__security_cookie
0x1800158f3  xor     rax, rsp
0x1800158f6  mov     [rbp+var_8], rax
0x1800158fa  mov     rax, [rbp+arg_20]
0x1800158fe  mov     r10, rcx
0x180015901  mov     [rbp+var_18], rax
0x180015905  lea     rcx, [rdx+0Bh]
0x180015909  movzx   eax, byte ptr [rdx]
0x18001590c  shl     eax, 18h
0x18001590f  mov     dword ptr [rbp+EventDescriptor.Id], eax
0x180015912  movzx   eax, word ptr [rdx+1]
0x180015916  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x180015919  mov     rax, [rdx+3]
0x18001591d  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180015921  mov     [rbp+EventDescriptor.Keyword], rax
0x180015925  mov     rax, [r10+8]
0x180015929  mov     [rbp+var_38.Ptr], rax
0x18001592d  mov     [rbp+var_10], 4
0x180015935  movzx   eax, word ptr [rax]
0x180015938  mov     [rbp+var_38.Size], eax
0x18001593b  movzx   eax, word ptr [rcx]
0x18001593e  mov     [rbp+var_20], eax
0x180015941  lea     rax, _TraceLoggingMetadataEnd
0x180015948  mov     [rbp+var_28], rcx
0x18001594c  lea     rcx, _TraceLoggingMetadata
0x180015953  sub     eax, ecx
0x180015955  mov     dword ptr [rbp+var_38.0Ch], 2
0x18001595c  mov     [rbp+var_1C], 1
0x180015963  mov     [rbp+var_50], eax
0x180015966  mov     eax, [rbp+var_50]
0x180015969  mov     rcx, [r10+20h]; RegHandle
0x18001596d  lea     rax, [rbp+var_38]
0x180015971  mov     [rsp+80h+UserData], rax; UserData
0x180015976  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x18001597e  call    cs:__imp_EventWriteTransfer
0x180015984  mov     rcx, [rbp+var_8]
0x180015988  xor     rcx, rsp; StackCookie
0x18001598b  call    __security_check_cookie
0x180015990  add     rsp, 80h
0x180015997  pop     rbp
0x180015998  retn
```
