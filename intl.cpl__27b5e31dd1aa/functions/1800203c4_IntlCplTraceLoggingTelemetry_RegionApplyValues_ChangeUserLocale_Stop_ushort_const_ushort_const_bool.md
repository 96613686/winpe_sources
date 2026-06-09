# IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::Stop(ushort const *,ushort const *,bool)

- ea: `0x1800203c4`
- end: `0x180020659`
- name: `?Stop@RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAAXPEBG0_N@Z`
- size: `661`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ebc8`

## callees

- `0x1800017fc`
- `0x1800020c4`
- `0x180002400`
- `0x1800093fc`
- `0x18000d524`
- `0x18000f5b4`
- `0x1800203c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205da`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::Stop(
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // r9
  __int64 v15; // r8
  const struct _tlgProvider_t *v16; // rax
  int v17; // edi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // r9d
  int v21; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v22; // [rsp+C4h] [rbp-7Ch] BYREF
  int v23; // [rsp+C8h] [rbp-78h] BYREF
  int v24; // [rsp+CCh] [rbp-74h] BYREF
  int v25; // [rsp+D0h] [rbp-70h] BYREF
  int v26; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v27; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v31; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+100h] [rbp-40h] BYREF
  __int64 v33; // [rsp+108h] [rbp-38h] BYREF
  __int64 v34; // [rsp+110h] [rbp-30h] BYREF
  __int64 v35; // [rsp+118h] [rbp-28h] BYREF
  __int64 v36; // [rsp+120h] [rbp-20h] BYREF
  __int64 v37; // [rsp+128h] [rbp-18h] BYREF
  _QWORD v38[8]; // [rsp+130h] [rbp-10h] BYREF
  char v39; // [rsp+180h] [rbp+40h] BYREF

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = IntlCplTraceLogging::Provider();
    v14 = v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      v32 = *((_QWORD *)v10 + 15);
      v33 = *((_QWORD *)v10 + 14);
      v15 = *((_QWORD *)this + 34);
      v23 = v10[26];
      v34 = *((_QWORD *)v10 + 12);
      v35 = *((_QWORD *)v10 + 11);
      v24 = v10[20];
      v36 = *((_QWORD *)v10 + 9);
      v25 = v10[8];
      v37 = *((_QWORD *)v10 + 3);
      v26 = *v10;
      v38[0] = *((_QWORD *)v10 + 16);
      v21 = v10[16];
      v27 = *((_QWORD *)v10 + 7);
      v22 = v10[2];
      v39 = a4;
      v30 = a3;
      v31 = a2;
      v28 = 0x1000000;
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        (_DWORD)v14,
        (unsigned int)&unk_180034190,
        v15 + 8,
        (_DWORD)v14,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)v38,
        (__int64)&v26,
        (__int64)&v37,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v24,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v23,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v39);
    }
  }
  else
  {
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v16 = IntlCplTraceLogging::Provider();
    v17 = (int)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x200000000000LL) )
    {
      v39 = a4;
      v29 = a3;
      v28 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v22 = CurrentThreadId;
      v21 = *(_DWORD *)(v19 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        v17,
        (unsigned int)&unk_180034312,
        v19 + 8,
        v20,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v39);
    }
  }
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v12,
    v13,
    v14);
}

```

## disassembly

