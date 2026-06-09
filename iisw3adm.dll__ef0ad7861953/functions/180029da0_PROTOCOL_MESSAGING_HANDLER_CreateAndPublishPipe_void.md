# PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe(void *)

- ea: `0x180029da0`
- end: `0x18002a01a`
- name: `?CreateAndPublishPipe@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAX@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct IPM_MESSAGE_PIPE **this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c2cc`

## callees

- `0x180029da0`
- `0x18002a020`
- `0x18002a214`
- `0x18002a58c`
- `0x18002b120`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029fe5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029fef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029fef`
- `iisutil!PuDbgPrintError` at `0x180029e56`
- `iisutil!PuDbgPrintError` at `0x180029ec8`
- `iisutil!PuDbgPrintError` at `0x180029e56`
- `iisutil!PuDbgPrintError` at `0x180029ec8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029df6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029df6`
- `iisutil!GenerateNameWithGUID` at `0x180029f05`
- `iisutil!GenerateNameWithGUID` at `0x180029f05`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x180029f2d`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x180029f2d`
- `iisutil!CreateSubkey` at `0x180029f99`
- `iisutil!CreateSubkey` at `0x180029f99`
- `iisutil!SetStringParameterValueInAnyService` at `0x180029fb8`
- `iisutil!SetStringParameterValueInAnyService` at `0x180029fb8`

## string_xrefs

- `0x180029e4b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x180029ec1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x180029e2b`: `Error creating registry security attribute\n`
- `0x180029e3f`: `PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe`
- `0x180029eb0`: `PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe`
- `0x180029ea4`: `Error creating pipe security attribute\n`
- `0x180029f7f`: `Could not get the protocols registry key name\n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe(struct IPM_MESSAGE_PIPE **this, void *a2)
{
  void *v3; // rdi
  PROTOCOL_MESSAGING_HANDLER *v5; // rcx
  int v6; // eax
  HLOCAL v7; // r15
  signed int PipeKeyName; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  struct _SECURITY_ATTRIBUTES *v11; // rax
  __int64 v12; // rcx
  int v13; // esi
  struct _SECURITY_ATTRIBUTES *v14; // rax
  __int64 v15; // rcx
  int NameWithGUID; // eax
  bool v17; // cc
  void *v19; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-49h] BYREF
  struct _SECURITY_ATTRIBUTES v22; // [rsp+48h] [rbp-41h] BYREF
  struct _SECURITY_ATTRIBUTES v23; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v24[32]; // [rsp+78h] [rbp-11h] BYREF
  const unsigned __int16 *v25; // [rsp+98h] [rbp+Fh]

  hMem = 0;
  v3 = 0;
  v19 = 0;
  memset(&v23, 0, sizeof(v23));
  memset(&v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v24);
  v20 = 0;
  PROTOCOL_MESSAGING_HANDLER::DeletePipeInfo((PROTOCOL_MESSAGING_HANDLER *)this);
  v6 = PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc(v5, a2, &hMem);
  v7 = hMem;
  PipeKeyName = v6;
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = "Error creating registry security attribute\n";
      v10 = 628;
      goto LABEL_4;
    }
    goto LABEL_31;
  }
  v11 = &v23;
  v12 = 24;
  do
  {
    LOBYTE(v11->nLength) = 0;
    v11 = (struct _SECURITY_ATTRIBUTES *)((char *)v11 + 1);
    --v12;
  }
  while ( v12 );
  v23.nLength = 24;
  v23.lpSecurityDescriptor = v7;
  v23.bInheritHandle = 0;
  PipeKeyName = PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc(0, a2, &v19);
  if ( PipeKeyName < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        646,
        "PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe",
        PipeKeyName,
        "Error creating pipe security attribute\n");
    v3 = v19;
    goto LABEL_31;
  }
  v13 = 0;
  v14 = &v22;
  v15 = 24;
  do
  {
    LOBYTE(v14->nLength) = 0;
    v14 = (struct _SECURITY_ATTRIBUTES *)((char *)v14 + 1);
    --v15;
  }
  while ( v15 );
  v22.nLength = 24;
  v3 = v19;
  v22.lpSecurityDescriptor = v19;
  v22.bInheritHandle = 0;
  while ( 1 )
  {
    NameWithGUID = GenerateNameWithGUID(L"\\\\.\\pipe\\wbhstipm", (struct STRU *)v24);
    PipeKeyName = NameWithGUID;
    if ( NameWithGUID )
    {
      if ( NameWithGUID <= 0 )
        goto LABEL_31;
      goto LABEL_30;
    }
    PipeKeyName = IPM_MESSAGE_PIPE::CreateIpmMessagePipe((struct IPM_MESSAGE_ACCEPTOR *)this, v25, 1, &v22, this + 4);
    if ( PipeKeyName != -2147024713 )
      break;
    if ( (unsigned int)++v13 >= 0xA )
      goto LABEL_19;
  }
  if ( PipeKeyName < 0 )
  {
LABEL_19:
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_31;
    v9 = "Creating message pipe failed\n";
    v10 = 690;
    goto LABEL_4;
  }
  PipeKeyName = PROTOCOL_MESSAGING_HANDLER::QueryPipeKeyName(
                  (PROTOCOL_MESSAGING_HANDLER *)this,
                  (const unsigned __int16 **)&v20);
  if ( PipeKeyName >= 0 )
  {
    NameWithGUID = CreateSubkey(v20, &v23);
    v17 = NameWithGUID <= 0;
    if ( !NameWithGUID )
    {
      NameWithGUID = SetStringParameterValueInAnyService(v20, L"Name", v25);
      v17 = NameWithGUID <= 0;
      if ( !NameWithGUID )
        goto LABEL_31;
    }
    if ( v17 )
    {
      PipeKeyName = NameWithGUID;
      goto LABEL_31;
    }
LABEL_30:
    PipeKeyName = (unsigned __int16)NameWithGUID | 0x80070000;
    goto LABEL_31;
  }
  if ( (g_dwDebugFlags & 0xF) == 0 )
    goto LABEL_31;
  v9 = "Could not get the protocols registry key name\n";
  v10 = 707;
