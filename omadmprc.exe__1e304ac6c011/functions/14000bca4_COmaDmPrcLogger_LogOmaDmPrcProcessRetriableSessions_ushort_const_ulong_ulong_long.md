# COmaDmPrcLogger::LogOmaDmPrcProcessRetriableSessions(ushort const *,ulong,ulong,long)

- ea: `0x14000bca4`
- end: `0x14000bd8a`
- name: `?LogOmaDmPrcProcessRetriableSessions@COmaDmPrcLogger@@QEAAXPEBGKKJ@Z`
- size: `230`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400112f4`

## callees

- `0x1400015dc`
- `0x14000bca4`
- `0x14000ce84`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcProcessRetriableSessions(
        COmaDmPrcLogger *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  char v5; // bl
  int v6; // edi
  int v8; // [rsp+50h] [rbp-30h] BYREF
  int v9; // [rsp+54h] [rbp-2Ch] BYREF
  int v10; // [rsp+58h] [rbp-28h] BYREF
  const unsigned __int16 *v11; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v12; // [rsp+68h] [rbp-18h] BYREF
  __int64 v13; // [rsp+70h] [rbp-10h] BYREF

  v5 = a4;
  v6 = a3;
  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v8 = a5;
    v11 = (const unsigned __int16 *)((char *)this + 16);
    v9 = a4;
    v10 = a3;
    v12 = (__int64 *)a2;
    v13 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)this,
      (unsigned __int8 *)&word_14001DCBE,
      a3,
      a4,
      (__int64)&v13,
      &v12,
      (__int64)&v10,
      (__int64)&v9,
      (__int64)&v8,
      &v11);
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    McTemplateU0zqqd_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionRetryProcessed,
      a2,
      v6,
      v5,
      a5);
}

```

## disassembly

```asm
0x14000bca4  mov     r11, rsp
0x14000bca7  push    rbp
0x14000bca8  push    rbx
0x14000bca9  push    rsi
0x14000bcaa  push    rdi
0x14000bcab  push    r14
0x14000bcad  mov     rbp, rsp
0x14000bcb0  sub     rsp, 80h
0x14000bcb7  mov     eax, cs:dword_140023000
0x14000bcbd  mov     ebx, r9d
0x14000bcc0  mov     r14d, [rbp+arg_20]
0x14000bcc4  mov     edi, r8d
0x14000bcc7  mov     rsi, rdx
0x14000bcca  cmp     eax, 5
0x14000bccd  jbe     loc_14000BD57
0x14000bcd3  mov     r10, cs:qword_140023018
0x14000bcda  mov     rdx, 400000000000h
0x14000bce4  mov     rax, cs:qword_140023010
0x14000bceb  test    rdx, rax
0x14000bcee  jz      short loc_14000BD57
0x14000bcf0  mov     rax, r10
0x14000bcf3  and     rax, rdx
0x14000bcf6  cmp     rax, r10
0x14000bcf9  jnz     short loc_14000BD57
0x14000bcfb  lea     rax, [rcx+10h]
0x14000bcff  mov     [rbp+var_30], r14d
0x14000bd03  mov     [rbp+var_20], rax
0x14000bd07  lea     rdx, word_14001DCBE
0x14000bd0e  lea     rax, [rbp+var_20]
0x14000bd12  mov     [rbp+var_2C], ebx
0x14000bd15  mov     [r11-60h], rax
0x14000bd19  lea     rax, [rbp+var_30]
0x14000bd1d  mov     [r11-68h], rax
0x14000bd21  lea     rax, [rbp+var_2C]
0x14000bd25  mov     [r11-70h], rax
0x14000bd29  lea     rax, [rbp+var_28]
0x14000bd2d  mov     [r11-78h], rax
0x14000bd31  lea     rax, [rbp+var_18]
0x14000bd35  mov     [r11-80h], rax
0x14000bd39  lea     rax, [rbp+var_10]
0x14000bd3d  mov     [rsp+80h+var_60], rax
0x14000bd42  mov     [rbp+var_28], r8d
0x14000bd46  mov     [rbp+var_18], rsi
0x14000bd4a  mov     [rbp+var_10], 2000000h
0x14000bd52  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000bd57  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000bd5e  jz      short loc_14000BD7B
0x14000bd60  mov     [rsp+80h+var_58], r14d
0x14000bd65  lea     rdx, EnterpriseDiagnosticsOmaDmSessionRetryProcessed
0x14000bd6c  mov     r9d, edi
0x14000bd6f  mov     dword ptr [rsp+80h+var_60], ebx
0x14000bd73  mov     r8, rsi
0x14000bd76  call    McTemplateU0zqqd_EventWriteTransfer
0x14000bd7b  add     rsp, 80h
0x14000bd82  pop     r14
0x14000bd84  pop     rdi
0x14000bd85  pop     rsi
0x14000bd86  pop     rbx
0x14000bd87  pop     rbp
0x14000bd88  retn
```
