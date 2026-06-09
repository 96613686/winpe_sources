# BdeSvcApipInitRpc(void * *)

- ea: `0x1800fffa8`
- end: `0x180100161`
- name: `?BdeSvcApipInitRpc@@YAJPEAPEAX@Z`
- size: `441`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ffe94`

## callees

- `0x1800fffa8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010008d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010008d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180100120`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180100120`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18010007d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18010007d`
- `RPCRT4!RpcBindingFree` at `0x18010013a`
- `RPCRT4!RpcBindingFree` at `0x18010013a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1801000da`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1801000da`
- `RPCRT4!RpcStringBindingComposeW` at `0x18010000f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18010000f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18010003d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18010003d`
- `RPCRT4!RpcStringFreeW` at `0x180100107`
- `RPCRT4!RpcStringFreeW` at `0x180100107`

## pseudocode

```c
__int64 __fastcall BdeSvcApipInitRpc(void **a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-19h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-1h] BYREF
  __int128 v10; // [rsp+88h] [rbp+Fh]
  PSID v11; // [rsp+98h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Binding = 0;
  v11 = 0;
  String = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SecurityQOS = 0;
  v10 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    v3 = LastError;
    v4 = LastError <= 0;
    if ( !LastError )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        SecurityQOS.Version = 3;
        SecurityQOS.ImpersonationType = 3;
        v11 = pSid;
        *(_QWORD *)&SecurityQOS.Capabilities = 1;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
        v3 = LastError;
        v4 = LastError <= 0;
        if ( !LastError )
        {
          v3 = 0;
          *a1 = Binding;
          Binding = 0;
          goto LABEL_9;
        }
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        v4 = LastError <= 0;
      }
    }
  }
  if ( !v4 )
    v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
  if ( String )
  {
    RpcStringFreeW(&String);
    String = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return v3;
}

```

## disassembly

