# PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)

- ea: `0x18001e8e0`
- end: `0x18001eb55`
- name: `?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z`
- size: `629`
- prototype: `int(unsigned int (*)(void *), void *, void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026cd0`

## callees

- `0x18000160c`
- `0x180001f98`
- `0x18001e6c8`
- `0x18001e8e0`
- `0x18001eb5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001ea32`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001ea32`

## string_xrefs

- `0x18001e93e`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001e9d1`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ea4f`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001e92b`: `PAL_System_ThreadAllocInit`
- `0x18001e9bd`: `PAL_System_ThreadAllocInit`
- `0x18001ea48`: `PAL_System_ThreadAllocInit`
- `0x18001e9ab`: `Could not allocate thread`
- `0x18001ea6f`: `Could not free newly-created thread. Error hr=0x%08x`
- `0x18001eae9`: `Failed to wait on thread events`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAllocInit(
        unsigned int (*a1)(void *),
        void *a2,
        void *a3,
        unsigned int *a4,
        void **a5)
{
  int v7; // ebx
  void **v8; // r14
  __int64 v9; // r8
  __int64 v10; // r9
  void *v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // eax
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int (*v23)(void *); // [rsp+B0h] [rbp+30h] BYREF
  int v24; // [rsp+C0h] [rbp+40h] BYREF

  v23 = a1;
  *(_OWORD *)Handles = 0;
  if ( a3 )
  {
    v8 = a5;
    v7 = PAL_System_ThreadAlloc(a1, a2, a4, a5);
    if ( v7 >= 0 )
    {
      v11 = *v8;
      Handles[0] = a3;
      Handles[1] = v11;
      if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
      {
        v12 = PAL_System_ThreadFree(*v8);
        if ( v12 < 0 )
        {
          v13 = (unsigned int)dword_180044008;
          if ( (unsigned int)dword_180044008 > 2 )
          {
            LODWORD(v23) = v12;
            v20 = "PAL_System_ThreadAllocInit";
            v21 = "Could not free newly-created thread. Error hr=0x%08x";
            v24 = 1209;
            v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
            LODWORD(v18) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)dword_180044008,
              (__int64)byte_18003EE6B,
              v14,
              v15,
              (const unsigned __int16 **)&v21,
              (__int64)&v18,
              (const unsigned __int16 **)&v19,
              (__int64)&v24,
              (const unsigned __int16 **)&v20,
              (__int64)&v23);
          }
        }
        v16 = dword_180044008;
        v7 = -2147467259;
        *a4 = 0;
        *v8 = 0;
        if ( v16 > 2 )
        {
          v21 = "PAL_System_ThreadAllocInit";
          v19 = "Failed to wait on thread events";
          LODWORD(v23) = 1217;
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v24 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v13,
            (__int64)word_18003EF42,
            v14,
            v15,
            (const unsigned __int16 **)&v19,
            (__int64)&v24,
            (const unsigned __int16 **)&v20,
            (__int64)&v23,
            (const unsigned __int16 **)&v21);
        }
      }
      else
      {
        return 0;
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v23) = 1181;
      v18 = "Could not allocate thread";
      v20 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)byte_18003EEFD,
        v9,
        v10,
        (const unsigned __int16 **)&v18,
        (__int64)&v24,
        (const unsigned __int16 **)&v19,
        (__int64)&v23,
        (const unsigned __int16 **)&v20);
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v23) = 1171;
      v20 = "NULL parameter passed";
      v18 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)a1,
        (__int64)qword_18003EEB8,
        0,
        (__int64)a4,
        (const unsigned __int16 **)&v20,
        (__int64)&v24,
        (const unsigned __int16 **)&v19,
        (__int64)&v23,
        (const unsigned __int16 **)&v18);
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e8e0  mov     r11, rsp
0x18001e8e3  mov     [r11+10h], rbx
0x18001e8e7  mov     [r11+8], rcx
0x18001e8eb  push    rbp
0x18001e8ec  push    rsi
0x18001e8ed  push    rdi
0x18001e8ee  push    r14
0x18001e8f0  push    r15
0x18001e8f2  mov     rbp, rsp
0x18001e8f5  sub     rsp, 80h
0x18001e8fc  xorps   xmm0, xmm0
0x18001e8ff  mov     r15, r9
0x18001e902  mov     rdi, r8
0x18001e905  movups  xmmword ptr [rbp+Handles], xmm0
0x18001e909  test    r8, r8
0x18001e90c  jnz     short loc_18001E987
0x18001e90e  mov     eax, cs:dword_180044008
0x18001e914  cmp     eax, 2
0x18001e917  jbe     short loc_18001E97D
0x18001e919  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001e920  mov     dword ptr [rbp+arg_0], 493h
0x18001e927  mov     [rbp+var_20], rax
0x18001e92b  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001e932  lea     rax, [rbp+var_30]
0x18001e936  mov     [rbp+var_30], rdi
0x18001e93a  mov     [r11-68h], rax
0x18001e93e  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001e945  lea     rax, [rbp+arg_0]
0x18001e949  mov     [rbp+var_28], rsi
0x18001e94d  mov     [r11-70h], rax
0x18001e951  lea     rdx, qword_18003EEB8
0x18001e958  lea     rax, [rbp+var_28]
0x18001e95c  mov     [rbp+arg_10], 80004005h
0x18001e963  mov     [r11-78h], rax
0x18001e967  lea     rax, [rbp+arg_10]
0x18001e96b  mov     [r11-80h], rax
0x18001e96f  lea     rax, [rbp+var_20]
0x18001e973  mov     [rsp+80h+var_60], rax
0x18001e978  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001e97d  mov     ebx, 80070057h
0x18001e982  jmp     loc_18001EB3C
0x18001e987  mov     r14, [rbp+arg_20]
0x18001e98b  mov     r8, r15; unsigned int *
0x18001e98e  mov     r9, r14; void **
0x18001e991  call    ?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z; PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)
0x18001e996  mov     ebx, eax
0x18001e998  test    eax, eax
0x18001e99a  jns     short loc_18001EA18
0x18001e99c  mov     ecx, cs:dword_180044008
0x18001e9a2  cmp     ecx, 2
0x18001e9a5  jbe     loc_18001EB3C
0x18001e9ab  lea     rax, aCouldNotAlloca; "Could not allocate thread"
0x18001e9b2  mov     dword ptr [rbp+arg_0], 49Dh
0x18001e9b9  mov     [rbp+var_30], rax
0x18001e9bd  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001e9c4  lea     rax, [rbp+var_20]
0x18001e9c8  mov     [rbp+var_20], rdi
0x18001e9cc  mov     [rsp+80h+var_40], rax
0x18001e9d1  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001e9d8  lea     rax, [rbp+arg_0]
0x18001e9dc  mov     [rbp+var_28], rsi
0x18001e9e0  mov     [rsp+80h+var_48], rax
0x18001e9e5  lea     rdx, byte_18003EEFD
0x18001e9ec  lea     rax, [rbp+var_28]
0x18001e9f0  mov     [rbp+arg_10], 80004005h
0x18001e9f7  mov     [rsp+80h+var_50], rax
0x18001e9fc  lea     rax, [rbp+arg_10]
0x18001ea00  mov     [rsp+80h+var_58], rax
0x18001ea05  lea     rax, [rbp+var_30]
0x18001ea09  mov     [rsp+80h+var_60], rax
0x18001ea0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ea13  jmp     loc_18001EB3C
0x18001ea18  mov     rax, [r14]
0x18001ea1b  lea     rdx, [rbp+Handles]; lpHandles
0x18001ea1f  xor     r8d, r8d; bWaitAll
0x18001ea22  mov     [rbp+Handles], rdi
0x18001ea26  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001ea2a  mov     [rbp+Handles+8], rax
0x18001ea2e  lea     ecx, [r8+2]; nCount
0x18001ea32  call    cs:__imp_WaitForMultipleObjects
0x18001ea38  test    eax, eax
0x18001ea3a  jz      loc_18001EB3A
0x18001ea40  mov     rcx, [r14]; void *
0x18001ea43  call    ?PAL_System_ThreadFree@@YAJPEAX@Z; PAL_System_ThreadFree(void *)
0x18001ea48  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x18001ea4f  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ea56  test    eax, eax
0x18001ea58  jns     short loc_18001EACB
0x18001ea5a  mov     ecx, cs:dword_180044008
0x18001ea60  cmp     ecx, 2
0x18001ea63  jbe     short loc_18001EACB
0x18001ea65  mov     dword ptr [rbp+arg_0], eax
0x18001ea68  lea     rdx, byte_18003EE6B
0x18001ea6f  lea     rax, aCouldNotFreeNe; "Could not free newly-created thread. Er"...
0x18001ea76  mov     [rbp+var_20], rdi
0x18001ea7a  mov     [rbp+var_18], rax
0x18001ea7e  lea     rax, [rbp+arg_0]
0x18001ea82  mov     [rsp+80h+var_38], rax
0x18001ea87  lea     rax, [rbp+var_20]
0x18001ea8b  mov     [rsp+80h+var_40], rax
0x18001ea90  lea     rax, [rbp+arg_10]
0x18001ea94  mov     [rsp+80h+var_48], rax
0x18001ea99  lea     rax, [rbp+var_28]
0x18001ea9d  mov     [rsp+80h+var_50], rax
0x18001eaa2  lea     rax, [rbp+var_30]
0x18001eaa6  mov     [rsp+80h+var_58], rax
0x18001eaab  lea     rax, [rbp+var_18]
0x18001eaaf  mov     [rsp+80h+var_60], rax
0x18001eab4  mov     [rbp+arg_10], 4B9h
0x18001eabb  mov     [rbp+var_28], rsi
0x18001eabf  mov     dword ptr [rbp+var_30], 80004005h
0x18001eac6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001eacb  mov     eax, cs:dword_180044008
0x18001ead1  mov     ebx, 80004005h
0x18001ead6  mov     dword ptr [r15], 0
0x18001eadd  mov     qword ptr [r14], 0
0x18001eae4  cmp     eax, 2
0x18001eae7  jbe     short loc_18001EB3C
0x18001eae9  lea     rax, aFailedToWaitOn; "Failed to wait on thread events"
0x18001eaf0  mov     [rbp+var_18], rdi
0x18001eaf4  mov     [rbp+var_28], rax
0x18001eaf8  lea     rdx, word_18003EF42
0x18001eaff  lea     rax, [rbp+var_18]
0x18001eb03  mov     dword ptr [rbp+arg_0], 4C1h
0x18001eb0a  mov     [rsp+80h+var_40], rax
0x18001eb0f  lea     rax, [rbp+arg_0]
0x18001eb13  mov     [rsp+80h+var_48], rax
0x18001eb18  lea     rax, [rbp+var_20]
0x18001eb1c  mov     [rsp+80h+var_50], rax
0x18001eb21  lea     rax, [rbp+arg_10]
0x18001eb25  mov     [rsp+80h+var_58], rax
0x18001eb2a  lea     rax, [rbp+var_28]
0x18001eb2e  mov     [rbp+var_20], rsi
0x18001eb32  mov     [rbp+arg_10], ebx
0x18001eb35  jmp     loc_18001EA09
0x18001eb3a  xor     ebx, ebx
0x18001eb3c  mov     eax, ebx
0x18001eb3e  mov     rbx, [rsp+80h+arg_8]
0x18001eb46  add     rsp, 80h
0x18001eb4d  pop     r15
0x18001eb4f  pop     r14
0x18001eb51  pop     rdi
0x18001eb52  pop     rsi
0x18001eb53  pop     rbp
0x18001eb54  retn
```
