# TlgHelper::LogWarningString<ushort const (&)[42],ushort const *>(ushort const (&)[42],ushort const * &&)

- ea: `0x18000450c`
- end: `0x180004577`
- name: `??$LogWarningString@AEAY0CK@$$CBGPEBG@TlgHelper@@SAXAEAY0CK@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3e0`

## callees

- `0x180001098`
- `0x18000450c`
- `0x18000f144`

## string_xrefs

- `0x18000454b`: `EventThresholdMet_UnexpectedNonHexP1Token`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[42],unsigned short const *>(
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
    v6 = L"EventThresholdMet_UnexpectedNonHexP1Token";
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
0x18000450c  mov     [rsp+arg_0], rcx
0x180004511  push    rbx
0x180004512  sub     rsp, 30h
0x180004516  mov     rbx, rdx
0x180004519  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000451e  mov     r8, rax
0x180004521  cmp     dword ptr [rax], 3
0x180004524  jbe     short loc_180004570
0x180004526  test    byte ptr [rax+10h], 2
0x18000452a  jz      short loc_180004570
0x18000452c  mov     rcx, [rax+18h]
0x180004530  and     ecx, 2
0x180004533  cmp     rcx, [rax+18h]
0x180004537  jnz     short loc_180004570
0x180004539  mov     rax, [rbx]
0x18000453c  lea     rdx, unk_18002AB1D
0x180004543  mov     [rsp+38h+arg_0], rax
0x180004548  mov     rcx, r8
0x18000454b  lea     rax, aEventthreshold_1; "EventThresholdMet_UnexpectedNonHexP1Tok"...
0x180004552  mov     [rsp+38h+arg_10], rax
0x180004557  lea     rax, [rsp+38h+arg_0]
0x18000455c  mov     [rsp+38h+var_10], rax
0x180004561  lea     rax, [rsp+38h+arg_10]
0x180004566  mov     [rsp+38h+var_18], rax
0x18000456b  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180004570  add     rsp, 30h
0x180004574  pop     rbx
0x180004575  retn
```
