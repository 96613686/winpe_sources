# RpcpBindRpc

- ea: `0x18004f730`
- end: `0x18004f9eb`
- name: `RpcpBindRpc`
- size: `699`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004f6c0`

## callees

- `0x180024568`
- `0x18003a730`
- `0x18003b28c`
- `0x18004f730`
- `0x1800510ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004f818`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004f87d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004f818`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004f87d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f7cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f852`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f8ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f7cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f852`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f8ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9bf`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004f950`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004f950`
- `RPCRT4!RpcStringFreeW` at `0x18004f97c`
- `RPCRT4!RpcStringFreeW` at `0x18004f97c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004f970`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004f970`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  char *v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  unsigned __int16 *v16; // rdi
  __int64 v17; // r11
  unsigned __int64 v18; // r8
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  RPC_STATUS v21; // ebx
  RPC_STATUS v22; // ebx
  int v23; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = Src;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !Src )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&Src[2 * v7] );
  if ( !*(_WORD *)Src )
    goto LABEL_26;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_27;
    v5 = Src + 4;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = (unsigned __int64)v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( *(_WORD *)&v5[2 * v7 - 2] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(wcsnicmp(v13, (const wchar_t *)v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_41;
  }
  if ( (int)RtlStringCopyWorkerW(v14, 14, v15, L"\\PIPE\\") >= 0 )
  {
    v18 = (unsigned int)v17;
    v19 = v16;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
    {
      v20 = (v17 - v18) & ((unsigned __int128)-(__int128)v18 >> 64);
      if ( (int)RtlStringCopyWorkerW(&v16[v20], v17 - v20, v18, L"lsarpc") >= 0 )
      {
        v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v16, 0, &String);
        LocalFree(v16);
        if ( !v21 )
        {
          v22 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v22 )
          {
            *a4 = 0;
            v23 = -1073741534;
            if ( (unsigned int)(v22 - 1706) > 1 )
              v23 = -1073741801;
            v8 = v23;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_41;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v16);
  v8 = -1073741811;
LABEL_41:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x18004f730  mov     [rsp-38h+arg_8], rbx
0x18004f735  push    rbp
0x18004f736  push    rsi
0x18004f737  push    rdi
0x18004f738  push    r12
0x18004f73a  push    r13
0x18004f73c  push    r14
0x18004f73e  push    r15
0x18004f740  mov     rbp, rsp
0x18004f743  sub     rsp, 70h
0x18004f747  mov     rax, cs:__security_cookie
0x18004f74e  xor     rax, rsp
0x18004f751  mov     [rbp+var_10], rax
0x18004f755  xor     r13d, r13d
0x18004f758  mov     r12, r9
0x18004f75b  mov     [rbp+String], r13
0x18004f75f  mov     rdi, rcx
0x18004f762  mov     [rbp+nSize], r13d
0x18004f766  mov     r14d, r13d
0x18004f769  mov     [r9], r13
0x18004f76c  test    rcx, rcx
0x18004f76f  jz      loc_18004F8B0
0x18004f775  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004f779  inc     rbx
0x18004f77c  cmp     [rcx+rbx*2], r13w
0x18004f781  jnz     short loc_18004F779
0x18004f783  cmp     [rcx], r13w
0x18004f787  jz      loc_18004F8B0
0x18004f78d  mov     esi, 5Ch ; '\'
0x18004f792  cmp     [rcx], si
0x18004f795  jnz     short loc_18004F7C2
0x18004f797  cmp     [rcx+2], si
0x18004f79b  jnz     short loc_18004F7A3
0x18004f79d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x18004f7a1  jnz     short loc_18004F7AD
0x18004f7a3  mov     ebx, 0C0000122h
0x18004f7a8  jmp     loc_18004F9C5
0x18004f7ad  lea     rax, [rcx+4]
0x18004f7b1  mov     rsi, rdi
0x18004f7b4  test    rax, rax
0x18004f7b7  jz      loc_18004F8B3
0x18004f7bd  mov     rdi, rax
0x18004f7c0  jmp     short loc_18004F801
0x18004f7c2  lea     rdx, ds:6[rbx*2]; uBytes
0x18004f7ca  xor     ecx, ecx; uFlags
0x18004f7cc  call    cs:__imp_LocalAlloc
0x18004f7d2  mov     r14, rax
0x18004f7d5  test    rax, rax
0x18004f7d8  jnz     short loc_18004F7E4
0x18004f7da  mov     ebx, 0C0000017h
0x18004f7df  jmp     loc_18004F9C5
0x18004f7e4  lea     r8, ds:2[rbx*2]; Size
0x18004f7ec  mov     dword ptr [rax], 5C005Ch
0x18004f7f2  lea     rcx, [rax+4]; void *
0x18004f7f6  mov     rdx, rdi; Src
0x18004f7f9  call    memcpy_0
0x18004f7fe  mov     rsi, r14
0x18004f801  cmp     rbx, 0Fh
0x18004f805  ja      short loc_18004F83D
0x18004f807  lea     r8, [rbp+nSize]; nSize
0x18004f80b  mov     [rbp+nSize], 10h
0x18004f812  lea     rdx, [rbp+Buffer]; lpBuffer
0x18004f816  xor     ecx, ecx; NameType
0x18004f818  call    cs:__imp_GetComputerNameExW
0x18004f81e  test    eax, eax
0x18004f820  jz      short loc_18004F83D
0x18004f822  mov     eax, [rbp+nSize]
0x18004f825  cmp     rbx, rax
0x18004f828  jnz     short loc_18004F83D
0x18004f82a  mov     r8, rbx; MaxCount
0x18004f82d  lea     rcx, [rbp+Buffer]; String1
0x18004f831  mov     rdx, rdi; String2
0x18004f834  call    _wcsnicmp
0x18004f839  test    eax, eax
0x18004f83b  jz      short loc_18004F8B0
0x18004f83d  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x18004f843  lea     r15, [rbx-1]
0x18004f847  mov     edx, 20Ah; uBytes
0x18004f84c  cmovnz  r15, rbx
0x18004f850  xor     ecx, ecx; uFlags
0x18004f852  call    cs:__imp_LocalAlloc
0x18004f858  mov     rbx, rax
0x18004f85b  test    rax, rax
0x18004f85e  jnz     short loc_18004F86A
0x18004f860  mov     ebx, 0C0000017h
0x18004f865  jmp     loc_18004F9B7
0x18004f86a  lea     r8, [rbp+nSize]; nSize
0x18004f86e  mov     [rbp+nSize], 105h
0x18004f875  mov     rdx, rbx; lpBuffer
0x18004f878  mov     ecx, 3; NameType
0x18004f87d  call    cs:__imp_GetComputerNameExW
0x18004f883  test    eax, eax
0x18004f885  jz      short loc_18004F8A5
0x18004f887  mov     eax, [rbp+nSize]
0x18004f88a  cmp     r15, rax
0x18004f88d  jnz     short loc_18004F8A5
0x18004f88f  mov     r8, r15; MaxCount
0x18004f892  mov     rdx, rdi; String2
0x18004f895  mov     rcx, rbx; String1
0x18004f898  call    _wcsnicmp
0x18004f89d  neg     eax
0x18004f89f  sbb     rcx, rcx
0x18004f8a2  and     rsi, rcx
0x18004f8a5  mov     rcx, rbx; hMem
0x18004f8a8  call    cs:__imp_LocalFree
0x18004f8ae  jmp     short loc_18004F8B3
0x18004f8b0  mov     rsi, r13
0x18004f8b3  mov     edx, 1Ch; uBytes
0x18004f8b8  xor     ecx, ecx; uFlags
0x18004f8ba  call    cs:__imp_LocalAlloc
0x18004f8c0  mov     rdi, rax
0x18004f8c3  test    rax, rax
0x18004f8c6  jz      short loc_18004F860
0x18004f8c8  mov     r11d, 0Eh
0x18004f8ce  lea     r9, aPipe; "\\PIPE\\"
0x18004f8d5  mov     edx, r11d
0x18004f8d8  mov     rcx, rax
0x18004f8db  call    RtlStringCopyWorkerW
0x18004f8e0  test    eax, eax
0x18004f8e2  js      loc_18004F9A9
0x18004f8e8  mov     r8d, r11d
0x18004f8eb  mov     rax, rdi
0x18004f8ee  cmp     [rax], r13w
0x18004f8f2  jz      short loc_18004F8FE
0x18004f8f4  add     rax, 2
0x18004f8f8  sub     r8, 1
0x18004f8fc  jnz     short loc_18004F8EE
0x18004f8fe  mov     rcx, r11
0x18004f901  mov     rax, r8
0x18004f904  sub     rcx, r8
0x18004f907  neg     rax
0x18004f90a  sbb     rdx, rdx
0x18004f90d  and     rdx, rcx
0x18004f910  test    r8, r8
0x18004f913  jz      loc_18004F9A9
0x18004f919  sub     r11, rdx
0x18004f91c  lea     rcx, [rdi+rdx*2]
0x18004f920  mov     rdx, r11
0x18004f923  lea     r9, aLsarpc; "lsarpc"
0x18004f92a  call    RtlStringCopyWorkerW
0x18004f92f  test    eax, eax
0x18004f931  js      short loc_18004F9A9
0x18004f933  lea     rax, [rbp+String]
0x18004f937  mov     r9, rdi; Endpoint
0x18004f93a  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18004f93f  lea     rdx, ProtSeq; "ncacn_np"
0x18004f946  mov     r8, rsi; NetworkAddr
0x18004f949  mov     [rsp+70h+Options], r13; Options
0x18004f94e  xor     ecx, ecx; ObjUuid
0x18004f950  call    cs:__imp_RpcStringBindingComposeW
0x18004f956  mov     rcx, rdi; hMem
0x18004f959  mov     ebx, eax
0x18004f95b  call    cs:__imp_LocalFree
0x18004f961  test    ebx, ebx
0x18004f963  jnz     loc_18004F860
0x18004f969  mov     rcx, [rbp+String]; StringBinding
0x18004f96d  mov     rdx, r12; Binding
0x18004f970  call    cs:__imp_RpcBindingFromStringBindingW
0x18004f976  lea     rcx, [rbp+String]; String
0x18004f97a  mov     ebx, eax
0x18004f97c  call    cs:__imp_RpcStringFreeW
0x18004f982  test    ebx, ebx
0x18004f984  jz      short loc_18004F9A4
0x18004f986  lea     eax, [rbx-6AAh]
0x18004f98c  mov     [r12], r13
0x18004f990  mov     ebx, 0C0000017h
0x18004f995  cmp     eax, 1
0x18004f998  mov     ecx, 0C0000122h
0x18004f99d  cmova   ecx, ebx
0x18004f9a0  mov     ebx, ecx
0x18004f9a2  jmp     short loc_18004F9B7
0x18004f9a4  mov     ebx, r13d
0x18004f9a7  jmp     short loc_18004F9B7
0x18004f9a9  mov     rcx, rdi; hMem
0x18004f9ac  call    cs:__imp_LocalFree
0x18004f9b2  mov     ebx, 0C000000Dh
0x18004f9b7  test    r14, r14
0x18004f9ba  jz      short loc_18004F9C5
0x18004f9bc  mov     rcx, r14; hMem
0x18004f9bf  call    cs:__imp_LocalFree
0x18004f9c5  mov     eax, ebx
0x18004f9c7  mov     rcx, [rbp+var_10]
0x18004f9cb  xor     rcx, rsp; StackCookie
0x18004f9ce  call    __security_check_cookie
0x18004f9d3  mov     rbx, [rsp+70h+arg_8]
0x18004f9db  add     rsp, 70h
0x18004f9df  pop     r15
0x18004f9e1  pop     r14
0x18004f9e3  pop     r13
0x18004f9e5  pop     r12
0x18004f9e7  pop     rdi
0x18004f9e8  pop     rsi
0x18004f9e9  pop     rbp
0x18004f9ea  retn
```
