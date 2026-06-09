# NdrpCloneInOnlyCorrArgs(_NDR_DCOM_ASYNC_MESSAGE *,uchar const *)

- ea: `0x180187024`
- end: `0x180187384`
- name: `?NdrpCloneInOnlyCorrArgs@@YAXPEAU_NDR_DCOM_ASYNC_MESSAGE@@PEBE@Z`
- size: `864`
- prototype: `void __fastcall(_NDR_DCOM_ASYNC_MESSAGE *pAsyncMsg, const unsigned __int8 *pTypeFormat)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c63c4`
- `0x1800c6ed4`

## callees

- `0x180187024`
- `0x1802135e9`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18018735c`
- `RPCRT4!RpcRaiseException` at `0x180187368`
- `RPCRT4!RpcRaiseException` at `0x18018735c`
- `RPCRT4!RpcRaiseException` at `0x180187368`
- `RPCRT4!I_RpcBCacheAllocate` at `0x1801870af`
- `RPCRT4!I_RpcBCacheAllocate` at `0x18018716b`
- `RPCRT4!I_RpcBCacheAllocate` at `0x180187235`
- `RPCRT4!I_RpcBCacheAllocate` at `0x1801872d3`
- `RPCRT4!I_RpcBCacheAllocate` at `0x1801870af`
- `RPCRT4!I_RpcBCacheAllocate` at `0x18018716b`
- `RPCRT4!I_RpcBCacheAllocate` at `0x180187235`
- `RPCRT4!I_RpcBCacheAllocate` at `0x1801872d3`
- `RPCRT4!NdrGetTypeFlags` at `0x18018713f`
- `RPCRT4!NdrGetTypeFlags` at `0x1801871f4`
- `RPCRT4!NdrGetTypeFlags` at `0x18018713f`
- `RPCRT4!NdrGetTypeFlags` at `0x1801871f4`
- `RPCRT4!SimpleTypeMemorySize` at `0x18018704e`
- `RPCRT4!SimpleTypeMemorySize` at `0x1801870d2`
- `RPCRT4!SimpleTypeMemorySize` at `0x1801871b3`
- `RPCRT4!SimpleTypeMemorySize` at `0x18018727d`
- `RPCRT4!SimpleTypeMemorySize` at `0x180187313`

## pseudocode

```c
void __fastcall NdrpCloneInOnlyCorrArgs(_NDR_DCOM_ASYNC_MESSAGE *pAsyncMsg, const unsigned __int8 *pTypeFormat)
{
  int nBeginParams; // eax
  _NDR_DCOM_ASYNC_MESSAGE *v3; // rdi
  unsigned __int8 *BeginStack; // r12
  int v5; // r15d
  _WORD *BeginParams; // r13
  __int64 v7; // rbp
  __int64 v8; // r14
  unsigned __int64 BytesRemaining; // rcx
  _LIST_ENTRY **v10; // rax
  _LIST_ENTRY *p_MemoryList; // rcx
  _LIST_ENTRY *Flink; // rdx
  unsigned __int8 *pBlockPointer; // rbx
  const unsigned __int8 *v14; // rbx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  _LIST_ENTRY **v17; // rax
  _LIST_ENTRY *v18; // rcx
  _LIST_ENTRY *v19; // rdx
  unsigned __int8 *v20; // rsi
  const unsigned __int8 *v21; // rsi
  unsigned __int64 v22; // rcx
  _LIST_ENTRY **v23; // rax
  _LIST_ENTRY *v24; // rcx
  _LIST_ENTRY *v25; // rdx
  _OWORD **v26; // rax
  unsigned __int64 v27; // rdx
  _LIST_ENTRY **v28; // rax
  _LIST_ENTRY *v29; // rcx
  _LIST_ENTRY *v30; // rdx
  int v31; // [rsp+60h] [rbp+8h]
  const unsigned __int8 *v32; // [rsp+68h] [rbp+10h]

  v32 = pTypeFormat;
  nBeginParams = pAsyncMsg->nBeginParams;
  v3 = pAsyncMsg;
  BeginStack = pAsyncMsg->BeginStack;
  v5 = 0;
  BeginParams = pAsyncMsg->BeginParams;
  v7 = SimpleTypeMemorySize;
  v31 = nBeginParams;
  while ( v5 < nBeginParams )
  {
    if ( (BeginParams[3 * v5] & 0x400) == 0 )
      goto LABEL_33;
    v8 = (unsigned __int16)BeginParams[3 * v5 + 1];
    if ( (BeginParams[3 * v5] & 0x40) != 0 )
    {
      if ( (BeginParams[3 * v5] & 0x100) == 0 )
        goto LABEL_33;
      BytesRemaining = v3->ProcContext.AllocateContext.BytesRemaining;
      if ( BytesRemaining < 0x10 )
      {
        v10 = (_LIST_ENTRY **)I_RpcBCacheAllocate(4096);
        if ( !v10 )
          goto LABEL_35;
        p_MemoryList = &v3->ProcContext.AllocateContext.MemoryList;
        Flink = v3->ProcContext.AllocateContext.MemoryList.Flink;
        if ( Flink->Blink != &v3->ProcContext.AllocateContext.MemoryList )
          goto LABEL_34;
        v7 = SimpleTypeMemorySize;
        v10[1] = p_MemoryList;
        *v10 = Flink;
        Flink->Blink = (_LIST_ENTRY *)v10;
        p_MemoryList->Flink = (_LIST_ENTRY *)v10;
        v3->ProcContext.AllocateContext.pBlockPointer = (unsigned __int8 *)(v10 + 2);
        BytesRemaining = 4080;
      }
      pBlockPointer = v3->ProcContext.AllocateContext.pBlockPointer;
      v3->ProcContext.AllocateContext.pBlockPointer = pBlockPointer + 16;
      v3->ProcContext.AllocateContext.BytesRemaining = BytesRemaining - 16;
      memcpy_0(
        pBlockPointer,
        *(const void **)&BeginStack[v8],
        *(unsigned __int8 *)(LOBYTE(BeginParams[3 * v5 + 2]) + v7));
      *(_QWORD *)&BeginStack[v8] = pBlockPointer;
    }
    else
    {
      v14 = &pTypeFormat[(unsigned __int16)BeginParams[3 * v5 + 2]];
      LOBYTE(pAsyncMsg) = *v14;
      if ( (NdrGetTypeFlags(pAsyncMsg) & 0x200) != 0 )
      {
        if ( (v14[1] & 8) != 0 )
        {
          v16 = v3->ProcContext.AllocateContext.BytesRemaining;
          if ( v16 < 0x10 )
          {
            v17 = (_LIST_ENTRY **)I_RpcBCacheAllocate(4096);
            if ( !v17 )
              goto LABEL_35;
            v18 = &v3->ProcContext.AllocateContext.MemoryList;
            v19 = v3->ProcContext.AllocateContext.MemoryList.Flink;
            if ( v19->Blink != &v3->ProcContext.AllocateContext.MemoryList )
              goto LABEL_34;
            v17[1] = v18;
            *v17 = v19;
            v19->Blink = (_LIST_ENTRY *)v17;
            v18->Flink = (_LIST_ENTRY *)v17;
            v3->ProcContext.AllocateContext.pBlockPointer = (unsigned __int8 *)(v17 + 2);
            v16 = 4080;
          }
          v20 = v3->ProcContext.AllocateContext.pBlockPointer;
          v7 = SimpleTypeMemorySize;
          v3->ProcContext.AllocateContext.pBlockPointer = v20 + 16;
          v3->ProcContext.AllocateContext.BytesRemaining = v16 - 16;
          memcpy_0(v20, *(const void **)&BeginStack[v8], *((unsigned __int8 *)&SimpleTypeMemorySize + v14[2]));
        }
        else
        {
          v21 = &v14[*((__int16 *)v14 + 1)];
          LOBYTE(v15) = *v21;
          if ( (((NdrGetTypeFlags(v15) & 0x200) != 0) & (unsigned __int8)~(v14[1] >> 3)) == 0
            || v21[*((__int16 *)v21 + 1)] != 21 )
          {
LABEL_36:
            RpcRaiseException(1766);
          }
          v22 = v3->ProcContext.AllocateContext.BytesRemaining;
          if ( v22 < 0x20 )
          {
            v23 = (_LIST_ENTRY **)I_RpcBCacheAllocate(4096);
            if ( !v23 )
              goto LABEL_35;
            v24 = &v3->ProcContext.AllocateContext.MemoryList;
            v25 = v3->ProcContext.AllocateContext.MemoryList.Flink;
            if ( v25->Blink != &v3->ProcContext.AllocateContext.MemoryList )
              goto LABEL_34;
            v23[1] = v24;
            *v23 = v25;
            v25->Blink = (_LIST_ENTRY *)v23;
            v24->Flink = (_LIST_ENTRY *)v23;
            v3->ProcContext.AllocateContext.pBlockPointer = (unsigned __int8 *)(v23 + 2);
            v22 = 4080;
          }
          v20 = v3->ProcContext.AllocateContext.pBlockPointer;
          v7 = SimpleTypeMemorySize;
          v3->ProcContext.AllocateContext.pBlockPointer = v20 + 32;
          v3->ProcContext.AllocateContext.BytesRemaining = v22 - 32;
          *(_QWORD *)v20 = v20 + 8;
          v26 = *(_OWORD ***)&BeginStack[v8];
          pAsyncMsg = (_NDR_DCOM_ASYNC_MESSAGE *)*v26;
          *(_OWORD *)(v20 + 8) = **v26;
        }
        *(_QWORD *)&BeginStack[v8] = v20;
      }
      else
      {
        if ( *v14 != 21 )
          goto LABEL_36;
        v27 = v3->ProcContext.AllocateContext.BytesRemaining;
        if ( v27 < 0x10 )
        {
          v28 = (_LIST_ENTRY **)I_RpcBCacheAllocate(4096);
          if ( !v28 )
LABEL_35:
            RpcRaiseException(14);
          v29 = &v3->ProcContext.AllocateContext.MemoryList;
          v30 = v3->ProcContext.AllocateContext.MemoryList.Flink;
          if ( v30->Blink != &v3->ProcContext.AllocateContext.MemoryList )
LABEL_34:
            __fastfail(3u);
          *v28 = v30;
          v28[1] = v29;
          v30->Blink = (_LIST_ENTRY *)v28;
          v27 = 4080;
          v29->Flink = (_LIST_ENTRY *)v28;
          v3->ProcContext.AllocateContext.pBlockPointer = (unsigned __int8 *)(v28 + 2);
        }
        pAsyncMsg = (_NDR_DCOM_ASYNC_MESSAGE *)v3->ProcContext.AllocateContext.pBlockPointer;
        v7 = SimpleTypeMemorySize;
        v3->ProcContext.AllocateContext.pBlockPointer = (unsigned __int8 *)&pAsyncMsg->BeginParams;
        v3->ProcContext.AllocateContext.BytesRemaining = v27 - 16;
        *(_OWORD *)&pAsyncMsg->Version = *(_OWORD *)*(_QWORD *)&BeginStack[v8];
        *(_QWORD *)&BeginStack[v8] = pAsyncMsg;
      }
    }
    pTypeFormat = v32;
LABEL_33:
    nBeginParams = v31;
    ++v5;
  }
}

