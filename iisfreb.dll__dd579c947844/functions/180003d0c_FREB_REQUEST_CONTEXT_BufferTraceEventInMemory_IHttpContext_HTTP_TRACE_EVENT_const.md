# FREB_REQUEST_CONTEXT::BufferTraceEventInMemory(IHttpContext *,HTTP_TRACE_EVENT const *)

- ea: `0x180003d0c`
- end: `0x1800040cd`
- name: `?BufferTraceEventInMemory@FREB_REQUEST_CONTEXT@@QEAAXPEAVIHttpContext@@PEBUHTTP_TRACE_EVENT@@@Z`
- size: `961`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this, struct IHttpContext *, const struct HTTP_TRACE_EVENT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000209c`

## callees

- `0x180003bbc`
- `0x180003d0c`
- `0x18000a6a8`
- `0x18000ac46`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800040b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800040b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004027`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004027`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004019`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004019`
- `iisutil!PuDbgPrint` at `0x180003d72`
- `iisutil!PuDbgPrint` at `0x180003d72`

## string_xrefs

- `0x180003d54`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`
- `0x180003d66`: `Freb: attempt to buffer event:%S\n`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::BufferTraceEventInMemory(
        FREB_REQUEST_CONTEXT *this,
        struct IHttpContext *a2,
        const struct HTTP_TRACE_EVENT *a3)
{
  FREB_REQUEST_CONTEXT *v5; // rsi
  unsigned int v6; // eax
  DWORD v7; // r12d
  DWORD cEventItems; // r10d
  HTTP_TRACE_EVENT_ITEM *pEventItems; // rdx
  int v10; // ecx
  int v11; // ebp
  DWORD i; // r8d
  LPCWSTR pszName; // r9
  __int64 v14; // rax
  LPCWSTR pszDataDescription; // r9
  __int64 v16; // rax
  __int64 v17; // r14
  FREB_LOG_NT_EVENT_TABLE *v18; // rcx
  unsigned __int64 v19; // r13
  __int64 v20; // rcx
  GUID *v21; // r15
  GUID *v22; // rbx
  GUID *v23; // rcx
  HTTP_TRACE_EVENT_ITEM *v24; // rax
  size_t v25; // r8
  GUID *v26; // rcx
  HTTP_TRACE_EVENT_ITEM *v27; // rdx
  LPCWSTR v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // edx
  GUID *v31; // rcx
  LPCWSTR v32; // r8
  GUID *v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // edx
  __int64 *v36; // rdx
  unsigned int v37; // ecx
  unsigned int v38; // eax
  struct TRACE_EVENTS_LIST_ENTRY *v39; // rdx
  __int64 v40; // rax

  v5 = this;
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
      388,
      "FREB_REQUEST_CONTEXT::BufferTraceEventInMemory",
      "Freb: attempt to buffer event:%S\n",
      a3->pszEventName);
  v6 = *((_DWORD *)v5 + 60);
  v7 = 0;
  if ( *((_DWORD *)v5 + 59) <= v6 || !v6 )
  {
    cEventItems = a3->cEventItems;
    pEventItems = a3->pEventItems;
    v10 = 40 * cEventItems + 16;
    if ( !a3->pActivityGuid )
      v10 = 40 * cEventItems;
    v11 = v10 + 16;
    if ( !a3->pRelatedActivityGuid )
      v11 = v10;
    if ( pEventItems )
    {
      for ( i = 0; i < cEventItems; ++i )
      {
        if ( pEventItems[i].pbData )
          v11 += (pEventItems[i].cbData + 7) & 0xFFFFFFF8;
        if ( (a3->dwFlags & 1) == 0 )
        {
          pszName = pEventItems[i].pszName;
          if ( pszName )
          {
            v14 = -1;
            do
              ++v14;
            while ( pszName[v14] );
            v11 += (2 * v14 + 9) & 0xFFFFFFF8;
          }
          pszDataDescription = pEventItems[i].pszDataDescription;
          if ( pszDataDescription )
          {
            v16 = -1;
            do
              ++v16;
            while ( pszDataDescription[v16] );
            v11 += (2 * v16 + 9) & 0xFFFFFFF8;
          }
        }
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 272));
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            (unsigned int)(v11 + 112));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 272));
    if ( v17 )
    {
      v19 = (v17 + 119) & 0xFFFFFFFFFFFFFFF8uLL;
      *(_OWORD *)(v17 + 16) = *(_OWORD *)&a3->pProviderGuid;
      *(_OWORD *)(v17 + 32) = *(_OWORD *)&a3->pAreaGuid;
      *(_OWORD *)(v17 + 48) = *(_OWORD *)&a3->pszEventName;
      *(_OWORD *)(v17 + 64) = *(_OWORD *)&a3->pActivityGuid;
      *(_OWORD *)(v17 + 80) = *(_OWORD *)&a3->dwTimeStamp;
      *(_QWORD *)(v17 + 96) = a3->pEventItems;
      v20 = a3->cEventItems;
      v21 = (GUID *)(40 * v20 + v19);
      v22 = v21;
      if ( (_DWORD)v20 )
        memcpy_0((void *)((v17 + 119) & 0xFFFFFFFFFFFFFFF8uLL), a3->pEventItems, 40 * v20);
      if ( a3->pActivityGuid )
      {
        *(_QWORD *)(v17 + 64) = v21;
        v22 = v21 + 1;
        *v21 = *a3->pActivityGuid;
      }
      if ( a3->pRelatedActivityGuid )
      {
        *(_QWORD *)(v17 + 72) = v22;
        v23 = v22++;
        *v23 = *a3->pRelatedActivityGuid;
      }
      if ( a3->cEventItems )
      {
        do
        {
          v24 = a3->pEventItems;
          if ( v24[v7].pbData )
          {
            v25 = *(unsigned int *)(v19 + 40LL * v7 + 24);
            v26 = v22;
            *(_QWORD *)(v19 + 40LL * v7 + 16) = v22;
            v27 = a3->pEventItems;
            v22 = (GUID *)((char *)v22 + ((v27[v7].cbData + 7) & 0xFFFFFFF8));
            memcpy_0(v26, v27[v7].pbData, v25);
            v24 = a3->pEventItems;
          }
          if ( (a3->dwFlags & 1) == 0 )
          {
            v28 = v24[v7].pszName;
            if ( v28 )
            {
              v29 = -1;
              do
                ++v29;
              while ( v28[v29] );
              v30 = 2 * v29 + 2;
              *(_QWORD *)(v19 + 40LL * v7) = v22;
              v31 = v22;
              v22 = (GUID *)((char *)v22 + ((v30 + 7) & 0xFFFFFFF8));
              memcpy_0(v31, a3->pEventItems[v7].pszName, v30);
            }
            v32 = a3->pEventItems[v7].pszDataDescription;
            if ( v32 )
            {
              v33 = v22;
              v34 = -1;
              do
                ++v34;
              while ( v32[v34] );
              v35 = 2 * v34 + 2;
              *(_QWORD *)(v19 + 40LL * v7 + 32) = v22;
              v22 = (GUID *)((char *)v22 + ((v35 + 7) & 0xFFFFFFF8));
              memcpy_0(v33, a3->pEventItems[v7].pszDataDescription, v35);
            }
          }
          ++v7;
        }
        while ( v7 < a3->cEventItems );
        v5 = this;
      }
      *(_QWORD *)(v17 + 96) = v19;
      *(_DWORD *)(v17 + 104) = GetTickCount();
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 112));
      *((_DWORD *)v5 + 59) += v11 + 1100;
      v36 = (__int64 *)*((_QWORD *)v5 + 13);
      if ( (FREB_REQUEST_CONTEXT *)*v36 != (FREB_REQUEST_CONTEXT *)((char *)v5 + 96) )
        __fastfail(3u);
      *(_QWORD *)v17 = (char *)v5 + 96;
      *(_QWORD *)(v17 + 8) = v36;
      *v36 = v17;
      *((_QWORD *)v5 + 13) = v17;
      v37 = *((_DWORD *)v5 + 60);
      v38 = *((_DWORD *)v5 + 59);
      if ( v38 > v37 )
      {
        if ( v37 )
        {
          if ( v38 - v11 - 1100 <= v37 )
          {
            v39 = (struct TRACE_EVENTS_LIST_ENTRY *)*((_QWORD *)v5 + 33);
            if ( v39 )
            {
              FREB_REQUEST_CONTEXT::AppendCommon(v5, v39);
              v40 = *((_QWORD *)v5 + 33);
              *(_DWORD *)(v40 + 60) = 3;
              *(_QWORD *)(v40 + 48) = L"LOG_FILE_MAX_SIZE_TRUNCATE";
              *((_QWORD *)v5 + 33) = 0;
            }
          }
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 112));
    }
    else
    {
      FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(v18, -2147024888);
    }
  }
}

