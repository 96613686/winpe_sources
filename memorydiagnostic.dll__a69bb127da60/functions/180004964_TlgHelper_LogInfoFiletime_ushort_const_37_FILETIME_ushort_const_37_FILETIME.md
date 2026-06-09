# TlgHelper::LogInfoFiletime<ushort const (&)[37],_FILETIME>(ushort const (&)[37],_FILETIME &&)

- ea: `0x180004964`
- end: `0x1800049d5`
- name: `??$LogInfoFiletime@AEAY0CF@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CF@$$CBG$$QEAU_FILETIME@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d77c`

## callees

- `0x180001220`
- `0x180004964`
- `0x18000e7ec`

## string_xrefs

- `0x1800049aa`: `InitializeConfig_LastScanOfferedTime`

## pseudocode

```c
__int64 __fastcall TlgHelper::LogInfoFiletime<unsigned short const (&)[37],_FILETIME>(__int64 a1, __int64 *a2)
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
      v6 = *a2;
      v7 = L"InitializeConfig_LastScanOfferedTime";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
               v5,
               (unsigned int)&byte_18002A12F,
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
0x180004964  mov     [rsp+arg_0], rcx
0x180004969  push    rbx
0x18000496a  sub     rsp, 30h
0x18000496e  mov     rbx, rdx
0x180004971  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180004976  mov     r8, rax
0x180004979  mov     ecx, [rax]
0x18000497b  cmp     ecx, 4
0x18000497e  jbe     short loc_1800049CF
0x180004980  mov     rax, [rax+18h]
0x180004984  mov     rcx, [r8+10h]
0x180004988  test    cl, 2
0x18000498b  jz      short loc_1800049CF
0x18000498d  mov     rcx, rax
0x180004990  and     ecx, 2
0x180004993  cmp     rcx, rax
0x180004996  jnz     short loc_1800049CF
0x180004998  mov     rax, [rbx]
0x18000499b  lea     rdx, byte_18002A12F
0x1800049a2  mov     [rsp+38h+arg_0], rax
0x1800049a7  mov     rcx, r8
0x1800049aa  lea     rax, aInitializeconf_10; "InitializeConfig_LastScanOfferedTime"
0x1800049b1  mov     [rsp+38h+arg_10], rax
0x1800049b6  lea     rax, [rsp+38h+arg_0]
0x1800049bb  mov     [rsp+38h+var_10], rax
0x1800049c0  lea     rax, [rsp+38h+arg_10]
0x1800049c5  mov     [rsp+38h+var_18], rax
0x1800049ca  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800049cf  add     rsp, 30h
0x1800049d3  pop     rbx
0x1800049d4  retn
```
