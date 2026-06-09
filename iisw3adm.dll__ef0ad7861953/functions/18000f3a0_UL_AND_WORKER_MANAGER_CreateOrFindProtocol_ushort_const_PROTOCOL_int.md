# UL_AND_WORKER_MANAGER::CreateOrFindProtocol(ushort const *,PROTOCOL * *,int *)

- ea: `0x18000f3a0`
- end: `0x18000f602`
- name: `?CreateOrFindProtocol@UL_AND_WORKER_MANAGER@@QEAAJPEBGPEAPEAVPROTOCOL@@PEAH@Z`
- size: `610`
- prototype: `__int64 __fastcall(UL_AND_WORKER_MANAGER *__hidden this, const unsigned __int16 *, struct PROTOCOL **, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000574c`
- `0x18000f920`
- `0x180015e44`

## callees

- `0x180001234`
- `0x18000f3a0`
- `0x18001b02c`
- `0x18001cd3c`
- `0x180062010`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f3ee`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f3ee`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000f57f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000f57f`
- `iisutil!PuDbgPrintError` at `0x18000f433`
- `iisutil!PuDbgPrintError` at `0x18000f553`
- `iisutil!PuDbgPrintError` at `0x18000f5c1`
- `iisutil!PuDbgPrintError` at `0x18000f433`
- `iisutil!PuDbgPrintError` at `0x18000f553`
- `iisutil!PuDbgPrintError` at `0x18000f5c1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000f4b3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000f4b3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f513`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f513`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18000f3cc`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18000f3cc`

## string_xrefs

- `0x18000f42c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f5ba`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f40b`: `Finding protocol failed and it wasn't just not there\n`
- `0x18000f417`: `UL_AND_WORKER_MANAGER::CreateOrFindProtocol`
- `0x18000f5a5`: `UL_AND_WORKER_MANAGER::CreateOrFindProtocol`
- `0x18000f599`: `Inserting protocol into hashtable failed\n`
- `0x18000f52f`: `Failed to copy in the protocol id\n`
- `0x18000f53b`: `PROTOCOL::Initialize`
- `0x18000f54c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol.cxx`

## pseudocode

```c
__int64 __fastcall UL_AND_WORKER_MANAGER::CreateOrFindProtocol(
        UL_AND_WORKER_MANAGER *this,
        const unsigned __int16 *a2,
        struct PROTOCOL **a3,
        int *a4)
{
  bool v8; // al
  bool v9; // bp
  int Key; // eax
  int v11; // edi
  HTTP_PROTOCOL *v12; // rbx
  HTTP_PROTOCOL *v13; // rax
  PROTOCOL *v14; // rax
  HTTP_PROTOCOL *v16; // [rsp+60h] [rbp+8h] BYREF

  v8 = IsStringEqualOrdinalIgnoreCase(a2, L"HTTP");
  v16 = 0;
  v9 = v8;
  Key = CLKRHashTable::FindKey((char *)this + 256, a2, &v16);
  if ( (Key & 0xFFFFFFFD) != 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        1254,
        "UL_AND_WORKER_MANAGER::CreateOrFindProtocol",
        -2147467259,
        "Finding protocol failed and it wasn't just not there\n");
    return (unsigned int)-2147467259;
  }
  v12 = v16;
  v11 = 0;
  if ( !Key )
  {
    if ( a4 )
      *a4 = 0;
    goto LABEL_27;
  }
  if ( Key != 2 )
  {
LABEL_27:
    *a3 = v12;
    return (unsigned int)v11;
  }
  if ( v9 )
  {
    v13 = (HTTP_PROTOCOL *)operator new(0xAAD8u);
    if ( v13 )
    {
      v12 = HTTP_PROTOCOL::HTTP_PROTOCOL(v13);
      goto LABEL_15;
    }
  }
  else
  {
    v14 = (PROTOCOL *)operator new(0x1D0u);
    v12 = v14;
    if ( v14 )
    {
      PROTOCOL::PROTOCOL(v14);
      *(_QWORD *)v12 = &LA_PROTOCOL::`vftable';
      STRU::STRU((HTTP_PROTOCOL *)((char *)v12 + 384));
      *((_QWORD *)v12 + 44) = 0;
      *((_QWORD *)v12 + 47) = (char *)v12 + 368;
      *((_QWORD *)v12 + 46) = (char *)v12 + 368;
      *((_QWORD *)v12 + 55) = 0;
      *((_DWORD *)v12 + 90) = 0;
      *((_DWORD *)v12 + 91) = 1;
      *(_QWORD *)((char *)v12 + 452) = 0;
      *((_DWORD *)v12 + 112) = 0;
      goto LABEL_15;
    }
  }
  v12 = 0;
