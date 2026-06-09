# CConfigRefreshLogger::LogConfigRefreshMutexReleaseStart(void)

- ea: `0x180022160`
- end: `0x1800221cc`
- name: `?LogConfigRefreshMutexReleaseStart@CConfigRefreshLogger@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(CConfigRefreshLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800118a0`

## callees

- `0x180001150`
- `0x180022160`

## pseudocode

```c
void __fastcall CConfigRefreshLogger::LogConfigRefreshMutexReleaseStart(
        CConfigRefreshLogger *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // [rsp+48h] [rbp+10h] BYREF
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned int)dword_180032098 > 5
    && (qword_1800320A8 & 0x400000000000LL) != 0
    && (qword_1800320B0 & 0x400000000000LL) == qword_1800320B0 )
  {
    v5 = 0x2000000;
    v4 = (const unsigned __int16 *)((char *)this + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)byte_18002B515,
      0x400000000000LL,
      a4,
      (__int64)&v5,
      &v4);
  }
}

```

## disassembly

```asm
0x180022160  mov     r11, rsp
0x180022163  sub     rsp, 38h
0x180022167  mov     eax, cs:dword_180032098
0x18002216d  cmp     eax, 5
0x180022170  jbe     short loc_1800221C6
0x180022172  mov     rdx, cs:qword_1800320B0
0x180022179  mov     r8, 400000000000h
0x180022183  mov     rax, cs:qword_1800320A8
0x18002218a  test    r8, rax
0x18002218d  jz      short loc_1800221C6
0x18002218f  mov     rax, rdx
0x180022192  and     rax, r8
0x180022195  cmp     rax, rdx
0x180022198  jnz     short loc_1800221C6
0x18002219a  lea     rax, [rcx+10h]
0x18002219e  mov     qword ptr [r11+18h], 2000000h
0x1800221a6  mov     [r11+10h], rax
0x1800221aa  lea     rdx, byte_18002B515
0x1800221b1  lea     rax, [r11+10h]
0x1800221b5  mov     [r11-10h], rax
0x1800221b9  lea     rax, [r11+18h]
0x1800221bd  mov     [r11-18h], rax
0x1800221c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800221c6  add     rsp, 38h
0x1800221ca  retn
```
