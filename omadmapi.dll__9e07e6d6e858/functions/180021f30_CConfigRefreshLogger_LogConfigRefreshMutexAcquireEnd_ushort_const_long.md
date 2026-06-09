# CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(ushort const *,long)

- ea: `0x180021f30`
- end: `0x180021fe4`
- name: `?LogConfigRefreshMutexAcquireEnd@CConfigRefreshLogger@@QEAAXPEBGJ@Z`
- size: `180`
- prototype: `void __fastcall(CConfigRefreshLogger *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b090`

## callees

- `0x1800012ec`
- `0x1800145f4`
- `0x180021f30`

## pseudocode

```c
void __fastcall CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(
        CConfigRefreshLogger *this,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4)
{
  __int64 *v6; // [rsp+40h] [rbp-18h] BYREF
  __int64 v7; // [rsp+48h] [rbp-10h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  const unsigned __int16 *v9; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180032098 > 5
    && (qword_1800320A8 & 0x400000000000LL) != 0
    && (qword_1800320B0 & 0x400000000000LL) == qword_1800320B0 )
  {
    v8 = a3;
    v9 = (const unsigned __int16 *)((char *)this + 16);
    v6 = (__int64 *)a2;
    v7 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)byte_18002B467,
      qword_1800320B0,
      a4,
      (__int64)&v7,
      &v6,
      (__int64)&v8,
      &v9);
  }
  if ( a3 < 0 && (byte_180032C41 & 2) != 0 )
    McTemplateU0zd_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)ConfigRefreshMutexAcquireFailure, a2, a3);
}

```

## disassembly

```asm
0x180021f30  mov     r11, rsp
0x180021f33  mov     [r11+8], rbx
0x180021f37  push    rdi
0x180021f38  sub     rsp, 50h
0x180021f3c  mov     eax, cs:dword_180032098
0x180021f42  mov     ebx, r8d
0x180021f45  mov     rdi, rdx
0x180021f48  cmp     eax, 5
0x180021f4b  jbe     short loc_180021FB9
0x180021f4d  mov     r8, cs:qword_1800320B0
0x180021f54  mov     rdx, 400000000000h
0x180021f5e  mov     rax, cs:qword_1800320A8
0x180021f65  test    rdx, rax
0x180021f68  jz      short loc_180021FB9
0x180021f6a  mov     rax, r8
0x180021f6d  and     rax, rdx
0x180021f70  cmp     rax, r8
0x180021f73  jnz     short loc_180021FB9
0x180021f75  lea     rax, [rcx+10h]
0x180021f79  mov     [rsp+58h+arg_10], ebx
0x180021f7d  mov     [r11+20h], rax
0x180021f81  lea     rdx, byte_18002B467
0x180021f88  lea     rax, [r11+20h]
0x180021f8c  mov     [r11-18h], rdi
0x180021f90  mov     [r11-20h], rax
0x180021f94  lea     rax, [r11+18h]
0x180021f98  mov     [r11-28h], rax
0x180021f9c  lea     rax, [r11-18h]
0x180021fa0  mov     [r11-30h], rax
0x180021fa4  lea     rax, [r11-10h]
0x180021fa8  mov     [r11-38h], rax
0x180021fac  mov     qword ptr [r11-10h], 2000000h
0x180021fb4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021fb9  test    ebx, ebx
0x180021fbb  jns     short loc_180021FD8
0x180021fbd  test    cs:byte_180032C41, 2
0x180021fc4  jz      short loc_180021FD8
0x180021fc6  mov     r9d, ebx
0x180021fc9  lea     rdx, ConfigRefreshMutexAcquireFailure
0x180021fd0  mov     r8, rdi
0x180021fd3  call    McTemplateU0zd_EventWriteTransfer
0x180021fd8  mov     rbx, [rsp+58h+arg_0]
0x180021fdd  add     rsp, 50h
0x180021fe1  pop     rdi
0x180021fe2  retn
```
