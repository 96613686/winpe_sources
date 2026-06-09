# WriteDetailedEvent<536870912>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x14000409c`
- end: `0x140004183`
- name: `??$WriteDetailedEvent@$0CAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x14000409c`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<536870912>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x20000000) != 0 )
    {
      result = qword_140014018 & 0x20000000;
      if ( result == qword_140014018 )
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
                 (__int64)byte_140010EAB,
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
0x14000409c  push    rbp
0x14000409e  lea     rbp, [rsp-47h]
0x1400040a3  sub     rsp, 0A0h
0x1400040aa  mov     eax, cs:dword_140014000
0x1400040b0  mov     r11d, ecx
0x1400040b3  cmp     eax, 5
0x1400040b6  jbe     loc_14000417A
0x1400040bc  mov     r10, cs:qword_140014018
0x1400040c3  mov     ecx, 20000000h
0x1400040c8  mov     rax, cs:qword_140014010
0x1400040cf  test    rcx, rax
0x1400040d2  jz      loc_14000417A
0x1400040d8  mov     rax, r10
0x1400040db  and     rax, rcx
0x1400040de  cmp     rax, r10
0x1400040e1  jnz     loc_14000417A
0x1400040e7  mov     rax, [rdx+10h]
0x1400040eb  mov     [rbp+47h+var_38], rax
0x1400040ef  mov     eax, [rbp+47h+arg_28]
0x1400040f2  mov     [rbp+47h+var_40], eax
0x1400040f5  mov     rax, [rbp+47h+arg_20]
0x1400040f9  mov     rcx, [rax+20h]
0x1400040fd  cmp     qword ptr [rcx+18h], 7
0x140004102  jbe     short loc_140004107
0x140004104  mov     rcx, [rcx]
0x140004107  mov     rax, [rdx+8]
0x14000410b  mov     [rbp+47h+var_20], rax
0x14000410f  mov     rax, [rdx]
0x140004112  lea     rdx, byte_140010EAB
0x140004119  mov     [rbp+47h+var_10], rax
0x14000411d  lea     rax, [rbp+47h+var_38]
0x140004121  mov     [rsp+0A0h+var_48], rax
0x140004126  lea     rax, [rbp+47h+var_40]
0x14000412a  mov     [rsp+0A0h+var_50], rax
0x14000412f  lea     rax, [rbp+47h+var_30]
0x140004133  mov     [rsp+0A0h+var_58], rax
0x140004138  lea     rax, [rbp+47h+var_28]
0x14000413c  mov     [rsp+0A0h+var_60], rax
0x140004141  lea     rax, [rbp+47h+var_20]
0x140004145  mov     [rsp+0A0h+var_68], rax
0x14000414a  lea     rax, [rbp+47h+var_18]
0x14000414e  mov     [rsp+0A0h+var_70], rax
0x140004153  lea     rax, [rbp+47h+var_10]
0x140004157  mov     [rsp+0A0h+var_78], rax
0x14000415c  lea     rax, [rbp+47h+var_3C]
0x140004160  mov     [rsp+0A0h+var_80], rax
0x140004165  mov     [rbp+47h+var_30], rcx
0x140004169  mov     [rbp+47h+var_28], r9
0x14000416d  mov     [rbp+47h+var_18], r8
0x140004171  mov     [rbp+47h+var_3C], r11d
0x140004175  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000417a  add     rsp, 0A0h
0x140004181  pop     rbp
0x140004182  retn
```
