# s_SrvRpcCryptSetKeyProperty

- ea: `0x180003360`
- end: `0x18000352e`
- name: `s_SrvRpcCryptSetKeyProperty`
- size: `462`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003360`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800066e0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000337e`
- `RPCRT4!RpcImpersonateClient` at `0x18000337e`
- `RPCRT4!RpcRevertToSelf` at `0x180003481`
- `RPCRT4!RpcRevertToSelf` at `0x180003481`

## string_xrefs

- `0x180003390`: `Security Descr`
- `0x180003425`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180003457`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800034b4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800034ff`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptSetKeyProperty(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8)
{
  RPC_STATUS v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // edx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // ebx
  _QWORD v20[6]; // [rsp+48h] [rbp-30h] BYREF

  v20[0] = 0;
  v11 = RpcImpersonateClient(a1);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        220);
    return 2148073504LL;
  }
  else
  {
    v12 = -1;
    do
    {
      v13 = *(unsigned __int16 *)(a5 + 2 * v12 + 2);
      v14 = aSecurityDescr[v12 + 1] - (_DWORD)v13;
      if ( v14 )
        break;
      v12 += 2;
      if ( v12 == 15 )
        break;
      v13 = *(unsigned __int16 *)(a5 + 2 * v12);
      v14 = aSecurityDescr[v12] - (_DWORD)v13;
    }
    while ( !v14 );
    if ( !v14 )
      SrvAdjustPrivilege(v13, 1, L"Security Descr", v20);
    v15 = off_180025048(a2, a3, a4, a5, a6, a7, a8);
    v18 = v15;
    if ( v15 < 0 )
      DebugTraceError(
        (unsigned int)v15,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        764);
    if ( v20[0] )
      SrvAdjustPrivilege(v16, 0, v17, v20);
    RpcRevertToSelf();
    return v18;
  }
}

```

## disassembly

```asm
0x180003360  push    rbx
0x180003362  push    rsi
0x180003363  push    rdi
0x180003364  push    r14
0x180003366  sub     rsp, 58h
0x18000336a  mov     rdi, r9
0x18000336d  mov     rsi, r8
0x180003370  mov     r14, rdx
0x180003373  xor     eax, eax
0x180003375  mov     [rsp+78h+var_38], eax
0x180003379  mov     [rsp+78h+var_30], rax
0x18000337e  call    cs:__imp_RpcImpersonateClient
0x180003384  mov     [rsp+78h+var_38], eax
0x180003388  test    eax, eax
0x18000338a  jnz     loc_180003493
0x180003390  lea     r8, aSecurityDescr; "Security Descr"
0x180003397  mov     rbx, [rsp+78h+arg_20]
0x18000339f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800033a6  nop     word ptr [rax+rax+00000000h]
0x1800033b0  movzx   edx, word ptr [r8+rax*2+2]
0x1800033b6  movzx   ecx, word ptr [rbx+rax*2+2]
0x1800033bb  sub     edx, ecx
0x1800033bd  jnz     short loc_1800033D6
0x1800033bf  add     rax, 2
0x1800033c3  cmp     rax, 0Fh
0x1800033c7  jz      short loc_1800033D6
0x1800033c9  movzx   edx, word ptr [r8+rax*2]
0x1800033ce  movzx   ecx, word ptr [rbx+rax*2]
0x1800033d2  sub     edx, ecx
0x1800033d4  jz      short loc_1800033B0
0x1800033d6  test    edx, edx
0x1800033d8  jz      short loc_18000343C
0x1800033da  mov     ecx, [rsp+78h+arg_38]
0x1800033e1  mov     [rsp+78h+var_48], ecx
0x1800033e5  mov     ecx, [rsp+78h+arg_30]
0x1800033ec  mov     dword ptr [rsp+78h+var_50], ecx
0x1800033f0  mov     rcx, [rsp+78h+arg_28]
0x1800033f8  mov     [rsp+78h+var_58], rcx
0x1800033fd  mov     r9, rbx
0x180003400  mov     r8, rdi
0x180003403  mov     rdx, rsi
0x180003406  mov     rcx, r14
0x180003409  mov     rax, cs:off_180025048
0x180003410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003415  mov     ebx, eax
0x180003417  mov     [rsp+78h+var_38], eax
0x18000341b  test    eax, eax
0x18000341d  jns     short loc_18000344D
0x18000341f  mov     r9d, 2FCh
0x180003425  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000342c  lea     rdx, aStatus; "Status"
0x180003433  mov     ecx, eax
0x180003435  call    DebugTraceError
0x18000343a  jmp     short loc_18000344D
0x18000343c  lea     r9, [rsp+78h+var_30]
0x180003441  mov     edx, 1
0x180003446  call    _SrvAdjustPrivilege
0x18000344b  jmp     short loc_1800033DA
0x18000344d  jmp     short loc_180003479
0x18000344f  mov     ebx, eax
0x180003451  mov     r9d, 302h
0x180003457  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000345e  lea     rdx, aNtstatus; "ntStatus"
0x180003465  mov     ecx, eax
0x180003467  call    DebugTraceError
0x18000346c  mov     ecx, ebx
0x18000346e  call    NormalizeNteStatus
0x180003473  mov     ebx, eax
0x180003475  mov     [rsp+78h+var_38], eax
0x180003479  cmp     [rsp+78h+var_30], 0
0x18000347f  jnz     short loc_1800034E9
0x180003481  call    cs:__imp_RpcRevertToSelf
0x180003487  mov     eax, ebx
0x180003489  add     rsp, 58h
0x18000348d  pop     r14
0x18000348f  pop     rdi
0x180003490  pop     rsi
0x180003491  pop     rbx
0x180003492  retn
0x180003493  lea     rdx, WPP_GLOBAL_Control
0x18000349a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034a1  cmp     rcx, rdx
0x1800034a4  jz      short loc_1800034D4
0x1800034a6  test    byte ptr [rcx+1Ch], 1
0x1800034aa  jz      short loc_1800034D4
0x1800034ac  mov     [rsp+78h+var_48], 2DCh
0x1800034b4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800034bb  mov     [rsp+78h+var_50], r8
0x1800034c0  mov     dword ptr [rsp+78h+var_58], eax
0x1800034c4  lea     r9, aStatus; "Status"
0x1800034cb  mov     rcx, [rcx+10h]
0x1800034cf  call    WPP_SF_sDsd
0x1800034d4  mov     ebx, 80090020h
0x1800034d9  mov     [rsp+78h+var_38], ebx
0x1800034dd  mov     eax, ebx
0x1800034df  add     rsp, 58h
0x1800034e3  pop     r14
0x1800034e5  pop     rdi
0x1800034e6  pop     rsi
0x1800034e7  pop     rbx
0x1800034e8  retn
0x1800034e9  lea     r9, [rsp+78h+var_30]
0x1800034ee  xor     edx, edx
0x1800034f0  call    _SrvAdjustPrivilege
0x1800034f5  jmp     short loc_180003481
0x1800034f7  mov     edi, eax
0x1800034f9  mov     r9d, 315h
0x1800034ff  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003506  lea     rdx, aNtstatus; "ntStatus"
0x18000350d  mov     ecx, eax
0x18000350f  call    DebugTraceError
0x180003514  mov     ebx, [rsp+78h+var_38]
0x180003518  test    ebx, ebx
0x18000351a  js      short loc_180003529
0x18000351c  mov     ecx, edi
0x18000351e  call    NormalizeNteStatus
0x180003523  mov     ebx, eax
0x180003525  mov     [rsp+78h+var_38], eax
0x180003529  jmp     loc_180003481
```
