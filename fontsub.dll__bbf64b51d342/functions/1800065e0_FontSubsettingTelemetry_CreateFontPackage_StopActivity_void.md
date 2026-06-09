# FontSubsettingTelemetry::CreateFontPackage::StopActivity(void)

- ea: `0x1800065e0`
- end: `0x18000680c`
- name: `?StopActivity@CreateFontPackage@FontSubsettingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontSubsettingTelemetry::CreateFontPackage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001010`
- `0x180001978`
- `0x180004c64`
- `0x1800055ac`
- `0x1800065e0`
- `0x1800073d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800067ad`
- `KERNEL32!GetCurrentThreadId` at `0x1800067ad`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::CreateFontPackage::StopActivity(
        FontSubsettingTelemetry::CreateFontPackage *this)
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
        (unsigned int)&unk_18001E1A0,
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
        (unsigned int)byte_18001E373,
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
0x1800065e0  push    rbp
0x1800065e2  push    rbx
0x1800065e3  push    rdi
0x1800065e4  lea     rbp, [rsp+10h]
0x1800065e9  sub     rsp, 130h
0x1800065f0  mov     rdi, [rcx+110h]
0x1800065f7  mov     rbx, rcx
0x1800065fa  mov     eax, [rdi+48h]
0x1800065fd  test    eax, eax
0x1800065ff  jns     loc_180006799
0x180006605  add     rdi, 50h ; 'P'
0x180006609  cmp     eax, [rdi+8]
0x18000660c  jnz     loc_180006799
0x180006612  test    rdi, rdi
0x180006615  jz      loc_180006799
0x18000661b  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180006620  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180006625  mov     r9, rax
0x180006628  mov     ecx, [rax]
0x18000662a  cmp     ecx, 5
0x18000662d  jbe     loc_1800067FA
0x180006633  mov     rax, [rdi+70h]
0x180006637  lea     rdx, unk_18001E1A0
0x18000663e  mov     rcx, [rdi+30h]
0x180006642  mov     [rbp+var_60], rax
0x180006646  mov     eax, [rdi+68h]
0x180006649  mov     r8, [rbx+110h]
0x180006650  mov     dword ptr [rbp+arg_10], eax
0x180006653  add     r8, 8
0x180006657  mov     rax, [rdi+60h]
0x18000665b  mov     [rbp+var_58], rax
0x18000665f  mov     rax, [rdi+58h]
0x180006663  mov     [rbp+var_50], rax
0x180006667  mov     eax, [rdi+50h]
0x18000666a  mov     [rbp+arg_18], eax
0x18000666d  mov     rax, [rdi+48h]
0x180006671  mov     [rbp+var_48], rax
0x180006675  mov     eax, [rdi+20h]
0x180006678  mov     [rbp+var_80], eax
0x18000667b  mov     rax, [rdi+18h]
0x18000667f  mov     [rbp+var_40], rax
0x180006683  mov     eax, [rdi]
0x180006685  mov     [rbp+var_7C], eax
0x180006688  mov     rax, [rdi+80h]
0x18000668f  mov     [rbp+var_38], rax
0x180006693  mov     eax, [rdi+40h]
0x180006696  mov     [rbp+var_78], eax
0x180006699  mov     rax, [rdi+38h]
0x18000669d  mov     [rbp+var_30], rax
0x1800066a1  mov     eax, [rdi+8]
0x1800066a4  mov     [rbp+var_74], eax
0x1800066a7  lea     rax, [rbp+var_70]
0x1800066ab  mov     [rsp+140h+var_90], rax
0x1800066b3  lea     rax, [rbp+arg_0]
0x1800066b7  mov     [rsp+140h+var_98], rax
0x1800066bf  lea     rax, [rbp+arg_8]
0x1800066c3  mov     [rsp+140h+var_A0], rax
0x1800066cb  lea     rax, [rbp+var_68]
0x1800066cf  mov     [rsp+140h+var_A8], rax
0x1800066d7  lea     rax, [rbp+var_60]
0x1800066db  mov     [rsp+140h+var_B0], rax
0x1800066e3  lea     rax, [rbp+arg_10]
0x1800066e7  mov     [rsp+140h+var_B8], rax
0x1800066ef  lea     rax, [rbp+var_58]
0x1800066f3  mov     [rsp+140h+var_C0], rax
0x1800066fb  lea     rax, [rbp+var_50]
0x1800066ff  mov     [rsp+140h+var_C8], rax
0x180006704  lea     rax, [rbp+arg_18]
0x180006708  mov     [rsp+140h+var_D0], rax
0x18000670d  lea     rax, [rbp+var_48]
0x180006711  mov     [rsp+140h+var_D8], rax
0x180006716  lea     rax, [rbp+var_80]
0x18000671a  mov     [rsp+140h+var_E0], rax
0x18000671f  lea     rax, [rbp+var_40]
0x180006723  mov     [rsp+140h+var_E8], rax
0x180006728  lea     rax, [rbp+var_7C]
0x18000672c  mov     [rsp+140h+var_F0], rax
0x180006731  lea     rax, [rbp+var_38]
0x180006735  mov     [rsp+140h+var_F8], rax
0x18000673a  lea     rax, [rbp+var_78]
0x18000673e  mov     [rsp+140h+var_100], rax
0x180006743  lea     rax, [rbp+var_30]
0x180006747  mov     [rsp+140h+var_108], rax
0x18000674c  lea     rax, [rbp+var_74]
0x180006750  mov     [rbp+var_70], rcx
0x180006754  mov     ecx, [rdi+44h]
0x180006757  mov     [rsp+140h+var_110], rax
0x18000675c  lea     rax, [rbp+var_28]
0x180006760  mov     [rbp+arg_0], ecx
0x180006763  mov     ecx, [rdi+10h]
0x180006766  mov     [rbp+arg_8], ecx
0x180006769  mov     rcx, [rdi+78h]
0x18000676d  mov     [rsp+140h+var_118], rax
0x180006772  lea     rax, [rbp+var_20]
0x180006776  mov     [rbp+var_68], rcx
0x18000677a  mov     rcx, r9
0x18000677d  mov     [rsp+140h+var_120], rax
0x180006782  mov     [rbp+var_28], 1000000h
0x18000678a  mov     [rbp+var_20], 0
0x180006792  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180006797  jmp     short loc_1800067FA
0x180006799  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000679e  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x1800067a3  mov     rdi, rax
0x1800067a6  mov     ecx, [rax]
0x1800067a8  cmp     ecx, 5
0x1800067ab  jbe     short loc_1800067FA
0x1800067ad  call    cs:__imp_GetCurrentThreadId
0x1800067b3  mov     r8, [rbx+110h]
0x1800067ba  lea     rdx, byte_18001E373
0x1800067c1  mov     [rbp+arg_0], eax
0x1800067c4  lea     rax, [rbp+arg_0]
0x1800067c8  mov     [rsp+140h+var_110], rax
0x1800067cd  lea     rax, [rbp+arg_8]
0x1800067d1  mov     [rsp+140h+var_118], rax
0x1800067d6  lea     rax, [rbp+arg_10]
0x1800067da  mov     ecx, [r8+48h]
0x1800067de  add     r8, 8
0x1800067e2  mov     [rbp+arg_8], ecx
0x1800067e5  mov     rcx, rdi
0x1800067e8  mov     [rsp+140h+var_120], rax
0x1800067ed  mov     [rbp+arg_10], 0
0x1800067f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800067fa  mov     rcx, rbx
0x1800067fd  add     rsp, 130h
0x180006804  pop     rdi
0x180006805  pop     rbx
0x180006806  pop     rbp
0x180006807  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
