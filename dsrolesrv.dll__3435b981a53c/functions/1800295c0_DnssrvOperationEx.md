# DnssrvOperationEx

- ea: `0x1800295c0`
- end: `0x180029a59`
- name: `DnssrvOperationEx`
- size: `1177`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, char *String1)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000f970`
- `0x1800100c0`

## callees

- `0x1800237ac`
- `0x180028074`
- `0x180028e10`
- `0x1800295c0`
- `0x180029ea8`
- `0x18002a3e0`
- `0x18002a724`
- `0x18002a9c0`
- `0x18002b810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029979`
- `RPCRT4!NdrClientCall3` at `0x180029741`
- `RPCRT4!NdrClientCall3` at `0x1800297d4`
- `RPCRT4!NdrClientCall3` at `0x180029741`
- `RPCRT4!NdrClientCall3` at `0x1800297d4`
- `ntdll!_stricmp` at `0x180029674`
- `ntdll!_stricmp` at `0x18002968d`
- `ntdll!_stricmp` at `0x18002999b`
- `ntdll!_stricmp` at `0x180029674`
- `ntdll!_stricmp` at `0x18002968d`
- `ntdll!_stricmp` at `0x18002999b`

## string_xrefs

- `0x180029665`: `EnlistDirectoryPartition`

## pseudocode

```c
__int64 __fastcall DnssrvOperationEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, char *String1)
{
  RPC_BINDING_HANDLE v7; // rbx
  char v8; // r12
  int v9; // r13d
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int Pointer; // eax
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v18; // [rsp+20h] [rbp-88h]
  __int64 v19; // [rsp+28h] [rbp-80h]
  __int64 v20; // [rsp+30h] [rbp-78h]
  __int64 v21; // [rsp+40h] [rbp-68h]
  __int64 v22; // [rsp+50h] [rbp-58h]
  RPC_BINDING_HANDLE RPCBindingHandle; // [rsp+B8h] [rbp+10h]

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DSsDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, a5, v20, (__int64)String1, 0);
  }
  while ( 1 )
  {
    if ( !_stricmp(String1, "EnlistDirectoryPartition") || !_stricmp(String1, "TransferKeymasterRole") )
    {
      v8 = 2;
      v9 = 1;
    }
    if ( v10 == 1 )
      v8 |= 1u;
    Dnssrv_FreeRPCBindingHandle(v7);
    RPCBindingHandle = Dnssrv_CreateRPCBindingHandle(v12, v11, v8);
    if ( v10 )
    {
      LODWORD(v21) = 0;
      LODWORD(v20) = 0;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0,
                                0,
                                RPCBindingHandle,
                                0,
                                a5,
                                v20,
                                String1,
                                v21,
                                0).Pointer;
      v14 = Pointer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = 15;
        goto LABEL_21;
      }
    }
    else
    {
      LODWORD(v22) = 0;
      LODWORD(v21) = 0;
      LODWORD(v19) = 0;
      LODWORD(v18) = 458752;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                5u,
                                0,
                                RPCBindingHandle,
                                v18,
                                v19,
                                0,
                                a5,
                                v21,
                                String1,
                                v22,
                                0).Pointer;
      v14 = Pointer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = 14;
LABEL_21:
        WPP_SF_d(v15[2], v16, (unsigned int)&WPP_37d584b9184134be2c2c41d914906a97_Traceguids, Pointer);
        v15 = WPP_GLOBAL_Control;
      }
    }
    if ( v14 == 1825 || v14 == 1722 || v14 == 1753 || !v10 && (!v14 || v14 - 1700 > 0x53) )
      v10 = 2;
    else
      ++v10;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 && *((_BYTE *)v15 + 25) >= 4u )
      WPP_SF_d(v15[2], 16, (unsigned int)&WPP_37d584b9184134be2c2c41d914906a97_Traceguids, v14);
    if ( v10 >= 2 )
      break;
    v7 = RPCBindingHandle;
  }
  printExtendedRpcErrorInfo(v14);
  Dnssrv_FreeRPCBindingHandle(RPCBindingHandle);
  if ( !_stricmp(String1, "PrepareForDemotion") && v14 && (unsigned int)Dns_MaintainNtdsDependency() )
    v14 = 1068;
  if ( v9 && v14 == 1825 )
    return 9571;
  return v14;
}

