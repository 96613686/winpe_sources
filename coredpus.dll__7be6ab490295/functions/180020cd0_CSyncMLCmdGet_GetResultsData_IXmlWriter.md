# CSyncMLCmdGet::GetResultsData(IXmlWriter *)

- ea: `0x180020cd0`
- end: `0x180020d6b`
- name: `?GetResultsData@CSyncMLCmdGet@@UEAAJPEAUIXmlWriter@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(CSyncMLCmdGet *__hidden this, struct IXmlWriter *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800034d0`
- `0x1800043c0`
- `0x18000bf60`
- `0x18000e490`
- `0x180020cd0`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdGet::GetResultsData(CSyncMLCmdGet *this, struct IXmlWriter *a2, __int64 a3, __int64 a4)
{
  int ResultsDataGeneric; // ebx
  int v8; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    ResultsDataGeneric = CSyncMLCmd::GetResultsDataGeneric(this, a2);
    if ( ResultsDataGeneric >= 0
      && (int)CSyncMLCmd::GetCmdPreExecHresult(this) >= 0
      && (__int64)(*((_QWORD *)this + 22) - *((_QWORD *)this + 21)) >> 3 )
    {
      ResultsDataGeneric = CSyncMLCmdGet::CreateResultForGet(this, a2);
    }
  }
  else
  {
    ResultsDataGeneric = -2147467261;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v8 = ResultsDataGeneric;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&byte_180036C7F,
      a3,
      a4,
      (__int64)&v8);
  }
  return (unsigned int)ResultsDataGeneric;
}

```

## disassembly

```asm
0x180020cd0  mov     [rsp+arg_0], rbx
0x180020cd5  mov     [rsp+arg_10], rsi
0x180020cda  push    rdi
0x180020cdb  sub     rsp, 30h
0x180020cdf  mov     rsi, rdx
0x180020ce2  mov     rdi, rcx
0x180020ce5  test    rdx, rdx
0x180020ce8  jnz     short loc_180020CF1
0x180020cea  mov     ebx, 80004003h
0x180020cef  jmp     short loc_180020D2C
0x180020cf1  call    ?GetResultsDataGeneric@CSyncMLCmd@@IEBAJPEAUIXmlWriter@@@Z; CSyncMLCmd::GetResultsDataGeneric(IXmlWriter *)
0x180020cf6  mov     ebx, eax
0x180020cf8  test    eax, eax
0x180020cfa  js      short loc_180020D2C
0x180020cfc  mov     rcx, rdi; this
0x180020cff  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x180020d04  test    eax, eax
0x180020d06  js      short loc_180020D2C
0x180020d08  mov     rcx, [rdi+0B0h]
0x180020d0f  sub     rcx, [rdi+0A8h]
0x180020d16  sar     rcx, 3
0x180020d1a  test    rcx, rcx
0x180020d1d  jz      short loc_180020D2C
0x180020d1f  mov     rdx, rsi; struct IXmlWriter *
0x180020d22  mov     rcx, rdi; this
0x180020d25  call    ?CreateResultForGet@CSyncMLCmdGet@@AEBAJPEAUIXmlWriter@@@Z; CSyncMLCmdGet::CreateResultForGet(IXmlWriter *)
0x180020d2a  mov     ebx, eax
0x180020d2c  mov     eax, cs:dword_18003E048
0x180020d32  cmp     eax, 5
0x180020d35  jbe     short loc_180020D58
0x180020d37  lea     rax, [rsp+38h+arg_8]
0x180020d3c  mov     [rsp+38h+arg_8], ebx
0x180020d40  lea     rdx, byte_180036C7F
0x180020d47  mov     [rsp+38h+var_18], rax
0x180020d4c  lea     rcx, dword_18003E048
0x180020d53  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020d58  mov     rsi, [rsp+38h+arg_10]
0x180020d5d  mov     eax, ebx
0x180020d5f  mov     rbx, [rsp+38h+arg_0]
0x180020d64  add     rsp, 30h
0x180020d68  pop     rdi
0x180020d69  retn
```
