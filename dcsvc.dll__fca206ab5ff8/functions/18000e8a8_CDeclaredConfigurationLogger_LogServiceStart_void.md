# CDeclaredConfigurationLogger::LogServiceStart(void)

- ea: `0x18000e8a8`
- end: `0x18000e913`
- name: `?LogServiceStart@CDeclaredConfigurationLogger@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(CDeclaredConfigurationLogger *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800060b0`

## callees

- `0x18000113c`
- `0x18000e8a8`

## pseudocode

```c
void __fastcall CDeclaredConfigurationLogger::LogServiceStart(
        CDeclaredConfigurationLogger *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // [rsp+48h] [rbp+10h] BYREF
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned int)dword_18001B060 > 5
    && (qword_18001B070 & 0x400000000000LL) != 0
    && (qword_18001B078 & 0x400000000000LL) == qword_18001B078 )
  {
    v5 = 0x2000000;
    v4 = (const unsigned __int16 *)((char *)this + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)&dword_180017524,
      0x400000000000LL,
      a4,
      (__int64)&v5,
      &v4);
  }
}

```

## disassembly

```asm
0x18000e8a8  mov     r11, rsp
0x18000e8ab  sub     rsp, 38h
0x18000e8af  mov     eax, cs:dword_18001B060
0x18000e8b5  cmp     eax, 5
0x18000e8b8  jbe     short loc_18000E90E
0x18000e8ba  mov     rdx, cs:qword_18001B078
0x18000e8c1  mov     r8, 400000000000h
0x18000e8cb  mov     rax, cs:qword_18001B070
0x18000e8d2  test    r8, rax
0x18000e8d5  jz      short loc_18000E90E
0x18000e8d7  mov     rax, rdx
0x18000e8da  and     rax, r8
0x18000e8dd  cmp     rax, rdx
0x18000e8e0  jnz     short loc_18000E90E
0x18000e8e2  lea     rax, [rcx+10h]
0x18000e8e6  mov     qword ptr [r11+18h], 2000000h
0x18000e8ee  mov     [r11+10h], rax
0x18000e8f2  lea     rdx, dword_180017524
0x18000e8f9  lea     rax, [r11+10h]
0x18000e8fd  mov     [r11-10h], rax
0x18000e901  lea     rax, [r11+18h]
0x18000e905  mov     [r11-18h], rax
0x18000e909  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18000e90e  add     rsp, 38h
0x18000e912  retn
```
