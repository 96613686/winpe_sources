# CFLACDecMFT::WriteOutputSample(ulong,ulong * *)

- ea: `0x18001f280`
- end: `0x18001f565`
- name: `?WriteOutputSample@CFLACDecMFT@@MEAAJKPEAPEAK@Z`
- size: `741`
- prototype: `int(CFLACDecMFT *__hidden this, unsigned int, unsigned int **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000284c`
- `0x1800028ac`
- `0x18001efc4`
- `0x18001f280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f2fb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f2fb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f50c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f50c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f53d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f53d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f354`
- `MFPlat!MFllMulDiv` at `0x18001f494`
- `MFPlat!MFllMulDiv` at `0x18001f494`

## string_xrefs

- `0x18001f29c`: `WriteOutputSample`
- `0x18001f2ab`: `CFLACDecMFT::WriteOutputSample`
- `0x18001f3de`: `CFLACDecMFT::WriteOutputSample`
- `0x18001f49d`: `CFLACDecMFT::WriteOutputSample`
- `0x18001f4ee`: `CFLACDecMFT::WriteOutputSample`
- `0x18001f51f`: `CFLACDecMFT::WriteOutputSample`

## pseudocode

```c
__int64 __fastcall CFLACDecMFT::WriteOutputSample(CFLACDecMFT *this, unsigned int a2, unsigned int **a3)
{
  TraceLoggingHelperBase *v3; // rbp
  LONGLONG v4; // r15
  DWORD v7; // eax
  unsigned int v9; // esi
  void *v10; // rcx
  double v11; // xmm0_8
  _BYTE *v12; // r11
  unsigned int v13; // r14d
  __int64 i; // rdx
  __int64 j; // rcx
  unsigned int *v16; // r9
  unsigned int v17; // r10d
  unsigned int *k; // r9
  char v19; // al
  LONGLONG v20; // r8
  LONGLONG v21; // rax
  int v22; // edx
  HANDLE Handles[9]; // [rsp+40h] [rbp-48h] BYREF

  v3 = (CFLACDecMFT *)((char *)this + 808);
  v4 = a2;
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 808),
    5u,
    "CFLACDecMFT::WriteOutputSample",
    0x4E0u,
    "WriteOutputSample");
  Handles[0] = *((HANDLE *)this + 100);
  Handles[1] = *((HANDLE *)this + 96);
  v7 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      TraceLoggingHelperBase::TraceVA(
        v3,
        2u,
        "CFLACDecMFT::WriteOutputSample",
        0x4ECu,
        "Neither eSTATE_FLUSH_ALL_SAMPLES nor eSTATE_OUTPUT_SAMPLE_EMPTY is set");
      return 3222091451LL;
    }
    if ( !*((_DWORD *)this + 38) )
    {
      TraceLoggingHelperBase::TraceVA(
        v3,
        2u,
        "CFLACDecMFT::WriteOutputSample",
        0x4F7u,
        ": MF_E_UNEXPECTED - Metadata is not set");
      return 3222091451LL;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    if ( a3 && (v10 = (void *)*((_QWORD *)this + 16)) != 0 )
    {
      memset_0(v10, 0, *((unsigned int *)this - 15));
      v11 = (double)*((int *)this + 176) * 0.125;
      o_ceil_0();
      if ( *((_DWORD *)this - 15) >= (unsigned int)(*((_DWORD *)this + 37) * v4) )
      {
        v12 = (_BYTE *)*((_QWORD *)this + 16);
        v9 = 0;
        v13 = (int)v11;
        for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
        {
          for ( j = 0; (unsigned int)j < *((_DWORD *)this + 175); j = (unsigned int)(j + 1) )
          {
            v16 = a3[j];
            if ( v16 )
            {
              v17 = 0;
              for ( k = &v16[i]; v17 < v13; ++v12 )
              {
                ++v17;
                v19 = *(_BYTE *)k + (v13 != 1 ? 0 : 0x80);
                k = (unsigned int *)((char *)k + 1);
                *v12 = v19;
              }
            }
          }
        }
        v20 = *((unsigned int *)this + 174);
        *((_DWORD *)this + 25) = *((_DWORD *)this + 175) * v4;
        v21 = MFllMulDiv(10000000, v4, v20, 0);
        v22 = *((_DWORD *)this + 25);
        *((_QWORD *)this + 13) = v21;
        *((_DWORD *)this + 24) = v13 * v22;
        TraceLoggingHelperBase::TraceVA(
          v3,
          5u,
          "CFLACDecMFT::WriteOutputSample",
          0x549u,
          "Frame duration: %I64d, Num of Samples: %u, Frame size: %u",
          v21,
          v22,
          v13 * v22);
        TraceLoggingHelperBase::TraceVA(
          v3,
          5u,
          "CFLACDecMFT::WriteOutputSample",
          0x54Bu,
          "ResetEvent(m_hProcessSampleEvents[eSTATE_OUTPUT_SAMPLE_EMPTY])");
        ResetEvent(*((HANDLE *)this + 96));
        TraceLoggingHelperBase::TraceVA(
          v3,
          5u,
          "CFLACDecMFT::WriteOutputSample",
          0x54Eu,
          "SetEvent(m_hProcessSampleEvents[eSTATE_OUTPUT_SAMPLE_AVAILABLE])");
        SetEvent(*((HANDLE *)this + 97));
        goto LABEL_21;
      }
      TraceLoggingHelperBase::TraceVA(
        v3,
        2u,
        "CFLACDecMFT::WriteOutputSample",
        0x508u,
        "MF_E_BUFFERTOOSMALL - Max OutputSampleSize < received output sample size");
      v9 = -1072875855;
    }
    else
    {
      v9 = -2147467261;
    }
    TraceLoggingHelperBase::TraceVA(
      v3,
      2u,
      "CFLACDecMFT::WriteOutputSample",
      0x552u,
      "Error %08X returned: File: %s, Line: %d",
      v9,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
      1362);
LABEL_21:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    return v9;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f280  push    rbx
0x18001f282  push    rbp
0x18001f283  push    rsi
0x18001f284  push    rdi
0x18001f285  push    r12
0x18001f287  push    r14
0x18001f289  push    r15
0x18001f28b  sub     rsp, 50h
0x18001f28f  lea     rbp, [rcx+328h]
0x18001f296  mov     r15d, edx
0x18001f299  mov     r12, r8
0x18001f29c  lea     rax, aWriteoutputsam; "WriteOutputSample"
0x18001f2a3  mov     rdi, rcx
0x18001f2a6  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f2ab  lea     rsi, aCflacdecmftWri; "CFLACDecMFT::WriteOutputSample"
0x18001f2b2  mov     rcx, rbp; this
0x18001f2b5  mov     r8, rsi; char *
0x18001f2b8  mov     r9d, 4E0h; unsigned int
0x18001f2be  mov     edx, 5; unsigned __int8
0x18001f2c3  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f2c8  mov     rax, [rdi+320h]
0x18001f2cf  lea     rdx, [rsp+88h+Handles]; lpHandles
0x18001f2d4  xor     r8d, r8d; bWaitAll
0x18001f2d7  mov     [rsp+88h+Handles], rax
0x18001f2dc  mov     rax, [rdi+300h]
0x18001f2e3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001f2e7  mov     [rsp+88h+var_40], rax
0x18001f2ec  mov     [rsp+88h+bAlertable], 0; bAlertable
0x18001f2f4  lea     r14d, [r8+2]
0x18001f2f8  mov     ecx, r14d; nCount
0x18001f2fb  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f301  test    eax, eax
0x18001f303  jz      loc_18001F551
0x18001f309  cmp     eax, 1
0x18001f30c  jz      short loc_18001F338
0x18001f30e  lea     rax, aNeitherEstateF; "Neither eSTATE_FLUSH_ALL_SAMPLES nor eS"...
0x18001f315  mov     r9d, 4ECh; unsigned int
0x18001f31b  mov     r8, rsi; char *
0x18001f31e  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f323  mov     edx, r14d; unsigned __int8
0x18001f326  mov     rcx, rbp; this
0x18001f329  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f32e  mov     eax, 0C00D36BBh
0x18001f333  jmp     loc_18001F556
0x18001f338  cmp     dword ptr [rdi+98h], 0
0x18001f33f  jnz     short loc_18001F350
0x18001f341  lea     rax, aMfEUnexpectedM; ": MF_E_UNEXPECTED - Metadata is not set"
0x18001f348  mov     r9d, 4F7h
0x18001f34e  jmp     short loc_18001F31B
0x18001f350  lea     rcx, [rdi+20h]; lpCriticalSection
0x18001f354  call    cs:__imp_EnterCriticalSection
0x18001f35a  test    r12, r12
0x18001f35d  jnz     short loc_18001F366
0x18001f35f  mov     esi, 80004003h
0x18001f364  jmp     short loc_18001F3CC
0x18001f366  mov     rcx, [rdi+80h]; void *
0x18001f36d  test    rcx, rcx
0x18001f370  jz      short loc_18001F35F
0x18001f372  mov     r8d, [rdi-3Ch]; Size
0x18001f376  xor     edx, edx; Val
0x18001f378  call    memset_0
0x18001f37d  mov     eax, [rdi+2C0h]
0x18001f383  xorps   xmm0, xmm0
0x18001f386  cvtsi2sd xmm0, rax
0x18001f38b  mulsd   xmm0, cs:__real@3fc0000000000000
0x18001f393  call    _o_ceil_0
0x18001f398  mov     eax, r15d
0x18001f39b  imul    eax, [rdi+94h]
0x18001f3a2  cmp     [rdi-3Ch], eax
0x18001f3a5  jnb     short loc_18001F40A
0x18001f3a7  lea     rax, aMfEBuffertoosm_0; "MF_E_BUFFERTOOSMALL - Max OutputSampleS"...
0x18001f3ae  mov     r9d, 508h; unsigned int
0x18001f3b4  mov     r8, rsi; char *
0x18001f3b7  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f3bc  mov     edx, r14d; unsigned __int8
0x18001f3bf  mov     rcx, rbp; this
0x18001f3c2  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f3c7  mov     esi, 0C00D36B1h
0x18001f3cc  mov     r9d, 552h; unsigned int
0x18001f3d2  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001f3d9  mov     [rsp+88h+var_50], r9d
0x18001f3de  lea     r8, aCflacdecmftWri; "CFLACDecMFT::WriteOutputSample"
0x18001f3e5  mov     [rsp+88h+var_58], rax
0x18001f3ea  mov     edx, r14d; unsigned __int8
0x18001f3ed  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001f3f4  mov     dword ptr [rsp+88h+var_60], esi
0x18001f3f8  mov     rcx, rbp; this
0x18001f3fb  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f400  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f405  jmp     loc_18001F543
0x18001f40a  mov     r11, [rdi+80h]
0x18001f411  xor     esi, esi
0x18001f413  cvttsd2si r14, xmm0
0x18001f418  cmp     r14d, 1
0x18001f41c  setnz   r8b
0x18001f420  xor     edx, edx
0x18001f422  dec     r8b
0x18001f425  and     r8b, 80h
0x18001f429  test    r15d, r15d
0x18001f42c  jz      short loc_18001F475
0x18001f42e  xor     ecx, ecx
0x18001f430  cmp     [rdi+2BCh], ecx
0x18001f436  jbe     short loc_18001F46E
0x18001f438  mov     r9, [r12+rcx*8]
0x18001f43c  test    r9, r9
0x18001f43f  jz      short loc_18001F464
0x18001f441  xor     r10d, r10d
0x18001f444  lea     r9, [r9+rdx*4]
0x18001f448  test    r14d, r14d
0x18001f44b  jz      short loc_18001F464
0x18001f44d  mov     al, r8b
0x18001f450  inc     r10d
0x18001f453  add     al, [r9]
0x18001f456  inc     r9
0x18001f459  mov     [r11], al
0x18001f45c  inc     r11
0x18001f45f  cmp     r10d, r14d
0x18001f462  jb      short loc_18001F44D
0x18001f464  inc     ecx
0x18001f466  cmp     ecx, [rdi+2BCh]
0x18001f46c  jb      short loc_18001F438
0x18001f46e  inc     edx
0x18001f470  cmp     edx, r15d
0x18001f473  jb      short loc_18001F42E
0x18001f475  mov     r8d, [rdi+2B8h]; c
0x18001f47c  mov     eax, r15d
0x18001f47f  imul    eax, [rdi+2BCh]
0x18001f486  mov     rdx, r15; b
0x18001f489  xor     r9d, r9d; d
0x18001f48c  mov     ecx, 989680h; a
0x18001f491  mov     [rdi+64h], eax
0x18001f494  call    cs:__imp_MFllMulDiv
0x18001f49a  mov     edx, [rdi+64h]
0x18001f49d  lea     r8, aCflacdecmftWri; "CFLACDecMFT::WriteOutputSample"
0x18001f4a4  mov     ecx, edx
0x18001f4a6  mov     [rdi+68h], rax
0x18001f4aa  imul    ecx, r14d
0x18001f4ae  mov     r9d, 549h; unsigned int
0x18001f4b4  mov     r14d, 5
0x18001f4ba  mov     [rsp+88h+var_50], ecx
0x18001f4be  mov     dword ptr [rsp+88h+var_58], edx
0x18001f4c2  mov     edx, r14d; unsigned __int8
0x18001f4c5  mov     [rsp+88h+var_60], rax
0x18001f4ca  lea     rax, aFrameDurationI; "Frame duration: %I64d, Num of Samples: "...
0x18001f4d1  mov     [rdi+60h], ecx
0x18001f4d4  mov     rcx, rbp; this
0x18001f4d7  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f4dc  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f4e1  lea     rax, aReseteventMHpr_1; "ResetEvent(m_hProcessSampleEvents[eSTAT"...
0x18001f4e8  mov     r9d, 54Bh; unsigned int
0x18001f4ee  lea     r8, aCflacdecmftWri; "CFLACDecMFT::WriteOutputSample"
0x18001f4f5  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f4fa  mov     edx, r14d; unsigned __int8
0x18001f4fd  mov     rcx, rbp; this
0x18001f500  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f505  mov     rcx, [rdi+300h]; hEvent
0x18001f50c  call    cs:__imp_ResetEvent
0x18001f512  lea     rax, aSeteventMHproc_1; "SetEvent(m_hProcessSampleEvents[eSTATE_"...
0x18001f519  mov     r9d, 54Eh; unsigned int
0x18001f51f  lea     r8, aCflacdecmftWri; "CFLACDecMFT::WriteOutputSample"
0x18001f526  mov     qword ptr [rsp+88h+bAlertable], rax; Format
0x18001f52b  mov     edx, r14d; unsigned __int8
0x18001f52e  mov     rcx, rbp; this
0x18001f531  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001f536  mov     rcx, [rdi+308h]; hEvent
0x18001f53d  call    cs:__imp_SetEvent
0x18001f543  lea     rcx, [rdi+20h]; lpCriticalSection
0x18001f547  call    cs:__imp_LeaveCriticalSection
0x18001f54d  mov     eax, esi
0x18001f54f  jmp     short loc_18001F556
0x18001f551  mov     eax, 1
0x18001f556  add     rsp, 50h
0x18001f55a  pop     r15
0x18001f55c  pop     r14
0x18001f55e  pop     r12
0x18001f560  pop     rdi
0x18001f561  pop     rsi
0x18001f562  pop     rbp
0x18001f563  pop     rbx
0x18001f564  retn
```
