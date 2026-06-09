# FontSubsettingTelemetry::CreateFontPackage::Stop(ulong)

- ea: `0x18000611c`
- end: `0x180006371`
- name: `?Stop@CreateFontPackage@FontSubsettingTelemetry@@QEAAXK@Z`
- size: `597`
- prototype: `void __fastcall(FontSubsettingTelemetry::CreateFontPackage *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002a70`

## callees

- `0x1800015e0`
- `0x180001a08`
- `0x180004c64`
- `0x1800055ac`
- `0x18000611c`
- `0x1800073d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006301`
- `KERNEL32!GetCurrentThreadId` at `0x180006301`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::CreateFontPackage::Stop(
        FontSubsettingTelemetry::CreateFontPackage *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  int v20; // [rsp+D0h] [rbp-70h] BYREF
  int v21; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v22; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+100h] [rbp-40h] BYREF
  __int64 v28; // [rsp+108h] [rbp-38h] BYREF
  __int64 v29; // [rsp+110h] [rbp-30h] BYREF
  __int64 v30; // [rsp+118h] [rbp-28h] BYREF
  __int64 v31; // [rsp+120h] [rbp-20h] BYREF
  __int64 v32[3]; // [rsp+128h] [rbp-18h] BYREF
  int v33; // [rsp+150h] [rbp+10h] BYREF
  DWORD v34; // [rsp+160h] [rbp+20h] BYREF
  int v35; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = FontSubsettingTelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v25 = *((_QWORD *)v6 + 14);
      v16 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v26 = *((_QWORD *)v6 + 12);
      v27 = *((_QWORD *)v6 + 11);
      v17 = v6[20];
      v28 = *((_QWORD *)v6 + 9);
      v18 = v6[8];
      v29 = *((_QWORD *)v6 + 3);
      v19 = *v6;
      v30 = *((_QWORD *)v6 + 16);
      v20 = v6[16];
      v31 = *((_QWORD *)v6 + 7);
      v21 = v6[2];
      v23 = v10;
      v34 = v6[17];
      v35 = v6[4];
      v24 = *((_QWORD *)v6 + 15);
      v33 = a2;
      v32[0] = 0x1000000;
      v22 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)byte_18001E04B,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v22,
        (__int64)v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v23,
        (__int64)&v33);
    }
  }
  else
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = FontSubsettingTelemetryProvider::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      v33 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v34 = CurrentThreadId;
      v35 = *(_DWORD *)(v14 + 72);
      v22 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)&dword_18001E2EC,
        v14 + 8,
        v15,
        (__int64)&v22,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33);
    }
  }
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x18000611c  mov     [rsp-8+arg_8], rbx
0x180006121  push    rbp
0x180006122  push    rsi
0x180006123  push    rdi
0x180006124  lea     rbp, [rsp+10h]
0x180006129  sub     rsp, 130h
0x180006130  mov     rdi, [rcx+110h]
0x180006137  mov     esi, edx
0x180006139  mov     rbx, rcx
0x18000613c  mov     eax, [rdi+48h]
0x18000613f  test    eax, eax
0x180006141  jns     loc_1800062EA
0x180006147  add     rdi, 50h ; 'P'
0x18000614b  cmp     eax, [rdi+8]
0x18000614e  jnz     loc_1800062EA
0x180006154  test    rdi, rdi
0x180006157  jz      loc_1800062EA
0x18000615d  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180006162  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180006167  mov     r9, rax
0x18000616a  mov     ecx, [rax]
0x18000616c  cmp     ecx, 5
0x18000616f  jbe     loc_180006357
0x180006175  mov     rax, [rdi+70h]
0x180006179  lea     rdx, byte_18001E04B
0x180006180  mov     rcx, [rdi+30h]
0x180006184  mov     [rbp+var_50], rax
0x180006188  mov     eax, [rdi+68h]
0x18000618b  mov     [rbp+var_80], eax
0x18000618e  mov     rax, [rdi+60h]
0x180006192  mov     r8, [rbx+110h]
0x180006199  mov     [rbp+var_48], rax
0x18000619d  add     r8, 8
0x1800061a1  mov     rax, [rdi+58h]
0x1800061a5  mov     [rbp+var_40], rax
0x1800061a9  mov     eax, [rdi+50h]
0x1800061ac  mov     [rbp+var_7C], eax
0x1800061af  mov     rax, [rdi+48h]
0x1800061b3  mov     [rbp+var_38], rax
0x1800061b7  mov     eax, [rdi+20h]
0x1800061ba  mov     [rbp+var_78], eax
0x1800061bd  mov     rax, [rdi+18h]
0x1800061c1  mov     [rbp+var_30], rax
0x1800061c5  mov     eax, [rdi]
0x1800061c7  mov     [rbp+var_74], eax
0x1800061ca  mov     rax, [rdi+80h]
0x1800061d1  mov     [rbp+var_28], rax
0x1800061d5  mov     eax, [rdi+40h]
0x1800061d8  mov     [rbp+var_70], eax
0x1800061db  mov     rax, [rdi+38h]
0x1800061df  mov     [rbp+var_20], rax
0x1800061e3  mov     eax, [rdi+8]
0x1800061e6  mov     [rbp+var_6C], eax
0x1800061e9  lea     rax, [rbp+arg_0]
0x1800061ed  mov     [rsp+140h+var_88], rax
0x1800061f5  lea     rax, [rbp+var_60]
0x1800061f9  mov     [rsp+140h+var_90], rax
0x180006201  lea     rax, [rbp+arg_10]
0x180006205  mov     [rsp+140h+var_98], rax
0x18000620d  lea     rax, [rbp+arg_18]
0x180006211  mov     [rsp+140h+var_A0], rax
0x180006219  lea     rax, [rbp+var_58]
0x18000621d  mov     [rsp+140h+var_A8], rax
0x180006225  lea     rax, [rbp+var_50]
0x180006229  mov     [rsp+140h+var_B0], rax
0x180006231  lea     rax, [rbp+var_80]
0x180006235  mov     [rsp+140h+var_B8], rax
0x18000623d  lea     rax, [rbp+var_48]
0x180006241  mov     [rsp+140h+var_C0], rax
0x180006249  lea     rax, [rbp+var_40]
0x18000624d  mov     [rsp+140h+var_C8], rax
0x180006252  lea     rax, [rbp+var_7C]
0x180006256  mov     [rsp+140h+var_D0], rax
0x18000625b  lea     rax, [rbp+var_38]
0x18000625f  mov     [rsp+140h+var_D8], rax
0x180006264  lea     rax, [rbp+var_78]
0x180006268  mov     [rsp+140h+var_E0], rax
0x18000626d  lea     rax, [rbp+var_30]
0x180006271  mov     [rsp+140h+var_E8], rax
0x180006276  lea     rax, [rbp+var_74]
0x18000627a  mov     [rsp+140h+var_F0], rax
0x18000627f  lea     rax, [rbp+var_28]
0x180006283  mov     [rsp+140h+var_F8], rax
0x180006288  lea     rax, [rbp+var_70]
0x18000628c  mov     [rsp+140h+var_100], rax
0x180006291  lea     rax, [rbp+var_20]
0x180006295  mov     [rsp+140h+var_108], rax
0x18000629a  lea     rax, [rbp+var_6C]
0x18000629e  mov     [rbp+var_60], rcx
0x1800062a2  mov     ecx, [rdi+44h]
0x1800062a5  mov     [rsp+140h+var_110], rax
0x1800062aa  lea     rax, [rbp+var_18]
0x1800062ae  mov     [rbp+arg_10], ecx
0x1800062b1  mov     ecx, [rdi+10h]
0x1800062b4  mov     [rbp+arg_18], ecx
0x1800062b7  mov     rcx, [rdi+78h]
0x1800062bb  mov     [rsp+140h+var_118], rax
0x1800062c0  lea     rax, [rbp+var_68]
0x1800062c4  mov     [rbp+var_58], rcx
0x1800062c8  mov     rcx, r9
0x1800062cb  mov     [rsp+140h+var_120], rax
0x1800062d0  mov     [rbp+arg_0], esi
0x1800062d3  mov     [rbp+var_18], 1000000h
0x1800062db  mov     [rbp+var_68], 0
0x1800062e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800062e8  jmp     short loc_180006357
0x1800062ea  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800062ef  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x1800062f4  mov     rdi, rax
0x1800062f7  mov     ecx, [rax]
0x1800062f9  cmp     ecx, 5
0x1800062fc  jbe     short loc_180006357
0x1800062fe  mov     [rbp+arg_0], esi
0x180006301  call    cs:__imp_GetCurrentThreadId
0x180006307  mov     r8, [rbx+110h]
0x18000630e  lea     rdx, dword_18001E2EC
0x180006315  mov     [rbp+arg_10], eax
0x180006318  lea     rax, [rbp+arg_0]
0x18000631c  mov     [rsp+140h+var_108], rax
0x180006321  lea     rax, [rbp+arg_10]
0x180006325  mov     [rsp+140h+var_110], rax
0x18000632a  lea     rax, [rbp+arg_18]
0x18000632e  mov     ecx, [r8+48h]
0x180006332  add     r8, 8
0x180006336  mov     [rsp+140h+var_118], rax
0x18000633b  lea     rax, [rbp+var_68]
0x18000633f  mov     [rbp+arg_18], ecx
0x180006342  mov     rcx, rdi
0x180006345  mov     [rsp+140h+var_120], rax
0x18000634a  mov     [rbp+var_68], 0
0x180006352  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180006357  mov     rcx, rbx
0x18000635a  mov     rbx, [rsp+140h+arg_8]
0x180006362  add     rsp, 130h
0x180006369  pop     rdi
0x18000636a  pop     rsi
0x18000636b  pop     rbp
0x18000636c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
