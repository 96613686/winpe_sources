# PROTOCOL::SetConfiguration(PROTOCOL_DATA_OBJECT *)

- ea: `0x18001b5e0`
- end: `0x18001b77c`
- name: `?SetConfiguration@PROTOCOL@@QEAAXPEAVPROTOCOL_DATA_OBJECT@@@Z`
- size: `412`
- prototype: `void __fastcall(PROTOCOL *__hidden this, struct PROTOCOL_DATA_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f920`

## callees

- `0x180005878`
- `0x18001b23c`
- `0x18001b5e0`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18001b664`
- `iisutil!PuDbgPrintError` at `0x18001b6e7`
- `iisutil!PuDbgPrintError` at `0x18001b744`
- `iisutil!PuDbgPrintError` at `0x18001b664`
- `iisutil!PuDbgPrintError` at `0x18001b6e7`
- `iisutil!PuDbgPrintError` at `0x18001b744`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b624`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b6a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b706`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b624`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b6a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b706`

## string_xrefs

- `0x18001b65d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol.cxx`
- `0x18001b6dc`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol.cxx`
- `0x18001b739`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol.cxx`
- `0x18001b640`: `Failed to copy in the identity\n`
- `0x18001b64c`: `PROTOCOL::SetConfiguration`
- `0x18001b6ce`: `PROTOCOL::SetConfiguration`
- `0x18001b72b`: `PROTOCOL::SetConfiguration`
- `0x18001b6bc`: `Failed to copy in the protocol manager dll\n`
- `0x18001b719`: `Failed to copy in the protocol manager dll entry point\n`

## pseudocode

```c
void __fastcall PROTOCOL::SetConfiguration(PROTOCOL *this, struct PROTOCOL_DATA_OBJECT *a2)
{
  int v4; // eax
  signed int v5; // esi
  int v6; // eax
  int v7; // eax
  unsigned __int16 *v8; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
  {
    *((_DWORD *)this + 86) = 0;
LABEL_23:
    (*(void (__fastcall **)(PROTOCOL *))(*(_QWORD *)this + 8LL))(this);
    PROTOCOL::CheckIfProtocolShouldExistAndTerminateIfNot(this);
    return;
  }
  v4 = 0;
  if ( !*((_DWORD *)this + 86) )
  {
    *((_DWORD *)this + 86) = 1;
    v4 = 1;
  }
  if ( (*((_BYTE *)a2 + 288) & 1) != 0 )
  {
    v5 = STRU::Copy((PROTOCOL *)((char *)this + 176), *((const unsigned __int16 **)a2 + 17));
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol.cxx",
          238,
          "PROTOCOL::SetConfiguration",
          v5,
          "Failed to copy in the identity\n");
      v8 = (unsigned __int16 *)*((_QWORD *)a2 + 10);
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC0001433, 1u, (const unsigned __int16 **const)&v8, v5);
    }
    v4 = 1;
  }
  if ( (*((_BYTE *)a2 + 288) & 2) != 0 )
  {
    v6 = STRU::Copy((PROTOCOL *)((char *)this + 232), *((const unsigned __int16 **)a2 + 24));
    if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol.cxx",
        262,
        "PROTOCOL::SetConfiguration",
        v6,
        "Failed to copy in the protocol manager dll\n");
    v4 = 1;
  }
  if ( (*((_BYTE *)a2 + 288) & 4) != 0 )
  {
    v7 = STRU::Copy((PROTOCOL *)((char *)this + 288), *((const unsigned __int16 **)a2 + 31));
    if ( v7 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol.cxx",
        278,
        "PROTOCOL::SetConfiguration",
        v7,
        "Failed to copy in the protocol manager dll entry point\n");
    v4 = 1;
  }
  if ( v4 )
    goto LABEL_23;
}