```

## disassembly

```asm
0x180187024  mov     [rsp+arg_10], rbx
0x180187029  mov     [rsp+arg_8], pTypeFormat
0x18018702e  push    rbp
0x18018702f  push    rsi
0x180187030  push    rdi
0x180187031  push    r12
0x180187033  push    r13
0x180187035  push    r14
0x180187037  push    r15
0x180187039  sub     rsp, 20h
0x18018703d  mov     eax, [pAsyncMsg+0Ch]
0x180187040  mov     rdi, pAsyncMsg
0x180187043  mov     r12, [pAsyncMsg+28h]
0x180187047  xor     r15d, r15d
0x18018704a  mov     r13, [pAsyncMsg+10h]
0x18018704e  mov     rbp, cs:__imp_SimpleTypeMemorySize
0x180187055  mov     [rsp+58h+arg_0], eax
0x180187059  cmp     r15d, eax
0x18018705c  jge     loc_18018736F
0x180187062  movsxd  rax, r15d
0x180187065  lea     rsi, [rax+rax*2]
0x180187069  mov     eax, 400h
0x18018706e  test    [r13+rsi*2+0], ax
0x180187074  jz      loc_180187344
0x18018707a  test    byte ptr [r13+rsi*2+0], 40h
0x180187080  movzx   r14d, word ptr [r13+rsi*2+2]
0x180187086  jz      loc_180187134
0x18018708c  mov     eax, 100h
0x180187091  test    [r13+rsi*2+0], ax
0x180187097  jz      loc_180187344
0x18018709d  mov     pAsyncMsg, [rdi+368h]
0x1801870a4  cmp     pAsyncMsg, 10h
0x1801870a8  jnb     short loc_1801870F7
0x1801870aa  mov     ecx, 1000h
0x1801870af  call    cs:__imp_I_RpcBCacheAllocate
0x1801870b5  test    rax, rax
0x1801870b8  jz      loc_180187357
0x1801870be  lea     pAsyncMsg, [rdi+358h]
0x1801870c5  mov     pTypeFormat, [pAsyncMsg]
0x1801870c8  cmp     [pTypeFormat+8], pAsyncMsg
0x1801870cc  jnz     loc_180187350
0x1801870d2  mov     rbp, cs:__imp_SimpleTypeMemorySize
0x1801870d9  mov     [rax+8], pAsyncMsg
0x1801870dd  mov     [rax], pTypeFormat
0x1801870e0  mov     [pTypeFormat+8], rax
0x1801870e4  mov     [pAsyncMsg], rax
0x1801870e7  add     rax, 10h
0x1801870eb  mov     [rdi+350h], rax
0x1801870f2  mov     ecx, 0FF0h
0x1801870f7  mov     rbx, [rdi+350h]
0x1801870fe  lea     rax, [rbx+10h]
0x180187102  mov     [rdi+350h], rax
0x180187109  lea     rax, [pAsyncMsg-10h]
0x18018710d  mov     [rdi+368h], rax
0x180187114  mov     pAsyncMsg, rbx; void *
0x180187117  movzx   eax, byte ptr [r13+rsi*2+4]
0x18018711d  mov     pTypeFormat, [r14+r12]; Src
0x180187121  movzx   r8d, byte ptr [rax+rbp]; Size
0x180187126  call    memcpy_0
0x18018712b  mov     [r14+r12], rbx
0x18018712f  jmp     loc_18018733F
0x180187134  movzx   ebx, word ptr [r13+rsi*2+4]
0x18018713a  add     rbx, pTypeFormat
0x18018713d  mov     cl, [rbx]
0x18018713f  call    cs:__imp_NdrGetTypeFlags
0x180187145  bt      eax, 9
0x180187149  jnb     loc_1801872B8
0x18018714f  test    byte ptr [rbx+1], 8
0x180187153  jz      loc_1801871EA
0x180187159  mov     pAsyncMsg, [rdi+368h]
0x180187160  cmp     pAsyncMsg, 10h
0x180187164  jnb     short loc_1801871AC
0x180187166  mov     ecx, 1000h
0x18018716b  call    cs:__imp_I_RpcBCacheAllocate
0x180187171  test    rax, rax
0x180187174  jz      loc_180187357
0x18018717a  lea     pAsyncMsg, [rdi+358h]
0x180187181  mov     pTypeFormat, [pAsyncMsg]
0x180187184  cmp     [pTypeFormat+8], pAsyncMsg
0x180187188  jnz     loc_180187350
0x18018718e  mov     [rax+8], pAsyncMsg
0x180187192  mov     [rax], pTypeFormat
0x180187195  mov     [pTypeFormat+8], rax
0x180187199  mov     [pAsyncMsg], rax
0x18018719c  add     rax, 10h
0x1801871a0  mov     [rdi+350h], rax
0x1801871a7  mov     ecx, 0FF0h
0x1801871ac  mov     rsi, [rdi+350h]
0x1801871b3  mov     rbp, cs:__imp_SimpleTypeMemorySize
0x1801871ba  lea     rax, [rsi+10h]
0x1801871be  mov     [rdi+350h], rax
0x1801871c5  lea     rax, [pAsyncMsg-10h]
0x1801871c9  mov     [rdi+368h], rax
0x1801871d0  mov     pAsyncMsg, rsi; void *
0x1801871d3  movzx   eax, byte ptr [rbx+2]
0x1801871d7  mov     pTypeFormat, [r14+r12]; Src
0x1801871db  movzx   r8d, byte ptr [rax+rbp]; Size
0x1801871e0  call    memcpy_0
0x1801871e5  jmp     loc_1801872AF
0x1801871ea  movsx   rsi, word ptr [rbx+2]
0x1801871ef  add     rsi, rbx
0x1801871f2  mov     cl, [rsi]
0x1801871f4  call    cs:__imp_NdrGetTypeFlags
0x1801871fa  mov     cl, [rbx+1]
0x1801871fd  bt      eax, 9
0x180187201  setb    al
0x180187204  shr     cl, 3
0x180187207  not     cl
0x180187209  and     cl, al
0x18018720b  test    cl, 1
0x18018720e  jz      loc_180187363
0x180187214  movsx   rax, word ptr [rsi+2]
0x180187219  cmp     byte ptr [rax+rsi], 15h
0x18018721d  jnz     loc_180187363
0x180187223  mov     pAsyncMsg, [rdi+368h]
0x18018722a  cmp     pAsyncMsg, 20h ; ' '
0x18018722e  jnb     short loc_180187276
0x180187230  mov     ecx, 1000h
0x180187235  call    cs:__imp_I_RpcBCacheAllocate
0x18018723b  test    rax, rax
0x18018723e  jz      loc_180187357
0x180187244  lea     pAsyncMsg, [rdi+358h]
0x18018724b  mov     pTypeFormat, [pAsyncMsg]
0x18018724e  cmp     [pTypeFormat+8], pAsyncMsg
0x180187252  jnz     loc_180187350
0x180187258  mov     [rax+8], pAsyncMsg
0x18018725c  mov     [rax], pTypeFormat
0x18018725f  mov     [pTypeFormat+8], rax
0x180187263  mov     [pAsyncMsg], rax
0x180187266  add     rax, 10h
0x18018726a  mov     [rdi+350h], rax
0x180187271  mov     ecx, 0FF0h
0x180187276  mov     rsi, [rdi+350h]
0x18018727d  mov     rbp, cs:__imp_SimpleTypeMemorySize
0x180187284  lea     rax, [rsi+20h]
0x180187288  mov     [rdi+350h], rax
0x18018728f  lea     pTypeFormat, [rsi+8]
0x180187293  lea     rax, [pAsyncMsg-20h]
0x180187297  mov     [rdi+368h], rax
0x18018729e  mov     [rsi], pTypeFormat
0x1801872a1  mov     rax, [r14+r12]
0x1801872a5  mov     pAsyncMsg, [rax]
0x1801872a8  movups  xmm0, xmmword ptr [pAsyncMsg]
0x1801872ab  movdqu  xmmword ptr [pTypeFormat], xmm0
0x1801872af  mov     [r14+r12], rsi
0x1801872b3  jmp     loc_18018733F
0x1801872b8  cmp     byte ptr [rbx], 15h
0x1801872bb  jnz     loc_180187363
0x1801872c1  mov     pTypeFormat, [rdi+368h]
0x1801872c8  cmp     pTypeFormat, 10h
0x1801872cc  jnb     short loc_18018730C
0x1801872ce  mov     ecx, 1000h
0x1801872d3  call    cs:__imp_I_RpcBCacheAllocate
0x1801872d9  test    rax, rax
0x1801872dc  jz      short loc_180187357
0x1801872de  lea     pAsyncMsg, [rdi+358h]
0x1801872e5  mov     pTypeFormat, [pAsyncMsg]
0x1801872e8  cmp     [pTypeFormat+8], pAsyncMsg
0x1801872ec  jnz     short loc_180187350
0x1801872ee  mov     [rax], pTypeFormat
0x1801872f1  mov     [rax+8], pAsyncMsg
0x1801872f5  mov     [pTypeFormat+8], rax
0x1801872f9  mov     edx, 0FF0h
0x1801872fe  mov     [pAsyncMsg], rax
0x180187301  add     rax, 10h
0x180187305  mov     [rdi+350h], rax
0x18018730c  mov     pAsyncMsg, [rdi+350h]
0x180187313  mov     rbp, cs:__imp_SimpleTypeMemorySize
0x18018731a  lea     rax, [pAsyncMsg+10h]
0x18018731e  mov     [rdi+350h], rax
0x180187325  lea     rax, [pTypeFormat-10h]
0x180187329  mov     [rdi+368h], rax
0x180187330  mov     rax, [r14+r12]
0x180187334  movups  xmm0, xmmword ptr [rax]
0x180187337  movdqu  xmmword ptr [pAsyncMsg], xmm0
0x18018733b  mov     [r14+r12], pAsyncMsg
0x18018733f  mov     pTypeFormat, [rsp+58h+arg_8]
0x180187344  mov     eax, [rsp+58h+arg_0]
0x180187348  inc     r15d
0x18018734b  jmp     loc_180187059
0x180187350  mov     ecx, 3
0x180187355  int     29h; Win8: RtlFailFast(ecx)
0x180187357  mov     ecx, 0Eh; exception
0x18018735c  call    cs:__imp_RpcRaiseException
0x180187362  int     3; Trap to Debugger
0x180187363  mov     ecx, 6E6h; exception
0x180187368  call    cs:__imp_RpcRaiseException
0x18018736e  int     3; Trap to Debugger
0x18018736f  mov     rbx, [rsp+58h+arg_10]
0x180187374  add     rsp, 20h
0x180187378  pop     r15
0x18018737a  pop     r14
0x18018737c  pop     r13
0x18018737e  pop     r12
0x180187380  pop     rdi
0x180187381  pop     rsi
0x180187382  pop     rbp
0x180187383  retn
```
