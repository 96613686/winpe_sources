# PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)

- ea: `0x140017d98`
- end: `0x14001800d`
- name: `?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z`
- size: `629`
- prototype: `int(unsigned int (*)(void *), void *, void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001e310`

## callees

- `0x1400014d4`
- `0x1400015ec`
- `0x140017b80`
- `0x140017d98`
- `0x140018014`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140017eea`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140017eea`

## string_xrefs

- `0x140017df6`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140017e89`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140017f07`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140017de3`: `PAL_System_ThreadAllocInit`
- `0x140017e75`: `PAL_System_ThreadAllocInit`
- `0x140017f00`: `PAL_System_ThreadAllocInit`
- `0x140017e63`: `Could not allocate thread`
- `0x140017f27`: `Could not free newly-created thread. Error hr=0x%08x`
- `0x140017fa1`: `Failed to wait on thread events`

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
  int v9; // r8d
  int v10; // r9d
  void *v11; // rax
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
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
          v13 = dword_1400880C8;
          if ( (unsigned int)dword_1400880C8 > 2 )
          {
            LODWORD(v23) = v12;
            v20 = "PAL_System_ThreadAllocInit";
            v21 = "Could not free newly-created thread. Error hr=0x%08x";
            v24 = 1209;
            v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
            LODWORD(v18) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_1400880C8,
              (unsigned int)byte_14007DC89,
              v14,
              v15,
              (__int64)&v21,
              (__int64)&v18,
              (__int64)&v19,
              (__int64)&v24,
              (__int64)&v20,
              (__int64)&v23);
          }
        }
        v16 = dword_1400880C8;
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
            (unsigned int)qword_14007DD60,
            v14,
            v15,
            (__int64)&v19,
            (__int64)&v24,
            (__int64)&v20,
            (__int64)&v23,
            (__int64)&v21);
        }
      }
      else
      {
        return 0;
      }
    }
    else if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v23) = 1181;
      v18 = "Could not allocate thread";
      v20 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1400880C8,
        (unsigned int)byte_14007DD1B,
        v9,
        v10,
        (__int64)&v18,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v20);
    }
  }
  else
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v23) = 1171;
      v20 = "NULL parameter passed";
      v18 = "PAL_System_ThreadAllocInit";
      v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&word_14007DCD6,
        0,
        (_DWORD)a4,
        (__int64)&v20,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v18);
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140017d98  mov     r11, rsp
0x140017d9b  mov     [r11+10h], rbx
0x140017d9f  mov     [r11+8], rcx
0x140017da3  push    rbp
0x140017da4  push    rsi
0x140017da5  push    rdi
0x140017da6  push    r14
0x140017da8  push    r15
0x140017daa  mov     rbp, rsp
0x140017dad  sub     rsp, 80h
0x140017db4  xorps   xmm0, xmm0
0x140017db7  mov     r15, r9
0x140017dba  mov     rdi, r8
0x140017dbd  movups  xmmword ptr [rbp+Handles], xmm0
0x140017dc1  test    r8, r8
0x140017dc4  jnz     short loc_140017E3F
0x140017dc6  mov     eax, cs:dword_1400880C8
0x140017dcc  cmp     eax, 2
0x140017dcf  jbe     short loc_140017E35
0x140017dd1  lea     rax, aNullParameterP; "NULL parameter passed"
0x140017dd8  mov     dword ptr [rbp+arg_0], 493h
0x140017ddf  mov     [rbp+var_20], rax
0x140017de3  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x140017dea  lea     rax, [rbp+var_30]
0x140017dee  mov     [rbp+var_30], rdi
0x140017df2  mov     [r11-68h], rax
0x140017df6  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140017dfd  lea     rax, [rbp+arg_0]
0x140017e01  mov     [rbp+var_28], rsi
0x140017e05  mov     [r11-70h], rax
0x140017e09  lea     rdx, word_14007DCD6
0x140017e10  lea     rax, [rbp+var_28]
0x140017e14  mov     [rbp+arg_10], 80004005h
0x140017e1b  mov     [r11-78h], rax
0x140017e1f  lea     rax, [rbp+arg_10]
0x140017e23  mov     [r11-80h], rax
0x140017e27  lea     rax, [rbp+var_20]
0x140017e2b  mov     [rsp+80h+var_60], rax
0x140017e30  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017e35  mov     ebx, 80070057h
0x140017e3a  jmp     loc_140017FF4
0x140017e3f  mov     r14, [rbp+arg_20]
0x140017e43  mov     r8, r15; unsigned int *
0x140017e46  mov     r9, r14; void **
0x140017e49  call    ?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z; PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)
0x140017e4e  mov     ebx, eax
0x140017e50  test    eax, eax
0x140017e52  jns     short loc_140017ED0
0x140017e54  mov     ecx, cs:dword_1400880C8
0x140017e5a  cmp     ecx, 2
0x140017e5d  jbe     loc_140017FF4
0x140017e63  lea     rax, aCouldNotAlloca; "Could not allocate thread"
0x140017e6a  mov     dword ptr [rbp+arg_0], 49Dh
0x140017e71  mov     [rbp+var_30], rax
0x140017e75  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x140017e7c  lea     rax, [rbp+var_20]
0x140017e80  mov     [rbp+var_20], rdi
0x140017e84  mov     [rsp+80h+var_40], rax
0x140017e89  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140017e90  lea     rax, [rbp+arg_0]
0x140017e94  mov     [rbp+var_28], rsi
0x140017e98  mov     [rsp+80h+var_48], rax
0x140017e9d  lea     rdx, byte_14007DD1B
0x140017ea4  lea     rax, [rbp+var_28]
0x140017ea8  mov     [rbp+arg_10], 80004005h
0x140017eaf  mov     [rsp+80h+var_50], rax
0x140017eb4  lea     rax, [rbp+arg_10]
0x140017eb8  mov     [rsp+80h+var_58], rax
0x140017ebd  lea     rax, [rbp+var_30]
0x140017ec1  mov     [rsp+80h+var_60], rax
0x140017ec6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017ecb  jmp     loc_140017FF4
0x140017ed0  mov     rax, [r14]
0x140017ed3  lea     rdx, [rbp+Handles]; lpHandles
0x140017ed7  xor     r8d, r8d; bWaitAll
0x140017eda  mov     [rbp+Handles], rdi
0x140017ede  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140017ee2  mov     [rbp+Handles+8], rax
0x140017ee6  lea     ecx, [r8+2]; nCount
0x140017eea  call    cs:__imp_WaitForMultipleObjects
0x140017ef0  test    eax, eax
0x140017ef2  jz      loc_140017FF2
0x140017ef8  mov     rcx, [r14]; void *
0x140017efb  call    ?PAL_System_ThreadFree@@YAJPEAX@Z; PAL_System_ThreadFree(void *)
0x140017f00  lea     rdi, aPalSystemThrea_3; "PAL_System_ThreadAllocInit"
0x140017f07  lea     rsi, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140017f0e  test    eax, eax
0x140017f10  jns     short loc_140017F83
0x140017f12  mov     ecx, cs:dword_1400880C8
0x140017f18  cmp     ecx, 2
0x140017f1b  jbe     short loc_140017F83
0x140017f1d  mov     dword ptr [rbp+arg_0], eax
0x140017f20  lea     rdx, byte_14007DC89
0x140017f27  lea     rax, aCouldNotFreeNe; "Could not free newly-created thread. Er"...
0x140017f2e  mov     [rbp+var_20], rdi
0x140017f32  mov     [rbp+var_18], rax
0x140017f36  lea     rax, [rbp+arg_0]
0x140017f3a  mov     [rsp+80h+var_38], rax
0x140017f3f  lea     rax, [rbp+var_20]
0x140017f43  mov     [rsp+80h+var_40], rax
0x140017f48  lea     rax, [rbp+arg_10]
0x140017f4c  mov     [rsp+80h+var_48], rax
0x140017f51  lea     rax, [rbp+var_28]
0x140017f55  mov     [rsp+80h+var_50], rax
0x140017f5a  lea     rax, [rbp+var_30]
0x140017f5e  mov     [rsp+80h+var_58], rax
0x140017f63  lea     rax, [rbp+var_18]
0x140017f67  mov     [rsp+80h+var_60], rax
0x140017f6c  mov     [rbp+arg_10], 4B9h
0x140017f73  mov     [rbp+var_28], rsi
0x140017f77  mov     dword ptr [rbp+var_30], 80004005h
0x140017f7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140017f83  mov     eax, cs:dword_1400880C8
0x140017f89  mov     ebx, 80004005h
0x140017f8e  mov     dword ptr [r15], 0
0x140017f95  mov     qword ptr [r14], 0
0x140017f9c  cmp     eax, 2
0x140017f9f  jbe     short loc_140017FF4
0x140017fa1  lea     rax, aFailedToWaitOn; "Failed to wait on thread events"
0x140017fa8  mov     [rbp+var_18], rdi
0x140017fac  mov     [rbp+var_28], rax
0x140017fb0  lea     rdx, qword_14007DD60
0x140017fb7  lea     rax, [rbp+var_18]
0x140017fbb  mov     dword ptr [rbp+arg_0], 4C1h
0x140017fc2  mov     [rsp+80h+var_40], rax
0x140017fc7  lea     rax, [rbp+arg_0]
0x140017fcb  mov     [rsp+80h+var_48], rax
0x140017fd0  lea     rax, [rbp+var_20]
0x140017fd4  mov     [rsp+80h+var_50], rax
0x140017fd9  lea     rax, [rbp+arg_10]
0x140017fdd  mov     [rsp+80h+var_58], rax
0x140017fe2  lea     rax, [rbp+var_28]
0x140017fe6  mov     [rbp+var_20], rsi
0x140017fea  mov     [rbp+arg_10], ebx
0x140017fed  jmp     loc_140017EC1
0x140017ff2  xor     ebx, ebx
0x140017ff4  mov     eax, ebx
0x140017ff6  mov     rbx, [rsp+80h+arg_8]
0x140017ffe  add     rsp, 80h
0x140018005  pop     r15
0x140018007  pop     r14
0x140018009  pop     rdi
0x14001800a  pop     rsi
0x14001800b  pop     rbp
0x14001800c  retn
```