```

## disassembly

```asm
0x18001b5e0  push    rbx
0x18001b5e2  push    rbp
0x18001b5e3  push    rsi
0x18001b5e4  push    rdi
0x18001b5e5  sub     rsp, 38h
0x18001b5e9  mov     rdi, rdx
0x18001b5ec  mov     rbx, rcx
0x18001b5ef  test    rdx, rdx
0x18001b5f2  jz      loc_18001B752
0x18001b5f8  xor     eax, eax
0x18001b5fa  lea     ebp, [rax+1]
0x18001b5fd  cmp     [rcx+158h], eax
0x18001b603  jnz     short loc_18001B60D
0x18001b605  mov     [rcx+158h], ebp
0x18001b60b  mov     eax, ebp
0x18001b60d  test    [rdx+120h], bpl
0x18001b614  jz      short loc_18001B692
0x18001b616  mov     rdx, [rdx+88h]
0x18001b61d  add     rcx, 0B0h
0x18001b624  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b62a  mov     esi, eax
0x18001b62c  test    eax, eax
0x18001b62e  jns     short loc_18001B690
0x18001b630  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001b637  jz      short loc_18001B66A
0x18001b639  mov     rcx, cs:g_pDebug
0x18001b640  lea     rax, aFailedToCopyIn_0; "Failed to copy in the identity\n"
0x18001b647  mov     [rsp+58h+var_30], rax
0x18001b64c  lea     r9, aProtocolSetcon; "PROTOCOL::SetConfiguration"
0x18001b653  mov     r8d, 0EEh
0x18001b659  mov     [rsp+58h+var_38], esi
0x18001b65d  lea     rdx, aServercommonIn_54; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001b664  call    cs:__imp_PuDbgPrintError
0x18001b66a  mov     rax, [rdi+50h]
0x18001b66e  lea     r9, [rsp+58h+arg_8]; unsigned __int16 **
0x18001b673  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001b67a  mov     r8d, ebp; unsigned __int16
0x18001b67d  mov     edx, 0C0001433h; unsigned int
0x18001b682  mov     [rsp+58h+arg_8], rax
0x18001b687  mov     [rsp+58h+var_38], esi; unsigned int
0x18001b68b  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001b690  mov     eax, ebp
0x18001b692  test    byte ptr [rdi+120h], 2
0x18001b699  jz      short loc_18001B6EF
0x18001b69b  mov     rdx, [rdi+0C0h]
0x18001b6a2  lea     rcx, [rbx+0E8h]
0x18001b6a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b6af  test    eax, eax
0x18001b6b1  jns     short loc_18001B6ED
0x18001b6b3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001b6ba  jz      short loc_18001B6ED
0x18001b6bc  lea     rcx, aFailedToCopyIn_3; "Failed to copy in the protocol manager "...
0x18001b6c3  mov     r8d, 106h
0x18001b6c9  mov     [rsp+58h+var_30], rcx
0x18001b6ce  lea     r9, aProtocolSetcon; "PROTOCOL::SetConfiguration"
0x18001b6d5  mov     rcx, cs:g_pDebug
0x18001b6dc  lea     rdx, aServercommonIn_54; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001b6e3  mov     [rsp+58h+var_38], eax
0x18001b6e7  call    cs:__imp_PuDbgPrintError
0x18001b6ed  mov     eax, ebp
0x18001b6ef  test    byte ptr [rdi+120h], 4
0x18001b6f6  jz      short loc_18001B74C
0x18001b6f8  mov     rdx, [rdi+0F8h]
0x18001b6ff  lea     rcx, [rbx+120h]
0x18001b706  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b70c  test    eax, eax
0x18001b70e  jns     short loc_18001B74A
0x18001b710  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001b717  jz      short loc_18001B74A
0x18001b719  lea     rcx, aFailedToCopyIn_1; "Failed to copy in the protocol manager "...
0x18001b720  mov     r8d, 116h
0x18001b726  mov     [rsp+58h+var_30], rcx
0x18001b72b  lea     r9, aProtocolSetcon; "PROTOCOL::SetConfiguration"
0x18001b732  mov     rcx, cs:g_pDebug
0x18001b739  lea     rdx, aServercommonIn_54; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001b740  mov     [rsp+58h+var_38], eax
0x18001b744  call    cs:__imp_PuDbgPrintError
0x18001b74a  mov     eax, ebp
0x18001b74c  test    eax, eax
0x18001b74e  jz      short loc_18001B773
0x18001b750  jmp     short loc_18001B75C
0x18001b752  mov     dword ptr [rcx+158h], 0
0x18001b75c  mov     rax, [rbx]
0x18001b75f  mov     rcx, rbx
0x18001b762  mov     rax, [rax+8]
0x18001b766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b76b  mov     rcx, rbx; this
0x18001b76e  call    ?CheckIfProtocolShouldExistAndTerminateIfNot@PROTOCOL@@QEAAXXZ; PROTOCOL::CheckIfProtocolShouldExistAndTerminateIfNot(void)
0x18001b773  add     rsp, 38h
0x18001b777  pop     rdi
0x18001b778  pop     rsi
0x18001b779  pop     rbp
0x18001b77a  pop     rbx
0x18001b77b  retn
```
