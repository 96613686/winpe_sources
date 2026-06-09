# TlgHelper::LogWarningString<ushort const (&)[44],ushort const *>(ushort const (&)[44],ushort const * &&)

- ea: `0x180004580`
- end: `0x1800045eb`
- name: `??$LogWarningString@AEAY0CM@$$CBGPEBG@TlgHelper@@SAXAEAY0CM@$$CBG$$QEAPEBG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3e0`

## callees

- `0x180001098`
- `0x180004580`
- `0x18000f144`

## string_xrefs

- `0x1800045bf`: `EventThresholdMet_UnexpectedNonHexCodeToken`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogWarningString<unsigned short const (&)[44],unsigned short const *>(
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
    v6 = L"EventThresholdMet_UnexpectedNonHexCodeToken";
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
0x180004580  mov     [rsp+arg_0], rcx
0x180004585  push    rbx
0x180004586  sub     rsp, 30h
0x18000458a  mov     rbx, rdx
0x18000458d  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180004592  mov     r8, rax
0x180004595  cmp     dword ptr [rax], 3
0x180004598  jbe     short loc_1800045E4
0x18000459a  test    byte ptr [rax+10h], 2
0x18000459e  jz      short loc_1800045E4
0x1800045a0  mov     rcx, [rax+18h]
0x1800045a4  and     ecx, 2
0x1800045a7  cmp     rcx, [rax+18h]
0x1800045ab  jnz     short loc_1800045E4
0x1800045ad  mov     rax, [rbx]
0x1800045b0  lea     rdx, unk_18002AB1D
0x1800045b7  mov     [rsp+38h+arg_0], rax
0x1800045bc  mov     rcx, r8
0x1800045bf  lea     rax, aEventthreshold_14; "EventThresholdMet_UnexpectedNonHexCodeT"...
0x1800045c6  mov     [rsp+38h+arg_10], rax
0x1800045cb  lea     rax, [rsp+38h+arg_0]
0x1800045d0  mov     [rsp+38h+var_10], rax
0x1800045d5  lea     rax, [rsp+38h+arg_10]
0x1800045da  mov     [rsp+38h+var_18], rax
0x1800045df  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800045e4  add     rsp, 30h
0x1800045e8  pop     rbx
0x1800045e9  retn
```
