# COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)

- ea: `0x14000bbbc`
- end: `0x14000bc9b`
- name: `?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z`
- size: `223`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000ef80`
- `0x140011ac8`

## callees

- `0x1400014a4`
- `0x14000bbbc`
- `0x14000cf44`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  char v5; // bl
  int v6; // edi
  __int64 *v7; // rsi
  int v8; // [rsp+50h] [rbp-30h] BYREF
  int v9; // [rsp+54h] [rbp-2Ch] BYREF
  const unsigned __int16 *v10; // [rsp+58h] [rbp-28h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v12; // [rsp+68h] [rbp-18h] BYREF
  __int64 v13; // [rsp+70h] [rbp-10h] BYREF

  v5 = a4;
  v6 = (int)a3;
  v7 = (__int64 *)a2;
  if ( (unsigned int)dword_140023000 > 5 )
  {
    LODWORD(a2) = 0;
    if ( (qword_140023010 & 0x400000000000LL) != 0 && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
    {
      v8 = a5;
      v10 = (const unsigned __int16 *)((char *)this + 16);
      v9 = a4;
      v11 = (__int64 *)a3;
      v12 = v7;
      v13 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)this,
        (unsigned __int8 *)word_14001DF0A,
        (__int64)a3,
        a4,
        (__int64)&v13,
        &v12,
        &v11,
        (__int64)&v9,
        (__int64)&v8,
        &v10);
    }
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    McTemplateU0zzqd_EventWriteTransfer((_DWORD)this, (_DWORD)a2, (_DWORD)v7, v6, v5, a5);
}

```

## disassembly

```asm
0x14000bbbc  mov     r11, rsp
0x14000bbbf  push    rbp
0x14000bbc0  push    rbx
0x14000bbc1  push    rsi
0x14000bbc2  push    rdi
0x14000bbc3  push    r14
0x14000bbc5  mov     rbp, rsp
0x14000bbc8  sub     rsp, 80h
0x14000bbcf  mov     eax, cs:dword_140023000
0x14000bbd5  mov     ebx, r9d
0x14000bbd8  mov     r14d, [rbp+arg_20]
0x14000bbdc  mov     rdi, r8
0x14000bbdf  mov     rsi, rdx
0x14000bbe2  cmp     eax, 5
0x14000bbe5  jbe     loc_14000BC6F
0x14000bbeb  mov     r10, cs:qword_140023018
0x14000bbf2  mov     rdx, 400000000000h
0x14000bbfc  mov     rax, cs:qword_140023010
0x14000bc03  test    rdx, rax
0x14000bc06  jz      short loc_14000BC6F
0x14000bc08  mov     rax, r10
0x14000bc0b  and     rax, rdx
0x14000bc0e  cmp     rax, r10
0x14000bc11  jnz     short loc_14000BC6F
0x14000bc13  lea     rax, [rcx+10h]
0x14000bc17  mov     [rbp+var_30], r14d
0x14000bc1b  mov     [rbp+var_28], rax
0x14000bc1f  lea     rdx, word_14001DF0A
0x14000bc26  lea     rax, [rbp+var_28]
0x14000bc2a  mov     [rbp+var_2C], ebx
0x14000bc2d  mov     [r11-60h], rax
0x14000bc31  lea     rax, [rbp+var_30]
0x14000bc35  mov     [r11-68h], rax
0x14000bc39  lea     rax, [rbp+var_2C]
0x14000bc3d  mov     [r11-70h], rax
0x14000bc41  lea     rax, [rbp+var_20]
0x14000bc45  mov     [r11-78h], rax
0x14000bc49  lea     rax, [rbp+var_18]
0x14000bc4d  mov     [r11-80h], rax
0x14000bc51  lea     rax, [rbp+var_10]
0x14000bc55  mov     [rsp+80h+var_60], rax
0x14000bc5a  mov     [rbp+var_20], r8
0x14000bc5e  mov     [rbp+var_18], rsi
0x14000bc62  mov     [rbp+var_10], 2000000h
0x14000bc6a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000bc6f  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000bc76  jz      short loc_14000BC8C
0x14000bc78  mov     [rsp+80h+var_58], r14d
0x14000bc7d  mov     r9, rdi
0x14000bc80  mov     r8, rsi
0x14000bc83  mov     dword ptr [rsp+80h+var_60], ebx
0x14000bc87  call    McTemplateU0zzqd_EventWriteTransfer
0x14000bc8c  add     rsp, 80h
0x14000bc93  pop     r14
0x14000bc95  pop     rdi
0x14000bc96  pop     rsi
0x14000bc97  pop     rbx
0x14000bc98  pop     rbp
0x14000bc99  retn
```
