# TlgHelper::LogWarningString<ushort const (&)[46],ushort const *>(ushort const (&)[46],ushort const * &&)

- ea: `0x1800045f4`
- end: `0x18000465f`
- name: `??$LogWarningString@AEAY0CO@$$CBGPEBG@TlgHelper@@SAXAEAY0CO@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002251f`

## callees

- `0x180001098`
- `0x1800045f4`
- `0x18000f144`

## string_xrefs

- `0x180004633`: `EventThresholdMet_UnexpectedP1TokenOutOfRange`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[46],unsigned short const *>(
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
    v6 = L"EventThresholdMet_UnexpectedP1TokenOutOfRange";
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
0x1800045f4  mov     [rsp+arg_0], rcx
0x1800045f9  push    rbx
0x1800045fa  sub     rsp, 30h
0x1800045fe  mov     rbx, rdx
0x180004601  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180004606  mov     r8, rax
0x180004609  cmp     dword ptr [rax], 3
0x18000460c  jbe     short loc_180004658
0x18000460e  test    byte ptr [rax+10h], 2
0x180004612  jz      short loc_180004658
0x180004614  mov     rcx, [rax+18h]
0x180004618  and     ecx, 2
0x18000461b  cmp     rcx, [rax+18h]
0x18000461f  jnz     short loc_180004658
0x180004621  mov     rax, [rbx]
0x180004624  lea     rdx, unk_18002AB1D
0x18000462b  mov     [rsp+38h+arg_0], rax
0x180004630  mov     rcx, r8
0x180004633  lea     rax, aEventthreshold_15; "EventThresholdMet_UnexpectedP1TokenOutO"...
0x18000463a  mov     [rsp+38h+arg_10], rax
0x18000463f  lea     rax, [rsp+38h+arg_0]
0x180004644  mov     [rsp+38h+var_10], rax
0x180004649  lea     rax, [rsp+38h+arg_10]
0x18000464e  mov     [rsp+38h+var_18], rax
0x180004653  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180004658  add     rsp, 30h
0x18000465c  pop     rbx
0x18000465d  retn
```
