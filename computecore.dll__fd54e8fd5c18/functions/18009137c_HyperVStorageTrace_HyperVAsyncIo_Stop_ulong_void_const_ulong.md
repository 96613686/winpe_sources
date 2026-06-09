# HyperVStorageTrace::HyperVAsyncIo::Stop(ulong,void const *,ulong)

- ea: `0x18009137c`
- end: `0x180091b19`
- name: `?Stop@HyperVAsyncIo@HyperVStorageTrace@@QEAAXKPEBXK@Z`
- size: `1949`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVAsyncIo *__hidden this, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18008ff70`

## callees

- `0x1800016ec`
- `0x180003368`
- `0x1800067c0`
- `0x180007dbc`
- `0x180007e24`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x180081f2c`
- `0x180082140`
- `0x18009137c`
- `0x180092168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800914e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800917eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800914e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800917eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800918a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800918a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HyperVStorageTrace::HyperVAsyncIo::Stop(
        HyperVStorageTrace::HyperVAsyncIo *this,
        signed int a2,
        const void *a3,
        unsigned int a4)
{
  char v8; // si
  _DWORD *v9; // rax
  int IsDebugTraceEnabled; // r14d
  _DWORD *v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // rsi
  __int64 v16; // r9
  __int64 v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  int v20; // r14d
  __int64 v21; // r12
  __int64 *v22; // rcx
  __int64 *v23; // rsi
  __int64 *v24; // rdi
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // ecx
  PSRWLOCK SRWLock; // [rsp+138h] [rbp-78h] BYREF
  int v29; // [rsp+140h] [rbp-70h] BYREF
  DWORD CurrentThreadId; // [rsp+144h] [rbp-6Ch] BYREF
  __int64 v31; // [rsp+148h] [rbp-68h] BYREF
  PSRWLOCK v32; // [rsp+150h] [rbp-60h] BYREF
  unsigned int v33; // [rsp+158h] [rbp-58h] BYREF
  signed int v34; // [rsp+15Ch] [rbp-54h] BYREF
  int v35; // [rsp+160h] [rbp-50h] BYREF
  int v36; // [rsp+164h] [rbp-4Ch] BYREF
  int v37; // [rsp+168h] [rbp-48h] BYREF
  int v38; // [rsp+16Ch] [rbp-44h] BYREF
  __int64 v39; // [rsp+170h] [rbp-40h] BYREF
  __int64 v40; // [rsp+178h] [rbp-38h] BYREF
  __int64 v41; // [rsp+180h] [rbp-30h] BYREF
  __int64 v42; // [rsp+188h] [rbp-28h] BYREF
  __int64 v43; // [rsp+190h] [rbp-20h] BYREF
  __int64 v44; // [rsp+198h] [rbp-18h] BYREF
  __int64 v45; // [rsp+1A0h] [rbp-10h] BYREF
  __int64 v46; // [rsp+1A8h] [rbp-8h] BYREF
  __int64 v47; // [rsp+1B0h] [rbp+0h] BYREF
  __int64 v48; // [rsp+1B8h] [rbp+8h] BYREF
  __int64 v49; // [rsp+1C0h] [rbp+10h] BYREF
  __int64 v50; // [rsp+1C8h] [rbp+18h] BYREF
  __int64 v51; // [rsp+1D0h] [rbp+20h] BYREF
  __int64 v52; // [rsp+1D8h] [rbp+28h] BYREF
  __int64 v53; // [rsp+1E0h] [rbp+30h] BYREF
  __int64 v54; // [rsp+1E8h] [rbp+38h] BYREF
  __int64 v55; // [rsp+1F0h] [rbp+40h] BYREF
  __int64 v56; // [rsp+1F8h] [rbp+48h] BYREF
  __int64 v57; // [rsp+200h] [rbp+50h] BYREF
  __int64 v58; // [rsp+208h] [rbp+58h] BYREF
  __int64 v59; // [rsp+210h] [rbp+60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+220h] [rbp+70h] BYREF
  __int64 *v61; // [rsp+240h] [rbp+90h]
  __int64 v62; // [rsp+248h] [rbp+98h]
  int *v63; // [rsp+250h] [rbp+A0h]
  __int64 v64; // [rsp+258h] [rbp+A8h]
  DWORD *p_CurrentThreadId; // [rsp+260h] [rbp+B0h]
  __int64 v66; // [rsp+268h] [rbp+B8h]
  char *v67; // [rsp+270h] [rbp+C0h]
  __int64 v68; // [rsp+278h] [rbp+C8h]
  char *v69; // [rsp+280h] [rbp+D0h]
  __int64 v70; // [rsp+288h] [rbp+D8h]
  __int64 *v71; // [rsp+290h] [rbp+E0h]
  int v72; // [rsp+298h] [rbp+E8h]
  int v73; // [rsp+29Ch] [rbp+ECh]
  __int64 *v74; // [rsp+2A0h] [rbp+F0h]
  __int64 v75; // [rsp+2A8h] [rbp+F8h]
  __int64 *v76; // [rsp+2B0h] [rbp+100h]
  int v77; // [rsp+2B8h] [rbp+108h]
  int v78; // [rsp+2BCh] [rbp+10Ch]
  __int64 *v79; // [rsp+2C0h] [rbp+110h]
  __int64 v80; // [rsp+2C8h] [rbp+118h]
  __int64 *v81; // [rsp+2D0h] [rbp+120h]
  __int64 v82; // [rsp+2D8h] [rbp+128h]
  __int64 *v83; // [rsp+2E0h] [rbp+130h]
  __int64 v84; // [rsp+2E8h] [rbp+138h]
  __int64 *v85; // [rsp+2F0h] [rbp+140h]
  __int64 v86; // [rsp+2F8h] [rbp+148h]
  char *v87; // [rsp+300h] [rbp+150h]
  __int64 v88; // [rsp+308h] [rbp+158h]
  __int64 *v89; // [rsp+310h] [rbp+160h]
  __int64 v90; // [rsp+318h] [rbp+168h]
  PSRWLOCK *v91; // [rsp+320h] [rbp+170h]
  __int64 v92; // [rsp+328h] [rbp+178h]
  __int64 *v93; // [rsp+330h] [rbp+180h]
  __int64 v94; // [rsp+338h] [rbp+188h]
  PSRWLOCK *p_SRWLock; // [rsp+340h] [rbp+190h]
  __int64 v96; // [rsp+348h] [rbp+198h]

  LODWORD(SRWLock) = a4;
  v8 = 1;
  if ( (unsigned int)(*((_DWORD *)this + 102) - 4) <= 1 )
  {
    v9 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( v9 )
    {
      if ( *v9 && **((_DWORD **)this + 34) == 1 )
        HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(this, L"ActivityStop", a3, a4);
    }
  }
  IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC020u);
  v11 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( !v11 || !*v11 )
    v8 = 0;
  v12 = -1;
  if ( IsDebugTraceEnabled || v8 )
  {
    if ( __TSS0__M___Stop_HyperVAsyncIo_HyperVStorageTrace__QEAAXKPEBXK_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                            + (unsigned int)tls_index)
                                                                                          + 16LL) )
    {
      Init_thread_header(&__TSS0__M___Stop_HyperVAsyncIo_HyperVStorageTrace__QEAAXKPEBXK_Z_4HA);
      if ( __TSS0__M___Stop_HyperVAsyncIo_HyperVStorageTrace__QEAAXKPEBXK_Z_4HA == -1 )
      {
        byte_1800E315C = IsDebugTraceEnabled != 0;
        byte_1800E315D = v8;
        Init_thread_footer(&__TSS0__M___Stop_HyperVAsyncIo_HyperVStorageTrace__QEAAXKPEBXK_Z_4HA);
      }
    }
    HvsDebugTraceInternal(
      0xC020u,
      (const struct HvsDebugTraceParameters *)&`HyperVStorageTrace::HyperVAsyncIo::Stop'::`12'::traceParameters);
  }
  v13 = *((_QWORD *)this + 34);
  v14 = *(_DWORD *)(v13 + 72);
  if ( v14 < 0 && (v15 = v13 + 80, v14 == *(_DWORD *)(v15 + 8)) && v15 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v16 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v16 > 5u
      && (*(_QWORD *)(v16 + 16) & 0xA0) != 0
      && (*(_QWORD *)(v16 + 24) & 0xA0LL) == *(_QWORD *)(v16 + 24) )
    {
      v33 = a4;
      v53 = (__int64)a3;
      if ( a2 > 0 )
        a2 = (unsigned __int16)a2 | 0x80070000;
      v34 = a2;
      v17 = *((_QWORD *)this + 56);
      v54 = *(_QWORD *)(v17 + 24);
      v35 = *(_DWORD *)(v17 + 20);
      v36 = *(_DWORD *)(v17 + 16);
      v55 = *(_QWORD *)(v17 + 8);
      v56 = *(_QWORD *)v17;
      v57 = v17;
      v18 = (_QWORD *)((char *)this + 416);
      if ( *((_QWORD *)this + 55) > 7u )
        v18 = (_QWORD *)*v18;
      v58 = (__int64)v18;
      v59 = *((_QWORD *)this + 50);
      v19 = (_QWORD *)((char *)this + 368);
      if ( *((_QWORD *)this + 49) > 7u )
        v19 = (_QWORD *)*v19;
      v46 = (__int64)v19;
      v47 = (__int64)this + 352;
      v48 = (__int64)this + 336;
      v49 = *(_QWORD *)(v15 + 48);
      v37 = *(_DWORD *)(v15 + 68);
      v38 = *(_DWORD *)(v15 + 16);
      v50 = *(_QWORD *)(v15 + 120);
      v51 = *(_QWORD *)(v15 + 112);
      v29 = *(_DWORD *)(v15 + 104);
      v52 = *(_QWORD *)(v15 + 96);
      v39 = *(_QWORD *)(v15 + 88);
      CurrentThreadId = *(_DWORD *)(v15 + 80);
      v40 = *(_QWORD *)(v15 + 72);
      LODWORD(v31) = *(_DWORD *)(v15 + 32);
      v41 = *(_QWORD *)(v15 + 24);
      HIDWORD(v31) = *(_DWORD *)v15;
      v42 = *(_QWORD *)(v15 + 128);
      LODWORD(v32) = *(_DWORD *)(v15 + 64);
      v43 = *(_QWORD *)(v15 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v15 + 8);
      v44 = 0x1000000;
      v45 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v16,
        (int)&byte_1800CD9ED,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v45,
        (__int64)&v44,
        (__int64)&SRWLock,
        (__int64)&v43,
        (__int64)&v32,
        (__int64)&v42,
        (__int64)&v31 + 4,
        (__int64)&v41,
        (__int64)&v31,
        (__int64)&v40,
        (__int64)&CurrentThreadId,
        (__int64)&v39,
        (__int64)&v52,
        (__int64)&v29,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v54,
        (__int64)&v34,
        (__int64)&v53,
        (__int64)&v33);
    }
  }
  else
  {
    v32 = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &v32);
    v20 = 2;
    **((_DWORD **)this + 34) = 2;
    if ( v32 )
      ReleaseSRWLockExclusive(v32);
    v21 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v21 > 5u
      && (*(_QWORD *)(v21 + 16) & 0xA0) != 0
      && (*(_QWORD *)(v21 + 24) & 0xA0LL) == *(_QWORD *)(v21 + 24) )
    {
      v45 = (__int64)a3;
      if ( a2 > 0 )
        a2 = (unsigned __int16)a2 | 0x80070000;
      LODWORD(v32) = a2;
      v22 = (__int64 *)*((_QWORD *)this + 56);
      v44 = v22[3];
      v31 = v22[2];
      v43 = v22[1];
      v42 = *v22;
      v41 = (__int64)v22;
      v23 = (__int64 *)((char *)this + 416);
      if ( *((_QWORD *)this + 55) > 7u )
        v23 = (__int64 *)*v23;
      v40 = *((_QWORD *)this + 50);
      v24 = (__int64 *)((char *)this + 368);
      if ( *((_QWORD *)this + 49) > 7u )
        v24 = (__int64 *)*v24;
      CurrentThreadId = GetCurrentThreadId();
      v25 = *((_QWORD *)this + 34);
      v29 = *(_DWORD *)(v25 + 72);
      v39 = 0;
      p_SRWLock = &SRWLock;
      v96 = 4;
      v93 = &v45;
      v94 = 8;
      v91 = &v32;
      v92 = 4;
      v89 = &v44;
      v90 = 8;
      v87 = (char *)&v31 + 4;
      v88 = 4;
      v85 = &v31;
      v86 = 4;
      v83 = &v43;
      v84 = 8;
      v81 = &v42;
      v82 = 8;
      v79 = &v41;
      v80 = 8;
      if ( v23 )
      {
        v26 = -1;
        do
          ++v26;
        while ( *((_WORD *)v23 + v26) );
        v27 = 2 * v26 + 2;
      }
      else
      {
        v23 = &qword_1800AD7F8;
        v27 = 2;
      }
      v76 = v23;
      v77 = v27;
      v78 = 0;
      v74 = &v40;
      v75 = 8;
      if ( v24 )
      {
        do
          ++v12;
        while ( *((_WORD *)v24 + v12) );
        v20 = 2 * v12 + 2;
      }
      else
      {
        v24 = &qword_1800AD7F8;
      }
      v71 = v24;
      v72 = v20;
      v73 = 0;
      v69 = (char *)this + 352;
      v70 = 16;
      v67 = (char *)this + 336;
      v68 = 16;
      p_CurrentThreadId = &CurrentThreadId;
      v66 = 4;
      v63 = &v29;
      v64 = 4;
      v61 = &v39;
      v62 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        v21,
        (unsigned __int8 *)&byte_1800CDBE7,
        (const GUID *)(v25 + 8),
        0,
        0x13u,
        &v60);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVAsyncIo *)((char *)this + 288));
}

