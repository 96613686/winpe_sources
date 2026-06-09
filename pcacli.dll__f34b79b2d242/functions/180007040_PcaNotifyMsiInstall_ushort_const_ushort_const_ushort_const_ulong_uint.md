# PcaNotifyMsiInstall(ushort const *,ushort const *,ushort const *,ulong,uint)

- ea: `0x180007040`
- end: `0x180007197`
- name: `?PcaNotifyMsiInstall@@YAKPEBG00KI@Z`
- size: `343`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x180001870`
- `0x180002bd0`
- `0x180002ca0`
- `0x180002ee8`
- `0x180007040`
- `0x180007738`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000c1d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c1d0`
- `RPCRT4!NdrClientCall3` at `0x180007117`
- `RPCRT4!NdrClientCall3` at `0x180007117`

## string_xrefs

- `0x1800070c2`: `PcaClient`
- `0x180007099`: `PcaNotifyMsiInstall`
- `0x1800070b6`: `SendToService ignored,PCA disabled`

## pseudocode

```c
__int64 __fastcall PcaNotifyMsiInstall(
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
    AslLogCallPrintf(1, "PcaNotifyMsiInstall", 1039, "Bad flags parameter");
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
      v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, v17, a1, a2, a3, v15, v16).Pointer;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007040  mov     rax, rsp
0x180007043  mov     [rax+20h], r9d
0x180007047  mov     [rax+18h], r8
0x18000704b  mov     [rax+10h], rdx
0x18000704f  mov     [rax+8], rcx
0x180007053  push    rbx
0x180007054  push    rsi
0x180007055  push    rdi
0x180007056  push    r12
0x180007058  push    r13
0x18000705a  push    r14
0x18000705c  push    r15
0x18000705e  sub     rsp, 70h
0x180007062  mov     esi, r9d
0x180007065  mov     r14, r8
0x180007068  mov     r15, rdx
0x18000706b  mov     r12, rcx
0x18000706e  xor     edi, edi
0x180007070  mov     [rsp+0A8h+var_58], edi
0x180007074  mov     [rax-50h], rdi
0x180007078  mov     r13d, [rsp+0A8h+arg_20]
0x180007080  test    r13d, 0FFFFFFFCh
0x180007087  jz      short loc_1800070AD
0x180007089  lea     ebx, [rdi+57h]
0x18000708c  lea     r9, aBadFlagsParame; "Bad flags parameter"
0x180007093  mov     r8d, 40Fh
0x180007099  lea     rdx, aPcanotifymsiin_0; "PcaNotifyMsiInstall"
0x1800070a0  lea     ecx, [rdi+1]
0x1800070a3  call    AslLogCallPrintf
0x1800070a8  jmp     loc_180007151
0x1800070ad  call    ?PcaIsPcaDisabled@@YAHXZ; PcaIsPcaDisabled(void)
0x1800070b2  test    eax, eax
0x1800070b4  jz      short loc_1800070D2
0x1800070b6  lea     r9, aSendtoserviceI; "SendToService ignored,PCA disabled"
0x1800070bd  xor     r8d, r8d; unsigned int
0x1800070c0  xor     edx, edx; unsigned int
0x1800070c2  lea     rcx, aPcaclient; "PcaClient"
0x1800070c9  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800070ce  xor     ebx, ebx
0x1800070d0  jmp     short loc_180007151
0x1800070d2  lea     rcx, [rsp+0A8h+var_50]; void **
0x1800070d7  call    ?PcapCreateBindingHandle@@YAKPEAPEAX@Z; PcapCreateBindingHandle(void * *)
0x1800070dc  test    eax, eax
0x1800070de  mov     ebx, eax
0x1800070e0  jnz     short loc_180007151
0x1800070e2  nop
0x1800070e3  mov     [rsp+0A8h+var_48], 0
0x1800070ec  mov     [rsp+0A8h+var_68], r13d
0x1800070f1  mov     dword ptr [rsp+0A8h+var_70], esi
0x1800070f5  mov     [rsp+0A8h+var_78], r14
0x1800070fa  mov     [rsp+0A8h+var_80], r15
0x1800070ff  mov     [rsp+0A8h+var_88], r12
0x180007104  mov     r9, [rsp+0A8h+var_50]
0x180007109  xor     r8d, r8d; pReturnValue
0x18000710c  lea     edx, [r8+2]; nProcNum
0x180007110  lea     rcx, pProxyInfo; pProxyInfo
0x180007117  call    cs:__imp_NdrClientCall3
0x18000711d  mov     [rsp+0A8h+var_48], rax
0x180007122  jmp     short loc_180007151
0x180007124  mov     ebx, eax
0x180007126  mov     r13d, [rsp+0A8h+arg_20]
0x18000712e  mov     esi, [rsp+0A8h+arg_18]
0x180007135  mov     r14, [rsp+0A8h+arg_10]
0x18000713d  mov     r15, [rsp+0A8h+arg_8]
0x180007145  mov     r12, [rsp+0A8h+arg_0]
0x18000714d  mov     edi, [rsp+0A8h+var_58]
0x180007151  test    ebx, ebx
0x180007153  jz      short loc_180007185
0x180007155  cmp     edi, 1
0x180007158  ja      short loc_180007185
0x18000715a  lea     eax, [rbx-6ACh]
0x180007160  cmp     eax, 2Dh ; '-'
0x180007163  ja      short loc_180007185
0x180007165  mov     rcx, 200000004201h
0x18000716f  bt      rcx, rax
0x180007173  jnb     short loc_180007185
0x180007175  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x18000717a  inc     edi
0x18000717c  mov     [rsp+0A8h+var_58], edi
0x180007180  jmp     loc_1800070DC
0x180007185  mov     eax, ebx
0x180007187  add     rsp, 70h
0x18000718b  pop     r15
0x18000718d  pop     r14
0x18000718f  pop     r13
0x180007191  pop     r12
0x180007193  pop     rdi
0x180007194  pop     rsi
0x180007195  pop     rbx
0x180007196  retn
0x18000c1c2  push    rbp
0x18000c1c4  sub     rsp, 50h
0x18000c1c8  mov     rbp, rdx
0x18000c1cb  mov     rcx, [rcx]
0x18000c1ce  mov     ecx, [rcx]; ExceptionCode
0x18000c1d0  call    cs:__imp_I_RpcExceptionFilter
0x18000c1d6  nop
0x18000c1d7  add     rsp, 50h
0x18000c1db  pop     rbp
0x18000c1dc  retn
```
