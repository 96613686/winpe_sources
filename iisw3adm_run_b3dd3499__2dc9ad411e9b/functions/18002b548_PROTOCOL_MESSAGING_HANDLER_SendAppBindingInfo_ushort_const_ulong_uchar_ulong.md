# PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo(ushort const *,ulong,uchar *,ulong)

- ea: `0x18002b548`
- end: `0x18002b720`
- name: `?SendAppBindingInfo@PROTOCOL_MESSAGING_HANDLER@@QEAAJPEBGKPEAEK@Z`
- size: `472`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cac0`

## callees

- `0x18002b548`
- `0x18002c2f4`
- `0x180061002`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b623`
- `iisutil!PuDbgPrint` at `0x18002b603`
- `iisutil!PuDbgPrint` at `0x18002b603`
- `iisutil!PuDbgPrintError` at `0x18002b6e8`
- `iisutil!PuDbgPrintError` at `0x18002b6e8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b6f3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b6f3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b619`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b619`

## string_xrefs

- `0x18002b5fc`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b6dd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b6bd`: `Failed copying data into buffer to send\n`
- `0x18002b5e3`: `PROTOCOL_MESSAGING_HANDLER::SendNewBindings called \n`
- `0x18002b5ea`: `PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo`
- `0x18002b6d1`: `PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo(
        PROTOCOL_MESSAGING_HANDLER *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  __int64 v5; // rax
  size_t v9; // rbx
  int v10; // eax
  unsigned int v11; // esi
  signed int LastError; // eax
  int v13; // ebx
  char *v14; // rdi
  char *v15; // rdi
  _QWORD v18[4]; // [rsp+38h] [rbp-70h] BYREF
  void *v19; // [rsp+58h] [rbp-50h]
  int v20; // [rsp+60h] [rbp-48h]
  __int16 v21; // [rsp+64h] [rbp-44h]

  v19 = v18;
  v18[0] = 0;
  v5 = -1;
  v20 = 32;
  v21 = 256;
  do
    ++v5;
  while ( a2[v5] );
  v9 = (unsigned int)(2 * v5 + 2);
  v10 = (2 * (_BYTE)v5 + 2) & 3;
  v11 = 4 - v10;
  if ( !v10 )
    v11 = 0;
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      1857,
      "PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo",
      "PROTOCOL_MESSAGING_HANDLER::SendNewBindings called \n");
  if ( BUFFER::Resize((BUFFER *)v18, Size + v11 + v9 + 8) )
  {
    v14 = (char *)v19;
    memcpy_0(v19, a2, v9);
    v15 = &v14[v9];
    if ( v11 )
    {
      memset_0(v15, 0, v11);
      v15 += v11;
    }
    *(_DWORD *)v15 = a3;
    *((_DWORD *)v15 + 1) = Size;
    memcpy_0(v15 + 8, a4, Size);
    v13 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 44);
    if ( v13 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        1920,
        "PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo",
        v13,
        "Failed copying data into buffer to send\n");
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        1882,
        "PROTOCOL_MESSAGING_HANDLER::SendAppBindingInfo",
        v13,
        "Failed resizing the buffer to send data\n");
  }
  BUFFER::~BUFFER((BUFFER *)v18);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002b548  mov     r11, rsp
0x18002b54b  mov     [r11+18h], rbx
0x18002b54f  push    rbp
0x18002b550  push    rsi
0x18002b551  push    rdi
0x18002b552  push    r12
0x18002b554  push    r13
0x18002b556  push    r14
0x18002b558  push    r15
0x18002b55a  sub     rsp, 70h
0x18002b55e  mov     rax, cs:__security_cookie
0x18002b565  xor     rax, rsp
0x18002b568  mov     [rsp+0A8h+var_40], rax
0x18002b56d  mov     r14d, dword ptr [rsp+0A8h+Size]
0x18002b575  lea     rax, [r11-70h]
0x18002b579  mov     [r11-50h], rax
0x18002b57d  xor     edi, edi
0x18002b57f  mov     [r11-70h], rdi
0x18002b583  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b587  mov     [rsp+0A8h+var_48], 20h ; ' '
0x18002b58f  mov     r12d, r8d
0x18002b592  mov     [rsp+0A8h+var_44], 100h
0x18002b599  mov     rbp, rdx
0x18002b59c  mov     [rsp+0A8h+Src], r9
0x18002b5a1  mov     r13, rcx
0x18002b5a4  inc     rax
0x18002b5a7  cmp     [rdx+rax*2], di
0x18002b5ab  jnz     short loc_18002B5A4
0x18002b5ad  lea     ebx, ds:2[rax*2]
0x18002b5b4  mov     esi, 4
0x18002b5b9  mov     eax, ebx
0x18002b5bb  and     eax, 3
0x18002b5be  sub     esi, eax
0x18002b5c0  test    eax, eax
0x18002b5c2  cmovz   esi, eax
0x18002b5c5  mov     eax, cs:g_dwDebugFlags
0x18002b5cb  test    eax, 210000h
0x18002b5d0  setnz   cl
0x18002b5d3  test    al, 3
0x18002b5d5  setnz   al
0x18002b5d8  test    al, cl
0x18002b5da  jz      short loc_18002B609
0x18002b5dc  mov     rcx, cs:g_pDebug
0x18002b5e3  lea     rax, aProtocolMessag_28; "PROTOCOL_MESSAGING_HANDLER::SendNewBind"...
0x18002b5ea  lea     r9, aProtocolMessag_49; "PROTOCOL_MESSAGING_HANDLER::SendAppBind"...
0x18002b5f1  mov     [rsp+0A8h+var_88], rax
0x18002b5f6  mov     r8d, 741h
0x18002b5fc  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b603  call    cs:__imp_PuDbgPrint
0x18002b609  lea     r15d, [rsi+rbx]
0x18002b60d  add     r15d, r14d
0x18002b610  lea     rcx, [rsp+0A8h+var_70]
0x18002b615  lea     edx, [r15+8]
0x18002b619  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002b61f  test    al, al
0x18002b621  jnz     short loc_18002B654
0x18002b623  call    cs:__imp_GetLastError
0x18002b629  mov     ebx, eax
0x18002b62b  test    eax, eax
0x18002b62d  jle     short loc_18002B638
0x18002b62f  movzx   ebx, ax
0x18002b632  or      ebx, 80070000h
0x18002b638  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b63f  jz      loc_18002B6EE
0x18002b645  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002b64c  mov     r8d, 75Ah
0x18002b652  jmp     short loc_18002B6CA
0x18002b654  mov     rdi, [rsp+0A8h+var_50]
0x18002b659  mov     r8, rbx; Size
0x18002b65c  mov     rcx, rdi; void *
0x18002b65f  mov     rdx, rbp; Src
0x18002b662  call    memcpy_0
0x18002b667  add     rdi, rbx
0x18002b66a  test    esi, esi
0x18002b66c  jz      short loc_18002B680
0x18002b66e  mov     r8d, esi; Size
0x18002b671  xor     edx, edx; Val
0x18002b673  mov     rcx, rdi; void *
0x18002b676  mov     ebx, esi
0x18002b678  call    memset_0
0x18002b67d  add     rdi, rbx
0x18002b680  mov     rdx, [rsp+0A8h+Src]; Src
0x18002b685  lea     rcx, [rdi+8]; void *
0x18002b689  mov     [rdi], r12d
0x18002b68c  mov     r8, r14; Size
0x18002b68f  mov     [rdi+4], r14d
0x18002b693  call    memcpy_0
0x18002b698  mov     r9, [rsp+0A8h+var_50]
0x18002b69d  lea     r8d, [r15+8]
0x18002b6a1  mov     edx, 2Ch ; ','
0x18002b6a6  mov     rcx, r13
0x18002b6a9  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002b6ae  mov     ebx, eax
0x18002b6b0  test    eax, eax
0x18002b6b2  jns     short loc_18002B6EE
0x18002b6b4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b6bb  jz      short loc_18002B6EE
0x18002b6bd  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002b6c4  mov     r8d, 780h
0x18002b6ca  mov     rcx, cs:g_pDebug
0x18002b6d1  lea     r9, aProtocolMessag_49; "PROTOCOL_MESSAGING_HANDLER::SendAppBind"...
0x18002b6d8  mov     [rsp+0A8h+var_80], rax
0x18002b6dd  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b6e4  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18002b6e8  call    cs:__imp_PuDbgPrintError
0x18002b6ee  lea     rcx, [rsp+0A8h+var_70]
0x18002b6f3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b6f9  mov     eax, ebx
0x18002b6fb  mov     rcx, [rsp+0A8h+var_40]
0x18002b700  xor     rcx, rsp; StackCookie
0x18002b703  call    __security_check_cookie
0x18002b708  mov     rbx, [rsp+0A8h+arg_10]
0x18002b710  add     rsp, 70h
0x18002b714  pop     r15
0x18002b716  pop     r14
0x18002b718  pop     r13
0x18002b71a  pop     r12
0x18002b71c  pop     rdi
0x18002b71d  pop     rsi
0x18002b71e  pop     rbp
0x18002b71f  retn
```
