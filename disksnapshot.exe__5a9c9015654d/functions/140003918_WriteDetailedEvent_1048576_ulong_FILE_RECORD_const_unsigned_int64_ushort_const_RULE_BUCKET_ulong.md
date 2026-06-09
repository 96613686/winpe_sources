# WriteDetailedEvent<1048576>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140003918`
- end: `0x1400039ff`
- name: `??$WriteDetailedEvent@$0BAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140003918`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<1048576>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x100000) != 0 )
    {
      result = qword_140014018 & 0x100000;
      if ( (qword_140014018 & 0x100000) == qword_140014018 )
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
                 (__int64)byte_140010DBB,
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
0x140003918  push    rbp
0x14000391a  lea     rbp, [rsp-47h]
0x14000391f  sub     rsp, 0A0h
0x140003926  mov     eax, cs:dword_140014000
0x14000392c  mov     r11d, ecx
0x14000392f  cmp     eax, 5
0x140003932  jbe     loc_1400039F6
0x140003938  mov     r10, cs:qword_140014018
0x14000393f  mov     ecx, 100000h
0x140003944  mov     rax, cs:qword_140014010
0x14000394b  test    rcx, rax
0x14000394e  jz      loc_1400039F6
0x140003954  mov     rax, r10
0x140003957  and     rax, rcx
0x14000395a  cmp     rax, r10
0x14000395d  jnz     loc_1400039F6
0x140003963  mov     rax, [rdx+10h]
0x140003967  mov     [rbp+47h+var_38], rax
0x14000396b  mov     eax, [rbp+47h+arg_28]
0x14000396e  mov     [rbp+47h+var_40], eax
0x140003971  mov     rax, [rbp+47h+arg_20]
0x140003975  mov     rcx, [rax+20h]
0x140003979  cmp     qword ptr [rcx+18h], 7
0x14000397e  jbe     short loc_140003983
0x140003980  mov     rcx, [rcx]
0x140003983  mov     rax, [rdx+8]
0x140003987  mov     [rbp+47h+var_20], rax
0x14000398b  mov     rax, [rdx]
0x14000398e  lea     rdx, byte_140010DBB
0x140003995  mov     [rbp+47h+var_10], rax
0x140003999  lea     rax, [rbp+47h+var_38]
0x14000399d  mov     [rsp+0A0h+var_48], rax
0x1400039a2  lea     rax, [rbp+47h+var_40]
0x1400039a6  mov     [rsp+0A0h+var_50], rax
0x1400039ab  lea     rax, [rbp+47h+var_30]
0x1400039af  mov     [rsp+0A0h+var_58], rax
0x1400039b4  lea     rax, [rbp+47h+var_28]
0x1400039b8  mov     [rsp+0A0h+var_60], rax
0x1400039bd  lea     rax, [rbp+47h+var_20]
0x1400039c1  mov     [rsp+0A0h+var_68], rax
0x1400039c6  lea     rax, [rbp+47h+var_18]
0x1400039ca  mov     [rsp+0A0h+var_70], rax
0x1400039cf  lea     rax, [rbp+47h+var_10]
0x1400039d3  mov     [rsp+0A0h+var_78], rax
0x1400039d8  lea     rax, [rbp+47h+var_3C]
0x1400039dc  mov     [rsp+0A0h+var_80], rax
0x1400039e1  mov     [rbp+47h+var_30], rcx
0x1400039e5  mov     [rbp+47h+var_28], r9
0x1400039e9  mov     [rbp+47h+var_18], r8
0x1400039ed  mov     [rbp+47h+var_3C], r11d
0x1400039f1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400039f6  add     rsp, 0A0h
0x1400039fd  pop     rbp
0x1400039fe  retn
```
