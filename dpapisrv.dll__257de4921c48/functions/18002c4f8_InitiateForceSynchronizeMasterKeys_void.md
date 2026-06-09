# InitiateForceSynchronizeMasterKeys(void *)

- ea: `0x18002c4f8`
- end: `0x18002c72f`
- name: `?InitiateForceSynchronizeMasterKeys@@YAKPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x180001184`
- `0x1800011e0`
- `0x180007f10`
- `0x180008300`
- `0x18001467c`
- `0x18001c2e0`
- `0x18001c8bc`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001fd64`
- `0x18001ff1c`
- `0x18002c4f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c649`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c5c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c5c6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002c639`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002c639`

## string_xrefs

- `0x18002c5e5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002c65d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall InitiateForceSynchronizeMasterKeys(void *a1)
{
  _DWORD *v2; // r9
  void **v3; // rax
  void **v4; // rdi
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // r8d
  __int64 v8; // rsi
  DWORD LastError; // eax
  __int64 v10; // r9
  int v11; // r9d
  unsigned int v13; // [rsp+30h] [rbp-19h] BYREF
  int v14; // [rsp+38h] [rbp-11h] BYREF
  char v15; // [rsp+3Ch] [rbp-Dh]
  _BYTE v16[16]; // [rsp+40h] [rbp-9h] BYREF
  _DWORD v17[4]; // [rsp+50h] [rbp+7h] BYREF
  char v18[16]; // [rsp+60h] [rbp+17h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  v14 = 0;
  v15 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v2 = v17;
    else
      v2 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18004C260,
      byte_180044C1B,
      v16,
      v2);
  }
  v3 = (void **)LocalAlloc(0, 0x10u);
  v4 = v3;
  if ( v3 )
  {
    *(_OWORD *)v3 = 0;
    *(_DWORD *)v3 = 16;
    v8 = (__int64)(v3 + 1);
    LastError = CPSDuplicateContext(a1, v3 + 1);
    v5 = LastError;
    if ( LastError )
    {
      v10 = 617;
    }
    else
    {
      if ( QueueUserWorkItem(QueueForceSyncMasterKeysThreadFunc, v4, 0x10u) )
        goto LABEL_21;
      LastError = GetLastError();
      v5 = LastError;
      v10 = 632;
    }
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v10);
    goto LABEL_21;
  }
  v5 = 1130;
  DebugTraceError(1130, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 602);
  v8 = 8;
LABEL_21:
  v14 = 2;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
  {
    v13 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18004C260,
      (unsigned int)&byte_180044E17,
      (unsigned int)v16,
      v11,
      (__int64)&v13);
  }
  if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v6, (unsigned int)ETW_LOG_DPAPI_MASTER_KEY_SYNCH, v7, 1, (__int64)v18);
  if ( v5 && v4 )
  {
    if ( *(_QWORD *)v8 )
      CPSFreeContext(*(HLOCAL *)v8);
    LocalFree(v4);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return v5;
}