```

## disassembly

```asm
0x180003d0c  mov     [rsp+arg_0], rcx
0x180003d11  push    rbx
0x180003d12  push    rbp
0x180003d13  push    rsi
0x180003d14  push    rdi
0x180003d15  push    r12
0x180003d17  push    r13
0x180003d19  push    r14
0x180003d1b  push    r15
0x180003d1d  sub     rsp, 38h
0x180003d21  mov     eax, cs:g_dwDebugFlags
0x180003d27  mov     rdi, r8
0x180003d2a  test    al, 3
0x180003d2c  mov     r14, rdx
0x180003d2f  mov     rsi, rcx
0x180003d32  setnz   r9b
0x180003d36  bt      eax, 1Fh
0x180003d3a  setb    al
0x180003d3d  test    al, r9b
0x180003d40  jz      short loc_180003D78
0x180003d42  mov     rax, [r8+20h]
0x180003d46  lea     r9, aFrebRequestCon_3; "FREB_REQUEST_CONTEXT::BufferTraceEventI"...
0x180003d4d  mov     rcx, cs:g_pDebug
0x180003d54  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003d5b  mov     [rsp+78h+var_50], rax
0x180003d60  mov     r8d, 184h
0x180003d66  lea     rax, aFrebAttemptToB; "Freb: attempt to buffer event:%S\n"
0x180003d6d  mov     [rsp+78h+var_58], rax
0x180003d72  call    cs:__imp_PuDbgPrint
0x180003d78  mov     eax, [rsi+0F0h]
0x180003d7e  xor     r12d, r12d
0x180003d81  cmp     [rsi+0ECh], eax
0x180003d87  jbe     short loc_180003D91
0x180003d89  test    eax, eax
0x180003d8b  jnz     loc_1800040BC
0x180003d91  mov     r10d, [rdi+48h]
0x180003d95  mov     r11d, 0FFFFFFF8h
0x180003d9b  mov     rdx, [rdi+50h]
0x180003d9f  lea     eax, [r10+r10*4]
0x180003da3  shl     eax, 3
0x180003da6  cmp     [rdi+30h], r12
0x180003daa  lea     ecx, [rax+10h]
0x180003dad  cmovz   ecx, eax
0x180003db0  cmp     [rdi+38h], r12
0x180003db4  lea     ebp, [rcx+10h]
0x180003db7  cmovz   ebp, ecx
0x180003dba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003dbe  test    rdx, rdx
0x180003dc1  jz      short loc_180003E35
0x180003dc3  mov     r8d, r12d
0x180003dc6  cmp     r8d, r10d
0x180003dc9  jnb     short loc_180003E35
0x180003dcb  mov     eax, r8d
0x180003dce  lea     rcx, [rax+rax*4]
0x180003dd2  cmp     [rdx+rcx*8+10h], r12
0x180003dd7  jz      short loc_180003DE5
0x180003dd9  mov     eax, [rdx+rcx*8+18h]
0x180003ddd  add     eax, 7
0x180003de0  and     eax, r11d
0x180003de3  add     ebp, eax
0x180003de5  test    byte ptr [rdi+44h], 1
0x180003de9  jnz     short loc_180003E30
0x180003deb  mov     r9, [rdx+rcx*8]
0x180003def  test    r9, r9
0x180003df2  jz      short loc_180003E0D
0x180003df4  mov     rax, rbx
0x180003df7  inc     rax
0x180003dfa  cmp     [r9+rax*2], r12w
0x180003dff  jnz     short loc_180003DF7
0x180003e01  lea     eax, ds:9[rax*2]
0x180003e08  and     eax, r11d
0x180003e0b  add     ebp, eax
0x180003e0d  mov     r9, [rdx+rcx*8+20h]
0x180003e12  test    r9, r9
0x180003e15  jz      short loc_180003E30
0x180003e17  mov     rax, rbx
0x180003e1a  inc     rax
0x180003e1d  cmp     [r9+rax*2], r12w
0x180003e22  jnz     short loc_180003E1A
0x180003e24  lea     eax, ds:9[rax*2]
0x180003e2b  and     eax, r11d
0x180003e2e  add     ebp, eax
0x180003e30  inc     r8d
0x180003e33  jmp     short loc_180003DC6
0x180003e35  lea     rbx, [rsi+110h]
0x180003e3c  mov     rcx, rbx; lpCriticalSection
0x180003e3f  call    cs:__imp_EnterCriticalSection
0x180003e45  mov     rax, [r14]
0x180003e48  lea     edx, [rbp+70h]
0x180003e4b  mov     rcx, r14
0x180003e4e  mov     rax, [rax+90h]
0x180003e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5a  mov     rcx, rbx; lpCriticalSection
0x180003e5d  mov     r14, rax
0x180003e60  call    cs:__imp_LeaveCriticalSection
0x180003e66  test    r14, r14
0x180003e69  jnz     short loc_180003E7A
0x180003e6b  mov     edx, 80070008h; int
0x180003e70  call    ?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z; FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)
0x180003e75  jmp     loc_1800040BC
0x180003e7a  movups  xmm0, xmmword ptr [rdi]
0x180003e7d  lea     r13, [r14+77h]
0x180003e81  and     r13, 0FFFFFFFFFFFFFFF8h
0x180003e85  movups  xmmword ptr [r14+10h], xmm0
0x180003e8a  movups  xmm1, xmmword ptr [rdi+10h]
0x180003e8e  movups  xmmword ptr [r14+20h], xmm1
0x180003e93  movups  xmm0, xmmword ptr [rdi+20h]
0x180003e97  movups  xmmword ptr [r14+30h], xmm0
0x180003e9c  movups  xmm1, xmmword ptr [rdi+30h]
0x180003ea0  movups  xmmword ptr [r14+40h], xmm1
0x180003ea5  movups  xmm0, xmmword ptr [rdi+40h]
0x180003ea9  movups  xmmword ptr [r14+50h], xmm0
0x180003eae  movsd   xmm1, qword ptr [rdi+50h]
0x180003eb3  movsd   qword ptr [r14+60h], xmm1
0x180003eb9  mov     ecx, [rdi+48h]
0x180003ebc  lea     rax, [rcx+rcx*4]
0x180003ec0  lea     r8, ds:0[rax*8]; Size
0x180003ec8  lea     r15, [r8+r13]
0x180003ecc  mov     rbx, r15
0x180003ecf  test    ecx, ecx
0x180003ed1  jz      short loc_180003EDF
0x180003ed3  mov     rdx, [rdi+50h]; Src
0x180003ed7  mov     rcx, r13; void *
0x180003eda  call    memcpy_0
0x180003edf  cmp     [rdi+30h], r12
0x180003ee3  jz      short loc_180003EF9
0x180003ee5  mov     [r14+40h], r15
0x180003ee9  lea     rbx, [r15+10h]
0x180003eed  mov     rax, [rdi+30h]
0x180003ef1  movups  xmm0, xmmword ptr [rax]
0x180003ef4  movdqu  xmmword ptr [r15], xmm0
0x180003ef9  cmp     [rdi+38h], r12
0x180003efd  jz      short loc_180003F15
0x180003eff  mov     [r14+48h], rbx
0x180003f03  mov     rcx, rbx
0x180003f06  mov     rax, [rdi+38h]
0x180003f0a  add     rbx, 10h
0x180003f0e  movups  xmm0, xmmword ptr [rax]
0x180003f11  movdqu  xmmword ptr [rcx], xmm0
0x180003f15  xor     r9d, r9d
0x180003f18  cmp     [rdi+48h], r9d
0x180003f1c  jbe     loc_180004015
0x180003f22  mov     esi, 0FFFFFFF8h
0x180003f27  mov     eax, r12d
0x180003f2a  lea     r15, [rax+rax*4]
0x180003f2e  mov     rax, [rdi+50h]
0x180003f32  cmp     [rax+r15*8+10h], r9
0x180003f37  jz      short loc_180003F69
0x180003f39  mov     r8d, [r13+r15*8+18h]; Size
0x180003f3e  mov     rcx, rbx; void *
0x180003f41  mov     [r13+r15*8+10h], rbx
0x180003f46  mov     rdx, [rdi+50h]
0x180003f4a  mov     eax, [rdx+r15*8+18h]
0x180003f4f  mov     rdx, [rdx+r15*8+10h]; Src
0x180003f54  add     eax, 7
0x180003f57  and     rax, rsi
0x180003f5a  add     rbx, rax
0x180003f5d  call    memcpy_0
0x180003f62  mov     rax, [rdi+50h]
0x180003f66  xor     r9d, r9d
0x180003f69  test    byte ptr [rdi+44h], 1
0x180003f6d  jnz     loc_180003FFA
0x180003f73  mov     rcx, [rax+r15*8]
0x180003f77  test    rcx, rcx
0x180003f7a  jz      short loc_180003FB5
0x180003f7c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003f80  inc     rdx
0x180003f83  cmp     [rcx+rdx*2], r9w
0x180003f88  jnz     short loc_180003F80
0x180003f8a  lea     edx, ds:2[rdx*2]
0x180003f91  mov     [r13+r15*8+0], rbx
0x180003f96  lea     eax, [rdx+7]
0x180003f99  mov     r8d, edx; Size
0x180003f9c  mov     rdx, [rdi+50h]
0x180003fa0  and     rax, rsi
0x180003fa3  mov     rcx, rbx; void *
0x180003fa6  add     rbx, rax
0x180003fa9  mov     rdx, [rdx+r15*8]; Src
0x180003fad  call    memcpy_0
0x180003fb2  xor     r9d, r9d
0x180003fb5  mov     rax, [rdi+50h]
0x180003fb9  mov     r8, [rax+r15*8+20h]
0x180003fbe  test    r8, r8
0x180003fc1  jz      short loc_180003FFA
0x180003fc3  mov     rcx, rbx; void *
0x180003fc6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003fca  inc     rdx
0x180003fcd  cmp     [r8+rdx*2], r9w
0x180003fd2  jnz     short loc_180003FCA
0x180003fd4  lea     edx, ds:2[rdx*2]
0x180003fdb  mov     [r13+r15*8+20h], rbx
0x180003fe0  lea     eax, [rdx+7]
0x180003fe3  mov     r8d, edx; Size
0x180003fe6  mov     rdx, [rdi+50h]
0x180003fea  and     rax, rsi
0x180003fed  add     rbx, rax
0x180003ff0  mov     rdx, [rdx+r15*8+20h]; Src
0x180003ff5  call    memcpy_0
0x180003ffa  inc     r12d
0x180003ffd  mov     r9d, 0
0x180004003  cmp     r12d, [rdi+48h]
0x180004007  jb      loc_180003F27
0x18000400d  mov     rsi, [rsp+78h+arg_0]
0x180004015  mov     [r14+60h], r13
0x180004019  call    cs:__imp_GetTickCount
0x18000401f  lea     rcx, [rsi+70h]; lpCriticalSection
0x180004023  mov     [r14+68h], eax
0x180004027  call    cs:__imp_EnterCriticalSection
0x18000402d  lea     eax, [rbp+44Ch]
0x180004033  add     [rsi+0ECh], eax
0x180004039  lea     rax, [rsi+60h]
0x18000403d  mov     rdx, [rax+8]
0x180004041  cmp     [rdx], rax
0x180004044  jz      short loc_18000404D
0x180004046  mov     ecx, 3
0x18000404b  int     29h; Win8: RtlFailFast(ecx)
0x18000404d  mov     [r14], rax
0x180004050  mov     [r14+8], rdx
0x180004054  mov     [rdx], r14
0x180004057  mov     [rax+8], r14
0x18000405b  mov     ecx, [rsi+0F0h]
0x180004061  mov     eax, [rsi+0ECh]
0x180004067  cmp     eax, ecx
0x180004069  jbe     short loc_1800040B2
0x18000406b  test    ecx, ecx
0x18000406d  jz      short loc_1800040B2
0x18000406f  sub     eax, ebp
0x180004071  sub     eax, 44Ch
0x180004076  cmp     eax, ecx
0x180004078  ja      short loc_1800040B2
0x18000407a  mov     rdx, [rsi+108h]; struct TRACE_EVENTS_LIST_ENTRY *
0x180004081  test    rdx, rdx
0x180004084  jz      short loc_1800040B2
0x180004086  mov     rcx, rsi; this
0x180004089  call    ?AppendCommon@FREB_REQUEST_CONTEXT@@AEAAXPEAVTRACE_EVENTS_LIST_ENTRY@@@Z; FREB_REQUEST_CONTEXT::AppendCommon(TRACE_EVENTS_LIST_ENTRY *)
0x18000408e  mov     rax, [rsi+108h]
0x180004095  lea     rcx, aLogFileMaxSize; "LOG_FILE_MAX_SIZE_TRUNCATE"
0x18000409c  mov     dword ptr [rax+3Ch], 3
0x1800040a3  mov     [rax+30h], rcx
0x1800040a7  mov     qword ptr [rsi+108h], 0
0x1800040b2  lea     rcx, [rsi+70h]; lpCriticalSection
0x1800040b6  call    cs:__imp_LeaveCriticalSection
0x1800040bc  add     rsp, 38h
0x1800040c0  pop     r15
0x1800040c2  pop     r14
0x1800040c4  pop     r13
0x1800040c6  pop     r12
0x1800040c8  pop     rdi
0x1800040c9  pop     rsi
0x1800040ca  pop     rbp
0x1800040cb  pop     rbx
0x1800040cc  retn
```