LABEL_4:
  PuDbgPrintError(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
    v10,
    "PROTOCOL_MESSAGING_HANDLER::CreateAndPublishPipe",
    PipeKeyName,
    v9);
LABEL_31:
  if ( v7 )
    LocalFree(v7);
  if ( v3 )
    LocalFree(v3);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)PipeKeyName;
}

```

## disassembly

```asm
0x180029da0  mov     [rsp-8+arg_10], rbx
0x180029da5  push    rbp
0x180029da6  push    rsi
0x180029da7  push    rdi
0x180029da8  push    r14
0x180029daa  push    r15
0x180029dac  lea     rbp, [rsp-37h]
0x180029db1  sub     rsp, 0C0h
0x180029db8  mov     rax, cs:__security_cookie
0x180029dbf  xor     rax, rsp
0x180029dc2  mov     [rbp+57h+var_30], rax
0x180029dc6  xor     eax, eax
0x180029dc8  mov     [rbp+57h+hMem], 0
0x180029dd0  mov     r14, rcx
0x180029dd3  mov     [rbp+57h+var_70], rax
0x180029dd7  xorps   xmm0, xmm0
0x180029dda  mov     [rbp+57h+var_88], rax
0x180029dde  xorps   xmm1, xmm1
0x180029de1  lea     rcx, [rbp+57h+var_68]
0x180029de5  xor     edi, edi
0x180029de7  mov     rsi, rdx
0x180029dea  mov     [rbp+57h+var_B0], rdi
0x180029dee  movups  [rbp+57h+var_80], xmm0
0x180029df2  movups  [rbp+57h+var_98], xmm1
0x180029df6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180029dfc  mov     rcx, r14; this
0x180029dff  mov     [rbp+57h+var_A8], rdi
0x180029e03  call    ?DeletePipeInfo@PROTOCOL_MESSAGING_HANDLER@@AEAAJXZ; PROTOCOL_MESSAGING_HANDLER::DeletePipeInfo(void)
0x180029e08  lea     r8, [rbp+57h+hMem]; void **
0x180029e0c  mov     rdx, rsi; void *
0x180029e0f  call    ?CreateRegistrySecDesc@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAXPEAPEAX@Z; PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc(void *,void * *)
0x180029e14  mov     r15, [rbp+57h+hMem]
0x180029e18  mov     ebx, eax
0x180029e1a  test    eax, eax
0x180029e1c  jns     short loc_180029E61
0x180029e1e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180029e25  jz      loc_180029FCF
0x180029e2b  lea     rax, aErrorCreatingR; "Error creating registry security attrib"...
0x180029e32  mov     r8d, 274h
0x180029e38  mov     rcx, cs:g_pDebug
0x180029e3f  lea     r9, aProtocolMessag_21; "PROTOCOL_MESSAGING_HANDLER::CreateAndPu"...
0x180029e46  mov     [rsp+0E0h+var_B8], rax
0x180029e4b  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029e52  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180029e56  call    cs:__imp_PuDbgPrintError
0x180029e5c  jmp     loc_180029FCF
0x180029e61  mov     edi, 18h
0x180029e66  lea     rax, [rbp+57h+var_80]
0x180029e6a  mov     ecx, edi
0x180029e6c  mov     byte ptr [rax], 0
0x180029e6f  inc     rax
0x180029e72  sub     rcx, 1; this
0x180029e76  jnz     short loc_180029E6C
0x180029e78  lea     r8, [rbp+57h+var_B0]; void **
0x180029e7c  mov     dword ptr [rbp+57h+var_80], edi
0x180029e7f  mov     rdx, rsi; void *
0x180029e82  mov     qword ptr [rbp+57h+var_80+8], r15
0x180029e86  mov     dword ptr [rbp+57h+var_70], ecx
0x180029e89  call    ?CreatePipeSecDesc@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAXPEAPEAX@Z; PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc(void *,void * *)
0x180029e8e  mov     ebx, eax
0x180029e90  test    eax, eax
0x180029e92  jns     short loc_180029ED7
0x180029e94  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180029e9b  jz      short loc_180029ECE
0x180029e9d  mov     rcx, cs:g_pDebug
0x180029ea4  lea     rax, aErrorCreatingP; "Error creating pipe security attribute"...
0x180029eab  mov     [rsp+0E0h+var_B8], rax
0x180029eb0  lea     r9, aProtocolMessag_21; "PROTOCOL_MESSAGING_HANDLER::CreateAndPu"...
0x180029eb7  mov     r8d, 286h
0x180029ebd  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180029ec1  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029ec8  call    cs:__imp_PuDbgPrintError
0x180029ece  mov     rdi, [rbp+57h+var_B0]
0x180029ed2  jmp     loc_180029FCF
0x180029ed7  xor     esi, esi
0x180029ed9  lea     rax, [rbp+57h+var_98]
0x180029edd  mov     rcx, rdi
0x180029ee0  mov     [rax], sil
0x180029ee3  inc     rax
0x180029ee6  sub     rcx, 1
0x180029eea  jnz     short loc_180029EE0
0x180029eec  mov     dword ptr [rbp+57h+var_98], edi
0x180029eef  mov     rdi, [rbp+57h+var_B0]
0x180029ef3  mov     qword ptr [rbp+57h+var_98+8], rdi
0x180029ef7  mov     dword ptr [rbp+57h+var_88], esi
0x180029efa  lea     rdx, [rbp+57h+var_68]
0x180029efe  lea     rcx, aPipeWbhstipm; "\\\\.\\pipe\\wbhstipm"
0x180029f05  call    cs:__imp_?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z; GenerateNameWithGUID(ushort const *,STRU *)
0x180029f0b  mov     ebx, eax
0x180029f0d  test    eax, eax
0x180029f0f  jnz     loc_180029FC4
0x180029f15  mov     rdx, [rbp+57h+var_48]
0x180029f19  lea     rax, [r14+20h]
0x180029f1d  lea     r9, [rbp+57h+var_98]
0x180029f21  mov     [rsp+0E0h+var_C0], rax
0x180029f26  lea     r8d, [rbx+1]
0x180029f2a  mov     rcx, r14
0x180029f2d  call    cs:__imp_?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z; IPM_MESSAGE_PIPE::CreateIpmMessagePipe(IPM_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM_MESSAGE_PIPE * *)
0x180029f33  mov     ebx, eax
0x180029f35  cmp     eax, 800700B7h
0x180029f3a  jnz     short loc_180029F45
0x180029f3c  inc     esi
0x180029f3e  cmp     esi, 0Ah
0x180029f41  jb      short loc_180029EFA
0x180029f43  jmp     short loc_180029F49
0x180029f45  test    ebx, ebx
0x180029f47  jns     short loc_180029F64
0x180029f49  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180029f50  jz      short loc_180029FCF
0x180029f52  lea     rax, aCreatingMessag; "Creating message pipe failed\n"
0x180029f59  mov     r8d, 2B2h
0x180029f5f  jmp     loc_180029E38
0x180029f64  lea     rdx, [rbp+57h+var_A8]; unsigned __int16 **
0x180029f68  mov     rcx, r14; this
0x180029f6b  call    ?QueryPipeKeyName@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAPEBG@Z; PROTOCOL_MESSAGING_HANDLER::QueryPipeKeyName(ushort const * *)
0x180029f70  mov     ebx, eax
0x180029f72  test    eax, eax
0x180029f74  jns     short loc_180029F91
0x180029f76  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180029f7d  jz      short loc_180029FCF
0x180029f7f  lea     rax, aCouldNotGetThe; "Could not get the protocols registry ke"...
0x180029f86  mov     r8d, 2C3h
0x180029f8c  jmp     loc_180029E38
0x180029f91  mov     rcx, [rbp+57h+var_A8]
0x180029f95  lea     rdx, [rbp+57h+var_80]
0x180029f99  call    cs:__imp_?CreateSubkey@@YAKPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateSubkey(ushort const *,_SECURITY_ATTRIBUTES *)
0x180029f9f  test    eax, eax
0x180029fa1  jz      short loc_180029FA9
0x180029fa3  jg      short loc_180029FC6
0x180029fa5  mov     ebx, eax
0x180029fa7  jmp     short loc_180029FCF
0x180029fa9  mov     r8, [rbp+57h+var_48]
0x180029fad  lea     rdx, aName; "Name"
0x180029fb4  mov     rcx, [rbp+57h+var_A8]
0x180029fb8  call    cs:__imp_?SetStringParameterValueInAnyService@@YAKPEBG00@Z; SetStringParameterValueInAnyService(ushort const *,ushort const *,ushort const *)
0x180029fbe  test    eax, eax
0x180029fc0  jz      short loc_180029FCF
0x180029fc2  jmp     short loc_180029FA3
0x180029fc4  jle     short loc_180029FCF
0x180029fc6  movzx   ebx, ax
0x180029fc9  or      ebx, 80070000h
0x180029fcf  test    r15, r15
0x180029fd2  jz      short loc_180029FDD
0x180029fd4  mov     rcx, r15; hMem
0x180029fd7  call    cs:__imp_LocalFree
0x180029fdd  test    rdi, rdi
0x180029fe0  jz      short loc_180029FEB
0x180029fe2  mov     rcx, rdi; hMem
0x180029fe5  call    cs:__imp_LocalFree
0x180029feb  lea     rcx, [rbp+57h+var_68]
0x180029fef  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029ff5  mov     eax, ebx
0x180029ff7  mov     rcx, [rbp+57h+var_30]
0x180029ffb  xor     rcx, rsp; StackCookie
0x180029ffe  call    __security_check_cookie
0x18002a003  mov     rbx, [rsp+0E0h+arg_10]
0x18002a00b  add     rsp, 0C0h
0x18002a012  pop     r15
0x18002a014  pop     r14
0x18002a016  pop     rdi
0x18002a017  pop     rsi
0x18002a018  pop     rbp
0x18002a019  retn
```
