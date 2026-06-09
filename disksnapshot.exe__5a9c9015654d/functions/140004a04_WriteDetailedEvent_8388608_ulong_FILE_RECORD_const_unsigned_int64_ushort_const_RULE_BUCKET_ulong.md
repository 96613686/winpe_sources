# WriteDetailedEvent<8388608>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140004a04`
- end: `0x140004aeb`
- name: `??$WriteDetailedEvent@$0IAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140004a04`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<8388608>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x800000) != 0 )
    {
      result = qword_140014018 & 0x800000;
      if ( (qword_140014018 & 0x800000) == qword_140014018 )
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
                 (__int64)byte_140011013,
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
0x140004a04  push    rbp
0x140004a06  lea     rbp, [rsp-47h]
0x140004a0b  sub     rsp, 0A0h
0x140004a12  mov     eax, cs:dword_140014000
0x140004a18  mov     r11d, ecx
0x140004a1b  cmp     eax, 5
0x140004a1e  jbe     loc_140004AE2
0x140004a24  mov     r10, cs:qword_140014018
0x140004a2b  mov     ecx, 800000h
0x140004a30  mov     rax, cs:qword_140014010
0x140004a37  test    rcx, rax
0x140004a3a  jz      loc_140004AE2
0x140004a40  mov     rax, r10
0x140004a43  and     rax, rcx
0x140004a46  cmp     rax, r10
0x140004a49  jnz     loc_140004AE2
0x140004a4f  mov     rax, [rdx+10h]
0x140004a53  mov     [rbp+47h+var_38], rax
0x140004a57  mov     eax, [rbp+47h+arg_28]
0x140004a5a  mov     [rbp+47h+var_40], eax
0x140004a5d  mov     rax, [rbp+47h+arg_20]
0x140004a61  mov     rcx, [rax+20h]
0x140004a65  cmp     qword ptr [rcx+18h], 7
0x140004a6a  jbe     short loc_140004A6F
0x140004a6c  mov     rcx, [rcx]
0x140004a6f  mov     rax, [rdx+8]
0x140004a73  mov     [rbp+47h+var_20], rax
0x140004a77  mov     rax, [rdx]
0x140004a7a  lea     rdx, byte_140011013
0x140004a81  mov     [rbp+47h+var_10], rax
0x140004a85  lea     rax, [rbp+47h+var_38]
0x140004a89  mov     [rsp+0A0h+var_48], rax
0x140004a8e  lea     rax, [rbp+47h+var_40]
0x140004a92  mov     [rsp+0A0h+var_50], rax
0x140004a97  lea     rax, [rbp+47h+var_30]
0x140004a9b  mov     [rsp+0A0h+var_58], rax
0x140004aa0  lea     rax, [rbp+47h+var_28]
0x140004aa4  mov     [rsp+0A0h+var_60], rax
0x140004aa9  lea     rax, [rbp+47h+var_20]
0x140004aad  mov     [rsp+0A0h+var_68], rax
0x140004ab2  lea     rax, [rbp+47h+var_18]
0x140004ab6  mov     [rsp+0A0h+var_70], rax
0x140004abb  lea     rax, [rbp+47h+var_10]
0x140004abf  mov     [rsp+0A0h+var_78], rax
0x140004ac4  lea     rax, [rbp+47h+var_3C]
0x140004ac8  mov     [rsp+0A0h+var_80], rax
0x140004acd  mov     [rbp+47h+var_30], rcx
0x140004ad1  mov     [rbp+47h+var_28], r9
0x140004ad5  mov     [rbp+47h+var_18], r8
0x140004ad9  mov     [rbp+47h+var_3C], r11d
0x140004add  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140004ae2  add     rsp, 0A0h
0x140004ae9  pop     rbp
0x140004aea  retn
```
