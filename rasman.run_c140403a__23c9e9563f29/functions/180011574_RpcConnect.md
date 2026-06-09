# RpcConnect

- ea: `0x180011574`
- end: `0x18001177d`
- name: `RpcConnect`
- size: `521`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, int, int, int, int, int, RPC_SECURITY_QOS *, int, int, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010cc0`
- `0x180010e00`
- `0x180011200`

## callees

- `0x180011574`
- `0x1800144e0`
- `0x180026400`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011646`
- `msvcrt!_wcsicmp` at `0x180011681`
- `msvcrt!_wcsicmp` at `0x180011646`
- `msvcrt!_wcsicmp` at `0x180011681`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001174d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001174d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116c9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800115e6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800115e6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800116bf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800116bf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011740`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011740`

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
0x180011574  mov     [rsp-8+arg_8], rbx
0x180011579  mov     [rsp-8+arg_10], rsi
0x18001157e  push    rbp
0x18001157f  push    rdi
0x180011580  push    r12
0x180011582  push    r14
0x180011584  push    r15
0x180011586  lea     rbp, [rsp-7]
0x18001158b  sub     rsp, 0A0h
0x180011592  mov     rax, cs:__security_cookie
0x180011599  xor     rax, rsp
0x18001159c  mov     [rbp+27h+var_28], rax
0x1800115a0  mov     rsi, [rbp+27h+Binding]
0x1800115a7  xor     r12d, r12d
0x1800115aa  mov     r15, [rbp+27h+arg_48]
0x1800115ae  xorps   xmm0, xmm0
0x1800115b1  mov     [rbp+27h+nSize], 10h
0x1800115b8  mov     rbx, rcx
0x1800115bb  mov     dword ptr [rbp+27h+pIdentifierAuthority.Value], r12d
0x1800115bf  mov     word ptr [rbp+27h+pIdentifierAuthority.Value+4], 500h
0x1800115c5  mov     [rbp+27h+var_58], r12
0x1800115c9  movups  xmmword ptr [rbp+27h+Buffer], xmm0
0x1800115cd  movups  [rbp+27h+var_38], xmm0
0x1800115d1  test    rsi, rsi
0x1800115d4  jnz     short loc_1800115DE
0x1800115d6  lea     eax, [rsi+57h]
0x1800115d9  jmp     loc_180011755
0x1800115de  lea     rdx, [rbp+27h+nSize]; nSize
0x1800115e2  lea     rcx, [rbp+27h+Buffer]; lpBuffer
0x1800115e6  call    cs:__imp_GetComputerNameW
0x1800115ec  test    eax, eax
0x1800115ee  jnz     short loc_1800115FB
0x1800115f0  call    cs:__imp_GetLastError
0x1800115f6  jmp     loc_180011755
0x1800115fb  lea     rcx, g_RpcCs; lpCriticalSection
0x180011602  call    cs:__imp_EnterCriticalSection
0x180011608  lea     r14, aRasmanlrpc; "RasmanLrpc"
0x18001160f  test    rbx, rbx
0x180011612  jz      short loc_18001165E
0x180011614  cmp     [rbx], r12w
0x180011618  jz      short loc_18001165E
0x18001161a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001161e  inc     rax
0x180011621  cmp     [rbx+rax*2], r12w
0x180011626  jnz     short loc_18001161E
0x180011628  cmp     rax, 2
0x18001162c  jbe     short loc_18001163F
0x18001162e  cmp     word ptr [rbx], 5Ch ; '\'
0x180011632  jnz     short loc_18001163F
0x180011634  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180011639  jnz     short loc_18001163F
0x18001163b  add     rbx, 4
0x18001163f  lea     rdx, [rbp+27h+Buffer]; String2
0x180011643  mov     rcx, rbx; String1
0x180011646  call    cs:__imp__wcsicmp
0x18001164c  test    eax, eax
0x18001164e  mov     edi, r12d
0x180011651  setz    dil
0x180011655  test    eax, eax
0x180011657  jz      short loc_180011667
0x180011659  jmp     loc_1800116E3
0x18001165e  lea     rbx, [rbp+27h+Buffer]
0x180011662  mov     edi, 1
0x180011667  mov     rax, cs:g_hBinding
0x18001166e  test    rax, rax
0x180011671  jz      short loc_18001167B
0x180011673  mov     ebx, r12d
0x180011676  jmp     loc_18001172E
0x18001167b  mov     rdx, r14; String2
0x18001167e  mov     rcx, r14; String1
0x180011681  call    cs:__imp__wcsicmp
0x180011687  test    eax, eax
0x180011689  jnz     short loc_1800116E3
0x18001168b  lea     rax, [rbp+27h+var_58]
0x18001168f  xor     r9d, r9d; nSubAuthority1
0x180011692  mov     [rsp+0C0h+pSid], rax; pSid
0x180011697  lea     rcx, [rbp+27h+pIdentifierAuthority]; pIdentifierAuthority
0x18001169b  mov     [rsp+0C0h+nSubAuthority7], r12d; nSubAuthority7
0x1800116a0  mov     dl, 1; nSubAuthorityCount
0x1800116a2  mov     [rsp+0C0h+nSubAuthority6], r12d; int
0x1800116a7  mov     dword ptr [rsp+0C0h+nSubAuthority5], r12d; RPC_WSTR
0x1800116ac  lea     r8d, [r9+12h]; nSubAuthority0
0x1800116b0  mov     [rsp+0C0h+nSubAuthority4], r12d; int
0x1800116b5  mov     [rsp+0C0h+nSubAuthority3], r12d; int
0x1800116ba  mov     dword ptr [rsp+0C0h+nSubAuthority2], r12d; ServerPrincName
0x1800116bf  call    cs:__imp_AllocateAndInitializeSid
0x1800116c5  test    eax, eax
0x1800116c7  jnz     short loc_1800116D3
0x1800116c9  call    cs:__imp_GetLastError
0x1800116cf  mov     ebx, eax
0x1800116d1  jmp     short loc_180011737
0x1800116d3  mov     rax, [rbp+27h+var_58]
0x1800116d7  mov     [r15+20h], rax
0x1800116db  mov     dword ptr [r15+4], 11h
0x1800116e3  test    edi, edi
0x1800116e5  lea     rax, g_hBinding
0x1800116ec  cmovz   rax, rsi
0x1800116f0  jz      short loc_1800116FE
0x1800116f2  lea     r8, aNcalrpc; "ncalrpc"
0x1800116f9  mov     rbx, r12
0x1800116fc  jmp     short loc_18001170C
0x1800116fe  lea     r14, aPipeRouter; "\\PIPE\\ROUTER"
0x180011705  lea     r8, aNcacnNp; "ncacn_np"
0x18001170c  mov     [rsp+0C0h+pSid], rax; Binding
0x180011711  mov     r9, r14
0x180011714  mov     rcx, rbx; NetworkAddr
0x180011717  mov     qword ptr [rsp+0C0h+nSubAuthority7], r15; RPC_SECURITY_QOS *
0x18001171c  call    RPCBind
0x180011721  mov     ebx, eax
0x180011723  test    edi, edi
0x180011725  jz      short loc_180011737
0x180011727  mov     rax, cs:g_hBinding
0x18001172e  inc     cs:g_dwRefCount
0x180011734  mov     [rsi], rax
0x180011737  mov     rcx, [rbp+27h+var_58]; pSid
0x18001173b  test    rcx, rcx
0x18001173e  jz      short loc_180011746
0x180011740  call    cs:__imp_FreeSid
0x180011746  lea     rcx, g_RpcCs; lpCriticalSection
0x18001174d  call    cs:__imp_LeaveCriticalSection
0x180011753  mov     eax, ebx
0x180011755  mov     rcx, [rbp+27h+var_28]
0x180011759  xor     rcx, rsp; StackCookie
0x18001175c  call    __security_check_cookie
0x180011761  lea     r11, [rsp+0C0h+var_20]
0x180011769  mov     rbx, [r11+38h]
0x18001176d  mov     rsi, [r11+40h]
0x180011771  mov     rsp, r11
0x180011774  pop     r15
0x180011776  pop     r14
0x180011778  pop     r12
0x18001177a  pop     rdi
0x18001177b  pop     rbp
0x18001177c  retn
```