```

## disassembly

```asm
0x18002c4f8  push    rbp
0x18002c4fa  push    rbx
0x18002c4fb  push    rsi
0x18002c4fc  push    rdi
0x18002c4fd  lea     rbp, [rsp-3Fh]
0x18002c502  sub     rsp, 88h
0x18002c509  mov     rax, cs:__security_cookie
0x18002c510  xor     rax, rsp
0x18002c513  mov     [rbp+57h+var_30], rax
0x18002c517  mov     rbx, rcx
0x18002c51a  lea     rax, WPP_GLOBAL_Control
0x18002c521  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c528  cmp     rcx, rax
0x18002c52b  jz      short loc_18002C548
0x18002c52d  test    byte ptr [rcx+1Ch], 4
0x18002c531  jz      short loc_18002C548
0x18002c533  mov     edx, 0Dh
0x18002c538  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002c53f  mov     rcx, [rcx+10h]
0x18002c543  call    WPP_SF_
0x18002c548  mov     [rbp+57h+var_68], 0
0x18002c54f  mov     [rbp+57h+var_64], 0
0x18002c553  lea     rcx, [rbp+57h+var_68]
0x18002c557  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18002c55c  mov     eax, cs:dword_18004C260
0x18002c562  cmp     eax, 5
0x18002c565  jbe     short loc_18002C5BF
0x18002c567  mov     rdx, 200000000000h
0x18002c571  lea     rcx, dword_18004C260
0x18002c578  call    _tlgKeywordOn
0x18002c57d  test    al, al
0x18002c57f  jz      short loc_18002C5BF
0x18002c581  cmp     [rbp+57h+var_64], 0
0x18002c585  jz      short loc_18002C5A5
0x18002c587  cmp     [rbp+57h+var_50], 0
0x18002c58b  jnz     short loc_18002C59F
0x18002c58d  cmp     [rbp+57h+var_4C], 0
0x18002c591  jnz     short loc_18002C59F
0x18002c593  cmp     [rbp+57h+var_48], 0
0x18002c597  jnz     short loc_18002C59F
0x18002c599  cmp     [rbp+57h+var_44], 0
0x18002c59d  jz      short loc_18002C5A5
0x18002c59f  lea     r9, [rbp+57h+var_50]
0x18002c5a3  jmp     short loc_18002C5A8
0x18002c5a5  xor     r9d, r9d
0x18002c5a8  lea     r8, [rbp+57h+var_60]
0x18002c5ac  lea     rdx, byte_180044C1B
0x18002c5b3  lea     rcx, dword_18004C260
0x18002c5ba  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002c5bf  mov     edx, 10h; uBytes
0x18002c5c4  xor     ecx, ecx; uFlags
0x18002c5c6  call    cs:__imp_LocalAlloc
0x18002c5cd  nop     dword ptr [rax+rax+00h]
0x18002c5d2  mov     rdi, rax
0x18002c5d5  test    rax, rax
0x18002c5d8  jnz     short loc_18002C600
0x18002c5da  mov     ebx, 46Ah
0x18002c5df  mov     r9d, 25Ah
0x18002c5e5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c5ec  lea     rdx, aDwlasterror; "dwLastError"
0x18002c5f3  mov     ecx, ebx
0x18002c5f5  call    DebugTraceError
0x18002c5fa  lea     rsi, [rdi+8]
0x18002c5fe  jmp     short loc_18002C672
0x18002c600  xorps   xmm0, xmm0
0x18002c603  movups  xmmword ptr [rax], xmm0
0x18002c606  mov     dword ptr [rax], 10h
0x18002c60c  lea     rsi, [rax+8]
0x18002c610  mov     rdx, rsi; void **
0x18002c613  mov     rcx, rbx; void *
0x18002c616  call    ?CPSDuplicateContext@@YAKPEAXPEAPEAX@Z; CPSDuplicateContext(void *,void * *)
0x18002c61b  mov     ebx, eax
0x18002c61d  test    eax, eax
0x18002c61f  jz      short loc_18002C629
0x18002c621  mov     r9d, 269h
0x18002c627  jmp     short loc_18002C65D
0x18002c629  mov     r8d, 10h; Flags
0x18002c62f  mov     rdx, rdi; Context
0x18002c632  lea     rcx, ?QueueForceSyncMasterKeysThreadFunc@@YAKPEAX@Z; Function
0x18002c639  call    cs:__imp_QueueUserWorkItem
0x18002c640  nop     dword ptr [rax+rax+00h]
0x18002c645  test    eax, eax
0x18002c647  jnz     short loc_18002C672
0x18002c649  call    cs:__imp_GetLastError
0x18002c650  nop     dword ptr [rax+rax+00h]
0x18002c655  mov     ebx, eax
0x18002c657  mov     r9d, 278h
0x18002c65d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c664  lea     rdx, aDwlasterror; "dwLastError"
0x18002c66b  mov     ecx, eax
0x18002c66d  call    DebugTraceError
0x18002c672  mov     [rbp+57h+var_68], 2
0x18002c679  mov     eax, cs:dword_18004C260
0x18002c67f  cmp     eax, 5
0x18002c682  jbe     short loc_18002C6C1
0x18002c684  mov     rdx, 200000000000h
0x18002c68e  lea     rcx, dword_18004C260
0x18002c695  call    _tlgKeywordOn
0x18002c69a  test    al, al
0x18002c69c  jz      short loc_18002C6C1
0x18002c69e  mov     [rbp+57h+var_70], ebx
0x18002c6a1  lea     rax, [rbp+57h+var_70]
0x18002c6a5  mov     [rsp+0A0h+var_80], rax
0x18002c6aa  lea     r8, [rbp+57h+var_60]
0x18002c6ae  lea     rdx, byte_180044E17
0x18002c6b5  lea     rcx, dword_18004C260
0x18002c6bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002c6c1  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 4
0x18002c6c8  jz      short loc_18002C6E5
0x18002c6ca  lea     rax, [rbp+57h+var_40]
0x18002c6ce  mov     [rsp+0A0h+var_80], rax
0x18002c6d3  mov     r9d, 1
0x18002c6d9  lea     rdx, ETW_LOG_DPAPI_MASTER_KEY_SYNCH
0x18002c6e0  call    McGenEventWrite_EtwEventWriteTransfer
0x18002c6e5  test    ebx, ebx
0x18002c6e7  jz      short loc_18002C70B
0x18002c6e9  test    rdi, rdi
0x18002c6ec  jz      short loc_18002C70B
0x18002c6ee  mov     rcx, [rsi]; hMem
0x18002c6f1  test    rcx, rcx
0x18002c6f4  jz      short loc_18002C6FB
0x18002c6f6  call    ?CPSFreeContext@@YAKPEAX@Z; CPSFreeContext(void *)
0x18002c6fb  mov     rcx, rdi; hMem
0x18002c6fe  call    cs:__imp_LocalFree
0x18002c705  nop     dword ptr [rax+rax+00h]
0x18002c70a  nop
0x18002c70b  lea     rcx, [rbp+57h+var_68]
0x18002c70f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x18002c714  mov     eax, ebx
0x18002c716  mov     rcx, [rbp+57h+var_30]
0x18002c71a  xor     rcx, rsp; StackCookie
0x18002c71d  call    __security_check_cookie
0x18002c722  add     rsp, 88h
0x18002c729  pop     rdi
0x18002c72a  pop     rsi
0x18002c72b  pop     rbx
0x18002c72c  pop     rbp
0x18002c72d  retn
```
