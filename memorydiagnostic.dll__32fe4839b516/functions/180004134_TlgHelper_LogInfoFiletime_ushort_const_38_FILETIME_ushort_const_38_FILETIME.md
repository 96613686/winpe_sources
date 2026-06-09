# TlgHelper::LogInfoFiletime<ushort const (&)[38],_FILETIME>(ushort const (&)[38],_FILETIME &&)

- ea: `0x180004134`
- end: `0x18000419f`
- name: `??$LogInfoFiletime@AEAY0CG@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CG@$$CBG$$QEAU_FILETIME@@@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000df2c`

## callees

- `0x180001224`
- `0x180004134`
- `0x18000f144`

## string_xrefs

- `0x180004173`: `InitializeConfig_LastScanDecisionTime`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogInfoFiletime<unsigned short const (&)[38],_FILETIME>(
        __int64 a1,
        __int64 *a2)
{
  const struct _tlgProvider_t *result; // rax
  int v4; // r9d
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v6; // [rsp+50h] [rbp+18h] BYREF

  v5 = a1;
  result = TlgHelper::Provider();
  if ( *(_DWORD *)result > 4u
    && (*((_BYTE *)result + 16) & 2) != 0
    && (*((_QWORD *)result + 3) & 2LL) == *((_QWORD *)result + 3) )
  {
    v5 = *a2;
    v6 = L"InitializeConfig_LastScanDecisionTime";
    return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                                            (_DWORD)result,
                                            (unsigned int)&unk_18002AB6C,
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
0x180004134  mov     [rsp+arg_0], rcx
0x180004139  push    rbx
0x18000413a  sub     rsp, 30h
0x18000413e  mov     rbx, rdx
0x180004141  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180004146  mov     r8, rax
0x180004149  cmp     dword ptr [rax], 4
0x18000414c  jbe     short loc_180004198
0x18000414e  test    byte ptr [rax+10h], 2
0x180004152  jz      short loc_180004198
0x180004154  mov     rcx, [rax+18h]
0x180004158  and     ecx, 2
0x18000415b  cmp     rcx, [rax+18h]
0x18000415f  jnz     short loc_180004198
0x180004161  mov     rax, [rbx]
0x180004164  lea     rdx, unk_18002AB6C
0x18000416b  mov     [rsp+38h+arg_0], rax
0x180004170  mov     rcx, r8
0x180004173  lea     rax, aInitializeconf_20; "InitializeConfig_LastScanDecisionTime"
0x18000417a  mov     [rsp+38h+arg_10], rax
0x18000417f  lea     rax, [rsp+38h+arg_0]
0x180004184  mov     [rsp+38h+var_10], rax
0x180004189  lea     rax, [rsp+38h+arg_10]
0x18000418e  mov     [rsp+38h+var_18], rax
0x180004193  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180004198  add     rsp, 30h
0x18000419c  pop     rbx
0x18000419d  retn
```
