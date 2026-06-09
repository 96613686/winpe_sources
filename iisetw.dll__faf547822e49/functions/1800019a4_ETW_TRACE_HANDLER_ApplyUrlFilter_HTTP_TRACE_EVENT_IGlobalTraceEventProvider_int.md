# ETW_TRACE_HANDLER::ApplyUrlFilter(HTTP_TRACE_EVENT *,IGlobalTraceEventProvider *,int *)

- ea: `0x1800019a4`
- end: `0x180001c8a`
- name: `?ApplyUrlFilter@ETW_TRACE_HANDLER@@SAJPEAUHTTP_TRACE_EVENT@@PEAVIGlobalTraceEventProvider@@PEAH@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct HTTP_TRACE_EVENT *, struct IGlobalTraceEventProvider *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800026bc`

## callees

- `0x180001008`
- `0x1800019a4`
- `0x180001c90`
- `0x180002428`
- `0x1800030f0`
- `0x180003406`
- `0x180003430`
- `0x180004010`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001b26`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001b26`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180001a98`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180001a98`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001a02`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001a02`
- `iisutil!PuDbgPrint` at `0x180001ada`
- `iisutil!PuDbgPrint` at `0x180001ada`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001bb9`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001bb9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c5c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c5c`

## string_xrefs

- `0x180001ac1`: `servercommon\inetsrv\iis\iisrearc\iis70\etw\etw_trace_handler.cxx`
- `0x180001ac8`: `Error copying the URL.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall ETW_TRACE_HANDLER::ApplyUrlFilter(
        struct HTTP_TRACE_EVENT *a1,
        struct IGlobalTraceEventProvider *a2,
        int *a3)
{
  __int64 v6; // rax
  int v7; // edi
  __int64 v8; // rdx
  LPCGUID pAreaGuid; // rax
  int v10; // eax
  __int64 v11; // rax
  unsigned int v12; // eax
  int Key; // eax
  TRACE_URLS_LIST *v14; // rbx
  __int64 v15; // rax
  unsigned int v16; // esi
  __int64 v17; // rax
  struct IHttpContext *v19; // [rsp+30h] [rbp-D0h] BYREF
  TRACE_URLS_LIST *v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp-88h]
  unsigned __int16 v24[512]; // [rsp+90h] [rbp-70h] BYREF

  v19 = 0;
  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v22, v24, 0x200u);
  (*(void (__fastcall **)(struct IGlobalTraceEventProvider *, struct IHttpContext **))(*(_QWORD *)a2 + 24LL))(a2, &v19);
  if ( !v19 )
    goto LABEL_23;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v19 + 24LL))(v19);
  v7 = 1;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( a1->dwEvent != 1
    || (pAreaGuid = a1->pAreaGuid) == 0
    || *(_QWORD *)&pAreaGuid->Data1 != *(_QWORD *)&`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid.Data1
    || *(_QWORD *)pAreaGuid->Data4 != *(_QWORD *)`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid.Data4 )
  {
    *a3 = 1;
    goto LABEL_23;
  }
  v10 = STRU::Copy((STRU *)v22, *(const unsigned __int16 **)(v8 + 88), *(unsigned __int16 *)(v8 + 68) >> 1);
  if ( v10 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\etw\\etw_trace_handler.cxx",
        904,
        "ETW_TRACE_HANDLER::ApplyUrlFilter",
        "Error copying the URL.  hr = %x\n",
        v10);
    goto LABEL_23;
  }
  v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v19 + 24LL))(v19);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 176LL))(v11);
  v20 = 0;
  Key = CLKRHashTable::FindKey((char *)ETW_TRACE_HANDLER::sm_pHttpTracingTable + 8, v12, &v20);
  if ( Key )
  {
    if ( Key != 2 )
      goto LABEL_23;
    v14 = (TRACE_URLS_LIST *)operator new(0x18u);
    if ( !v14 )
      goto LABEL_23;
    v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v19 + 24LL))(v19);
    *((_DWORD *)v14 + 5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 176LL))(v15);
    *((_DWORD *)v14 + 4) = 1;
    *((_QWORD *)v14 + 1) = v14;
    *(_QWORD *)v14 = v14;
    if ( (int)TRACE_URLS_LIST::BuildList(v14, v19) < 0 )
    {
LABEL_14:
      TRACE_URLS_LIST::Dereference(v14);
      goto LABEL_23;
    }
    CLKRHashTable::InsertRecord((char *)ETW_TRACE_HANDLER::sm_pHttpTracingTable + 8, v14, 0);
  }
  else
  {
    v14 = v20;
  }
  if ( !(unsigned int)TRACE_URLS_LIST::ShouldTraceUrl(v14, v23) )
  {
    v16 = 0;
    v21[2] = 0;
    v21[1] = 0;
    if ( off_180007020 )
    {
      do
      {
        v21[0] = (&off_180007020)[2 * v16];
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v19 + 272LL))(v19);
        (*(void (__fastcall **)(__int64, void *, _QWORD *, __int64))(*(_QWORD *)v17 + 8LL))(
          v17,
          s_pModuleContext,
          v21,
          1);
        ++v16;
      }
      while ( (&off_180007020)[2 * v16] );
    }
    v7 = 0;
  }
  *a3 = v7;
  if ( v14 )
    goto LABEL_14;
LABEL_23:
  STRU::~STRU((STRU *)v22);
  return 0;
}

```

