# s_SrvRpcCryptGetKeyProperty

- ea: `0x180003f60`
- end: `0x18000419b`
- name: `s_SrvRpcCryptGetKeyProperty`
- size: `571`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int, _DWORD *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180003f60`
- `0x180004470`
- `0x1800048f0`
- `0x1800066e0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003f95`
- `RPCRT4!RpcImpersonateClient` at `0x180003f95`
- `RPCRT4!RpcRevertToSelf` at `0x1800040ca`
- `RPCRT4!RpcRevertToSelf` at `0x1800040ca`

## string_xrefs

- `0x180003fa7`: `Security Descr`
- `0x18000405c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000409c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000411a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000416c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptGetKeyProperty(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        _DWORD *a8,
        int a9)
{
  RPC_STATUS v12; // eax
  int v13; // r8d
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // edx
  int v17; // eax
  void *v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // ebx
  PTOKEN_PRIVILEGES v22[8]; // [rsp+58h] [rbp-40h] BYREF

  v22[0] = 0;
  if ( !a8 )
    return 2148073511LL;
  v12 = RpcImpersonateClient(a1);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        v13,
        (unsigned int)"Status",
        v12,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        127);
    return 2148073504LL;
  }
  else
  {
    v14 = -1;
    do
    {
      v15 = *(unsigned __int16 *)(a5 + 2 * v14 + 2);
      v16 = aSecurityDescr[v14 + 1] - (_DWORD)v15;
      if ( v16 )
        break;
      v14 += 2;
      if ( v14 == 15 )
        break;
      v15 = *(unsigned __int16 *)(a5 + 2 * v14);
      v16 = aSecurityDescr[v14] - (_DWORD)v15;
    }
    while ( !v16 );
    if ( !v16 )
      SrvAdjustPrivilege(v15, 1u, (__int64)L"Security Descr", v22);
    *a8 = 0;
    v17 = off_180025038(a2, a3, a4, a5, a6, a7, (__int64)a8, a9);
    v20 = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          v19,
          (unsigned int)"Status",
          v17,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          162);
    }
    if ( v22[0] )
      SrvAdjustPrivilege((__int64)v18, 0, v19, v22);
    RpcRevertToSelf();
    return v20;
  }
}

