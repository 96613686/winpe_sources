# RpcConnect

- ea: `0x1800401b8`
- end: `0x1800403ad`
- name: `RpcConnect`
- size: `501`
- prototype: `DWORD __fastcall(wchar_t *String1, __int64, __int64, __int64, int, int, int, int, int, int, int, int, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006c60`
- `0x180007330`

## callees

- `0x180001706`
- `0x18003fff4`
- `0x1800401b8`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040389`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040389`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040303`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800402f9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800402f9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004037c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004037c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18004021d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18004021d`

## string_xrefs

- `0x18004023f`: `RemoteAccessLrpc`

## pseudocode

```c
DWORD __fastcall RpcConnect(
        wchar_t *String1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        RPC_BINDING_HANDLE *Binding)
{
  unsigned __int64 v15; // rax
  int v16; // eax
  BOOL v17; // edi
  void *v18; // rax
  DWORD LastError; // ebx
  RPC_BINDING_HANDLE *v20; // rax
  unsigned __int16 *nSubAuthority2; // [rsp+20h] [rbp-81h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-79h]
  DWORD nSubAuthority4; // [rsp+30h] [rbp-71h]
  DWORD nSubAuthority5; // [rsp+38h] [rbp-69h]
  DWORD nSubAuthority6; // [rsp+40h] [rbp-61h]
  DWORD nSubAuthority7; // [rsp+48h] [rbp-59h]
  DWORD nSize; // [rsp+60h] [rbp-41h] BYREF
  PSID pSid; // [rsp+68h] [rbp-39h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-31h] BYREF
  WCHAR Buffer[8]; // [rsp+78h] [rbp-29h] BYREF
  __int128 v31; // [rsp+88h] [rbp-19h]

  nSize = 16;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  *(_OWORD *)Buffer = 0;
  v31 = 0;
  if ( !Binding )
    return 87;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return GetLastError();
  EnterCriticalSection(&g_RpcCs);
  if ( String1 && *String1 )
  {
    v15 = -1;
    do
      ++v15;
    while ( String1[v15] );
    if ( v15 > 2 && *String1 == 92 && String1[1] == 92 )
      String1 += 2;
    v16 = wcsicmp_0(String1, Buffer);
    v17 = v16 == 0;
    if ( v16 )
      goto LABEL_22;
  }
  else
  {
    String1 = Buffer;
    v17 = 1;
  }
  v18 = (void *)g_hBinding;
  if ( g_hBinding )
  {
    LastError = 0;
LABEL_27:
    ++g_dwRefCount;
    *Binding = v18;
    goto LABEL_28;
  }
  if ( wcsicmp_0(L"RemoteAccessLrpc", L"RasmanLrpc") )
  {
LABEL_22:
    v20 = (RPC_BINDING_HANDLE *)&g_hBinding;
    if ( v17 )
      String1 = 0;
    else
      v20 = Binding;
    LastError = RPCBind(
                  String1,
                  nSubAuthority2,
                  nSubAuthority3,
                  nSubAuthority4,
                  nSubAuthority5,
                  nSubAuthority6,
                  nSubAuthority7,
                  v20);
    if ( !v17 )
      goto LABEL_28;
    v18 = (void *)g_hBinding;
    goto LABEL_27;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    MEMORY[0x20] = pSid;
    MEMORY[4] = 17;
    goto LABEL_22;
  }
  LastError = GetLastError();
LABEL_28:
  if ( pSid )
    FreeSid(pSid);
  LeaveCriticalSection(&g_RpcCs);
  return LastError;
}

```

## disassembly

