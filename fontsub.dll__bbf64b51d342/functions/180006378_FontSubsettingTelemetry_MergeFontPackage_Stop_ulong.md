# FontSubsettingTelemetry::MergeFontPackage::Stop(ulong)

- ea: `0x180006378`
- end: `0x1800065cd`
- name: `?Stop@MergeFontPackage@FontSubsettingTelemetry@@QEAAXK@Z`
- size: `597`
- prototype: `void __fastcall(FontSubsettingTelemetry::MergeFontPackage *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002c80`

## callees

- `0x1800015e0`
- `0x180001a08`
- `0x180004c64`
- `0x1800055ac`
- `0x180006378`
- `0x1800073d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000655d`
- `KERNEL32!GetCurrentThreadId` at `0x18000655d`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::MergeFontPackage::Stop(
        FontSubsettingTelemetry::MergeFontPackage *this,
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
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33[3]; // [rsp+128h] [rbp-18h] BYREF
  int v34; // [rsp+150h] [rbp+10h] BYREF
  DWORD v35; // [rsp+160h] [rbp+20h] BYREF
  int v36; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = FontSubsettingTelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v26 = *((_QWORD *)v6 + 14);
      v17 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v18 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v19 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v20 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v21 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v22 = v6[2];
      v24 = v10;
      v35 = v6[17];
      v36 = v6[4];
      v25 = *((_QWORD *)v6 + 15);
      v34 = a2;
      v33[0] = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&unk_18001E5A0,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v23,
        (__int64)v33,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = FontSubsettingTelemetryProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 5u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&word_18001E546,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
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
0x180006378  mov     [rsp-8+arg_8], rbx
0x18000637d  push    rbp
0x18000637e  push    rsi
0x18000637f  push    rdi
0x180006380  lea     rbp, [rsp+10h]
0x180006385  sub     rsp, 130h
0x18000638c  mov     rdi, [rcx+110h]
0x180006393  mov     esi, edx
0x180006395  mov     rbx, rcx
0x180006398  mov     eax, [rdi+48h]
0x18000639b  test    eax, eax
0x18000639d  jns     loc_180006546
0x1800063a3  add     rdi, 50h ; 'P'
0x1800063a7  cmp     eax, [rdi+8]
0x1800063aa  jnz     loc_180006546
0x1800063b0  test    rdi, rdi
0x1800063b3  jz      loc_180006546
0x1800063b9  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800063be  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x1800063c3  mov     r9, rax
0x1800063c6  mov     ecx, [rax]
0x1800063c8  cmp     ecx, 5
0x1800063cb  jbe     loc_1800065B3
0x1800063d1  mov     rax, [rdi+70h]
0x1800063d5  lea     rdx, unk_18001E5A0
0x1800063dc  mov     rcx, [rdi+30h]
0x1800063e0  mov     [rbp+var_50], rax
0x1800063e4  mov     eax, [rdi+68h]
0x1800063e7  mov     [rbp+var_80], eax
0x1800063ea  mov     rax, [rdi+60h]
0x1800063ee  mov     r8, [rbx+110h]
0x1800063f5  mov     [rbp+var_48], rax
0x1800063f9  add     r8, 8
0x1800063fd  mov     rax, [rdi+58h]
0x180006401  mov     [rbp+var_40], rax
0x180006405  mov     eax, [rdi+50h]
0x180006408  mov     [rbp+var_7C], eax
0x18000640b  mov     rax, [rdi+48h]
0x18000640f  mov     [rbp+var_38], rax
0x180006413  mov     eax, [rdi+20h]
0x180006416  mov     [rbp+var_78], eax
0x180006419  mov     rax, [rdi+18h]
0x18000641d  mov     [rbp+var_30], rax
0x180006421  mov     eax, [rdi]
0x180006423  mov     [rbp+var_74], eax
0x180006426  mov     rax, [rdi+80h]
0x18000642d  mov     [rbp+var_28], rax
0x180006431  mov     eax, [rdi+40h]
0x180006434  mov     [rbp+var_70], eax
0x180006437  mov     rax, [rdi+38h]
0x18000643b  mov     [rbp+var_20], rax
0x18000643f  mov     eax, [rdi+8]
0x180006442  mov     [rbp+var_6C], eax
0x180006445  lea     rax, [rbp+arg_0]
0x180006449  mov     [rsp+140h+var_88], rax
0x180006451  lea     rax, [rbp+var_60]
0x180006455  mov     [rsp+140h+var_90], rax
0x18000645d  lea     rax, [rbp+arg_10]
0x180006461  mov     [rsp+140h+var_98], rax
0x180006469  lea     rax, [rbp+arg_18]
0x18000646d  mov     [rsp+140h+var_A0], rax
0x180006475  lea     rax, [rbp+var_58]
0x180006479  mov     [rsp+140h+var_A8], rax
0x180006481  lea     rax, [rbp+var_50]
0x180006485  mov     [rsp+140h+var_B0], rax
0x18000648d  lea     rax, [rbp+var_80]
0x180006491  mov     [rsp+140h+var_B8], rax
0x180006499  lea     rax, [rbp+var_48]
0x18000649d  mov     [rsp+140h+var_C0], rax
0x1800064a5  lea     rax, [rbp+var_40]
0x1800064a9  mov     [rsp+140h+var_C8], rax
0x1800064ae  lea     rax, [rbp+var_7C]
0x1800064b2  mov     [rsp+140h+var_D0], rax
0x1800064b7  lea     rax, [rbp+var_38]
0x1800064bb  mov     [rsp+140h+var_D8], rax
0x1800064c0  lea     rax, [rbp+var_78]
0x1800064c4  mov     [rsp+140h+var_E0], rax
0x1800064c9  lea     rax, [rbp+var_30]
0x1800064cd  mov     [rsp+140h+var_E8], rax
0x1800064d2  lea     rax, [rbp+var_74]
0x1800064d6  mov     [rsp+140h+var_F0], rax
0x1800064db  lea     rax, [rbp+var_28]
0x1800064df  mov     [rsp+140h+var_F8], rax
0x1800064e4  lea     rax, [rbp+var_70]
0x1800064e8  mov     [rsp+140h+var_100], rax
0x1800064ed  lea     rax, [rbp+var_20]
0x1800064f1  mov     [rsp+140h+var_108], rax
0x1800064f6  lea     rax, [rbp+var_6C]
0x1800064fa  mov     [rbp+var_60], rcx
0x1800064fe  mov     ecx, [rdi+44h]
0x180006501  mov     [rsp+140h+var_110], rax
0x180006506  lea     rax, [rbp+var_18]
0x18000650a  mov     [rbp+arg_10], ecx
0x18000650d  mov     ecx, [rdi+10h]
0x180006510  mov     [rbp+arg_18], ecx
0x180006513  mov     rcx, [rdi+78h]
0x180006517  mov     [rsp+140h+var_118], rax
0x18000651c  lea     rax, [rbp+var_68]
0x180006520  mov     [rbp+var_58], rcx
0x180006524  mov     rcx, r9
0x180006527  mov     [rsp+140h+var_120], rax
0x18000652c  mov     [rbp+arg_0], esi
0x18000652f  mov     [rbp+var_18], 1000000h
0x180006537  mov     [rbp+var_68], 0
0x18000653f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006544  jmp     short loc_1800065B3
0x180006546  call    ?zInternalStop@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000654b  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180006550  mov     rdi, rax
0x180006553  mov     ecx, [rax]
0x180006555  cmp     ecx, 5
0x180006558  jbe     short loc_1800065B3
0x18000655a  mov     [rbp+arg_0], esi
0x18000655d  call    cs:__imp_GetCurrentThreadId
0x180006563  mov     r8, [rbx+110h]
0x18000656a  lea     rdx, word_18001E546
0x180006571  mov     [rbp+arg_10], eax
0x180006574  lea     rax, [rbp+arg_0]
0x180006578  mov     [rsp+140h+var_108], rax
0x18000657d  lea     rax, [rbp+arg_10]
0x180006581  mov     [rsp+140h+var_110], rax
0x180006586  lea     rax, [rbp+arg_18]
0x18000658a  mov     ecx, [r8+48h]
0x18000658e  add     r8, 8
0x180006592  mov     [rsp+140h+var_118], rax
0x180006597  lea     rax, [rbp+var_68]
0x18000659b  mov     [rbp+arg_18], ecx
0x18000659e  mov     rcx, rdi
0x1800065a1  mov     [rsp+140h+var_120], rax
0x1800065a6  mov     [rbp+var_68], 0
0x1800065ae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800065b3  mov     rcx, rbx
0x1800065b6  mov     rbx, [rsp+140h+arg_8]
0x1800065be  add     rsp, 130h
0x1800065c5  pop     rdi
0x1800065c6  pop     rsi
0x1800065c7  pop     rbp
0x1800065c8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