```

## disassembly

```asm
0x180003f60  push    rbx
0x180003f62  push    rsi
0x180003f63  push    rdi
0x180003f64  push    r12
0x180003f66  push    r14
0x180003f68  push    r15
0x180003f6a  sub     rsp, 68h
0x180003f6e  mov     rsi, r9
0x180003f71  mov     r14, r8
0x180003f74  mov     r15, rdx
0x180003f77  xor     r12d, r12d
0x180003f7a  mov     [rsp+98h+var_48], r12d
0x180003f7f  mov     [rsp+98h+var_40], r12
0x180003f84  mov     rdi, [rsp+98h+arg_38]
0x180003f8c  test    rdi, rdi
0x180003f8f  jz      loc_1800040E0
0x180003f95  call    cs:__imp_RpcImpersonateClient
0x180003f9b  mov     [rsp+98h+var_48], eax
0x180003f9f  test    eax, eax
0x180003fa1  jnz     loc_1800040F9
0x180003fa7  lea     r8, aSecurityDescr; "Security Descr"
0x180003fae  mov     rbx, [rsp+98h+arg_20]
0x180003fb6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003fbd  nop     dword ptr [rax]
0x180003fc0  movzx   edx, word ptr [r8+rax*2+2]
0x180003fc6  movzx   ecx, word ptr [rbx+rax*2+2]
0x180003fcb  sub     edx, ecx
0x180003fcd  jnz     short loc_180003FE6
0x180003fcf  add     rax, 2
0x180003fd3  cmp     rax, 0Fh
0x180003fd7  jz      short loc_180003FE6
0x180003fd9  movzx   edx, word ptr [r8+rax*2]
0x180003fde  movzx   ecx, word ptr [rbx+rax*2]
0x180003fe2  sub     edx, ecx
0x180003fe4  jz      short loc_180003FC0
0x180003fe6  test    edx, edx
0x180003fe8  jz      loc_18000407E
0x180003fee  mov     [rdi], r12d
0x180003ff1  mov     eax, [rsp+98h+arg_40]
0x180003ff8  mov     [rsp+98h+var_60], eax
0x180003ffc  mov     [rsp+98h+var_68], rdi
0x180004001  mov     eax, [rsp+98h+arg_30]
0x180004008  mov     dword ptr [rsp+98h+var_70], eax
0x18000400c  mov     rax, [rsp+98h+arg_28]
0x180004014  mov     [rsp+98h+var_78], rax
0x180004019  mov     r9, rbx
0x18000401c  mov     r8, rsi
0x18000401f  mov     rdx, r14
0x180004022  mov     rcx, r15
0x180004025  mov     rax, cs:off_180025038
0x18000402c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004031  mov     ebx, eax
0x180004033  mov     [rsp+98h+var_48], eax
0x180004037  test    eax, eax
0x180004039  jns     short loc_180004092
0x18000403b  lea     rdx, WPP_GLOBAL_Control
0x180004042  mov     rcx, cs:WPP_GLOBAL_Control
0x180004049  cmp     rcx, rdx
0x18000404c  jz      short loc_180004092
0x18000404e  test    byte ptr [rcx+1Ch], 1
0x180004052  jz      short loc_180004092
0x180004054  mov     dword ptr [rsp+98h+var_68], 2A2h
0x18000405c  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004063  mov     [rsp+98h+var_70], rdx
0x180004068  mov     dword ptr [rsp+98h+var_78], eax
0x18000406c  lea     r9, aStatus; "Status"
0x180004073  mov     rcx, [rcx+10h]
0x180004077  call    WPP_SF_sDsd
0x18000407c  jmp     short loc_180004092
0x18000407e  lea     r9, [rsp+98h+var_40]
0x180004083  mov     edx, 1
0x180004088  call    _SrvAdjustPrivilege
0x18000408d  jmp     loc_180003FEE
0x180004092  jmp     short loc_1800040BE
0x180004094  mov     ebx, eax
0x180004096  mov     r9d, 2A8h
0x18000409c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800040a3  lea     rdx, aNtstatus; "ntStatus"
0x1800040aa  mov     ecx, eax
0x1800040ac  call    DebugTraceError
0x1800040b1  mov     ecx, ebx
0x1800040b3  call    NormalizeNteStatus
0x1800040b8  mov     ebx, eax
0x1800040ba  mov     [rsp+98h+var_48], eax
0x1800040be  cmp     [rsp+98h+var_40], 0
0x1800040c4  jnz     loc_180004153
0x1800040ca  call    cs:__imp_RpcRevertToSelf
0x1800040d0  mov     eax, ebx
0x1800040d2  add     rsp, 68h
0x1800040d6  pop     r15
0x1800040d8  pop     r14
0x1800040da  pop     r12
0x1800040dc  pop     rdi
0x1800040dd  pop     rsi
0x1800040de  pop     rbx
0x1800040df  retn
0x1800040e0  mov     ebx, 80090027h
0x1800040e5  mov     [rsp+98h+var_48], ebx
0x1800040e9  mov     eax, ebx
0x1800040eb  add     rsp, 68h
0x1800040ef  pop     r15
0x1800040f1  pop     r14
0x1800040f3  pop     r12
0x1800040f5  pop     rdi
0x1800040f6  pop     rsi
0x1800040f7  pop     rbx
0x1800040f8  retn
0x1800040f9  lea     rdx, WPP_GLOBAL_Control
0x180004100  mov     rcx, cs:WPP_GLOBAL_Control
0x180004107  cmp     rcx, rdx
0x18000410a  jz      short loc_18000413A
0x18000410c  test    byte ptr [rcx+1Ch], 1
0x180004110  jz      short loc_18000413A
0x180004112  mov     dword ptr [rsp+98h+var_68], 27Fh
0x18000411a  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004121  mov     [rsp+98h+var_70], rdx
0x180004126  mov     dword ptr [rsp+98h+var_78], eax
0x18000412a  lea     r9, aStatus; "Status"
0x180004131  mov     rcx, [rcx+10h]
0x180004135  call    WPP_SF_sDsd
0x18000413a  mov     ebx, 80090020h
0x18000413f  mov     [rsp+98h+var_48], ebx
0x180004143  mov     eax, ebx
0x180004145  add     rsp, 68h
0x180004149  pop     r15
0x18000414b  pop     r14
0x18000414d  pop     r12
0x18000414f  pop     rdi
0x180004150  pop     rsi
0x180004151  pop     rbx
0x180004152  retn
0x180004153  lea     r9, [rsp+98h+var_40]
0x180004158  xor     edx, edx
0x18000415a  call    _SrvAdjustPrivilege
0x18000415f  jmp     loc_1800040CA
0x180004164  mov     edi, eax
0x180004166  mov     r9d, 2BAh
0x18000416c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004173  lea     rdx, aNtstatus; "ntStatus"
0x18000417a  mov     ecx, eax
0x18000417c  call    DebugTraceError
0x180004181  mov     ebx, [rsp+98h+var_48]
0x180004185  test    ebx, ebx
0x180004187  js      short loc_180004196
0x180004189  mov     ecx, edi
0x18000418b  call    NormalizeNteStatus
0x180004190  mov     ebx, eax
0x180004192  mov     [rsp+98h+var_48], eax
0x180004196  jmp     loc_1800040CA
```
