# PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool(ulong,ushort const *,int)

- ea: `0x18002c0b0`
- end: `0x18002c238`
- name: `?SendEnableOrDisableAppPool@PROTOCOL_MESSAGING_HANDLER@@QEAAJKPEBGH@Z`
- size: `392`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, unsigned int, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c5d0`
- `0x18001c660`

## callees

- `0x18002c0b0`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c16d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c16d`
- `iisutil!PuDbgPrint` at `0x18002c155`
- `iisutil!PuDbgPrint` at `0x18002c155`
- `iisutil!PuDbgPrintError` at `0x18002c1ff`
- `iisutil!PuDbgPrintError` at `0x18002c1ff`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c20a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c20a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002c163`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002c163`

## string_xrefs

- `0x18002c14e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c1f4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002c1d4`: `Failed copying data into buffer to send\n`
- `0x18002c135`: `PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool called \n`
- `0x18002c13c`: `PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool`
- `0x18002c1e8`: `PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool(
        PROTOCOL_MESSAGING_HANDLER *this,
        int a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v5; // rax
  unsigned int v8; // esi
  int v9; // ebp
  signed int LastError; // eax
  int v11; // ebx
  _DWORD *v12; // rcx
  _QWORD v14[4]; // [rsp+30h] [rbp-68h] BYREF
  _DWORD *v15; // [rsp+50h] [rbp-48h]
  int v16; // [rsp+58h] [rbp-40h]
  __int16 v17; // [rsp+5Ch] [rbp-3Ch]

  v15 = v14;
  v14[0] = 0;
  v5 = -1;
  v16 = 32;
  v17 = 256;
  do
    ++v5;
  while ( a3[v5] );
  v8 = 2 * v5 + 2;
  v9 = -(a4 != 0);
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      2579,
      "PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool",
      "PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool called \n");
  if ( BUFFER::Resize((BUFFER *)v14, v8 + 4) )
  {
    v12 = v15;
    *v15 = a2;
    memcpy_0(v12 + 1, a3, v8);
    v11 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, v9 + 35);
    if ( v11 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        2619,
        "PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool",
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
        2596,
        "PROTOCOL_MESSAGING_HANDLER::SendEnableOrDisableAppPool",
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
0x18002c0b0  mov     r11, rsp
0x18002c0b3  mov     [r11+10h], rbx
0x18002c0b7  mov     [r11+20h], rbp
0x18002c0bb  push    rsi
0x18002c0bc  push    rdi
0x18002c0bd  push    r12
0x18002c0bf  push    r14
0x18002c0c1  push    r15
0x18002c0c3  sub     rsp, 70h
0x18002c0c7  mov     rax, cs:__security_cookie
0x18002c0ce  xor     rax, rsp
0x18002c0d1  mov     [rsp+98h+var_38], rax
0x18002c0d6  xor     r12d, r12d
0x18002c0d9  lea     rax, [r11-68h]
0x18002c0dd  mov     [r11-48h], rax
0x18002c0e1  mov     rdi, r8
0x18002c0e4  mov     [r11-68h], r12
0x18002c0e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c0ec  mov     [rsp+98h+var_40], 20h ; ' '
0x18002c0f4  mov     r14d, edx
0x18002c0f7  mov     [rsp+98h+var_3C], 100h
0x18002c0fe  mov     r15, rcx
0x18002c101  inc     rax
0x18002c104  cmp     [r8+rax*2], r12w
0x18002c109  jnz     short loc_18002C101
0x18002c10b  neg     r9d
0x18002c10e  lea     esi, ds:2[rax*2]
0x18002c115  mov     eax, cs:g_dwDebugFlags
0x18002c11b  sbb     ebp, ebp
0x18002c11d  test    eax, 210000h
0x18002c122  setnz   cl
0x18002c125  test    al, 3
0x18002c127  setnz   al
0x18002c12a  test    al, cl
0x18002c12c  jz      short loc_18002C15B
0x18002c12e  mov     rcx, cs:g_pDebug
0x18002c135  lea     rax, aProtocolMessag_36; "PROTOCOL_MESSAGING_HANDLER::SendEnableO"...
0x18002c13c  lea     r9, aProtocolMessag_25; "PROTOCOL_MESSAGING_HANDLER::SendEnableO"...
0x18002c143  mov     [rsp+98h+var_78], rax
0x18002c148  mov     r8d, 0A13h
0x18002c14e  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002c155  call    cs:__imp_PuDbgPrint
0x18002c15b  lea     edx, [rsi+4]
0x18002c15e  lea     rcx, [rsp+98h+var_68]
0x18002c163  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002c169  test    al, al
0x18002c16b  jnz     short loc_18002C19A
0x18002c16d  call    cs:__imp_GetLastError
0x18002c173  mov     ebx, eax
0x18002c175  test    eax, eax
0x18002c177  jle     short loc_18002C182
0x18002c179  movzx   ebx, ax
0x18002c17c  or      ebx, 80070000h
0x18002c182  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002c189  jz      short loc_18002C205
0x18002c18b  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002c192  mov     r8d, 0A24h
0x18002c198  jmp     short loc_18002C1E1
0x18002c19a  mov     rcx, [rsp+98h+var_48]
0x18002c19f  mov     rdx, rdi; Src
0x18002c1a2  mov     r8d, esi; Size
0x18002c1a5  mov     [rcx], r14d
0x18002c1a8  add     rcx, 4; void *
0x18002c1ac  call    memcpy_0
0x18002c1b1  mov     r9, [rsp+98h+var_48]
0x18002c1b6  lea     r8d, [rsi+4]
0x18002c1ba  lea     edx, [rbp+23h]
0x18002c1bd  mov     rcx, r15
0x18002c1c0  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002c1c5  mov     ebx, eax
0x18002c1c7  test    eax, eax
0x18002c1c9  jns     short loc_18002C205
0x18002c1cb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002c1d2  jz      short loc_18002C205
0x18002c1d4  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002c1db  mov     r8d, 0A3Bh
0x18002c1e1  mov     rcx, cs:g_pDebug
0x18002c1e8  lea     r9, aProtocolMessag_25; "PROTOCOL_MESSAGING_HANDLER::SendEnableO"...
0x18002c1ef  mov     [rsp+98h+var_70], rax
0x18002c1f4  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002c1fb  mov     dword ptr [rsp+98h+var_78], ebx
0x18002c1ff  call    cs:__imp_PuDbgPrintError
0x18002c205  lea     rcx, [rsp+98h+var_68]
0x18002c20a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c210  mov     eax, ebx
0x18002c212  mov     rcx, [rsp+98h+var_38]
0x18002c217  xor     rcx, rsp; StackCookie
0x18002c21a  call    __security_check_cookie
0x18002c21f  lea     r11, [rsp+98h+var_28]
0x18002c224  mov     rbx, [r11+38h]
0x18002c228  mov     rbp, [r11+48h]
0x18002c22c  mov     rsp, r11
0x18002c22f  pop     r15
0x18002c231  pop     r14
0x18002c233  pop     r12
0x18002c235  pop     rdi
0x18002c236  pop     rsi
0x18002c237  retn
```
