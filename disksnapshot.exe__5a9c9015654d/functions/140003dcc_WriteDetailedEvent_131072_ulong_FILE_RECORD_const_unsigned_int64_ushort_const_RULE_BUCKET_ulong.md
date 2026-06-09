# WriteDetailedEvent<131072>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140003dcc`
- end: `0x140003eb3`
- name: `??$WriteDetailedEvent@$0CAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140003dcc`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<131072>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x20000) != 0 )
    {
      result = qword_140014018 & 0x20000;
      if ( (qword_140014018 & 0x20000) == qword_140014018 )
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
                 (__int64)byte_140010C33,
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
0x140003dcc  push    rbp
0x140003dce  lea     rbp, [rsp-47h]
0x140003dd3  sub     rsp, 0A0h
0x140003dda  mov     eax, cs:dword_140014000
0x140003de0  mov     r11d, ecx
0x140003de3  cmp     eax, 5
0x140003de6  jbe     loc_140003EAA
0x140003dec  mov     r10, cs:qword_140014018
0x140003df3  mov     ecx, 20000h
0x140003df8  mov     rax, cs:qword_140014010
0x140003dff  test    rcx, rax
0x140003e02  jz      loc_140003EAA
0x140003e08  mov     rax, r10
0x140003e0b  and     rax, rcx
0x140003e0e  cmp     rax, r10
0x140003e11  jnz     loc_140003EAA
0x140003e17  mov     rax, [rdx+10h]
0x140003e1b  mov     [rbp+47h+var_38], rax
0x140003e1f  mov     eax, [rbp+47h+arg_28]
0x140003e22  mov     [rbp+47h+var_40], eax
0x140003e25  mov     rax, [rbp+47h+arg_20]
0x140003e29  mov     rcx, [rax+20h]
0x140003e2d  cmp     qword ptr [rcx+18h], 7
0x140003e32  jbe     short loc_140003E37
0x140003e34  mov     rcx, [rcx]
0x140003e37  mov     rax, [rdx+8]
0x140003e3b  mov     [rbp+47h+var_20], rax
0x140003e3f  mov     rax, [rdx]
0x140003e42  lea     rdx, byte_140010C33
0x140003e49  mov     [rbp+47h+var_10], rax
0x140003e4d  lea     rax, [rbp+47h+var_38]
0x140003e51  mov     [rsp+0A0h+var_48], rax
0x140003e56  lea     rax, [rbp+47h+var_40]
0x140003e5a  mov     [rsp+0A0h+var_50], rax
0x140003e5f  lea     rax, [rbp+47h+var_30]
0x140003e63  mov     [rsp+0A0h+var_58], rax
0x140003e68  lea     rax, [rbp+47h+var_28]
0x140003e6c  mov     [rsp+0A0h+var_60], rax
0x140003e71  lea     rax, [rbp+47h+var_20]
0x140003e75  mov     [rsp+0A0h+var_68], rax
0x140003e7a  lea     rax, [rbp+47h+var_18]
0x140003e7e  mov     [rsp+0A0h+var_70], rax
0x140003e83  lea     rax, [rbp+47h+var_10]
0x140003e87  mov     [rsp+0A0h+var_78], rax
0x140003e8c  lea     rax, [rbp+47h+var_3C]
0x140003e90  mov     [rsp+0A0h+var_80], rax
0x140003e95  mov     [rbp+47h+var_30], rcx
0x140003e99  mov     [rbp+47h+var_28], r9
0x140003e9d  mov     [rbp+47h+var_18], r8
0x140003ea1  mov     [rbp+47h+var_3C], r11d
0x140003ea5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140003eaa  add     rsp, 0A0h
0x140003eb1  pop     rbp
0x140003eb2  retn
```
