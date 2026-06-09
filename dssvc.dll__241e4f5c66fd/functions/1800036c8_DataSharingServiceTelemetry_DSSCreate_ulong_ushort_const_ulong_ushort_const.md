# DataSharingServiceTelemetry::DSSCreate<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x1800036c8`
- end: `0x18000374e`
- name: `??$DSSCreate@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: `const struct _tlgProvider_t *__fastcall(int *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007300`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x1800036c8`
- `0x180005c54`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DataSharingServiceTelemetry::DSSCreate<unsigned long,unsigned short const *>(
        int *a1,
        __int64 *a2)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v5; // r8
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  result = DataSharingServiceProvider::Provider();
  v5 = *(unsigned int *)result;
  if ( (unsigned int)v5 > 5 )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x200000000000LL, v5, result);
    if ( (_BYTE)result )
    {
      v8 = *a2;
      v10 = *a1;
      v9[0] = v8;
      v11 = 0x1000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                                              v7,
                                              (unsigned int)&byte_1800256AF,
                                              v6,
                                              v7,
                                              (__int64)&v10,
                                              (__int64)v9,
                                              (__int64)&v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800036c8  mov     [rsp+arg_0], rbx
0x1800036cd  push    rdi
0x1800036ce  sub     rsp, 50h
0x1800036d2  mov     rbx, rdx
0x1800036d5  mov     rdi, rcx
0x1800036d8  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x1800036dd  mov     r9, rax
0x1800036e0  mov     r8d, [rax]
0x1800036e3  cmp     r8d, 5
0x1800036e7  jbe     short loc_180003743
0x1800036e9  mov     rdx, 200000000000h
0x1800036f3  mov     rcx, rax
0x1800036f6  call    _tlgKeywordOn
0x1800036fb  test    al, al
0x1800036fd  jz      short loc_180003743
0x1800036ff  mov     eax, [rdi]
0x180003701  lea     rdx, byte_1800256AF
0x180003708  mov     rcx, [rbx]
0x18000370b  mov     [rsp+58h+arg_10], eax
0x18000370f  lea     rax, [rsp+58h+arg_18]
0x180003714  mov     [rsp+58h+var_28], rax
0x180003719  lea     rax, [rsp+58h+var_18]
0x18000371e  mov     [rsp+58h+var_30], rax
0x180003723  lea     rax, [rsp+58h+arg_10]
0x180003728  mov     [rsp+58h+var_18], rcx
0x18000372d  mov     rcx, r9
0x180003730  mov     [rsp+58h+var_38], rax
0x180003735  mov     [rsp+58h+arg_18], 1000000h
0x18000373e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180003743  mov     rbx, [rsp+58h+arg_0]
0x180003748  add     rsp, 50h
0x18000374c  pop     rdi
0x18000374d  retn
```
