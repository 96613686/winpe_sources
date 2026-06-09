# PcaNotifyMsiCustomAction(ushort const *,ushort const *,ushort const *,ulong,uint)

- ea: `0x1800012c0`
- end: `0x180001426`
- name: `?PcaNotifyMsiCustomAction@@YAKPEBG00KI@Z`
- size: `358`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x1800012c0`
- `0x180001870`
- `0x180002bd0`
- `0x180002ca0`
- `0x180002ee8`
- `0x180007738`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000c14e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c14e`
- `RPCRT4!NdrClientCall3` at `0x1800013a1`
- `RPCRT4!NdrClientCall3` at `0x1800013a1`

## string_xrefs

- `0x18000131d`: `PcaNotifyMsiCustomAction`
- `0x180001348`: `PcaClient`
- `0x18000133c`: `SendToService ignored,PCA disabled`

## pseudocode

```c
__int64 __fastcall PcaNotifyMsiCustomAction(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  unsigned int v9; // edi
  unsigned int v10; // ebx
  unsigned int started; // eax
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+38h] [rbp-70h]
  __int64 v16; // [rsp+40h] [rbp-68h]
  void *v17; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+60h] [rbp-48h]

  v9 = 0;
  v17 = 0;
  if ( (a5 & 0xFFFFFFFC) != 0 )
  {
    v10 = 87;
    AslLogCallPrintf(1, "PcaNotifyMsiCustomAction", 1162, "Bad flags parameter");
  }
  else
  {
    if ( !(unsigned int)PcaIsPcaDisabled() )
    {
      started = PcapCreateBindingHandle(&v17);
      goto LABEL_6;
    }
    PcaTracePrintf("PcaClient", 0, 0, "SendToService ignored,PCA disabled");
    v10 = 0;
  }
  while ( v10 )
  {
    if ( v9 > 1 )
      break;
    v12 = v10 - 1708;
    if ( (unsigned int)v12 > 0x2D )
      break;
    v13 = 0x200000004201LL;
    if ( !_bittest64(&v13, v12) )
      break;
    started = PcacpStartPCAService();
    ++v9;
LABEL_6:
    v10 = started;
    if ( !started )
    {
      v18.Simple = 0;
      LODWORD(v16) = a5;
      LODWORD(v15) = a4;
      v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, v17, a1, a2, a3, v15, v16).Pointer;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800012c0  mov     [rsp+arg_18], r9d
0x1800012c5  mov     [rsp+arg_10], r8
0x1800012ca  mov     [rsp+arg_8], rdx
0x1800012cf  mov     [rsp+arg_0], rcx
0x1800012d4  push    rbx
0x1800012d5  push    rsi
0x1800012d6  push    rdi
0x1800012d7  push    r12
0x1800012d9  push    r13
0x1800012db  push    r14
0x1800012dd  push    r15
0x1800012df  sub     rsp, 70h
0x1800012e3  mov     esi, r9d
0x1800012e6  mov     r14, r8
0x1800012e9  mov     r15, rdx
0x1800012ec  mov     r12, rcx
0x1800012ef  xor     edi, edi
0x1800012f1  mov     [rsp+0A8h+var_58], edi
0x1800012f5  mov     [rsp+0A8h+var_50], rdi
0x1800012fa  mov     r13d, [rsp+0A8h+arg_20]
0x180001302  test    r13d, 0FFFFFFFCh
0x180001309  jz      short loc_180001333
0x18000130b  mov     ebx, 57h ; 'W'
0x180001310  lea     r9, aBadFlagsParame; "Bad flags parameter"
0x180001317  mov     r8d, 48Ah
0x18000131d  lea     rdx, aPcanotifymsicu_0; "PcaNotifyMsiCustomAction"
0x180001324  mov     ecx, 1
0x180001329  call    AslLogCallPrintf
0x18000132e  jmp     loc_1800013E0
0x180001333  call    ?PcaIsPcaDisabled@@YAHXZ; PcaIsPcaDisabled(void)
0x180001338  test    eax, eax
0x18000133a  jz      short loc_18000135B
0x18000133c  lea     r9, aSendtoserviceI; "SendToService ignored,PCA disabled"
0x180001343  xor     r8d, r8d; unsigned int
0x180001346  xor     edx, edx; unsigned int
0x180001348  lea     rcx, aPcaclient; "PcaClient"
0x18000134f  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180001354  xor     ebx, ebx
0x180001356  jmp     loc_1800013E0
0x18000135b  lea     rcx, [rsp+0A8h+var_50]; void **
0x180001360  call    ?PcapCreateBindingHandle@@YAKPEAPEAX@Z; PcapCreateBindingHandle(void * *)
0x180001365  test    eax, eax
0x180001367  mov     ebx, eax
0x180001369  jnz     short loc_1800013E0
0x18000136b  nop
0x18000136c  mov     [rsp+0A8h+var_48], 0
0x180001375  mov     [rsp+0A8h+var_68], r13d
0x18000137a  mov     dword ptr [rsp+0A8h+var_70], esi
0x18000137e  mov     [rsp+0A8h+var_78], r14
0x180001383  mov     [rsp+0A8h+var_80], r15
0x180001388  mov     [rsp+0A8h+var_88], r12
0x18000138d  mov     r9, [rsp+0A8h+var_50]
0x180001392  xor     r8d, r8d; pReturnValue
0x180001395  mov     edx, 3; nProcNum
0x18000139a  lea     rcx, pProxyInfo; pProxyInfo
0x1800013a1  call    cs:__imp_NdrClientCall3
0x1800013a7  mov     [rsp+0A8h+var_48], rax
0x1800013ac  jmp     short loc_1800013E0
0x1800013ae  mov     ebx, eax
0x1800013b0  mov     r13d, [rsp+0A8h+arg_20]
0x1800013b8  mov     esi, [rsp+0A8h+arg_18]
0x1800013bf  mov     r14, [rsp+0A8h+arg_10]
0x1800013c7  mov     r15, [rsp+0A8h+arg_8]
0x1800013cf  mov     r12, [rsp+0A8h+arg_0]
0x1800013d7  mov     edi, [rsp+0A8h+var_58]
0x1800013db  nop     dword ptr [rax+rax+00h]
0x1800013e0  test    ebx, ebx
0x1800013e2  jz      short loc_180001414
0x1800013e4  cmp     edi, 1
0x1800013e7  ja      short loc_180001414
0x1800013e9  lea     eax, [rbx-6ACh]
0x1800013ef  cmp     eax, 2Dh ; '-'
0x1800013f2  ja      short loc_180001414
0x1800013f4  mov     rcx, 200000004201h
0x1800013fe  bt      rcx, rax
0x180001402  jnb     short loc_180001414
0x180001404  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x180001409  inc     edi
0x18000140b  mov     [rsp+0A8h+var_58], edi
0x18000140f  jmp     loc_180001365
0x180001414  mov     eax, ebx
0x180001416  add     rsp, 70h
0x18000141a  pop     r15
0x18000141c  pop     r14
0x18000141e  pop     r13
0x180001420  pop     r12
0x180001422  pop     rdi
0x180001423  pop     rsi
0x180001424  pop     rbx
0x180001425  retn
0x18000c140  push    rbp
0x18000c142  sub     rsp, 50h
0x18000c146  mov     rbp, rdx
0x18000c149  mov     rcx, [rcx]
0x18000c14c  mov     ecx, [rcx]; ExceptionCode
0x18000c14e  call    cs:__imp_I_RpcExceptionFilter
0x18000c154  nop
0x18000c155  add     rsp, 50h
0x18000c159  pop     rbp
0x18000c15a  retn
```
