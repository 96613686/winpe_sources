# NlSetStatusClientSession(_CLIENT_SESSION *,long)

- ea: `0x18006d2b0`
- end: `0x18006d78c`
- name: `?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z`
- size: `1244`
- prototype: `void __fastcall(struct _CLIENT_SESSION *, int)`
- caller_count: `21`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18002346c`
- `0x180029218`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033b90`
- `0x180033f80`
- `0x180035924`
- `0x180036420`
- `0x180038f68`
- `0x180039ac4`
- `0x18005239c`
- `0x18005ae88`
- `0x18005b2b0`
- `0x18005c514`
- `0x18005fa30`
- `0x180069290`
- `0x180069c60`
- `0x18006ad64`
- `0x180070380`
- `0x180075b60`

## callees

- `0x180003250`
- `0x1800037f0`
- `0x180007518`
- `0x18000dd00`
- `0x18000f3e4`
- `0x180040f18`
- `0x1800562f0`
- `0x1800682a4`
- `0x18006d2b0`
- `0x180070260`
- `0x180075998`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d439`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d477`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d439`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d477`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d4a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d730`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d4a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d730`
- `RPCRT4!RpcCancelThread` at `0x18006d3dd`
- `RPCRT4!RpcCancelThread` at `0x18006d3dd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d5b3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d63d`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d6aa`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d767`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d5b3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d63d`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d6aa`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d767`
- `ntdll!RtlEnterCriticalSection` at `0x18006d347`
- `ntdll!RtlEnterCriticalSection` at `0x18006d37a`
- `ntdll!RtlEnterCriticalSection` at `0x18006d618`
- `ntdll!RtlEnterCriticalSection` at `0x18006d347`
- `ntdll!RtlEnterCriticalSection` at `0x18006d37a`
- `ntdll!RtlEnterCriticalSection` at `0x18006d618`
- `netutils!NetApiBufferFree` at `0x18006d650`
- `netutils!NetApiBufferFree` at `0x18006d70d`
- `netutils!NetApiBufferFree` at `0x18006d650`
- `netutils!NetApiBufferFree` at `0x18006d70d`

## string_xrefs

- `0x18006d31d`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006d2f4`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d316`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d567`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d74d`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d3cd`: `NlSetStatusClientSession: Start RpcCancelThread on %ws\n`
- `0x18006d3f0`: `NlSetStatusClientSession: Finish RpcCancelThread on %ws %ld\n`
- `0x18006d40d`: `NlSetStatusClientSession: No thread handle so can't cancel RPC on %ws\n`

## pseudocode

