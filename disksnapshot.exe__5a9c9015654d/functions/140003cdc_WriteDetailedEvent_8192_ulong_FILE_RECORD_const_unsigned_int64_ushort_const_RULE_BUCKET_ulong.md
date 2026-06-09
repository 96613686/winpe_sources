# WriteDetailedEvent<8192>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140003cdc`
- end: `0x140003dc3`
- name: `??$WriteDetailedEvent@$0CAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140003cdc`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<8192>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x2000) != 0 )
    {
      result = qword_140014018 & 0x2000;
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
                 (__int64)&dword_14001117C,
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
0x140003cdc  push    rbp
0x140003cde  lea     rbp, [rsp-47h]
0x140003ce3  sub     rsp, 0A0h
0x140003cea  mov     eax, cs:dword_140014000
0x140003cf0  mov     r11d, ecx
0x140003cf3  cmp     eax, 5
0x140003cf6  jbe     loc_140003DBA
0x140003cfc  mov     r10, cs:qword_140014018
0x140003d03  mov     ecx, 2000h
0x140003d08  mov     rax, cs:qword_140014010
0x140003d0f  test    rcx, rax
0x140003d12  jz      loc_140003DBA
0x140003d18  mov     rax, r10
0x140003d1b  and     rax, rcx
0x140003d1e  cmp     rax, r10
0x140003d21  jnz     loc_140003DBA
0x140003d27  mov     rax, [rdx+10h]
0x140003d2b  mov     [rbp+47h+var_38], rax
0x140003d2f  mov     eax, [rbp+47h+arg_28]
0x140003d32  mov     [rbp+47h+var_40], eax
0x140003d35  mov     rax, [rbp+47h+arg_20]
0x140003d39  mov     rcx, [rax+20h]
0x140003d3d  cmp     qword ptr [rcx+18h], 7
0x140003d42  jbe     short loc_140003D47
0x140003d44  mov     rcx, [rcx]
0x140003d47  mov     rax, [rdx+8]
0x140003d4b  mov     [rbp+47h+var_20], rax
0x140003d4f  mov     rax, [rdx]
0x140003d52  lea     rdx, dword_14001117C
0x140003d59  mov     [rbp+47h+var_10], rax
0x140003d5d  lea     rax, [rbp+47h+var_38]
0x140003d61  mov     [rsp+0A0h+var_48], rax
0x140003d66  lea     rax, [rbp+47h+var_40]
0x140003d6a  mov     [rsp+0A0h+var_50], rax
0x140003d6f  lea     rax, [rbp+47h+var_30]
0x140003d73  mov     [rsp+0A0h+var_58], rax
0x140003d78  lea     rax, [rbp+47h+var_28]
0x140003d7c  mov     [rsp+0A0h+var_60], rax
0x140003d81  lea     rax, [rbp+47h+var_20]
0x140003d85  mov     [rsp+0A0h+var_68], rax
0x140003d8a  lea     rax, [rbp+47h+var_18]
0x140003d8e  mov     [rsp+0A0h+var_70], rax
0x140003d93  lea     rax, [rbp+47h+var_10]
0x140003d97  mov     [rsp+0A0h+var_78], rax
0x140003d9c  lea     rax, [rbp+47h+var_3C]
0x140003da0  mov     [rsp+0A0h+var_80], rax
0x140003da5  mov     [rbp+47h+var_30], rcx
0x140003da9  mov     [rbp+47h+var_28], r9
0x140003dad  mov     [rbp+47h+var_18], r8
0x140003db1  mov     [rbp+47h+var_3C], r11d
0x140003db5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140003dba  add     rsp, 0A0h
0x140003dc1  pop     rbp
0x140003dc2  retn
```
