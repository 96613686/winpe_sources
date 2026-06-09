# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)

- ea: `0x18002fa80`
- end: `0x18002fb96`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `278`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 *, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038040`

## callees

- `0x18002fa80`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fb6c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fb6c`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        const unsigned __int16 **a6,
        __int64 a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  __int64 v17; // [rsp+70h] [rbp-1h]
  __int64 v18; // [rsp+78h] [rbp+7h]
  const unsigned __int16 *v19; // [rsp+80h] [rbp+Fh]
  int v20; // [rsp+88h] [rbp+17h]
  int v21; // [rsp+8Ch] [rbp+1Bh]
  __int64 v22; // [rsp+90h] [rbp+1Fh]
  __int64 v23; // [rsp+98h] [rbp+27h]

  v22 = a7;
  v23 = 1;
  v7 = *a6;
  if ( *a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_18009CA18;
    v9 = 2;
  }
  v20 = v9;
  v19 = v7;
  v21 = 0;
  v18 = 16;
  v10 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1800C60B0;
  v17 = v10;
  UserData.Size = *(unsigned __int16 *)off_1800C60B0;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  UserData.Reserved = 2;
  v16 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x18002fa80  push    rbp
0x18002fa82  lea     rbp, [rsp-3Fh]
0x18002fa87  sub     rsp, 0B0h
0x18002fa8e  mov     rax, cs:__security_cookie
0x18002fa95  xor     rax, rsp
0x18002fa98  mov     [rbp+3Fh+var_10], rax
0x18002fa9c  mov     rax, [rbp+3Fh+arg_30]
0x18002faa0  mov     r10d, 1
0x18002faa6  mov     [rbp+3Fh+var_20], rax
0x18002faaa  xor     r8d, r8d; ActivityId
0x18002faad  mov     rax, [rbp+3Fh+arg_28]
0x18002fab1  mov     [rbp+3Fh+var_18], r10
0x18002fab5  lea     r9d, [r10+1]
0x18002fab9  mov     rcx, [rax]
0x18002fabc  test    rcx, rcx
0x18002fabf  jz      loc_18002FB87
0x18002fac5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fac9  inc     rax
0x18002facc  cmp     [rcx+rax*2], r8w
0x18002fad1  jnz     short loc_18002FAC9
0x18002fad3  lea     eax, ds:2[rax*2]
0x18002fada  mov     [rbp+3Fh+var_28], eax
0x18002fadd  mov     rax, [rbp+3Fh+arg_20]
0x18002fae1  mov     [rbp+3Fh+var_30], rcx
0x18002fae5  mov     [rbp+3Fh+var_24], r8d
0x18002fae9  mov     [rbp+3Fh+var_38], 10h
0x18002faf1  mov     rcx, [rax]
0x18002faf4  movzx   eax, byte ptr [rdx]
0x18002faf7  shl     eax, 18h
0x18002fafa  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18002fafd  movzx   eax, word ptr [rdx+1]
0x18002fb01  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18002fb04  mov     rax, [rdx+3]
0x18002fb08  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18002fb0c  mov     rax, cs:off_1800C60B0
0x18002fb13  mov     [rbp+3Fh+var_60.Ptr], rax
0x18002fb17  mov     [rbp+3Fh+var_40], rcx
0x18002fb1b  lea     rcx, [rdx+0Bh]
0x18002fb1f  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18002fb23  movzx   eax, word ptr [rax]
0x18002fb26  mov     [rbp+3Fh+var_60.Size], eax
0x18002fb29  movzx   eax, word ptr [rcx]
0x18002fb2c  mov     [rbp+3Fh+var_48], eax
0x18002fb2f  lea     rax, _TraceLoggingMetadataEnd
0x18002fb36  mov     [rbp+3Fh+var_50], rcx
0x18002fb3a  lea     rcx, _TraceLoggingMetadata
0x18002fb41  sub     eax, ecx
0x18002fb43  mov     dword ptr [rbp+3Fh+var_60.0Ch], r9d
0x18002fb47  mov     [rbp+3Fh+var_44], r10d
0x18002fb4b  xor     r9d, r9d; RelatedActivityId
0x18002fb4e  mov     [rbp+3Fh+var_80], eax
0x18002fb51  mov     eax, [rbp+3Fh+var_80]
0x18002fb54  mov     rcx, cs:RegHandle; RegHandle
0x18002fb5b  lea     rax, [rbp+3Fh+var_60]
0x18002fb5f  mov     [rsp+0B0h+UserData], rax; UserData
0x18002fb64  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x18002fb6c  call    cs:__imp_EventWriteTransfer
0x18002fb72  mov     rcx, [rbp+3Fh+var_10]
0x18002fb76  xor     rcx, rsp; StackCookie
0x18002fb79  call    __security_check_cookie
0x18002fb7e  add     rsp, 0B0h
0x18002fb85  pop     rbp
0x18002fb86  retn
0x18002fb87  lea     rcx, qword_18009CA18
0x18002fb8e  mov     eax, r9d
0x18002fb91  jmp     loc_18002FADA
```
