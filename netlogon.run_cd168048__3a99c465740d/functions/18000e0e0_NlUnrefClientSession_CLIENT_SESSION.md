# NlUnrefClientSession(_CLIENT_SESSION *)

- ea: `0x18000e0e0`
- end: `0x18000e3c0`
- name: `?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z`
- size: `736`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `46`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800055d4`
- `0x18000ddec`
- `0x18000de8c`
- `0x18000dfd4`
- `0x18002346c`
- `0x1800266b0`
- `0x1800267ec`
- `0x180029218`
- `0x18002ada0`
- `0x18002eed0`
- `0x18003033c`
- `0x180032aa4`
- `0x180033b90`
- `0x180033f80`
- `0x180034650`
- `0x180038944`
- `0x18004370c`
- `0x180047dfc`
- `0x1800522f4`
- `0x18005c514`
- `0x18005ea30`
- `0x18005eb90`
- `0x18005ee10`
- `0x18005f180`
- `0x18005fa30`
- `0x1800613f0`
- `0x180061580`
- `0x180061800`
- `0x180068008`
- `0x18006834c`
- `0x18006891c`
- `0x180068f40`
- `0x1800690ac`
- `0x180069a30`
- `0x180069f80`
- `0x18006a67c`
- `0x18006ad64`
- `0x18006b5b4`
- `0x18006e0d0`
- `0x18006e1bc`
- `0x18006f6b0`
- `0x180070380`
- `0x180073c20`
- `0x1800758a0`
- `0x180075b60`
- `0x1800792d4`

## callees

- `0x1800037f0`
- `0x18000dd00`
- `0x18000e0e0`
- `0x1800409c4`
- `0x1800562f0`
- `0x180070260`
- `0x180075998`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e38f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e162`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e162`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e3b4`
- `ntdll!RtlDeleteCriticalSection` at `0x18000e171`
- `ntdll!RtlDeleteCriticalSection` at `0x18000e171`
- `ntdll!RtlEnterCriticalSection` at `0x18000e103`
- `ntdll!RtlEnterCriticalSection` at `0x18000e14b`
- `ntdll!RtlEnterCriticalSection` at `0x18000e103`
- `ntdll!RtlEnterCriticalSection` at `0x18000e14b`
- `netutils!NetApiBufferFree` at `0x18000e33b`
- `netutils!NetApiBufferFree` at `0x18000e35a`
- `netutils!NetApiBufferFree` at `0x18000e379`
- `netutils!NetApiBufferFree` at `0x18000e33b`
- `netutils!NetApiBufferFree` at `0x18000e35a`
- `netutils!NetApiBufferFree` at `0x18000e379`

## string_xrefs