```c
void __fastcall NlSetStatusClientSession(struct _CLIENT_SESSION *a1, int a2, __int64 a3, char *a4)
{
  unsigned int v4; // r12d
  void **v7; // rsi
  enum _NL_RPC_BINDING *v8; // r14
  char v9; // r13
  int v10; // r15d
  void *v11; // rbp
  char *v12; // r9
  char *v13; // rbx
  __int64 v14; // r9
  char v15; // al
  void *v16; // rcx
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  char *v19; // r9
  unsigned int v20; // eax
  unsigned int i; // ebx
  void *v22; // rdx
  __int64 v23; // [rsp+20h] [rbp-48h]
  enum _NL_RPC_BINDING *v24; // [rsp+70h] [rbp+8h] BYREF
  int v25; // [rsp+78h] [rbp+10h]
  void **v26; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  v7 = 0;
  v8 = 0;
  v24 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v25 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x766u,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x767u,
      a4);
  NlPrintCsRoutine(0x200u, a1, L"NlSetStatusClientSession: Set connection status to %lx\n", (unsigned int)a2);
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  *((_DWORD *)a1 + 72) = a2;
  if ( a2 >= 0 )
  {
    *((_DWORD *)a1 + 71) = 2;
    goto LABEL_39;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  if ( NlGlobalMaxConcurrentApi )
  {
    while ( 1 )
    {
      v13 = (char *)a1 + 560 * v4 + 680;
      if ( (v13[24] & 1) != 0 )
      {
        if ( *((_DWORD *)v13 + 2) == -1 )
        {
          if ( !v9 )
          {
            v9 = 1;
            v26 = (void **)LocalAlloc(0x40u, 8LL * NlGlobalMaxConcurrentApi);
            v7 = v26;
            if ( !v26 )
            {
              NlPrintRoutine(0x100u, L"Cannot LocalAlloc pOldRpchandle\n");
              goto LABEL_18;
            }
            v24 = (enum _NL_RPC_BINDING *)LocalAlloc(0x40u, 4LL * NlGlobalMaxConcurrentApi);
            v8 = v24;
            if ( !v24 )
            {
              NlPrintRoutine(0x100u, L"Cannot LocalAlloc pOldRpcBindingType\n");
              LocalFree(v7);
LABEL_18:
              AcquireHandleBuffers(&v26, &v24);
              v8 = v24;
              v7 = v26;
              v25 = 1;
            }
          }
          v15 = -(*((_DWORD *)v13 + 6) & 2);
          --NlGlobalBindingHandleCount;
          *((_DWORD *)v8 + v4) = (v15 != 0) + 1;
          *((_DWORD *)v13 + 6) &= 0xFFFFFFF8;
          if ( !v11 )
          {
            v16 = (void *)*((_QWORD *)a1 + 63);
            if ( v16 )
            {
              v11 = (void *)NetpAllocWStrFromWStr(v16);
              if ( !v11 )
                NlPrintCsRoutine(
                  0x100u,
                  a1,
                  L"NlSetStatusClientSession: failed to allocate server name: %ws\n",
                  *((_QWORD *)a1 + 63));
            }
          }
          if ( (unsigned int)(560LL * v4 / 560) )
          {
            v7[v4] = (void *)*((_QWORD *)v13 + 4);
          }
          else
          {
            if ( !*((_QWORD *)a1 + 63) )
              NlAssertFailed(
                "ClientSession->CsUncServerName != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
                0x7F0u,
                v12);
            v7[v4] = v11;
          }
          *((_QWORD *)v13 + 4) = 0;
          goto LABEL_29;
        }
        v14 = *((_QWORD *)a1 + 63);
        if ( *((_QWORD *)v13 + 2) )
        {
          NlPrintCsRoutine(0x100u, a1, L"NlSetStatusClientSession: Start RpcCancelThread on %ws\n", v14);
          LODWORD(v23) = RpcCancelThread(*((void **)v13 + 2));
          NlPrintCsRoutine(
            0x100u,
            a1,
            L"NlSetStatusClientSession: Finish RpcCancelThread on %ws %ld\n",
            *((_QWORD *)a1 + 63),
            v23);
        }
        else
        {
          NlPrintCsRoutine(0x100u, a1, L"NlSetStatusClientSession: No thread handle so can't cancel RPC on %ws\n", v14);
        }
      }
LABEL_29:
      if ( ++v4 >= NlGlobalMaxConcurrentApi )
      {
        v10 = v25;
        break;
      }
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  v17 = (_QWORD *)((char *)a1 + 464);
  if ( *((_QWORD *)a1 + 59) || *v17 )
  {
    FreeCredentialsHandle((PCredHandle)a1 + 29);
    *((_QWORD *)a1 + 59) = 0;
    *v17 = 0;
  }
  v18 = *((_QWORD *)a1 + 57);
  if ( v18 )
  {
    NetpMemoryFree(v18);
    *((_QWORD *)a1 + 57) = 0;
  }
  *((_DWORD *)a1 + 71) = 0;
  if ( *((_QWORD *)a1 + 63) )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 344));
    NlLogTimeoutRecurringEvents(a1);
    *((_QWORD *)a1 + 49) = 0;
    *((_QWORD *)a1 + 50) = 0;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 344));
    NetApiBufferFree(*((LPVOID *)a1 + 63));
    *((_QWORD *)a1 + 63) = 0;
  }
  *((_OWORD *)a1 + 32) = 0;
  memset_0((char *)a1 + 528, 0, 0x80u);
  *((_DWORD *)a1 + 102) &= 0xFFFFF803;
  ++*((_DWORD *)a1 + 81);
  *((_QWORD *)a1 + 60) = 0;
  *((_QWORD *)a1 + 53) = 0;
  *((_QWORD *)a1 + 2) = 0;
LABEL_39:
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( v9 )
  {
    v20 = NlGlobalMaxConcurrentApi;
    for ( i = 0; i < v20; ++i )
    {
      v22 = v7[i];
      if ( v22 )
      {
        NlpSecureChannelUnbind(a1, v11, "NlSetStatusClientSession", i, v22, *((_DWORD *)v8 + i));
        v20 = NlGlobalMaxConcurrentApi;
      }
    }
    if ( v11 )
      NetApiBufferFree(v11);
    if ( v10 )
    {
      if ( !dword_1800F8F80 )
        NlAssertFailed(
          "NlFallBackMemory.bCritSecInitialized",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          0x73Eu,
          v19);
      RtlLeaveCriticalSection(&stru_1800F8F50);
    }
    else
    {
      LocalFree(v7);
      LocalFree(v8);
    }
  }
}

```

