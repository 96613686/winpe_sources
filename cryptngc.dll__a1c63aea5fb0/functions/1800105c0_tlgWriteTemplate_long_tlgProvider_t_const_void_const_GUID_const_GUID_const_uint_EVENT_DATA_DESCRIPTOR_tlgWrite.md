# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800105c0`
- end: `0x1800106ee`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001df90`
- `0x18001ee80`
- `0x180031fa0`

## callees

- `0x1800105c0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800106bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800106bf`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v9; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+6Ch] [rbp-3Ch]
  __int64 v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  const WCHAR *v18; // [rsp+80h] [rbp-28h]
  int v19; // [rsp+88h] [rbp-20h]
  int v20; // [rsp+8Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    while ( v6[++v7] != 0 )
      ;
    v9 = 2 * v7 + 2;
  }
  else
  {
    v6 = &LocaleName;
    v9 = 2;
  }
  v19 = v9;
  v16 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18006E008;
  v18 = v6;
  v20 = 0;
  v17 = 4;
  UserData.Size = *(unsigned __int16 *)off_18006E008;
  v14 = *(unsigned __int16 *)(a2 + 11);
  v13 = a2 + 11;
  UserData.Reserved = 2;
  v15 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x1800105c0  sub     rsp, 0A8h
0x1800105c7  mov     rax, cs:__security_cookie
0x1800105ce  xor     rax, rsp
0x1800105d1  mov     [rsp+0A8h+var_18], rax
0x1800105d9  mov     rax, [rsp+0A8h+arg_28]
0x1800105e1  mov     rcx, [rax]
0x1800105e4  test    rcx, rcx
0x1800105e7  jz      loc_1800106DD
0x1800105ed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800105f4  cmp     word ptr [rcx+rax*2+2], 0
0x1800105fa  lea     rax, [rax+1]
0x1800105fe  jnz     short loc_1800105F4
0x180010600  lea     eax, ds:2[rax*2]
0x180010607  mov     [rsp+0A8h+var_20], eax
0x18001060e  xor     r9d, r9d; RelatedActivityId
0x180010611  mov     rax, [rsp+0A8h+arg_20]
0x180010619  xor     r8d, r8d; ActivityId
0x18001061c  mov     [rsp+0A8h+var_38], rax
0x180010621  movzx   eax, byte ptr [rdx]
0x180010624  shl     eax, 18h
0x180010627  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], eax
0x18001062b  movzx   eax, word ptr [rdx+1]
0x18001062f  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x180010633  mov     rax, [rdx+3]
0x180010637  mov     [rsp+0A8h+EventDescriptor.Keyword], rax
0x18001063c  mov     rax, cs:off_18006E008
0x180010643  mov     [rsp+0A8h+var_58.Ptr], rax
0x180010648  mov     [rsp+0A8h+var_28], rcx
0x180010650  xor     ecx, ecx
0x180010652  mov     [rsp+0A8h+var_1C], ecx
0x180010659  lea     rcx, [rdx+0Bh]
0x18001065d  mov     [rsp+0A8h+var_30], 4
0x180010666  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18001066b  movzx   eax, word ptr [rax]
0x18001066e  mov     [rsp+0A8h+var_58.Size], eax
0x180010672  movzx   eax, word ptr [rcx]
0x180010675  mov     [rsp+0A8h+var_40], eax
0x180010679  lea     rax, _TraceLoggingMetadataEnd
0x180010680  mov     [rsp+0A8h+var_48], rcx
0x180010685  lea     rcx, _TraceLoggingMetadata
0x18001068c  sub     eax, ecx
0x18001068e  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x180010696  mov     [rsp+0A8h+var_3C], 1
0x18001069e  mov     [rsp+0A8h+var_78], eax
0x1800106a2  mov     eax, [rsp+0A8h+var_78]
0x1800106a6  mov     rcx, cs:RegHandle; RegHandle
0x1800106ad  lea     rax, [rsp+0A8h+var_58]
0x1800106b2  mov     [rsp+0A8h+UserData], rax; UserData
0x1800106b7  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x1800106bf  call    cs:__imp_EventWriteTransfer
0x1800106c5  mov     rcx, [rsp+0A8h+var_18]
0x1800106cd  xor     rcx, rsp; StackCookie
0x1800106d0  call    __security_check_cookie
0x1800106d5  add     rsp, 0A8h
0x1800106dc  retn
0x1800106dd  lea     rcx, LocaleName
0x1800106e4  mov     eax, 2
0x1800106e9  jmp     loc_180010607
```
