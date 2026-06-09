# TlgHelper::LogInfo<ushort const (&)[42],uint>(ushort const (&)[42],uint &&)

- ea: `0x1800046cc`
- end: `0x18000473b`
- name: `??$LogInfo@AEAY0CK@$$CBGI@TlgHelper@@SAXAEAY0CK@$$CBG$$QEAI@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d77c`

## callees

- `0x180001174`
- `0x1800046cc`
- `0x18000e7ec`

## string_xrefs

- `0x180004710`: `InitializeConfig_StoreCorruptionThreshold`

## pseudocode

```c
__int64 __fastcall TlgHelper::LogInfo<unsigned short const (&)[42],unsigned int>(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v4; // r9d
  __int64 v5; // r8
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v7; // [rsp+50h] [rbp+18h] BYREF

  v6 = a1;
  result = (__int64)TlgHelper::Provider();
  v5 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v5 + 16) & 2) != 0 && (result & 2) == result )
    {
      LODWORD(v6) = *a2;
      v7 = L"InitializeConfig_StoreCorruptionThreshold";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v5,
               (unsigned int)word_18002A382,
               v5,
               v4,
               (__int64)&v7,
               (__int64)&v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800046cc  mov     [rsp+arg_0], rcx
0x1800046d1  push    rbx
0x1800046d2  sub     rsp, 30h
0x1800046d6  mov     rbx, rdx
0x1800046d9  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800046de  mov     r8, rax
0x1800046e1  mov     ecx, [rax]
0x1800046e3  cmp     ecx, 4
0x1800046e6  jbe     short loc_180004735
0x1800046e8  mov     rax, [rax+18h]
0x1800046ec  mov     rcx, [r8+10h]
0x1800046f0  test    cl, 2
0x1800046f3  jz      short loc_180004735
0x1800046f5  mov     rcx, rax
0x1800046f8  and     ecx, 2
0x1800046fb  cmp     rcx, rax
0x1800046fe  jnz     short loc_180004735
0x180004700  mov     eax, [rbx]
0x180004702  lea     rdx, word_18002A382
0x180004709  mov     dword ptr [rsp+38h+arg_0], eax
0x18000470d  mov     rcx, r8
0x180004710  lea     rax, aInitializeconf_9; "InitializeConfig_StoreCorruptionThresho"...
0x180004717  mov     [rsp+38h+arg_10], rax
0x18000471c  lea     rax, [rsp+38h+arg_0]
0x180004721  mov     [rsp+38h+var_10], rax
0x180004726  lea     rax, [rsp+38h+arg_10]
0x18000472b  mov     [rsp+38h+var_18], rax
0x180004730  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180004735  add     rsp, 30h
0x180004739  pop     rbx
0x18000473a  retn
```
