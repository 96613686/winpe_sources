# DataSharingServiceTelemetry::DSSRemove<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x1800038f8`
- end: `0x18000397e`
- name: `??$DSSRemove@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: `const struct _tlgProvider_t *__fastcall(int *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007870`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x1800038f8`
- `0x180005c54`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DataSharingServiceTelemetry::DSSRemove<unsigned long,unsigned short const *>(
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
                                              (unsigned int)&dword_180025844,
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
0x1800038f8  mov     [rsp+arg_0], rbx
0x1800038fd  push    rdi
0x1800038fe  sub     rsp, 50h
0x180003902  mov     rbx, rdx
0x180003905  mov     rdi, rcx
0x180003908  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000390d  mov     r9, rax
0x180003910  mov     r8d, [rax]
0x180003913  cmp     r8d, 5
0x180003917  jbe     short loc_180003973
0x180003919  mov     rdx, 200000000000h
0x180003923  mov     rcx, rax
0x180003926  call    _tlgKeywordOn
0x18000392b  test    al, al
0x18000392d  jz      short loc_180003973
0x18000392f  mov     eax, [rdi]
0x180003931  lea     rdx, dword_180025844
0x180003938  mov     rcx, [rbx]
0x18000393b  mov     [rsp+58h+arg_10], eax
0x18000393f  lea     rax, [rsp+58h+arg_18]
0x180003944  mov     [rsp+58h+var_28], rax
0x180003949  lea     rax, [rsp+58h+var_18]
0x18000394e  mov     [rsp+58h+var_30], rax
0x180003953  lea     rax, [rsp+58h+arg_10]
0x180003958  mov     [rsp+58h+var_18], rcx
0x18000395d  mov     rcx, r9
0x180003960  mov     [rsp+58h+var_38], rax
0x180003965  mov     [rsp+58h+arg_18], 1000000h
0x18000396e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180003973  mov     rbx, [rsp+58h+arg_0]
0x180003978  add     rsp, 50h
0x18000397c  pop     rdi
0x18000397d  retn
```
