# NlSetStatusClientSession(_CLIENT_SESSION *,long)

- ea: `0x180068458`
- end: `0x1800688d9`
- name: `?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z`
- size: `1153`
- prototype: `void __fastcall(struct _CLIENT_SESSION *, int)`
- caller_count: `21`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180022374`
- `0x180027d78`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180031d90`
- `0x180032160`
- `0x180033a34`
- `0x1800344a4`
- `0x180036df8`
- `0x1800378d4`
- `0x18004ecb8`
- `0x18005703c`
- `0x180057434`
- `0x1800585a0`
- `0x18005b7e0`
- `0x180064834`
- `0x18006515c`
- `0x180066108`
- `0x18006b2e0`
- `0x18007070c`

## callees

- `0x180003170`
- `0x180003670`
- `0x180007278`
- `0x18000d710`
- `0x18000ed34`
- `0x18003e71c`
- `0x180052960`
- `0x180063940`
- `0x180068458`
- `0x18006b1d4`
- `0x180070544`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800685cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068607`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800685cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006862e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068881`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006888a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006862e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068881`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006888a`
- `RPCRT4!RpcCancelThread` at `0x180068579`
- `RPCRT4!RpcCancelThread` at `0x180068579`
- `ntdll!RtlLeaveCriticalSection` at `0x180068737`
- `ntdll!RtlLeaveCriticalSection` at `0x1800687b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180068816`
- `ntdll!RtlLeaveCriticalSection` at `0x1800688bb`
- `ntdll!RtlLeaveCriticalSection` at `0x180068737`
- `ntdll!RtlLeaveCriticalSection` at `0x1800687b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180068816`
- `ntdll!RtlLeaveCriticalSection` at `0x1800688bb`
- `ntdll!RtlEnterCriticalSection` at `0x1800684ef`
- `ntdll!RtlEnterCriticalSection` at `0x18006851c`
- `ntdll!RtlEnterCriticalSection` at `0x180068796`
- `ntdll!RtlEnterCriticalSection` at `0x1800684ef`
- `ntdll!RtlEnterCriticalSection` at `0x18006851c`
- `ntdll!RtlEnterCriticalSection` at `0x180068796`
- `netutils!NetApiBufferFree` at `0x1800687c2`
- `netutils!NetApiBufferFree` at `0x180068873`
- `netutils!NetApiBufferFree` at `0x1800687c2`
- `netutils!NetApiBufferFree` at `0x180068873`

## string_xrefs

- `0x1800684c5`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006849c`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800684be`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800686eb`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800688a1`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068569`: `NlSetStatusClientSession: Start RpcCancelThread on %ws\n`
- `0x180068586`: `NlSetStatusClientSession: Finish RpcCancelThread on %ws %ld\n`
- `0x1800685a3`: `NlSetStatusClientSession: No thread handle so can't cancel RPC on %ws\n`

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
  __int64 v15; // r8
  char *v16; // r9
  char v17; // al
  void *v18; // rcx
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  char *v21; // r9
  unsigned int v22; // eax
  unsigned int i; // ebx
  void *v24; // rdx
  __int64 v25; // [rsp+20h] [rbp-48h]
  enum _NL_RPC_BINDING *v26; // [rsp+70h] [rbp+8h] BYREF
  int v27; // [rsp+78h] [rbp+10h]
  void **v28; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  v7 = 0;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v27 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      1894,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      1895,
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
            v28 = (void **)LocalAlloc(0x40u, 8LL * NlGlobalMaxConcurrentApi);
            v7 = v28;
            if ( !v28 )
            {
              NlPrintRoutine(0x100u, L"Cannot LocalAlloc pOldRpchandle\n");
              goto LABEL_18;
            }
            v26 = (enum _NL_RPC_BINDING *)LocalAlloc(0x40u, 4LL * NlGlobalMaxConcurrentApi);
            v8 = v26;
            if ( !v26 )
            {
              NlPrintRoutine(0x100u, L"Cannot LocalAlloc pOldRpcBindingType\n");
              LocalFree(v7);
LABEL_18:
              AcquireHandleBuffers(&v28, &v26, v15, v16);
              v8 = v26;
              v7 = v28;
              v27 = 1;
            }
          }
          v17 = -(*((_DWORD *)v13 + 6) & 2);
          --NlGlobalBindingHandleCount;
          *((_DWORD *)v8 + v4) = (v17 != 0) + 1;
          *((_DWORD *)v13 + 6) &= 0xFFFFFFF8;
          if ( !v11 )
          {
            v18 = (void *)*((_QWORD *)a1 + 63);
            if ( v18 )
            {
              v11 = (void *)NetpAllocWStrFromWStr(v18);
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
                2032,
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
          LODWORD(v25) = RpcCancelThread(*((void **)v13 + 2));
          NlPrintCsRoutine(
            0x100u,
            a1,
            L"NlSetStatusClientSession: Finish RpcCancelThread on %ws %ld\n",
            *((_QWORD *)a1 + 63),
            v25);
        }
        else
        {
          NlPrintCsRoutine(0x100u, a1, L"NlSetStatusClientSession: No thread handle so can't cancel RPC on %ws\n", v14);
        }
      }
