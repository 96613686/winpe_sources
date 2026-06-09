# StartWinregRPCServer

- ea: `0x180008694`
- end: `0x180008827`
- name: `StartWinregRPCServer`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x180008694`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180008807`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180008807`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800087f6`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800087f6`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800087e5`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800087e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000879a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000879a`

## string_xrefs

- `0x180008702`: `Software\Microsoft\Windows NT\CurrentVersion\RemoteRegistry`
- `0x1800086dd`: `RemoteRegistry Interface`
- `0x180008722`: `RemoteRegistry Perflib Interface`

## pseudocode

```c
__int64 StartWinregRPCServer()
{
  int v1; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v2; // [rsp+48h] [rbp-B8h]
  const wchar_t *v3; // [rsp+50h] [rbp-B0h]
  __int64 v4; // [rsp+58h] [rbp-A8h]
  int v5; // [rsp+60h] [rbp-A0h]
  int v6; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v7; // [rsp+78h] [rbp-88h]
  __int128 v8; // [rsp+80h] [rbp-80h]
  int v9; // [rsp+90h] [rbp-70h]
  int v10; // [rsp+94h] [rbp-6Ch]
  int v11; // [rsp+98h] [rbp-68h]
  __int64 v12; // [rsp+A0h] [rbp-60h]
  __int64 v13; // [rsp+A8h] [rbp-58h]
  const wchar_t *v14; // [rsp+B0h] [rbp-50h]
  __int64 v15; // [rsp+B8h] [rbp-48h]
  int v16; // [rsp+C0h] [rbp-40h]
  __int64 *v17; // [rsp+C8h] [rbp-38h]
  __int128 v18; // [rsp+D0h] [rbp-30h]
  int v19; // [rsp+E0h] [rbp-20h]
  int v20; // [rsp+E4h] [rbp-1Ch]
  int v21; // [rsp+E8h] [rbp-18h]
  void *v22; // [rsp+F0h] [rbp-10h]
  __int64 v23; // [rsp+F8h] [rbp-8h]
  const wchar_t *v24; // [rsp+100h] [rbp+0h]
  __int64 v25; // [rsp+108h] [rbp+8h]
  int pvData; // [rsp+120h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+128h] [rbp+28h] BYREF

  if ( !g_svcsGlobalData )
    return 0;
  v6 = 0;
  v11 = -1;
  v10 = 1234;
  v20 = 1234;
  v7 = qword_1800214F0;
  v21 = -1;
  v14 = L"RemoteRegistry Interface";
  v8 = 0;
  v17 = qword_180021CF0;
  v9 = 1;
  v22 = &PerflibSecurityCallbackFn;
  v12 = 0;
  v24 = L"RemoteRegistry Perflib Interface";
  v2 = L"ncacn_np";
  v3 = L"\\PIPE\\winreg";
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 1;
  v23 = 0;
  v25 = 0;
  v1 = 0;
  v4 = 0;
  v5 = 10;
  pvData = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\RemoteRegistry",
    L"DisableIdleStop",
    0x10u,
    0,
    &pvData,
    &pcbData);
  if ( (unsigned int)((__int64 (__fastcall *)(int *, __int64, int *, __int64, int, __int64 (__fastcall *)(), _QWORD, __int64 *))RpcServerInterfaceGroupCreateW)(
                       &v6,
                       2,
                       &v1,
                       1,
                       pvData != 0 ? -1 : 600,
                       RegSvcIdleCallback,
                       0,
                       &g_regSvcIfGroup) )
    return 0;
  if ( (unsigned int)RpcServerInterfaceGroupActivate(g_regSvcIfGroup) )
  {
    RpcServerInterfaceGroupClose(g_regSvcIfGroup);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180008694  mov     [rsp-8+arg_10], rbx
0x180008699  push    rbp
0x18000869a  lea     rbp, [rsp-10h]
0x18000869f  sub     rsp, 110h
0x1800086a6  xor     ebx, ebx
0x1800086a8  cmp     cs:g_svcsGlobalData, rbx
0x1800086af  jz      loc_18000880D
0x1800086b5  or      ecx, 0FFFFFFFFh
0x1800086b8  mov     [rsp+110h+var_A0], ebx
0x1800086bc  mov     edx, 4D2h
0x1800086c1  mov     [rbp+10h+var_78], ecx
0x1800086c4  xorps   xmm0, xmm0
0x1800086c7  mov     [rbp+10h+var_7C], edx
0x1800086ca  lea     rax, qword_1800214F0
0x1800086d1  mov     [rbp+10h+var_2C], edx
0x1800086d4  mov     [rsp+110h+var_98], rax
0x1800086d9  lea     r9d, [rbx+10h]; dwFlags
0x1800086dd  lea     rax, aRemoteregistry_1; "RemoteRegistry Interface"
0x1800086e4  mov     [rbp+10h+var_28], ecx
0x1800086e7  mov     [rbp+10h+var_60], rax
0x1800086eb  lea     r8, Value; "DisableIdleStop"
0x1800086f2  lea     rax, qword_180021CF0
0x1800086f9  movdqa  [rbp+10h+var_90], xmm0
0x1800086fe  mov     [rbp+10h+var_48], rax
0x180008702  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180008709  lea     rax, PerflibSecurityCallbackFn
0x180008710  mov     [rbp+10h+var_80], 1
0x180008717  mov     [rbp+10h+var_20], rax
0x18000871b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008722  lea     rax, aRemoteregistry_0; "RemoteRegistry Perflib Interface"
0x180008729  mov     [rbp+10h+var_70], rbx
0x18000872d  mov     [rbp+10h+var_10], rax
0x180008731  lea     rax, aNcacnNp; "ncacn_np"
0x180008738  mov     [rsp+110h+var_C8], rax
0x18000873d  lea     rax, aPipeWinreg; "\\PIPE\\winreg"
0x180008744  mov     [rsp+110h+var_C0], rax
0x180008749  lea     rax, [rbp+10h+arg_8]
0x18000874d  mov     [rsp+110h+pcbData], rax; pcbData
0x180008752  lea     rax, [rbp+10h+arg_0]
0x180008756  mov     [rsp+110h+pvData], rax; pvData
0x18000875b  mov     [rsp+110h+pdwType], rbx; pdwType
0x180008760  mov     [rbp+10h+var_68], rbx
0x180008764  mov     [rbp+10h+var_58], rbx
0x180008768  mov     [rbp+10h+var_50], ebx
0x18000876b  movdqa  [rbp+10h+var_40], xmm0
0x180008770  mov     [rbp+10h+var_30], 1
0x180008777  mov     [rbp+10h+var_18], rbx
0x18000877b  mov     [rbp+10h+var_8], rbx
0x18000877f  mov     [rsp+110h+var_D0], ebx
0x180008783  mov     [rsp+110h+var_B8], rbx
0x180008788  mov     [rsp+110h+var_B0], 0Ah
0x180008790  mov     [rbp+10h+arg_0], ebx
0x180008793  mov     [rbp+10h+arg_8], 4
0x18000879a  call    cs:__imp_RegGetValueW
0x1800087a0  mov     eax, [rbp+10h+arg_0]
0x1800087a3  lea     r9d, [rbx+1]
0x1800087a7  neg     eax
0x1800087a9  lea     r8, [rsp+110h+var_D0]
0x1800087ae  lea     rax, g_regSvcIfGroup
0x1800087b5  mov     [rsp+110h+var_D8], rax
0x1800087ba  lea     edx, [rbx+2]
0x1800087bd  sbb     ecx, ecx
0x1800087bf  mov     [rsp+110h+pcbData], rbx
0x1800087c4  and     ecx, 0FFFFFDA7h
0x1800087ca  lea     rax, RegSvcIdleCallback
0x1800087d1  add     ecx, 258h
0x1800087d7  mov     [rsp+110h+pvData], rax
0x1800087dc  mov     dword ptr [rsp+110h+pdwType], ecx
0x1800087e0  lea     rcx, [rsp+110h+var_A0]
0x1800087e5  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x1800087eb  test    eax, eax
0x1800087ed  jnz     short loc_18000880D
0x1800087ef  mov     rcx, cs:g_regSvcIfGroup
0x1800087f6  call    cs:__imp_RpcServerInterfaceGroupActivate
0x1800087fc  test    eax, eax
0x1800087fe  jz      short loc_180008820
0x180008800  mov     rcx, cs:g_regSvcIfGroup
0x180008807  call    cs:__imp_RpcServerInterfaceGroupClose
0x18000880d  xor     eax, eax
0x18000880f  mov     rbx, [rsp+110h+arg_10]
0x180008817  add     rsp, 110h
0x18000881e  pop     rbp
0x18000881f  retn
0x180008820  mov     eax, 1
0x180008825  jmp     short loc_18000880F
```
