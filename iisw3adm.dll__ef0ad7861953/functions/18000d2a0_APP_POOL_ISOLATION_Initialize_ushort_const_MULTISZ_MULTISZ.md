# APP_POOL_ISOLATION::Initialize(ushort const *,MULTISZ *,MULTISZ *)

- ea: `0x18000d2a0`
- end: `0x18000d48c`
- name: `?Initialize@APP_POOL_ISOLATION@@QEAAJPEBGPEAVMULTISZ@@1@Z`
- size: `492`
- prototype: `__int64 __fastcall(APP_POOL_ISOLATION *__hidden this, const unsigned __int16 *, struct MULTISZ *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800044d4`

## callees

- `0x180005878`
- `0x180009350`
- `0x18000c754`
- `0x18000c9b4`
- `0x18000d2a0`
- `0x1800609c0`
- `0x180061026`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d3c6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d3c6`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000d2d3`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000d2eb`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000d2d3`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000d2eb`
- `iisutil!IsPathUnc` at `0x18000d331`
- `iisutil!IsPathUnc` at `0x18000d331`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000d397`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000d397`

## string_xrefs

- `0x18000d2bb`: `%systemdrive%\inetpub\temp\apppools`
- `0x18000d3d7`: `%systemdrive%\inetpub\temp\apppools`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::Initialize(
        APP_POOL_ISOLATION *this,
        const unsigned __int16 *a2,
        struct MULTISZ *a3,
        struct MULTISZ *a4)
{
  const unsigned __int16 *v5; // r14
  APP_POOL_ISOLATION *v7; // rcx
  int DefaultTempConfigIsolationDirectory; // ebx
  int v9; // esi
  DWORD FileAttributesW; // eax
  DWORD LastError; // ebx
  signed int v12; // eax
  int v14; // [rsp+70h] [rbp+8h] BYREF

  v14 = 0;
  v5 = L"%systemdrive%\\inetpub\\temp\\apppools";
  if ( a2 )
    v5 = a2;
  if ( MULTISZ::Copy((APP_POOL_ISOLATION *)((char *)this + 336), a3)
    && MULTISZ::Copy((APP_POOL_ISOLATION *)((char *)this + 280), a4) )
  {
    DefaultTempConfigIsolationDirectory = XML_NODE_PATTERN_HELPER::ComputeWholeSiteInclusionXmlPattern((struct XML_NODE_PATTERN **)this + 30);
    if ( DefaultTempConfigIsolationDirectory < 0 )
      return (unsigned int)DefaultTempConfigIsolationDirectory;
    DefaultTempConfigIsolationDirectory = APP_POOL_ISOLATION::ExpandPath(
                                            v7,
                                            v5,
                                            (APP_POOL_ISOLATION *)((char *)this + 96));
    if ( DefaultTempConfigIsolationDirectory < 0 )
      return (unsigned int)DefaultTempConfigIsolationDirectory;
    DefaultTempConfigIsolationDirectory = IsPathUnc(*((const unsigned __int16 **)this + 16), &v14);
    if ( DefaultTempConfigIsolationDirectory < 0 )
      return (unsigned int)DefaultTempConfigIsolationDirectory;
    if ( v14 )
    {
      DefaultTempConfigIsolationDirectory = -2147024809;
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC0001447, 0, 0, 0x80070057);
      return (unsigned int)DefaultTempConfigIsolationDirectory;
    }
    v9 = 1;
    if ( *(_WORD *)(*((_QWORD *)this + 16) + 2LL * (unsigned int)(*((_DWORD *)this + 36) - 1)) != 92 )
    {
      DefaultTempConfigIsolationDirectory = STRU::Append((APP_POOL_ISOLATION *)((char *)this + 96), 0x5Cu);
      if ( DefaultTempConfigIsolationDirectory < 0 )
        return (unsigned int)DefaultTempConfigIsolationDirectory;
    }
    *(_WORD *)(*((_QWORD *)this + 16) + 2LL * (unsigned int)(*((_DWORD *)this + 36) - 1)) = 0;
    FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 16));
    if ( FileAttributesW != -1 )
    {
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_17;
      DefaultTempConfigIsolationDirectory = -2147024809;
      goto LABEL_28;
    }
    LastError = GetLastError();
    if ( !wcscmp_0(v5, L"%systemdrive%\\inetpub\\temp\\apppools") && LastError - 2 <= 1 )
    {
      DefaultTempConfigIsolationDirectory = APP_POOL_ISOLATION::CreateDefaultTempConfigIsolationDirectory(this);
      if ( DefaultTempConfigIsolationDirectory >= 0 )
      {
LABEL_17:
        *(_WORD *)(*((_QWORD *)this + 16) + 2LL * (unsigned int)(*((_DWORD *)this + 36) - 1)) = 92;
        return (unsigned int)MULTI_WORK_QUEUE::Initialize((APP_POOL_ISOLATION *)((char *)this + 392));
      }
LABEL_28:
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC0001444, 0, 0, DefaultTempConfigIsolationDirectory);
      return (unsigned int)DefaultTempConfigIsolationDirectory;
    }
    if ( !GetLastError() )
    {
      DefaultTempConfigIsolationDirectory = -2147467259;
      goto LABEL_26;
    }
  }
  else
  {
    if ( !GetLastError() )
      return (unsigned int)-2147467259;
    v9 = 0;
  }
  v12 = GetLastError();
  DefaultTempConfigIsolationDirectory = v12;
  if ( v12 > 0 )
    DefaultTempConfigIsolationDirectory = (unsigned __int16)v12 | 0x80070000;
LABEL_26:
  if ( DefaultTempConfigIsolationDirectory < 0 && v9 )
    goto LABEL_28;
  return (unsigned int)DefaultTempConfigIsolationDirectory;
}

```

