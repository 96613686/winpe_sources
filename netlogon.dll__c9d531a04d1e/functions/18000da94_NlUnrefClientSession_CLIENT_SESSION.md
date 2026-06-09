# NlUnrefClientSession(_CLIENT_SESSION *)

- ea: `0x18000da94`
- end: `0x18000dd21`
- name: `?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z`
- size: `653`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `46`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005420`
- `0x18000d7e0`
- `0x18000d874`
- `0x18000d9a8`
- `0x180022374`
- `0x1800255f4`
- `0x180025708`
- `0x180027d78`
- `0x180029680`
- `0x18002d3c0`
- `0x18002e730`
- `0x180030d88`
- `0x180031d90`
- `0x180032160`
- `0x180032800`
- `0x18003682c`
- `0x180040bf8`
- `0x180044eb8`
- `0x18004ec14`
- `0x1800585a0`
- `0x18005a840`
- `0x18005a990`
- `0x18005abe0`
- `0x18005af40`
- `0x18005b7e0`
- `0x18005d040`
- `0x18005d1c0`
- `0x18005d440`
- `0x1800636d4`
- `0x1800639e0`
- `0x180063f6c`
- `0x180064520`
- `0x180064674`
- `0x180064f64`
- `0x180065440`
- `0x180065aa8`
- `0x180066108`
- `0x180066904`
- `0x180069178`
- `0x18006925c`
- `0x18006a694`
- `0x18006b2e0`
- `0x18006e960`
- `0x180070470`
- `0x18007070c`
- `0x180073b6c`

## callees

- `0x180003670`
- `0x18000d710`
- `0x18000da94`
- `0x18003e294`
- `0x180052960`
- `0x18006b1d4`
- `0x180070544`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcfb`
- `ntdll!RtlLeaveCriticalSection` at `0x18000db0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000db0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dd1a`
- `ntdll!RtlDeleteCriticalSection` at `0x18000db13`
- `ntdll!RtlDeleteCriticalSection` at `0x18000db13`
- `ntdll!RtlEnterCriticalSection` at `0x18000dab7`
- `ntdll!RtlEnterCriticalSection` at `0x18000daf9`
- `ntdll!RtlEnterCriticalSection` at `0x18000dab7`
- `ntdll!RtlEnterCriticalSection` at `0x18000daf9`
- `netutils!NetApiBufferFree` at `0x18000dcb9`
- `netutils!NetApiBufferFree` at `0x18000dcd2`
- `netutils!NetApiBufferFree` at `0x18000dceb`
- `netutils!NetApiBufferFree` at `0x18000dcb9`
- `netutils!NetApiBufferFree` at `0x18000dcd2`
- `netutils!NetApiBufferFree` at `0x18000dceb`

## string_xrefs

- `0x18000dacf`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18000db9d`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`

## pseudocode

```c
void __fastcall NlUnrefClientSession(char *hMem)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  char *v3; // r9
  char *v5; // r9
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  unsigned int i; // ebx
  __int64 v10; // rsi
  void *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rbx
  __int64 v14; // rcx
  void *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)hMem + 34);
  RtlEnterCriticalSection(v1 + 10);
  if ( !*((_DWORD *)hMem + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      1179,
      v3);
  if ( (*((_DWORD *)hMem + 82))-- == 1 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 344));
    NlLogTimeoutRecurringEvents((struct _CLIENT_SESSION *)hMem);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 344));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 344));
    v6 = (void *)*((_QWORD *)hMem + 52);
    if ( v6 )
      CloseHandle(v6);
    v7 = (void *)*((_QWORD *)hMem + 42);
    if ( v7 )
      CloseHandle(v7);
    v8 = (void *)*((_QWORD *)hMem + 83);
    if ( v8 )
      CloseHandle(v8);
    for ( i = 0; i < NlGlobalMaxConcurrentApi; ++i )
    {
      v10 = 560LL * i;
      v11 = *(void **)&hMem[v10 + 696];
      if ( v11 )
        CloseHandle(v11);
      if ( (hMem[v10 + 704] & 1) != 0 )
      {
        --NlGlobalBindingHandleCount;
        v12 = *((_QWORD *)hMem + 63);
        if ( !v12 )
        {
          NlAssertFailed(
            "ClientSession->CsUncServerName != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
            1261,
            v5);
          v12 = *((_QWORD *)hMem + 63);
        }
        NlpSecureChannelUnbind(
          hMem,
          v12,
          "NlFreeClientSession",
          i,
          *(_QWORD *)&hMem[v10 + 712],
          ((*(_DWORD *)&hMem[v10 + 704] & 2) != 0) + 1);
      }
    }
    v13 = hMem + 464;
    if ( *((_QWORD *)hMem + 59) || *v13 )
    {
      FreeCredentialsHandle((PCredHandle)hMem + 29);
      *((_QWORD *)hMem + 59) = 0;
      *v13 = 0;
    }
    v14 = *((_QWORD *)hMem + 57);
    if ( v14 )
    {
      NetpMemoryFree(v14);
      *((_QWORD *)hMem + 57) = 0;
    }
    v15 = (void *)*((_QWORD *)hMem + 33);
    if ( v15 )
    {
      LocalFree(v15);
      *((_QWORD *)hMem + 33) = 0;
    }
    if ( *((_QWORD *)hMem + 15) )
      NlFreeUnicodeString((struct _UNICODE_STRING *)hMem + 7);
    *((_DWORD *)hMem + 36) = 0;
    hMem[128] = 0;
    if ( *((_QWORD *)hMem + 20) )
      NlFreeUnicodeString((struct _UNICODE_STRING *)(hMem + 152));
    v16 = *((_QWORD *)hMem + 21);
    if ( v16 )
    {
      NetpMemoryFree(v16);
      *((_QWORD *)hMem + 21) = 0;
    }
    v17 = *((_QWORD *)hMem + 32);
    if ( v17 )
    {
      NetpMemoryFree(v17);
      *((_QWORD *)hMem + 32) = 0;
    }
    v18 = (void *)*((_QWORD *)hMem + 63);
    if ( v18 )
    {
      NetApiBufferFree(v18);
      *((_QWORD *)hMem + 63) = 0;
    }
    v19 = (void *)*((_QWORD *)hMem + 25);
    if ( v19 )
    {
      NetApiBufferFree(v19);
      *((_QWORD *)hMem + 25) = 0;
    }
    v20 = (void *)*((_QWORD *)hMem + 82);
    if ( v20 )
    {
      NetApiBufferFree(v20);
      *((_QWORD *)hMem + 82) = 0;
    }
    LocalFree(hMem);
  }
  RtlLeaveCriticalSection(v1 + 10);
}

```

