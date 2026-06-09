# WriteDetailedEvent<32768>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140004824`
- end: `0x14000490b`
- name: `??$WriteDetailedEvent@$0IAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140004824`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<32768>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x8000) != 0 )
    {
      result = (unsigned __int16)qword_140014018 & 0x8000;
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
                 (__int64)byte_140010B43,
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
0x140004824  push    rbp
0x140004826  lea     rbp, [rsp-47h]
0x14000482b  sub     rsp, 0A0h
0x140004832  mov     eax, cs:dword_140014000
0x140004838  mov     r11d, ecx
0x14000483b  cmp     eax, 5
0x14000483e  jbe     loc_140004902
0x140004844  mov     r10, cs:qword_140014018
0x14000484b  mov     ecx, 8000h
0x140004850  mov     rax, cs:qword_140014010
0x140004857  test    rcx, rax
0x14000485a  jz      loc_140004902
0x140004860  mov     rax, r10
0x140004863  and     rax, rcx
0x140004866  cmp     rax, r10
0x140004869  jnz     loc_140004902
0x14000486f  mov     rax, [rdx+10h]
0x140004873  mov     [rbp+47h+var_38], rax
0x140004877  mov     eax, [rbp+47h+arg_28]
0x14000487a  mov     [rbp+47h+var_40], eax
0x14000487d  mov     rax, [rbp+47h+arg_20]
0x140004881  mov     rcx, [rax+20h]
0x140004885  cmp     qword ptr [rcx+18h], 7
0x14000488a  jbe     short loc_14000488F
0x14000488c  mov     rcx, [rcx]
0x14000488f  mov     rax, [rdx+8]
0x140004893  mov     [rbp+47h+var_20], rax
0x140004897  mov     rax, [rdx]
0x14000489a  lea     rdx, byte_140010B43
0x1400048a1  mov     [rbp+47h+var_10], rax
0x1400048a5  lea     rax, [rbp+47h+var_38]
0x1400048a9  mov     [rsp+0A0h+var_48], rax
0x1400048ae  lea     rax, [rbp+47h+var_40]
0x1400048b2  mov     [rsp+0A0h+var_50], rax
0x1400048b7  lea     rax, [rbp+47h+var_30]
0x1400048bb  mov     [rsp+0A0h+var_58], rax
0x1400048c0  lea     rax, [rbp+47h+var_28]
0x1400048c4  mov     [rsp+0A0h+var_60], rax
0x1400048c9  lea     rax, [rbp+47h+var_20]
0x1400048cd  mov     [rsp+0A0h+var_68], rax
0x1400048d2  lea     rax, [rbp+47h+var_18]
0x1400048d6  mov     [rsp+0A0h+var_70], rax
0x1400048db  lea     rax, [rbp+47h+var_10]
0x1400048df  mov     [rsp+0A0h+var_78], rax
0x1400048e4  lea     rax, [rbp+47h+var_3C]
0x1400048e8  mov     [rsp+0A0h+var_80], rax
0x1400048ed  mov     [rbp+47h+var_30], rcx
0x1400048f1  mov     [rbp+47h+var_28], r9
0x1400048f5  mov     [rbp+47h+var_18], r8
0x1400048f9  mov     [rbp+47h+var_3C], r11d
0x1400048fd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140004902  add     rsp, 0A0h
0x140004909  pop     rbp
0x14000490a  retn
```
