# TlgHelper::LogInfoFiletime<ushort const (&)[36],_FILETIME>(ushort const (&)[36],_FILETIME &&)

- ea: `0x1800048ec`
- end: `0x18000495d`
- name: `??$LogInfoFiletime@AEAY0CE@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CE@$$CBG$$QEAU_FILETIME@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d77c`

## callees

- `0x180001220`
- `0x1800048ec`
- `0x18000e7ec`

## string_xrefs

- `0x180004932`: `InitializeConfig_MdSchedLastRunTime`

## pseudocode

```c
__int64 __fastcall TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME>(__int64 a1, __int64 *a2)
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
      v7 = L"InitializeConfig_MdSchedLastRunTime";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
               v5,
               (unsigned int)byte_18002A095,
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
0x1800048ec  mov     [rsp+arg_0], rcx
0x1800048f1  push    rbx
0x1800048f2  sub     rsp, 30h
0x1800048f6  mov     rbx, rdx
0x1800048f9  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800048fe  mov     r8, rax
0x180004901  mov     ecx, [rax]
0x180004903  cmp     ecx, 4
0x180004906  jbe     short loc_180004957
0x180004908  mov     rax, [rax+18h]
0x18000490c  mov     rcx, [r8+10h]
0x180004910  test    cl, 2
0x180004913  jz      short loc_180004957
0x180004915  mov     rcx, rax
0x180004918  and     ecx, 2
0x18000491b  cmp     rcx, rax
0x18000491e  jnz     short loc_180004957
0x180004920  mov     rax, [rbx]
0x180004923  lea     rdx, byte_18002A095
0x18000492a  mov     [rsp+38h+arg_0], rax
0x18000492f  mov     rcx, r8
0x180004932  lea     rax, aInitializeconf_11; "InitializeConfig_MdSchedLastRunTime"
0x180004939  mov     [rsp+38h+arg_10], rax
0x18000493e  lea     rax, [rsp+38h+arg_0]
0x180004943  mov     [rsp+38h+var_10], rax
0x180004948  lea     rax, [rsp+38h+arg_10]
0x18000494d  mov     [rsp+38h+var_18], rax
0x180004952  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180004957  add     rsp, 30h
0x18000495b  pop     rbx
0x18000495c  retn
```
