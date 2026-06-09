# RPCBind

- ea: `0x18003fff4`
- end: `0x1800401b2`
- name: `RPCBind`
- size: `446`
- prototype: `int __fastcall(RPC_WSTR ServerPrincName, __int64, wchar_t *, unsigned __int16 *, RPC_WSTR, int, int, int, int, int, RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800401b8`

## callees

- `0x180001706`
- `0x180016c40`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800400ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800400ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800400f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800400f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040135`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004019a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004019a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18004012a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18004015e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18004012a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18004015e`
- `RPCRT4!RpcBindingFree` at `0x18004018f`
- `RPCRT4!RpcBindingFree` at `0x18004018f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180040076`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180040076`
- `RPCRT4!RpcStringFreeW` at `0x180040086`
- `RPCRT4!RpcStringFreeW` at `0x180040178`
- `RPCRT4!RpcStringFreeW` at `0x180040086`
- `RPCRT4!RpcStringFreeW` at `0x180040178`
- `RPCRT4!RpcStringBindingComposeW` at `0x180040053`
- `RPCRT4!RpcStringBindingComposeW` at `0x180040053`

## string_xrefs

- `0x180040045`: `Security=Impersonation Dynamic True`

## pseudocode

```c
int __fastcall RPCBind(
        RPC_WSTR ServerPrincName,
        __int64 a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        RPC_WSTR a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        RPC_BINDING_HANDLE *Binding)
{
  int v12; // r14d
  int v15; // esi
  RPC_STATUS v16; // eax
  RPC_BINDING_HANDLE *v17; // rdi
  RPC_STATUS v18; // ebx
  unsigned __int16 *v19; // rdx
  unsigned int v20; // r9d
  __int64 v21; // rax
  __int64 v22; // rbx
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rsi
  RPC_WSTR String; // [rsp+88h] [rbp+10h] BYREF

  String = 0;
  a5 = 0;
  v12 = 0;
  v15 = wcsicmp_0(a3, L"ncalrpc");
  v16 = RpcStringBindingComposeW(0, a3, ServerPrincName, a4, (RPC_WSTR)L"Security=Impersonation Dynamic True", &String);
  v17 = Binding;
  v18 = v16;
  if ( !v16 )
  {
    v18 = RpcBindingFromStringBindingW(String, Binding);
    RpcStringFreeW(&String);
    if ( !v18 )
    {
      v12 = 1;
      if ( v15 )
      {
        if ( ServerPrincName )
        {
          v21 = -1;
          do
            ++v21;
          while ( ServerPrincName[v21] );
          v22 = (unsigned int)(v21 + 8);
          v23 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v22);
          v24 = v23;
          if ( v23 )
          {
            if ( (int)StringCchPrintfW(v23, (unsigned int)v22, L"host/%s", ServerPrincName) >= 0 )
            {
              v18 = RpcBindingSetAuthInfoExW(*v17, v24, 6u, 9u, 0, 0, 0);
              LocalFree(v24);
              goto LABEL_14;
            }
            LocalFree(v24);
          }
        }
        v20 = 9;
        v19 = ServerPrincName;
      }
      else
      {
        v19 = 0;
        v20 = 10;
      }
      v18 = RpcBindingSetAuthInfoExW(*v17, v19, 6u, v20, 0, 0, 0);
    }
  }
LABEL_14:
  if ( a5 )
    RpcStringFreeW(&a5);
  if ( !v18 )
    return 0;
  if ( v12 )
  {
    if ( *v17 )
      RpcBindingFree(v17);
    *v17 = 0;
  }
  return I_RpcMapWin32Status(v18);
}

