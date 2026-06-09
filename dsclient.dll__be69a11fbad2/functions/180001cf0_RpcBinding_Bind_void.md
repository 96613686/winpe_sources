# RpcBinding::Bind(void)

- ea: `0x180001cf0`
- end: `0x180001e08`
- name: `?Bind@RpcBinding@@QEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *this)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001400`
- `0x180001500`
- `0x180001b20`
- `0x180001be0`
- `0x1800039c0`
- `0x180003a7c`
- `0x180003b38`
- `0x180003c20`

## callees

- `0x180001cf0`
- `0x1800095e8`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001db8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001db8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001dd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001dd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de7`
- `RPCRT4!RpcBindingFree` at `0x180001dc6`
- `RPCRT4!RpcBindingFree` at `0x180001dc6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180001d6a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180001d6a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180001dab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180001dab`

## pseudocode

```c
__int64 __fastcall RpcBinding::Bind(RPC_BINDING_HANDLE *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  signed int v3; // ebx
  void *v4; // rdx
  DevPlat::Shared *v5; // rcx
  const unsigned __int16 *v6; // r8
  signed int LastError; // eax
  void **nSubAuthority2; // [rsp+20h] [rbp-88h]
  void *nSubAuthority4; // [rsp+30h] [rbp-78h]
  PSID pSid; // [rsp+60h] [rbp-48h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-40h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  if ( *this )
    goto LABEL_14;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
LABEL_6:
    v3 = DevPlat::Shared::BindToRPCServerInSessionMutualAuth(
           v5,
           v4,
           v6,
           (unsigned int)this,
           nSubAuthority2,
           (unsigned int)pSid,
           nSubAuthority4);
  if ( pSid )
    FreeSid(pSid);
  if ( v3 >= 0 )
  {
LABEL_14:
    if ( v1 )
      goto LABEL_15;
  }
  else
  {
    EnterCriticalSection(v1);
    if ( *this )
    {
      RpcBindingFree(this);
      *this = 0;
    }
    if ( v1 )
    {
      LeaveCriticalSection(v1);
LABEL_15:
      LeaveCriticalSection(v1);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001cf0  push    rbx
0x180001cf2  push    rbp
0x180001cf3  push    rsi
0x180001cf4  push    rdi
0x180001cf5  sub     rsp, 88h
0x180001cfc  mov     rax, cs:__security_cookie
0x180001d03  xor     rax, rsp
0x180001d06  mov     [rsp+0A8h+var_38], rax
0x180001d0b  lea     rdi, [rcx+8]
0x180001d0f  mov     rsi, rcx
0x180001d12  xor     ebp, ebp
0x180001d14  mov     rcx, rdi; lpCriticalSection
0x180001d17  mov     ebx, ebp
0x180001d19  call    cs:__imp_EnterCriticalSection
0x180001d1f  cmp     [rsi], rbx
0x180001d22  jnz     loc_180001DDF
0x180001d28  lea     rax, [rsp+0A8h+var_48]
0x180001d2d  mov     [rsp+0A8h+var_48], rbp
0x180001d32  mov     [rsp+0A8h+pSid], rax; pSid
0x180001d37  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x180001d3c  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x180001d40  xor     r9d, r9d; nSubAuthority1
0x180001d43  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x180001d47  mov     r8d, 12h; nSubAuthority0
0x180001d4d  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x180001d51  mov     dl, 1; nSubAuthorityCount
0x180001d53  mov     dword ptr [rsp+0A8h+nSubAuthority4], ebp; void *
0x180001d57  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x180001d5b  mov     dword ptr [rsp+0A8h+nSubAuthority2], ebp; void **
0x180001d5f  mov     dword ptr [rsp+0A8h+pIdentifierAuthority.Value], ebx
0x180001d63  mov     word ptr [rsp+0A8h+pIdentifierAuthority.Value+4], 500h
0x180001d6a  call    cs:__imp_AllocateAndInitializeSid
0x180001d70  test    eax, eax
0x180001d72  jnz     short loc_180001D8D
0x180001d74  call    cs:__imp_GetLastError
0x180001d7a  mov     ebx, eax
0x180001d7c  test    eax, eax
0x180001d7e  jle     short loc_180001D89
0x180001d80  movzx   ebx, ax
0x180001d83  or      ebx, 80070000h
0x180001d89  test    ebx, ebx
0x180001d8b  js      short loc_180001DA1
0x180001d8d  mov     rax, [rsp+0A8h+var_48]
0x180001d92  mov     r9, rsi; unsigned int
0x180001d95  mov     qword ptr [rsp+0A8h+nSubAuthority3], rax; unsigned int
0x180001d9a  call    ?BindToRPCServerInSessionMutualAuth@Shared@DevPlat@@YAJPEAXPEBGKPEAPEAXK0@Z; DevPlat::Shared::BindToRPCServerInSessionMutualAuth(void *,ushort const *,ulong,void * *,ulong,void *)
0x180001d9f  mov     ebx, eax
0x180001da1  mov     rcx, [rsp+0A8h+var_48]; pSid
0x180001da6  test    rcx, rcx
0x180001da9  jz      short loc_180001DB1
0x180001dab  call    cs:__imp_FreeSid
0x180001db1  test    ebx, ebx
0x180001db3  jns     short loc_180001DDF
0x180001db5  mov     rcx, rdi; lpCriticalSection
0x180001db8  call    cs:__imp_EnterCriticalSection
0x180001dbe  cmp     [rsi], rbp
0x180001dc1  jz      short loc_180001DCF
0x180001dc3  mov     rcx, rsi; Binding
0x180001dc6  call    cs:__imp_RpcBindingFree
0x180001dcc  mov     [rsi], rbp
0x180001dcf  test    rdi, rdi
0x180001dd2  jz      short loc_180001DED
0x180001dd4  mov     rcx, rdi; lpCriticalSection
0x180001dd7  call    cs:__imp_LeaveCriticalSection
0x180001ddd  jmp     short loc_180001DE4
0x180001ddf  test    rdi, rdi
0x180001de2  jz      short loc_180001DED
0x180001de4  mov     rcx, rdi; lpCriticalSection
0x180001de7  call    cs:__imp_LeaveCriticalSection
0x180001ded  mov     eax, ebx
0x180001def  mov     rcx, [rsp+0A8h+var_38]
0x180001df4  xor     rcx, rsp; StackCookie
0x180001df7  call    __security_check_cookie
0x180001dfc  add     rsp, 88h
0x180001e03  pop     rdi
0x180001e04  pop     rsi
0x180001e05  pop     rbp
0x180001e06  pop     rbx
0x180001e07  retn
```
