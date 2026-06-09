# DataSharingServiceTelemetry::DSSDelegate<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x180003754`
- end: `0x1800037da`
- name: `??$DSSDelegate@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007440`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x180003754`
- `0x180005c54`

## pseudocode

```c
int __fastcall DataSharingServiceTelemetry::DSSDelegate<unsigned long,unsigned short const *>(
        int *a1,
        const WCHAR **a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *v7; // rcx
  const WCHAR *v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v4 = DataSharingServiceProvider::Provider((__int64)a1);
  if ( *(_DWORD *)v4 > 5u )
  {
    LODWORD(v4) = tlgKeywordOn(v4, 0x200000000000LL);
    if ( (_BYTE)v4 )
    {
      v7 = *a2;
      v10 = *a1;
      v9 = v7;
      v11 = 0x1000000;
      LODWORD(v4) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                      v6,
                      (unsigned __int8 *)word_1800258F2,
                      v5,
                      v6,
                      (__int64)&v10,
                      &v9,
                      (__int64)&v11);
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180003754  mov     [rsp+arg_0], rbx
0x180003759  push    rdi
0x18000375a  sub     rsp, 50h
0x18000375e  mov     rbx, rdx
0x180003761  mov     rdi, rcx
0x180003764  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x180003769  mov     r9, rax
0x18000376c  mov     r8d, [rax]
0x18000376f  cmp     r8d, 5
0x180003773  jbe     short loc_1800037CF
0x180003775  mov     rdx, 200000000000h
0x18000377f  mov     rcx, rax
0x180003782  call    _tlgKeywordOn
0x180003787  test    al, al
0x180003789  jz      short loc_1800037CF
0x18000378b  mov     eax, [rdi]
0x18000378d  lea     rdx, word_1800258F2
0x180003794  mov     rcx, [rbx]
0x180003797  mov     [rsp+58h+arg_10], eax
0x18000379b  lea     rax, [rsp+58h+arg_18]
0x1800037a0  mov     [rsp+58h+var_28], rax
0x1800037a5  lea     rax, [rsp+58h+var_18]
0x1800037aa  mov     [rsp+58h+var_30], rax
0x1800037af  lea     rax, [rsp+58h+arg_10]
0x1800037b4  mov     [rsp+58h+var_18], rcx
0x1800037b9  mov     rcx, r9
0x1800037bc  mov     [rsp+58h+var_38], rax
0x1800037c1  mov     [rsp+58h+arg_18], 1000000h
0x1800037ca  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800037cf  mov     rbx, [rsp+58h+arg_0]
0x1800037d4  add     rsp, 50h
0x1800037d8  pop     rdi
0x1800037d9  retn
```
