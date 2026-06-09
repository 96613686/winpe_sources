# ETW_TRACE_HANDLER::Initialize(void)

- ea: `0x180002c20`
- end: `0x180002f7c`
- name: `?Initialize@ETW_TRACE_HANDLER@@SAJXZ`
- size: `860`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003070`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002c20`
- `0x180003204`
- `0x180003430`
- `0x180004010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002d1f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002d1f`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002da7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002da7`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180002e3f`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180002e3f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002f29`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002f4d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002f29`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002f4d`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002d82`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002d82`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180002e2e`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180002e2e`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180002f0d`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180002f0d`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180002e08`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180002e08`

## pseudocode

```c
__int64 ETW_TRACE_HANDLER::Initialize(void)
{
  unsigned int v0; // ebp
  char *v1; // rax
  __int64 v2; // rbx
  GUID *v3; // rcx
  ULONG v4; // r14d
  void *v5; // rcx
  EVENT_LOG *v6; // rbx
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  EVENT_LOG *v9; // rax
  EVENT_LOG *v10; // rbx
  __int64 *v11; // rax
  char *v12; // rax
  __int64 v13; // rdi
  __int64 *v14; // rax
  char *v15; // rax
  struct HTTP_TRACING_TABLE *v16; // rbx
  _QWORD v18[5]; // [rsp+50h] [rbp-88h] BYREF
  int v19; // [rsp+78h] [rbp-60h]
  __int16 v20; // [rsp+7Ch] [rbp-5Ch]

  v19 = 32;
  v18[0] = 0;
  v20 = 256;
  v18[4] = v18;
  qword_180007748 = (__int64)&ETW_TRACE_HANDLER::sm_EtwProviderListHead;
  v0 = 0;
  ETW_TRACE_HANDLER::sm_EtwProviderListHead = &ETW_TRACE_HANDLER::sm_EtwProviderListHead;
  qword_180007738 = (__int64)&ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead;
  ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead = &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead;
  if ( off_180007020 )
  {
    do
    {
      if ( (*((_BYTE *)&(&off_180007020)[2 * v0] + 12) & 2) != 0 )
      {
        v1 = (char *)operator new(0x68u);
        v2 = (__int64)v1;
        if ( !v1 )
          goto LABEL_22;
        *((_QWORD *)v1 + 2) = &CCustomEtwTracerV2::`vftable';
        *((_DWORD *)v1 + 6) = 0;
        *(_QWORD *)(v1 + 28) = 1;
        *(_QWORD *)(v1 + 36) = 0;
        *((_QWORD *)v1 + 9) = 0;
        *((_QWORD *)v1 + 10) = 0;
        v3 = (&off_180007020)[2 * v0];
        *((_DWORD *)v1 + 8) = 1;
        *((_DWORD *)v1 + 7) = 1;
        *(GUID *)(v1 + 44) = *v3;
        v4 = EventRegister(v3, (PENABLECALLBACK)ControlCallbackV2, v1 + 16, (PREGHANDLE)v1 + 8);
        if ( !v4 )
        {
          *(_DWORD *)(v2 + 96) = *((_DWORD *)&(&off_180007020)[2 * v0] + 2);
          v11 = (__int64 *)qword_180007738;
          if ( *(void ***)qword_180007738 != &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead )
            goto LABEL_21;
          *(_QWORD *)v2 = &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead;
          *(_QWORD *)(v2 + 8) = v11;
          *v11 = v2;
          qword_180007738 = v2;
          goto LABEL_18;
        }
        v5 = (void *)v2;
        *(_QWORD *)(v2 + 16) = &CCustomEtwTracerV2::`vftable';
      }
      else
      {
        v12 = (char *)operator new(0x58u);
        v13 = (__int64)v12;
        if ( !v12 )
        {
LABEL_22:
          ETW_TRACE_HANDLER::Terminate();
          goto LABEL_24;
        }
        CEtwTracer::CEtwTracer((CEtwTracer *)(v12 + 16));
        *(_QWORD *)(v13 + 16) = &CCustomEtwTracer::`vftable';
        v4 = CEtwTracer::Register((CEtwTracer *)(v13 + 16), (&off_180007020)[2 * v0], 0, 0);
        if ( !v4 )
        {
          *(_DWORD *)(v13 + 80) = *((_DWORD *)&(&off_180007020)[2 * v0] + 2);
          v14 = (__int64 *)qword_180007748;
          if ( *(void ***)qword_180007748 != &ETW_TRACE_HANDLER::sm_EtwProviderListHead )
LABEL_21:
            __fastfail(3u);
          *(_QWORD *)v13 = &ETW_TRACE_HANDLER::sm_EtwProviderListHead;
          *(_QWORD *)(v13 + 8) = v14;
          *v14 = v13;
          qword_180007748 = v13;
          goto LABEL_18;
        }
        CEtwTracer::~CEtwTracer((CEtwTracer *)(v13 + 16));
        v5 = (void *)v13;
      }
      operator delete(v5);
      v6 = (EVENT_LOG *)operator new(4u);
      if ( v6 )
      {
        v7 = (**(__int64 (__fastcall ***)(struct IHttpServer *))s_pGlobalInfo)(s_pGlobalInfo);
        v8 = L"HostableWebCore";
        if ( !v7 )
          v8 = L"W3SVC-WP";
        v9 = EVENT_LOG::EVENT_LOG(v6, v8);
        v10 = v9;
        if ( v9 )
        {
          EVENT_LOG::LogEvent(v9, 0x800008E3, 0, 0, v4);
          operator delete(v10);
        }
      }
LABEL_18:
      ++v0;
    }
    while ( (&off_180007020)[2 * v0] );
  }
  v15 = (char *)operator new(0x50u);
  v16 = (struct HTTP_TRACING_TABLE *)v15;
  if ( v15 )
  {
    CLKRHashTable::CLKRHashTable(
      (CLKRHashTable *)(v15 + 8),
      "HTTP_TRACING_TABLE",
      (unsigned __int64 (*)(const void *))CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,unsigned long,CLKRHashTable>::_ExtractKey,
      (unsigned int (*)(unsigned __int64))CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,unsigned long,CLKRHashTable>::_CalcKeyHash,
      (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,unsigned long,CLKRHashTable>::_EqualKeys,
      (void (*)(const void *, int))CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,unsigned long,CLKRHashTable>::_AddRefRecord,
      4.0,
      1u,
      0,
      0);
    ETW_TRACE_HANDLER::sm_pHttpTracingTable = v16;
    *(_QWORD *)v16 = &HTTP_TRACING_TABLE::`vftable';
    BUFFER::~BUFFER((BUFFER *)v18);
    return 0;
  }
  else
  {
    ETW_TRACE_HANDLER::sm_pHttpTracingTable = 0;
LABEL_24:
    BUFFER::~BUFFER((BUFFER *)v18);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180002c20  push    rbx
0x180002c22  push    rbp
0x180002c23  push    rsi
0x180002c24  push    rdi
0x180002c25  push    r12
0x180002c27  push    r13
0x180002c29  push    r14
0x180002c2b  push    r15
0x180002c2d  sub     rsp, 98h
0x180002c34  mov     rax, cs:__security_cookie
0x180002c3b  xor     rax, rsp
0x180002c3e  mov     [rsp+0D8h+var_58], rax
0x180002c46  xor     r15d, r15d
0x180002c49  mov     [rsp+0D8h+var_60], 20h ; ' '
0x180002c51  cmp     cs:off_180007020, r15
0x180002c58  lea     r13, ?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x180002c5f  lea     r12, ?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x180002c66  mov     [rsp+0D8h+var_88], r15
0x180002c6b  lea     rax, [rsp+0D8h+var_88]
0x180002c70  mov     [rsp+0D8h+var_5C], 100h
0x180002c77  lea     r14d, [r15+1]
0x180002c7b  mov     [rsp+0D8h+var_68], rax
0x180002c80  mov     cs:qword_180007748, r13
0x180002c87  mov     ebp, r15d
0x180002c8a  mov     cs:?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A, r13; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x180002c91  mov     cs:qword_180007738, r12
0x180002c98  mov     cs:?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A, r12; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x180002c9f  jz      loc_180002EA9
0x180002ca5  lea     rax, off_180007020
0x180002cac  lea     rdi, ??_7CCustomEtwTracerV2@@6B@; const CCustomEtwTracerV2::`vftable'
0x180002cb3  mov     esi, ebp
0x180002cb5  add     rsi, rsi
0x180002cb8  test    byte ptr [rax+rsi*8+0Ch], 2
0x180002cbd  jz      loc_180002DEE
0x180002cc3  mov     ecx, 68h ; 'h'; Size
0x180002cc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ccd  mov     rbx, rax
0x180002cd0  test    rax, rax
0x180002cd3  jz      loc_180002F3A
0x180002cd9  mov     [rax+10h], rdi
0x180002cdd  lea     r9, [rbx+40h]; RegHandle
0x180002ce1  mov     [rax+18h], r15d
0x180002ce5  lea     r8, [rbx+10h]; CallbackContext
0x180002ce9  mov     qword ptr [rax+1Ch], 1
0x180002cf1  lea     rdx, ControlCallbackV2; EnableCallback
0x180002cf8  mov     [rax+24h], r15
0x180002cfc  mov     [rax+48h], r15
0x180002d00  mov     [rax+50h], r15
0x180002d04  lea     rax, off_180007020
0x180002d0b  mov     rcx, [rax+rsi*8]; ProviderId
0x180002d0f  mov     [rbx+20h], r14d
0x180002d13  mov     [rbx+1Ch], r14d
0x180002d17  movups  xmm0, xmmword ptr [rcx]
0x180002d1a  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x180002d1f  call    cs:__imp_EventRegister
0x180002d25  mov     r14d, eax
0x180002d28  test    eax, eax
0x180002d2a  jz      loc_180002DBA
0x180002d30  lea     rax, ??_7CCustomEtwTracerV2@@6B@; const CCustomEtwTracerV2::`vftable'
0x180002d37  mov     rcx, rbx; Block
0x180002d3a  mov     [rbx+10h], rax
0x180002d3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d43  mov     ecx, 4; Size
0x180002d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d4d  mov     rbx, rax
0x180002d50  test    rax, rax
0x180002d53  jz      loc_180002E7C
0x180002d59  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180002d60  mov     rdx, [rcx]
0x180002d63  mov     rax, [rdx]
0x180002d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6b  test    eax, eax
0x180002d6d  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180002d74  lea     rax, aW3svcWp; "W3SVC-WP"
0x180002d7b  mov     rcx, rbx
0x180002d7e  cmovz   rdx, rax
0x180002d82  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180002d88  mov     rbx, rax
0x180002d8b  test    rax, rax
0x180002d8e  jz      loc_180002E7C
0x180002d94  xor     r8d, r8d
0x180002d97  mov     dword ptr [rsp+0D8h+var_B8], r14d
0x180002d9c  xor     r9d, r9d
0x180002d9f  mov     edx, 800008E3h
0x180002da4  mov     rcx, rax
0x180002da7  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180002dad  mov     rcx, rbx; Block
0x180002db0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002db5  jmp     loc_180002E7C
0x180002dba  lea     rax, off_180007020
0x180002dc1  mov     eax, [rax+rsi*8+8]
0x180002dc5  mov     [rbx+60h], eax
0x180002dc8  mov     rax, cs:qword_180007738
0x180002dcf  cmp     [rax], r12
0x180002dd2  jnz     loc_180002F33
0x180002dd8  mov     [rbx], r12
0x180002ddb  mov     [rbx+8], rax
0x180002ddf  mov     [rax], rbx
0x180002de2  mov     cs:qword_180007738, rbx
0x180002de9  jmp     loc_180002E7C
0x180002dee  mov     ecx, 58h ; 'X'; Size
0x180002df3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002df8  mov     rdi, rax
0x180002dfb  test    rax, rax
0x180002dfe  jz      loc_180002F3A
0x180002e04  lea     rcx, [rax+10h]
0x180002e08  call    cs:__imp_??0CEtwTracer@@QEAA@XZ; CEtwTracer::CEtwTracer(void)
0x180002e0e  lea     rax, ??_7CCustomEtwTracer@@6B@; const CCustomEtwTracer::`vftable'
0x180002e15  xor     r9d, r9d
0x180002e18  mov     [rdi+10h], rax
0x180002e1c  lea     rcx, [rdi+10h]
0x180002e20  lea     rax, off_180007020
0x180002e27  xor     r8d, r8d
0x180002e2a  mov     rdx, [rax+rsi*8]
0x180002e2e  call    cs:__imp_?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z; CEtwTracer::Register(_GUID const *,ushort *,ushort *)
0x180002e34  mov     r14d, eax
0x180002e37  test    eax, eax
0x180002e39  jz      short loc_180002E4D
0x180002e3b  lea     rcx, [rdi+10h]
0x180002e3f  call    cs:__imp_??1CEtwTracer@@QEAA@XZ; CEtwTracer::~CEtwTracer(void)
0x180002e45  mov     rcx, rdi
0x180002e48  jmp     loc_180002D3E
0x180002e4d  lea     rax, off_180007020
0x180002e54  mov     eax, [rax+rsi*8+8]
0x180002e58  mov     [rdi+50h], eax
0x180002e5b  mov     rax, cs:qword_180007748
0x180002e62  cmp     [rax], r13
0x180002e65  jnz     loc_180002F33
0x180002e6b  mov     [rdi], r13
0x180002e6e  mov     [rdi+8], rax
0x180002e72  mov     [rax], rdi
0x180002e75  mov     cs:qword_180007748, rdi
0x180002e7c  mov     r14d, 1
0x180002e82  lea     rcx, off_180007020
0x180002e89  add     ebp, r14d
0x180002e8c  lea     rdi, ??_7CCustomEtwTracerV2@@6B@; const CCustomEtwTracerV2::`vftable'
0x180002e93  mov     eax, ebp
0x180002e95  add     rax, rax
0x180002e98  cmp     [rcx+rax*8], r15
0x180002e9c  lea     rax, off_180007020
0x180002ea3  jnz     loc_180002CB3
0x180002ea9  mov     ecx, 50h ; 'P'; Size
0x180002eae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002eb3  mov     rbx, rax
0x180002eb6  test    rax, rax
0x180002eb9  jz      loc_180002F41
0x180002ebf  movsd   xmm0, cs:__real@4010000000000000
0x180002ec7  lea     rcx, [rax+8]
0x180002ecb  mov     [rsp+0D8h+var_90], r15b
0x180002ed0  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VHTTP_TRACING_TABLE@@VTRACE_URLS_LIST@@KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180002ed7  mov     [rsp+0D8h+var_98], r15d
0x180002edc  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VHTTP_TRACING_TABLE@@VTRACE_URLS_LIST@@KVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,ulong,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180002ee3  mov     [rsp+0D8h+var_A0], r14d
0x180002ee8  lea     r8, ?_ExtractKey@?$CTypedHashTable@VHTTP_TRACING_TABLE@@VTRACE_URLS_LIST@@KVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,ulong,CLKRHashTable>::_ExtractKey(void const *)
0x180002eef  movsd   [rsp+0D8h+var_A8], xmm0
0x180002ef5  lea     rdx, aHttpTracingTab; "HTTP_TRACING_TABLE"
0x180002efc  mov     [rsp+0D8h+var_B0], rax
0x180002f01  lea     rax, ?_EqualKeys@?$CTypedHashTable@VHTTP_TRACING_TABLE@@VTRACE_URLS_LIST@@KVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,ulong,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180002f08  mov     [rsp+0D8h+var_B8], rax
0x180002f0d  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180002f13  lea     rax, ??_7HTTP_TRACING_TABLE@@6B@; const HTTP_TRACING_TABLE::`vftable'
0x180002f1a  mov     cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA, rbx; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x180002f21  lea     rcx, [rsp+0D8h+var_88]
0x180002f26  mov     [rbx], rax
0x180002f29  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002f2f  xor     eax, eax
0x180002f31  jmp     short loc_180002F58
0x180002f33  mov     ecx, 3
0x180002f38  int     29h; Win8: RtlFailFast(ecx)
0x180002f3a  call    ?Terminate@ETW_TRACE_HANDLER@@SAXXZ; ETW_TRACE_HANDLER::Terminate(void)
0x180002f3f  jmp     short loc_180002F48
0x180002f41  mov     cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA, r15; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x180002f48  lea     rcx, [rsp+0D8h+var_88]
0x180002f4d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002f53  mov     eax, 80070008h
0x180002f58  mov     rcx, [rsp+0D8h+var_58]
0x180002f60  xor     rcx, rsp; StackCookie
0x180002f63  call    __security_check_cookie
0x180002f68  add     rsp, 98h
0x180002f6f  pop     r15
0x180002f71  pop     r14
0x180002f73  pop     r13
0x180002f75  pop     r12
0x180002f77  pop     rdi
0x180002f78  pop     rsi
0x180002f79  pop     rbp
0x180002f7a  pop     rbx
0x180002f7b  retn
```
