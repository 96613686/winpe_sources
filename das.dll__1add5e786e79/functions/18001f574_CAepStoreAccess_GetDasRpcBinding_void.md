# CAepStoreAccess::GetDasRpcBinding(void * *)

- ea: `0x18001f574`
- end: `0x18001f64e`
- name: `?GetDasRpcBinding@CAepStoreAccess@@IEAAJPEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(CAepStoreAccess *__hidden this, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180042310`
- `0x1800423e0`

## callees

- `0x18001f574`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f597`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f597`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f612`
- `RPCRT4!RpcBindingSetOption` at `0x18001f5fd`
- `RPCRT4!RpcBindingSetOption` at `0x18001f5fd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001f5e8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001f5e8`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f5d5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001f5d5`
- `RPCRT4!RpcStringFreeW` at `0x18001f625`
- `RPCRT4!RpcStringFreeW` at `0x18001f625`

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
LABEL_7:
      *a2 = v4;
      goto LABEL_8;
    }
    v6 = RpcStringBindingComposeW(
           (RPC_WSTR)L"1475c123-1193-4379-81ac-302c4383421d",
           (RPC_WSTR)L"ncalrpc",
           0,
           0,
           0,
           &String);
    v7 = v6 < 0;
    if ( !v6 )
    {
      v6 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)this + 5);
      v7 = v6 < 0;
      if ( !v6 )
      {
        if ( RpcBindingSetOption(*((RPC_BINDING_HANDLE *)this + 5), 0xDu, 1u) )
          goto LABEL_8;
        v4 = (void *)*((_QWORD *)this + 5);
        goto LABEL_7;
      }
    }
    if ( v7 )
      v5 = v6;
    else
      v5 = (unsigned __int16)v6 | 0x80010000;
  }
  else
  {
    v5 = -2140930029;
  }
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( String )
    RpcStringFreeW(&String);
  return v5;
}

```

## disassembly

```asm
0x18001f574  push    rbx
0x18001f576  push    rbp
0x18001f577  push    rsi
0x18001f578  push    rdi
0x18001f579  sub     rsp, 38h
0x18001f57d  mov     rdi, rcx
0x18001f580  mov     [rsp+58h+String], 0
0x18001f589  add     rcx, 30h ; '0'; lpCriticalSection
0x18001f58d  mov     qword ptr [rdx], 0
0x18001f594  mov     rsi, rdx
0x18001f597  call    cs:__imp_EnterCriticalSection
0x18001f59d  cmp     dword ptr [rdi+20h], 0
0x18001f5a1  jz      loc_18001F647
0x18001f5a7  mov     rax, [rdi+28h]
0x18001f5ab  xor     ebx, ebx
0x18001f5ad  test    rax, rax
0x18001f5b0  jnz     short loc_18001F60B
0x18001f5b2  lea     rax, [rsp+58h+String]
0x18001f5b7  xor     r9d, r9d; Endpoint
0x18001f5ba  mov     [rsp+58h+StringBinding], rax; StringBinding
0x18001f5bf  lea     rdx, ProtSeq; "ncalrpc"
0x18001f5c6  xor     r8d, r8d; NetworkAddr
0x18001f5c9  mov     [rsp+58h+Options], rbx; Options
0x18001f5ce  lea     rcx, ObjUuid; "1475c123-1193-4379-81ac-302c4383421d"
0x18001f5d5  call    cs:__imp_RpcStringBindingComposeW
0x18001f5db  test    eax, eax
0x18001f5dd  jnz     short loc_18001F636
0x18001f5df  mov     rcx, [rsp+58h+String]; StringBinding
0x18001f5e4  lea     rdx, [rdi+28h]; Binding
0x18001f5e8  call    cs:__imp_RpcBindingFromStringBindingW
0x18001f5ee  test    eax, eax
0x18001f5f0  jnz     short loc_18001F636
0x18001f5f2  mov     rcx, [rdi+28h]; hBinding
0x18001f5f6  lea     edx, [rbx+0Dh]; option
0x18001f5f9  lea     r8d, [rbx+1]; optionValue
0x18001f5fd  call    cs:__imp_RpcBindingSetOption
0x18001f603  test    eax, eax
0x18001f605  jnz     short loc_18001F60E
0x18001f607  mov     rax, [rdi+28h]
0x18001f60b  mov     [rsi], rax
0x18001f60e  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001f612  call    cs:__imp_LeaveCriticalSection
0x18001f618  cmp     [rsp+58h+String], 0
0x18001f61e  jz      short loc_18001F62B
0x18001f620  lea     rcx, [rsp+58h+String]; String
0x18001f625  call    cs:__imp_RpcStringFreeW
0x18001f62b  mov     eax, ebx
0x18001f62d  add     rsp, 38h
0x18001f631  pop     rdi
0x18001f632  pop     rsi
0x18001f633  pop     rbp
0x18001f634  pop     rbx
0x18001f635  retn
0x18001f636  jns     short loc_18001F63C
0x18001f638  mov     ebx, eax
0x18001f63a  jmp     short loc_18001F60E
0x18001f63c  movzx   ebx, ax
0x18001f63f  or      ebx, 80010000h
0x18001f645  jmp     short loc_18001F60E
0x18001f647  mov     ebx, 80640013h
0x18001f64c  jmp     short loc_18001F60E
```
