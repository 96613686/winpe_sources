# PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue(ulong,ushort const *)

- ea: `0x18002bf20`
- end: `0x18002c0a8`
- name: `?SendDemandStartForQueue@PROTOCOL_MESSAGING_HANDLER@@QEAAJKPEBG@Z`
- size: `392`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c580`

## callees

- `0x18002bf20`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfde`
- `iisutil!PuDbgPrint` at `0x18002bfc6`
- `iisutil!PuDbgPrint` at `0x18002bfc6`
- `iisutil!PuDbgPrintError` at `0x18002c071`
- `iisutil!PuDbgPrintError` at `0x18002c071`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c07c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c07c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bfd4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bfd4`

## string_xrefs

- `0x18002bfb4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c066`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c046`: `Failed copying data into buffer to send\n`
- `0x18002bf9d`: `PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue called for Queue %d, App Pool %S\n`
- `0x18002bfa9`: `PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue`
- `0x18002c05a`: `PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue(
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
      2056,
      "PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue",
      "PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue called for Queue %d, App Pool %S\n",
      a2,
      a3);
  if ( BUFFER::Resize((BUFFER *)v12, v7 + 4) )
  {
    v10 = v13;
    *v13 = a2;
    memcpy_0(v10 + 1, a3, v7);
    v9 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 36);
    if ( v9 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2092,
        "PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue",
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
        2068,
        "PROTOCOL_MESSAGING_HANDLER::SendDemandStartForQueue",
        v9,
        "Failed resizing the buffer to send data\n");
  }
  BUFFER::~BUFFER((BUFFER *)v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002bf20  mov     r11, rsp
0x18002bf23  mov     [r11+20h], rbx
0x18002bf27  push    rbp
0x18002bf28  push    rsi
0x18002bf29  push    rdi
0x18002bf2a  push    r14
0x18002bf2c  push    r15
0x18002bf2e  sub     rsp, 80h
0x18002bf35  mov     rax, cs:__security_cookie
0x18002bf3c  xor     rax, rsp
0x18002bf3f  mov     [rsp+0A8h+var_38], rax
0x18002bf44  xor     r15d, r15d
0x18002bf47  lea     rax, [r11-68h]
0x18002bf4b  mov     [r11-48h], rax
0x18002bf4f  mov     rbx, r8
0x18002bf52  mov     [r11-68h], r15
0x18002bf56  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bf5a  mov     [rsp+0A8h+var_40], 20h ; ' '
0x18002bf62  mov     esi, edx
0x18002bf64  mov     [rsp+0A8h+var_3C], 100h
0x18002bf6b  mov     r14, rcx
0x18002bf6e  inc     rax
0x18002bf71  cmp     [r8+rax*2], r15w
0x18002bf76  jnz     short loc_18002BF6E
0x18002bf78  lea     ebp, ds:2[rax*2]
0x18002bf7f  mov     eax, cs:g_dwDebugFlags
0x18002bf85  test    eax, 210000h
0x18002bf8a  setnz   cl
0x18002bf8d  test    al, 3
0x18002bf8f  setnz   al
0x18002bf92  test    al, cl
0x18002bf94  jz      short loc_18002BFCC
0x18002bf96  mov     rcx, cs:g_pDebug
0x18002bf9d  lea     rax, aProtocolMessag_17; "PROTOCOL_MESSAGING_HANDLER::SendDemandS"...
0x18002bfa4  mov     [rsp+0A8h+var_78], rbx
0x18002bfa9  lea     r9, aProtocolMessag_16; "PROTOCOL_MESSAGING_HANDLER::SendDemandS"...
0x18002bfb0  mov     dword ptr [rsp+0A8h+var_80], esi
0x18002bfb4  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002bfbb  mov     r8d, 808h
0x18002bfc1  mov     [rsp+0A8h+var_88], rax
0x18002bfc6  call    cs:__imp_PuDbgPrint
0x18002bfcc  lea     edx, [rbp+4]
0x18002bfcf  lea     rcx, [rsp+0A8h+var_68]
0x18002bfd4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002bfda  test    al, al
0x18002bfdc  jnz     short loc_18002C00B
0x18002bfde  call    cs:__imp_GetLastError
0x18002bfe4  mov     ebx, eax
0x18002bfe6  test    eax, eax
0x18002bfe8  jle     short loc_18002BFF3
0x18002bfea  movzx   ebx, ax
0x18002bfed  or      ebx, 80070000h
0x18002bff3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002bffa  jz      short loc_18002C077
0x18002bffc  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002c003  mov     r8d, 814h
0x18002c009  jmp     short loc_18002C053
0x18002c00b  mov     rcx, [rsp+0A8h+var_48]
0x18002c010  mov     rdx, rbx; Src
0x18002c013  mov     r8d, ebp; Size
0x18002c016  mov     [rcx], esi
0x18002c018  add     rcx, 4; void *
0x18002c01c  call    memcpy_0
0x18002c021  mov     r9, [rsp+0A8h+var_48]
0x18002c026  lea     r8d, [rbp+4]
0x18002c02a  mov     edx, 24h ; '$'
0x18002c02f  mov     rcx, r14
0x18002c032  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002c037  mov     ebx, eax
0x18002c039  test    eax, eax
0x18002c03b  jns     short loc_18002C077
0x18002c03d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002c044  jz      short loc_18002C077
0x18002c046  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002c04d  mov     r8d, 82Ch
0x18002c053  mov     rcx, cs:g_pDebug
0x18002c05a  lea     r9, aProtocolMessag_16; "PROTOCOL_MESSAGING_HANDLER::SendDemandS"...
0x18002c061  mov     [rsp+0A8h+var_80], rax
0x18002c066  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002c06d  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18002c071  call    cs:__imp_PuDbgPrintError
0x18002c077  lea     rcx, [rsp+0A8h+var_68]
0x18002c07c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c082  mov     eax, ebx
0x18002c084  mov     rcx, [rsp+0A8h+var_38]
0x18002c089  xor     rcx, rsp; StackCookie
0x18002c08c  call    __security_check_cookie
0x18002c091  mov     rbx, [rsp+0A8h+arg_18]
0x18002c099  add     rsp, 80h
0x18002c0a0  pop     r15
0x18002c0a2  pop     r14
0x18002c0a4  pop     rdi
0x18002c0a5  pop     rsi
0x18002c0a6  pop     rbp
0x18002c0a7  retn
```
