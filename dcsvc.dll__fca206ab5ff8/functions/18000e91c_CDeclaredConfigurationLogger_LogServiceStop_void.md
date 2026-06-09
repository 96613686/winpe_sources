# CDeclaredConfigurationLogger::LogServiceStop(void)

- ea: `0x18000e91c`
- end: `0x18000e987`
- name: `?LogServiceStop@CDeclaredConfigurationLogger@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(CDeclaredConfigurationLogger *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000993c`

## callees

- `0x18000113c`
- `0x18000e91c`

## pseudocode

```c
void __fastcall CDeclaredConfigurationLogger::LogServiceStop(
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
      (__int64)byte_1800174E9,
      0x400000000000LL,
      a4,
      (__int64)&v5,
      &v4);
  }
}

```

## disassembly

```asm
0x18000e91c  mov     r11, rsp
0x18000e91f  sub     rsp, 38h
0x18000e923  mov     eax, cs:dword_18001B060
0x18000e929  cmp     eax, 5
0x18000e92c  jbe     short loc_18000E982
0x18000e92e  mov     rdx, cs:qword_18001B078
0x18000e935  mov     r8, 400000000000h
0x18000e93f  mov     rax, cs:qword_18001B070
0x18000e946  test    r8, rax
0x18000e949  jz      short loc_18000E982
0x18000e94b  mov     rax, rdx
0x18000e94e  and     rax, r8
0x18000e951  cmp     rax, rdx
0x18000e954  jnz     short loc_18000E982
0x18000e956  lea     rax, [rcx+10h]
0x18000e95a  mov     qword ptr [r11+18h], 2000000h
0x18000e962  mov     [r11+10h], rax
0x18000e966  lea     rdx, byte_1800174E9
0x18000e96d  lea     rax, [r11+10h]
0x18000e971  mov     [r11-10h], rax
0x18000e975  lea     rax, [r11+18h]
0x18000e979  mov     [r11-18h], rax
0x18000e97d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18000e982  add     rsp, 38h
0x18000e986  retn
```
