# DataSharingServiceTelemetry::DSSGetToken<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x1800037e0`
- end: `0x180003866`
- name: `??$DSSGetToken@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: `const struct _tlgProvider_t *__fastcall(int *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800075e0`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x1800037e0`
- `0x180005c54`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DataSharingServiceTelemetry::DSSGetToken<unsigned long,unsigned short const *>(
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
                                              (unsigned int)&word_1800258B6,
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
0x1800037e0  mov     [rsp+arg_0], rbx
0x1800037e5  push    rdi
0x1800037e6  sub     rsp, 50h
0x1800037ea  mov     rbx, rdx
0x1800037ed  mov     rdi, rcx
0x1800037f0  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x1800037f5  mov     r9, rax
0x1800037f8  mov     r8d, [rax]
0x1800037fb  cmp     r8d, 5
0x1800037ff  jbe     short loc_18000385B
0x180003801  mov     rdx, 200000000000h
0x18000380b  mov     rcx, rax
0x18000380e  call    _tlgKeywordOn
0x180003813  test    al, al
0x180003815  jz      short loc_18000385B
0x180003817  mov     eax, [rdi]
0x180003819  lea     rdx, word_1800258B6
0x180003820  mov     rcx, [rbx]
0x180003823  mov     [rsp+58h+arg_10], eax
0x180003827  lea     rax, [rsp+58h+arg_18]
0x18000382c  mov     [rsp+58h+var_28], rax
0x180003831  lea     rax, [rsp+58h+var_18]
0x180003836  mov     [rsp+58h+var_30], rax
0x18000383b  lea     rax, [rsp+58h+arg_10]
0x180003840  mov     [rsp+58h+var_18], rcx
0x180003845  mov     rcx, r9
0x180003848  mov     [rsp+58h+var_38], rax
0x18000384d  mov     [rsp+58h+arg_18], 1000000h
0x180003856  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18000385b  mov     rbx, [rsp+58h+arg_0]
0x180003860  add     rsp, 50h
0x180003864  pop     rdi
0x180003865  retn
```
