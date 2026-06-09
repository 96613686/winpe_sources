# TlgHelper::LogWarningString<ushort const (&)[53],ushort const *>(ushort const (&)[53],ushort const * &&)

- ea: `0x1800046dc`
- end: `0x180004747`
- name: `??$LogWarningString@AEAY0DF@$$CBGPEBG@TlgHelper@@SAXAEAY0DF@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800224d0`

## callees

- `0x180001098`
- `0x1800046dc`
- `0x18000f144`

## string_xrefs

- `0x18000471b`: `EventThresholdMet_UnexpectedP1TokenConversionFailure`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[53],unsigned short const *>(
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
    v6 = L"EventThresholdMet_UnexpectedP1TokenConversionFailure";
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
0x1800046dc  mov     [rsp+arg_0], rcx
0x1800046e1  push    rbx
0x1800046e2  sub     rsp, 30h
0x1800046e6  mov     rbx, rdx
0x1800046e9  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800046ee  mov     r8, rax
0x1800046f1  cmp     dword ptr [rax], 3
0x1800046f4  jbe     short loc_180004740
0x1800046f6  test    byte ptr [rax+10h], 2
0x1800046fa  jz      short loc_180004740
0x1800046fc  mov     rcx, [rax+18h]
0x180004700  and     ecx, 2
0x180004703  cmp     rcx, [rax+18h]
0x180004707  jnz     short loc_180004740
0x180004709  mov     rax, [rbx]
0x18000470c  lea     rdx, unk_18002AB1D
0x180004713  mov     [rsp+38h+arg_0], rax
0x180004718  mov     rcx, r8
0x18000471b  lea     rax, aEventthreshold; "EventThresholdMet_UnexpectedP1TokenConv"...
0x180004722  mov     [rsp+38h+arg_10], rax
0x180004727  lea     rax, [rsp+38h+arg_0]
0x18000472c  mov     [rsp+38h+var_10], rax
0x180004731  lea     rax, [rsp+38h+arg_10]
0x180004736  mov     [rsp+38h+var_18], rax
0x18000473b  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180004740  add     rsp, 30h
0x180004744  pop     rbx
0x180004745  retn
```