- `0x18000e121`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18000e219`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`

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
      0x49Bu,
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
            0x4EDu,
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
0x18000e0e0  mov     [rsp+arg_8], rbx
0x18000e0e5  mov     [rsp+arg_10], rbp
0x18000e0ea  push    rsi
0x18000e0eb  push    rdi
0x18000e0ec  push    r14
0x18000e0ee  sub     rsp, 30h
0x18000e0f2  mov     rbp, [rcx+110h]
0x18000e0f9  mov     rdi, rcx
0x18000e0fc  lea     rcx, [rbp+190h]; CriticalSection
0x18000e103  call    cs:__imp_RtlEnterCriticalSection
0x18000e10a  nop     dword ptr [rax+rax+00h]
0x18000e10f  xor     r14d, r14d
0x18000e112  cmp     [rdi+148h], r14d
0x18000e119  ja      short loc_18000E134
0x18000e11b  mov     r8d, 49Bh; unsigned int
0x18000e121  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000e128  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18000e12f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000e134  add     dword ptr [rdi+148h], 0FFFFFFFFh
0x18000e13b  jnz     loc_18000E39B
0x18000e141  lea     rbx, [rdi+158h]
0x18000e148  mov     rcx, rbx; CriticalSection
0x18000e14b  call    cs:__imp_RtlEnterCriticalSection
0x18000e152  nop     dword ptr [rax+rax+00h]
0x18000e157  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18000e15a  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x18000e15f  mov     rcx, rbx; CriticalSection
0x18000e162  call    cs:__imp_RtlLeaveCriticalSection
0x18000e169  nop     dword ptr [rax+rax+00h]
0x18000e16e  mov     rcx, rbx; CriticalSection
0x18000e171  call    cs:__imp_RtlDeleteCriticalSection
0x18000e178  nop     dword ptr [rax+rax+00h]
0x18000e17d  mov     rcx, [rdi+1A0h]; hObject
0x18000e184  test    rcx, rcx
0x18000e187  jz      short loc_18000E195
0x18000e189  call    cs:__imp_CloseHandle
0x18000e190  nop     dword ptr [rax+rax+00h]
0x18000e195  mov     rcx, [rdi+150h]; hObject
0x18000e19c  test    rcx, rcx
0x18000e19f  jz      short loc_18000E1AD
0x18000e1a1  call    cs:__imp_CloseHandle
0x18000e1a8  nop     dword ptr [rax+rax+00h]
0x18000e1ad  mov     rcx, [rdi+298h]; hObject
0x18000e1b4  test    rcx, rcx
0x18000e1b7  jz      short loc_18000E1C5
0x18000e1b9  call    cs:__imp_CloseHandle
0x18000e1c0  nop     dword ptr [rax+rax+00h]
0x18000e1c5  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r14d; ulong NlGlobalMaxConcurrentApi
0x18000e1cc  mov     ebx, r14d
0x18000e1cf  jbe     loc_18000E275
0x18000e1d5  mov     eax, ebx
0x18000e1d7  imul    rsi, rax, 230h
0x18000e1de  mov     rcx, [rsi+rdi+2B8h]; hObject
0x18000e1e6  test    rcx, rcx
0x18000e1e9  jz      short loc_18000E1F7
0x18000e1eb  call    cs:__imp_CloseHandle
0x18000e1f2  nop     dword ptr [rax+rax+00h]
0x18000e1f7  test    byte ptr [rsi+rdi+2C0h], 1
0x18000e1ff  jz      short loc_18000E267
0x18000e201  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18000e207  mov     rdx, [rdi+1F8h]
0x18000e20e  test    rdx, rdx
0x18000e211  jnz     short loc_18000E233
0x18000e213  mov     r8d, 4EDh; unsigned int
0x18000e219  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000e220  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18000e227  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000e22c  mov     rdx, [rdi+1F8h]
0x18000e233  mov     eax, [rsi+rdi+2C0h]
0x18000e23a  lea     r8, aNlfreeclientse; "NlFreeClientSession"
0x18000e241  and     al, 2
0x18000e243  mov     r9d, ebx
0x18000e246  neg     al
0x18000e248  mov     rax, [rsi+rdi+2C8h]
0x18000e250  sbb     ecx, ecx
0x18000e252  neg     ecx
0x18000e254  inc     ecx
0x18000e256  mov     [rsp+48h+var_20], ecx
0x18000e25a  mov     rcx, rdi
0x18000e25d  mov     [rsp+48h+var_28], rax
0x18000e262  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18000e267  inc     ebx
0x18000e269  cmp     ebx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x18000e26f  jb      loc_18000E1D5
0x18000e275  lea     rbx, [rdi+1D0h]
0x18000e27c  cmp     [rbx+8], r14
0x18000e280  jnz     short loc_18000E287
0x18000e282  cmp     [rbx], r14
0x18000e285  jz      short loc_18000E299
0x18000e287  mov     rcx, rbx; phCredential
0x18000e28a  call    FreeCredentialsHandle
0x18000e28f  mov     [rdi+1D8h], r14
0x18000e296  mov     [rbx], r14
0x18000e299  mov     rcx, [rdi+1C8h]
0x18000e2a0  test    rcx, rcx
0x18000e2a3  jz      short loc_18000E2B1
0x18000e2a5  call    NetpMemoryFree
0x18000e2aa  mov     [rdi+1C8h], r14
0x18000e2b1  mov     rcx, [rdi+108h]; hMem
0x18000e2b8  test    rcx, rcx
0x18000e2bb  jz      short loc_18000E2D0
0x18000e2bd  call    cs:__imp_LocalFree
0x18000e2c4  nop     dword ptr [rax+rax+00h]
0x18000e2c9  mov     [rdi+108h], r14
0x18000e2d0  lea     rcx, [rdi+70h]; struct _UNICODE_STRING *
0x18000e2d4  cmp     [rcx+8], r14
0x18000e2d8  jz      short loc_18000E2DF
0x18000e2da  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18000e2df  lea     rcx, [rdi+98h]; struct _UNICODE_STRING *
0x18000e2e6  mov     [rdi+90h], r14d
0x18000e2ed  mov     [rdi+80h], r14b
0x18000e2f4  cmp     [rcx+8], r14
0x18000e2f8  jz      short loc_18000E2FF
0x18000e2fa  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18000e2ff  mov     rcx, [rdi+0A8h]
0x18000e306  test    rcx, rcx
0x18000e309  jz      short loc_18000E317
0x18000e30b  call    NetpMemoryFree
0x18000e310  mov     [rdi+0A8h], r14
0x18000e317  mov     rcx, [rdi+100h]
0x18000e31e  test    rcx, rcx
0x18000e321  jz      short loc_18000E32F
0x18000e323  call    NetpMemoryFree
0x18000e328  mov     [rdi+100h], r14
0x18000e32f  mov     rcx, [rdi+1F8h]; Buffer
0x18000e336  test    rcx, rcx
0x18000e339  jz      short loc_18000E34E
0x18000e33b  call    cs:__imp_NetApiBufferFree
0x18000e342  nop     dword ptr [rax+rax+00h]
0x18000e347  mov     [rdi+1F8h], r14
0x18000e34e  mov     rcx, [rdi+0C8h]; Buffer
0x18000e355  test    rcx, rcx
0x18000e358  jz      short loc_18000E36D
0x18000e35a  call    cs:__imp_NetApiBufferFree
0x18000e361  nop     dword ptr [rax+rax+00h]
0x18000e366  mov     [rdi+0C8h], r14
0x18000e36d  mov     rcx, [rdi+290h]; Buffer
0x18000e374  test    rcx, rcx
0x18000e377  jz      short loc_18000E38C
0x18000e379  call    cs:__imp_NetApiBufferFree
0x18000e380  nop     dword ptr [rax+rax+00h]
0x18000e385  mov     [rdi+290h], r14
0x18000e38c  mov     rcx, rdi; hMem
0x18000e38f  call    cs:__imp_LocalFree
0x18000e396  nop     dword ptr [rax+rax+00h]
0x18000e39b  lea     rcx, [rbp+190h]
0x18000e3a2  mov     rbx, [rsp+48h+arg_8]
0x18000e3a7  mov     rbp, [rsp+48h+arg_10]
0x18000e3ac  add     rsp, 30h
0x18000e3b0  pop     r14
0x18000e3b2  pop     rdi
0x18000e3b3  pop     rsi
0x18000e3b4  jmp     cs:__imp_RtlLeaveCriticalSection
```
