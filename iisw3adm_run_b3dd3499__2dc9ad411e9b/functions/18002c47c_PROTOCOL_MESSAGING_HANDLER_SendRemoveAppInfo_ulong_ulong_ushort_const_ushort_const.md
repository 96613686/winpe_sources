# PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo(ulong,ulong,ushort const *,ushort const *)

- ea: `0x18002c47c`
- end: `0x18002c639`
- name: `?SendRemoveAppInfo@PROTOCOL_MESSAGING_HANDLER@@QEAAJKKPEBG0@Z`
- size: `445`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001c9c0`

## callees

- `0x18002c2f4`
- `0x18002c47c`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c554`
- `iisutil!PuDbgPrint` at `0x18002c539`
- `iisutil!PuDbgPrint` at `0x18002c539`
- `iisutil!PuDbgPrintError` at `0x18002c601`
- `iisutil!PuDbgPrintError` at `0x18002c601`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c60c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c60c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002c54a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002c54a`

## string_xrefs

- `0x18002c532`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c5f6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c5d6`: `Failed copying data into buffer to send\n`
- `0x18002c519`: `PROTOCOL_MESSAGING_HANDLER::Send Remove App Info called \n`
- `0x18002c520`: `PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo`
- `0x18002c5ea`: `PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo(
        PROTOCOL_MESSAGING_HANDLER *this,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v11; // ebp
  size_t v12; // rbx
  signed int LastError; // eax
  int v14; // ebx
  _DWORD *v15; // rax
  _DWORD *v16; // rdi
  _QWORD v18[4]; // [rsp+30h] [rbp-78h] BYREF
  _DWORD *v19; // [rsp+50h] [rbp-58h]
  int v20; // [rsp+58h] [rbp-50h]
  __int16 v21; // [rsp+5Ch] [rbp-4Ch]

  v19 = v18;
  v18[0] = 0;
  v7 = -1;
  v8 = -1;
  v20 = 32;
  v21 = 256;
  do
    ++v8;
  while ( Src[v8] );
  v11 = 2 * v8 + 2;
  do
    ++v7;
  while ( a4[v7] );
  v12 = (unsigned int)(2 * v7 + 2);
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      2751,
      "PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo",
      "PROTOCOL_MESSAGING_HANDLER::Send Remove App Info called \n");
  if ( BUFFER::Resize((BUFFER *)v18, v12 + v11 + 8) )
  {
    v15 = v19;
    *v19 = a2;
    v15[1] = a3;
    v16 = v15 + 2;
    memcpy_0(v15 + 2, a4, v12);
    memcpy_0((char *)v16 + v12, Src, v11);
    v14 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 33);
    if ( v14 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2801,
        "PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo",
        v14,
        "Failed copying data into buffer to send\n",
        v18[0]);
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2770,
        "PROTOCOL_MESSAGING_HANDLER::SendRemoveAppInfo",
        v14,
        "Failed resizing the buffer to send data\n",
        v18[0]);
  }
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002c47c  mov     r11, rsp
0x18002c47f  mov     [r11+10h], rbx
0x18002c483  push    rbp
0x18002c484  push    rsi
0x18002c485  push    rdi
0x18002c486  push    r12
0x18002c488  push    r13
0x18002c48a  push    r14
0x18002c48c  push    r15
0x18002c48e  sub     rsp, 70h
0x18002c492  mov     rax, cs:__security_cookie
0x18002c499  xor     rax, rsp
0x18002c49c  mov     [rsp+0A8h+var_48], rax
0x18002c4a1  mov     r15, [rsp+0A8h+Src]
0x18002c4a9  lea     rax, [r11-78h]
0x18002c4ad  mov     [r11-58h], rax
0x18002c4b1  mov     r12d, edx
0x18002c4b4  xor     edx, edx
0x18002c4b6  mov     r13, rcx
0x18002c4b9  mov     [r11-78h], rdx
0x18002c4bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c4c1  mov     rcx, rax
0x18002c4c4  mov     [rsp+0A8h+var_50], 20h ; ' '
0x18002c4cc  mov     r14, r9
0x18002c4cf  mov     [rsp+0A8h+var_4C], 100h
0x18002c4d6  mov     edi, r8d
0x18002c4d9  inc     rcx
0x18002c4dc  cmp     [r15+rcx*2], dx
0x18002c4e1  jnz     short loc_18002C4D9
0x18002c4e3  lea     ebp, ds:2[rcx*2]
0x18002c4ea  inc     rax
0x18002c4ed  cmp     [r9+rax*2], dx
0x18002c4f2  jnz     short loc_18002C4EA
0x18002c4f4  lea     ebx, ds:2[rax*2]
0x18002c4fb  mov     eax, cs:g_dwDebugFlags
0x18002c501  test    eax, 210000h
0x18002c506  setnz   cl
0x18002c509  test    al, 3
0x18002c50b  setnz   al
0x18002c50e  test    al, cl
0x18002c510  jz      short loc_18002C53F
0x18002c512  mov     rcx, cs:g_pDebug
0x18002c519  lea     rax, aProtocolMessag_34; "PROTOCOL_MESSAGING_HANDLER::Send Remove"...
0x18002c520  lea     r9, aProtocolMessag_14; "PROTOCOL_MESSAGING_HANDLER::SendRemoveA"...
0x18002c527  mov     [rsp+0A8h+var_88], rax
0x18002c52c  mov     r8d, 0ABFh
0x18002c532  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002c539  call    cs:__imp_PuDbgPrint
0x18002c53f  lea     esi, [rbx+rbp]
0x18002c542  lea     edx, [rsi+8]
0x18002c545  lea     rcx, [rsp+0A8h+var_78]
0x18002c54a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002c550  test    al, al
0x18002c552  jnz     short loc_18002C585
0x18002c554  call    cs:__imp_GetLastError
0x18002c55a  mov     ebx, eax
0x18002c55c  test    eax, eax
0x18002c55e  jle     short loc_18002C569
0x18002c560  movzx   ebx, ax
0x18002c563  or      ebx, 80070000h
0x18002c569  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002c570  jz      loc_18002C607
0x18002c576  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002c57d  mov     r8d, 0AD2h
0x18002c583  jmp     short loc_18002C5E3
0x18002c585  mov     rax, [rsp+0A8h+var_58]
0x18002c58a  mov     r8, rbx; Size
0x18002c58d  mov     rdx, r14; Src
0x18002c590  mov     [rax], r12d
0x18002c593  mov     [rax+4], edi
0x18002c596  lea     rdi, [rax+8]
0x18002c59a  mov     rcx, rdi; void *
0x18002c59d  call    memcpy_0
0x18002c5a2  mov     r8d, ebp; Size
0x18002c5a5  lea     rcx, [rbx+rdi]; void *
0x18002c5a9  mov     rdx, r15; Src
0x18002c5ac  call    memcpy_0
0x18002c5b1  mov     r9, [rsp+0A8h+var_58]
0x18002c5b6  lea     r8d, [rsi+8]
0x18002c5ba  mov     edx, 21h ; '!'
0x18002c5bf  mov     rcx, r13
0x18002c5c2  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002c5c7  mov     ebx, eax
0x18002c5c9  test    eax, eax
0x18002c5cb  jns     short loc_18002C607
0x18002c5cd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002c5d4  jz      short loc_18002C607
0x18002c5d6  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002c5dd  mov     r8d, 0AF1h
0x18002c5e3  mov     rcx, cs:g_pDebug
0x18002c5ea  lea     r9, aProtocolMessag_14; "PROTOCOL_MESSAGING_HANDLER::SendRemoveA"...
0x18002c5f1  mov     [rsp+0A8h+var_80], rax
0x18002c5f6  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002c5fd  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18002c601  call    cs:__imp_PuDbgPrintError
0x18002c607  lea     rcx, [rsp+0A8h+var_78]
0x18002c60c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c612  mov     eax, ebx
0x18002c614  mov     rcx, [rsp+0A8h+var_48]
0x18002c619  xor     rcx, rsp; StackCookie
0x18002c61c  call    __security_check_cookie
0x18002c621  mov     rbx, [rsp+0A8h+arg_8]
0x18002c629  add     rsp, 70h
0x18002c62d  pop     r15
0x18002c62f  pop     r14
0x18002c631  pop     r13
0x18002c633  pop     r12
0x18002c635  pop     rdi
0x18002c636  pop     rsi
0x18002c637  pop     rbp
0x18002c638  retn
```
