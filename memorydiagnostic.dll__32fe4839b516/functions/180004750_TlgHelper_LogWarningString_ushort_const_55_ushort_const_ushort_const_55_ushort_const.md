# TlgHelper::LogWarningString<ushort const (&)[55],ushort const *>(ushort const (&)[55],ushort const * &&)

- ea: `0x180004750`
- end: `0x1800047bb`
- name: `??$LogWarningString@AEAY0DH@$$CBGPEBG@TlgHelper@@SAXAEAY0DH@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002256e`

## callees

- `0x180001098`
- `0x180004750`
- `0x18000f144`

## string_xrefs

- `0x18000478f`: `EventThresholdMet_UnexpectedCodeTokenConversionFailure`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[55],unsigned short const *>(
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
    v6 = L"EventThresholdMet_UnexpectedCodeTokenConversionFailure";
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
0x180004750  mov     [rsp+arg_0], rcx
0x180004755  push    rbx
0x180004756  sub     rsp, 30h
0x18000475a  mov     rbx, rdx
0x18000475d  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180004762  mov     r8, rax
0x180004765  cmp     dword ptr [rax], 3
0x180004768  jbe     short loc_1800047B4
0x18000476a  test    byte ptr [rax+10h], 2
0x18000476e  jz      short loc_1800047B4
0x180004770  mov     rcx, [rax+18h]
0x180004774  and     ecx, 2
0x180004777  cmp     rcx, [rax+18h]
0x18000477b  jnz     short loc_1800047B4
0x18000477d  mov     rax, [rbx]
0x180004780  lea     rdx, unk_18002AB1D
0x180004787  mov     [rsp+38h+arg_0], rax
0x18000478c  mov     rcx, r8
0x18000478f  lea     rax, aEventthreshold_3; "EventThresholdMet_UnexpectedCodeTokenCo"...
0x180004796  mov     [rsp+38h+arg_10], rax
0x18000479b  lea     rax, [rsp+38h+arg_0]
0x1800047a0  mov     [rsp+38h+var_10], rax
0x1800047a5  lea     rax, [rsp+38h+arg_10]
0x1800047aa  mov     [rsp+38h+var_18], rax
0x1800047af  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800047b4  add     rsp, 30h
0x1800047b8  pop     rbx
0x1800047b9  retn
```
