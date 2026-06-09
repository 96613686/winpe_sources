# RpcConnect

- ea: `0x180011d34`
- end: `0x180011f74`
- name: `RpcConnect`
- size: `576`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, int, int, int, int, int, RPC_SECURITY_QOS *, int, int, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011440`
- `0x180011590`
- `0x1800119b0`

## callees

- `0x180011d34`
- `0x180014e10`
- `0x1800273d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011e18`
- `msvcrt!_wcsicmp` at `0x180011e59`
- `msvcrt!_wcsicmp` at `0x180011e18`
- `msvcrt!_wcsicmp` at `0x180011e59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011dce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011dce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ead`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180011da6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180011da6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011e9d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011e9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011f2a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011f2a`

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
        RPC_SECURITY_QOS *a10,
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
  unsigned __int16 *nSubAuthority2; // [rsp+20h] [rbp-79h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-71h]
  DWORD nSubAuthority4; // [rsp+30h] [rbp-69h]
  unsigned __int16 *nSubAuthority5; // [rsp+38h] [rbp-61h]
  DWORD nSubAuthority6; // [rsp+40h] [rbp-59h]
  DWORD nSize; // [rsp+60h] [rbp-39h] BYREF
  PSID pSid; // [rsp+68h] [rbp-31h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-29h] BYREF
  WCHAR Buffer[8]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v30; // [rsp+88h] [rbp-11h]

  nSize = 16;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  *(_OWORD *)Buffer = 0;
  v30 = 0;
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
    v16 = _wcsicmp(String1, Buffer);
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
  if ( _wcsicmp(L"RasmanLrpc", L"RasmanLrpc") )
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
                  a10,
                  v20);
    if ( !v17 )
      goto LABEL_28;
    v18 = (void *)g_hBinding;
    goto LABEL_27;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    *(_QWORD *)&a10[2].Version = pSid;
    a10->Capabilities = 17;
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
0x180011d34  mov     [rsp-8+arg_8], rbx
0x180011d39  mov     [rsp-8+arg_10], rsi
0x180011d3e  push    rbp
0x180011d3f  push    rdi
0x180011d40  push    r12
0x180011d42  push    r14
0x180011d44  push    r15
0x180011d46  lea     rbp, [rsp-7]
0x180011d4b  sub     rsp, 0A0h
0x180011d52  mov     rax, cs:__security_cookie
0x180011d59  xor     rax, rsp
0x180011d5c  mov     [rbp+27h+var_28], rax
0x180011d60  mov     rsi, [rbp+27h+Binding]
0x180011d67  xor     r12d, r12d
0x180011d6a  mov     r15, [rbp+27h+arg_48]
0x180011d6e  xorps   xmm0, xmm0
0x180011d71  mov     [rbp+27h+nSize], 10h
0x180011d78  mov     rbx, rcx
0x180011d7b  mov     dword ptr [rbp+27h+pIdentifierAuthority.Value], r12d
0x180011d7f  mov     word ptr [rbp+27h+pIdentifierAuthority.Value+4], 500h
0x180011d85  mov     [rbp+27h+var_58], r12
0x180011d89  movups  xmmword ptr [rbp+27h+Buffer], xmm0
0x180011d8d  movups  [rbp+27h+var_38], xmm0
0x180011d91  test    rsi, rsi
0x180011d94  jnz     short loc_180011D9E
0x180011d96  lea     eax, [rsi+57h]
0x180011d99  jmp     loc_180011F4B
0x180011d9e  lea     rdx, [rbp+27h+nSize]; nSize
0x180011da2  lea     rcx, [rbp+27h+Buffer]; lpBuffer
0x180011da6  call    cs:__imp_GetComputerNameW
0x180011dad  nop     dword ptr [rax+rax+00h]
0x180011db2  test    eax, eax
0x180011db4  jnz     short loc_180011DC7
0x180011db6  call    cs:__imp_GetLastError
0x180011dbd  nop     dword ptr [rax+rax+00h]
0x180011dc2  jmp     loc_180011F4B
0x180011dc7  lea     rcx, g_RpcCs; lpCriticalSection
0x180011dce  call    cs:__imp_EnterCriticalSection
0x180011dd5  nop     dword ptr [rax+rax+00h]
0x180011dda  lea     r14, aRasmanlrpc; "RasmanLrpc"
0x180011de1  test    rbx, rbx
0x180011de4  jz      short loc_180011E36
0x180011de6  cmp     [rbx], r12w
0x180011dea  jz      short loc_180011E36
0x180011dec  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011df0  inc     rax
0x180011df3  cmp     [rbx+rax*2], r12w
0x180011df8  jnz     short loc_180011DF0
0x180011dfa  cmp     rax, 2
0x180011dfe  jbe     short loc_180011E11
0x180011e00  cmp     word ptr [rbx], 5Ch ; '\'
0x180011e04  jnz     short loc_180011E11
0x180011e06  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180011e0b  jnz     short loc_180011E11
0x180011e0d  add     rbx, 4
0x180011e11  lea     rdx, [rbp+27h+Buffer]; String2
0x180011e15  mov     rcx, rbx; String1
0x180011e18  call    cs:__imp__wcsicmp
0x180011e1f  nop     dword ptr [rax+rax+00h]
0x180011e24  test    eax, eax
0x180011e26  mov     edi, r12d
0x180011e29  setz    dil
0x180011e2d  test    eax, eax
0x180011e2f  jz      short loc_180011E3F
0x180011e31  jmp     loc_180011ECD
0x180011e36  lea     rbx, [rbp+27h+Buffer]
0x180011e3a  mov     edi, 1
0x180011e3f  mov     rax, cs:g_hBinding
0x180011e46  test    rax, rax
0x180011e49  jz      short loc_180011E53
0x180011e4b  mov     ebx, r12d
0x180011e4e  jmp     loc_180011F18
0x180011e53  mov     rdx, r14; String2
0x180011e56  mov     rcx, r14; String1
0x180011e59  call    cs:__imp__wcsicmp
0x180011e60  nop     dword ptr [rax+rax+00h]
0x180011e65  test    eax, eax
0x180011e67  jnz     short loc_180011ECD
0x180011e69  lea     rax, [rbp+27h+var_58]
0x180011e6d  xor     r9d, r9d; nSubAuthority1
0x180011e70  mov     [rsp+0C0h+pSid], rax; pSid
0x180011e75  lea     rcx, [rbp+27h+pIdentifierAuthority]; pIdentifierAuthority
0x180011e79  mov     [rsp+0C0h+nSubAuthority7], r12d; nSubAuthority7
0x180011e7e  mov     dl, 1; nSubAuthorityCount
0x180011e80  mov     [rsp+0C0h+nSubAuthority6], r12d; int
0x180011e85  mov     dword ptr [rsp+0C0h+nSubAuthority5], r12d; RPC_WSTR
0x180011e8a  lea     r8d, [r9+12h]; nSubAuthority0
0x180011e8e  mov     [rsp+0C0h+nSubAuthority4], r12d; int
0x180011e93  mov     [rsp+0C0h+nSubAuthority3], r12d; int
0x180011e98  mov     dword ptr [rsp+0C0h+nSubAuthority2], r12d; ServerPrincName
0x180011e9d  call    cs:__imp_AllocateAndInitializeSid
0x180011ea4  nop     dword ptr [rax+rax+00h]
0x180011ea9  test    eax, eax
0x180011eab  jnz     short loc_180011EBD
0x180011ead  call    cs:__imp_GetLastError
0x180011eb4  nop     dword ptr [rax+rax+00h]
0x180011eb9  mov     ebx, eax
0x180011ebb  jmp     short loc_180011F21
0x180011ebd  mov     rax, [rbp+27h+var_58]
0x180011ec1  mov     [r15+20h], rax
0x180011ec5  mov     dword ptr [r15+4], 11h
0x180011ecd  test    edi, edi
0x180011ecf  lea     rax, g_hBinding
0x180011ed6  cmovz   rax, rsi
0x180011eda  jz      short loc_180011EE8
0x180011edc  lea     r8, aNcalrpc; "ncalrpc"
0x180011ee3  mov     rbx, r12
0x180011ee6  jmp     short loc_180011EF6
0x180011ee8  lea     r14, aPipeRouter; "\\PIPE\\ROUTER"
0x180011eef  lea     r8, aNcacnNp; "ncacn_np"
0x180011ef6  mov     [rsp+0C0h+pSid], rax; Binding
0x180011efb  mov     r9, r14
0x180011efe  mov     rcx, rbx; NetworkAddr
0x180011f01  mov     qword ptr [rsp+0C0h+nSubAuthority7], r15; RPC_SECURITY_QOS *
0x180011f06  call    RPCBind
0x180011f0b  mov     ebx, eax
0x180011f0d  test    edi, edi
0x180011f0f  jz      short loc_180011F21
0x180011f11  mov     rax, cs:g_hBinding
0x180011f18  inc     cs:g_dwRefCount
0x180011f1e  mov     [rsi], rax
0x180011f21  mov     rcx, [rbp+27h+var_58]; pSid
0x180011f25  test    rcx, rcx
0x180011f28  jz      short loc_180011F36
0x180011f2a  call    cs:__imp_FreeSid
0x180011f31  nop     dword ptr [rax+rax+00h]
0x180011f36  lea     rcx, g_RpcCs; lpCriticalSection
0x180011f3d  call    cs:__imp_LeaveCriticalSection
0x180011f44  nop     dword ptr [rax+rax+00h]
0x180011f49  mov     eax, ebx
0x180011f4b  mov     rcx, [rbp+27h+var_28]
0x180011f4f  xor     rcx, rsp; StackCookie
0x180011f52  call    __security_check_cookie
0x180011f57  lea     r11, [rsp+0C0h+var_20]
0x180011f5f  mov     rbx, [r11+38h]
0x180011f63  mov     rsi, [r11+40h]
0x180011f67  mov     rsp, r11
0x180011f6a  pop     r15
0x180011f6c  pop     r14
0x180011f6e  pop     r12
0x180011f70  pop     rdi
0x180011f71  pop     rbp
0x180011f72  retn
```