```

## disassembly

```asm
0x18009137c  mov     [rsp-8+arg_8], rbx
0x180091381  push    rbp
0x180091382  push    rsi
0x180091383  push    rdi
0x180091384  push    r12
0x180091386  push    r13
0x180091388  push    r14
0x18009138a  push    r15
0x18009138c  lea     rbp, [rsp-1B0h]
0x180091394  sub     rsp, 360h
0x18009139b  mov     rax, cs:__security_cookie
0x1800913a2  xor     rax, rsp
0x1800913a5  mov     [rbp+1E0h+var_40], rax
0x1800913ac  mov     r12d, r9d
0x1800913af  mov     dword ptr [rbp+1E0h+SRWLock], r9d
0x1800913b3  mov     r13, r8
0x1800913b6  mov     edi, edx
0x1800913b8  mov     rbx, rcx
0x1800913bb  mov     eax, [rcx+198h]
0x1800913c1  sub     eax, 4
0x1800913c4  mov     esi, 1
0x1800913c9  cmp     eax, esi
0x1800913cb  ja      short loc_180091401
0x1800913cd  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x1800913d2  mov     rax, [rax+8]
0x1800913d6  test    rax, rax
0x1800913d9  jz      short loc_180091401
0x1800913db  mov     eax, [rax]
0x1800913dd  test    eax, eax
0x1800913df  jz      short loc_180091401
0x1800913e1  mov     rax, [rbx+110h]
0x1800913e8  cmp     [rax], esi
0x1800913ea  jnz     short loc_180091401
0x1800913ec  mov     r9d, r12d; unsigned int
0x1800913ef  mov     r8, r13; void *
0x1800913f2  lea     rdx, aActivitystop; "ActivityStop"
0x1800913f9  mov     rcx, rbx; this
0x1800913fc  call    ?TraceBufferContent@HyperVAsyncIo@HyperVStorageTrace@@AEAAXPEBGPEBXK@Z; HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(ushort const *,void const *,ulong)
0x180091401  mov     ecx, 0C020h; unsigned __int16
0x180091406  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x18009140b  mov     r14d, eax
0x18009140e  test    eax, eax
0x180091410  setnz   [rbp+1E0h+var_260]
0x180091414  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180091419  mov     rcx, [rax+8]
0x18009141d  xor     edx, edx
0x18009141f  test    rcx, rcx
0x180091422  jz      short loc_18009142A
0x180091424  mov     ecx, [rcx]
0x180091426  test    ecx, ecx
0x180091428  jnz     short loc_18009142D
0x18009142a  mov     sil, dl
0x18009142d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180091431  test    r14d, r14d
0x180091434  jnz     short loc_18009143B
0x180091436  test    sil, sil
0x180091439  jz      short loc_180091497
0x18009143b  mov     ecx, cs:_tls_index
0x180091441  mov     rax, gs:58h
0x18009144a  mov     edx, 10h
0x18009144f  mov     rax, [rax+rcx*8]
0x180091453  mov     ecx, [rdx+rax]
0x180091456  cmp     cs:?$TSS0@?M@??Stop@HyperVAsyncIo@HyperVStorageTrace@@QEAAXKPEBXK@Z@4HA, ecx
0x18009145c  jg      loc_180091ADF
0x180091462  lea     r9, [rbx+170h]
0x180091469  cmp     qword ptr [r9+18h], 7
0x18009146e  jbe     short loc_180091473
0x180091470  mov     r9, [r9]
0x180091473  lea     r8, [rbx+1A0h]
0x18009147a  cmp     qword ptr [r8+18h], 7
0x18009147f  jbe     short loc_180091484
0x180091481  mov     r8, [r8]
0x180091484  lea     rdx, ?traceParameters@?M@??Stop@HyperVAsyncIo@HyperVStorageTrace@@QEAAXKPEBXK@Z@4UHvsDebugTraceParameters@@B; struct HvsDebugTraceParameters *
0x18009148b  mov     ecx, 0C020h; unsigned int
0x180091490  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180091495  xor     edx, edx
0x180091497  mov     rsi, [rbx+110h]
0x18009149e  mov     eax, [rsi+48h]
0x1800914a1  test    eax, eax
0x1800914a3  jns     loc_1800917C2
0x1800914a9  add     rsi, 50h ; 'P'
0x1800914ad  cmp     eax, [rsi+8]
0x1800914b0  jnz     loc_1800917C2
0x1800914b6  test    rsi, rsi
0x1800914b9  jz      loc_1800917C2
0x1800914bf  mov     [rbp+1E0h+SRWLock], rdx
0x1800914c3  lea     rdx, [rbp+1E0h+SRWLock]
0x1800914c7  mov     rcx, rbx
0x1800914ca  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800914cf  mov     rax, [rbx+110h]
0x1800914d6  mov     dword ptr [rax], 2
0x1800914dc  mov     rcx, [rbp+1E0h+SRWLock]; SRWLock
0x1800914e0  xor     r14d, r14d
0x1800914e3  test    rcx, rcx
0x1800914e6  jz      short loc_1800914EE
0x1800914e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800914ee  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x1800914f3  mov     r9, [rax+8]
0x1800914f7  mov     eax, [r9]
0x1800914fa  cmp     eax, 5
0x1800914fd  jbe     loc_180091AA2
0x180091503  mov     rcx, [r9+18h]
0x180091507  mov     rax, [r9+10h]
0x18009150b  test    al, 0A0h
0x18009150d  jz      loc_180091AA2
0x180091513  mov     rax, rcx
0x180091516  and     eax, 0A0h
0x18009151b  cmp     rax, rcx
0x18009151e  jnz     loc_180091AA2
0x180091524  mov     dword ptr [rbp+1E0h+var_238], r12d
0x180091528  mov     [rbp+1E0h+var_1B0], r13
0x18009152c  test    edi, edi
0x18009152e  jle     short loc_180091539
0x180091530  movzx   edi, di
0x180091533  or      edi, 80070000h
0x180091539  mov     dword ptr [rbp+1E0h+var_238+4], edi
0x18009153c  mov     rcx, [rbx+1C0h]
0x180091543  mov     rax, [rcx+18h]
0x180091547  mov     [rbp+1E0h+var_1A8], rax
0x18009154b  mov     eax, [rcx+14h]
0x18009154e  mov     dword ptr [rbp+1E0h+var_230], eax
0x180091551  mov     eax, [rcx+10h]
0x180091554  mov     dword ptr [rbp+1E0h+var_230+4], eax
0x180091557  mov     rax, [rcx+8]
0x18009155b  mov     [rbp+1E0h+var_1A0], rax
0x18009155f  mov     rax, [rcx]
0x180091562  mov     [rbp+1E0h+var_198], rax
0x180091566  mov     [rbp+1E0h+var_190], rcx
0x18009156a  lea     rax, [rbx+1A0h]
0x180091571  cmp     qword ptr [rax+18h], 7
0x180091576  jbe     short loc_18009157B
0x180091578  mov     rax, [rax]
0x18009157b  mov     [rbp+1E0h+var_188], rax
0x18009157f  mov     rax, [rbx+190h]
0x180091586  mov     [rbp+1E0h+var_180], rax
0x18009158a  lea     rax, [rbx+170h]
0x180091591  cmp     qword ptr [rax+18h], 7
0x180091596  jbe     short loc_18009159B
0x180091598  mov     rax, [rax]
0x18009159b  mov     [rbp+1E0h+var_1E8], rax
0x18009159f  lea     rax, [rbx+160h]
0x1800915a6  mov     [rbp+1E0h+var_1E0], rax
0x1800915aa  lea     rax, [rbx+150h]
0x1800915b1  mov     [rbp+1E0h+var_1D8], rax
0x1800915b5  mov     rax, [rsi+30h]
0x1800915b9  mov     [rbp+1E0h+var_1D0], rax
0x1800915bd  mov     eax, [rsi+44h]
0x1800915c0  mov     [rbp+1E0h+var_228], eax
0x1800915c3  mov     eax, [rsi+10h]
0x1800915c6  mov     [rbp+1E0h+var_224], eax
0x1800915c9  mov     rax, [rsi+78h]
0x1800915cd  mov     [rbp+1E0h+var_1C8], rax
0x1800915d1  mov     rax, [rsi+70h]
0x1800915d5  mov     [rbp+1E0h+var_1C0], rax
0x1800915d9  mov     eax, [rsi+68h]
0x1800915dc  mov     dword ptr [rbp+1E0h+var_250], eax
0x1800915df  mov     rax, [rsi+60h]
0x1800915e3  mov     [rbp+1E0h+var_1B8], rax
0x1800915e7  mov     rax, [rsi+58h]
0x1800915eb  mov     [rbp+1E0h+var_220], rax
0x1800915ef  mov     eax, [rsi+50h]
0x1800915f2  mov     dword ptr [rbp+1E0h+var_250+4], eax
0x1800915f5  mov     rax, [rsi+48h]
0x1800915f9  mov     [rbp+1E0h+var_218], rax
0x1800915fd  mov     eax, [rsi+20h]
0x180091600  mov     dword ptr [rbp+1E0h+var_248], eax
0x180091603  mov     rax, [rsi+18h]
0x180091607  mov     [rbp+1E0h+var_210], rax
0x18009160b  mov     eax, [rsi]
0x18009160d  mov     dword ptr [rbp+1E0h+var_248+4], eax
0x180091610  mov     rax, [rsi+80h]
0x180091617  mov     [rbp+1E0h+var_208], rax
0x18009161b  mov     eax, [rsi+40h]
0x18009161e  mov     dword ptr [rbp+1E0h+var_240], eax
0x180091621  mov     rax, [rsi+38h]
0x180091625  mov     [rbp+1E0h+var_200], rax
0x180091629  mov     eax, [rsi+8]
0x18009162c  mov     dword ptr [rbp+1E0h+SRWLock], eax
0x18009162f  mov     [rbp+1E0h+var_1F8], 1000000h
0x180091637  mov     [rbp+1E0h+var_1F0], r14
0x18009163b  mov     r8, [rbx+110h]
0x180091642  add     r8, 8; int
0x180091646  lea     rax, [rbp+1E0h+var_238]
0x18009164a  mov     [rsp+390h+var_270], rax; __int64
0x180091652  lea     rax, [rbp+1E0h+var_1B0]
0x180091656  mov     [rsp+390h+var_278], rax; __int64
0x18009165e  lea     rax, [rbp+1E0h+var_238+4]
0x180091662  mov     [rsp+390h+var_280], rax; __int64
0x18009166a  lea     rax, [rbp+1E0h+var_1A8]
0x18009166e  mov     [rsp+390h+var_288], rax; __int64
0x180091676  lea     rax, [rbp+1E0h+var_230]
0x18009167a  mov     [rsp+390h+var_290], rax; __int64
0x180091682  lea     rax, [rbp+1E0h+var_230+4]
0x180091686  mov     [rsp+390h+var_298], rax; __int64
0x18009168e  lea     rax, [rbp+1E0h+var_1A0]
0x180091692  mov     [rsp+390h+var_2A0], rax; __int64
0x18009169a  lea     rax, [rbp+1E0h+var_198]
0x18009169e  mov     [rsp+390h+var_2A8], rax; __int64
0x1800916a6  lea     rax, [rbp+1E0h+var_190]
0x1800916aa  mov     [rsp+390h+var_2B0], rax; __int64
0x1800916b2  lea     rax, [rbp+1E0h+var_188]
0x1800916b6  mov     [rsp+390h+var_2B8], rax; __int64
0x1800916be  lea     rax, [rbp+1E0h+var_180]
0x1800916c2  mov     [rsp+390h+var_2C0], rax; __int64
0x1800916ca  lea     rax, [rbp+1E0h+var_1E8]
0x1800916ce  mov     [rsp+390h+var_2C8], rax; __int64
0x1800916d6  lea     rax, [rbp+1E0h+var_1E0]
0x1800916da  mov     [rsp+390h+var_2D0], rax; __int64
0x1800916e2  lea     rax, [rbp+1E0h+var_1D8]
0x1800916e6  mov     [rsp+390h+var_2D8], rax; __int64
0x1800916ee  lea     rax, [rbp+1E0h+var_1D0]
0x1800916f2  mov     [rsp+390h+var_2E0], rax; __int64
0x1800916fa  lea     rax, [rbp+1E0h+var_228]
0x1800916fe  mov     [rsp+390h+var_2E8], rax; __int64
0x180091706  lea     rax, [rbp+1E0h+var_224]
0x18009170a  mov     [rsp+390h+var_2F0], rax; __int64
0x180091712  lea     rax, [rbp+1E0h+var_1C8]
0x180091716  mov     [rsp+390h+var_2F8], rax; __int64
0x18009171e  lea     rax, [rbp+1E0h+var_1C0]
0x180091722  mov     [rsp+390h+var_300], rax; __int64
0x18009172a  lea     rax, [rbp+1E0h+var_250]
0x18009172e  mov     [rsp+390h+var_308], rax; __int64
0x180091736  lea     rax, [rbp+1E0h+var_1B8]
0x18009173a  mov     [rsp+390h+var_310], rax; __int64
0x180091742  lea     rax, [rbp+1E0h+var_220]
0x180091746  mov     [rsp+390h+var_318], rax; __int64
0x18009174b  lea     rax, [rbp+1E0h+var_250+4]
0x18009174f  mov     [rsp+390h+var_320], rax; __int64
0x180091754  lea     rax, [rbp+1E0h+var_218]
0x180091758  mov     [rsp+390h+var_328], rax; __int64
0x18009175d  lea     rax, [rbp+1E0h+var_248]
0x180091761  mov     [rsp+390h+var_330], rax; __int64
0x180091766  lea     rax, [rbp+1E0h+var_210]
0x18009176a  mov     [rsp+390h+var_338], rax; __int64
0x18009176f  lea     rax, [rbp+1E0h+var_248+4]
0x180091773  mov     [rsp+390h+var_340], rax; __int64
0x180091778  lea     rax, [rbp+1E0h+var_208]
0x18009177c  mov     [rsp+390h+var_348], rax; __int64
0x180091781  lea     rax, [rbp+1E0h+var_240]
0x180091785  mov     [rsp+390h+var_350], rax; __int64
0x18009178a  lea     rax, [rbp+1E0h+var_200]
0x18009178e  mov     [rsp+390h+var_358], rax; __int64
0x180091793  lea     rax, [rbp+1E0h+SRWLock]
0x180091797  mov     [rsp+390h+var_360], rax; __int64
0x18009179c  lea     rax, [rbp+1E0h+var_1F8]
0x1800917a0  mov     [rsp+390h+var_368], rax; __int64
0x1800917a5  lea     rax, [rbp+1E0h+var_1F0]
0x1800917a9  mov     qword ptr [rsp+390h+var_370], rax; __int64
0x1800917ae  lea     rdx, byte_1800CD9ED; int
0x1800917b5  mov     rcx, r9; int
0x1800917b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByRef@$0BA@@@U5@U4@U1@U4@U1@U1@U1@U2@U2@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445AEBU?$_tlgWrapperByRef@$0BA@@@7636333443434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800917bd  jmp     loc_180091AA2
0x1800917c2  mov     [rbp+1E0h+var_240], rdx
0x1800917c6  lea     rdx, [rbp+1E0h+var_240]
0x1800917ca  mov     rcx, rbx
0x1800917cd  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800917d2  mov     rax, [rbx+110h]
0x1800917d9  mov     r14d, 2
0x1800917df  mov     [rax], r14d
0x1800917e2  mov     rcx, [rbp+1E0h+var_240]; SRWLock
0x1800917e6  test    rcx, rcx
0x1800917e9  jz      short loc_1800917F1
0x1800917eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800917f1  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x1800917f6  mov     r12, [rax+8]
0x1800917fa  mov     eax, [r12]
0x1800917fe  cmp     eax, 5
0x180091801  jbe     loc_180091A9F
0x180091807  mov     rcx, [r12+18h]
0x18009180c  mov     rax, [r12+10h]
0x180091811  test    al, 0A0h
0x180091813  jz      loc_180091A9F
0x180091819  mov     rax, rcx
0x18009181c  and     eax, 0A0h
0x180091821  cmp     rax, rcx
0x180091824  jnz     loc_180091A9F
0x18009182a  mov     eax, dword ptr [rbp+1E0h+SRWLock]
0x18009182d  mov     dword ptr [rbp+1E0h+SRWLock], eax
0x180091830  mov     [rbp+1E0h+var_1F0], r13
0x180091834  test    edi, edi
0x180091836  jle     short loc_180091841
0x180091838  movzx   edi, di
0x18009183b  or      edi, 80070000h
0x180091841  mov     dword ptr [rbp+1E0h+var_240], edi
0x180091844  mov     rcx, [rbx+1C0h]
0x18009184b  mov     rax, [rcx+18h]
0x18009184f  mov     [rbp+1E0h+var_1F8], rax
0x180091853  mov     eax, [rcx+14h]
0x180091856  mov     dword ptr [rbp+1E0h+var_248+4], eax
0x180091859  mov     eax, [rcx+10h]
0x18009185c  mov     dword ptr [rbp+1E0h+var_248], eax
0x18009185f  mov     rax, [rcx+8]
0x180091863  mov     [rbp+1E0h+var_200], rax
0x180091867  mov     rax, [rcx]
0x18009186a  mov     [rbp+1E0h+var_208], rax
0x18009186e  mov     [rbp+1E0h+var_210], rcx
0x180091872  lea     rsi, [rbx+1A0h]
0x180091879  cmp     qword ptr [rsi+18h], 7
0x18009187e  jbe     short loc_180091883
0x180091880  mov     rsi, [rsi]
  ... truncated ...
```
