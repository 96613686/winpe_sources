# CAepStoreAccess::GetDasRpcBinding(void * *)

- ea: `0x1400194f4`
- end: `0x1400195cc`
- name: `?GetDasRpcBinding@CAepStoreAccess@@IEAAJPEAPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(CAepStoreAccess *__hidden this, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019330`
- `0x140019410`
- `0x140019840`

## callees

- `0x1400194f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400195a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400195a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019517`
- `RPCRT4!RpcStringFreeW` at `0x1400195bb`
- `RPCRT4!RpcStringFreeW` at `0x1400195bb`
- `RPCRT4!RpcStringBindingComposeW` at `0x140019556`
- `RPCRT4!RpcStringBindingComposeW` at `0x140019556`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14001957a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14001957a`
- `RPCRT4!RpcBindingSetOption` at `0x14001958f`
- `RPCRT4!RpcBindingSetOption` at `0x14001958f`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::GetDasRpcBinding(CAepStoreAccess *this, void **a2)
{
  void *v4; // rax
  unsigned int v5; // ebx
  RPC_STATUS v6; // eax
  bool v7; // sf
  RPC_WSTR String; // [rsp+60h] [rbp+8h] BYREF

  String = 0;
  *a2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 8) )
  {
    v4 = (void *)*((_QWORD *)this + 5);
    v5 = 0;
    if ( v4 )
    {
LABEL_3:
      *a2 = v4;
      goto LABEL_12;
    }
    v6 = RpcStringBindingComposeW(
           (RPC_WSTR)L"1475c123-1193-4379-81ac-302c4383421d",
           (RPC_WSTR)L"ncalrpc",
           0,
           0,
           0,
           &String);
    v7 = v6 < 0;
    if ( v6 || (v6 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)this + 5), v7 = v6 < 0, v6) )
    {
      if ( v7 )
        v5 = v6;
      else
        v5 = (unsigned __int16)v6 | 0x80010000;
    }
    else if ( !RpcBindingSetOption(*((RPC_BINDING_HANDLE *)this + 5), 0xDu, 1u) )
    {
      v4 = (void *)*((_QWORD *)this + 5);
      goto LABEL_3;
    }
  }
  else
  {
    v5 = -2140930029;
  }
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( String )
    RpcStringFreeW(&String);
  return v5;
}

```

## disassembly

```asm
0x1400194f4  push    rbx
0x1400194f6  push    rbp
0x1400194f7  push    rsi
0x1400194f8  push    rdi
0x1400194f9  sub     rsp, 38h
0x1400194fd  mov     rdi, rcx
0x140019500  mov     [rsp+58h+String], 0
0x140019509  add     rcx, 30h ; '0'; lpCriticalSection
0x14001950d  mov     qword ptr [rdx], 0
0x140019514  mov     rsi, rdx
0x140019517  call    cs:__imp_EnterCriticalSection
0x14001951d  cmp     dword ptr [rdi+20h], 0
0x140019521  jz      short loc_14001959F
0x140019523  mov     rax, [rdi+28h]
0x140019527  xor     ebx, ebx
0x140019529  test    rax, rax
0x14001952c  jz      short loc_140019533
0x14001952e  mov     [rsi], rax
0x140019531  jmp     short loc_1400195A4
0x140019533  lea     rax, [rsp+58h+String]
0x140019538  xor     r9d, r9d; Endpoint
0x14001953b  mov     [rsp+58h+StringBinding], rax; StringBinding
0x140019540  lea     rdx, ProtSeq; "ncalrpc"
0x140019547  xor     r8d, r8d; NetworkAddr
0x14001954a  mov     [rsp+58h+Options], rbx; Options
0x14001954f  lea     rcx, ObjUuid; "1475c123-1193-4379-81ac-302c4383421d"
0x140019556  call    cs:__imp_RpcStringBindingComposeW
0x14001955c  test    eax, eax
0x14001955e  jz      short loc_140019571
0x140019560  js      short loc_14001956D
0x140019562  movzx   ebx, ax
0x140019565  or      ebx, 80010000h
0x14001956b  jmp     short loc_1400195A4
0x14001956d  mov     ebx, eax
0x14001956f  jmp     short loc_1400195A4
0x140019571  mov     rcx, [rsp+58h+String]; StringBinding
0x140019576  lea     rdx, [rdi+28h]; Binding
0x14001957a  call    cs:__imp_RpcBindingFromStringBindingW
0x140019580  test    eax, eax
0x140019582  jnz     short loc_140019560
0x140019584  mov     rcx, [rdi+28h]; hBinding
0x140019588  lea     edx, [rax+0Dh]; option
0x14001958b  lea     r8d, [rax+1]; optionValue
0x14001958f  call    cs:__imp_RpcBindingSetOption
0x140019595  test    eax, eax
0x140019597  jnz     short loc_1400195A4
0x140019599  mov     rax, [rdi+28h]
0x14001959d  jmp     short loc_14001952E
0x14001959f  mov     ebx, 80640013h
0x1400195a4  lea     rcx, [rdi+30h]; lpCriticalSection
0x1400195a8  call    cs:__imp_LeaveCriticalSection
0x1400195ae  cmp     [rsp+58h+String], 0
0x1400195b4  jz      short loc_1400195C1
0x1400195b6  lea     rcx, [rsp+58h+String]; String
0x1400195bb  call    cs:__imp_RpcStringFreeW
0x1400195c1  mov     eax, ebx
0x1400195c3  add     rsp, 38h
0x1400195c7  pop     rdi
0x1400195c8  pop     rsi
0x1400195c9  pop     rbp
0x1400195ca  pop     rbx
0x1400195cb  retn
```