```

## disassembly

```asm
0x1800295c0  mov     rax, rsp
0x1800295c3  mov     [rax+20h], r9
0x1800295c7  mov     [rax+18h], r8d
0x1800295cb  mov     [rax+10h], rdx
0x1800295cf  mov     [rax+8], ecx
0x1800295d2  push    rbx
0x1800295d3  push    rdi
0x1800295d4  push    r12
0x1800295d6  push    r13
0x1800295d8  push    r14
0x1800295da  sub     rsp, 80h
0x1800295e1  xor     r14d, r14d
0x1800295e4  mov     [rax-38h], r14
0x1800295e8  mov     [rax-48h], r14d
0x1800295ec  mov     [rax+30h], r14d
0x1800295f0  xor     ebx, ebx
0x1800295f2  xor     r12d, r12d
0x1800295f5  mov     [rsp+0A8h+arg_10], r12d
0x1800295fd  xor     r13d, r13d
0x180029600  mov     [rsp+0A8h+arg_0], r13d
0x180029608  xor     edi, edi
0x18002960a  mov     [rax-40h], edi
0x18002960d  lea     rax, WPP_GLOBAL_Control
0x180029614  mov     rcx, cs:WPP_GLOBAL_Control
0x18002961b  cmp     rcx, rax
0x18002961e  jz      short loc_180029653
0x180029620  test    byte ptr [rcx+1Ch], 4
0x180029624  jz      short loc_180029653
0x180029626  cmp     byte ptr [rcx+19h], 4
0x18002962a  jb      short loc_180029653
0x18002962c  mov     dword ptr [rsp+0A8h+var_68], ebx; char
0x180029630  mov     rax, [rsp+0A8h+String1]
0x180029638  mov     [rsp+0A8h+var_70], rax; __int64
0x18002963d  mov     rax, [rsp+0A8h+arg_20]
0x180029645  mov     [rsp+0A8h+var_80], rax; __int64
0x18002964a  mov     rcx, [rcx+10h]; LoggerHandle
0x18002964e  call    WPP_SF_DSsDsd
0x180029653  mov     [rsp+0A8h+arg_18], rbx
0x18002965b  jmp     short loc_180029665
0x18002965d  mov     rbx, [rsp+0A8h+arg_8]
0x180029665  lea     rdx, aEnlistdirector; "EnlistDirectoryPartition"
0x18002966c  mov     rcx, [rsp+0A8h+String1]; String1
0x180029674  call    cs:__imp__stricmp
0x18002967a  test    eax, eax
0x18002967c  jz      short loc_180029697
0x18002967e  lea     rdx, aTransferkeymas; "TransferKeymasterRole"
0x180029685  mov     rcx, [rsp+0A8h+String1]; String1
0x18002968d  call    cs:__imp__stricmp
0x180029693  test    eax, eax
0x180029695  jnz     short loc_1800296B2
0x180029697  mov     r12d, 2
0x18002969d  mov     [rsp+0A8h+arg_10], r12d
0x1800296a5  lea     r13d, [r12-1]
0x1800296aa  mov     [rsp+0A8h+arg_0], r13d
0x1800296b2  cmp     edi, 1
0x1800296b5  jnz     short loc_1800296C2
0x1800296b7  or      r12d, edi
0x1800296ba  mov     [rsp+0A8h+arg_10], r12d
0x1800296c2  mov     rcx, rbx
0x1800296c5  call    Dnssrv_FreeRPCBindingHandle
0x1800296ca  mov     r8d, r12d
0x1800296cd  call    Dnssrv_CreateRPCBindingHandle
0x1800296d2  mov     rcx, rax
0x1800296d5  mov     [rsp+0A8h+arg_8], rax
0x1800296dd  mov     r9, rax
0x1800296e0  xor     r8d, r8d; pReturnValue
0x1800296e3  lea     rcx, pProxyInfo; pProxyInfo
0x1800296ea  test    edi, edi
0x1800296ec  jnz     loc_180029789
0x1800296f2  mov     [rsp+0A8h+arg_40], r8
0x1800296fa  mov     rax, [rsp+0A8h+arg_18]
0x180029702  mov     [rsp+0A8h+var_50], rax
0x180029707  mov     eax, [rsp+0A8h+var_48]
0x18002970b  mov     dword ptr [rsp+0A8h+var_58], eax
0x18002970f  mov     rax, [rsp+0A8h+String1]
0x180029717  mov     [rsp+0A8h+var_60], rax
0x18002971c  mov     dword ptr [rsp+0A8h+var_68], edi
0x180029720  mov     rax, [rsp+0A8h+arg_20]
0x180029728  mov     [rsp+0A8h+var_70], rax
0x18002972d  mov     [rsp+0A8h+var_78], r8
0x180029732  mov     dword ptr [rsp+0A8h+var_80], edi
0x180029736  mov     dword ptr [rsp+0A8h+var_88], 70000h
0x18002973e  lea     edx, [rdi+5]; nProcNum
0x180029741  call    cs:__imp_NdrClientCall3
0x180029747  mov     rbx, rax
0x18002974a  mov     [rsp+0A8h+arg_40], rax
0x180029752  mov     [rsp+0A8h+var_3C], eax
0x180029756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002975d  lea     rdx, WPP_GLOBAL_Control
0x180029764  cmp     rcx, rdx
0x180029767  jz      loc_18002982A
0x18002976d  test    byte ptr [rcx+1Ch], 4
0x180029771  jz      loc_18002982A
0x180029777  cmp     byte ptr [rcx+19h], 4
0x18002977b  jb      loc_18002982A
0x180029781  lea     edx, [rdi+0Eh]
0x180029784  jmp     loc_180029809
0x180029789  mov     [rsp+0A8h+var_30], 0
0x180029792  mov     rax, [rsp+0A8h+arg_18]
0x18002979a  mov     [rsp+0A8h+var_60], rax
0x18002979f  mov     eax, [rsp+0A8h+var_48]
0x1800297a3  mov     dword ptr [rsp+0A8h+var_68], eax
0x1800297a7  mov     rax, [rsp+0A8h+String1]
0x1800297af  mov     [rsp+0A8h+var_70], rax
0x1800297b4  mov     dword ptr [rsp+0A8h+var_78], 0
0x1800297bc  mov     rax, [rsp+0A8h+arg_20]
0x1800297c4  mov     [rsp+0A8h+var_80], rax
0x1800297c9  mov     [rsp+0A8h+var_88], 0
0x1800297d2  xor     edx, edx; nProcNum
0x1800297d4  call    cs:__imp_NdrClientCall3
0x1800297da  mov     [rsp+0A8h+var_30], rax
0x1800297df  mov     ebx, eax
0x1800297e1  mov     [rsp+0A8h+var_3C], eax
0x1800297e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297ec  lea     rdx, WPP_GLOBAL_Control
0x1800297f3  cmp     rcx, rdx
0x1800297f6  jz      short loc_18002982A
0x1800297f8  test    byte ptr [rcx+1Ch], 4
0x1800297fc  jz      short loc_18002982A
0x1800297fe  cmp     byte ptr [rcx+19h], 4
0x180029802  jb      short loc_18002982A
0x180029804  mov     edx, 0Fh
0x180029809  mov     r9d, eax
0x18002980c  lea     r8, WPP_37d584b9184134be2c2c41d914906a97_Traceguids
0x180029813  mov     rcx, [rcx+10h]
0x180029817  call    WPP_SF_d
0x18002981c  lea     rdx, WPP_GLOBAL_Control
0x180029823  mov     rcx, cs:WPP_GLOBAL_Control
0x18002982a  cmp     ebx, 721h
0x180029830  jz      short loc_180029859
0x180029832  cmp     ebx, 6BAh
0x180029838  jz      short loc_180029859
0x18002983a  cmp     ebx, 6D9h
0x180029840  jz      short loc_180029859
0x180029842  test    edi, edi
0x180029844  jnz     short loc_180029855
0x180029846  test    ebx, ebx
0x180029848  jz      short loc_180029859
0x18002984a  lea     eax, [rbx-6A4h]
0x180029850  cmp     eax, 53h ; 'S'
0x180029853  ja      short loc_180029859
0x180029855  inc     edi
0x180029857  jmp     short loc_18002985E
0x180029859  mov     edi, 2
0x18002985e  mov     [rsp+0A8h+var_40], edi
0x180029862  cmp     rcx, rdx
0x180029865  jz      short loc_18002988B
0x180029867  test    byte ptr [rcx+1Ch], 4
0x18002986b  jz      short loc_18002988B
0x18002986d  cmp     byte ptr [rcx+19h], 4
0x180029871  jb      short loc_18002988B
0x180029873  mov     edx, 10h
0x180029878  mov     r9d, ebx
0x18002987b  lea     r8, WPP_37d584b9184134be2c2c41d914906a97_Traceguids
0x180029882  mov     rcx, [rcx+10h]
0x180029886  call    WPP_SF_d
0x18002988b  jmp     short loc_18002990A
0x18002988d  mov     edi, eax
0x18002988f  mov     ebx, eax
0x180029891  mov     [rsp+0A8h+var_3C], eax
0x180029895  lea     rax, WPP_GLOBAL_Control
0x18002989c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298a3  cmp     rcx, rax
0x1800298a6  jz      short loc_1800298CC
0x1800298a8  test    byte ptr [rcx+1Ch], 4
0x1800298ac  jz      short loc_1800298CC
0x1800298ae  cmp     byte ptr [rcx+19h], 4
0x1800298b2  jb      short loc_1800298CC
0x1800298b4  mov     edx, 11h
0x1800298b9  mov     r9d, ebx
0x1800298bc  lea     r8, WPP_37d584b9184134be2c2c41d914906a97_Traceguids
0x1800298c3  mov     rcx, [rcx+10h]
0x1800298c7  call    WPP_SF_d
0x1800298cc  cmp     edi, 6C5h
0x1800298d2  jnz     loc_1800299DD
0x1800298d8  cmp     [rsp+0A8h+var_48], 36h ; '6'
0x1800298dd  jnz     loc_1800299DD
0x1800298e3  mov     ebx, 32h ; '2'
0x1800298e8  mov     [rsp+0A8h+var_3C], ebx
0x1800298ec  mov     edi, 2
0x1800298f1  mov     [rsp+0A8h+var_40], edi
0x1800298f5  mov     r14, [rsp+0A8h+var_38]
0x1800298fa  mov     r12d, [rsp+0A8h+arg_10]
0x180029902  mov     r13d, [rsp+0A8h+arg_0]
0x18002990a  cmp     edi, 2
0x18002990d  jl      loc_18002965D
0x180029913  mov     ecx, ebx
0x180029915  call    printExtendedRpcErrorInfo
0x18002991a  cmp     [rsp+0A8h+arg_28], 0
0x180029922  jz      short loc_18002997F
0x180029924  cmp     [rsp+0A8h+var_48], 0Eh
0x180029929  jnz     short loc_18002993D
0x18002992b  mov     rcx, [r14+30h]; lpMem
0x18002992f  call    Dns_Free
0x180029934  mov     rcx, [r14+38h]; lpMem
0x180029938  call    Dns_Free
0x18002993d  cmp     [rsp+0A8h+var_48], 8
0x180029942  jnz     short loc_18002994D
0x180029944  mov     rcx, [r14+8]; lpMem
0x180029948  call    Dns_Free
0x18002994d  cmp     [rsp+0A8h+var_48], 0Dh
0x180029952  jnz     short loc_18002995D
0x180029954  mov     rcx, [r14+8]; lpMem
0x180029958  call    Dns_Free
0x18002995d  cmp     [rsp+0A8h+var_48], 0Bh
0x180029962  jnz     short loc_180029976
0x180029964  mov     rcx, [r14+8]; lpMem
0x180029968  call    Dns_Free
0x18002996d  mov     rcx, [r14+10h]; lpMem
0x180029971  call    Dns_Free
0x180029976  mov     rcx, r14; hMem
0x180029979  call    cs:__imp_LocalFree
0x18002997f  mov     rcx, [rsp+0A8h+arg_8]
0x180029987  call    Dnssrv_FreeRPCBindingHandle
0x18002998c  lea     rdx, aPreparefordemo; "PrepareForDemotion"
0x180029993  mov     rcx, [rsp+0A8h+String1]; String1
0x18002999b  call    cs:__imp__stricmp
0x1800299a1  test    eax, eax
0x1800299a3  jnz     short loc_1800299B8
0x1800299a5  test    ebx, ebx
0x1800299a7  jz      short loc_1800299B8
0x1800299a9  call    Dns_MaintainNtdsDependency
0x1800299ae  mov     ecx, 42Ch
0x1800299b3  test    eax, eax
0x1800299b5  cmovnz  ebx, ecx
0x1800299b8  test    r13d, r13d
0x1800299bb  jz      short loc_1800299CB
0x1800299bd  mov     eax, 2563h
0x1800299c2  cmp     ebx, 721h
0x1800299c8  cmovz   ebx, eax
0x1800299cb  mov     eax, ebx
0x1800299cd  add     rsp, 80h
0x1800299d4  pop     r14
0x1800299d6  pop     r13
0x1800299d8  pop     r12
0x1800299da  pop     rdi
0x1800299db  pop     rbx
0x1800299dc  retn
0x1800299dd  cmp     ebx, 721h
0x1800299e3  jz      short loc_180029A10
0x1800299e5  cmp     ebx, 6BAh
0x1800299eb  jz      short loc_180029A10
0x1800299ed  cmp     ebx, 6D9h
0x1800299f3  jz      short loc_180029A10
0x1800299f5  mov     edi, [rsp+0A8h+var_40]
0x1800299f9  test    edi, edi
0x1800299fb  jnz     short loc_180029A0C
0x1800299fd  test    ebx, ebx
0x1800299ff  jz      short loc_180029A10
0x180029a01  lea     eax, [rbx-6A4h]
0x180029a07  cmp     eax, 53h ; 'S'
0x180029a0a  ja      short loc_180029A10
0x180029a0c  inc     edi
0x180029a0e  jmp     short loc_180029A15
0x180029a10  mov     edi, 2
0x180029a15  mov     [rsp+0A8h+var_40], edi
0x180029a19  cmp     edi, 1
0x180029a1c  jnz     loc_1800298F5
0x180029a22  lea     r8, [rsp+0A8h+arg_28]
0x180029a2a  lea     rdx, [rsp+0A8h+var_38]
0x180029a2f  lea     rcx, [rsp+0A8h+var_48]
0x180029a34  call    DnsRpc_ConvertToUnversioned
0x180029a39  mov     ebx, eax
0x180029a3b  mov     [rsp+0A8h+var_3C], eax
0x180029a3f  test    eax, eax
0x180029a41  jnz     loc_1800298EC
0x180029a47  mov     r14, [rsp+0A8h+var_38]
0x180029a4c  mov     [rsp+0A8h+arg_18], r14
0x180029a54  jmp     loc_1800298FA
```
