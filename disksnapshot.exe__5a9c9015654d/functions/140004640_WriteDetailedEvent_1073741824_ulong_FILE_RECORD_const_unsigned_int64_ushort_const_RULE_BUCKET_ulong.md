# WriteDetailedEvent<1073741824>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)

- ea: `0x140004640`
- end: `0x140004727`
- name: `??$WriteDetailedEvent@$0EAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z`
- size: `231`
- prototype: `__int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009834`

## callees

- `0x140001008`
- `0x140004640`

## pseudocode

```c
__int64 __fastcall WriteDetailedEvent<1073741824>(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
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
    if ( (qword_140014010 & 0x40000000) != 0 )
    {
      result = qword_140014018 & 0x40000000;
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
                 (__int64)byte_140010421,
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
0x140004640  push    rbp
0x140004642  lea     rbp, [rsp-47h]
0x140004647  sub     rsp, 0A0h
0x14000464e  mov     eax, cs:dword_140014000
0x140004654  mov     r11d, ecx
0x140004657  cmp     eax, 5
0x14000465a  jbe     loc_14000471E
0x140004660  mov     r10, cs:qword_140014018
0x140004667  mov     ecx, 40000000h
0x14000466c  mov     rax, cs:qword_140014010
0x140004673  test    rcx, rax
0x140004676  jz      loc_14000471E
0x14000467c  mov     rax, r10
0x14000467f  and     rax, rcx
0x140004682  cmp     rax, r10
0x140004685  jnz     loc_14000471E
0x14000468b  mov     rax, [rdx+10h]
0x14000468f  mov     [rbp+47h+var_38], rax
0x140004693  mov     eax, [rbp+47h+arg_28]
0x140004696  mov     [rbp+47h+var_40], eax
0x140004699  mov     rax, [rbp+47h+arg_20]
0x14000469d  mov     rcx, [rax+20h]
0x1400046a1  cmp     qword ptr [rcx+18h], 7
0x1400046a6  jbe     short loc_1400046AB
0x1400046a8  mov     rcx, [rcx]
0x1400046ab  mov     rax, [rdx+8]
0x1400046af  mov     [rbp+47h+var_20], rax
0x1400046b3  mov     rax, [rdx]
0x1400046b6  lea     rdx, byte_140010421
0x1400046bd  mov     [rbp+47h+var_10], rax
0x1400046c1  lea     rax, [rbp+47h+var_38]
0x1400046c5  mov     [rsp+0A0h+var_48], rax
0x1400046ca  lea     rax, [rbp+47h+var_40]
0x1400046ce  mov     [rsp+0A0h+var_50], rax
0x1400046d3  lea     rax, [rbp+47h+var_30]
0x1400046d7  mov     [rsp+0A0h+var_58], rax
0x1400046dc  lea     rax, [rbp+47h+var_28]
0x1400046e0  mov     [rsp+0A0h+var_60], rax
0x1400046e5  lea     rax, [rbp+47h+var_20]
0x1400046e9  mov     [rsp+0A0h+var_68], rax
0x1400046ee  lea     rax, [rbp+47h+var_18]
0x1400046f2  mov     [rsp+0A0h+var_70], rax
0x1400046f7  lea     rax, [rbp+47h+var_10]
0x1400046fb  mov     [rsp+0A0h+var_78], rax
0x140004700  lea     rax, [rbp+47h+var_3C]
0x140004704  mov     [rsp+0A0h+var_80], rax
0x140004709  mov     [rbp+47h+var_30], rcx
0x14000470d  mov     [rbp+47h+var_28], r9
0x140004711  mov     [rbp+47h+var_18], r8
0x140004715  mov     [rbp+47h+var_3C], r11d
0x140004719  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapSz@G@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapSz@G@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000471e  add     rsp, 0A0h
0x140004725  pop     rbp
0x140004726  retn
```
