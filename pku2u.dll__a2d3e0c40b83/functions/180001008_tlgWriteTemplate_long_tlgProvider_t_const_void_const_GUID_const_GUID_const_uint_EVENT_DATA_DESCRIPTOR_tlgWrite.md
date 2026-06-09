# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x180001155`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@D@@@Z`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e368`

## callees

- `0x180001008`
- `0x1800210f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000113a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000113a`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        const unsigned __int16 **a11)
{
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v19; // [rsp+60h] [rbp-71h]
  int v20; // [rsp+68h] [rbp-69h]
  int v21; // [rsp+6Ch] [rbp-65h]
  __int64 v22; // [rsp+70h] [rbp-61h]
  __int64 v23; // [rsp+78h] [rbp-59h]
  __int64 v24; // [rsp+80h] [rbp-51h]
  __int64 v25; // [rsp+88h] [rbp-49h]
  __int64 v26; // [rsp+90h] [rbp-41h]
  __int64 v27; // [rsp+98h] [rbp-39h]
  __int64 v28; // [rsp+A0h] [rbp-31h]
  __int64 v29; // [rsp+A8h] [rbp-29h]
  __int64 v30; // [rsp+B0h] [rbp-21h]
  __int64 v31; // [rsp+B8h] [rbp-19h]
  __int64 v32; // [rsp+C0h] [rbp-11h]
  __int64 v33; // [rsp+C8h] [rbp-9h]
  const unsigned __int16 *v34; // [rsp+D0h] [rbp-1h]
  int v35; // [rsp+D8h] [rbp+7h]
  int v36; // [rsp+DCh] [rbp+Bh]

  v12 = *a11;
  if ( *a11 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &byte_18004A111;
    v14 = 1;
  }
  v35 = v14;
  v32 = a10;
  v30 = a9;
  v28 = a8;
  v34 = v12;
  v36 = 0;
  v33 = 8;
  v15 = *a7;
  v24 = a6;
  v22 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v26 = v15;
  v31 = 4;
  v29 = 1;
  v27 = 16;
  v25 = 8;
  v23 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v20 = *(unsigned __int16 *)(a2 + 11);
  v19 = a2 + 11;
  UserData.Reserved = 2;
  v21 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-1Fh]
0x18000100f  sub     rsp, 0F0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+1Fh+var_10], rax
0x180001024  mov     rax, [rbp+1Fh+arg_50]
0x180001028  mov     r10, rcx
0x18000102b  xor     r9d, r9d; RelatedActivityId
0x18000102e  mov     r11d, 1
0x180001034  mov     rcx, [rax]
0x180001037  test    rcx, rcx
0x18000103a  jz      short loc_18000104D
0x18000103c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001040  inc     rax
0x180001043  cmp     [rcx+rax], r9b
0x180001047  jnz     short loc_180001040
0x180001049  inc     eax
0x18000104b  jmp     short loc_180001057
0x18000104d  lea     rcx, byte_18004A111
0x180001054  mov     eax, r11d
0x180001057  mov     [rbp+1Fh+var_18], eax
0x18000105a  xor     r8d, r8d; ActivityId
0x18000105d  mov     rax, [rbp+1Fh+arg_48]
0x180001061  mov     [rbp+1Fh+var_30], rax
0x180001065  mov     rax, [rbp+1Fh+arg_40]
0x180001069  mov     [rbp+1Fh+var_40], rax
0x18000106d  mov     rax, [rbp+1Fh+arg_38]
0x180001071  mov     [rbp+1Fh+var_50], rax
0x180001075  mov     rax, [rbp+1Fh+arg_30]
0x180001079  mov     [rbp+1Fh+var_20], rcx
0x18000107d  mov     [rbp+1Fh+var_14], r9d
0x180001081  mov     [rbp+1Fh+var_28], 8
0x180001089  mov     rcx, [rax]
0x18000108c  mov     rax, [rbp+1Fh+arg_28]
0x180001090  mov     [rbp+1Fh+var_70], rax
0x180001094  mov     rax, [rbp+1Fh+arg_20]
0x180001098  mov     [rbp+1Fh+var_80], rax
0x18000109c  movzx   eax, byte ptr [rdx]
0x18000109f  shl     eax, 18h
0x1800010a2  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x1800010a6  movzx   eax, word ptr [rdx+1]
0x1800010aa  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x1800010ae  mov     rax, [rdx+3]
0x1800010b2  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x1800010b7  mov     rax, [r10+8]
0x1800010bb  mov     [rsp+0F0h+var_A0.Ptr], rax
0x1800010c0  mov     [rbp+1Fh+var_60], rcx
0x1800010c4  lea     rcx, [rdx+0Bh]
0x1800010c8  mov     [rbp+1Fh+var_38], 4
0x1800010d0  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x1800010d5  mov     [rbp+1Fh+var_48], r11
0x1800010d9  mov     [rbp+1Fh+var_58], 10h
0x1800010e1  mov     [rbp+1Fh+var_68], 8
0x1800010e9  mov     [rbp+1Fh+var_78], 8
0x1800010f1  movzx   eax, word ptr [rax]
0x1800010f4  mov     [rbp+1Fh+var_A0.Size], eax
0x1800010f7  movzx   eax, word ptr [rcx]
0x1800010fa  mov     [rbp+1Fh+var_88], eax
0x1800010fd  lea     rax, _TraceLoggingMetadataEnd
0x180001104  mov     [rbp+1Fh+var_90], rcx
0x180001108  lea     rcx, _TraceLoggingMetadata
0x18000110f  sub     eax, ecx
0x180001111  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x180001118  mov     [rbp+1Fh+var_84], r11d
0x18000111c  mov     [rsp+0F0h+var_C0], eax
0x180001120  mov     eax, [rsp+0F0h+var_C0]
0x180001124  mov     rcx, [r10+20h]; RegHandle
0x180001128  lea     rax, [rsp+0F0h+var_A0]
0x18000112d  mov     [rsp+0F0h+UserData], rax; UserData
0x180001132  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x18000113a  call    cs:__imp_EventWriteTransfer
0x180001140  mov     rcx, [rbp+1Fh+var_10]
0x180001144  xor     rcx, rsp; StackCookie
0x180001147  call    __security_check_cookie
0x18000114c  add     rsp, 0F0h
0x180001153  pop     rbp
0x180001154  retn
```
