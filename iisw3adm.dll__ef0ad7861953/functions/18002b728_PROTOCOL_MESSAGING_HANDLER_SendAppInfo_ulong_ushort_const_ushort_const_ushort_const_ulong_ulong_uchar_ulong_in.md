# PROTOCOL_MESSAGING_HANDLER::SendAppInfo(ulong,ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *,ulong,int)

- ea: `0x18002b728`
- end: `0x18002b98b`
- name: `?SendAppInfo@PROTOCOL_MESSAGING_HANDLER@@QEAAJKPEBG00KKPEAEKH@Z`
- size: `611`
- prototype: `__int64 __fastcall(PROTOCOL_MESSAGING_HANDLER *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, size_t Size, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c930`

## callees

- `0x18002b728`
- `0x18002c2f4`
- `0x180061002`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b84a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b84a`
- `iisutil!PuDbgPrint` at `0x18002b825`
- `iisutil!PuDbgPrint` at `0x18002b825`
- `iisutil!PuDbgPrintError` at `0x18002b952`
- `iisutil!PuDbgPrintError` at `0x18002b952`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b95c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b95c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b840`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002b840`

## string_xrefs

- `0x18002b81e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b947`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002b805`: `PROTOCOL_MESSAGING_HANDLER::SendAppInfo called \n`
- `0x18002b80c`: `PROTOCOL_MESSAGING_HANDLER::SendAppInfo`
- `0x18002b93b`: `PROTOCOL_MESSAGING_HANDLER::SendAppInfo`
- `0x18002b927`: `Failed copying data into buffer to send\n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::SendAppInfo(
        PROTOCOL_MESSAGING_HANDLER *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int8 *a8,
        size_t Size,
        int a10)
{
  __int64 v11; // rax
  __int64 v12; // rcx
  size_t v13; // rbx
  __int64 v14; // rcx
  unsigned int v15; // r14d
  unsigned int v16; // r12d
  int v17; // eax
  unsigned int v18; // esi
  signed int LastError; // eax
  int v20; // ebx
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  char *v23; // rdi
  char *v24; // rdi
  char *v25; // rdi
  _QWORD v30[4]; // [rsp+58h] [rbp-31h] BYREF
  _DWORD *v31; // [rsp+78h] [rbp-11h]
  int v32; // [rsp+80h] [rbp-9h]
  __int16 v33; // [rsp+84h] [rbp-5h]

  v31 = v30;
  v11 = -1;
  v12 = -1;
  v30[0] = 0;
  v32 = 32;
  v33 = 256;
  do
    ++v12;
  while ( a3[v12] );
  v13 = (unsigned int)(2 * v12 + 2);
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  v15 = 2 * v14 + 2;
  do
    ++v11;
  while ( a5[v11] );
  v16 = 2 * v11 + 2;
  v17 = ((_BYTE)v13 + 2 * (_BYTE)v11 + 2 + (_BYTE)v15) & 3;
  v18 = 4 - v17;
  if ( !v17 )
    v18 = 0;
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      1625,
      "PROTOCOL_MESSAGING_HANDLER::SendAppInfo",
      "PROTOCOL_MESSAGING_HANDLER::SendAppInfo called \n");
  if ( BUFFER::Resize((BUFFER *)v30, Size + v13 + v15 + v18 + v16 + 20) )
  {
    v21 = v31;
    *v31 = a2;
    v22 = v21 + 1;
    memcpy_0(v21 + 1, a3, v13);
    v23 = (char *)v22 + v13;
    memcpy_0(v23, a4, v15);
    v24 = &v23[v15];
    memcpy_0(v24, a5, v16);
    v25 = &v24[v16];
    if ( v18 )
    {
      memset_0(v25, 0, v18);
      v25 += v18;
    }
    *(_DWORD *)v25 = a6;
    *((_DWORD *)v25 + 1) = a10;
    *((_DWORD *)v25 + 2) = a7;
    *((_DWORD *)v25 + 3) = Size;
    memcpy_0(v25 + 16, a8, (unsigned int)Size);
    v20 = PROTOCOL_MESSAGING_HANDLER::SendMessageW((__int64)this, 32);
    if ( v20 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        1713,
        "PROTOCOL_MESSAGING_HANDLER::SendAppInfo",
        v20,
        "Failed copying data into buffer to send\n");
  }
  else
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        1660,
        "PROTOCOL_MESSAGING_HANDLER::SendAppInfo",
        v20,
        "Failed resizing the buffer to send data\n");
  }
  BUFFER::~BUFFER((BUFFER *)v30);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18002b728  mov     [rsp-8+arg_8], rbx
0x18002b72d  push    rbp
0x18002b72e  push    rsi
0x18002b72f  push    rdi
0x18002b730  push    r12
0x18002b732  push    r13
0x18002b734  push    r14
0x18002b736  push    r15
0x18002b738  lea     rbp, [rsp-7]
0x18002b73d  sub     rsp, 90h
0x18002b744  mov     rax, cs:__security_cookie
0x18002b74b  xor     rax, rsp
0x18002b74e  mov     [rbp+37h+var_38], rax
0x18002b752  mov     rax, [rbp+37h+arg_38]
0x18002b756  xor     r10d, r10d
0x18002b759  mov     r13d, dword ptr [rbp+37h+Size]
0x18002b760  mov     edi, edx
0x18002b762  mov     rdx, [rbp+37h+arg_20]
0x18002b766  mov     [rbp+37h+var_78], rax
0x18002b76a  lea     rax, [rbp+37h+var_68]
0x18002b76e  mov     [rbp+37h+var_48], rax
0x18002b772  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b776  mov     [rbp+37h+var_70], rcx
0x18002b77a  mov     rcx, rax
0x18002b77d  mov     [rbp+37h+var_88], r9
0x18002b781  mov     [rbp+37h+Src], r8
0x18002b785  mov     [rbp+37h+var_80], rdx
0x18002b789  mov     [rbp+37h+var_68], r10
0x18002b78d  mov     [rbp+37h+var_40], 20h ; ' '
0x18002b794  mov     [rbp+37h+var_3C], 100h
0x18002b79a  inc     rcx
0x18002b79d  cmp     [r8+rcx*2], r10w
0x18002b7a2  jnz     short loc_18002B79A
0x18002b7a4  lea     ebx, ds:2[rcx*2]
0x18002b7ab  mov     rcx, rax
0x18002b7ae  inc     rcx
0x18002b7b1  cmp     [r9+rcx*2], r10w
0x18002b7b6  jnz     short loc_18002B7AE
0x18002b7b8  lea     r14d, ds:2[rcx*2]
0x18002b7c0  inc     rax
0x18002b7c3  cmp     [rdx+rax*2], r10w
0x18002b7c8  jnz     short loc_18002B7C0
0x18002b7ca  lea     r12d, ds:2[rax*2]
0x18002b7d2  mov     esi, 4
0x18002b7d7  lea     eax, [r12+r14]
0x18002b7db  add     eax, ebx
0x18002b7dd  and     eax, 3
0x18002b7e0  sub     esi, eax
0x18002b7e2  test    eax, eax
0x18002b7e4  cmovz   esi, eax
0x18002b7e7  mov     eax, cs:g_dwDebugFlags
0x18002b7ed  test    eax, 210000h
0x18002b7f2  setnz   cl
0x18002b7f5  test    al, 3
0x18002b7f7  setnz   al
0x18002b7fa  test    al, cl
0x18002b7fc  jz      short loc_18002B82B
0x18002b7fe  mov     rcx, cs:g_pDebug
0x18002b805  lea     rax, aProtocolMessag_47; "PROTOCOL_MESSAGING_HANDLER::SendAppInfo"...
0x18002b80c  lea     r9, aProtocolMessag_7; "PROTOCOL_MESSAGING_HANDLER::SendAppInfo"
0x18002b813  mov     [rsp+0C0h+var_A0], rax
0x18002b818  mov     r8d, 659h
0x18002b81e  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b825  call    cs:__imp_PuDbgPrint
0x18002b82b  lea     r15d, [rsi+r12]
0x18002b82f  add     r15d, r14d
0x18002b832  lea     rcx, [rbp+37h+var_68]
0x18002b836  add     r15d, ebx
0x18002b839  add     r15d, r13d
0x18002b83c  lea     edx, [r15+14h]
0x18002b840  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002b846  test    al, al
0x18002b848  jnz     short loc_18002B87E
0x18002b84a  call    cs:__imp_GetLastError
0x18002b850  mov     ebx, eax
0x18002b852  test    eax, eax
0x18002b854  jle     short loc_18002B85F
0x18002b856  movzx   ebx, ax
0x18002b859  or      ebx, 80070000h
0x18002b85f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b866  jz      loc_18002B958
0x18002b86c  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x18002b873  mov     r8d, 67Ch
0x18002b879  jmp     loc_18002B934
0x18002b87e  mov     rax, [rbp+37h+var_48]
0x18002b882  mov     r8, rbx; Size
0x18002b885  mov     rdx, [rbp+37h+Src]; Src
0x18002b889  mov     [rax], edi
0x18002b88b  lea     rdi, [rax+4]
0x18002b88f  mov     rcx, rdi; void *
0x18002b892  call    memcpy_0
0x18002b897  mov     rdx, [rbp+37h+var_88]; Src
0x18002b89b  add     rdi, rbx
0x18002b89e  mov     rcx, rdi; void *
0x18002b8a1  mov     r8d, r14d; Size
0x18002b8a4  mov     ebx, r14d
0x18002b8a7  call    memcpy_0
0x18002b8ac  mov     rdx, [rbp+37h+var_80]; Src
0x18002b8b0  add     rdi, rbx
0x18002b8b3  mov     rcx, rdi; void *
0x18002b8b6  mov     r8d, r12d; Size
0x18002b8b9  mov     ebx, r12d
0x18002b8bc  call    memcpy_0
0x18002b8c1  add     rdi, rbx
0x18002b8c4  test    esi, esi
0x18002b8c6  jz      short loc_18002B8DA
0x18002b8c8  mov     r8d, esi; Size
0x18002b8cb  xor     edx, edx; Val
0x18002b8cd  mov     rcx, rdi; void *
0x18002b8d0  mov     ebx, esi
0x18002b8d2  call    memset_0
0x18002b8d7  add     rdi, rbx
0x18002b8da  mov     eax, [rbp+37h+arg_28]
0x18002b8dd  lea     rcx, [rdi+10h]; void *
0x18002b8e1  mov     rdx, [rbp+37h+var_78]; Src
0x18002b8e5  mov     r8, r13; Size
0x18002b8e8  mov     [rdi], eax
0x18002b8ea  mov     eax, [rbp+37h+arg_48]
0x18002b8f0  mov     [rdi+4], eax
0x18002b8f3  mov     eax, [rbp+37h+arg_30]
0x18002b8f6  mov     [rdi+8], eax
0x18002b8f9  mov     [rdi+0Ch], r13d
0x18002b8fd  call    memcpy_0
0x18002b902  mov     r9, [rbp+37h+var_48]
0x18002b906  lea     r8d, [r15+14h]
0x18002b90a  mov     rcx, [rbp+37h+var_70]
0x18002b90e  mov     edx, 20h ; ' '
0x18002b913  call    ?SendMessageW@PROTOCOL_MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; PROTOCOL_MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002b918  mov     ebx, eax
0x18002b91a  test    eax, eax
0x18002b91c  jns     short loc_18002B958
0x18002b91e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002b925  jz      short loc_18002B958
0x18002b927  lea     rax, aFailedCopyingD; "Failed copying data into buffer to send"...
0x18002b92e  mov     r8d, 6B1h
0x18002b934  mov     rcx, cs:g_pDebug
0x18002b93b  lea     r9, aProtocolMessag_7; "PROTOCOL_MESSAGING_HANDLER::SendAppInfo"
0x18002b942  mov     [rsp+0C0h+var_98], rax
0x18002b947  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b94e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18002b952  call    cs:__imp_PuDbgPrintError
0x18002b958  lea     rcx, [rbp+37h+var_68]
0x18002b95c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b962  mov     eax, ebx
0x18002b964  mov     rcx, [rbp+37h+var_38]
0x18002b968  xor     rcx, rsp; StackCookie
0x18002b96b  call    __security_check_cookie
0x18002b970  mov     rbx, [rsp+0C0h+arg_8]
0x18002b978  add     rsp, 90h
0x18002b97f  pop     r15
0x18002b981  pop     r14
0x18002b983  pop     r13
0x18002b985  pop     r12
0x18002b987  pop     rdi
0x18002b988  pop     rsi
0x18002b989  pop     rbp
0x18002b98a  retn
```
