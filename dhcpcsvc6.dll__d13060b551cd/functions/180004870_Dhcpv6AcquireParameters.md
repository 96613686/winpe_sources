# Dhcpv6AcquireParameters

- ea: `0x180004870`
- end: `0x1800049d2`
- name: `Dhcpv6AcquireParameters`
- size: `354`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001ff0`
- `0x180003650`
- `0x180004870`
- `0x1800072fc`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004924`
- `RPCRT4!NdrClientCall3` at `0x180004924`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800048e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004940`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000495e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800048e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004940`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000495e`

## pseudocode

```c
__int64 __fastcall Dhcpv6AcquireParameters(const WCHAR *a1)
{
  int v2; // ecx
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v5; // ecx
  CLIENT_CALL_RETURN v6; // rax
  LPWSTR v7; // rax
  int v8; // ecx
  int v9; // r8d
  NET_LUID v11; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+60h] [rbp+18h]

  v11.Value = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 10, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 11, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
    goto LABEL_13;
  }
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_13;
  }
  Pointer = Dhcpv6AdapterNameToIfId(a1, &v11);
  if ( Pointer )
  {
LABEL_13:
    if ( (xmmword_18000F160 & 0x10) != 0 )
      WPP_SF_SD(v2, 14, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v5,
      Pointer + 12,
      (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
      (_DWORD)a1,
      (__int64)CommandLineW);
  }
  v12.Simple = 0;
  v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0).Pointer;
  Pointer = (unsigned int)v6.Pointer;
  v12.Pointer = v6.Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v7 = GetCommandLineW();
    WPP_SF_DSS(v8, 13, v9, Pointer, (__int64)a1, (__int64)v7);
    goto LABEL_13;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180004870  mov     [rsp+arg_18], rbx
0x180004875  mov     [rsp+arg_0], rcx
0x18000487a  push    rdi
0x18000487b  sub     rsp, 40h
0x18000487f  mov     rdi, rcx
0x180004882  mov     [rsp+48h+arg_8], 0
0x18000488b  test    byte ptr cs:xmmword_18000F160, 10h
0x180004892  jz      short loc_1800048A8
0x180004894  mov     edx, 0Ah
0x180004899  mov     r9, rcx
0x18000489c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800048a3  call    WPP_SF_S
0x1800048a8  call    DhcpIsFSEGuestSystem
0x1800048ad  test    eax, eax
0x1800048af  jnz     loc_18000497D
0x1800048b5  test    rdi, rdi
0x1800048b8  jnz     short loc_1800048C2
0x1800048ba  lea     ebx, [rax+57h]
0x1800048bd  jmp     loc_1800049A4
0x1800048c2  lea     rdx, [rsp+48h+arg_8]
0x1800048c7  mov     rcx, rdi
0x1800048ca  call    Dhcpv6AdapterNameToIfId
0x1800048cf  mov     ebx, eax
0x1800048d1  test    eax, eax
0x1800048d3  jnz     loc_1800049A4
0x1800048d9  test    byte ptr cs:xmmword_18000F160, 10h
0x1800048e0  jz      short loc_180004900
0x1800048e2  call    cs:__imp_GetCommandLineW
0x1800048e8  lea     edx, [rbx+0Ch]
0x1800048eb  mov     [rsp+48h+var_28], rax
0x1800048f0  mov     r9, rdi
0x1800048f3  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800048fa  call    WPP_SF_SS
0x1800048ff  nop
0x180004900  mov     [rsp+48h+arg_10], 0
0x180004909  lea     rax, [rsp+48h+arg_8]
0x18000490e  mov     [rsp+48h+var_28], rax
0x180004913  xor     r9d, r9d
0x180004916  xor     r8d, r8d; pReturnValue
0x180004919  lea     edx, [r9+5]; nProcNum
0x18000491d  lea     rcx, pProxyInfo; pProxyInfo
0x180004924  call    cs:__imp_NdrClientCall3
0x18000492a  mov     rbx, rax
0x18000492d  mov     [rsp+48h+arg_10], rax
0x180004932  mov     [rsp+48h+var_18], eax
0x180004936  jmp     short loc_180004955
0x180004938  mov     edi, eax
0x18000493a  mov     ebx, eax
0x18000493c  mov     [rsp+48h+var_18], eax
0x180004940  call    cs:__imp_GetCommandLineW
0x180004946  mov     rdx, rax
0x180004949  mov     ecx, ebx
0x18000494b  call    TraceRpcException
0x180004950  mov     rdi, [rsp+48h+arg_0]
0x180004955  test    byte ptr cs:xmmword_18000F160, 10h
0x18000495c  jz      short loc_1800049C5
0x18000495e  call    cs:__imp_GetCommandLineW
0x180004964  mov     edx, 0Dh
0x180004969  mov     [rsp+48h+var_20], rax
0x18000496e  mov     [rsp+48h+var_28], rdi
0x180004973  mov     r9d, ebx
0x180004976  call    WPP_SF_DSS
0x18000497b  jmp     short loc_1800049A4
0x18000497d  mov     r9d, 32h ; '2'
0x180004983  mov     ebx, r9d
0x180004986  test    byte ptr cs:xmmword_18000F160, 2
0x18000498d  jz      short loc_1800049A4
0x18000498f  lea     edx, [r9-27h]
0x180004993  mov     ecx, 401h
0x180004998  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000499f  call    WPP_SF_D
0x1800049a4  test    byte ptr cs:xmmword_18000F160, 10h
0x1800049ab  jz      short loc_1800049C5
0x1800049ad  mov     edx, 0Eh
0x1800049b2  mov     dword ptr [rsp+48h+var_28], ebx
0x1800049b6  mov     r9, rdi
0x1800049b9  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800049c0  call    WPP_SF_SD
0x1800049c5  mov     eax, ebx
0x1800049c7  mov     rbx, [rsp+48h+arg_18]
0x1800049cc  add     rsp, 40h
0x1800049d0  pop     rdi
0x1800049d1  retn
0x180007a0c  push    rbp
0x180007a0e  sub     rsp, 30h
0x180007a12  mov     rbp, rdx
0x180007a15  mov     rcx, [rcx]
0x180007a18  mov     ecx, [rcx]; ExceptionCode
0x180007a1a  call    cs:__imp_I_RpcExceptionFilter
0x180007a20  nop
0x180007a21  add     rsp, 30h
0x180007a25  pop     rbp
0x180007a26  retn
```
