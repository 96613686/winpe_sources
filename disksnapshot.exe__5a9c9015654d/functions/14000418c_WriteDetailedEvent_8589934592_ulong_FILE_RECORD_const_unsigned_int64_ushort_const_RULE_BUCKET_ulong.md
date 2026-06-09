# WriteDetailedEvent<8589934592>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x14000418c`
- end: `0x140004278`
- name: `??$WriteDetailedEvent@$0CAAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `236`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x14000418c`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<8589934592>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
{
  __int64 result; // rax
  __int64 *v8; // rcx
  int v9; // [rsp+60h] [rbp+7h] BYREF
  int v10; // [rsp+64h] [rbp+Bh] BYREF
  __int64 v11; // [rsp+68h] [rbp+Fh] BYREF
  __int64 *v12; // [rsp+70h] [rbp+17h] BYREF
  __int64 *v13; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v14; // [rsp+80h] [rbp+27h] BYREF
  __int64 v15; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v16; // [rsp+90h] [rbp+37h] BYREF

  result = (unsigned int)dword_140014000;
  if ( (unsigned int)dword_140014000 > 5 )
  {
    result = qword_140014010;
    if ( (qword_140014010 & 0x200000000LL) != 0 )
    {
      result = qword_140014018 & 0x200000000LL;
      if ( (qword_140014018 & 0x200000000LL) == qword_140014018 )
      {
        v11 = a2[2];
        v9 = a6;
        v8 = *(__int64 **)(a5 + 32);
        if ( (unsigned __int64)v8[3] > 7 )
          v8 = (__int64 *)*v8;
        v14 = a2[1];
        v16 = *a2;
        v12 = v8;
        v13 = a4;
        v15 = a3;
        v10 = a1;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                 (__int64)v8,
                 (__int64)byte_140010E33,
                 a3,
                 (__int64)a4,
                 (__int64)&v10,
                 (__int64)&v16,
                 (__int64)&v15,
                 (__int64)&v14,
                 &v13,
                 &v12,
                 (__int64)&v9,
                 (__int64)&v11);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000418c  push    rbp
0x14000418e  lea     rbp, [rsp-47h]
0x140004193  sub     rsp, 0A0h
0x14000419a  mov     eax, cs:dword_140014000
0x1400041a0  mov     r11d, ecx
0x1400041a3  cmp     eax, 5
0x1400041a6  jbe     loc_14000426F
0x1400041ac  mov     r10, cs:qword_140014018
0x1400041b3  mov     rcx, 200000000h
0x1400041bd  mov     rax, cs:qword_140014010
0x1400041c4  test    rcx, rax
0x1400041c7  jz      loc_14000426F
0x1400041cd  mov     rax, r10
0x1400041d0  and     rax, rcx
0x1400041d3  cmp     rax, r10
0x1400041d6  jnz     loc_14000426F
0x1400041dc  mov     rax, [rdx+10h]
0x1400041e0  mov     [rbp+47h+var_38], rax
0x1400041e4  mov     eax, [rbp+47h+arg_28]
0x1400041e7  mov     [rbp+47h+var_40], eax
0x1400041ea  mov     rax, [rbp+47h+arg_20]
0x1400041ee  mov     rcx, [rax+20h]
0x1400041f2  cmp     qword ptr [rcx+18h], 7
0x1400041f7  jbe     short loc_1400041FC
0x1400041f9  mov     rcx, [rcx]
0x1400041fc  mov     rax, [rdx+8]
0x140004200  mov     [rbp+47h+var_20], rax
0x140004204  mov     rax, [rdx]
0x140004207  lea     rdx, byte_140010E33
0x14000420e  mov     [rbp+47h+var_10], rax
0x140004212  lea     rax, [rbp+47h+var_38]
0x140004216  mov     [rsp+0A0h+var_48], rax
0x14000421b  lea     rax, [rbp+47h+var_40]
0x14000421f  mov     [rsp+0A0h+var_50], rax
0x140004224  lea     rax, [rbp+47h+var_30]
0x140004228  mov     [rsp+0A0h+var_58], rax
0x14000422d  lea     rax, [rbp+47h+var_28]
0x140004231  mov     [rsp+0A0h+var_60], rax
0x140004236  lea     rax, [rbp+47h+var_20]
0x14000423a  mov     [rsp+0A0h+var_68], rax
0x14000423f  lea     rax, [rbp+47h+var_18]
0x140004243  mov     [rsp+0A0h+var_70], rax
0x140004248  lea     rax, [rbp+47h+var_10]
0x14000424c  mov     [rsp+0A0h+var_78], rax
0x140004251  lea     rax, [rbp+47h+var_3C]
0x140004255  mov     [rsp+0A0h+var_80], rax
0x14000425a  mov     [rbp+47h+var_30], rcx
0x14000425e  mov     [rbp+47h+var_28], r9
0x140004262  mov     [rbp+47h+var_18], r8
0x140004266  mov     [rbp+47h+var_3C], r11d
0x14000426a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000426f  add     rsp, 0A0h
0x140004276  pop     rbp
0x140004277  retn
```
