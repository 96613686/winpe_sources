# WriteDetailedEvent<262144>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140004370`
- end: `0x140004457`
- name: `??$WriteDetailedEvent@$0EAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140004370`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<262144>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x40000) != 0 )
    {
      result = qword_140014018 & 0x40000;
      if ( (qword_140014018 & 0x40000) == qword_140014018 )
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
                 (__int64)&dword_14001095C,
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
0x140004370  push    rbp
0x140004372  lea     rbp, [rsp-47h]
0x140004377  sub     rsp, 0A0h
0x14000437e  mov     eax, cs:dword_140014000
0x140004384  mov     r11d, ecx
0x140004387  cmp     eax, 5
0x14000438a  jbe     loc_14000444E
0x140004390  mov     r10, cs:qword_140014018
0x140004397  mov     ecx, 40000h
0x14000439c  mov     rax, cs:qword_140014010
0x1400043a3  test    rcx, rax
0x1400043a6  jz      loc_14000444E
0x1400043ac  mov     rax, r10
0x1400043af  and     rax, rcx
0x1400043b2  cmp     rax, r10
0x1400043b5  jnz     loc_14000444E
0x1400043bb  mov     rax, [rdx+10h]
0x1400043bf  mov     [rbp+47h+var_38], rax
0x1400043c3  mov     eax, [rbp+47h+arg_28]
0x1400043c6  mov     [rbp+47h+var_40], eax
0x1400043c9  mov     rax, [rbp+47h+arg_20]
0x1400043cd  mov     rcx, [rax+20h]
0x1400043d1  cmp     qword ptr [rcx+18h], 7
0x1400043d6  jbe     short loc_1400043DB
0x1400043d8  mov     rcx, [rcx]
0x1400043db  mov     rax, [rdx+8]
0x1400043df  mov     [rbp+47h+var_20], rax
0x1400043e3  mov     rax, [rdx]
0x1400043e6  lea     rdx, dword_14001095C
0x1400043ed  mov     [rbp+47h+var_10], rax
0x1400043f1  lea     rax, [rbp+47h+var_38]
0x1400043f5  mov     [rsp+0A0h+var_48], rax
0x1400043fa  lea     rax, [rbp+47h+var_40]
0x1400043fe  mov     [rsp+0A0h+var_50], rax
0x140004403  lea     rax, [rbp+47h+var_30]
0x140004407  mov     [rsp+0A0h+var_58], rax
0x14000440c  lea     rax, [rbp+47h+var_28]
0x140004410  mov     [rsp+0A0h+var_60], rax
0x140004415  lea     rax, [rbp+47h+var_20]
0x140004419  mov     [rsp+0A0h+var_68], rax
0x14000441e  lea     rax, [rbp+47h+var_18]
0x140004422  mov     [rsp+0A0h+var_70], rax
0x140004427  lea     rax, [rbp+47h+var_10]
0x14000442b  mov     [rsp+0A0h+var_78], rax
0x140004430  lea     rax, [rbp+47h+var_3C]
0x140004434  mov     [rsp+0A0h+var_80], rax
0x140004439  mov     [rbp+47h+var_30], rcx
0x14000443d  mov     [rbp+47h+var_28], r9
0x140004441  mov     [rbp+47h+var_18], r8
0x140004445  mov     [rbp+47h+var_3C], r11d
0x140004449  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000444e  add     rsp, 0A0h
0x140004455  pop     rbp
0x140004456  retn
```