```asm
0x1800401b8  push    rbp
0x1800401ba  push    rbx
0x1800401bb  push    rsi
0x1800401bc  push    rdi
0x1800401bd  push    r14
0x1800401bf  push    r15
0x1800401c1  lea     rbp, [rsp-7]
0x1800401c6  sub     rsp, 0A8h
0x1800401cd  mov     rax, cs:__security_cookie
0x1800401d4  xor     rax, rsp
0x1800401d7  mov     [rbp+2Fh+var_38], rax
0x1800401db  mov     rsi, [rbp+2Fh+Binding]
0x1800401e2  xor     r15d, r15d
0x1800401e5  mov     [rbp+2Fh+nSize], 10h
0x1800401ec  xorps   xmm0, xmm0
0x1800401ef  mov     dword ptr [rbp+2Fh+pIdentifierAuthority.Value], r15d
0x1800401f3  mov     rbx, rcx
0x1800401f6  mov     word ptr [rbp+2Fh+pIdentifierAuthority.Value+4], 500h
0x1800401fc  mov     [rbp+2Fh+var_68], r15
0x180040200  movups  xmmword ptr [rbp+2Fh+Buffer], xmm0
0x180040204  movups  [rbp+2Fh+var_48], xmm0
0x180040208  test    rsi, rsi
0x18004020b  jnz     short loc_180040215
0x18004020d  lea     eax, [rsi+57h]
0x180040210  jmp     loc_180040391
0x180040215  lea     rdx, [rbp+2Fh+nSize]; nSize
0x180040219  lea     rcx, [rbp+2Fh+Buffer]; lpBuffer
0x18004021d  call    cs:__imp_GetComputerNameW
0x180040223  test    eax, eax
0x180040225  jnz     short loc_180040232
0x180040227  call    cs:__imp_GetLastError
0x18004022d  jmp     loc_180040391
0x180040232  lea     rcx, g_RpcCs; lpCriticalSection
0x180040239  call    cs:__imp_EnterCriticalSection
0x18004023f  lea     r14, aRemoteaccesslr; "RemoteAccessLrpc"
0x180040246  test    rbx, rbx
0x180040249  jz      short loc_180040295
0x18004024b  cmp     [rbx], r15w
0x18004024f  jz      short loc_180040295
0x180040251  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040255  inc     rax
0x180040258  cmp     [rbx+rax*2], r15w
0x18004025d  jnz     short loc_180040255
0x18004025f  cmp     rax, 2
0x180040263  jbe     short loc_180040276
0x180040265  cmp     word ptr [rbx], 5Ch ; '\'
0x180040269  jnz     short loc_180040276
0x18004026b  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180040270  jnz     short loc_180040276
0x180040272  add     rbx, 4
0x180040276  lea     rdx, [rbp+2Fh+Buffer]; String2
0x18004027a  mov     rcx, rbx; String1
0x18004027d  call    _wcsicmp_0
0x180040282  test    eax, eax
0x180040284  mov     edi, r15d
0x180040287  setz    dil
0x18004028b  test    eax, eax
0x18004028d  jnz     loc_180040324
0x180040293  jmp     short loc_18004029E
0x180040295  lea     rbx, [rbp+2Fh+Buffer]
0x180040299  mov     edi, 1
0x18004029e  mov     rax, cs:g_hBinding
0x1800402a5  test    rax, rax
0x1800402a8  jz      short loc_1800402B2
0x1800402aa  mov     ebx, r15d
0x1800402ad  jmp     loc_18004036A
0x1800402b2  lea     rdx, aRasmanlrpc; "RasmanLrpc"
0x1800402b9  mov     rcx, r14; String1
0x1800402bc  call    _wcsicmp_0
0x1800402c1  test    eax, eax
0x1800402c3  jnz     short loc_180040324
0x1800402c5  lea     rax, [rbp+2Fh+var_68]
0x1800402c9  xor     r9d, r9d; nSubAuthority1
0x1800402cc  mov     [rsp+0D0h+pSid], rax; pSid
0x1800402d1  lea     rcx, [rbp+2Fh+pIdentifierAuthority]; pIdentifierAuthority
0x1800402d5  mov     [rsp+0D0h+nSubAuthority7], r15d; int
0x1800402da  mov     dl, 1; nSubAuthorityCount
0x1800402dc  mov     [rsp+0D0h+nSubAuthority6], r15d; int
0x1800402e1  mov     [rsp+0D0h+nSubAuthority5], r15d; int
0x1800402e6  lea     r8d, [r9+12h]; nSubAuthority0
0x1800402ea  mov     [rsp+0D0h+nSubAuthority4], r15d; int
0x1800402ef  mov     [rsp+0D0h+nSubAuthority3], r15d; int
0x1800402f4  mov     dword ptr [rsp+0D0h+nSubAuthority2], r15d; RPC_WSTR
0x1800402f9  call    cs:__imp_AllocateAndInitializeSid
0x1800402ff  test    eax, eax
0x180040301  jnz     short loc_18004030D
0x180040303  call    cs:__imp_GetLastError
0x180040309  mov     ebx, eax
0x18004030b  jmp     short loc_180040373
0x18004030d  mov     rax, [rbp+2Fh+var_68]
0x180040311  mov     ds:20h, rax
0x180040319  mov     dword ptr ds:4, 11h
0x180040324  test    edi, edi
0x180040326  lea     rax, g_hBinding
0x18004032d  cmovz   rax, rsi
0x180040331  jz      short loc_18004033F
0x180040333  lea     r8, aNcalrpc; "ncalrpc"
0x18004033a  mov     rbx, r15
0x18004033d  jmp     short loc_18004034D
0x18004033f  lea     r14, aPipeRouter; "\\PIPE\\ROUTER"
0x180040346  lea     r8, aNcacnNp; "ncacn_np"
0x18004034d  mov     r9, r14
0x180040350  mov     [rsp+0D0h+pSid], rax; Binding
0x180040355  mov     rcx, rbx; ServerPrincName
0x180040358  call    RPCBind
0x18004035d  mov     ebx, eax
0x18004035f  test    edi, edi
0x180040361  jz      short loc_180040373
0x180040363  mov     rax, cs:g_hBinding
0x18004036a  inc     cs:g_dwRefCount
0x180040370  mov     [rsi], rax
0x180040373  mov     rcx, [rbp+2Fh+var_68]; pSid
0x180040377  test    rcx, rcx
0x18004037a  jz      short loc_180040382
0x18004037c  call    cs:__imp_FreeSid
0x180040382  lea     rcx, g_RpcCs; lpCriticalSection
0x180040389  call    cs:__imp_LeaveCriticalSection
0x18004038f  mov     eax, ebx
0x180040391  mov     rcx, [rbp+2Fh+var_38]
0x180040395  xor     rcx, rsp; StackCookie
0x180040398  call    __security_check_cookie
0x18004039d  add     rsp, 0A8h
0x1800403a4  pop     r15
0x1800403a6  pop     r14
0x1800403a8  pop     rdi
0x1800403a9  pop     rsi
0x1800403aa  pop     rbx
0x1800403ab  pop     rbp
0x1800403ac  retn
```
