# COmaDmPrcLogger::LogOmaDmPrcDeleteRetriableSessions(ushort const *,ulong,ulong,long)

- ea: `0x14000b774`
- end: `0x14000b85a`
- name: `?LogOmaDmPrcDeleteRetriableSessions@COmaDmPrcLogger@@QEAAXPEBGKKJ@Z`
- size: `230`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f580`

## callees

- `0x1400015dc`
- `0x14000b774`
- `0x14000ce84`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcDeleteRetriableSessions(
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
      (unsigned __int8 *)byte_14001DD31,
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
      (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionRetryDeleted,
      a2,
      v6,
      v5,
      a5);
}

```

## disassembly

```asm
0x14000b774  mov     r11, rsp
0x14000b777  push    rbp
0x14000b778  push    rbx
0x14000b779  push    rsi
0x14000b77a  push    rdi
0x14000b77b  push    r14
0x14000b77d  mov     rbp, rsp
0x14000b780  sub     rsp, 80h
0x14000b787  mov     eax, cs:dword_140023000
0x14000b78d  mov     ebx, r9d
0x14000b790  mov     r14d, [rbp+arg_20]
0x14000b794  mov     edi, r8d
0x14000b797  mov     rsi, rdx
0x14000b79a  cmp     eax, 5
0x14000b79d  jbe     loc_14000B827
0x14000b7a3  mov     r10, cs:qword_140023018
0x14000b7aa  mov     rdx, 400000000000h
0x14000b7b4  mov     rax, cs:qword_140023010
0x14000b7bb  test    rdx, rax
0x14000b7be  jz      short loc_14000B827
0x14000b7c0  mov     rax, r10
0x14000b7c3  and     rax, rdx
0x14000b7c6  cmp     rax, r10
0x14000b7c9  jnz     short loc_14000B827
0x14000b7cb  lea     rax, [rcx+10h]
0x14000b7cf  mov     [rbp+var_30], r14d
0x14000b7d3  mov     [rbp+var_20], rax
0x14000b7d7  lea     rdx, byte_14001DD31
0x14000b7de  lea     rax, [rbp+var_20]
0x14000b7e2  mov     [rbp+var_2C], ebx
0x14000b7e5  mov     [r11-60h], rax
0x14000b7e9  lea     rax, [rbp+var_30]
0x14000b7ed  mov     [r11-68h], rax
0x14000b7f1  lea     rax, [rbp+var_2C]
0x14000b7f5  mov     [r11-70h], rax
0x14000b7f9  lea     rax, [rbp+var_28]
0x14000b7fd  mov     [r11-78h], rax
0x14000b801  lea     rax, [rbp+var_18]
0x14000b805  mov     [r11-80h], rax
0x14000b809  lea     rax, [rbp+var_10]
0x14000b80d  mov     [rsp+80h+var_60], rax
0x14000b812  mov     [rbp+var_28], r8d
0x14000b816  mov     [rbp+var_18], rsi
0x14000b81a  mov     [rbp+var_10], 2000000h
0x14000b822  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000b827  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000b82e  jz      short loc_14000B84B
0x14000b830  mov     [rsp+80h+var_58], r14d
0x14000b835  lea     rdx, EnterpriseDiagnosticsOmaDmSessionRetryDeleted
0x14000b83c  mov     r9d, edi
0x14000b83f  mov     dword ptr [rsp+80h+var_60], ebx
0x14000b843  mov     r8, rsi
0x14000b846  call    McTemplateU0zqqd_EventWriteTransfer
0x14000b84b  add     rsp, 80h
0x14000b852  pop     r14
0x14000b854  pop     rdi
0x14000b855  pop     rsi
0x14000b856  pop     rbx
0x14000b857  pop     rbp
0x14000b858  retn
```
