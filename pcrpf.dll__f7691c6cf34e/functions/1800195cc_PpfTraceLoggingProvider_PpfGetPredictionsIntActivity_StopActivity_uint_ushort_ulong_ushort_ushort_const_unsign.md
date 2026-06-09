# PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StopActivity(uint,ushort,ulong,ushort,ushort const *,unsigned __int64)

- ea: `0x1800195cc`
- end: `0x180019a4e`
- name: `?StopActivity@PpfGetPredictionsIntActivity@PpfTraceLoggingProvider@@QEAAXIGKGPEBG_K@Z`
- size: `1154`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *this, int, unsigned __int16, int, unsigned __int16, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800141f4`

## callees

- `0x180001640`
- `0x180001a18`
- `0x180003270`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x1800195cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019653`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019653`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StopActivity(
        PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *this,
        int a2,
        unsigned __int16 a3,
        int a4,
        unsigned __int16 a5,
        const unsigned __int16 *a6,
        unsigned __int64 a7)
{
  __int64 v7; // rsi
  int v12; // eax
  __int64 v13; // rsi
  RTL_SRWLOCK *v14; // rcx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // r8
  RTL_SRWLOCK *v19; // rcx
  const struct _tlgProvider_t *v20; // rax
  const struct _tlgProvider_t *v21; // rsi
  __int64 v22; // rax
  DWORD CurrentThreadId; // eax
  __int64 v24; // r8
  const wchar_t *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  unsigned __int16 v28; // [rsp+E0h] [rbp-80h] BYREF
  unsigned __int16 v29; // [rsp+E2h] [rbp-7Eh] BYREF
  int v30; // [rsp+E4h] [rbp-7Ch] BYREF
  DWORD v31; // [rsp+E8h] [rbp-78h] BYREF
  int v32; // [rsp+ECh] [rbp-74h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp-70h] BYREF
  PSRWLOCK v34; // [rsp+F8h] [rbp-68h] BYREF
  int v35; // [rsp+100h] [rbp-60h] BYREF
  int v36; // [rsp+104h] [rbp-5Ch] BYREF
  int v37; // [rsp+108h] [rbp-58h] BYREF
  int v38; // [rsp+10Ch] [rbp-54h] BYREF
  __int64 v39; // [rsp+110h] [rbp-50h] BYREF
  unsigned __int64 v40; // [rsp+118h] [rbp-48h] BYREF
  __int64 v41; // [rsp+120h] [rbp-40h] BYREF
  unsigned __int64 v42; // [rsp+128h] [rbp-38h] BYREF
  const wchar_t *v43; // [rsp+130h] [rbp-30h] BYREF
  const wchar_t *v44; // [rsp+138h] [rbp-28h] BYREF
  const unsigned __int16 *v45; // [rsp+140h] [rbp-20h] BYREF
  const wchar_t *v46; // [rsp+148h] [rbp-18h] BYREF
  const unsigned __int16 *v47; // [rsp+150h] [rbp-10h] BYREF
  const unsigned __int16 *v48; // [rsp+158h] [rbp-8h] BYREF
  const wchar_t *v49; // [rsp+160h] [rbp+0h] BYREF
  const unsigned __int16 *v50; // [rsp+168h] [rbp+8h] BYREF
  char v51[32]; // [rsp+170h] [rbp+10h] BYREF
  __int64 *v52; // [rsp+190h] [rbp+30h]
  __int64 v53; // [rsp+198h] [rbp+38h]
  int *v54; // [rsp+1A0h] [rbp+40h]
  __int64 v55; // [rsp+1A8h] [rbp+48h]
  DWORD *v56; // [rsp+1B0h] [rbp+50h]
  __int64 v57; // [rsp+1B8h] [rbp+58h]
  int *v58; // [rsp+1C0h] [rbp+60h]
  __int64 v59; // [rsp+1C8h] [rbp+68h]
  unsigned __int16 *v60; // [rsp+1D0h] [rbp+70h]
  __int64 v61; // [rsp+1D8h] [rbp+78h]
  PSRWLOCK *p_SRWLock; // [rsp+1E0h] [rbp+80h]
  __int64 v63; // [rsp+1E8h] [rbp+88h]
  unsigned __int16 *v64; // [rsp+1F0h] [rbp+90h]
  __int64 v65; // [rsp+1F8h] [rbp+98h]
  const wchar_t *v66; // [rsp+200h] [rbp+A0h]
  int v67; // [rsp+208h] [rbp+A8h]
  int v68; // [rsp+20Ch] [rbp+ACh]
  unsigned __int64 *v69; // [rsp+210h] [rbp+B0h]
  __int64 v70; // [rsp+218h] [rbp+B8h]
  PSRWLOCK *v71; // [rsp+220h] [rbp+C0h]
  __int64 v72; // [rsp+228h] [rbp+C8h]

  v7 = *((_QWORD *)this + 34);
  v12 = *(_DWORD *)(v7 + 72);
  if ( v12 < 0 && (v13 = v7 + 80, v12 == *(_DWORD *)(v13 + 8)) && v13 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v14 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    v15 = PpfTraceLoggingProvider::Provider();
    v16 = (__int64)v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *((_QWORD *)v15 + 3);
      if ( (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        v42 = a7;
        v43 = a6;
        v28 = a5;
        v44 = *(const wchar_t **)(v13 + 120);
        v45 = *(const unsigned __int16 **)(v13 + 112);
        v18 = *((_QWORD *)this + 34);
        v37 = *(_DWORD *)(v13 + 104);
        v46 = *(const wchar_t **)(v13 + 96);
        v47 = *(const unsigned __int16 **)(v13 + 88);
        v38 = *(_DWORD *)(v13 + 80);
        v48 = *(const unsigned __int16 **)(v13 + 72);
        v30 = *(_DWORD *)(v13 + 32);
        v49 = *(const wchar_t **)(v13 + 24);
        v31 = *(_DWORD *)v13;
        v50 = *(const unsigned __int16 **)(v13 + 128);
        v32 = *(_DWORD *)(v13 + 64);
        v39 = *(_QWORD *)(v13 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v13 + 8);
        v41 = 0x1000000;
        v35 = a4;
        v29 = a3;
        v36 = a2;
        v40 = 0x1000000;
        v34 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v16,
          (__int64)&word_180068316,
          v18 + 8,
          v16,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v39,
          (__int64)&v32,
          &v50,
          (__int64)&v31,
          &v49,
          (__int64)&v30,
          &v48,
          (__int64)&v38,
          &v47,
          &v46,
          (__int64)&v37,
          &v45,
          &v44,
          (__int64)&v36,
          (__int64)&v29,
          (__int64)&v35,
          (__int64)&v28,
          &v43,
          (__int64)&v42,
          (__int64)&v41);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v34);
    v19 = v34;
    **((_DWORD **)this + 34) = 2;
    if ( v19 )
      ReleaseSRWLockExclusive(v19);
    v20 = PpfTraceLoggingProvider::Provider();
    v21 = v20;
    if ( *(_DWORD *)v20 > 5u )
    {
      v22 = *((_QWORD *)v20 + 3);
      if ( (*((_QWORD *)v21 + 2) & 0x400000000000LL) != 0 && (v22 & 0x400000000000LL) == v22 )
      {
        v40 = a7;
        v29 = a5;
        v34 = (PSRWLOCK)0x1000000;
        LODWORD(SRWLock) = a4;
        v28 = a3;
        v32 = a2;
        CurrentThreadId = GetCurrentThreadId();
        v24 = *((_QWORD *)this + 34);
        v25 = a6;
        v31 = CurrentThreadId;
        v72 = 8;
        v30 = *(_DWORD *)(v24 + 72);
        v71 = &v34;
        v69 = &v40;
        v39 = 0x1000000;
        v70 = 8;
        if ( a6 )
        {
          v26 = -1;
          do
            ++v26;
          while ( a6[v26] );
          v27 = 2 * v26 + 2;
        }
        else
        {
          v25 = &Format;
          v27 = 2;
        }
        v67 = v27;
        v66 = v25;
        v64 = &v29;
        v68 = 0;
        p_SRWLock = &SRWLock;
        v65 = 2;
        v60 = &v28;
        v63 = 4;
        v58 = &v32;
        v56 = &v31;
        v54 = &v30;
        v52 = &v39;
        v61 = 2;
        v59 = 4;
        v57 = 4;
        v55 = 4;
        v53 = 8;
        tlgWriteTransfer_EventWriteTransfer(v21, byte_1800690CB, v24 + 8, 0, 12, v51);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800195cc  mov     [rsp-8+arg_8], rbx
0x1800195d1  mov     [rsp-8+arg_10], rsi
0x1800195d6  push    rbp
0x1800195d7  push    r12
0x1800195d9  push    r13
0x1800195db  push    r14
0x1800195dd  push    r15
0x1800195df  lea     rbp, [rsp-0E0h]
0x1800195e7  sub     rsp, 240h
0x1800195ee  mov     rax, cs:__security_cookie
0x1800195f5  xor     rax, rsp
0x1800195f8  mov     [rbp+100h+var_30], rax
0x1800195ff  mov     rsi, [rcx+110h]
0x180019606  mov     r15d, r9d
0x180019609  movzx   r12d, r8w
0x18001960d  mov     r13d, edx
0x180019610  mov     rbx, rcx
0x180019613  mov     eax, [rsi+48h]
0x180019616  test    eax, eax
0x180019618  jns     loc_180019851
0x18001961e  add     rsi, 50h ; 'P'
0x180019622  cmp     eax, [rsi+8]
0x180019625  jnz     loc_180019851
0x18001962b  test    rsi, rsi
0x18001962e  jz      loc_180019851
0x180019634  lea     rdx, [rbp+100h+SRWLock]
0x180019638  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001963d  mov     rax, [rbx+110h]
0x180019644  mov     rcx, [rbp+100h+SRWLock]; SRWLock
0x180019648  mov     dword ptr [rax], 2
0x18001964e  test    rcx, rcx
0x180019651  jz      short loc_18001965F
0x180019653  call    cs:__imp_ReleaseSRWLockExclusive
0x18001965a  nop     dword ptr [rax+rax+00h]
0x18001965f  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019664  mov     r9, rax
0x180019667  mov     ecx, [rax]
0x180019669  cmp     ecx, 5
0x18001966c  jbe     loc_180019A19
0x180019672  mov     rax, [rax+18h]
0x180019676  mov     rdx, 400000000000h
0x180019680  mov     rcx, [r9+10h]
0x180019684  test    rdx, rcx
0x180019687  jz      loc_180019A19
0x18001968d  mov     rcx, rax
0x180019690  and     rcx, rdx
0x180019693  cmp     rcx, rax
0x180019696  jnz     loc_180019A19
0x18001969c  mov     rax, [rbp+100h+arg_30]
0x1800196a3  mov     r14d, 1000000h
0x1800196a9  mov     [rbp+100h+var_138], rax
0x1800196ad  mov     rax, [rbp+100h+arg_28]
0x1800196b4  mov     [rbp+100h+var_130], rax
0x1800196b8  movzx   eax, [rbp+100h+arg_20]
0x1800196bf  mov     [rbp+100h+var_180], ax
0x1800196c3  mov     rax, [rsi+78h]
0x1800196c7  mov     [rbp+100h+var_128], rax
0x1800196cb  mov     rax, [rsi+70h]
0x1800196cf  mov     [rbp+100h+var_120], rax
0x1800196d3  mov     eax, [rsi+68h]
0x1800196d6  mov     r8, [rbx+110h]
0x1800196dd  mov     [rbp+100h+var_158], eax
0x1800196e0  add     r8, 8
0x1800196e4  mov     rax, [rsi+60h]
0x1800196e8  mov     [rbp+100h+var_118], rax
0x1800196ec  mov     rax, [rsi+58h]
0x1800196f0  mov     [rbp+100h+var_110], rax
0x1800196f4  mov     eax, [rsi+50h]
0x1800196f7  mov     [rbp+100h+var_154], eax
0x1800196fa  mov     rax, [rsi+48h]
0x1800196fe  mov     [rbp+100h+var_108], rax
0x180019702  mov     eax, [rsi+20h]
0x180019705  mov     [rbp+100h+var_17C], eax
0x180019708  mov     rax, [rsi+18h]
0x18001970c  mov     [rbp+100h+var_100], rax
0x180019710  mov     eax, [rsi]
0x180019712  mov     [rbp+100h+var_178], eax
0x180019715  mov     rax, [rsi+80h]
0x18001971c  mov     [rbp+100h+var_F8], rax
0x180019720  mov     eax, [rsi+40h]
0x180019723  mov     [rbp+100h+var_174], eax
0x180019726  mov     rax, [rsi+38h]
0x18001972a  mov     [rbp+100h+var_150], rax
0x18001972e  mov     eax, [rsi+8]
0x180019731  mov     dword ptr [rbp+100h+SRWLock], eax
0x180019734  lea     rax, [rbp+100h+var_140]
0x180019738  mov     [rsp+260h+var_190], rax
0x180019740  lea     rax, [rbp+100h+var_138]
0x180019744  mov     [rsp+260h+var_198], rax
0x18001974c  lea     rax, [rbp+100h+var_130]
0x180019750  mov     [rsp+260h+var_1A0], rax
0x180019758  lea     rax, [rbp+100h+var_180]
0x18001975c  mov     [rsp+260h+var_1A8], rax
0x180019764  lea     rax, [rbp+100h+var_160]
0x180019768  mov     [rsp+260h+var_1B0], rax
0x180019770  lea     rax, [rbp+100h+var_17E]
0x180019774  mov     [rsp+260h+var_1B8], rax
0x18001977c  lea     rax, [rbp+100h+var_15C]
0x180019780  mov     [rsp+260h+var_1C0], rax
0x180019788  lea     rax, [rbp+100h+var_128]
0x18001978c  mov     [rsp+260h+var_1C8], rax
0x180019794  lea     rax, [rbp+100h+var_120]
0x180019798  mov     [rsp+260h+var_1D0], rax
0x1800197a0  lea     rax, [rbp+100h+var_158]
0x1800197a4  mov     [rsp+260h+var_1D8], rax
0x1800197ac  lea     rax, [rbp+100h+var_118]
0x1800197b0  mov     [rsp+260h+var_1E0], rax
0x1800197b8  lea     rax, [rbp+100h+var_110]
0x1800197bc  mov     [rsp+260h+var_1E8], rax
0x1800197c1  lea     rax, [rbp+100h+var_154]
0x1800197c5  mov     [rsp+260h+var_1F0], rax
0x1800197ca  lea     rax, [rbp+100h+var_108]
0x1800197ce  mov     [rsp+260h+var_1F8], rax
0x1800197d3  lea     rax, [rbp+100h+var_17C]
0x1800197d7  mov     [rsp+260h+var_200], rax
0x1800197dc  lea     rax, [rbp+100h+var_100]
0x1800197e0  mov     [rsp+260h+var_208], rax
0x1800197e5  lea     rax, [rbp+100h+var_178]
0x1800197e9  mov     [rsp+260h+var_210], rax
0x1800197ee  lea     rax, [rbp+100h+var_F8]
0x1800197f2  mov     [rsp+260h+var_218], rax
0x1800197f7  lea     rax, [rbp+100h+var_174]
0x1800197fb  mov     [rsp+260h+var_220], rax
0x180019800  mov     [rbp+100h+var_140], r14
0x180019804  mov     [rbp+100h+var_160], r15d
0x180019808  mov     [rbp+100h+var_17E], r12w
0x18001980d  mov     [rbp+100h+var_15C], r13d
0x180019811  mov     [rbp+100h+var_148], r14
0x180019815  mov     [rbp+100h+var_168], r14
0x180019819  lea     rax, [rbp+100h+var_150]
0x18001981d  mov     rcx, r9
0x180019820  mov     [rsp+260h+var_228], rax
0x180019825  lea     rdx, word_180068316
0x18001982c  lea     rax, [rbp+100h+SRWLock]
0x180019830  mov     [rsp+260h+var_230], rax
0x180019835  lea     rax, [rbp+100h+var_148]
0x180019839  mov     [rsp+260h+var_238], rax
0x18001983e  lea     rax, [rbp+100h+var_168]
0x180019842  mov     [rsp+260h+var_240], rax
0x180019847  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U?$_tlgWrapperByVal@$01@@U2@U5@U4@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564AEBU?$_tlgWrapperByVal@$01@@47633@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001984c  jmp     loc_180019A19
0x180019851  lea     rdx, [rbp+100h+var_168]
0x180019855  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001985a  mov     rax, [rbx+110h]
0x180019861  mov     rcx, [rbp+100h+var_168]; SRWLock
0x180019865  mov     dword ptr [rax], 2
0x18001986b  test    rcx, rcx
0x18001986e  jz      short loc_18001987C
0x180019870  call    cs:__imp_ReleaseSRWLockExclusive
0x180019877  nop     dword ptr [rax+rax+00h]
0x18001987c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019881  mov     rsi, rax
0x180019884  mov     ecx, [rax]
0x180019886  cmp     ecx, 5
0x180019889  jbe     loc_180019A19
0x18001988f  mov     rax, [rax+18h]
0x180019893  mov     rdx, 400000000000h
0x18001989d  mov     rcx, [rsi+10h]
0x1800198a1  test    rdx, rcx
0x1800198a4  jz      loc_180019A19
0x1800198aa  mov     rcx, rax
0x1800198ad  and     rcx, rdx
0x1800198b0  cmp     rcx, rax
0x1800198b3  jnz     loc_180019A19
0x1800198b9  mov     rax, [rbp+100h+arg_30]
0x1800198c0  mov     r14d, 1000000h
0x1800198c6  mov     [rbp+100h+var_148], rax
0x1800198ca  movzx   eax, [rbp+100h+arg_20]
0x1800198d1  mov     [rbp+100h+var_17E], ax
0x1800198d5  mov     [rbp+100h+var_168], r14
0x1800198d9  mov     dword ptr [rbp+100h+SRWLock], r15d
0x1800198dd  mov     [rbp+100h+var_180], r12w
0x1800198e2  mov     [rbp+100h+var_174], r13d
0x1800198e6  call    cs:__imp_GetCurrentThreadId
0x1800198ed  nop     dword ptr [rax+rax+00h]
0x1800198f2  mov     r8, [rbx+110h]
0x1800198f9  xor     edx, edx
0x1800198fb  mov     rcx, [rbp+100h+arg_28]
0x180019902  mov     [rbp+100h+var_178], eax
0x180019905  mov     [rbp+100h+var_38], 8
0x180019910  mov     eax, [r8+48h]
0x180019914  mov     [rbp+100h+var_17C], eax
0x180019917  lea     rax, [rbp+100h+var_168]
0x18001991b  mov     [rbp+100h+var_40], rax
0x180019922  lea     rax, [rbp+100h+var_148]
0x180019926  mov     [rbp+100h+var_50], rax
0x18001992d  mov     [rbp+100h+var_150], r14
0x180019931  mov     [rbp+100h+var_48], 8
0x18001993c  test    rcx, rcx
0x18001993f  jz      short loc_180019957
0x180019941  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019945  inc     rax
0x180019948  cmp     [rcx+rax*2], dx
0x18001994c  jnz     short loc_180019945
0x18001994e  lea     eax, ds:2[rax*2]
0x180019955  jmp     short loc_180019963
0x180019957  lea     rcx, Format
0x18001995e  mov     eax, 2
0x180019963  mov     [rbp+100h+var_58], eax
0x180019969  add     r8, 8
0x18001996d  lea     rax, [rbp+100h+var_17E]
0x180019971  mov     [rbp+100h+var_60], rcx
0x180019978  mov     [rbp+100h+var_70], rax
0x18001997f  xor     r9d, r9d
0x180019982  lea     rax, [rbp+100h+SRWLock]
0x180019986  mov     [rbp+100h+var_54], edx
0x18001998c  mov     [rbp+100h+var_80], rax
0x180019993  lea     rdx, byte_1800690CB
0x18001999a  lea     rax, [rbp+100h+var_180]
0x18001999e  mov     [rbp+100h+var_68], 2
0x1800199a9  mov     [rbp+100h+var_90], rax
0x1800199ad  mov     rcx, rsi
0x1800199b0  lea     rax, [rbp+100h+var_174]
0x1800199b4  mov     [rbp+100h+var_78], 4
0x1800199bf  mov     [rbp+100h+var_A0], rax
0x1800199c3  lea     rax, [rbp+100h+var_178]
0x1800199c7  mov     [rbp+100h+var_B0], rax
0x1800199cb  lea     rax, [rbp+100h+var_17C]
0x1800199cf  mov     [rbp+100h+var_C0], rax
0x1800199d3  lea     rax, [rbp+100h+var_150]
0x1800199d7  mov     [rbp+100h+var_D0], rax
0x1800199db  lea     rax, [rbp+100h+var_F0]
0x1800199df  mov     [rsp+260h+var_238], rax
0x1800199e4  mov     dword ptr [rsp+260h+var_240], 0Ch
0x1800199ec  mov     [rbp+100h+var_88], 2
0x1800199f4  mov     [rbp+100h+var_98], 4
0x1800199fc  mov     [rbp+100h+var_A8], 4
0x180019a04  mov     [rbp+100h+var_B8], 4
0x180019a0c  mov     [rbp+100h+var_C8], 8
0x180019a14  call    _tlgWriteTransfer_EventWriteTransfer
0x180019a19  mov     rcx, rbx
0x180019a1c  call    ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180019a21  mov     rcx, [rbp+100h+var_30]
0x180019a28  xor     rcx, rsp; StackCookie
0x180019a2b  call    __security_check_cookie
0x180019a30  lea     r11, [rsp+260h+var_20]
0x180019a38  mov     rbx, [r11+38h]
0x180019a3c  mov     rsi, [r11+40h]
0x180019a40  mov     rsp, r11
0x180019a43  pop     r15
0x180019a45  pop     r14
0x180019a47  pop     r13
0x180019a49  pop     r12
0x180019a4b  pop     rbp
0x180019a4c  retn
```
