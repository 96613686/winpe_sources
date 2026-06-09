# InitiateSynchronizeMasterKeys(void *)

- ea: `0x180019d00`
- end: `0x180019f37`
- name: `?InitiateSynchronizeMasterKeys@@YAKPEAX@Z`
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
- `0x180019d00`
- `0x18001c2e0`
- `0x18001c8bc`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001fd64`
- `0x18001ff1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019dce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019dce`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180019e41`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180019e41`

## string_xrefs

- `0x180019ded`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180019e65`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall InitiateSynchronizeMasterKeys(void *a1)
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
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
      qword_180045010,
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
      v10 = 438;
    }
    else
    {
      if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)QueueSyncMasterKeysThreadFunc, v4, 0x10u) )
        goto LABEL_21;
      LastError = GetLastError();
      v5 = LastError;
      v10 = 455;
    }
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v10);
    goto LABEL_21;
  }
  v5 = 1130;
  DebugTraceError(1130, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 423);
  v8 = 8;
LABEL_21:
  v14 = 2;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x200000000000LL) )
  {
    v13 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18004C260,
      (unsigned int)byte_180044DE1,
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
0x180019d00  push    rbp
0x180019d02  push    rbx
0x180019d03  push    rsi
0x180019d04  push    rdi
0x180019d05  lea     rbp, [rsp-3Fh]
0x180019d0a  sub     rsp, 88h
0x180019d11  mov     rax, cs:__security_cookie
0x180019d18  xor     rax, rsp
0x180019d1b  mov     [rbp+57h+var_30], rax
0x180019d1f  mov     rbx, rcx
0x180019d22  lea     rax, WPP_GLOBAL_Control
0x180019d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d30  cmp     rcx, rax
0x180019d33  jz      short loc_180019D50
0x180019d35  test    byte ptr [rcx+1Ch], 4
0x180019d39  jz      short loc_180019D50
0x180019d3b  mov     edx, 0Ah
0x180019d40  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180019d47  mov     rcx, [rcx+10h]
0x180019d4b  call    WPP_SF_
0x180019d50  mov     [rbp+57h+var_68], 0
0x180019d57  mov     [rbp+57h+var_64], 0
0x180019d5b  lea     rcx, [rbp+57h+var_68]
0x180019d5f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180019d64  mov     eax, cs:dword_18004C260
0x180019d6a  cmp     eax, 5
0x180019d6d  jbe     short loc_180019DC7
0x180019d6f  mov     rdx, 200000000000h
0x180019d79  lea     rcx, dword_18004C260
0x180019d80  call    _tlgKeywordOn
0x180019d85  test    al, al
0x180019d87  jz      short loc_180019DC7
0x180019d89  cmp     [rbp+57h+var_64], 0
0x180019d8d  jz      short loc_180019DAD
0x180019d8f  cmp     [rbp+57h+var_50], 0
0x180019d93  jnz     short loc_180019DA7
0x180019d95  cmp     [rbp+57h+var_4C], 0
0x180019d99  jnz     short loc_180019DA7
0x180019d9b  cmp     [rbp+57h+var_48], 0
0x180019d9f  jnz     short loc_180019DA7
0x180019da1  cmp     [rbp+57h+var_44], 0
0x180019da5  jz      short loc_180019DAD
0x180019da7  lea     r9, [rbp+57h+var_50]
0x180019dab  jmp     short loc_180019DB0
0x180019dad  xor     r9d, r9d
0x180019db0  lea     r8, [rbp+57h+var_60]
0x180019db4  lea     rdx, qword_180045010
0x180019dbb  lea     rcx, dword_18004C260
0x180019dc2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180019dc7  mov     edx, 10h; uBytes
0x180019dcc  xor     ecx, ecx; uFlags
0x180019dce  call    cs:__imp_LocalAlloc
0x180019dd5  nop     dword ptr [rax+rax+00h]
0x180019dda  mov     rdi, rax
0x180019ddd  test    rax, rax
0x180019de0  jnz     short loc_180019E08
0x180019de2  mov     ebx, 46Ah
0x180019de7  mov     r9d, 1A7h
0x180019ded  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180019df4  lea     rdx, aDwlasterror; "dwLastError"
0x180019dfb  mov     ecx, ebx
0x180019dfd  call    DebugTraceError
0x180019e02  lea     rsi, [rdi+8]
0x180019e06  jmp     short loc_180019E7A
0x180019e08  xorps   xmm0, xmm0
0x180019e0b  movups  xmmword ptr [rax], xmm0
0x180019e0e  mov     dword ptr [rax], 10h
0x180019e14  lea     rsi, [rax+8]
0x180019e18  mov     rdx, rsi; void **
0x180019e1b  mov     rcx, rbx; void *
0x180019e1e  call    ?CPSDuplicateContext@@YAKPEAXPEAPEAX@Z; CPSDuplicateContext(void *,void * *)
0x180019e23  mov     ebx, eax
0x180019e25  test    eax, eax
0x180019e27  jz      short loc_180019E31
0x180019e29  mov     r9d, 1B6h
0x180019e2f  jmp     short loc_180019E65
0x180019e31  mov     r8d, 10h; Flags
0x180019e37  mov     rdx, rdi; Context
0x180019e3a  lea     rcx, ?QueueSyncMasterKeysThreadFunc@@YAKPEAX@Z; Function
0x180019e41  call    cs:__imp_QueueUserWorkItem
0x180019e48  nop     dword ptr [rax+rax+00h]
0x180019e4d  test    eax, eax
0x180019e4f  jnz     short loc_180019E7A
0x180019e51  call    cs:__imp_GetLastError
0x180019e58  nop     dword ptr [rax+rax+00h]
0x180019e5d  mov     ebx, eax
0x180019e5f  mov     r9d, 1C7h
0x180019e65  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180019e6c  lea     rdx, aDwlasterror; "dwLastError"
0x180019e73  mov     ecx, eax
0x180019e75  call    DebugTraceError
0x180019e7a  mov     [rbp+57h+var_68], 2
0x180019e81  mov     eax, cs:dword_18004C260
0x180019e87  cmp     eax, 5
0x180019e8a  jbe     short loc_180019EC9
0x180019e8c  mov     rdx, 200000000000h
0x180019e96  lea     rcx, dword_18004C260
0x180019e9d  call    _tlgKeywordOn
0x180019ea2  test    al, al
0x180019ea4  jz      short loc_180019EC9
0x180019ea6  mov     [rbp+57h+var_70], ebx
0x180019ea9  lea     rax, [rbp+57h+var_70]
0x180019ead  mov     [rsp+0A0h+var_80], rax
0x180019eb2  lea     r8, [rbp+57h+var_60]
0x180019eb6  lea     rdx, byte_180044DE1
0x180019ebd  lea     rcx, dword_18004C260
0x180019ec4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180019ec9  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 4
0x180019ed0  jz      short loc_180019EED
0x180019ed2  lea     rax, [rbp+57h+var_40]
0x180019ed6  mov     [rsp+0A0h+var_80], rax
0x180019edb  mov     r9d, 1
0x180019ee1  lea     rdx, ETW_LOG_DPAPI_MASTER_KEY_SYNCH
0x180019ee8  call    McGenEventWrite_EtwEventWriteTransfer
0x180019eed  test    ebx, ebx
0x180019eef  jz      short loc_180019F13
0x180019ef1  test    rdi, rdi
0x180019ef4  jz      short loc_180019F13
0x180019ef6  mov     rcx, [rsi]; hMem
0x180019ef9  test    rcx, rcx
0x180019efc  jz      short loc_180019F03
0x180019efe  call    ?CPSFreeContext@@YAKPEAX@Z; CPSFreeContext(void *)
0x180019f03  mov     rcx, rdi; hMem
0x180019f06  call    cs:__imp_LocalFree
0x180019f0d  nop     dword ptr [rax+rax+00h]
0x180019f12  nop
0x180019f13  lea     rcx, [rbp+57h+var_68]
0x180019f17  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x180019f1c  mov     eax, ebx
0x180019f1e  mov     rcx, [rbp+57h+var_30]
0x180019f22  xor     rcx, rsp; StackCookie
0x180019f25  call    __security_check_cookie
0x180019f2a  add     rsp, 88h
0x180019f31  pop     rdi
0x180019f32  pop     rsi
0x180019f33  pop     rbx
0x180019f34  pop     rbp
0x180019f35  retn
```