```

## disassembly

```asm
0x18003fff4  mov     rax, rsp
0x18003fff7  mov     [rax+10h], rdx
0x18003fffb  push    rbx
0x18003fffc  push    rbp
0x18003fffd  push    rsi
0x18003fffe  push    rdi
0x18003ffff  push    r14
0x180040001  push    r15
0x180040003  sub     rsp, 48h
0x180040007  xor     r15d, r15d
0x18004000a  lea     rdx, aNcalrpc; "ncalrpc"
0x180040011  mov     rbp, rcx
0x180040014  mov     [rax+10h], r15
0x180040018  mov     rcx, r8; String1
0x18004001b  mov     [rax+28h], r15
0x18004001f  mov     r14d, r15d
0x180040022  mov     rbx, r9
0x180040025  mov     rdi, r8
0x180040028  call    _wcsicmp_0
0x18004002d  mov     esi, eax
0x18004002f  mov     r9, rbx; Endpoint
0x180040032  lea     rax, [rsp+78h+String]
0x18004003a  mov     r8, rbp; NetworkAddr
0x18004003d  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180040042  mov     rdx, rdi; ProtSeq
0x180040045  lea     rax, Options; "Security=Impersonation Dynamic True"
0x18004004c  xor     ecx, ecx; ObjUuid
0x18004004e  mov     [rsp+78h+Options], rax; Options
0x180040053  call    cs:__imp_RpcStringBindingComposeW
0x180040059  mov     rdi, [rsp+78h+Binding]
0x180040061  mov     ebx, eax
0x180040063  test    eax, eax
0x180040065  jnz     loc_180040166
0x18004006b  mov     rcx, [rsp+78h+String]; StringBinding
0x180040073  mov     rdx, rdi; Binding
0x180040076  call    cs:__imp_RpcBindingFromStringBindingW
0x18004007c  lea     rcx, [rsp+78h+String]; String
0x180040084  mov     ebx, eax
0x180040086  call    cs:__imp_RpcStringFreeW
0x18004008c  test    ebx, ebx
0x18004008e  jnz     loc_180040166
0x180040094  lea     r14d, [r15+1]
0x180040098  test    esi, esi
0x18004009a  jnz     short loc_1800400A7
0x18004009c  xor     edx, edx
0x18004009e  lea     r9d, [r15+0Ah]
0x1800400a2  jmp     loc_180040146
0x1800400a7  test    rbp, rbp
0x1800400aa  jz      loc_18004013D
0x1800400b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800400b4  inc     rax
0x1800400b7  cmp     [rbp+rax*2+0], r15w
0x1800400bd  jnz     short loc_1800400B4
0x1800400bf  lea     rbx, [rax+8]
0x1800400c3  mov     ecx, 40h ; '@'; uFlags
0x1800400c8  mov     ebx, ebx
0x1800400ca  lea     rdx, [rbx+rbx]; uBytes
0x1800400ce  call    cs:__imp_LocalAlloc
0x1800400d4  mov     rsi, rax
0x1800400d7  test    rax, rax
0x1800400da  jz      short loc_18004013D
0x1800400dc  mov     r9, rbp
0x1800400df  lea     r8, aHostS; "host/%s"
0x1800400e6  mov     edx, ebx; unsigned __int64
0x1800400e8  mov     rcx, rax; unsigned __int16 *
0x1800400eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800400f0  mov     ebx, eax
0x1800400f2  test    eax, eax
0x1800400f4  jns     short loc_180040102
0x1800400f6  mov     rcx, rsi; hMem
0x1800400f9  call    cs:__imp_LocalFree
0x1800400ff  mov     rsi, r15
0x180040102  not     ebx
0x180040104  shr     ebx, 1Fh
0x180040107  test    ebx, ebx
0x180040109  jz      short loc_18004013D
0x18004010b  mov     rcx, [rdi]; Binding
0x18004010e  mov     r9d, 9; AuthnSvc
0x180040114  mov     [rsp+78h+SecurityQOS], r15; SecurityQOS
0x180040119  mov     rdx, rsi; ServerPrincName
0x18004011c  mov     dword ptr [rsp+78h+StringBinding], r15d; AuthzSvc
0x180040121  mov     [rsp+78h+Options], r15; AuthIdentity
0x180040126  lea     r8d, [r9-3]; AuthnLevel
0x18004012a  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180040130  mov     rcx, rsi; hMem
0x180040133  mov     ebx, eax
0x180040135  call    cs:__imp_LocalFree
0x18004013b  jmp     short loc_180040166
0x18004013d  mov     r9d, 9; AuthnSvc
0x180040143  mov     rdx, rbp; ServerPrincName
0x180040146  mov     rcx, [rdi]; Binding
0x180040149  mov     r8d, 6; AuthnLevel
0x18004014f  mov     [rsp+78h+SecurityQOS], r15; SecurityQOS
0x180040154  mov     dword ptr [rsp+78h+StringBinding], r15d; AuthzSvc
0x180040159  mov     [rsp+78h+Options], r15; AuthIdentity
0x18004015e  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180040164  mov     ebx, eax
0x180040166  cmp     [rsp+78h+arg_20], r15
0x18004016e  jz      short loc_18004017E
0x180040170  lea     rcx, [rsp+78h+arg_20]; String
0x180040178  call    cs:__imp_RpcStringFreeW
0x18004017e  test    ebx, ebx
0x180040180  jz      short loc_1800401A2
0x180040182  test    r14d, r14d
0x180040185  jz      short loc_180040198
0x180040187  cmp     [rdi], r15
0x18004018a  jz      short loc_180040195
0x18004018c  mov     rcx, rdi; Binding
0x18004018f  call    cs:__imp_RpcBindingFree
0x180040195  mov     [rdi], r15
0x180040198  mov     ecx, ebx; Status
0x18004019a  call    cs:__imp_I_RpcMapWin32Status
0x1800401a0  jmp     short loc_1800401A5
0x1800401a2  mov     eax, r15d
0x1800401a5  add     rsp, 48h
0x1800401a9  pop     r15
0x1800401ab  pop     r14
0x1800401ad  pop     rdi
0x1800401ae  pop     rsi
0x1800401af  pop     rbp
0x1800401b0  pop     rbx
0x1800401b1  retn
```