LABEL_15:
  if ( !v12 )
    return (unsigned int)-2147024882;
  *((_DWORD *)v12 + 4) = 2;
  v11 = STRU::Copy((HTTP_PROTOCOL *)((char *)v12 + 120), a2);
  if ( v11 >= 0 )
  {
    *((_DWORD *)v12 + 4) = 3;
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 256, v12, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          1314,
          "UL_AND_WORKER_MANAGER::CreateOrFindProtocol",
          -2147467259,
          "Inserting protocol into hashtable failed\n");
      (*(void (__fastcall **)(HTTP_PROTOCOL *))(*(_QWORD *)v12 + 16LL))(v12);
      return (unsigned int)-2147467259;
    }
    if ( a4 )
      *a4 = 1;
    goto LABEL_27;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol.cxx",
      162,
      "PROTOCOL::Initialize",
      v11,
      "Failed to copy in the protocol id\n");
  (*(void (__fastcall **)(HTTP_PROTOCOL *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f3a0  mov     [rsp+arg_8], rbx
0x18000f3a5  mov     [rsp+arg_10], rbp
0x18000f3aa  push    rsi
0x18000f3ab  push    rdi
0x18000f3ac  push    r12
0x18000f3ae  push    r14
0x18000f3b0  push    r15
0x18000f3b2  sub     rsp, 30h
0x18000f3b6  mov     r14, rdx
0x18000f3b9  mov     r12, rcx
0x18000f3bc  mov     rcx, r14
0x18000f3bf  lea     rdx, aHttp_0; "HTTP"
0x18000f3c6  mov     rsi, r9
0x18000f3c9  mov     r15, r8
0x18000f3cc  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18000f3d2  lea     r8, [rsp+58h+arg_0]
0x18000f3d7  mov     [rsp+58h+arg_0], 0
0x18000f3e0  mov     rdx, r14
0x18000f3e3  lea     rcx, [r12+100h]
0x18000f3eb  mov     bpl, al
0x18000f3ee  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000f3f4  test    eax, 0FFFFFFFDh
0x18000f3f9  jz      short loc_18000F443
0x18000f3fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f402  jz      short loc_18000F439
0x18000f404  mov     rcx, cs:g_pDebug
0x18000f40b  lea     rax, aFindingProtoco; "Finding protocol failed and it wasn't j"...
0x18000f412  mov     [rsp+58h+var_30], rax
0x18000f417  lea     r9, aUlAndWorkerMan_4; "UL_AND_WORKER_MANAGER::CreateOrFindProt"...
0x18000f41e  mov     r8d, 4E6h
0x18000f424  mov     [rsp+58h+var_38], 80004005h
0x18000f42c  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f433  call    cs:__imp_PuDbgPrintError
0x18000f439  mov     edi, 80004005h
0x18000f43e  jmp     loc_18000F5E9
0x18000f443  mov     rbx, [rsp+58h+arg_0]
0x18000f448  xor     edi, edi
0x18000f44a  test    eax, eax
0x18000f44c  jnz     short loc_18000F45E
0x18000f44e  test    rsi, rsi
0x18000f451  jz      loc_18000F5E6
0x18000f457  mov     [rsi], edi
0x18000f459  jmp     loc_18000F5E6
0x18000f45e  cmp     eax, 2
0x18000f461  jnz     loc_18000F5E6
0x18000f467  test    bpl, bpl
0x18000f46a  jz      short loc_18000F488
0x18000f46c  mov     ecx, 0AAD8h; Size
0x18000f471  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f476  test    rax, rax
0x18000f479  jz      short loc_18000F4F4
0x18000f47b  mov     rcx, rax; this
0x18000f47e  call    ??0HTTP_PROTOCOL@@QEAA@XZ; HTTP_PROTOCOL::HTTP_PROTOCOL(void)
0x18000f483  mov     rbx, rax
0x18000f486  jmp     short loc_18000F4F6
0x18000f488  mov     ecx, 1D0h; Size
0x18000f48d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f492  mov     rbx, rax
0x18000f495  test    rax, rax
0x18000f498  jz      short loc_18000F4F4
0x18000f49a  mov     rcx, rax; this
0x18000f49d  call    ??0PROTOCOL@@QEAA@XZ; PROTOCOL::PROTOCOL(void)
0x18000f4a2  lea     rax, ??_7LA_PROTOCOL@@6B@; const LA_PROTOCOL::`vftable'
0x18000f4a9  lea     rcx, [rbx+180h]
0x18000f4b0  mov     [rbx], rax
0x18000f4b3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000f4b9  lea     rax, [rbx+170h]
0x18000f4c0  mov     [rbx+160h], rdi
0x18000f4c7  mov     [rax+8], rax
0x18000f4cb  mov     [rax], rax
0x18000f4ce  mov     [rbx+1B8h], rdi
0x18000f4d5  mov     [rbx+168h], edi
0x18000f4db  mov     dword ptr [rbx+16Ch], 1
0x18000f4e5  mov     [rbx+1C4h], rdi
0x18000f4ec  mov     [rbx+1C0h], edi
0x18000f4f2  jmp     short loc_18000F4F6
0x18000f4f4  xor     ebx, ebx
0x18000f4f6  test    rbx, rbx
0x18000f4f9  jnz     short loc_18000F505
0x18000f4fb  mov     edi, 8007000Eh
0x18000f500  jmp     loc_18000F5E9
0x18000f505  lea     rcx, [rbx+78h]
0x18000f509  mov     dword ptr [rbx+10h], 2
0x18000f510  mov     rdx, r14
0x18000f513  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f519  mov     edi, eax
0x18000f51b  test    eax, eax
0x18000f51d  jns     short loc_18000F56A
0x18000f51f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f526  jz      short loc_18000F559
0x18000f528  mov     rcx, cs:g_pDebug
0x18000f52f  lea     rax, aFailedToCopyIn; "Failed to copy in the protocol id\n"
0x18000f536  mov     [rsp+58h+var_30], rax
0x18000f53b  lea     r9, aProtocolInitia; "PROTOCOL::Initialize"
0x18000f542  mov     r8d, 0A2h
0x18000f548  mov     [rsp+58h+var_38], edi
0x18000f54c  lea     rdx, aServercommonIn_54; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f553  call    cs:__imp_PuDbgPrintError
0x18000f559  mov     rax, [rbx]
0x18000f55c  mov     rcx, rbx
0x18000f55f  mov     rax, [rax+10h]
0x18000f563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f568  jmp     short loc_18000F5E9
0x18000f56a  xor     r8d, r8d
0x18000f56d  mov     dword ptr [rbx+10h], 3
0x18000f574  mov     rdx, rbx
0x18000f577  lea     rcx, [r12+100h]
0x18000f57f  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000f585  test    eax, eax
0x18000f587  jz      short loc_18000F5DB
0x18000f589  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f590  jz      short loc_18000F5C7
0x18000f592  mov     rcx, cs:g_pDebug
0x18000f599  lea     rax, aInsertingProto; "Inserting protocol into hashtable faile"...
0x18000f5a0  mov     [rsp+58h+var_30], rax
0x18000f5a5  lea     r9, aUlAndWorkerMan_4; "UL_AND_WORKER_MANAGER::CreateOrFindProt"...
0x18000f5ac  mov     r8d, 522h
0x18000f5b2  mov     [rsp+58h+var_38], 80004005h
0x18000f5ba  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f5c1  call    cs:__imp_PuDbgPrintError
0x18000f5c7  mov     rax, [rbx]
0x18000f5ca  mov     rcx, rbx
0x18000f5cd  mov     rax, [rax+10h]
0x18000f5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d6  jmp     loc_18000F439
0x18000f5db  test    rsi, rsi
0x18000f5de  jz      short loc_18000F5E6
0x18000f5e0  mov     dword ptr [rsi], 1
0x18000f5e6  mov     [r15], rbx
0x18000f5e9  mov     rbx, [rsp+58h+arg_8]
0x18000f5ee  mov     eax, edi
0x18000f5f0  mov     rbp, [rsp+58h+arg_10]
0x18000f5f5  add     rsp, 30h
0x18000f5f9  pop     r15
0x18000f5fb  pop     r14
0x18000f5fd  pop     r12
0x18000f5ff  pop     rdi
0x18000f600  pop     rsi
0x18000f601  retn
```
