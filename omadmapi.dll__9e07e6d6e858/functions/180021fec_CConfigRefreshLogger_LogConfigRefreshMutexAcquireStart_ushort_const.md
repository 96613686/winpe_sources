# CConfigRefreshLogger::LogConfigRefreshMutexAcquireStart(ushort const *)

- ea: `0x180021fec`
- end: `0x180022064`
- name: `?LogConfigRefreshMutexAcquireStart@CConfigRefreshLogger@@QEAAXPEBG@Z`
- size: `120`
- prototype: `void __fastcall(CConfigRefreshLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b090`

## callees

- `0x1800011f8`
- `0x180021fec`

## pseudocode

```c
void __fastcall CConfigRefreshLogger::LogConfigRefreshMutexAcquireStart(
        CConfigRefreshLogger *this,
        const unsigned __int16 *a2)
{
  __int64 v2[3]; // [rsp+40h] [rbp-18h] BYREF
  const unsigned __int16 *v3; // [rsp+70h] [rbp+18h] BYREF
  __int64 *v4; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180032098 > 5
    && (qword_1800320A8 & 0x400000000000LL) != 0
    && (qword_1800320B0 & 0x400000000000LL) == qword_1800320B0 )
  {
    v4 = (__int64 *)a2;
    v3 = (const unsigned __int16 *)((char *)this + 16);
    v2[0] = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)&word_18002B55E,
      qword_1800320B0,
      0x400000000000LL,
      (__int64)v2,
      &v4,
      &v3);
  }
}

```

## disassembly

```asm
0x180021fec  mov     r11, rsp
0x180021fef  sub     rsp, 58h
0x180021ff3  mov     eax, cs:dword_180032098
0x180021ff9  cmp     eax, 5
0x180021ffc  jbe     short loc_18002205E
0x180021ffe  mov     r8, cs:qword_1800320B0
0x180022005  mov     r9, 400000000000h
0x18002200f  mov     rax, cs:qword_1800320A8
0x180022016  test    r9, rax
0x180022019  jz      short loc_18002205E
0x18002201b  mov     rax, r8
0x18002201e  and     rax, r9
0x180022021  cmp     rax, r8
0x180022024  jnz     short loc_18002205E
0x180022026  lea     rax, [rcx+10h]
0x18002202a  mov     [r11+20h], rdx
0x18002202e  mov     [r11+18h], rax
0x180022032  lea     rdx, word_18002B55E
0x180022039  lea     rax, [r11+18h]
0x18002203d  mov     qword ptr [r11-18h], 2000000h
0x180022045  mov     [r11-28h], rax
0x180022049  lea     rax, [r11+20h]
0x18002204d  mov     [r11-30h], rax
0x180022051  lea     rax, [r11-18h]
0x180022055  mov     [r11-38h], rax
0x180022059  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x18002205e  add     rsp, 58h
0x180022062  retn
```