## disassembly

```asm
0x18000da94  mov     [rsp+arg_8], rbx
0x18000da99  mov     [rsp+arg_10], rbp
0x18000da9e  push    rsi
0x18000da9f  push    rdi
0x18000daa0  push    r14
0x18000daa2  sub     rsp, 30h
0x18000daa6  mov     rbp, [rcx+110h]
0x18000daad  mov     rdi, rcx
0x18000dab0  lea     rcx, [rbp+190h]; CriticalSection
0x18000dab7  call    cs:__imp_RtlEnterCriticalSection
0x18000dabd  xor     r14d, r14d
0x18000dac0  cmp     [rdi+148h], r14d
0x18000dac7  ja      short loc_18000DAE2
0x18000dac9  mov     r8d, 49Bh; unsigned int
0x18000dacf  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000dad6  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18000dadd  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000dae2  add     dword ptr [rdi+148h], 0FFFFFFFFh
0x18000dae9  jnz     loc_18000DD01
0x18000daef  lea     rbx, [rdi+158h]
0x18000daf6  mov     rcx, rbx; CriticalSection
0x18000daf9  call    cs:__imp_RtlEnterCriticalSection
0x18000daff  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18000db02  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x18000db07  mov     rcx, rbx; CriticalSection
0x18000db0a  call    cs:__imp_RtlLeaveCriticalSection
0x18000db10  mov     rcx, rbx; CriticalSection
0x18000db13  call    cs:__imp_RtlDeleteCriticalSection
0x18000db19  mov     rcx, [rdi+1A0h]; hObject
0x18000db20  test    rcx, rcx
0x18000db23  jz      short loc_18000DB2B
0x18000db25  call    cs:__imp_CloseHandle
0x18000db2b  mov     rcx, [rdi+150h]; hObject
0x18000db32  test    rcx, rcx
0x18000db35  jz      short loc_18000DB3D
0x18000db37  call    cs:__imp_CloseHandle
0x18000db3d  mov     rcx, [rdi+298h]; hObject
0x18000db44  test    rcx, rcx
0x18000db47  jz      short loc_18000DB4F
0x18000db49  call    cs:__imp_CloseHandle
0x18000db4f  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r14d; ulong NlGlobalMaxConcurrentApi
0x18000db56  mov     ebx, r14d
0x18000db59  jbe     loc_18000DBF9
0x18000db5f  mov     eax, ebx
0x18000db61  imul    rsi, rax, 230h
0x18000db68  mov     rcx, [rsi+rdi+2B8h]; hObject
0x18000db70  test    rcx, rcx
0x18000db73  jz      short loc_18000DB7B
0x18000db75  call    cs:__imp_CloseHandle
0x18000db7b  test    byte ptr [rsi+rdi+2C0h], 1
0x18000db83  jz      short loc_18000DBEB
0x18000db85  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18000db8b  mov     rdx, [rdi+1F8h]
0x18000db92  test    rdx, rdx
0x18000db95  jnz     short loc_18000DBB7
0x18000db97  mov     r8d, 4EDh; unsigned int
0x18000db9d  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000dba4  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18000dbab  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000dbb0  mov     rdx, [rdi+1F8h]
0x18000dbb7  mov     eax, [rsi+rdi+2C0h]
0x18000dbbe  lea     r8, aNlfreeclientse; "NlFreeClientSession"
0x18000dbc5  and     al, 2
0x18000dbc7  mov     r9d, ebx
0x18000dbca  neg     al
0x18000dbcc  mov     rax, [rsi+rdi+2C8h]
0x18000dbd4  sbb     ecx, ecx
0x18000dbd6  neg     ecx
0x18000dbd8  inc     ecx
0x18000dbda  mov     [rsp+48h+var_20], ecx
0x18000dbde  mov     rcx, rdi
0x18000dbe1  mov     [rsp+48h+var_28], rax
0x18000dbe6  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18000dbeb  inc     ebx
0x18000dbed  cmp     ebx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18000dbf3  jb      loc_18000DB5F
0x18000dbf9  lea     rbx, [rdi+1D0h]
0x18000dc00  cmp     [rbx+8], r14
0x18000dc04  jnz     short loc_18000DC0B
0x18000dc06  cmp     [rbx], r14
0x18000dc09  jz      short loc_18000DC1D
0x18000dc0b  mov     rcx, rbx; phCredential
0x18000dc0e  call    FreeCredentialsHandle
0x18000dc13  mov     [rdi+1D8h], r14
0x18000dc1a  mov     [rbx], r14
0x18000dc1d  mov     rcx, [rdi+1C8h]
0x18000dc24  test    rcx, rcx
0x18000dc27  jz      short loc_18000DC35
0x18000dc29  call    NetpMemoryFree
0x18000dc2e  mov     [rdi+1C8h], r14
0x18000dc35  mov     rcx, [rdi+108h]; hMem
0x18000dc3c  test    rcx, rcx
0x18000dc3f  jz      short loc_18000DC4E
0x18000dc41  call    cs:__imp_LocalFree
0x18000dc47  mov     [rdi+108h], r14
0x18000dc4e  lea     rcx, [rdi+70h]; struct _UNICODE_STRING *
0x18000dc52  cmp     [rcx+8], r14
0x18000dc56  jz      short loc_18000DC5D
0x18000dc58  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18000dc5d  lea     rcx, [rdi+98h]; struct _UNICODE_STRING *
0x18000dc64  mov     [rdi+90h], r14d
0x18000dc6b  mov     [rdi+80h], r14b
0x18000dc72  cmp     [rcx+8], r14
0x18000dc76  jz      short loc_18000DC7D
0x18000dc78  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18000dc7d  mov     rcx, [rdi+0A8h]
0x18000dc84  test    rcx, rcx
0x18000dc87  jz      short loc_18000DC95
0x18000dc89  call    NetpMemoryFree
0x18000dc8e  mov     [rdi+0A8h], r14
0x18000dc95  mov     rcx, [rdi+100h]
0x18000dc9c  test    rcx, rcx
0x18000dc9f  jz      short loc_18000DCAD
0x18000dca1  call    NetpMemoryFree
0x18000dca6  mov     [rdi+100h], r14
0x18000dcad  mov     rcx, [rdi+1F8h]; Buffer
0x18000dcb4  test    rcx, rcx
0x18000dcb7  jz      short loc_18000DCC6
0x18000dcb9  call    cs:__imp_NetApiBufferFree
0x18000dcbf  mov     [rdi+1F8h], r14
0x18000dcc6  mov     rcx, [rdi+0C8h]; Buffer
0x18000dccd  test    rcx, rcx
0x18000dcd0  jz      short loc_18000DCDF
0x18000dcd2  call    cs:__imp_NetApiBufferFree
0x18000dcd8  mov     [rdi+0C8h], r14
0x18000dcdf  mov     rcx, [rdi+290h]; Buffer
0x18000dce6  test    rcx, rcx
0x18000dce9  jz      short loc_18000DCF8
0x18000dceb  call    cs:__imp_NetApiBufferFree
0x18000dcf1  mov     [rdi+290h], r14
0x18000dcf8  mov     rcx, rdi; hMem
0x18000dcfb  call    cs:__imp_LocalFree
0x18000dd01  lea     rcx, [rbp+190h]
0x18000dd08  mov     rbx, [rsp+48h+arg_8]
0x18000dd0d  mov     rbp, [rsp+48h+arg_10]
0x18000dd12  add     rsp, 30h
0x18000dd16  pop     r14
0x18000dd18  pop     rdi
0x18000dd19  pop     rsi
0x18000dd1a  jmp     cs:__imp_RtlLeaveCriticalSection
```
