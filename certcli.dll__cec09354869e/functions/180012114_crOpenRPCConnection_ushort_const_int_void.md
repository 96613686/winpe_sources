# crOpenRPCConnection(ushort const *,int *,void * *)

- ea: `0x180012114`
- end: `0x180012225`
- name: `?crOpenRPCConnection@@YAJPEBGPEAHPEAPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr, int *, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001062c`
- `0x180012358`

## callees

- `0x180012114`
- `0x1800126e4`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800121a3`
- `RPCRT4!RpcStringFreeW` at `0x180012206`
- `RPCRT4!RpcStringFreeW` at `0x1800121a3`
- `RPCRT4!RpcStringFreeW` at `0x180012206`
- `RPCRT4!RpcNetworkIsProtseqValidW` at `0x18001214e`
- `RPCRT4!RpcNetworkIsProtseqValidW` at `0x18001214e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001217a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001217a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001218e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001218e`
- `RPCRT4!RpcEpResolveBinding` at `0x1800121b7`
- `RPCRT4!RpcEpResolveBinding` at `0x1800121b7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800121f3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800121f3`

## pseudocode

```c
__int64 __fastcall crOpenRPCConnection(RPC_WSTR NetworkAddr, int *a2, RPC_BINDING_HANDLE *Binding)
{
  unsigned int v3; // ebx
  unsigned int v4; // edi
  unsigned int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  RPC_WSTR String; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  String = 0;
  v4 = 0;
  while ( 1 )
  {
    if ( !RpcNetworkIsProtseqValidW((&off_1800697E0)[2 * v4]) )
    {
      v3 = RpcStringBindingComposeW(
             0,
             (&off_1800697E0)[2 * v4],
             NetworkAddr,
             *(&off_1800697E0 + 2 * v4 + 1),
             0,
             &String);
      if ( !v3 )
      {
        v3 = RpcBindingFromStringBindingW(String, Binding);
        if ( String )
          RpcStringFreeW(&String);
        if ( !v3 )
        {
          v3 = RpcEpResolveBinding(*Binding, qword_180049020);
          if ( !v3 )
            break;
        }
      }
    }
    if ( (int)++v4 >= 2 )
    {
      if ( v3 )
      {
        v8 = v3;
        v9 = 12976836;
        goto LABEL_13;
      }
      break;
    }
  }
  v10 = crSetRPCSecurity(*Binding, a2);
  v3 = v10;
  if ( !v10 )
    goto LABEL_14;
  v8 = v10;
  v9 = 13173444;
LABEL_13:
  CSPrintErrorLineFile(v9, v8);
LABEL_14:
  if ( String )
    RpcStringFreeW(&String);
  return v3;
}

```

## disassembly

```asm
0x180012114  mov     [rsp+arg_0], rbx
0x180012119  mov     [rsp+arg_8], rbp
0x18001211e  push    rsi
0x18001211f  push    rdi
0x180012120  push    r13
0x180012122  push    r14
0x180012124  push    r15
0x180012126  sub     rsp, 30h
0x18001212a  xor     ebx, ebx
0x18001212c  lea     r13, off_1800697E0; "ncacn_ip_tcp"
0x180012133  mov     [rsp+58h+String], rbx
0x180012138  xor     edi, edi
0x18001213a  mov     rsi, r8
0x18001213d  mov     rbp, rdx
0x180012140  mov     r15, rcx
0x180012143  mov     r14d, edi
0x180012146  add     r14, r14
0x180012149  mov     rcx, [r13+r14*8+0]; Protseq
0x18001214e  call    cs:__imp_RpcNetworkIsProtseqValidW
0x180012154  test    eax, eax
0x180012156  jnz     short loc_1800121C3
0x180012158  mov     r9, [r13+r14*8+8]; Endpoint
0x18001215d  lea     rax, [rsp+58h+String]
0x180012162  mov     rdx, [r13+r14*8+0]; ProtSeq
0x180012167  mov     r8, r15; NetworkAddr
0x18001216a  mov     [rsp+58h+StringBinding], rax; StringBinding
0x18001216f  xor     ecx, ecx; ObjUuid
0x180012171  mov     [rsp+58h+Options], 0; Options
0x18001217a  call    cs:__imp_RpcStringBindingComposeW
0x180012180  mov     ebx, eax
0x180012182  test    eax, eax
0x180012184  jnz     short loc_1800121C3
0x180012186  mov     rcx, [rsp+58h+String]; StringBinding
0x18001218b  mov     rdx, rsi; Binding
0x18001218e  call    cs:__imp_RpcBindingFromStringBindingW
0x180012194  cmp     [rsp+58h+String], 0
0x18001219a  mov     ebx, eax
0x18001219c  jz      short loc_1800121A9
0x18001219e  lea     rcx, [rsp+58h+String]; String
0x1800121a3  call    cs:__imp_RpcStringFreeW
0x1800121a9  test    ebx, ebx
0x1800121ab  jnz     short loc_1800121C3
0x1800121ad  mov     rcx, [rsi]; Binding
0x1800121b0  lea     rdx, qword_180049020; IfSpec
0x1800121b7  call    cs:__imp_RpcEpResolveBinding
0x1800121bd  mov     ebx, eax
0x1800121bf  test    eax, eax
0x1800121c1  jz      short loc_1800121DB
0x1800121c3  inc     edi
0x1800121c5  cmp     edi, 2
0x1800121c8  jl      loc_180012143
0x1800121ce  test    ebx, ebx
0x1800121d0  jz      short loc_1800121DB
0x1800121d2  mov     edx, ebx
0x1800121d4  mov     ecx, 0C602C4h
0x1800121d9  jmp     short loc_1800121F3
0x1800121db  mov     rcx, [rsi]; Binding
0x1800121de  mov     rdx, rbp; int *
0x1800121e1  call    ?crSetRPCSecurity@@YAJPEAXPEAH@Z; crSetRPCSecurity(void *,int *)
0x1800121e6  mov     ebx, eax
0x1800121e8  test    eax, eax
0x1800121ea  jz      short loc_1800121F9
0x1800121ec  mov     edx, eax
0x1800121ee  mov     ecx, 0C902C4h
0x1800121f3  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800121f9  cmp     [rsp+58h+String], 0
0x1800121ff  jz      short loc_18001220C
0x180012201  lea     rcx, [rsp+58h+String]; String
0x180012206  call    cs:__imp_RpcStringFreeW
0x18001220c  mov     rbp, [rsp+58h+arg_8]
0x180012211  mov     eax, ebx
0x180012213  mov     rbx, [rsp+58h+arg_0]
0x180012218  add     rsp, 30h
0x18001221c  pop     r15
0x18001221e  pop     r14
0x180012220  pop     r13
0x180012222  pop     rdi
0x180012223  pop     rsi
0x180012224  retn
```