## disassembly

```asm
0x18006d2b0  mov     [rsp+arg_18], rbx
0x18006d2b5  push    rbp
0x18006d2b6  push    rsi
0x18006d2b7  push    rdi
0x18006d2b8  push    r12
0x18006d2ba  push    r13
0x18006d2bc  push    r14
0x18006d2be  push    r15
0x18006d2c0  sub     rsp, 30h
0x18006d2c4  xor     r12d, r12d
0x18006d2c7  mov     ebx, edx
0x18006d2c9  mov     rdi, rcx
0x18006d2cc  mov     esi, r12d
0x18006d2cf  mov     r14d, r12d
0x18006d2d2  mov     [rsp+68h+arg_0], r12
0x18006d2d7  mov     r13b, r12b
0x18006d2da  mov     r15d, r12d
0x18006d2dd  mov     ebp, r12d
0x18006d2e0  mov     [rsp+68h+arg_8], r12d
0x18006d2e5  cmp     [rcx+148h], r12d
0x18006d2ec  ja      short loc_18006D307
0x18006d2ee  mov     r8d, 766h; unsigned int
0x18006d2f4  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d2fb  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006d302  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d307  test    byte ptr [rdi+124h], 8
0x18006d30e  jnz     short loc_18006D329
0x18006d310  mov     r8d, 767h; unsigned int
0x18006d316  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d31d  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18006d324  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d329  mov     r9d, ebx
0x18006d32c  lea     r8, aNlsetstatuscli_4; "NlSetStatusClientSession: Set connectio"...
0x18006d333  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006d336  mov     ecx, 200h; unsigned int
0x18006d33b  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d340  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006d347  call    cs:__imp_RtlEnterCriticalSection
0x18006d34e  nop     dword ptr [rax+rax+00h]
0x18006d353  mov     [rdi+120h], ebx
0x18006d359  test    ebx, ebx
0x18006d35b  js      short loc_18006D36C
0x18006d35d  mov     dword ptr [rdi+11Ch], 2
0x18006d367  jmp     loc_18006D6A3
0x18006d36c  mov     rcx, [rdi+110h]
0x18006d373  add     rcx, 190h; CriticalSection
0x18006d37a  call    cs:__imp_RtlEnterCriticalSection
0x18006d381  nop     dword ptr [rax+rax+00h]
0x18006d386  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r12d; ulong NlGlobalMaxConcurrentApi
0x18006d38d  jbe     loc_18006D5A5
0x18006d393  mov     r15d, r12d
0x18006d396  imul    rbx, r15, 230h
0x18006d39d  add     rbx, 2A8h
0x18006d3a4  add     rbx, rdi
0x18006d3a7  test    byte ptr [rbx+18h], 1
0x18006d3ab  jz      loc_18006D590
0x18006d3b1  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x18006d3b5  jz      short loc_18006D41E
0x18006d3b7  cmp     qword ptr [rbx+10h], 0
0x18006d3bc  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006d3bf  mov     r9, [rdi+1F8h]
0x18006d3c6  mov     ecx, 100h; unsigned int
0x18006d3cb  jz      short loc_18006D40D
0x18006d3cd  lea     r8, aNlsetstatuscli_2; "NlSetStatusClientSession: Start RpcCanc"...
0x18006d3d4  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d3d9  mov     rcx, [rbx+10h]; Thread
0x18006d3dd  call    cs:__imp_RpcCancelThread
0x18006d3e4  nop     dword ptr [rax+rax+00h]
0x18006d3e9  mov     r9, [rdi+1F8h]
0x18006d3f0  lea     r8, aNlsetstatuscli_1; "NlSetStatusClientSession: Finish RpcCan"...
0x18006d3f7  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006d3fa  mov     dword ptr [rsp+68h+var_48], eax
0x18006d3fe  mov     ecx, 100h; unsigned int
0x18006d403  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d408  jmp     loc_18006D590
0x18006d40d  lea     r8, aNlsetstatuscli; "NlSetStatusClientSession: No thread han"...
0x18006d414  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d419  jmp     loc_18006D590
0x18006d41e  test    r13b, r13b
0x18006d421  jnz     loc_18006D4D7
0x18006d427  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006d42d  mov     ecx, 40h ; '@'; uFlags
0x18006d432  shl     rdx, 3; uBytes
0x18006d436  mov     r13b, 1
0x18006d439  call    cs:__imp_LocalAlloc
0x18006d440  nop     dword ptr [rax+rax+00h]
0x18006d445  mov     [rsp+68h+arg_10], rax
0x18006d44d  mov     rsi, rax
0x18006d450  test    rax, rax
0x18006d453  jnz     short loc_18006D468
0x18006d455  lea     rdx, aCannotLocalall_0; "Cannot LocalAlloc pOldRpchandle\n"
0x18006d45c  mov     ecx, 100h; unsigned int
0x18006d461  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006d466  jmp     short loc_18006D4B0
0x18006d468  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006d46e  mov     ecx, 40h ; '@'; uFlags
0x18006d473  shl     rdx, 2; uBytes
0x18006d477  call    cs:__imp_LocalAlloc
0x18006d47e  nop     dword ptr [rax+rax+00h]
0x18006d483  mov     [rsp+68h+arg_0], rax
0x18006d488  mov     r14, rax
0x18006d48b  test    rax, rax
0x18006d48e  jnz     short loc_18006D4D7
0x18006d490  lea     rdx, aCannotLocalall; "Cannot LocalAlloc pOldRpcBindingType\n"
0x18006d497  mov     ecx, 100h; unsigned int
0x18006d49c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006d4a1  mov     rcx, rsi; hMem
0x18006d4a4  call    cs:__imp_LocalFree
0x18006d4ab  nop     dword ptr [rax+rax+00h]
0x18006d4b0  lea     rdx, [rsp+68h+arg_0]; enum _NL_RPC_BINDING **
0x18006d4b5  lea     rcx, [rsp+68h+arg_10]; void ***
0x18006d4bd  call    ?AcquireHandleBuffers@@YAXPEAPEAPEAXPEAPEAW4_NL_RPC_BINDING@@@Z; AcquireHandleBuffers(void * * *,_NL_RPC_BINDING * *)
0x18006d4c2  mov     r14, [rsp+68h+arg_0]
0x18006d4c7  mov     rsi, [rsp+68h+arg_10]
0x18006d4cf  mov     [rsp+68h+arg_8], 1
0x18006d4d7  mov     eax, [rbx+18h]
0x18006d4da  and     al, 2
0x18006d4dc  neg     al
0x18006d4de  sbb     ecx, ecx
0x18006d4e0  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18006d4e6  neg     ecx
0x18006d4e8  inc     ecx
0x18006d4ea  mov     [r14+r15*4], ecx
0x18006d4ee  and     dword ptr [rbx+18h], 0FFFFFFF8h
0x18006d4f2  test    rbp, rbp
0x18006d4f5  jnz     short loc_18006D52B
0x18006d4f7  mov     rcx, [rdi+1F8h]; Src
0x18006d4fe  test    rcx, rcx
0x18006d501  jz      short loc_18006D52B
0x18006d503  call    NetpAllocWStrFromWStr
0x18006d508  mov     rbp, rax
0x18006d50b  test    rax, rax
0x18006d50e  jnz     short loc_18006D52B
0x18006d510  mov     r9, [rdi+1F8h]
0x18006d517  lea     r8, aNlsetstatuscli_3; "NlSetStatusClientSession: failed to all"...
0x18006d51e  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006d521  mov     ecx, 100h; unsigned int
0x18006d526  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d52b  mov     rcx, rbx
0x18006d52e  mov     rax, 0EA0EA0EA0EA0EA1h
0x18006d538  sub     rcx, rdi
0x18006d53b  sub     rcx, 2A8h
0x18006d542  imul    rcx
0x18006d545  sar     rdx, 5
0x18006d549  mov     rax, rdx
0x18006d54c  shr     rax, 3Fh
0x18006d550  add     rdx, rax
0x18006d553  test    edx, edx
0x18006d555  jnz     short loc_18006D580
0x18006d557  cmp     qword ptr [rdi+1F8h], 0
0x18006d55f  jnz     short loc_18006D57A
0x18006d561  mov     r8d, 7F0h; unsigned int
0x18006d567  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d56e  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18006d575  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d57a  mov     [rsi+r15*8], rbp
0x18006d57e  jmp     short loc_18006D588
0x18006d580  mov     rax, [rbx+20h]
0x18006d584  mov     [rsi+r15*8], rax
0x18006d588  mov     qword ptr [rbx+20h], 0
0x18006d590  inc     r12d
0x18006d593  cmp     r12d, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006d59a  jb      loc_18006D393
0x18006d5a0  mov     r15d, [rsp+68h+arg_8]
0x18006d5a5  mov     rcx, [rdi+110h]
0x18006d5ac  add     rcx, 190h; CriticalSection
0x18006d5b3  call    cs:__imp_RtlLeaveCriticalSection
0x18006d5ba  nop     dword ptr [rax+rax+00h]
0x18006d5bf  lea     rbx, [rdi+1D0h]
0x18006d5c6  xor     r12d, r12d
0x18006d5c9  cmp     [rbx+8], r12
0x18006d5cd  jnz     short loc_18006D5D4
0x18006d5cf  cmp     [rbx], r12
0x18006d5d2  jz      short loc_18006D5E6
0x18006d5d4  mov     rcx, rbx; phCredential
0x18006d5d7  call    FreeCredentialsHandle
0x18006d5dc  mov     [rdi+1D8h], r12
0x18006d5e3  mov     [rbx], r12
0x18006d5e6  mov     rcx, [rdi+1C8h]
0x18006d5ed  test    rcx, rcx
0x18006d5f0  jz      short loc_18006D5FE
0x18006d5f2  call    NetpMemoryFree
0x18006d5f7  mov     [rdi+1C8h], r12
0x18006d5fe  mov     [rdi+11Ch], r12d
0x18006d605  cmp     [rdi+1F8h], r12
0x18006d60c  jz      short loc_18006D663
0x18006d60e  lea     rbx, [rdi+158h]
0x18006d615  mov     rcx, rbx; CriticalSection
0x18006d618  call    cs:__imp_RtlEnterCriticalSection
0x18006d61f  nop     dword ptr [rax+rax+00h]
0x18006d624  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18006d627  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x18006d62c  mov     rcx, rbx; CriticalSection
0x18006d62f  mov     [rdi+188h], r12
0x18006d636  mov     [rdi+190h], r12
0x18006d63d  call    cs:__imp_RtlLeaveCriticalSection
0x18006d644  nop     dword ptr [rax+rax+00h]
0x18006d649  mov     rcx, [rdi+1F8h]; Buffer
0x18006d650  call    cs:__imp_NetApiBufferFree
0x18006d657  nop     dword ptr [rax+rax+00h]
0x18006d65c  mov     [rdi+1F8h], r12
0x18006d663  xorps   xmm0, xmm0
0x18006d666  lea     rcx, [rdi+210h]; void *
0x18006d66d  xor     edx, edx; Val
0x18006d66f  mov     r8d, 80h; Size
0x18006d675  movups  xmmword ptr [rdi+200h], xmm0
0x18006d67c  call    memset_0
0x18006d681  and     dword ptr [rdi+198h], 0FFFFF803h
0x18006d68b  inc     dword ptr [rdi+144h]
0x18006d691  mov     [rdi+1E0h], r12
0x18006d698  mov     [rdi+1A8h], r12
0x18006d69f  mov     [rdi+10h], r12
0x18006d6a3  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006d6aa  call    cs:__imp_RtlLeaveCriticalSection
0x18006d6b1  nop     dword ptr [rax+rax+00h]
0x18006d6b6  test    r13b, r13b
0x18006d6b9  jz      loc_18006D773
0x18006d6bf  mov     eax, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006d6c5  mov     ebx, r12d
0x18006d6c8  test    eax, eax
0x18006d6ca  jz      short loc_18006D705
0x18006d6cc  mov     ecx, ebx
0x18006d6ce  mov     rdx, [rsi+rcx*8]
0x18006d6d2  test    rdx, rdx
0x18006d6d5  jz      short loc_18006D6FF
0x18006d6d7  mov     eax, [r14+rcx*4]
0x18006d6db  lea     r8, aNlsetstatuscli_0; "NlSetStatusClientSession"
0x18006d6e2  mov     [rsp+68h+var_40], eax
0x18006d6e6  mov     r9d, ebx
0x18006d6e9  mov     [rsp+68h+var_48], rdx
0x18006d6ee  mov     rcx, rdi
0x18006d6f1  mov     rdx, rbp
0x18006d6f4  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18006d6f9  mov     eax, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006d6ff  inc     ebx
0x18006d701  cmp     ebx, eax
0x18006d703  jb      short loc_18006D6CC
0x18006d705  test    rbp, rbp
0x18006d708  jz      short loc_18006D719
0x18006d70a  mov     rcx, rbp; Buffer
0x18006d70d  call    cs:__imp_NetApiBufferFree
0x18006d714  nop     dword ptr [rax+rax+00h]
0x18006d719  test    r15d, r15d
0x18006d71c  jnz     short loc_18006D73E
0x18006d71e  mov     rcx, rsi; hMem
0x18006d721  call    cs:__imp_LocalFree
0x18006d728  nop     dword ptr [rax+rax+00h]
0x18006d72d  mov     rcx, r14; hMem
0x18006d730  call    cs:__imp_LocalFree
0x18006d737  nop     dword ptr [rax+rax+00h]
0x18006d73c  jmp     short loc_18006D773
0x18006d73e  cmp     cs:dword_1800F8F80, r12d
0x18006d745  jnz     short loc_18006D760
0x18006d747  mov     r8d, 73Eh; unsigned int
0x18006d74d  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d754  lea     rcx, aNlfallbackmemo; "NlFallBackMemory.bCritSecInitialized"
0x18006d75b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d760  lea     rcx, stru_1800F8F50; CriticalSection
0x18006d767  call    cs:__imp_RtlLeaveCriticalSection
0x18006d76e  nop     dword ptr [rax+rax+00h]
0x18006d773  mov     rbx, [rsp+68h+arg_18]
0x18006d77b  add     rsp, 30h
0x18006d77f  pop     r15
0x18006d781  pop     r14
0x18006d783  pop     r13
0x18006d785  pop     r12
0x18006d787  pop     rdi
0x18006d788  pop     rsi
0x18006d789  pop     rbp
0x18006d78a  retn
```
