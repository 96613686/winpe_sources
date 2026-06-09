# PlaiGetBinding(void * *)

- ea: `0x18002a5c8`
- end: `0x18002aa28`
- name: `?PlaiGetBinding@@YAJPEAPEAX@Z`
- size: `1120`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006da34`
- `0x1800e23b4`
- `0x1800ee324`
- `0x1800fed14`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002a5c8`
- `0x18002b3a0`
- `0x18010b2f8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a62e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a62e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a741`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a741`
- `RPCRT4!RpcStringFreeW` at `0x18002a9f3`
- `RPCRT4!RpcStringFreeW` at `0x18002a9f3`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002a81c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002a81c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002a8a8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002a8a8`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18002a943`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18002a943`
- `RPCRT4!RpcBindingFree` at `0x18002a9e3`
- `RPCRT4!RpcBindingFree` at `0x18002a9e3`

## string_xrefs

- `0x18002a60a`: `System\CurrentControlSet\Services\PLA\Configuration`

## pseudocode

```c
__int64 __fastcall PlaiGetBinding(void **a1)
{
  LSTATUS v2; // eax
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rax
  int *v6; // r9
  int *v7; // rcx
  LSTATUS v8; // eax
  int v9; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  RPC_STATUS v12; // eax
  int v13; // eax
  __int64 v14; // rax
  RPC_STATUS v15; // eax
  int v16; // eax
  __int64 v17; // rax
  RPC_STATUS v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  RPC_WSTR StringBinding; // [rsp+98h] [rbp-68h] BYREF
  DWORD Type[4]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE Data[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v30; // [rsp+FEh] [rbp-2h]
  unsigned __int16 v31[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v32[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v33[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v34[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v35[64]; // [rsp+300h] [rbp+200h] BYREF

  Binding = 0;
  StringBinding = 0;
  hKey = 0;
  Type[0] = 0;
  cbData = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\PLA\\Configuration", 0, 1u, &hKey);
  v3 = PlaiHResultFromWin32(v2);
  v4 = v3;
  if ( v3 < 0 )
  {
    v22 = 0;
    v23 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v31, 0x4000000000000800uLL);
      v5 = -1;
      do
        ++v5;
      while ( v31[v5] );
      v6 = &v23;
      v7 = &v22;
      goto LABEL_8;
    }
    goto LABEL_42;
  }
  cbData = 80;
  v8 = RegQueryValueExW(hKey, L"RPCEndPoint", 0, Type, Data, &cbData);
  v9 = PlaiHResultFromWin32(v8);
  v4 = v9;
  if ( v9 < 0 )
  {
    v23 = 0;
    v22 = v9;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_42;
    }
    PlaiWhoAmI(v32, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v32[v10] );
    goto LABEL_15;
  }
  if ( cbData < 0x50 )
  {
    v11 = cbData & 0xFFFFFFFE;
    if ( v11 >= 0x50 )
      _report_rangecheckfailure();
    *(_WORD *)&Data[v11] = 0;
  }
  else
  {
    v30 = 0;
  }
  v12 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)Data, 0, &StringBinding);
  v13 = PlaiHResultFromWin32(v12);
  v4 = v13;
  if ( v13 < 0 )
  {
    v23 = 0;
    v22 = v13;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_42;
    }
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v33[v14] );
    goto LABEL_15;
  }
  v15 = RpcBindingFromStringBindingW(StringBinding, &Binding);
  v16 = PlaiHResultFromWin32(v15);
  v4 = v16;
  if ( v16 < 0 )
  {
    v23 = 0;
    v22 = v16;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_42;
    }
    PlaiWhoAmI(v34, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v34[v17] );
LABEL_15:
    v6 = &v22;
    v7 = &v23;
LABEL_8:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v6, 4, byte_180147320, 1, v7, 4);
    goto LABEL_42;
  }
  v18 = RpcBindingSetAuthInfoW(Binding, 0, 6u, 0xFFFFFFFF, 0, 0);
  v19 = PlaiHResultFromWin32(v18);
  v4 = v19;
  if ( v19 >= 0 )
  {
    *a1 = Binding;
    goto LABEL_42;
  }
  v23 = 0;
  v22 = v19;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v35, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v35[v20] );
    goto LABEL_15;
  }
LABEL_42:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 < 0 && Binding )
    RpcBindingFree(&Binding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002a5c8  mov     [rsp-8+arg_8], rbx
0x18002a5cd  mov     [rsp-8+arg_10], rsi
0x18002a5d2  push    rbp
0x18002a5d3  push    rdi
0x18002a5d4  push    r14
0x18002a5d6  lea     rbp, [rsp-290h]
0x18002a5de  sub     rsp, 390h
0x18002a5e5  mov     rax, cs:__security_cookie
0x18002a5ec  xor     rax, rsp
0x18002a5ef  mov     [rbp+2A0h+var_20], rax
0x18002a5f6  xor     esi, esi
0x18002a5f8  lea     rax, [rbp+2A0h+hKey]
0x18002a5fc  mov     rdi, rcx
0x18002a5ff  mov     [rbp+2A0h+Binding], rsi
0x18002a603  xor     r8d, r8d; ulOptions
0x18002a606  mov     [rbp+2A0h+StringBinding], rsi
0x18002a60a  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\PL"...
0x18002a611  mov     [rbp+2A0h+hKey], rsi
0x18002a615  lea     r14d, [rsi+1]
0x18002a619  mov     [rbp+2A0h+Type], esi
0x18002a61c  mov     r9d, r14d; samDesired
0x18002a61f  mov     [rbp+2A0h+cbData], esi
0x18002a622  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a629  mov     [rsp+3A0h+phkResult], rax; phkResult
0x18002a62e  call    cs:__imp_RegOpenKeyExW
0x18002a634  mov     ecx, eax; unsigned int
0x18002a636  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a63b  mov     ebx, eax
0x18002a63d  test    eax, eax
0x18002a63f  jns     loc_18002A716
0x18002a645  cmp     dword ptr cs:xmmword_180169738, esi
0x18002a64b  mov     [rsp+3A0h+var_330], esi
0x18002a64f  mov     [rsp+3A0h+var_328], eax
0x18002a653  jz      loc_18002A9C2
0x18002a659  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a663  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a66a  jz      loc_18002A9C2
0x18002a670  mov     rax, cs:qword_180169748
0x18002a677  and     rax, rdx
0x18002a67a  cmp     cs:qword_180169748, rax
0x18002a681  jnz     loc_18002A9C2
0x18002a687  lea     rcx, [rbp+2A0h+var_2A0]; unsigned __int16 *
0x18002a68b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a690  lea     rcx, [rbp+2A0h+var_2A0]
0x18002a694  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a698  inc     rax
0x18002a69b  cmp     [rcx+rax*2], si
0x18002a69f  jnz     short loc_18002A698
0x18002a6a1  lea     ecx, [rax+rax]
0x18002a6a4  add     rcx, 2
0x18002a6a8  lea     rax, [rbp+2A0h+var_2A0]
0x18002a6ac  mov     [rsp+3A0h+var_340], rcx
0x18002a6b1  lea     r9, [rsp+3A0h+var_328]
0x18002a6b6  lea     rcx, [rsp+3A0h+var_330]
0x18002a6bb  mov     [rsp+3A0h+var_348], rax
0x18002a6c0  lea     rdx, PLA_EVENT_ERROR
0x18002a6c7  mov     [rsp+3A0h+var_350], 0Fh
0x18002a6d0  lea     rax, aPlaigetbinding; "PlaiGetBinding"
0x18002a6d7  mov     [rsp+3A0h+var_358], rax
0x18002a6dc  mov     eax, 4
0x18002a6e1  mov     [rsp+3A0h+var_360], rax
0x18002a6e6  mov     [rsp+3A0h+var_368], rcx
0x18002a6eb  lea     rcx, byte_180147320
0x18002a6f2  mov     [rsp+3A0h+var_370], r14
0x18002a6f7  mov     [rsp+3A0h+lpcbData], rcx
0x18002a6fc  lea     r8d, [rax+1]
0x18002a700  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002a707  mov     [rsp+3A0h+phkResult], rax
0x18002a70c  call    EventingWriteEvent
0x18002a711  jmp     loc_18002A9C2
0x18002a716  mov     rcx, [rbp+2A0h+hKey]; hKey
0x18002a71a  lea     rax, [rbp+2A0h+cbData]
0x18002a71e  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x18002a723  lea     r9, [rbp+2A0h+Type]; lpType
0x18002a727  lea     rax, [rbp+2A0h+Data]
0x18002a72b  mov     [rbp+2A0h+cbData], 50h ; 'P'
0x18002a732  xor     r8d, r8d; lpReserved
0x18002a735  mov     [rsp+3A0h+phkResult], rax; lpData
0x18002a73a  lea     rdx, ValueName; "RPCEndPoint"
0x18002a741  call    cs:__imp_RegQueryValueExW
0x18002a747  mov     ecx, eax; unsigned int
0x18002a749  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a74e  mov     ebx, eax
0x18002a750  test    eax, eax
0x18002a752  jns     loc_18002A7DC
0x18002a758  cmp     dword ptr cs:xmmword_180169738, esi
0x18002a75e  mov     [rsp+3A0h+var_328], esi
0x18002a762  mov     [rsp+3A0h+var_330], eax
0x18002a766  jz      loc_18002A9C2
0x18002a76c  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a776  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a77d  jz      loc_18002A9C2
0x18002a783  mov     rax, cs:qword_180169748
0x18002a78a  and     rax, rdx
0x18002a78d  cmp     cs:qword_180169748, rax
0x18002a794  jnz     loc_18002A9C2
0x18002a79a  lea     rcx, [rbp+2A0h+var_220]; unsigned __int16 *
0x18002a7a1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a7a6  lea     rcx, [rbp+2A0h+var_220]
0x18002a7ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a7b1  inc     rax
0x18002a7b4  cmp     [rcx+rax*2], si
0x18002a7b8  jnz     short loc_18002A7B1
0x18002a7ba  lea     ecx, [rax+rax]
0x18002a7bd  lea     rax, [rbp+2A0h+var_220]
0x18002a7c4  add     rcx, 2
0x18002a7c8  lea     r9, [rsp+3A0h+var_330]
0x18002a7cd  mov     [rsp+3A0h+var_340], rcx
0x18002a7d2  lea     rcx, [rsp+3A0h+var_328]
0x18002a7d7  jmp     loc_18002A6BB
0x18002a7dc  cmp     [rbp+2A0h+cbData], 50h ; 'P'
0x18002a7e0  jb      short loc_18002A7E8
0x18002a7e2  mov     [rbp+2A0h+var_2A2], si
0x18002a7e6  jmp     short loc_18002A7FE
0x18002a7e8  mov     ecx, [rbp+2A0h+cbData]
0x18002a7eb  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002a7ef  cmp     rcx, 50h ; 'P'
0x18002a7f3  jnb     loc_18002AA22
0x18002a7f9  mov     word ptr [rbp+rcx+2A0h+Data], si
0x18002a7fe  lea     rax, [rbp+2A0h+StringBinding]
0x18002a802  xor     r8d, r8d; NetworkAddr
0x18002a805  mov     [rsp+3A0h+lpcbData], rax; StringBinding
0x18002a80a  lea     r9, [rbp+2A0h+Data]; Endpoint
0x18002a80e  lea     rdx, Protseq; "ncalrpc"
0x18002a815  mov     [rsp+3A0h+phkResult], rsi; Options
0x18002a81a  xor     ecx, ecx; ObjUuid
0x18002a81c  call    cs:__imp_RpcStringBindingComposeW
0x18002a822  mov     ecx, eax; unsigned int
0x18002a824  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a829  mov     ebx, eax
0x18002a82b  test    eax, eax
0x18002a82d  jns     short loc_18002A8A0
0x18002a82f  cmp     dword ptr cs:xmmword_180169738, esi
0x18002a835  mov     [rsp+3A0h+var_328], esi
0x18002a839  mov     [rsp+3A0h+var_330], eax
0x18002a83d  jz      loc_18002A9C2
0x18002a843  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a84d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a854  jz      loc_18002A9C2
0x18002a85a  mov     rax, cs:qword_180169748
0x18002a861  and     rax, rdx
0x18002a864  cmp     cs:qword_180169748, rax
0x18002a86b  jnz     loc_18002A9C2
0x18002a871  lea     rcx, [rbp+2A0h+var_1A0]; unsigned __int16 *
0x18002a878  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a87d  lea     rcx, [rbp+2A0h+var_1A0]
0x18002a884  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a888  inc     rax
0x18002a88b  cmp     [rcx+rax*2], si
0x18002a88f  jnz     short loc_18002A888
0x18002a891  lea     ecx, [rax+rax]
0x18002a894  lea     rax, [rbp+2A0h+var_1A0]
0x18002a89b  jmp     loc_18002A7C4
0x18002a8a0  mov     rcx, [rbp+2A0h+StringBinding]; StringBinding
0x18002a8a4  lea     rdx, [rbp+2A0h+Binding]; Binding
0x18002a8a8  call    cs:__imp_RpcBindingFromStringBindingW
0x18002a8ae  mov     ecx, eax; unsigned int
0x18002a8b0  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a8b5  mov     ebx, eax
0x18002a8b7  test    eax, eax
0x18002a8b9  jns     short loc_18002A92C
0x18002a8bb  cmp     dword ptr cs:xmmword_180169738, esi
0x18002a8c1  mov     [rsp+3A0h+var_328], esi
0x18002a8c5  mov     [rsp+3A0h+var_330], eax
0x18002a8c9  jz      loc_18002A9C2
0x18002a8cf  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a8d9  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a8e0  jz      loc_18002A9C2
0x18002a8e6  mov     rax, cs:qword_180169748
0x18002a8ed  and     rax, rdx
0x18002a8f0  cmp     cs:qword_180169748, rax
0x18002a8f7  jnz     loc_18002A9C2
0x18002a8fd  lea     rcx, [rbp+2A0h+var_120]; unsigned __int16 *
0x18002a904  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a909  lea     rcx, [rbp+2A0h+var_120]
0x18002a910  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a914  inc     rax
0x18002a917  cmp     [rcx+rax*2], si
0x18002a91b  jnz     short loc_18002A914
0x18002a91d  lea     ecx, [rax+rax]
0x18002a920  lea     rax, [rbp+2A0h+var_120]
0x18002a927  jmp     loc_18002A7C4
0x18002a92c  mov     rcx, [rbp+2A0h+Binding]; Binding
0x18002a930  xor     edx, edx; ServerPrincName
0x18002a932  mov     dword ptr [rsp+3A0h+lpcbData], esi; AuthzSvc
0x18002a936  or      r9d, 0FFFFFFFFh; AuthnSvc
0x18002a93a  mov     [rsp+3A0h+phkResult], rsi; AuthIdentity
0x18002a93f  lea     r8d, [rdx+6]; AuthnLevel
0x18002a943  call    cs:__imp_RpcBindingSetAuthInfoW
0x18002a949  mov     ecx, eax; unsigned int
0x18002a94b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a950  mov     ebx, eax
0x18002a952  test    eax, eax
0x18002a954  jns     short loc_18002A9BB
0x18002a956  cmp     dword ptr cs:xmmword_180169738, esi
0x18002a95c  mov     [rsp+3A0h+var_328], esi
0x18002a960  mov     [rsp+3A0h+var_330], eax
0x18002a964  jz      short loc_18002A9C2
0x18002a966  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a970  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a977  jz      short loc_18002A9C2
0x18002a979  mov     rax, cs:qword_180169748
0x18002a980  and     rax, rdx
0x18002a983  cmp     cs:qword_180169748, rax
0x18002a98a  jnz     short loc_18002A9C2
0x18002a98c  lea     rcx, [rbp+2A0h+var_A0]; unsigned __int16 *
0x18002a993  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a998  lea     rcx, [rbp+2A0h+var_A0]
0x18002a99f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a9a3  inc     rax
0x18002a9a6  cmp     [rcx+rax*2], si
0x18002a9aa  jnz     short loc_18002A9A3
0x18002a9ac  lea     ecx, [rax+rax]
0x18002a9af  lea     rax, [rbp+2A0h+var_A0]
0x18002a9b6  jmp     loc_18002A7C4
0x18002a9bb  mov     rax, [rbp+2A0h+Binding]
0x18002a9bf  mov     [rdi], rax
0x18002a9c2  mov     rcx, [rbp+2A0h+hKey]; hKey
0x18002a9c6  test    rcx, rcx
0x18002a9c9  jz      short loc_18002A9D5
0x18002a9cb  call    cs:__imp_RegCloseKey
0x18002a9d1  mov     [rbp+2A0h+hKey], rsi
0x18002a9d5  test    ebx, ebx
0x18002a9d7  jns     short loc_18002A9E9
0x18002a9d9  cmp     [rbp+2A0h+Binding], rsi
0x18002a9dd  jz      short loc_18002A9E9
0x18002a9df  lea     rcx, [rbp+2A0h+Binding]; Binding
0x18002a9e3  call    cs:__imp_RpcBindingFree
0x18002a9e9  cmp     [rbp+2A0h+StringBinding], rsi
0x18002a9ed  jz      short loc_18002A9F9
0x18002a9ef  lea     rcx, [rbp+2A0h+StringBinding]; String
0x18002a9f3  call    cs:__imp_RpcStringFreeW
0x18002a9f9  mov     eax, ebx
0x18002a9fb  mov     rcx, [rbp+2A0h+var_20]
0x18002aa02  xor     rcx, rsp; StackCookie
0x18002aa05  call    __security_check_cookie
0x18002aa0a  lea     r11, [rsp+3A0h+var_10]
0x18002aa12  mov     rbx, [r11+28h]
0x18002aa16  mov     rsi, [r11+30h]
0x18002aa1a  mov     rsp, r11
0x18002aa1d  pop     r14
0x18002aa1f  pop     rdi
0x18002aa20  pop     rbp
0x18002aa21  retn
0x18002aa22  call    __report_rangecheckfailure
```
