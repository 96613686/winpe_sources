# RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk(RdpDWMDirectWindowContext *,_DWMIndirectCompositionCreateVailSuperWetInkMetadata *)

- ea: `0x18000fff0`
- end: `0x1800103d1`
- name: `?ProcessCreateVailSuperWetInk@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionCreateVailSuperWetInkMetadata@@@Z`
- size: `993`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectCompositionCreateVailSuperWetInkMetadata *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180002b04`
- `0x18000dc04`
- `0x18000fff0`

## string_xrefs

- `0x18001004e`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010369`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001002a`: `No target window for the create vail super wet ink message.`
- `0x180010043`: `ProcessCreateVailSuperWetInk`
- `0x18001035e`: `ProcessCreateVailSuperWetInk`
- `0x18001011d`: `RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk`
- `0x18001024a`: `RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk per frame data`
- `0x180010345`: `Failed to send create vail super wet ink object message`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        struct _DWMIndirectCompositionCreateVailSuperWetInkMetadata *a3,
        __int64 a4)
{
  int VailSuperWetInk; // ebx
  char *v7; // rdx
  const char **v8; // rax
  const char **v10; // [rsp+30h] [rbp-99h]
  const unsigned __int16 **v11; // [rsp+40h] [rbp-89h]
  int v12; // [rsp+A0h] [rbp-29h] BYREF
  int v13; // [rsp+A4h] [rbp-25h] BYREF
  int v14; // [rsp+A8h] [rbp-21h] BYREF
  int v15; // [rsp+ACh] [rbp-1Dh] BYREF
  int v16; // [rsp+B0h] [rbp-19h] BYREF
  int v17; // [rsp+B4h] [rbp-15h] BYREF
  int v18; // [rsp+B8h] [rbp-11h] BYREF
  int v19; // [rsp+BCh] [rbp-Dh] BYREF
  const char *v20; // [rsp+C0h] [rbp-9h] BYREF
  const char *v21; // [rsp+C8h] [rbp-1h] BYREF
  const char *v22; // [rsp+D0h] [rbp+7h] BYREF
  const char *v23; // [rsp+D8h] [rbp+Fh] BYREF
  const unsigned __int16 *v24[8]; // [rsp+E0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+130h] [rbp+67h] BYREF
  int v26; // [rsp+138h] [rbp+6Fh] BYREF
  const char *v27; // [rsp+148h] [rbp+7Fh] BYREF

  v25 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v25) = *((_DWORD *)a3 + 6);
      v26 = *((_DWORD *)a3 + 5);
      LODWORD(v27) = *((_DWORD *)a3 + 4);
      v12 = *((unsigned __int8 *)a3 + 15);
      v13 = *((unsigned __int8 *)a3 + 14);
      v14 = *((unsigned __int8 *)a3 + 13);
      v15 = *((unsigned __int8 *)a3 + 12);
      v16 = *((unsigned __int8 *)a3 + 11);
      v17 = *((unsigned __int8 *)a3 + 10);
      v18 = *((unsigned __int8 *)a3 + 9);
      v19 = *((unsigned __int8 *)a3 + 8);
      LODWORD(v21) = *((unsigned __int16 *)a3 + 3);
      LODWORD(v22) = *((unsigned __int16 *)a3 + 2);
      LODWORD(v20) = *(_DWORD *)a3;
      v23 = (const char *)*((_QWORD *)a2 + 8);
      v24[0] = (const unsigned __int16 *)"RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        this,
        (__int64)&unk_18003A5C0,
        (__int64)a3,
        a4,
        v24,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25);
    }
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v25) = *((_DWORD *)a3 + 13);
      v26 = *((_DWORD *)a3 + 12);
      LODWORD(v27) = *((_DWORD *)a3 + 11);
      LODWORD(v20) = *((unsigned __int8 *)a3 + 43);
      LODWORD(v22) = *((unsigned __int8 *)a3 + 42);
      LODWORD(v21) = *((unsigned __int8 *)a3 + 41);
      v19 = *((unsigned __int8 *)a3 + 40);
      v18 = *((unsigned __int8 *)a3 + 39);
      v17 = *((unsigned __int8 *)a3 + 38);
      v16 = *((unsigned __int8 *)a3 + 37);
      v15 = *((unsigned __int8 *)a3 + 36);
      v14 = *((unsigned __int16 *)a3 + 17);
      v13 = *((unsigned __int16 *)a3 + 16);
      v12 = *((_DWORD *)a3 + 7);
      v24[0] = *((const unsigned __int16 **)a2 + 8);
      v23 = "RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk per frame data";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        this,
        (__int64)&dword_18003A16C,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v23,
        (__int64)v24,
        (__int64)&v12,
        (__int64)&v13,
        (__int64)&v14,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v17,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25);
    }
    VailSuperWetInk = RdpDWMDirectWindowContext::CreateVailSuperWetInk(
                        a2,
                        (const struct _GUID *)a3,
                        *((unsigned int *)a3 + 4),
                        *((unsigned int *)a3 + 5),
                        *((_DWORD *)a3 + 6),
                        (const struct _GUID *)((char *)a3 + 28),
                        *((_DWORD *)a3 + 11),
                        *((_DWORD *)a3 + 12),
                        *((_DWORD *)a3 + 13));
    if ( VailSuperWetInk < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v25) = 1111;
        v27 = "Failed to send create vail super wet ink object message";
        v7 = &byte_18003A11F;
        v24[0] = (const unsigned __int16 *)"ProcessCreateVailSuperWetInk";
        v23 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v20 = "Error HResult failed";
        v11 = v24;
        v10 = &v23;
        v8 = &v20;
        goto LABEL_11;
      }
    }
  }
  else
  {
    VailSuperWetInk = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v25) = 1058;
      v27 = "No target window for the create vail super wet ink message.";
      v7 = byte_18003A9E9;
      v20 = "ProcessCreateVailSuperWetInk";
      v22 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v21 = "Error condition failed";
      v11 = (const unsigned __int16 **)&v20;
      v10 = &v22;
      v8 = &v21;
LABEL_11:
      v26 = VailSuperWetInk;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v7,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)v8,
        (__int64)&v26,
        (const unsigned __int16 **)v10,
        (__int64)&v25,
        v11,
        (const unsigned __int16 **)&v27);
    }
  }
  return (unsigned int)VailSuperWetInk;
}

```

