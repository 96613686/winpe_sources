# CImpersonate::ImpersonateRpcClient(void)

- ea: `0x180023984`
- end: `0x180023a3e`
- name: `?ImpersonateRpcClient@CImpersonate@@QEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180032be0`
- `0x1800334a0`
- `0x18005ea70`
- `0x180060530`
- `0x180060a60`

## callees

- `0x1800077a0`
- `0x180023984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002399a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002399a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800239d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800239d1`
- `RPCRT4!RpcImpersonateClient` at `0x1800239df`
- `RPCRT4!RpcImpersonateClient` at `0x1800239df`

## string_xrefs

- `0x180023a2b`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180023a21`: `CImpersonate::ImpersonateRpcClient`

## pseudocode

```c
__int64 __fastcall CImpersonate::ImpersonateRpcClient(CImpersonate *this)
{
  HANDLE CurrentThread; // rax
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    GetLastError();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v4, "CImpersonate::ImpersonateRpcClient");
  else
    *(_WORD *)this = 257;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023984  mov     [rsp+arg_0], rbx
0x180023989  push    rdi
0x18002398a  sub     rsp, 20h
0x18002398e  mov     rdi, rcx
0x180023991  mov     [rsp+28h+TokenHandle], 0
0x18002399a  call    cs:__imp_GetCurrentThread
0x1800239a1  nop     dword ptr [rax+rax+00h]
0x1800239a6  mov     edx, 0Eh; DesiredAccess
0x1800239ab  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800239b0  mov     rcx, rax; ThreadHandle
0x1800239b3  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800239b7  call    cs:__imp_OpenThreadToken
0x1800239be  nop     dword ptr [rax+rax+00h]
0x1800239c3  test    eax, eax
0x1800239c5  jz      short loc_180023A08
0x1800239c7  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800239cc  test    rcx, rcx
0x1800239cf  jz      short loc_1800239DD
0x1800239d1  call    cs:__imp_CloseHandle
0x1800239d8  nop     dword ptr [rax+rax+00h]
0x1800239dd  xor     ecx, ecx; BindingHandle
0x1800239df  call    cs:__imp_RpcImpersonateClient
0x1800239e6  nop     dword ptr [rax+rax+00h]
0x1800239eb  mov     ebx, eax
0x1800239ed  test    eax, eax
0x1800239ef  jg      short loc_180023A16
0x1800239f1  test    ebx, ebx
0x1800239f3  js      short loc_180023A21
0x1800239f5  mov     word ptr [rdi], 101h
0x1800239fa  mov     eax, ebx
0x1800239fc  mov     rbx, [rsp+28h+arg_0]
0x180023a01  add     rsp, 20h
0x180023a05  pop     rdi
0x180023a06  retn
0x180023a08  call    cs:__imp_GetLastError
0x180023a0f  nop     dword ptr [rax+rax+00h]
0x180023a14  jmp     short loc_1800239C7
0x180023a16  movzx   ebx, ax
0x180023a19  or      ebx, 80070000h
0x180023a1f  jmp     short loc_1800239F1
0x180023a21  lea     r9, aCimpersonateIm_0; "CImpersonate::ImpersonateRpcClient"
0x180023a28  mov     r8d, ebx
0x180023a2b  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180023a32  mov     ecx, 8; int
0x180023a37  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023a3c  jmp     short loc_1800239FA
```
