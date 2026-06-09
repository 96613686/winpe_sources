# WorkItems::SubmitWork(Work *)

- ea: `0x18001a770`
- end: `0x18001a827`
- name: `?SubmitWork@WorkItems@@QEAAJPEAVWork@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(WorkItems *this, struct Work *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016f0c`
- `0x18001bd38`

## callees

- `0x180010664`
- `0x18001a770`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001a7c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001a7c9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a816`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a816`

## pseudocode

```c
__int64 __fastcall WorkItems::SubmitWork(WorkItems *this, struct Work *a2)
{
  struct _TP_WORK *ThreadpoolWork; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this, a2);
  }
  ThreadpoolWork = CreateThreadpoolWork(WorkItems::TpWorkCallback, a2, (PTP_CALLBACK_ENVIRON)((char *)this + 8));
  if ( !ThreadpoolWork )
    return 2147942414LL;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this, a2);
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  return 0;
}

```

## disassembly

```asm
0x18001a770  push    rbx
0x18001a772  push    rbp
0x18001a773  push    rsi
0x18001a774  push    rdi
0x18001a775  sub     rsp, 38h
0x18001a779  mov     rdi, rdx
0x18001a77c  mov     rsi, rcx
0x18001a77f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a786  lea     rbp, WPP_GLOBAL_Control
0x18001a78d  cmp     rcx, rbp
0x18001a790  jz      short loc_18001A7BB
0x18001a792  cmp     byte ptr [rcx+19h], 3
0x18001a796  jb      short loc_18001A7BB
0x18001a798  test    byte ptr [rcx+1Ch], 1
0x18001a79c  jz      short loc_18001A7BB
0x18001a79e  mov     rcx, [rcx+10h]
0x18001a7a2  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a7a9  mov     edx, 0Bh
0x18001a7ae  mov     [rsp+58h+var_38], rdi
0x18001a7b3  mov     r9, rsi
0x18001a7b6  call    WPP_SF_qq
0x18001a7bb  lea     r8, [rsi+8]; pcbe
0x18001a7bf  mov     rdx, rdi; pv
0x18001a7c2  lea     rcx, ?TpWorkCallback@WorkItems@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001a7c9  call    cs:__imp_CreateThreadpoolWork
0x18001a7cf  mov     rbx, rax
0x18001a7d2  test    rax, rax
0x18001a7d5  jnz     short loc_18001A7DE
0x18001a7d7  mov     eax, 8007000Eh
0x18001a7dc  jmp     short loc_18001A81E
0x18001a7de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7e5  cmp     rcx, rbp
0x18001a7e8  jz      short loc_18001A813
0x18001a7ea  cmp     byte ptr [rcx+19h], 3
0x18001a7ee  jb      short loc_18001A813
0x18001a7f0  test    byte ptr [rcx+1Ch], 1
0x18001a7f4  jz      short loc_18001A813
0x18001a7f6  mov     rcx, [rcx+10h]
0x18001a7fa  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a801  mov     edx, 0Ch
0x18001a806  mov     [rsp+58h+var_38], rdi
0x18001a80b  mov     r9, rsi
0x18001a80e  call    WPP_SF_qq
0x18001a813  mov     rcx, rbx; pwk
0x18001a816  call    cs:__imp_SubmitThreadpoolWork
0x18001a81c  xor     eax, eax
0x18001a81e  add     rsp, 38h
0x18001a822  pop     rdi
0x18001a823  pop     rsi
0x18001a824  pop     rbp
0x18001a825  pop     rbx
0x18001a826  retn
```
