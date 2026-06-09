# COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduled(ushort const *,ulong,long)

- ea: `0x14000baec`
- end: `0x14000bbb4`
- name: `?LogOmaDmPrcOmaDmSessionRetryScheduled@COmaDmPrcLogger@@QEAAXPEBGKJ@Z`
- size: `200`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012060`

## callees

- `0x1400016e8`
- `0x14000baec`
- `0x14000cddc`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduled(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl
  int v5; // edi
  __int64 *v6; // rsi
  int v7; // [rsp+50h] [rbp-28h] BYREF
  int v8; // [rsp+54h] [rbp-24h] BYREF
  const unsigned __int16 *v9; // [rsp+58h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+60h] [rbp-18h] BYREF
  __int64 v11; // [rsp+68h] [rbp-10h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = (__int64 *)a2;
  if ( (unsigned int)dword_140023000 > 5 )
  {
    LODWORD(a2) = 0;
    if ( (qword_140023010 & 0x400000000000LL) != 0 && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
    {
      v7 = a4;
      v9 = (const unsigned __int16 *)((char *)this + 16);
      v8 = a3;
      v10 = v6;
      v11 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)this,
        (unsigned __int8 *)&dword_14001E1CC,
        a3,
        a4,
        (__int64)&v11,
        &v10,
        (__int64)&v8,
        (__int64)&v7,
        &v9);
    }
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    McTemplateU0zqd_EventWriteTransfer((_DWORD)this, (_DWORD)a2, (_DWORD)v6, v5, v4);
}

```

## disassembly

```asm
0x14000baec  mov     r11, rsp
0x14000baef  mov     [r11+8], rbx
0x14000baf3  mov     [r11+10h], rsi
0x14000baf7  push    rdi
0x14000baf8  sub     rsp, 70h
0x14000bafc  mov     eax, cs:dword_140023000
0x14000bb02  mov     ebx, r9d
0x14000bb05  mov     edi, r8d
0x14000bb08  mov     rsi, rdx
0x14000bb0b  cmp     eax, 5
0x14000bb0e  jbe     short loc_14000BB89
0x14000bb10  mov     r10, cs:qword_140023018
0x14000bb17  mov     rdx, 400000000000h
0x14000bb21  mov     rax, cs:qword_140023010
0x14000bb28  test    rdx, rax
0x14000bb2b  jz      short loc_14000BB89
0x14000bb2d  mov     rax, r10
0x14000bb30  and     rax, rdx
0x14000bb33  cmp     rax, r10
0x14000bb36  jnz     short loc_14000BB89
0x14000bb38  lea     rax, [rcx+10h]
0x14000bb3c  mov     [rsp+78h+var_28], ebx
0x14000bb40  mov     [r11-20h], rax
0x14000bb44  lea     rdx, dword_14001E1CC
0x14000bb4b  lea     rax, [r11-20h]
0x14000bb4f  mov     [rsp+78h+var_24], r8d
0x14000bb54  mov     [r11-38h], rax
0x14000bb58  lea     rax, [r11-28h]
0x14000bb5c  mov     [r11-40h], rax
0x14000bb60  lea     rax, [r11-24h]
0x14000bb64  mov     [r11-48h], rax
0x14000bb68  lea     rax, [r11-18h]
0x14000bb6c  mov     [r11-50h], rax
0x14000bb70  lea     rax, [r11-10h]
0x14000bb74  mov     [r11-58h], rax
0x14000bb78  mov     [r11-18h], rsi
0x14000bb7c  mov     qword ptr [r11-10h], 2000000h
0x14000bb84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000bb89  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000bb90  jz      short loc_14000BBA1
0x14000bb92  mov     r9d, edi
0x14000bb95  mov     [rsp+78h+var_58], ebx
0x14000bb99  mov     r8, rsi
0x14000bb9c  call    McTemplateU0zqd_EventWriteTransfer
0x14000bba1  lea     r11, [rsp+78h+var_8]
0x14000bba6  mov     rbx, [r11+10h]
0x14000bbaa  mov     rsi, [r11+18h]
0x14000bbae  mov     rsp, r11
0x14000bbb1  pop     rdi
0x14000bbb2  retn
```
