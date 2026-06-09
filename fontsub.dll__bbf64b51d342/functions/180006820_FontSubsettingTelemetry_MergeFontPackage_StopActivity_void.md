# FontSubsettingTelemetry::MergeFontPackage::StopActivity(void)

- ea: `0x180006820`
- end: `0x180006a4c`
- name: `?StopActivity@MergeFontPackage@FontSubsettingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontSubsettingTelemetry::MergeFontPackage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001010`
- `0x180001978`
- `0x180004c64`
- `0x1800055ac`
- `0x180006820`
- `0x1800073d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800069ed`
- `KERNEL32!GetCurrentThreadId` at `0x1800069ed`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::MergeFontPackage::StopActivity(
        FontSubsettingTelemetry::MergeFontPackage *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v30; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = FontSubsettingTelemetryProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v30 = v4[17];
      v31 = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&dword_18001E73C,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = FontSubsettingTelemetryProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_18001DDA1,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x180006820  push    rbp
0x180006822  push    rbx
0x180006823  push    rdi
0x180006824  lea     rbp, [rsp+10h]
0x180006829  sub     rsp, 130h
0x180006830  mov     rdi, [rcx+110h]
0x180006837  mov     rbx, rcx
0x18000683a  mov     eax, [rdi+48h]
0x18000683d  test    eax, eax
0x18000683f  jns     loc_1800069D9
0x180006845  add     rdi, 50h ; 'P'
0x180006849  cmp     eax, [rdi+8]
0x18000684c  jnz     loc_1800069D9
0x180006852  test    rdi, rdi
0x180006855  jz      loc_1800069D9
0x18000685b  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180006860  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180006865  mov     r9, rax
0x180006868  mov     ecx, [rax]
0x18000686a  cmp     ecx, 5
0x18000686d  jbe     loc_180006A3A
0x180006873  mov     rax, [rdi+70h]
0x180006877  lea     rdx, dword_18001E73C
0x18000687e  mov     rcx, [rdi+30h]
0x180006882  mov     [rbp+var_60], rax
0x180006886  mov     eax, [rdi+68h]
0x180006889  mov     r8, [rbx+110h]
0x180006890  mov     dword ptr [rbp+arg_10], eax
0x180006893  add     r8, 8
0x180006897  mov     rax, [rdi+60h]
0x18000689b  mov     [rbp+var_58], rax
0x18000689f  mov     rax, [rdi+58h]
0x1800068a3  mov     [rbp+var_50], rax
0x1800068a7  mov     eax, [rdi+50h]
0x1800068aa  mov     [rbp+arg_18], eax
0x1800068ad  mov     rax, [rdi+48h]
0x1800068b1  mov     [rbp+var_48], rax
0x1800068b5  mov     eax, [rdi+20h]
0x1800068b8  mov     [rbp+var_80], eax
0x1800068bb  mov     rax, [rdi+18h]
0x1800068bf  mov     [rbp+var_40], rax
0x1800068c3  mov     eax, [rdi]
0x1800068c5  mov     [rbp+var_7C], eax
0x1800068c8  mov     rax, [rdi+80h]
0x1800068cf  mov     [rbp+var_38], rax
0x1800068d3  mov     eax, [rdi+40h]
0x1800068d6  mov     [rbp+var_78], eax
0x1800068d9  mov     rax, [rdi+38h]
0x1800068dd  mov     [rbp+var_30], rax
0x1800068e1  mov     eax, [rdi+8]
0x1800068e4  mov     [rbp+var_74], eax
0x1800068e7  lea     rax, [rbp+var_70]
0x1800068eb  mov     [rsp+140h+var_90], rax
0x1800068f3  lea     rax, [rbp+arg_0]
0x1800068f7  mov     [rsp+140h+var_98], rax
0x1800068ff  lea     rax, [rbp+arg_8]
0x180006903  mov     [rsp+140h+var_A0], rax
0x18000690b  lea     rax, [rbp+var_68]
0x18000690f  mov     [rsp+140h+var_A8], rax
0x180006917  lea     rax, [rbp+var_60]
0x18000691b  mov     [rsp+140h+var_B0], rax
0x180006923  lea     rax, [rbp+arg_10]
0x180006927  mov     [rsp+140h+var_B8], rax
0x18000692f  lea     rax, [rbp+var_58]
0x180006933  mov     [rsp+140h+var_C0], rax
0x18000693b  lea     rax, [rbp+var_50]
0x18000693f  mov     [rsp+140h+var_C8], rax
0x180006944  lea     rax, [rbp+arg_18]
0x180006948  mov     [rsp+140h+var_D0], rax
0x18000694d  lea     rax, [rbp+var_48]
0x180006951  mov     [rsp+140h+var_D8], rax
0x180006956  lea     rax, [rbp+var_80]
0x18000695a  mov     [rsp+140h+var_E0], rax
0x18000695f  lea     rax, [rbp+var_40]
0x180006963  mov     [rsp+140h+var_E8], rax
0x180006968  lea     rax, [rbp+var_7C]
0x18000696c  mov     [rsp+140h+var_F0], rax
0x180006971  lea     rax, [rbp+var_38]
0x180006975  mov     [rsp+140h+var_F8], rax
0x18000697a  lea     rax, [rbp+var_78]
0x18000697e  mov     [rsp+140h+var_100], rax
0x180006983  lea     rax, [rbp+var_30]
0x180006987  mov     [rsp+140h+var_108], rax
0x18000698c  lea     rax, [rbp+var_74]
0x180006990  mov     [rbp+var_70], rcx
0x180006994  mov     ecx, [rdi+44h]
0x180006997  mov     [rsp+140h+var_110], rax
0x18000699c  lea     rax, [rbp+var_28]
0x1800069a0  mov     [rbp+arg_0], ecx
0x1800069a3  mov     ecx, [rdi+10h]
0x1800069a6  mov     [rbp+arg_8], ecx
0x1800069a9  mov     rcx, [rdi+78h]
0x1800069ad  mov     [rsp+140h+var_118], rax
0x1800069b2  lea     rax, [rbp+var_20]
0x1800069b6  mov     [rbp+var_68], rcx
0x1800069ba  mov     rcx, r9
0x1800069bd  mov     [rsp+140h+var_120], rax
0x1800069c2  mov     [rbp+var_28], 1000000h
0x1800069ca  mov     [rbp+var_20], 0
0x1800069d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800069d7  jmp     short loc_180006A3A
0x1800069d9  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800069de  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x1800069e3  mov     rdi, rax
0x1800069e6  mov     ecx, [rax]
0x1800069e8  cmp     ecx, 5
0x1800069eb  jbe     short loc_180006A3A
0x1800069ed  call    cs:__imp_GetCurrentThreadId
0x1800069f3  mov     r8, [rbx+110h]
0x1800069fa  lea     rdx, byte_18001DDA1
0x180006a01  mov     [rbp+arg_0], eax
0x180006a04  lea     rax, [rbp+arg_0]
0x180006a08  mov     [rsp+140h+var_110], rax
0x180006a0d  lea     rax, [rbp+arg_8]
0x180006a11  mov     [rsp+140h+var_118], rax
0x180006a16  lea     rax, [rbp+arg_10]
0x180006a1a  mov     ecx, [r8+48h]
0x180006a1e  add     r8, 8
0x180006a22  mov     [rbp+arg_8], ecx
0x180006a25  mov     rcx, rdi
0x180006a28  mov     [rsp+140h+var_120], rax
0x180006a2d  mov     [rbp+arg_10], 0
0x180006a35  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006a3a  mov     rcx, rbx
0x180006a3d  add     rsp, 130h
0x180006a44  pop     rdi
0x180006a45  pop     rbx
0x180006a46  pop     rbp
0x180006a47  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