## disassembly

```asm
0x18000fff0  mov     [rsp-8+arg_0], rcx
0x18000fff5  push    rbp
0x18000fff6  push    rbx
0x18000fff7  push    rsi
0x18000fff8  push    rdi
0x18000fff9  push    r12
0x18000fffb  push    r14
0x18000fffd  push    r15
0x18000ffff  lea     rbp, [rsp-27h]
0x180010004  sub     rsp, 0F0h
0x18001000b  mov     eax, cs:dword_180044008
0x180010011  mov     rbx, r8
0x180010014  mov     r15, rdx
0x180010017  test    rdx, rdx
0x18001001a  jnz     short loc_18001009A
0x18001001c  mov     ebx, 8000FFFFh
0x180010021  cmp     eax, 2
0x180010024  jbe     loc_1800103BD
0x18001002a  lea     rax, aNoTargetWindow_5; "No target window for the create vail su"...
0x180010031  mov     dword ptr [rbp+57h+arg_0], 422h
0x180010038  mov     [rbp+57h+arg_18], rax
0x18001003c  lea     rdx, byte_18003A9E9
0x180010043  lea     rax, aProcesscreatev; "ProcessCreateVailSuperWetInk"
0x18001004a  mov     [rbp+57h+var_60], rax
0x18001004e  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010055  mov     [rbp+57h+var_50], rax
0x180010059  lea     rax, aErrorCondition; "Error condition failed"
0x180010060  mov     [rbp+57h+var_58], rax
0x180010064  lea     rax, [rbp+57h+arg_18]
0x180010068  mov     [rsp+120h+var_D8], rax
0x18001006d  lea     rax, [rbp+57h+var_60]
0x180010071  mov     qword ptr [rsp+120h+var_E0], rax
0x180010076  lea     rax, [rbp+57h+arg_0]
0x18001007a  mov     qword ptr [rsp+120h+var_E8], rax
0x18001007f  lea     rax, [rbp+57h+var_50]
0x180010083  mov     qword ptr [rsp+120h+var_F0], rax
0x180010088  lea     rax, [rbp+57h+arg_8]
0x18001008c  mov     [rsp+120h+var_F8], rax
0x180010091  lea     rax, [rbp+57h+var_58]
0x180010095  jmp     loc_1800103B0
0x18001009a  cmp     eax, 5
0x18001009d  jbe     loc_1800101C9
0x1800100a3  mov     eax, [r8+18h]
0x1800100a7  mov     dword ptr [rbp+57h+arg_0], eax
0x1800100aa  mov     eax, [r8+14h]
0x1800100ae  mov     [rbp+57h+arg_8], eax
0x1800100b1  mov     eax, [r8+10h]
0x1800100b5  mov     dword ptr [rbp+57h+arg_18], eax
0x1800100b8  movzx   eax, byte ptr [r8+0Fh]
0x1800100bd  mov     [rbp+57h+var_80], eax
0x1800100c0  movzx   eax, byte ptr [r8+0Eh]
0x1800100c5  mov     [rbp+57h+var_7C], eax
0x1800100c8  movzx   eax, byte ptr [r8+0Dh]
0x1800100cd  mov     [rbp+57h+var_78], eax
0x1800100d0  movzx   eax, byte ptr [r8+0Ch]
0x1800100d5  mov     [rbp+57h+var_74], eax
0x1800100d8  movzx   eax, byte ptr [r8+0Bh]
0x1800100dd  mov     [rbp+57h+var_70], eax
0x1800100e0  movzx   eax, byte ptr [r8+0Ah]
0x1800100e5  mov     [rbp+57h+var_6C], eax
0x1800100e8  movzx   eax, byte ptr [r8+9]
0x1800100ed  mov     [rbp+57h+var_68], eax
0x1800100f0  movzx   eax, byte ptr [r8+8]
0x1800100f5  mov     [rbp+57h+var_64], eax
0x1800100f8  movzx   eax, word ptr [r8+6]
0x1800100fd  mov     dword ptr [rbp+57h+var_58], eax
0x180010100  movzx   eax, word ptr [r8+4]
0x180010105  mov     dword ptr [rbp+57h+var_50], eax
0x180010108  mov     eax, [r8]
0x18001010b  mov     dword ptr [rbp+57h+var_60], eax
0x18001010e  mov     rax, [rdx+40h]
0x180010112  lea     rdx, unk_18003A5C0
0x180010119  mov     [rbp+57h+var_48], rax
0x18001011d  lea     rax, aRdsdwmdirectup_10; "RdsDWMDirectUpdateProcessor::ProcessCre"...
0x180010124  mov     [rbp+57h+var_40], rax
0x180010128  lea     rax, [rbp+57h+arg_0]
0x18001012c  mov     [rsp+120h+var_88], rax
0x180010134  lea     rax, [rbp+57h+arg_8]
0x180010138  mov     [rsp+120h+var_90], rax
0x180010140  lea     rax, [rbp+57h+arg_18]
0x180010144  mov     [rsp+120h+var_98], rax
0x18001014c  lea     rax, [rbp+57h+var_80]
0x180010150  mov     [rsp+120h+var_A0], rax
0x180010158  lea     rax, [rbp+57h+var_7C]
0x18001015c  mov     [rsp+120h+var_A8], rax
0x180010161  lea     rax, [rbp+57h+var_78]
0x180010165  mov     [rsp+120h+var_B0], rax
0x18001016a  lea     rax, [rbp+57h+var_74]
0x18001016e  mov     [rsp+120h+var_B8], rax
0x180010173  lea     rax, [rbp+57h+var_70]
0x180010177  mov     [rsp+120h+var_C0], rax
0x18001017c  lea     rax, [rbp+57h+var_6C]
0x180010180  mov     [rsp+120h+var_C8], rax
0x180010185  lea     rax, [rbp+57h+var_68]
0x180010189  mov     [rsp+120h+var_D0], rax
0x18001018e  lea     rax, [rbp+57h+var_64]
0x180010192  mov     [rsp+120h+var_D8], rax
0x180010197  lea     rax, [rbp+57h+var_58]
0x18001019b  mov     qword ptr [rsp+120h+var_E0], rax
0x1800101a0  lea     rax, [rbp+57h+var_50]
0x1800101a4  mov     qword ptr [rsp+120h+var_E8], rax
0x1800101a9  lea     rax, [rbp+57h+var_60]
0x1800101ad  mov     qword ptr [rsp+120h+var_F0], rax
0x1800101b2  lea     rax, [rbp+57h+var_48]
0x1800101b6  mov     [rsp+120h+var_F8], rax
0x1800101bb  lea     rax, [rbp+57h+var_40]
0x1800101bf  mov     qword ptr [rsp+120h+var_100], rax
0x1800101c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5555555555555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800101c9  mov     eax, cs:dword_180044008
0x1800101cf  cmp     eax, 5
0x1800101d2  jbe     loc_1800102F8
0x1800101d8  mov     eax, [rbx+34h]
0x1800101db  lea     r12, [rbx+1Ch]
0x1800101df  mov     dword ptr [rbp+57h+arg_0], eax
0x1800101e2  lea     rdx, dword_18003A16C
0x1800101e9  mov     eax, [rbx+30h]
0x1800101ec  mov     [rbp+57h+arg_8], eax
0x1800101ef  mov     eax, [rbx+2Ch]
0x1800101f2  mov     dword ptr [rbp+57h+arg_18], eax
0x1800101f5  movzx   eax, byte ptr [rbx+2Bh]
0x1800101f9  mov     dword ptr [rbp+57h+var_60], eax
0x1800101fc  movzx   eax, byte ptr [rbx+2Ah]
0x180010200  mov     dword ptr [rbp+57h+var_50], eax
0x180010203  movzx   eax, byte ptr [rbx+29h]
0x180010207  mov     dword ptr [rbp+57h+var_58], eax
0x18001020a  movzx   eax, byte ptr [rbx+28h]
0x18001020e  mov     [rbp+57h+var_64], eax
0x180010211  movzx   eax, byte ptr [rbx+27h]
0x180010215  mov     [rbp+57h+var_68], eax
0x180010218  movzx   eax, byte ptr [rbx+26h]
0x18001021c  mov     [rbp+57h+var_6C], eax
0x18001021f  movzx   eax, byte ptr [rbx+25h]
0x180010223  mov     [rbp+57h+var_70], eax
0x180010226  movzx   eax, byte ptr [rbx+24h]
0x18001022a  mov     [rbp+57h+var_74], eax
0x18001022d  movzx   eax, word ptr [rbx+22h]
0x180010231  mov     [rbp+57h+var_78], eax
0x180010234  movzx   eax, word ptr [rbx+20h]
0x180010238  mov     [rbp+57h+var_7C], eax
0x18001023b  mov     eax, [r12]
0x18001023f  mov     [rbp+57h+var_80], eax
0x180010242  mov     rax, [r15+40h]
0x180010246  mov     [rbp+57h+var_40], rax
0x18001024a  lea     rax, aRdsdwmdirectup_11; "RdsDWMDirectUpdateProcessor::ProcessCre"...
0x180010251  mov     [rbp+57h+var_48], rax
0x180010255  lea     rax, [rbp+57h+arg_0]
0x180010259  mov     [rsp+120h+var_88], rax
0x180010261  lea     rax, [rbp+57h+arg_8]
0x180010265  mov     [rsp+120h+var_90], rax
0x18001026d  lea     rax, [rbp+57h+arg_18]
0x180010271  mov     [rsp+120h+var_98], rax
0x180010279  lea     rax, [rbp+57h+var_60]
0x18001027d  mov     [rsp+120h+var_A0], rax
0x180010285  lea     rax, [rbp+57h+var_50]
0x180010289  mov     [rsp+120h+var_A8], rax
0x18001028e  lea     rax, [rbp+57h+var_58]
0x180010292  mov     [rsp+120h+var_B0], rax
0x180010297  lea     rax, [rbp+57h+var_64]
0x18001029b  mov     [rsp+120h+var_B8], rax
0x1800102a0  lea     rax, [rbp+57h+var_68]
0x1800102a4  mov     [rsp+120h+var_C0], rax
0x1800102a9  lea     rax, [rbp+57h+var_6C]
0x1800102ad  mov     [rsp+120h+var_C8], rax
0x1800102b2  lea     rax, [rbp+57h+var_70]
0x1800102b6  mov     [rsp+120h+var_D0], rax
0x1800102bb  lea     rax, [rbp+57h+var_74]
0x1800102bf  mov     [rsp+120h+var_D8], rax
0x1800102c4  lea     rax, [rbp+57h+var_78]
0x1800102c8  mov     qword ptr [rsp+120h+var_E0], rax
0x1800102cd  lea     rax, [rbp+57h+var_7C]
0x1800102d1  mov     qword ptr [rsp+120h+var_E8], rax
0x1800102d6  lea     rax, [rbp+57h+var_80]
0x1800102da  mov     qword ptr [rsp+120h+var_F0], rax
0x1800102df  lea     rax, [rbp+57h+var_40]
0x1800102e3  mov     [rsp+120h+var_F8], rax
0x1800102e8  lea     rax, [rbp+57h+var_48]
0x1800102ec  mov     qword ptr [rsp+120h+var_100], rax
0x1800102f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5555555555555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800102f6  jmp     short loc_1800102FC
0x1800102f8  lea     r12, [rbx+1Ch]
0x1800102fc  mov     eax, [rbx+34h]
0x1800102ff  mov     rdx, rbx; struct _GUID *
0x180010302  mov     r9d, [rbx+14h]; unsigned int
0x180010306  mov     rcx, r15; this
0x180010309  mov     r8d, [rbx+10h]; unsigned int
0x18001030d  mov     [rsp+120h+var_E0], eax; unsigned int
0x180010311  mov     eax, [rbx+30h]
0x180010314  mov     [rsp+120h+var_E8], eax; unsigned int
0x180010318  mov     eax, [rbx+2Ch]
0x18001031b  mov     [rsp+120h+var_F0], eax; unsigned int
0x18001031f  mov     eax, [rbx+18h]
0x180010322  mov     [rsp+120h+var_F8], r12; struct _GUID *
0x180010327  mov     [rsp+120h+var_100], eax; unsigned int
0x18001032b  call    ?CreateVailSuperWetInk@RdpDWMDirectWindowContext@@QEAAJAEBU_GUID@@III0III@Z; RdpDWMDirectWindowContext::CreateVailSuperWetInk(_GUID const &,uint,uint,uint,_GUID const &,uint,uint,uint)
0x180010330  mov     ebx, eax
0x180010332  test    eax, eax
0x180010334  jns     loc_1800103BD
0x18001033a  mov     ecx, cs:dword_180044008
0x180010340  cmp     ecx, 2
0x180010343  jbe     short loc_1800103BD
0x180010345  lea     rax, aFailedToSendCr; "Failed to send create vail super wet in"...
0x18001034c  mov     dword ptr [rbp+57h+arg_0], 457h
0x180010353  mov     [rbp+57h+arg_18], rax
0x180010357  lea     rdx, byte_18003A11F
0x18001035e  lea     rax, aProcesscreatev; "ProcessCreateVailSuperWetInk"
0x180010365  mov     [rbp+57h+var_40], rax
0x180010369  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010370  mov     [rbp+57h+var_48], rax
0x180010374  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001037b  mov     [rbp+57h+var_60], rax
0x18001037f  lea     rax, [rbp+57h+arg_18]
0x180010383  mov     [rsp+120h+var_D8], rax
0x180010388  lea     rax, [rbp+57h+var_40]
0x18001038c  mov     qword ptr [rsp+120h+var_E0], rax
0x180010391  lea     rax, [rbp+57h+arg_0]
0x180010395  mov     qword ptr [rsp+120h+var_E8], rax
0x18001039a  lea     rax, [rbp+57h+var_48]
0x18001039e  mov     qword ptr [rsp+120h+var_F0], rax
0x1800103a3  lea     rax, [rbp+57h+arg_8]
0x1800103a7  mov     [rsp+120h+var_F8], rax
0x1800103ac  lea     rax, [rbp+57h+var_60]
0x1800103b0  mov     qword ptr [rsp+120h+var_100], rax
0x1800103b5  mov     [rbp+57h+arg_8], ebx
0x1800103b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800103bd  mov     eax, ebx
0x1800103bf  add     rsp, 0F0h
0x1800103c6  pop     r15
0x1800103c8  pop     r14
0x1800103ca  pop     r12
0x1800103cc  pop     rdi
0x1800103cd  pop     rsi
0x1800103ce  pop     rbx
0x1800103cf  pop     rbp
0x1800103d0  retn
```