LABEL_29:
      if ( ++v4 >= NlGlobalMaxConcurrentApi )
      {
        v10 = v27;
        break;
      }
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  v19 = (_QWORD *)((char *)a1 + 464);
  if ( *((_QWORD *)a1 + 59) || *v19 )
  {
    FreeCredentialsHandle((PCredHandle)a1 + 29);
    *((_QWORD *)a1 + 59) = 0;
    *v19 = 0;
  }
  v20 = *((_QWORD *)a1 + 57);
  if ( v20 )
  {
    NetpMemoryFree(v20);
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
    v22 = NlGlobalMaxConcurrentApi;
    for ( i = 0; i < v22; ++i )
    {
      v24 = v7[i];
      if ( v24 )
      {
        NlpSecureChannelUnbind(a1, v11, "NlSetStatusClientSession", i, v24, *((_DWORD *)v8 + i));
        v22 = NlGlobalMaxConcurrentApi;
      }
    }
    if ( v11 )
      NetApiBufferFree(v11);
    if ( v10 )
    {
      if ( !dword_1800F1FC0 )
        NlAssertFailed(
          "NlFallBackMemory.bCritSecInitialized",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          1854,
          v21);
      RtlLeaveCriticalSection(&stru_1800F1F90);
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
0x180068458  mov     [rsp+arg_18], rbx
0x18006845d  push    rbp
0x18006845e  push    rsi
0x18006845f  push    rdi
0x180068460  push    r12
0x180068462  push    r13
0x180068464  push    r14
0x180068466  push    r15
0x180068468  sub     rsp, 30h
0x18006846c  xor     r12d, r12d
0x18006846f  mov     ebx, edx
0x180068471  mov     rdi, rcx
0x180068474  mov     esi, r12d
0x180068477  mov     r14d, r12d
0x18006847a  mov     [rsp+68h+arg_0], r12
0x18006847f  mov     r13b, r12b
0x180068482  mov     r15d, r12d
0x180068485  mov     ebp, r12d
0x180068488  mov     [rsp+68h+arg_8], r12d
0x18006848d  cmp     [rcx+148h], r12d
0x180068494  ja      short loc_1800684AF
0x180068496  mov     r8d, 766h; unsigned int
0x18006849c  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800684a3  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x1800684aa  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800684af  test    byte ptr [rdi+124h], 8
0x1800684b6  jnz     short loc_1800684D1
0x1800684b8  mov     r8d, 767h; unsigned int
0x1800684be  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800684c5  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x1800684cc  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800684d1  mov     r9d, ebx
0x1800684d4  lea     r8, aNlsetstatuscli_4; "NlSetStatusClientSession: Set connectio"...
0x1800684db  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800684de  mov     ecx, 200h; unsigned int
0x1800684e3  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800684e8  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800684ef  call    cs:__imp_RtlEnterCriticalSection
0x1800684f5  mov     [rdi+120h], ebx
0x1800684fb  test    ebx, ebx
0x1800684fd  js      short loc_18006850E
0x1800684ff  mov     dword ptr [rdi+11Ch], 2
0x180068509  jmp     loc_18006880F
0x18006850e  mov     rcx, [rdi+110h]
0x180068515  add     rcx, 190h; CriticalSection
0x18006851c  call    cs:__imp_RtlEnterCriticalSection
0x180068522  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r12d; ulong NlGlobalMaxConcurrentApi
0x180068529  jbe     loc_180068729
0x18006852f  mov     r15d, r12d
0x180068532  imul    rbx, r15, 230h
0x180068539  add     rbx, 2A8h
0x180068540  add     rbx, rdi
0x180068543  test    byte ptr [rbx+18h], 1
0x180068547  jz      loc_180068714
0x18006854d  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180068551  jz      short loc_1800685B4
0x180068553  cmp     qword ptr [rbx+10h], 0
0x180068558  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006855b  mov     r9, [rdi+1F8h]
0x180068562  mov     ecx, 100h; unsigned int
0x180068567  jz      short loc_1800685A3
0x180068569  lea     r8, aNlsetstatuscli_2; "NlSetStatusClientSession: Start RpcCanc"...
0x180068570  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068575  mov     rcx, [rbx+10h]; Thread
0x180068579  call    cs:__imp_RpcCancelThread
0x18006857f  mov     r9, [rdi+1F8h]
0x180068586  lea     r8, aNlsetstatuscli_1; "NlSetStatusClientSession: Finish RpcCan"...
0x18006858d  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180068590  mov     dword ptr [rsp+68h+var_48], eax
0x180068594  mov     ecx, 100h; unsigned int
0x180068599  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006859e  jmp     loc_180068714
0x1800685a3  lea     r8, aNlsetstatuscli; "NlSetStatusClientSession: No thread han"...
0x1800685aa  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800685af  jmp     loc_180068714
0x1800685b4  test    r13b, r13b
0x1800685b7  jnz     loc_18006865B
0x1800685bd  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x1800685c3  mov     ecx, 40h ; '@'; uFlags
0x1800685c8  shl     rdx, 3; uBytes
0x1800685cc  mov     r13b, 1
0x1800685cf  call    cs:__imp_LocalAlloc
0x1800685d5  mov     [rsp+68h+arg_10], rax
0x1800685dd  mov     rsi, rax
0x1800685e0  test    rax, rax
0x1800685e3  jnz     short loc_1800685F8
0x1800685e5  lea     rdx, aCannotLocalall_0; "Cannot LocalAlloc pOldRpchandle\n"
0x1800685ec  mov     ecx, 100h; unsigned int
0x1800685f1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800685f6  jmp     short loc_180068634
0x1800685f8  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x1800685fe  mov     ecx, 40h ; '@'; uFlags
0x180068603  shl     rdx, 2; uBytes
0x180068607  call    cs:__imp_LocalAlloc
0x18006860d  mov     [rsp+68h+arg_0], rax
0x180068612  mov     r14, rax
0x180068615  test    rax, rax
0x180068618  jnz     short loc_18006865B
0x18006861a  lea     rdx, aCannotLocalall; "Cannot LocalAlloc pOldRpcBindingType\n"
0x180068621  mov     ecx, 100h; unsigned int
0x180068626  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006862b  mov     rcx, rsi; hMem
0x18006862e  call    cs:__imp_LocalFree
0x180068634  lea     rdx, [rsp+68h+arg_0]; enum _NL_RPC_BINDING **
0x180068639  lea     rcx, [rsp+68h+arg_10]; void ***
0x180068641  call    ?AcquireHandleBuffers@@YAXPEAPEAPEAXPEAPEAW4_NL_RPC_BINDING@@@Z; AcquireHandleBuffers(void * * *,_NL_RPC_BINDING * *)
0x180068646  mov     r14, [rsp+68h+arg_0]
0x18006864b  mov     rsi, [rsp+68h+arg_10]
0x180068653  mov     [rsp+68h+arg_8], 1
0x18006865b  mov     eax, [rbx+18h]
0x18006865e  and     al, 2
0x180068660  neg     al
0x180068662  sbb     ecx, ecx
0x180068664  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18006866a  neg     ecx
0x18006866c  inc     ecx
0x18006866e  mov     [r14+r15*4], ecx
0x180068672  and     dword ptr [rbx+18h], 0FFFFFFF8h
0x180068676  test    rbp, rbp
0x180068679  jnz     short loc_1800686AF
0x18006867b  mov     rcx, [rdi+1F8h]; Src
0x180068682  test    rcx, rcx
0x180068685  jz      short loc_1800686AF
0x180068687  call    NetpAllocWStrFromWStr
0x18006868c  mov     rbp, rax
0x18006868f  test    rax, rax
0x180068692  jnz     short loc_1800686AF
0x180068694  mov     r9, [rdi+1F8h]
0x18006869b  lea     r8, aNlsetstatuscli_3; "NlSetStatusClientSession: failed to all"...
0x1800686a2  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800686a5  mov     ecx, 100h; unsigned int
0x1800686aa  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800686af  mov     rcx, rbx
0x1800686b2  mov     rax, 0EA0EA0EA0EA0EA1h
0x1800686bc  sub     rcx, rdi
0x1800686bf  sub     rcx, 2A8h
0x1800686c6  imul    rcx
0x1800686c9  sar     rdx, 5
0x1800686cd  mov     rax, rdx
0x1800686d0  shr     rax, 3Fh
0x1800686d4  add     rdx, rax
0x1800686d7  test    edx, edx
0x1800686d9  jnz     short loc_180068704
0x1800686db  cmp     qword ptr [rdi+1F8h], 0
0x1800686e3  jnz     short loc_1800686FE
0x1800686e5  mov     r8d, 7F0h; unsigned int
0x1800686eb  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800686f2  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x1800686f9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800686fe  mov     [rsi+r15*8], rbp
0x180068702  jmp     short loc_18006870C
0x180068704  mov     rax, [rbx+20h]
0x180068708  mov     [rsi+r15*8], rax
0x18006870c  mov     qword ptr [rbx+20h], 0
0x180068714  inc     r12d
0x180068717  cmp     r12d, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006871e  jb      loc_18006852F
0x180068724  mov     r15d, [rsp+68h+arg_8]
0x180068729  mov     rcx, [rdi+110h]
0x180068730  add     rcx, 190h; CriticalSection
0x180068737  call    cs:__imp_RtlLeaveCriticalSection
0x18006873d  lea     rbx, [rdi+1D0h]
0x180068744  xor     r12d, r12d
0x180068747  cmp     [rbx+8], r12
0x18006874b  jnz     short loc_180068752
0x18006874d  cmp     [rbx], r12
0x180068750  jz      short loc_180068764
0x180068752  mov     rcx, rbx; phCredential
0x180068755  call    FreeCredentialsHandle
0x18006875a  mov     [rdi+1D8h], r12
0x180068761  mov     [rbx], r12
0x180068764  mov     rcx, [rdi+1C8h]
0x18006876b  test    rcx, rcx
0x18006876e  jz      short loc_18006877C
0x180068770  call    NetpMemoryFree
0x180068775  mov     [rdi+1C8h], r12
0x18006877c  mov     [rdi+11Ch], r12d
0x180068783  cmp     [rdi+1F8h], r12
0x18006878a  jz      short loc_1800687CF
0x18006878c  lea     rbx, [rdi+158h]
0x180068793  mov     rcx, rbx; CriticalSection
0x180068796  call    cs:__imp_RtlEnterCriticalSection
0x18006879c  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18006879f  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x1800687a4  mov     rcx, rbx; CriticalSection
0x1800687a7  mov     [rdi+188h], r12
0x1800687ae  mov     [rdi+190h], r12
0x1800687b5  call    cs:__imp_RtlLeaveCriticalSection
0x1800687bb  mov     rcx, [rdi+1F8h]; Buffer
0x1800687c2  call    cs:__imp_NetApiBufferFree
0x1800687c8  mov     [rdi+1F8h], r12
0x1800687cf  xorps   xmm0, xmm0
0x1800687d2  lea     rcx, [rdi+210h]; void *
0x1800687d9  xor     edx, edx; Val
0x1800687db  mov     r8d, 80h; Size
0x1800687e1  movups  xmmword ptr [rdi+200h], xmm0
0x1800687e8  call    memset_0
0x1800687ed  and     dword ptr [rdi+198h], 0FFFFF803h
0x1800687f7  inc     dword ptr [rdi+144h]
0x1800687fd  mov     [rdi+1E0h], r12
0x180068804  mov     [rdi+1A8h], r12
0x18006880b  mov     [rdi+10h], r12
0x18006880f  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180068816  call    cs:__imp_RtlLeaveCriticalSection
0x18006881c  test    r13b, r13b
0x18006881f  jz      loc_1800688C1
0x180068825  mov     eax, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18006882b  mov     ebx, r12d
0x18006882e  test    eax, eax
0x180068830  jz      short loc_18006886B
0x180068832  mov     ecx, ebx
0x180068834  mov     rdx, [rsi+rcx*8]
0x180068838  test    rdx, rdx
0x18006883b  jz      short loc_180068865
0x18006883d  mov     eax, [r14+rcx*4]
0x180068841  lea     r8, aNlsetstatuscli_0; "NlSetStatusClientSession"
0x180068848  mov     [rsp+68h+var_40], eax
0x18006884c  mov     r9d, ebx
0x18006884f  mov     [rsp+68h+var_48], rdx
0x180068854  mov     rcx, rdi
0x180068857  mov     rdx, rbp
0x18006885a  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18006885f  mov     eax, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180068865  inc     ebx
0x180068867  cmp     ebx, eax
0x180068869  jb      short loc_180068832
0x18006886b  test    rbp, rbp
0x18006886e  jz      short loc_180068879
0x180068870  mov     rcx, rbp; Buffer
0x180068873  call    cs:__imp_NetApiBufferFree
0x180068879  test    r15d, r15d
0x18006887c  jnz     short loc_180068892
0x18006887e  mov     rcx, rsi; hMem
0x180068881  call    cs:__imp_LocalFree
0x180068887  mov     rcx, r14; hMem
0x18006888a  call    cs:__imp_LocalFree
0x180068890  jmp     short loc_1800688C1
0x180068892  cmp     cs:dword_1800F1FC0, r12d
0x180068899  jnz     short loc_1800688B4
0x18006889b  mov     r8d, 73Eh; unsigned int
0x1800688a1  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800688a8  lea     rcx, aNlfallbackmemo; "NlFallBackMemory.bCritSecInitialized"
0x1800688af  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800688b4  lea     rcx, stru_1800F1F90; CriticalSection
0x1800688bb  call    cs:__imp_RtlLeaveCriticalSection
0x1800688c1  mov     rbx, [rsp+68h+arg_18]
0x1800688c9  add     rsp, 30h
0x1800688cd  pop     r15
0x1800688cf  pop     r14
0x1800688d1  pop     r13
0x1800688d3  pop     r12
0x1800688d5  pop     rdi
0x1800688d6  pop     rsi
0x1800688d7  pop     rbp
0x1800688d8  retn
```
