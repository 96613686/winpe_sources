# PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped(ulong,ushort const *)

- ea: `0x18002b3b8`
- end: `0x18002b540`
- name: `?SendAllQueueInstancesStopped@PROTOCOL_MESSAGING_HANDLER@@QEAAJKPEBG@Z`
- size: `392`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c4e0`

## callees

- `0x18002b3b8`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b476`
- `iisutil!PuDbgPrint` at `0x18002b45e`
- `iisutil!PuDbgPrint` at `0x18002b45e`
- `iisutil!PuDbgPrintError` at `0x18002b509`
- `iisutil!PuDbgPrintError` at `0x18002b509`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b514`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b514`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b46c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b46c`

## string_xrefs

- `0x18002b44c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b4fe`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b4de`: `Failed copying data into buffer to send\n`
- `0x18002b435`: `PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped called for Queue %d, App Pool %S\n`
- `0x18002b441`: `PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped`
- `0x18002b4f2`: `PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped(
        PROTOCOL_MESSAGING_HANDLER *this,
        int a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rax
  unsigned int v7; // ebp
  signed int LastError; // eax
  int v9; // ebx
  int *v10; // rcx
  _QWORD v12[4]; // [rsp+40h] [rbp-68h] BYREF
  int *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  __int16 v15; // [rsp+6Ch] [rbp-3Ch]

  v13 = (int *)v12;
  v12[0] = 0;
  v4 = -1;
  v14 = 32;
  v15 = 256;
  do
    ++v4;
  while ( a3[v4] );
  v7 = 2 * v4 + 2;
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      2143,
      "PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped",
      "PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped called for Queue %d, App Pool %S\n",
      a2,
      a3);
  if ( BUFFER::Resize((BUFFER *)v12, v7 + 4) )
  {
    v10 = v13;
    *v13 = a2;
    memcpy_0(v10 + 1, a3, v7);
    v9 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 42);
    if ( v9 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2179,
        "PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped",
        v9,
        "Failed copying data into buffer to send\n");
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2155,
        "PROTOCOL_MESSAGING_HANDLER::SendAllQueueInstancesStopped",
        v9,
        "Failed resizing the buffer to send data\n");
  }
  BUFFER::~BUFFER((BUFFER *)v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b3b8  mov     r11, rsp
0x18002b3bb  mov     [r11+20h], rbx
0x18002b3bf  push    rbp
0x18002b3c0  push    rsi
0x18002b3c1  push    rdi
0x18002b3c2  push    r14
0x18002b3c4  push    r15
0x18002b3c6  sub     rsp, 80h
0x18002b3cd  mov     rax, cs:__security_cookie
0x18002b3d4  xor     rax, rsp
0x18002b3d7  mov     [rsp+0A8h+var_38], rax
0x18002b3dc  xor     r15d, r15d
0x18002b3df  lea     rax, [r11-68h]
0x18002b3e3  mov     [r11-48h], rax
0x18002b3e7  mov     rbx, r8
0x18002b3ea  mov     [r11-68h], r15
0x18002b3ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b3f2  mov     [rsp+0A8h+var_40], 20h ; ' '
0x18002b3fa  mov     esi, edx
0x18002b3fc  mov     [rsp+0A8h+var_3C], 100h
0x18002b403  mov     r14, rcx
0x18002b406  inc     rax
0x18002b409  cmp     [r8+rax*2], r15w
0x18002b40e  jnz     short loc_18002B406
0x18002b410  lea     ebp, ds:2[rax*2]
0x18002b417  mov     eax, cs:g_dwDebugFlags
0x18002b41d  test    eax, 210000h
0x18002b422  setnz   cl
0x18002b425  test    al, 3
0x18002b427  setnz   al
0x18002b42a  test    al, cl
0x18002b42c  jz      short loc_18002B464
0x18002b42e  mov     rcx, cs:g_pDebug
0x18002b435  lea     rax, aProtocolMessag_5; "PROTOCOL_MESSAGING_HANDLER::SendAllQueu"...
0x18002b43c  mov     [rsp+0A8h+var_78], rbx
0x18002b441  lea     r9, aProtocolMessag_38; "PROTOCOL_MESSAGING_HANDLER::SendAllQueu"...
0x18002b448  mov     dword ptr [rsp+0A8h+var_80], esi
0x18002b44c  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b453  mov     r8d, 85Fh
0x18002b459  mov     [rsp+0A8h+var_88], rax
0x18002b45e  call    cs:__imp_PuDbgPrint
0x18002b464  lea     edx, [rbp+4]
0x18002b467  lea     rcx, [rsp+0A8h+var_68]
0x18002b46c  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002b472  test    al, al
0x18002b474  jnz     short loc_18002B4A3
0x18002b476  call    cs:__imp_GetLastError
0x18002b47c  mov     ebx, eax
0x18002b47e  test    eax, eax
0x18002b480  jle     short loc_18002B48B
0x18002b482  movzx   ebx, ax
0x18002b485  or      ebx, 80070000h
0x18002b48b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b492  jz      short loc_18002B50F
0x18002b494  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002b49b  mov     r8d, 86Bh
0x18002b4a1  jmp     short loc_18002B4EB
0x18002b4a3  mov     rcx, [rsp+0A8h+var_48]
0x18002b4a8  mov     rdx, rbx; Src
0x18002b4ab  mov     r8d, ebp; Size
0x18002b4ae  mov     [rcx], esi
0x18002b4b0  add     rcx, 4; void *
0x18002b4b4  call    memcpy_0
0x18002b4b9  mov     r9, [rsp+0A8h+var_48]
0x18002b4be  lea     r8d, [rbp+4]
0x18002b4c2  mov     edx, 2Ah ; '*'
0x18002b4c7  mov     rcx, r14
0x18002b4ca  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002b4cf  mov     ebx, eax
0x18002b4d1  test    eax, eax
0x18002b4d3  jns     short loc_18002B50F
0x18002b4d5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b4dc  jz      short loc_18002B50F
0x18002b4de  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002b4e5  mov     r8d, 883h
0x18002b4eb  mov     rcx, cs:g_pDebug
0x18002b4f2  lea     r9, aProtocolMessag_38; "PROTOCOL_MESSAGING_HANDLER::SendAllQueu"...
0x18002b4f9  mov     [rsp+0A8h+var_80], rax
0x18002b4fe  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b505  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18002b509  call    cs:__imp_PuDbgPrintError
0x18002b50f  lea     rcx, [rsp+0A8h+var_68]
0x18002b514  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b51a  mov     eax, ebx
0x18002b51c  mov     rcx, [rsp+0A8h+var_38]
0x18002b521  xor     rcx, rsp; StackCookie
0x18002b524  call    __security_check_cookie
0x18002b529  mov     rbx, [rsp+0A8h+arg_18]
0x18002b531  add     rsp, 80h
0x18002b538  pop     r15
0x18002b53a  pop     r14
0x18002b53c  pop     rdi
0x18002b53d  pop     rsi
0x18002b53e  pop     rbp
0x18002b53f  retn
```
