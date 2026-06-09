# PpfTraceLoggingProvider::PpfStageTransformActivity::StopActivity(ushort const *,ushort,long)

- ea: `0x18001a93c`
- end: `0x18001acfd`
- name: `?StopActivity@PpfStageTransformActivity@PpfTraceLoggingProvider@@QEAAXPEBGGJ@Z`
- size: `961`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfStageTransformActivity *this, const unsigned __int16 *, __int16, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001bab0`
- `0x18001bb90`

## callees

- `0x180001640`
- `0x180001d90`
- `0x180003270`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18001a93c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ab96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ab96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001abf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001abf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfStageTransformActivity::StopActivity(
        PpfTraceLoggingProvider::PpfStageTransformActivity *this,
        const unsigned __int16 *a2,
        __int16 a3,
        int a4)
{
  __int64 v4; // rsi
  int v9; // eax
  int *v10; // rsi
  RTL_SRWLOCK *v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  int v16; // edi
  RTL_SRWLOCK *v17; // rcx
  const struct _tlgProvider_t *v18; // rax
  const struct _tlgProvider_t *v19; // rsi
  __int64 v20; // rax
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  __int64 v23; // rdi
  _WORD v24[2]; // [rsp+C0h] [rbp-80h] BYREF
  int v25; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v26; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v28; // [rsp+D8h] [rbp-68h] BYREF
  int v29; // [rsp+E0h] [rbp-60h] BYREF
  int v30; // [rsp+E4h] [rbp-5Ch] BYREF
  int v31; // [rsp+E8h] [rbp-58h] BYREF
  int v32; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v35; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v36; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v37; // [rsp+110h] [rbp-30h] BYREF
  const wchar_t *v38; // [rsp+118h] [rbp-28h] BYREF
  const unsigned __int16 *v39; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v40; // [rsp+128h] [rbp-18h] BYREF
  const wchar_t *v41; // [rsp+130h] [rbp-10h] BYREF
  const unsigned __int16 *v42; // [rsp+138h] [rbp-8h] BYREF
  const unsigned __int16 *v43; // [rsp+140h] [rbp+0h] BYREF
  char v44[32]; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v45; // [rsp+170h] [rbp+30h]
  __int64 v46; // [rsp+178h] [rbp+38h]
  int *v47; // [rsp+180h] [rbp+40h]
  __int64 v48; // [rsp+188h] [rbp+48h]
  DWORD *v49; // [rsp+190h] [rbp+50h]
  __int64 v50; // [rsp+198h] [rbp+58h]
  const unsigned __int16 *v51; // [rsp+1A0h] [rbp+60h]
  int v52; // [rsp+1A8h] [rbp+68h]
  int v53; // [rsp+1ACh] [rbp+6Ch]
  _WORD *v54; // [rsp+1B0h] [rbp+70h]
  __int64 v55; // [rsp+1B8h] [rbp+78h]
  PSRWLOCK *p_SRWLock; // [rsp+1C0h] [rbp+80h]
  __int64 v57; // [rsp+1C8h] [rbp+88h]
  PSRWLOCK *v58; // [rsp+1D0h] [rbp+90h]
  __int64 v59; // [rsp+1D8h] [rbp+98h]

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v11 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = PpfTraceLoggingProvider::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u )
    {
      v14 = *((_QWORD *)v12 + 3);
      if ( (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0 && (v14 & 0x400000000000LL) == v14 )
      {
        v36 = (const wchar_t *)*((_QWORD *)v10 + 15);
        v37 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
        v30 = v10[26];
        v15 = *((_QWORD *)this + 34);
        v38 = (const wchar_t *)*((_QWORD *)v10 + 12);
        v39 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
        v31 = v10[20];
        v40 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
        v32 = v10[8];
        v41 = (const wchar_t *)*((_QWORD *)v10 + 3);
        v25 = *v10;
        v42 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
        v26 = v10[16];
        v43 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v34 = 0x1000000;
        v29 = a4;
        v24[0] = a3;
        v35 = a2;
        v33 = 0x1000000;
        v28 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v13,
          (__int64)byte_180068DF5,
          v15 + 8,
          v13,
          (__int64)&v28,
          (__int64)&v33,
          (__int64)&SRWLock,
          &v43,
          (__int64)&v26,
          &v42,
          (__int64)&v25,
          &v41,
          (__int64)&v32,
          &v40,
          (__int64)&v31,
          &v39,
          &v38,
          (__int64)&v30,
          &v37,
          &v36,
          &v35,
          (__int64)v24,
          (__int64)&v29,
          (__int64)&v34);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v28);
    v16 = 2;
    v17 = v28;
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v18 = PpfTraceLoggingProvider::Provider();
    v19 = v18;
    if ( *(_DWORD *)v18 > 5u )
    {
      v20 = *((_QWORD *)v18 + 3);
      if ( (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0 && (v20 & 0x400000000000LL) == v20 )
      {
        LODWORD(SRWLock) = a4;
        v28 = (PSRWLOCK)0x1000000;
        v24[0] = a3;
        CurrentThreadId = GetCurrentThreadId();
        v22 = *((_QWORD *)this + 34);
        v26 = CurrentThreadId;
        v59 = 8;
        v57 = 4;
        v25 = *(_DWORD *)(v22 + 72);
        v58 = &v28;
        p_SRWLock = &SRWLock;
        v54 = v24;
        v33 = 0x1000000;
        v55 = 2;
        if ( a2 )
        {
          v23 = -1;
          do
            ++v23;
          while ( a2[v23] );
          v16 = 2 * v23 + 2;
        }
        else
        {
          a2 = &Format;
        }
        v53 = 0;
        v49 = &v26;
        v51 = a2;
        v47 = &v25;
        v52 = v16;
        v45 = &v33;
        v50 = 4;
        v48 = 4;
        v46 = 8;
        tlgWriteTransfer_EventWriteTransfer(v19, &word_18006828E, v22 + 8, 0, 9, v44);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001a93c  push    rbp
0x18001a93e  push    rbx
0x18001a93f  push    rsi
0x18001a940  push    rdi
0x18001a941  push    r12
0x18001a943  push    r13
0x18001a945  push    r14
0x18001a947  push    r15
0x18001a949  lea     rbp, [rsp-0B8h]
0x18001a951  sub     rsp, 1F8h
0x18001a958  mov     rax, cs:__security_cookie
0x18001a95f  xor     rax, rsp
0x18001a962  mov     [rbp+0F0h+var_50], rax
0x18001a969  mov     rsi, [rcx+110h]
0x18001a970  mov     r12d, r9d
0x18001a973  movzx   r13d, r8w
0x18001a977  mov     r14, rdx
0x18001a97a  mov     rbx, rcx
0x18001a97d  mov     eax, [rsi+48h]
0x18001a980  test    eax, eax
0x18001a982  jns     loc_18001AB76
0x18001a988  add     rsi, 50h ; 'P'
0x18001a98c  cmp     eax, [rsi+8]
0x18001a98f  jnz     loc_18001AB76
0x18001a995  test    rsi, rsi
0x18001a998  jz      loc_18001AB76
0x18001a99e  lea     rdx, [rbp+0F0h+SRWLock]
0x18001a9a2  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a9a7  mov     rax, [rbx+110h]
0x18001a9ae  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x18001a9b2  mov     dword ptr [rax], 2
0x18001a9b8  test    rcx, rcx
0x18001a9bb  jz      short loc_18001A9C9
0x18001a9bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a9c4  nop     dword ptr [rax+rax+00h]
0x18001a9c9  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001a9ce  mov     r9, rax
0x18001a9d1  mov     ecx, [rax]
0x18001a9d3  cmp     ecx, 5
0x18001a9d6  jbe     loc_18001ACD1
0x18001a9dc  mov     rax, [rax+18h]
0x18001a9e0  mov     rdx, 400000000000h
0x18001a9ea  mov     rcx, [r9+10h]
0x18001a9ee  test    rdx, rcx
0x18001a9f1  jz      loc_18001ACD1
0x18001a9f7  mov     rcx, rax
0x18001a9fa  and     rcx, rdx
0x18001a9fd  cmp     rcx, rax
0x18001aa00  jnz     loc_18001ACD1
0x18001aa06  mov     rax, [rsi+78h]
0x18001aa0a  lea     rdx, byte_180068DF5
0x18001aa11  mov     [rbp+0F0h+var_128], rax
0x18001aa15  mov     r15d, 1000000h
0x18001aa1b  mov     rax, [rsi+70h]
0x18001aa1f  mov     rcx, r9
0x18001aa22  mov     [rbp+0F0h+var_120], rax
0x18001aa26  mov     eax, [rsi+68h]
0x18001aa29  mov     [rbp+0F0h+var_14C], eax
0x18001aa2c  mov     rax, [rsi+60h]
0x18001aa30  mov     r8, [rbx+110h]
0x18001aa37  mov     [rbp+0F0h+var_118], rax
0x18001aa3b  add     r8, 8
0x18001aa3f  mov     rax, [rsi+58h]
0x18001aa43  mov     [rbp+0F0h+var_110], rax
0x18001aa47  mov     eax, [rsi+50h]
0x18001aa4a  mov     [rbp+0F0h+var_148], eax
0x18001aa4d  mov     rax, [rsi+48h]
0x18001aa51  mov     [rbp+0F0h+var_108], rax
0x18001aa55  mov     eax, [rsi+20h]
0x18001aa58  mov     [rbp+0F0h+var_144], eax
0x18001aa5b  mov     rax, [rsi+18h]
0x18001aa5f  mov     [rbp+0F0h+var_100], rax
0x18001aa63  mov     eax, [rsi]
0x18001aa65  mov     [rbp+0F0h+var_16C], eax
0x18001aa68  mov     rax, [rsi+80h]
0x18001aa6f  mov     [rbp+0F0h+var_F8], rax
0x18001aa73  mov     eax, [rsi+40h]
0x18001aa76  mov     [rbp+0F0h+var_168], eax
0x18001aa79  mov     rax, [rsi+38h]
0x18001aa7d  mov     [rbp+0F0h+var_F0], rax
0x18001aa81  mov     eax, [rsi+8]
0x18001aa84  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x18001aa87  lea     rax, [rbp+0F0h+var_138]
0x18001aa8b  mov     [rsp+230h+var_178], rax
0x18001aa93  lea     rax, [rbp+0F0h+var_150]
0x18001aa97  mov     [rsp+230h+var_180], rax
0x18001aa9f  lea     rax, [rbp+0F0h+var_170]
0x18001aaa3  mov     [rsp+230h+var_188], rax
0x18001aaab  lea     rax, [rbp+0F0h+var_130]
0x18001aaaf  mov     [rsp+230h+var_190], rax
0x18001aab7  lea     rax, [rbp+0F0h+var_128]
0x18001aabb  mov     [rsp+230h+var_198], rax
0x18001aac3  lea     rax, [rbp+0F0h+var_120]
0x18001aac7  mov     [rsp+230h+var_1A0], rax
0x18001aacf  lea     rax, [rbp+0F0h+var_14C]
0x18001aad3  mov     [rsp+230h+var_1A8], rax
0x18001aadb  lea     rax, [rbp+0F0h+var_118]
0x18001aadf  mov     [rsp+230h+var_1B0], rax
0x18001aae7  lea     rax, [rbp+0F0h+var_110]
0x18001aaeb  mov     [rsp+230h+var_1B8], rax
0x18001aaf0  lea     rax, [rbp+0F0h+var_148]
0x18001aaf4  mov     [rsp+230h+var_1C0], rax
0x18001aaf9  lea     rax, [rbp+0F0h+var_108]
0x18001aafd  mov     [rsp+230h+var_1C8], rax
0x18001ab02  lea     rax, [rbp+0F0h+var_144]
0x18001ab06  mov     [rsp+230h+var_1D0], rax
0x18001ab0b  lea     rax, [rbp+0F0h+var_100]
0x18001ab0f  mov     [rsp+230h+var_1D8], rax
0x18001ab14  lea     rax, [rbp+0F0h+var_16C]
0x18001ab18  mov     [rsp+230h+var_1E0], rax
0x18001ab1d  lea     rax, [rbp+0F0h+var_F8]
0x18001ab21  mov     [rsp+230h+var_1E8], rax
0x18001ab26  lea     rax, [rbp+0F0h+var_168]
0x18001ab2a  mov     [rsp+230h+var_1F0], rax
0x18001ab2f  lea     rax, [rbp+0F0h+var_F0]
0x18001ab33  mov     [rsp+230h+var_1F8], rax
0x18001ab38  lea     rax, [rbp+0F0h+SRWLock]
0x18001ab3c  mov     [rsp+230h+var_200], rax
0x18001ab41  lea     rax, [rbp+0F0h+var_140]
0x18001ab45  mov     [rsp+230h+var_208], rax
0x18001ab4a  lea     rax, [rbp+0F0h+var_158]
0x18001ab4e  mov     [rsp+230h+var_210], rax
0x18001ab53  mov     [rbp+0F0h+var_138], r15
0x18001ab57  mov     [rbp+0F0h+var_150], r12d
0x18001ab5b  mov     [rbp+0F0h+var_170], r13w
0x18001ab60  mov     [rbp+0F0h+var_130], r14
0x18001ab64  mov     [rbp+0F0h+var_140], r15
0x18001ab68  mov     [rbp+0F0h+var_158], r15
0x18001ab6c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$01@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566AEBU?$_tlgWrapperByVal@$01@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001ab71  jmp     loc_18001ACD1
0x18001ab76  lea     rdx, [rbp+0F0h+var_158]
0x18001ab7a  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ab7f  mov     rax, [rbx+110h]
0x18001ab86  mov     edi, 2
0x18001ab8b  mov     rcx, [rbp+0F0h+var_158]; SRWLock
0x18001ab8f  mov     [rax], edi
0x18001ab91  test    rcx, rcx
0x18001ab94  jz      short loc_18001ABA2
0x18001ab96  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ab9d  nop     dword ptr [rax+rax+00h]
0x18001aba2  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001aba7  mov     rsi, rax
0x18001abaa  mov     ecx, [rax]
0x18001abac  cmp     ecx, 5
0x18001abaf  jbe     loc_18001ACD1
0x18001abb5  mov     rax, [rax+18h]
0x18001abb9  mov     rdx, 400000000000h
0x18001abc3  mov     rcx, [rsi+10h]
0x18001abc7  test    rdx, rcx
0x18001abca  jz      loc_18001ACD1
0x18001abd0  mov     rcx, rax
0x18001abd3  and     rcx, rdx
0x18001abd6  cmp     rcx, rax
0x18001abd9  jnz     loc_18001ACD1
0x18001abdf  mov     r15d, 1000000h
0x18001abe5  mov     dword ptr [rbp+0F0h+SRWLock], r12d
0x18001abe9  mov     [rbp+0F0h+var_158], r15
0x18001abed  mov     [rbp+0F0h+var_170], r13w
0x18001abf2  call    cs:__imp_GetCurrentThreadId
0x18001abf9  nop     dword ptr [rax+rax+00h]
0x18001abfe  mov     r8, [rbx+110h]
0x18001ac05  xor     ecx, ecx
0x18001ac07  mov     [rbp+0F0h+var_168], eax
0x18001ac0a  mov     [rbp+0F0h+var_58], 8
0x18001ac15  mov     [rbp+0F0h+var_68], 4
0x18001ac20  mov     eax, [r8+48h]
0x18001ac24  mov     [rbp+0F0h+var_16C], eax
0x18001ac27  lea     rax, [rbp+0F0h+var_158]
0x18001ac2b  mov     [rbp+0F0h+var_60], rax
0x18001ac32  lea     rax, [rbp+0F0h+SRWLock]
0x18001ac36  mov     [rbp+0F0h+var_70], rax
0x18001ac3d  lea     rax, [rbp+0F0h+var_170]
0x18001ac41  mov     [rbp+0F0h+var_80], rax
0x18001ac45  mov     [rbp+0F0h+var_140], r15
0x18001ac49  mov     [rbp+0F0h+var_78], rdi
0x18001ac4d  test    r14, r14
0x18001ac50  jz      short loc_18001AC69
0x18001ac52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ac56  inc     rdi
0x18001ac59  cmp     [r14+rdi*2], cx
0x18001ac5e  jnz     short loc_18001AC56
0x18001ac60  lea     edi, ds:2[rdi*2]
0x18001ac67  jmp     short loc_18001AC70
0x18001ac69  lea     r14, Format
0x18001ac70  lea     rax, [rbp+0F0h+var_168]
0x18001ac74  mov     [rbp+0F0h+var_84], ecx
0x18001ac77  mov     [rbp+0F0h+var_A0], rax
0x18001ac7b  lea     rdx, word_18006828E
0x18001ac82  lea     rax, [rbp+0F0h+var_16C]
0x18001ac86  mov     [rbp+0F0h+var_90], r14
0x18001ac8a  mov     [rbp+0F0h+var_B0], rax
0x18001ac8e  add     r8, 8
0x18001ac92  lea     rax, [rbp+0F0h+var_140]
0x18001ac96  mov     [rbp+0F0h+var_88], edi
0x18001ac99  mov     [rbp+0F0h+var_C0], rax
0x18001ac9d  xor     r9d, r9d
0x18001aca0  lea     rax, [rbp+0F0h+var_E0]
0x18001aca4  mov     [rbp+0F0h+var_98], 4
0x18001acac  mov     [rsp+230h+var_208], rax
0x18001acb1  mov     rcx, rsi
0x18001acb4  mov     dword ptr [rsp+230h+var_210], 9
0x18001acbc  mov     [rbp+0F0h+var_A8], 4
0x18001acc4  mov     [rbp+0F0h+var_B8], 8
0x18001accc  call    _tlgWriteTransfer_EventWriteTransfer
0x18001acd1  mov     rcx, rbx
0x18001acd4  call    ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001acd9  mov     rcx, [rbp+0F0h+var_50]
0x18001ace0  xor     rcx, rsp; StackCookie
0x18001ace3  call    __security_check_cookie
0x18001ace8  add     rsp, 1F8h
0x18001acef  pop     r15
0x18001acf1  pop     r14
0x18001acf3  pop     r13
0x18001acf5  pop     r12
0x18001acf7  pop     rdi
0x18001acf8  pop     rsi
0x18001acf9  pop     rbx
0x18001acfa  pop     rbp
0x18001acfb  retn
```