```asm
0x1800203c4  push    rbp
0x1800203c6  push    rbx
0x1800203c7  push    rsi
0x1800203c8  push    rdi
0x1800203c9  push    r14
0x1800203cb  push    r15
0x1800203cd  lea     rbp, [rsp-8]
0x1800203d2  sub     rsp, 148h
0x1800203d9  mov     rdi, [rcx+110h]
0x1800203e0  mov     sil, r9b
0x1800203e3  mov     r14, r8
0x1800203e6  mov     r15, rdx
0x1800203e9  mov     rbx, rcx
0x1800203ec  mov     eax, [rdi+48h]
0x1800203ef  test    eax, eax
0x1800203f1  jns     loc_1800205A0
0x1800203f7  add     rdi, 50h ; 'P'
0x1800203fb  cmp     eax, [rdi+8]
0x1800203fe  jnz     loc_1800205A0
0x180020404  test    rdi, rdi
0x180020407  jz      loc_1800205A0
0x18002040d  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020412  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180020417  mov     r9, rax
0x18002041a  mov     ecx, [rax]
0x18002041c  cmp     ecx, 5
0x18002041f  jbe     loc_180020642
0x180020425  mov     rdx, 200000000000h
0x18002042f  mov     rcx, rax
0x180020432  call    _tlgKeywordOn
0x180020437  test    al, al
0x180020439  jz      loc_180020642
0x18002043f  mov     rax, [rdi+78h]
0x180020443  lea     rdx, unk_180034190
0x18002044a  mov     [rbp+30h+var_70], rax
0x18002044e  mov     rcx, r9
0x180020451  mov     rax, [rdi+70h]
0x180020455  mov     [rbp+30h+var_68], rax
0x180020459  mov     eax, [rdi+68h]
0x18002045c  mov     r8, [rbx+110h]
0x180020463  mov     [rbp+30h+var_A8], eax
0x180020466  add     r8, 8
0x18002046a  mov     rax, [rdi+60h]
0x18002046e  mov     [rbp+30h+var_60], rax
0x180020472  mov     rax, [rdi+58h]
0x180020476  mov     [rbp+30h+var_58], rax
0x18002047a  mov     eax, [rdi+50h]
0x18002047d  mov     [rbp+30h+var_A4], eax
0x180020480  mov     rax, [rdi+48h]
0x180020484  mov     [rbp+30h+var_50], rax
0x180020488  mov     eax, [rdi+20h]
0x18002048b  mov     [rbp+30h+var_A0], eax
0x18002048e  mov     rax, [rdi+18h]
0x180020492  mov     [rbp+30h+var_48], rax
0x180020496  mov     eax, [rdi]
0x180020498  mov     [rbp+30h+var_9C], eax
0x18002049b  mov     rax, [rdi+80h]
0x1800204a2  mov     [rbp+30h+var_40], rax
0x1800204a6  mov     eax, [rdi+40h]
0x1800204a9  mov     [rbp+30h+var_B0], eax
0x1800204ac  mov     rax, [rdi+38h]
0x1800204b0  mov     [rbp+30h+var_98], rax
0x1800204b4  mov     eax, [rdi+8]
0x1800204b7  mov     [rbp+30h+var_AC], eax
0x1800204ba  lea     rax, [rbp+30h+arg_0]
0x1800204be  mov     [rsp+170h+var_C0], rax
0x1800204c6  lea     rax, [rbp+30h+var_80]
0x1800204ca  mov     [rsp+170h+var_C8], rax
0x1800204d2  lea     rax, [rbp+30h+var_78]
0x1800204d6  mov     [rsp+170h+var_D0], rax
0x1800204de  lea     rax, [rbp+30h+var_70]
0x1800204e2  mov     [rsp+170h+var_D8], rax
0x1800204ea  lea     rax, [rbp+30h+var_68]
0x1800204ee  mov     [rsp+170h+var_E0], rax
0x1800204f6  lea     rax, [rbp+30h+var_A8]
0x1800204fa  mov     [rsp+170h+var_E8], rax
0x180020502  lea     rax, [rbp+30h+var_60]
0x180020506  mov     [rsp+170h+var_F0], rax
0x18002050e  lea     rax, [rbp+30h+var_58]
0x180020512  mov     [rsp+170h+var_F8], rax
0x180020517  lea     rax, [rbp+30h+var_A4]
0x18002051b  mov     [rsp+170h+var_100], rax
0x180020520  lea     rax, [rbp+30h+var_50]
0x180020524  mov     [rsp+170h+var_108], rax
0x180020529  lea     rax, [rbp+30h+var_A0]
0x18002052d  mov     [rsp+170h+var_110], rax
0x180020532  lea     rax, [rbp+30h+var_48]
0x180020536  mov     [rsp+170h+var_118], rax
0x18002053b  lea     rax, [rbp+30h+var_9C]
0x18002053f  mov     [rsp+170h+var_120], rax
0x180020544  lea     rax, [rbp+30h+var_40]
0x180020548  mov     [rsp+170h+var_128], rax
0x18002054d  lea     rax, [rbp+30h+var_B0]
0x180020551  mov     [rsp+170h+var_130], rax
0x180020556  lea     rax, [rbp+30h+var_98]
0x18002055a  mov     [rsp+170h+var_138], rax
0x18002055f  lea     rax, [rbp+30h+var_AC]
0x180020563  mov     [rsp+170h+var_140], rax
0x180020568  lea     rax, [rbp+30h+var_90]
0x18002056c  mov     [rsp+170h+var_148], rax
0x180020571  lea     rax, [rbp+30h+var_88]
0x180020575  mov     [rsp+170h+var_150], rax
0x18002057a  mov     [rbp+30h+arg_0], sil
0x18002057e  mov     [rbp+30h+var_80], r14
0x180020582  mov     [rbp+30h+var_78], r15
0x180020586  mov     [rbp+30h+var_90], 1000000h
0x18002058e  mov     [rbp+30h+var_88], 0
0x180020596  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645666AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x18002059b  jmp     loc_180020642
0x1800205a0  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800205a5  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x1800205aa  mov     rdi, rax
0x1800205ad  mov     ecx, [rax]
0x1800205af  cmp     ecx, 5
0x1800205b2  jbe     loc_180020642
0x1800205b8  mov     rdx, 200000000000h
0x1800205c2  mov     rcx, rax
0x1800205c5  call    _tlgKeywordOn
0x1800205ca  test    al, al
0x1800205cc  jz      short loc_180020642
0x1800205ce  mov     [rbp+30h+arg_0], sil
0x1800205d2  mov     [rbp+30h+var_88], r14
0x1800205d6  mov     [rbp+30h+var_90], r15
0x1800205da  call    cs:__imp_GetCurrentThreadId
0x1800205e0  mov     r8, [rbx+110h]
0x1800205e7  lea     rdx, unk_180034312
0x1800205ee  mov     [rbp+30h+var_AC], eax
0x1800205f1  mov     rcx, rdi
0x1800205f4  mov     eax, [r8+48h]
0x1800205f8  add     r8, 8
0x1800205fc  mov     [rbp+30h+var_B0], eax
0x1800205ff  lea     rax, [rbp+30h+arg_0]
0x180020603  mov     [rsp+170h+var_128], rax
0x180020608  lea     rax, [rbp+30h+var_88]
0x18002060c  mov     [rsp+170h+var_130], rax
0x180020611  lea     rax, [rbp+30h+var_90]
0x180020615  mov     [rsp+170h+var_138], rax
0x18002061a  lea     rax, [rbp+30h+var_AC]
0x18002061e  mov     [rsp+170h+var_140], rax
0x180020623  lea     rax, [rbp+30h+var_B0]
0x180020627  mov     [rsp+170h+var_148], rax
0x18002062c  lea     rax, [rbp+30h+var_98]
0x180020630  mov     [rsp+170h+var_150], rax
0x180020635  mov     [rbp+30h+var_98], 0
0x18002063d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x180020642  mov     rcx, rbx
0x180020645  add     rsp, 148h
0x18002064c  pop     r15
0x18002064e  pop     r14
0x180020650  pop     rdi
0x180020651  pop     rsi
0x180020652  pop     rbx
0x180020653  pop     rbp
0x180020654  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