## disassembly

```asm
0x18000d2a0  push    rbx
0x18000d2a2  push    rbp
0x18000d2a3  push    rsi
0x18000d2a4  push    rdi
0x18000d2a5  push    r14
0x18000d2a7  push    r15
0x18000d2a9  sub     rsp, 38h
0x18000d2ad  test    rdx, rdx
0x18000d2b0  mov     [rsp+68h+arg_0], 0
0x18000d2b8  mov     rdi, rcx
0x18000d2bb  lea     r14, aSystemdriveIne; "%systemdrive%\\inetpub\\temp\\apppools"
0x18000d2c2  cmovnz  r14, rdx
0x18000d2c6  mov     rbx, r9
0x18000d2c9  add     rcx, 150h
0x18000d2d0  mov     rdx, r8
0x18000d2d3  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x18000d2d9  test    eax, eax
0x18000d2db  jz      loc_18000D441
0x18000d2e1  lea     rcx, [rdi+118h]
0x18000d2e8  mov     rdx, rbx
0x18000d2eb  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x18000d2f1  test    eax, eax
0x18000d2f3  jz      loc_18000D441
0x18000d2f9  lea     rcx, [rdi+0F0h]; struct XML_NODE_PATTERN **
0x18000d300  call    ?ComputeWholeSiteInclusionXmlPattern@XML_NODE_PATTERN_HELPER@@SAJPEAPEAVXML_NODE_PATTERN@@@Z; XML_NODE_PATTERN_HELPER::ComputeWholeSiteInclusionXmlPattern(XML_NODE_PATTERN * *)
0x18000d305  mov     ebx, eax
0x18000d307  test    eax, eax
0x18000d309  js      loc_18000D47D
0x18000d30f  lea     r8, [rdi+60h]; struct STRU *
0x18000d313  mov     rdx, r14; unsigned __int16 *
0x18000d316  call    ?ExpandPath@APP_POOL_ISOLATION@@AEAAJPEBGPEAVSTRU@@@Z; APP_POOL_ISOLATION::ExpandPath(ushort const *,STRU *)
0x18000d31b  mov     ebx, eax
0x18000d31d  test    eax, eax
0x18000d31f  js      loc_18000D47D
0x18000d325  mov     rcx, [rdi+80h]
0x18000d32c  lea     rdx, [rsp+68h+arg_0]
0x18000d331  call    cs:__imp_?IsPathUnc@@YAJPEBGPEAH@Z; IsPathUnc(ushort const *,int *)
0x18000d337  mov     ebx, eax
0x18000d339  test    eax, eax
0x18000d33b  js      loc_18000D47D
0x18000d341  cmp     [rsp+68h+arg_0], 0
0x18000d346  jz      short loc_18000D371
0x18000d348  mov     ebx, 80070057h
0x18000d34d  mov     [rsp+68h+var_48], 80070057h; unsigned int
0x18000d355  mov     edx, 0C0001447h; unsigned int
0x18000d35a  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18000d361  xor     r8d, r8d; unsigned __int16
0x18000d364  xor     r9d, r9d; unsigned __int16 **
0x18000d367  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000d36c  jmp     loc_18000D47D
0x18000d371  mov     edx, [rdi+90h]
0x18000d377  mov     esi, 1
0x18000d37c  mov     rax, [rdi+80h]
0x18000d383  sub     edx, esi
0x18000d385  lea     r15d, [rsi+5Bh]
0x18000d389  cmp     [rax+rdx*2], r15w
0x18000d38e  jz      short loc_18000D3A7
0x18000d390  mov     edx, r15d
0x18000d393  lea     rcx, [rdi+60h]
0x18000d397  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x18000d39d  mov     ebx, eax
0x18000d39f  test    eax, eax
0x18000d3a1  js      loc_18000D47D
0x18000d3a7  mov     r9d, [rdi+90h]
0x18000d3ae  xor     eax, eax
0x18000d3b0  mov     r8, [rdi+80h]
0x18000d3b7  sub     r9d, esi
0x18000d3ba  mov     [r8+r9*2], ax
0x18000d3bf  mov     rcx, [rdi+80h]; lpFileName
0x18000d3c6  call    cs:__imp_GetFileAttributesW
0x18000d3cc  cmp     eax, 0FFFFFFFFh
0x18000d3cf  jnz     short loc_18000D436
0x18000d3d1  call    cs:__imp_GetLastError
0x18000d3d7  lea     rdx, aSystemdriveIne; "%systemdrive%\\inetpub\\temp\\apppools"
0x18000d3de  mov     rcx, r14; String1
0x18000d3e1  mov     ebx, eax
0x18000d3e3  call    wcscmp_0
0x18000d3e8  test    eax, eax
0x18000d3ea  jnz     short loc_18000D425
0x18000d3ec  lea     eax, [rbx-2]
0x18000d3ef  cmp     eax, esi
0x18000d3f1  ja      short loc_18000D425
0x18000d3f3  mov     rcx, rdi; this
0x18000d3f6  call    ?CreateDefaultTempConfigIsolationDirectory@APP_POOL_ISOLATION@@AEBAJXZ; APP_POOL_ISOLATION::CreateDefaultTempConfigIsolationDirectory(void)
0x18000d3fb  mov     ebx, eax
0x18000d3fd  test    eax, eax
0x18000d3ff  js      short loc_18000D46A
0x18000d401  mov     ecx, [rdi+90h]
0x18000d407  mov     rax, [rdi+80h]
0x18000d40e  sub     ecx, esi
0x18000d410  mov     [rax+rcx*2], r15w
0x18000d415  lea     rcx, [rdi+188h]; this
0x18000d41c  call    ?Initialize@MULTI_WORK_QUEUE@@QEAAJXZ; MULTI_WORK_QUEUE::Initialize(void)
0x18000d421  mov     ebx, eax
0x18000d423  jmp     short loc_18000D47D
0x18000d425  call    cs:__imp_GetLastError
0x18000d42b  test    eax, eax
0x18000d42d  jnz     short loc_18000D44D
0x18000d42f  mov     ebx, 80004005h
0x18000d434  jmp     short loc_18000D462
0x18000d436  test    al, 10h
0x18000d438  jnz     short loc_18000D401
0x18000d43a  mov     ebx, 80070057h
0x18000d43f  jmp     short loc_18000D46A
0x18000d441  call    cs:__imp_GetLastError
0x18000d447  test    eax, eax
0x18000d449  jz      short loc_18000D478
0x18000d44b  xor     esi, esi
0x18000d44d  call    cs:__imp_GetLastError
0x18000d453  mov     ebx, eax
0x18000d455  test    eax, eax
0x18000d457  jle     short loc_18000D462
0x18000d459  movzx   ebx, ax
0x18000d45c  or      ebx, 80070000h
0x18000d462  test    ebx, ebx
0x18000d464  jns     short loc_18000D47D
0x18000d466  test    esi, esi
0x18000d468  jz      short loc_18000D47D
0x18000d46a  mov     [rsp+68h+var_48], ebx
0x18000d46e  mov     edx, 0C0001444h
0x18000d473  jmp     loc_18000D35A
0x18000d478  mov     ebx, 80004005h
0x18000d47d  mov     eax, ebx
0x18000d47f  add     rsp, 38h
0x18000d483  pop     r15
0x18000d485  pop     r14
0x18000d487  pop     rdi
0x18000d488  pop     rsi
0x18000d489  pop     rbp
0x18000d48a  pop     rbx
0x18000d48b  retn
```
