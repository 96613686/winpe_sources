# PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool(ushort const *,ushort const *)

- ea: `0x18002bb14`
- end: `0x18002bcbb`
- name: `?SendApplicationAppPool@PROTOCOL_MESSAGING_HANDLER@@QEAAJPEBG0@Z`
- size: `423`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c8f0`

## callees

- `0x18002bb14`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbe1`
- `iisutil!PuDbgPrint` at `0x18002bbc7`
- `iisutil!PuDbgPrint` at `0x18002bbc7`
- `iisutil!PuDbgPrintError` at `0x18002bc83`
- `iisutil!PuDbgPrintError` at `0x18002bc83`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bc8e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bc8e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bbd7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bbd7`

## string_xrefs

- `0x18002bbc0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002bc78`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002bc58`: `Failed copying data into buffer to send\n`
- `0x18002bba7`: `PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool called \n`
- `0x18002bbae`: `PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool`
- `0x18002bc6c`: `PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool(
        PROTOCOL_MESSAGING_HANDLER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v8; // ebp
  size_t v9; // rbx
  signed int LastError; // eax
  int v11; // ebx
  char *v12; // rdi
  _QWORD v14[4]; // [rsp+30h] [rbp-78h] BYREF
  void *v15; // [rsp+50h] [rbp-58h]
  int v16; // [rsp+58h] [rbp-50h]
  __int16 v17; // [rsp+5Ch] [rbp-4Ch]

  v15 = v14;
  v14[0] = 0;
  v4 = -1;
  v5 = -1;
  v16 = 32;
  v17 = 256;
  do
    ++v5;
  while ( a3[v5] );
  v8 = 2 * v5 + 2;
  do
    ++v4;
  while ( a2[v4] );
  v9 = (unsigned int)(2 * v4 + 2);
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      1967,
      "PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool",
      "PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool called \n");
  if ( BUFFER::Resize((BUFFER *)v14, v9 + v8) )
  {
    v12 = (char *)v15;
    memcpy_0(v15, a2, v9);
    memcpy_0(&v12[v9], a3, v8);
    v11 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 43);
    if ( v11 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2007,
        "PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool",
        v11,
        "Failed copying data into buffer to send\n",
        v14[0]);
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        1986,
        "PROTOCOL_MESSAGING_HANDLER::SendApplicationAppPool",
        v11,
        "Failed resizing the buffer to send data\n",
        v14[0]);
  }
  BUFFER::~BUFFER((BUFFER *)v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002bb14  mov     r11, rsp
0x18002bb17  mov     [r11+20h], rbx
0x18002bb1b  push    rbp
0x18002bb1c  push    rsi
0x18002bb1d  push    rdi
0x18002bb1e  push    r12
0x18002bb20  push    r13
0x18002bb22  push    r14
0x18002bb24  push    r15
0x18002bb26  sub     rsp, 70h
0x18002bb2a  mov     rax, cs:__security_cookie
0x18002bb31  xor     rax, rsp
0x18002bb34  mov     [rsp+0A8h+var_48], rax
0x18002bb39  lea     rax, [r11-78h]
0x18002bb3d  xor     r13d, r13d
0x18002bb40  mov     [r11-58h], rax
0x18002bb44  mov     r12, rcx
0x18002bb47  mov     [r11-78h], r13
0x18002bb4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bb4f  mov     rcx, rax
0x18002bb52  mov     [rsp+0A8h+var_50], 20h ; ' '
0x18002bb5a  mov     r15, r8
0x18002bb5d  mov     [rsp+0A8h+var_4C], 100h
0x18002bb64  mov     r14, rdx
0x18002bb67  inc     rcx
0x18002bb6a  cmp     [r8+rcx*2], r13w
0x18002bb6f  jnz     short loc_18002BB67
0x18002bb71  lea     ebp, ds:2[rcx*2]
0x18002bb78  inc     rax
0x18002bb7b  cmp     [rdx+rax*2], r13w
0x18002bb80  jnz     short loc_18002BB78
0x18002bb82  lea     ebx, ds:2[rax*2]
0x18002bb89  mov     eax, cs:g_dwDebugFlags
0x18002bb8f  test    eax, 210000h
0x18002bb94  setnz   cl
0x18002bb97  test    al, 3
0x18002bb99  setnz   al
0x18002bb9c  test    al, cl
0x18002bb9e  jz      short loc_18002BBCD
0x18002bba0  mov     rcx, cs:g_pDebug
0x18002bba7  lea     rax, aProtocolMessag_18; "PROTOCOL_MESSAGING_HANDLER::SendApplica"...
0x18002bbae  lea     r9, aProtocolMessag; "PROTOCOL_MESSAGING_HANDLER::SendApplica"...
0x18002bbb5  mov     [rsp+0A8h+var_88], rax
0x18002bbba  mov     r8d, 7AFh
0x18002bbc0  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002bbc7  call    cs:__imp_PuDbgPrint
0x18002bbcd  lea     esi, [rbx+rbp]
0x18002bbd0  mov     edx, esi
0x18002bbd2  lea     rcx, [rsp+0A8h+var_78]
0x18002bbd7  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002bbdd  test    al, al
0x18002bbdf  jnz     short loc_18002BC12
0x18002bbe1  call    cs:__imp_GetLastError
0x18002bbe7  mov     ebx, eax
0x18002bbe9  test    eax, eax
0x18002bbeb  jle     short loc_18002BBF6
0x18002bbed  movzx   ebx, ax
0x18002bbf0  or      ebx, 80070000h
0x18002bbf6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002bbfd  jz      loc_18002BC89
0x18002bc03  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002bc0a  mov     r8d, 7C2h
0x18002bc10  jmp     short loc_18002BC65
0x18002bc12  mov     rdi, [rsp+0A8h+var_58]
0x18002bc17  mov     r8, rbx; Size
0x18002bc1a  mov     rcx, rdi; void *
0x18002bc1d  mov     rdx, r14; Src
0x18002bc20  call    memcpy_0
0x18002bc25  mov     r8d, ebp; Size
0x18002bc28  lea     rcx, [rbx+rdi]; void *
0x18002bc2c  mov     rdx, r15; Src
0x18002bc2f  call    memcpy_0
0x18002bc34  mov     r9, [rsp+0A8h+var_58]
0x18002bc39  mov     r8d, esi
0x18002bc3c  mov     edx, 2Bh ; '+'
0x18002bc41  mov     rcx, r12
0x18002bc44  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002bc49  mov     ebx, eax
0x18002bc4b  test    eax, eax
0x18002bc4d  jns     short loc_18002BC89
0x18002bc4f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002bc56  jz      short loc_18002BC89
0x18002bc58  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002bc5f  mov     r8d, 7D7h
0x18002bc65  mov     rcx, cs:g_pDebug
0x18002bc6c  lea     r9, aProtocolMessag; "PROTOCOL_MESSAGING_HANDLER::SendApplica"...
0x18002bc73  mov     [rsp+0A8h+var_80], rax
0x18002bc78  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002bc7f  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18002bc83  call    cs:__imp_PuDbgPrintError
0x18002bc89  lea     rcx, [rsp+0A8h+var_78]
0x18002bc8e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002bc94  mov     eax, ebx
0x18002bc96  mov     rcx, [rsp+0A8h+var_48]
0x18002bc9b  xor     rcx, rsp; StackCookie
0x18002bc9e  call    __security_check_cookie
0x18002bca3  mov     rbx, [rsp+0A8h+arg_18]
0x18002bcab  add     rsp, 70h
0x18002bcaf  pop     r15
0x18002bcb1  pop     r14
0x18002bcb3  pop     r13
0x18002bcb5  pop     r12
0x18002bcb7  pop     rdi
0x18002bcb8  pop     rsi
0x18002bcb9  pop     rbp
0x18002bcba  retn
```
