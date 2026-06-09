# TlgHelper::LogWarningString<ushort const (&)[48],ushort const *>(ushort const (&)[48],ushort const * &&)

- ea: `0x180004668`
- end: `0x1800046d3`
- name: `??$LogWarningString@AEAY0DA@$$CBGPEBG@TlgHelper@@SAXAEAY0DA@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800225bd`

## callees

- `0x180001098`
- `0x180004668`
- `0x18000f144`

## string_xrefs

- `0x1800046a7`: `EventThresholdMet_UnexpectedCodeTokenOutOfRange`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[48],unsigned short const *>(
        __int64 a1,
        __int64 *a2)
{
  const struct _tlgProvider_t *result; // rax
  int v4; // r9d
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v6; // [rsp+50h] [rbp+18h] BYREF

  v5 = a1;
  result = TlgHelper::Provider();
  if ( *(_DWORD *)result > 3u
    && (*((_BYTE *)result + 16) & 2) != 0
    && (*((_QWORD *)result + 3) & 2LL) == *((_QWORD *)result + 3) )
  {
    v5 = *a2;
    v6 = L"EventThresholdMet_UnexpectedCodeTokenOutOfRange";
    return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                                            (_DWORD)result,
                                            (unsigned int)&unk_18002AB1D,
                                            (_DWORD)result,
                                            v4,
                                            (__int64)&v6,
                                            (__int64)&v5);
  }
  return result;
}

```

## disassembly

```asm
0x180004668  mov     [rsp+arg_0], rcx
0x18000466d  push    rbx
0x18000466e  sub     rsp, 30h
0x180004672  mov     rbx, rdx
0x180004675  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000467a  mov     r8, rax
0x18000467d  cmp     dword ptr [rax], 3
0x180004680  jbe     short loc_1800046CC
0x180004682  test    byte ptr [rax+10h], 2
0x180004686  jz      short loc_1800046CC
0x180004688  mov     rcx, [rax+18h]
0x18000468c  and     ecx, 2
0x18000468f  cmp     rcx, [rax+18h]
0x180004693  jnz     short loc_1800046CC
0x180004695  mov     rax, [rbx]
0x180004698  lea     rdx, unk_18002AB1D
0x18000469f  mov     [rsp+38h+arg_0], rax
0x1800046a4  mov     rcx, r8
0x1800046a7  lea     rax, aEventthreshold_9; "EventThresholdMet_UnexpectedCodeTokenOu"...
0x1800046ae  mov     [rsp+38h+arg_10], rax
0x1800046b3  lea     rax, [rsp+38h+arg_0]
0x1800046b8  mov     [rsp+38h+var_10], rax
0x1800046bd  lea     rax, [rsp+38h+arg_10]
0x1800046c2  mov     [rsp+38h+var_18], rax
0x1800046c7  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800046cc  add     rsp, 30h
0x1800046d0  pop     rbx
0x1800046d1  retn
```
