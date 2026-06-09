# ComputeService::Resources::DuplicateNetworkHandle(void *)

- ea: `0x1800147ec`
- end: `0x1800148e8`
- name: `?DuplicateNetworkHandle@Resources@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800126a8`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18001017c`
- `0x1800147ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001483d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001483d`
- `WS2_32!WSADuplicateSocketW` at `0x18001484d`
- `WS2_32!WSADuplicateSocketW` at `0x18001484d`
- `WS2_32!WSASocketW` at `0x18001487a`
- `WS2_32!WSASocketW` at `0x18001487a`

## string_xrefs

- `0x1800148c1`: `onecore\vm\compute\shared\computesystem\ServerResources.h`
- `0x1800148d3`: `onecore\vm\compute\shared\computesystem\ServerResources.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SOCKET *__fastcall ComputeService::Resources::DuplicateNetworkHandle(SOCKET *a1, SOCKET a2)
{
  DWORD CurrentProcessId; // eax
  const char *v5; // r9
  SOCKET v6; // rax
  const char *v7; // r9
  _WSAPROTOCOL_INFOW ProtocolInfo; // [rsp+40h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  memset_0(&ProtocolInfo, 0, sizeof(ProtocolInfo));
  CurrentProcessId = GetCurrentProcessId();
  if ( WSADuplicateSocketW(a2, CurrentProcessId, &ProtocolInfo) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\compute\\shared\\computesystem\\ServerResources.h",
      v5);
  v6 = WSASocketW(ProtocolInfo.iAddressFamily, ProtocolInfo.iSocketType, ProtocolInfo.iProtocol, &ProtocolInfo, 0, 0);
  *a1 = v6;
  if ( v6 == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\vm\\compute\\shared\\computesystem\\ServerResources.h",
      v7);
  return a1;
}

```

## disassembly

```asm
0x1800147ec  mov     [rsp+arg_10], rbx
0x1800147f1  mov     [rsp+arg_18], rsi
0x1800147f6  push    rdi
0x1800147f7  sub     rsp, 2D0h
0x1800147fe  mov     rax, cs:__security_cookie
0x180014805  xor     rax, rsp
0x180014808  mov     [rsp+2D8h+var_18], rax
0x180014810  mov     rbx, rdx
0x180014813  mov     rdi, rcx
0x180014816  mov     [rsp+2D8h+var_2A0], rcx
0x18001481b  mov     [rsp+2D8h+var_2A8], 0
0x180014823  xor     edx, edx; Val
0x180014825  mov     r8d, 274h; Size
0x18001482b  lea     rcx, [rsp+2D8h+ProtocolInfo]; void *
0x180014830  call    memset_0
0x180014835  mov     rsi, [rsp+2D8h]
0x18001483d  call    cs:__imp_GetCurrentProcessId
0x180014843  mov     edx, eax; dwProcessId
0x180014845  lea     r8, [rsp+2D8h+ProtocolInfo]; lpProtocolInfo
0x18001484a  mov     rcx, rbx; s
0x18001484d  call    cs:__imp_WSADuplicateSocketW
0x180014853  test    eax, eax
0x180014855  jnz     short loc_1800148D3
0x180014857  mov     [rsp+2D8h+dwFlags], eax; dwFlags
0x18001485b  mov     [rsp+2D8h+g], eax; g
0x18001485f  lea     r9, [rsp+2D8h+ProtocolInfo]; lpProtocolInfo
0x180014864  mov     r8d, [rsp+2D8h+ProtocolInfo.iProtocol]; protocol
0x18001486c  mov     edx, [rsp+2D8h+ProtocolInfo.iSocketType]; type
0x180014873  mov     ecx, [rsp+2D8h+ProtocolInfo.iAddressFamily]; af
0x18001487a  call    cs:__imp_WSASocketW
0x180014880  mov     [rdi], rax
0x180014883  mov     [rsp+2D8h+var_2A8], 1
0x18001488b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001488f  jz      short loc_1800148B9
0x180014891  mov     rax, rdi
0x180014894  mov     rcx, [rsp+2D8h+var_18]
0x18001489c  xor     rcx, rsp; StackCookie
0x18001489f  call    __security_check_cookie
0x1800148a4  lea     r11, [rsp+2D8h+var_8]
0x1800148ac  mov     rbx, [r11+20h]
0x1800148b0  mov     rsi, [r11+28h]
0x1800148b4  mov     rsp, r11
0x1800148b7  pop     rdi
0x1800148b8  retn
0x1800148b9  mov     rcx, [rsp+2D8h]; this
0x1800148c1  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\shared\\computesy"...
0x1800148c8  mov     edx, 2Ch ; ','; void *
0x1800148cd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800148d3  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\shared\\computesy"...
0x1800148da  mov     edx, 29h ; ')'; void *
0x1800148df  mov     rcx, rsi; this
0x1800148e2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
