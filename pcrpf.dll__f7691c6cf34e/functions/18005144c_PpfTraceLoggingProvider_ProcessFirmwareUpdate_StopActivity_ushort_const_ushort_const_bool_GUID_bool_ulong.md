# PpfTraceLoggingProvider::ProcessFirmwareUpdate::StopActivity(ushort const *,ushort const *,bool,_GUID,bool,ulong)

- ea: `0x18005144c`
- end: `0x1800518c9`
- name: `?StopActivity@ProcessFirmwareUpdate@PpfTraceLoggingProvider@@QEAAXPEBG0_NU_GUID@@1K@Z`
- size: `1149`
- prototype: `void __fastcall(PpfTraceLoggingProvider::ProcessFirmwareUpdate *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, struct _GUID *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180001640`
- `0x1800027a4`
- `0x180003270`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18005144c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800514cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800516e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800514cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800516e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005174e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005174e`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::ProcessFirmwareUpdate::StopActivity(
        PpfTraceLoggingProvider::ProcessFirmwareUpdate *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct _GUID *a5,
        bool a6,
        unsigned int a7)
{
  __int64 v7; // rsi
  int v11; // eax
  int *v12; // rsi
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  int v18; // edi
  RTL_SRWLOCK *v19; // rcx
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // rsi
  __int64 v22; // rax
  DWORD CurrentThreadId; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  bool v28; // [rsp+E0h] [rbp-80h] BYREF
  _BYTE v29[3]; // [rsp+E1h] [rbp-7Fh] BYREF
  int v30; // [rsp+E4h] [rbp-7Ch] BYREF
  DWORD v31; // [rsp+E8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp-70h] BYREF
  PSRWLOCK v33; // [rsp+F8h] [rbp-68h] BYREF
  unsigned int v34; // [rsp+100h] [rbp-60h] BYREF
  int v35; // [rsp+104h] [rbp-5Ch] BYREF
  int v36; // [rsp+108h] [rbp-58h] BYREF
  int v37; // [rsp+10Ch] [rbp-54h] BYREF
  __int64 v38; // [rsp+110h] [rbp-50h] BYREF
  __int64 v39; // [rsp+118h] [rbp-48h] BYREF
  struct _GUID *v40; // [rsp+120h] [rbp-40h] BYREF
  const wchar_t *v41; // [rsp+128h] [rbp-38h] BYREF
  const wchar_t *v42; // [rsp+130h] [rbp-30h] BYREF
  const wchar_t *v43; // [rsp+138h] [rbp-28h] BYREF
  const unsigned __int16 *v44; // [rsp+140h] [rbp-20h] BYREF
  const wchar_t *v45; // [rsp+148h] [rbp-18h] BYREF
  const unsigned __int16 *v46; // [rsp+150h] [rbp-10h] BYREF
  const unsigned __int16 *v47; // [rsp+158h] [rbp-8h] BYREF
  const wchar_t *v48; // [rsp+160h] [rbp+0h] BYREF
  const unsigned __int16 *v49; // [rsp+168h] [rbp+8h] BYREF
  const unsigned __int16 *v50; // [rsp+170h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+180h] [rbp+20h] BYREF
  __int64 *v52; // [rsp+1A0h] [rbp+40h]
  __int64 v53; // [rsp+1A8h] [rbp+48h]
  int *v54; // [rsp+1B0h] [rbp+50h]
  __int64 v55; // [rsp+1B8h] [rbp+58h]
  DWORD *v56; // [rsp+1C0h] [rbp+60h]
  __int64 v57; // [rsp+1C8h] [rbp+68h]
  const unsigned __int16 *v58; // [rsp+1D0h] [rbp+70h]
  int v59; // [rsp+1D8h] [rbp+78h]
  int v60; // [rsp+1DCh] [rbp+7Ch]
  const unsigned __int16 *v61; // [rsp+1E0h] [rbp+80h]
  int v62; // [rsp+1E8h] [rbp+88h]
  int v63; // [rsp+1ECh] [rbp+8Ch]
  struct _GUID *v64; // [rsp+1F0h] [rbp+90h]
  __int64 v65; // [rsp+1F8h] [rbp+98h]
  bool *v66; // [rsp+200h] [rbp+A0h]
  __int64 v67; // [rsp+208h] [rbp+A8h]
  _BYTE *v68; // [rsp+210h] [rbp+B0h]
  __int64 v69; // [rsp+218h] [rbp+B8h]
  PSRWLOCK *p_SRWLock; // [rsp+220h] [rbp+C0h]
  __int64 v71; // [rsp+228h] [rbp+C8h]
  PSRWLOCK *v72; // [rsp+230h] [rbp+D0h]
  __int64 v73; // [rsp+238h] [rbp+D8h]

  v7 = *((_QWORD *)this + 34);
  v11 = *(_DWORD *)(v7 + 72);
  if ( v11 < 0 && (v12 = (int *)(v7 + 80), v11 == v12[2]) && v12 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v13 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v14 = PpfTraceLoggingProvider::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u )
    {
      v16 = *((_QWORD *)v14 + 3);
      if ( (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0 && (v16 & 0x400000000000LL) == v16 )
      {
        v34 = a7;
        v28 = a6;
        v40 = a5;
        v43 = (const wchar_t *)*((_QWORD *)v12 + 15);
        v44 = (const unsigned __int16 *)*((_QWORD *)v12 + 14);
        v17 = *((_QWORD *)this + 34);
        v35 = v12[26];
        v45 = (const wchar_t *)*((_QWORD *)v12 + 12);
        v46 = (const unsigned __int16 *)*((_QWORD *)v12 + 11);
        v36 = v12[20];
        v47 = (const unsigned __int16 *)*((_QWORD *)v12 + 9);
        v37 = v12[8];
        v48 = (const wchar_t *)*((_QWORD *)v12 + 3);
        v30 = *v12;
        v49 = (const unsigned __int16 *)*((_QWORD *)v12 + 16);
        v31 = v12[16];
        v50 = (const unsigned __int16 *)*((_QWORD *)v12 + 7);
        LODWORD(SRWLock) = v12[2];
        v39 = 0x1000000;
        v29[0] = 1;
        v41 = a3;
        v42 = a2;
        v38 = 0x1000000;
        v33 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v15,
          (__int64)word_180069CA2,
          v17 + 8,
          v15,
          (__int64)&v33,
          (__int64)&v38,
          (__int64)&SRWLock,
          &v50,
          (__int64)&v31,
          &v49,
          (__int64)&v30,
          &v48,
          (__int64)&v37,
          &v47,
          (__int64)&v36,
          &v46,
          &v45,
          (__int64)&v35,
          &v44,
          &v43,
          &v42,
          &v41,
          (__int64 *)&v40,
          (__int64)v29,
          (__int64)&v28,
          (__int64)&v34,
          (__int64)&v39);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v33);
    v18 = 2;
    v19 = v33;
    **((_DWORD **)this + 34) = 2;
    if ( v19 )
      ReleaseSRWLockExclusive(v19);
    v20 = PpfTraceLoggingProvider::Provider();
    v21 = (__int64)v20;
    if ( *(_DWORD *)v20 > 5u )
    {
      v22 = *((_QWORD *)v20 + 3);
      if ( (*(_QWORD *)(v21 + 16) & 0x400000000000LL) != 0 && (v22 & 0x400000000000LL) == v22 )
      {
        LODWORD(SRWLock) = a7;
        v29[0] = a6;
        v33 = (PSRWLOCK)0x1000000;
        v28 = 1;
        CurrentThreadId = GetCurrentThreadId();
        v24 = *((_QWORD *)this + 34);
        v31 = CurrentThreadId;
        v73 = 8;
        v71 = 4;
        v30 = *(_DWORD *)(v24 + 72);
        v72 = &v33;
        p_SRWLock = &SRWLock;
        v68 = v29;
        v66 = &v28;
        v64 = a5;
        v25 = -1;
        v38 = 0x1000000;
        v69 = 1;
        v67 = 1;
        v65 = 16;
        if ( a3 )
        {
          v26 = -1;
          do
            ++v26;
          while ( a3[v26] );
          v27 = 2 * v26 + 2;
        }
        else
        {
          a3 = &Format;
          v27 = 2;
        }
        v61 = a3;
        v62 = v27;
        v63 = 0;
        if ( a2 )
        {
          do
            ++v25;
          while ( a2[v25] );
          v18 = 2 * v25 + 2;
        }
        else
        {
          a2 = &Format;
        }
        v58 = a2;
        v56 = &v31;
        v59 = v18;
        v54 = &v30;
        v60 = 0;
        v52 = &v38;
        v57 = 4;
        v55 = 4;
        v53 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v21,
          (unsigned __int8 *)&dword_180069944,
          (const GUID *)(v24 + 8),
          0,
          0xCu,
          &v51);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18005144c  push    rbp
0x18005144e  push    rbx
0x18005144f  push    rsi
0x180051450  push    rdi
0x180051451  push    r12
0x180051453  push    r13
0x180051455  push    r14
0x180051457  push    r15
0x180051459  lea     rbp, [rsp-0F8h]
0x180051461  sub     rsp, 258h
0x180051468  mov     rax, cs:__security_cookie
0x18005146f  xor     rax, rsp
0x180051472  mov     [rbp+130h+var_50], rax
0x180051479  mov     rsi, [rcx+110h]
0x180051480  xor     r13d, r13d
0x180051483  mov     r15, r8
0x180051486  mov     r14, rdx
0x180051489  mov     rbx, rcx
0x18005148c  mov     eax, [rsi+48h]
0x18005148f  test    eax, eax
0x180051491  jns     loc_1800516C5
0x180051497  add     rsi, 50h ; 'P'
0x18005149b  cmp     eax, [rsi+8]
0x18005149e  jnz     loc_1800516C5
0x1800514a4  test    rsi, rsi
0x1800514a7  jz      loc_1800516C5
0x1800514ad  lea     rdx, [rbp+130h+SRWLock]
0x1800514b1  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800514b6  mov     rax, [rbx+110h]
0x1800514bd  mov     rcx, [rbp+130h+SRWLock]; SRWLock
0x1800514c1  mov     dword ptr [rax], 2
0x1800514c7  test    rcx, rcx
0x1800514ca  jz      short loc_1800514D8
0x1800514cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800514d3  nop     dword ptr [rax+rax+00h]
0x1800514d8  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x1800514dd  mov     r9, rax
0x1800514e0  mov     ecx, [rax]
0x1800514e2  cmp     ecx, 5
0x1800514e5  jbe     loc_18005189D
0x1800514eb  mov     rax, [rax+18h]
0x1800514ef  mov     rdx, 400000000000h
0x1800514f9  mov     rcx, [r9+10h]
0x1800514fd  test    rdx, rcx
0x180051500  jz      loc_18005189D
0x180051506  mov     rcx, rax
0x180051509  and     rcx, rdx
0x18005150c  cmp     rcx, rax
0x18005150f  jnz     loc_18005189D
0x180051515  mov     eax, [rbp+130h+arg_30]
0x18005151b  mov     r12d, 1000000h
0x180051521  mov     [rbp+130h+var_190], eax
0x180051524  mov     al, [rbp+130h+arg_28]
0x18005152a  mov     [rbp+130h+var_1B0], al
0x18005152d  mov     rax, [rbp+130h+arg_20]
0x180051534  mov     [rbp+130h+var_170], rax
0x180051538  mov     rax, [rsi+78h]
0x18005153c  mov     [rbp+130h+var_158], rax
0x180051540  mov     rax, [rsi+70h]
0x180051544  mov     [rbp+130h+var_150], rax
0x180051548  mov     eax, [rsi+68h]
0x18005154b  mov     r8, [rbx+110h]
0x180051552  mov     [rbp+130h+var_18C], eax
0x180051555  add     r8, 8
0x180051559  mov     rax, [rsi+60h]
0x18005155d  mov     [rbp+130h+var_148], rax
0x180051561  mov     rax, [rsi+58h]
0x180051565  mov     [rbp+130h+var_140], rax
0x180051569  mov     eax, [rsi+50h]
0x18005156c  mov     [rbp+130h+var_188], eax
0x18005156f  mov     rax, [rsi+48h]
0x180051573  mov     [rbp+130h+var_138], rax
0x180051577  mov     eax, [rsi+20h]
0x18005157a  mov     [rbp+130h+var_184], eax
0x18005157d  mov     rax, [rsi+18h]
0x180051581  mov     [rbp+130h+var_130], rax
0x180051585  mov     eax, [rsi]
0x180051587  mov     [rbp+130h+var_1AC], eax
0x18005158a  mov     rax, [rsi+80h]
0x180051591  mov     [rbp+130h+var_128], rax
0x180051595  mov     eax, [rsi+40h]
0x180051598  mov     [rbp+130h+var_1A8], eax
0x18005159b  mov     rax, [rsi+38h]
0x18005159f  mov     [rbp+130h+var_120], rax
0x1800515a3  mov     eax, [rsi+8]
0x1800515a6  mov     dword ptr [rbp+130h+SRWLock], eax
0x1800515a9  lea     rax, [rbp+130h+var_178]
0x1800515ad  mov     [rsp+290h+var_1C0], rax
0x1800515b5  lea     rax, [rbp+130h+var_190]
0x1800515b9  mov     [rsp+290h+var_1C8], rax
0x1800515c1  lea     rax, [rbp+130h+var_1B0]
0x1800515c5  mov     [rsp+290h+var_1D0], rax
0x1800515cd  lea     rax, [rbp+130h+var_1AF]
0x1800515d1  mov     [rsp+290h+var_1D8], rax
0x1800515d9  lea     rax, [rbp+130h+var_170]
0x1800515dd  mov     [rsp+290h+var_1E0], rax
0x1800515e5  lea     rax, [rbp+130h+var_168]
0x1800515e9  mov     [rsp+290h+var_1E8], rax
0x1800515f1  lea     rax, [rbp+130h+var_160]
0x1800515f5  mov     [rsp+290h+var_1F0], rax
0x1800515fd  lea     rax, [rbp+130h+var_158]
0x180051601  mov     [rsp+290h+var_1F8], rax
0x180051609  lea     rax, [rbp+130h+var_150]
0x18005160d  mov     [rsp+290h+var_200], rax
0x180051615  lea     rax, [rbp+130h+var_18C]
0x180051619  mov     [rsp+290h+var_208], rax
0x180051621  lea     rax, [rbp+130h+var_148]
0x180051625  mov     [rsp+290h+var_210], rax
0x18005162d  lea     rax, [rbp+130h+var_140]
0x180051631  mov     [rsp+290h+var_218], rax
0x180051636  lea     rax, [rbp+130h+var_188]
0x18005163a  mov     [rsp+290h+var_220], rax
0x18005163f  lea     rax, [rbp+130h+var_138]
0x180051643  mov     [rsp+290h+var_228], rax
0x180051648  lea     rax, [rbp+130h+var_184]
0x18005164c  mov     [rsp+290h+var_230], rax
0x180051651  lea     rax, [rbp+130h+var_130]
0x180051655  mov     [rsp+290h+var_238], rax
0x18005165a  lea     rax, [rbp+130h+var_1AC]
0x18005165e  mov     [rsp+290h+var_240], rax
0x180051663  lea     rax, [rbp+130h+var_128]
0x180051667  mov     [rsp+290h+var_248], rax
0x18005166c  lea     rax, [rbp+130h+var_1A8]
0x180051670  mov     [rsp+290h+var_250], rax
0x180051675  mov     [rbp+130h+var_178], r12
0x180051679  mov     [rbp+130h+var_1AF], 1
0x18005167d  mov     [rbp+130h+var_168], r15
0x180051681  mov     [rbp+130h+var_160], r14
0x180051685  mov     [rbp+130h+var_180], r12
0x180051689  mov     [rbp+130h+var_198], r12
0x18005168d  lea     rax, [rbp+130h+var_120]
0x180051691  mov     rcx, r9
0x180051694  mov     [rsp+290h+var_258], rax
0x180051699  lea     rdx, word_180069CA2
0x1800516a0  lea     rax, [rbp+130h+SRWLock]
0x1800516a4  mov     [rsp+290h+var_260], rax
0x1800516a9  lea     rax, [rbp+130h+var_180]
0x1800516ad  mov     [rsp+290h+var_268], rax
0x1800516b2  lea     rax, [rbp+130h+var_198]
0x1800516b6  mov     [rsp+290h+var_270], rax
0x1800516bb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U6@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645666AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@843@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800516c0  jmp     loc_18005189D
0x1800516c5  lea     rdx, [rbp+130h+var_198]
0x1800516c9  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800516ce  mov     rax, [rbx+110h]
0x1800516d5  mov     edi, 2
0x1800516da  mov     rcx, [rbp+130h+var_198]; SRWLock
0x1800516de  mov     [rax], edi
0x1800516e0  test    rcx, rcx
0x1800516e3  jz      short loc_1800516F1
0x1800516e5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800516ec  nop     dword ptr [rax+rax+00h]
0x1800516f1  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x1800516f6  mov     rsi, rax
0x1800516f9  mov     ecx, [rax]
0x1800516fb  cmp     ecx, 5
0x1800516fe  jbe     loc_18005189D
0x180051704  mov     rax, [rax+18h]
0x180051708  mov     rdx, 400000000000h
0x180051712  mov     rcx, [rsi+10h]
0x180051716  test    rdx, rcx
0x180051719  jz      loc_18005189D
0x18005171f  mov     rcx, rax
0x180051722  and     rcx, rdx
0x180051725  cmp     rcx, rax
0x180051728  jnz     loc_18005189D
0x18005172e  mov     eax, [rbp+130h+arg_30]
0x180051734  mov     r12d, 1000000h
0x18005173a  mov     dword ptr [rbp+130h+SRWLock], eax
0x18005173d  mov     al, [rbp+130h+arg_28]
0x180051743  mov     [rbp+130h+var_1AF], al
0x180051746  mov     [rbp+130h+var_198], r12
0x18005174a  mov     [rbp+130h+var_1B0], 1
0x18005174e  call    cs:__imp_GetCurrentThreadId
0x180051755  nop     dword ptr [rax+rax+00h]
0x18005175a  mov     r8, [rbx+110h]
0x180051761  mov     [rbp+130h+var_1A8], eax
0x180051764  mov     [rbp+130h+var_58], 8
0x18005176f  mov     [rbp+130h+var_68], 4
0x18005177a  mov     eax, [r8+48h]
0x18005177e  mov     [rbp+130h+var_1AC], eax
0x180051781  lea     rax, [rbp+130h+var_198]
0x180051785  mov     [rbp+130h+var_60], rax
0x18005178c  lea     rax, [rbp+130h+SRWLock]
0x180051790  mov     [rbp+130h+var_70], rax
0x180051797  lea     rax, [rbp+130h+var_1AF]
0x18005179b  mov     [rbp+130h+var_80], rax
0x1800517a2  lea     rax, [rbp+130h+var_1B0]
0x1800517a6  mov     [rbp+130h+var_90], rax
0x1800517ad  mov     rax, [rbp+130h+arg_20]
0x1800517b4  mov     [rbp+130h+var_A0], rax
0x1800517bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800517bf  mov     [rbp+130h+var_180], r12
0x1800517c3  mov     [rbp+130h+var_78], 1
0x1800517ce  mov     [rbp+130h+var_88], 1
0x1800517d9  mov     [rbp+130h+var_98], 10h
0x1800517e4  test    r15, r15
0x1800517e7  jz      short loc_1800517FF
0x1800517e9  mov     rcx, rax
0x1800517ec  inc     rcx
0x1800517ef  cmp     [r15+rcx*2], r13w
0x1800517f4  jnz     short loc_1800517EC
0x1800517f6  lea     ecx, ds:2[rcx*2]
0x1800517fd  jmp     short loc_180051808
0x1800517ff  lea     r15, Format
0x180051806  mov     ecx, edi
0x180051808  mov     [rbp+130h+var_B0], r15
0x18005180f  mov     [rbp+130h+var_A8], ecx
0x180051815  mov     [rbp+130h+var_A4], r13d
0x18005181c  test    r14, r14
0x18005181f  jz      short loc_180051834
0x180051821  inc     rax
0x180051824  cmp     [r14+rax*2], r13w
0x180051829  jnz     short loc_180051821
0x18005182b  lea     edi, ds:2[rax*2]
0x180051832  jmp     short loc_18005183B
0x180051834  lea     r14, Format
0x18005183b  lea     rax, [rbp+130h+var_1A8]
0x18005183f  mov     [rbp+130h+var_C0], r14
0x180051843  mov     [rbp+130h+var_D0], rax
0x180051847  lea     rdx, dword_180069944
0x18005184e  lea     rax, [rbp+130h+var_1AC]
0x180051852  mov     [rbp+130h+var_B8], edi
0x180051855  mov     [rbp+130h+var_E0], rax
0x180051859  add     r8, 8
0x18005185d  lea     rax, [rbp+130h+var_180]
0x180051861  mov     [rbp+130h+var_B4], r13d
0x180051865  mov     [rbp+130h+var_F0], rax
0x180051869  xor     r9d, r9d
0x18005186c  lea     rax, [rbp+130h+var_110]
0x180051870  mov     [rbp+130h+var_C8], 4
0x180051878  mov     [rsp+290h+var_268], rax
0x18005187d  mov     rcx, rsi
0x180051880  mov     dword ptr [rsp+290h+var_270], 0Ch
0x180051888  mov     [rbp+130h+var_D8], 4
0x180051890  mov     [rbp+130h+var_E8], 8
0x180051898  call    _tlgWriteTransfer_EventWriteTransfer
0x18005189d  mov     rcx, rbx
0x1800518a0  call    ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800518a5  mov     rcx, [rbp+130h+var_50]
0x1800518ac  xor     rcx, rsp; StackCookie
0x1800518af  call    __security_check_cookie
0x1800518b4  add     rsp, 258h
0x1800518bb  pop     r15
0x1800518bd  pop     r14
0x1800518bf  pop     r13
0x1800518c1  pop     r12
0x1800518c3  pop     rdi
0x1800518c4  pop     rsi
0x1800518c5  pop     rbx
0x1800518c6  pop     rbp
0x1800518c7  retn
```