```asm
0x1800fffa8  push    rbp
0x1800fffaa  push    rbx
0x1800fffab  push    rsi
0x1800fffac  push    rdi
0x1800fffad  lea     rbp, [rsp-3Fh]
0x1800fffb2  sub     rsp, 0B8h
0x1800fffb9  mov     rax, cs:__security_cookie
0x1800fffc0  xor     rax, rsp
0x1800fffc3  mov     [rbp+57h+var_28], rax
0x1800fffc7  xor     esi, esi
0x1800fffc9  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800fffcf  xor     eax, eax
0x1800fffd1  mov     [rbp+57h+Binding], rsi
0x1800fffd5  xorps   xmm0, xmm0
0x1800fffd8  mov     [rbp+57h+var_38], rax
0x1800fffdc  lea     rax, [rbp+57h+String]
0x1800fffe0  mov     [rbp+57h+String], rsi
0x1800fffe4  mov     rdi, rcx
0x1800fffe7  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x1800fffec  xor     r9d, r9d; Endpoint
0x1800fffef  mov     [rsp+0D0h+Options], rsi; Options
0x1800ffff4  xor     r8d, r8d; NetworkAddr
0x1800ffff7  mov     [rbp+57h+var_60], rsi
0x1800ffffb  lea     rdx, ProtSeq; "ncalrpc"
0x180100002  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180100005  xor     ecx, ecx; ObjUuid
0x180100007  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x18010000b  movups  [rbp+57h+var_48], xmm0
0x18010000f  call    cs:__imp_RpcStringBindingComposeW
0x180100016  nop     dword ptr [rax+rax+00h]
0x18010001b  mov     ebx, eax
0x18010001d  test    eax, eax
0x18010001f  jz      short loc_180100035
0x180100021  jle     loc_1801000FD
0x180100027  movzx   ebx, ax
0x18010002a  or      ebx, 80070000h
0x180100030  jmp     loc_1801000FD
0x180100035  mov     rcx, [rbp+57h+String]; StringBinding
0x180100039  lea     rdx, [rbp+57h+Binding]; Binding
0x18010003d  call    cs:__imp_RpcBindingFromStringBindingW
0x180100044  nop     dword ptr [rax+rax+00h]
0x180100049  mov     ebx, eax
0x18010004b  test    eax, eax
0x18010004d  jnz     short loc_180100021
0x18010004f  lea     rax, [rbp+57h+var_60]
0x180100053  xor     r9d, r9d; nSubAuthority1
0x180100056  mov     [rsp+0D0h+pSid], rax; pSid
0x18010005b  lea     r8d, [rbx+12h]; nSubAuthority0
0x18010005f  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x180100063  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180100067  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x18010006b  mov     dl, 1; nSubAuthorityCount
0x18010006d  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x180100071  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x180100075  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x180100079  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x18010007d  call    cs:__imp_AllocateAndInitializeSid
0x180100084  nop     dword ptr [rax+rax+00h]
0x180100089  test    eax, eax
0x18010008b  jnz     short loc_18010009F
0x18010008d  call    cs:__imp_GetLastError
0x180100094  nop     dword ptr [rax+rax+00h]
0x180100099  mov     ebx, eax
0x18010009b  test    eax, eax
0x18010009d  jmp     short loc_180100021
0x18010009f  mov     rcx, [rbp+57h+Binding]; Binding
0x1801000a3  mov     eax, 3
0x1801000a8  mov     [rbp+57h+SecurityQOS.Version], eax
0x1801000ab  xor     edx, edx; ServerPrincName
0x1801000ad  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x1801000b0  mov     rax, [rbp+57h+var_60]
0x1801000b4  mov     [rbp+57h+var_38], rax
0x1801000b8  lea     rax, [rbp+57h+SecurityQOS]
0x1801000bc  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x1801000c1  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1801000c5  mov     dword ptr [rsp+0D0h+StringBinding], esi; AuthzSvc
0x1801000c9  lea     r8d, [rdx+6]; AuthnLevel
0x1801000cd  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x1801000d2  mov     qword ptr [rbp+57h+SecurityQOS.Capabilities], 1
0x1801000da  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1801000e1  nop     dword ptr [rax+rax+00h]
0x1801000e6  mov     ebx, eax
0x1801000e8  test    eax, eax
0x1801000ea  jnz     loc_180100021
0x1801000f0  mov     rax, [rbp+57h+Binding]
0x1801000f4  mov     ebx, esi
0x1801000f6  mov     [rdi], rax
0x1801000f9  mov     [rbp+57h+Binding], rsi
0x1801000fd  cmp     [rbp+57h+String], rsi
0x180100101  jz      short loc_180100117
0x180100103  lea     rcx, [rbp+57h+String]; String
0x180100107  call    cs:__imp_RpcStringFreeW
0x18010010e  nop     dword ptr [rax+rax+00h]
0x180100113  mov     [rbp+57h+String], rsi
0x180100117  mov     rcx, [rbp+57h+var_60]; pSid
0x18010011b  test    rcx, rcx
0x18010011e  jz      short loc_180100130
0x180100120  call    cs:__imp_FreeSid
0x180100127  nop     dword ptr [rax+rax+00h]
0x18010012c  mov     [rbp+57h+var_60], rsi
0x180100130  cmp     [rbp+57h+Binding], rsi
0x180100134  jz      short loc_180100146
0x180100136  lea     rcx, [rbp+57h+Binding]; Binding
0x18010013a  call    cs:__imp_RpcBindingFree
0x180100141  nop     dword ptr [rax+rax+00h]
0x180100146  mov     eax, ebx
0x180100148  mov     rcx, [rbp+57h+var_28]
0x18010014c  xor     rcx, rsp; StackCookie
0x18010014f  call    __security_check_cookie
0x180100154  add     rsp, 0B8h
0x18010015b  pop     rdi
0x18010015c  pop     rsi
0x18010015d  pop     rbx
0x18010015e  pop     rbp
0x18010015f  retn
```