## disassembly

```asm
0x1800019a4  mov     [rsp-8+arg_0], rbx
0x1800019a9  push    rbp
0x1800019aa  push    rsi
0x1800019ab  push    rdi
0x1800019ac  push    r12
0x1800019ae  push    r14
0x1800019b0  lea     rbp, [rsp-3A0h]
0x1800019b8  sub     rsp, 4A0h
0x1800019bf  mov     rax, cs:__security_cookie
0x1800019c6  xor     rax, rsp
0x1800019c9  mov     [rbp+3C0h+var_30], rax
0x1800019d0  mov     r14, r8
0x1800019d3  mov     [rsp+4C0h+var_490], 0
0x1800019dc  mov     rbx, rdx
0x1800019df  mov     rsi, rcx
0x1800019e2  xor     edx, edx; Val
0x1800019e4  lea     rcx, [rbp+3C0h+var_430]; void *
0x1800019e8  mov     r8d, 400h; Size
0x1800019ee  call    memset_0
0x1800019f3  mov     r8d, 200h
0x1800019f9  lea     rdx, [rbp+3C0h+var_430]
0x1800019fd  lea     rcx, [rsp+4C0h+var_468]
0x180001a02  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001a08  mov     rax, [rbx]
0x180001a0b  lea     rdx, [rsp+4C0h+var_490]
0x180001a10  mov     rcx, rbx
0x180001a13  mov     rax, [rax+18h]
0x180001a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1c  mov     rcx, [rsp+4C0h+var_490]
0x180001a21  test    rcx, rcx
0x180001a24  jz      loc_180001C57
0x180001a2a  mov     rax, [rcx]
0x180001a2d  mov     rax, [rax+18h]
0x180001a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a36  mov     rdx, rax
0x180001a39  mov     rcx, [rax]
0x180001a3c  mov     rax, [rcx+8]
0x180001a40  mov     rcx, rdx
0x180001a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a48  mov     edi, 1
0x180001a4d  mov     rdx, rax
0x180001a50  cmp     [rsi+18h], edi
0x180001a53  jnz     loc_180001C54
0x180001a59  mov     rax, [rsi+10h]
0x180001a5d  test    rax, rax
0x180001a60  jz      loc_180001C54
0x180001a66  mov     rcx, [rax]
0x180001a69  cmp     rcx, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B.Data1; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x180001a70  jnz     loc_180001C54
0x180001a76  mov     rax, [rax+8]
0x180001a7a  cmp     rax, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B.Data4; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x180001a81  jnz     loc_180001C54
0x180001a87  movzx   r8d, word ptr [rdx+44h]
0x180001a8c  lea     rcx, [rsp+4C0h+var_468]
0x180001a91  mov     rdx, [rdx+58h]
0x180001a95  shr     r8d, 1
0x180001a98  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180001a9e  test    eax, eax
0x180001aa0  jns     short loc_180001AE5
0x180001aa2  test    cs:g_dwDebugFlags, 3
0x180001aa9  jz      loc_180001C57
0x180001aaf  mov     rcx, cs:g_pDebug
0x180001ab6  lea     r9, aEtwTraceHandle_0; "ETW_TRACE_HANDLER::ApplyUrlFilter"
0x180001abd  mov     [rsp+4C0h+var_498], eax
0x180001ac1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001ac8  lea     rax, aErrorCopyingTh; "Error copying the URL.  hr = %x\n"
0x180001acf  mov     r8d, 388h
0x180001ad5  mov     [rsp+4C0h+var_4A0], rax
0x180001ada  call    cs:__imp_PuDbgPrint
0x180001ae0  jmp     loc_180001C57
0x180001ae5  mov     rcx, [rsp+4C0h+var_490]
0x180001aea  mov     rax, [rcx]
0x180001aed  mov     rax, [rax+18h]
0x180001af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af6  mov     rdx, rax
0x180001af9  mov     rcx, [rax]
0x180001afc  mov     rax, [rcx+0B0h]
0x180001b03  mov     rcx, rdx
0x180001b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b0b  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x180001b12  lea     r8, [rsp+4C0h+var_488]
0x180001b17  add     rcx, 8
0x180001b1b  mov     edx, eax
0x180001b1d  mov     [rsp+4C0h+var_488], 0
0x180001b26  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180001b2c  test    eax, eax
0x180001b2e  jnz     short loc_180001B3A
0x180001b30  mov     rbx, [rsp+4C0h+var_488]
0x180001b35  jmp     loc_180001BBF
0x180001b3a  cmp     eax, 2
0x180001b3d  jnz     loc_180001C57
0x180001b43  lea     ecx, [rax+16h]; Size
0x180001b46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b4b  mov     rbx, rax
0x180001b4e  test    rax, rax
0x180001b51  jz      loc_180001C57
0x180001b57  mov     rcx, [rsp+4C0h+var_490]
0x180001b5c  mov     rax, [rcx]
0x180001b5f  mov     rax, [rax+18h]
0x180001b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b68  mov     rdx, rax
0x180001b6b  mov     rcx, [rax]
0x180001b6e  mov     rax, [rcx+0B0h]
0x180001b75  mov     rcx, rdx
0x180001b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7d  mov     [rbx+14h], eax
0x180001b80  mov     rcx, rbx; this
0x180001b83  mov     [rbx+10h], edi
0x180001b86  mov     [rbx+8], rbx
0x180001b8a  mov     [rbx], rbx
0x180001b8d  mov     rdx, [rsp+4C0h+var_490]; struct IHttpContext *
0x180001b92  call    ?BuildList@TRACE_URLS_LIST@@QEAAJPEAVIHttpContext@@@Z; TRACE_URLS_LIST::BuildList(IHttpContext *)
0x180001b97  test    eax, eax
0x180001b99  jns     short loc_180001BA8
0x180001b9b  mov     rcx, rbx; this
0x180001b9e  call    ?Dereference@TRACE_URLS_LIST@@QEAAXXZ; TRACE_URLS_LIST::Dereference(void)
0x180001ba3  jmp     loc_180001C57
0x180001ba8  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x180001baf  xor     r8d, r8d
0x180001bb2  add     rcx, 8
0x180001bb6  mov     rdx, rbx
0x180001bb9  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180001bbf  mov     rdx, [rsp+4C0h+var_448]; unsigned __int16 *
0x180001bc4  mov     rcx, rbx; this
0x180001bc7  call    ?ShouldTraceUrl@TRACE_URLS_LIST@@QEAAHPEBG@Z; TRACE_URLS_LIST::ShouldTraceUrl(ushort const *)
0x180001bcc  test    eax, eax
0x180001bce  jnz     short loc_180001C47
0x180001bd0  xor     esi, esi
0x180001bd2  mov     [rsp+4C0h+var_470], 0
0x180001bdb  cmp     cs:off_180007020, rsi
0x180001be2  mov     [rsp+4C0h+var_478], 0
0x180001beb  jz      short loc_180001C45
0x180001bed  lea     r12, off_180007020
0x180001bf4  mov     rcx, [rsp+4C0h+var_490]
0x180001bf9  mov     eax, esi
0x180001bfb  add     rax, rax
0x180001bfe  mov     rax, [r12+rax*8]
0x180001c02  mov     [rsp+4C0h+var_480], rax
0x180001c07  mov     rax, [rcx]
0x180001c0a  mov     rax, [rax+110h]
0x180001c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c16  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001c1d  lea     r8, [rsp+4C0h+var_480]
0x180001c22  mov     r10, rax
0x180001c25  mov     r9d, edi
0x180001c28  mov     rcx, [rax]
0x180001c2b  mov     rax, [rcx+8]
0x180001c2f  mov     rcx, r10
0x180001c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c37  add     esi, edi
0x180001c39  mov     eax, esi
0x180001c3b  add     rax, rax
0x180001c3e  cmp     qword ptr [r12+rax*8], 0
0x180001c43  jnz     short loc_180001BF4
0x180001c45  xor     edi, edi
0x180001c47  mov     [r14], edi
0x180001c4a  test    rbx, rbx
0x180001c4d  jz      short loc_180001C57
0x180001c4f  jmp     loc_180001B9B
0x180001c54  mov     [r14], edi
0x180001c57  lea     rcx, [rsp+4C0h+var_468]
0x180001c5c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001c62  xor     eax, eax
0x180001c64  mov     rcx, [rbp+3C0h+var_30]
0x180001c6b  xor     rcx, rsp; StackCookie
0x180001c6e  call    __security_check_cookie
0x180001c73  mov     rbx, [rsp+4C0h+arg_0]
0x180001c7b  add     rsp, 4A0h
0x180001c82  pop     r14
0x180001c84  pop     r12
0x180001c86  pop     rdi
0x180001c87  pop     rsi
0x180001c88  pop     rbp
0x180001c89  retn
```
