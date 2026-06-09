# TlgHelper::LogInfoFiletime<ushort const (&)[36],_FILETIME>(ushort const (&)[36],_FILETIME &&)

- ea: `0x18000404c`
- end: `0x1800040b7`
- name: `??$LogInfoFiletime@AEAY0CE@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CE@$$CBG$$QEAU_FILETIME@@@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000df2c`

## callees

- `0x180001224`
- `0x18000404c`
- `0x18000f144`

## string_xrefs

- `0x18000408b`: `InitializeConfig_MdSchedLastRunTime`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME>(
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
    v6 = L"InitializeConfig_MdSchedLastRunTime";
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
0x18000404c  mov     [rsp+arg_0], rcx
0x180004051  push    rbx
0x180004052  sub     rsp, 30h
0x180004056  mov     rbx, rdx
0x180004059  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000405e  mov     r8, rax
0x180004061  cmp     dword ptr [rax], 4
0x180004064  jbe     short loc_1800040B0
0x180004066  test    byte ptr [rax+10h], 2
0x18000406a  jz      short loc_1800040B0
0x18000406c  mov     rcx, [rax+18h]
0x180004070  and     ecx, 2
0x180004073  cmp     rcx, [rax+18h]
0x180004077  jnz     short loc_1800040B0
0x180004079  mov     rax, [rbx]
0x18000407c  lea     rdx, unk_18002AB6C
0x180004083  mov     [rsp+38h+arg_0], rax
0x180004088  mov     rcx, r8
0x18000408b  lea     rax, aInitializeconf_11; "InitializeConfig_MdSchedLastRunTime"
0x180004092  mov     [rsp+38h+arg_10], rax
0x180004097  lea     rax, [rsp+38h+arg_0]
0x18000409c  mov     [rsp+38h+var_10], rax
0x1800040a1  lea     rax, [rsp+38h+arg_10]
0x1800040a6  mov     [rsp+38h+var_18], rax
0x1800040ab  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800040b0  add     rsp, 30h
0x1800040b4  pop     rbx
0x1800040b5  retn
```
