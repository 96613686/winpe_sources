# VIDMM_GLOBAL::Defragment(VIDMM_SEGMENT *)

- ea: `0x1400a58c4`
- end: `0x1400a5b5f`
- name: `?Defragment@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_SEGMENT@@@Z`
- size: `667`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_SEGMENT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400c9d18`

## callees

- `0x14001265c`
- `0x1400475cc`
- `0x1400475f0`
- `0x140058760`
- `0x14009b1ac`
- `0x14009c7fc`
- `0x1400a38c4`
- `0x1400a58c4`
- `0x1400a5cc8`
- `0x1400a61a4`
- `0x1400b4274`
- `0x1400cf1c8`
- `0x1400d0134`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x1400a5a83`
- `ntoskrnl!PsIsSystemProcess` at `0x1400a5a83`
- `watchdog!WdLogSingleEntry1` at `0x1400a5905`
- `watchdog!WdLogSingleEntry1` at `0x1400a59b6`
- `watchdog!WdLogSingleEntry1` at `0x1400a5a44`
- `watchdog!WdLogSingleEntry1` at `0x1400a5905`
- `watchdog!WdLogSingleEntry1` at `0x1400a59b6`
- `watchdog!WdLogSingleEntry1` at `0x1400a5a44`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::Defragment(VIDMM_GLOBAL *this, struct VIDMM_SEGMENT *a2)
{
  VIDMM_GLOBAL *v3; // rsi
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 v6; // rdx
  VIDMM_SEGMENT *v7; // rcx
  unsigned __int64 ActiveVprEnd; // rbx
  struct VIDMM_SEGMENT *v9; // rbx
  char *v10; // r15
  struct VIDMM_SEGMENT *v11; // r13
  __int64 v12; // rcx
  _QWORD *v13; // r13
  _QWORD *v14; // r15
  VIDMM_DEVICE *v15; // r12
  __int64 v16; // rcx
  __int64 v17; // r8

  v3 = this;
  v4 = *(_QWORD *)(*(_QWORD *)this + 128LL);
  *((_QWORD *)a2 + 63) = v4;
  if ( (*((_DWORD *)this + 786) & 0x4000) != 0 )
  {
    WdLogSingleEntry1(4, a2);
    WdLogGlobalForLineNumber = 30274;
  }
  else
  {
    v5 = *((unsigned __int16 *)a2 + 34);
    if ( (byte_140086203 & 4) != 0 )
      McTemplateK0x_EtwWriteTransfer(this, EventVidMmStartDefragment, v4, this);
    VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 1002);
    v6 = *((_QWORD *)v3 + 3);
    if ( (*(_DWORD *)(352 * v5 + *(_QWORD *)(v6 + 3104) + 16) & 4) != 0
      && (*(_BYTE *)(v6 + 2572) & 8) != 0
      && (*((_DWORD *)v3 + 786) & 0x20000) == 0 )
    {
      WdLogSingleEntry1(4, a2);
      WdLogGlobalForLineNumber = 30320;
      VIDMM_GLOBAL::EnsureFlipQueuesSuspendedForMove(v3);
      VIDMM_SEGMENT::TrimAllMarkedForEvictionAllocations(a2, 0);
      if ( (*((_BYTE *)a2 + 66) & 1) != 0 )
      {
        VIDMM_SEGMENT::GetActiveVprStart(a2);
        ActiveVprEnd = VIDMM_SEGMENT::GetActiveVprEnd(v7);
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, _QWORD, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0, 0);
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, _QWORD, unsigned __int64, _QWORD))(*(_QWORD *)a2 + 96LL))(
          a2,
          0,
          ActiveVprEnd,
          *((_QWORD *)a2 + 5));
      }
      else
      {
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 96LL))(
          a2,
          0,
          0,
          *((_QWORD *)a2 + 5));
      }
    }
    else
    {
      WdLogSingleEntry1(4, a2);
      WdLogGlobalForLineNumber = 30357;
      v9 = (struct VIDMM_SEGMENT *)*((_QWORD *)a2 + 14);
      if ( v9 != (struct VIDMM_SEGMENT *)((char *)a2 + 112) )
      {
        do
        {
          v10 = (char *)v9 - 24;
          v11 = v9;
          v12 = *((_QWORD *)v9 - 3);
          v9 = *(struct VIDMM_SEGMENT **)v9;
          if ( !(unsigned __int8)PsIsSystemProcess(*(_QWORD *)(v12 + 16))
            && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v10 + 72LL) + 408LL) & 1) == 0 )
          {
            v13 = (_QWORD *)((char *)v11 + 16);
            v14 = (_QWORD *)*v13;
            while ( v14 != v13 )
            {
              v15 = (VIDMM_DEVICE *)v14[4];
              v14 = (_QWORD *)*v14;
              if ( *((_QWORD *)v15 + 3) )
              {
                if ( !*((_QWORD *)v15 + 23) )
                  VIDMM_DEVICE::PartiallySuspend(v15);
                VIDMM_DEVICE::FaultAllAllocations(v15, 0);
              }
            }
          }
        }
        while ( v9 != (struct VIDMM_SEGMENT *)((char *)a2 + 112) );
        v3 = this;
      }
      VIDMM_SEGMENT::OldDefragment(a2, 0);
    }
    VIDMM_GLOBAL::EndPreparation(v3, 0, 0xFFFFFFFF, 0, 0, 0, 0);
    VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(v3, 0, 0xFFFFFFFF);
    if ( (byte_140086203 & 4) != 0 )
      McTemplateK0x_EtwWriteTransfer(v16, EventVidMmEndDefragment, v17, v3);
  }
}

```

## disassembly

```asm
0x1400a58c4  mov     [rsp+arg_10], rbx
0x1400a58c9  mov     [rsp+arg_0], rcx
0x1400a58ce  push    rbp
0x1400a58cf  push    rsi
0x1400a58d0  push    rdi
0x1400a58d1  push    r12
0x1400a58d3  push    r13
0x1400a58d5  push    r14
0x1400a58d7  push    r15
0x1400a58d9  sub     rsp, 40h
0x1400a58dd  mov     rax, [rcx]
0x1400a58e0  mov     rdi, rdx
0x1400a58e3  mov     rsi, rcx
0x1400a58e6  mov     r8, [rax+80h]
0x1400a58ed  mov     [rdx+1F8h], r8
0x1400a58f4  test    dword ptr [rcx+0C48h], 4000h
0x1400a58fe  jz      short loc_1400A5920
0x1400a5900  mov     ecx, 4
0x1400a5905  call    cs:__imp_WdLogSingleEntry1
0x1400a590c  nop     dword ptr [rax+rax+00h]
0x1400a5911  mov     cs:WdLogGlobalForLineNumber, 7642h
0x1400a591b  jmp     loc_1400A5B46
0x1400a5920  movzx   ebx, word ptr [rdx+44h]
0x1400a5924  mov     ebp, 4
0x1400a5929  test    cs:byte_140086203, bpl
0x1400a5930  jz      short loc_1400A5941
0x1400a5932  mov     r9, rsi
0x1400a5935  lea     rdx, EventVidMmStartDefragment
0x1400a593c  call    McTemplateK0x_EtwWriteTransfer
0x1400a5941  lea     rax, [rsp+78h+arg_8]
0x1400a5949  mov     [rsp+78h+arg_8], 0
0x1400a5955  mov     [rsp+78h+var_50], rax
0x1400a595a  xor     r9d, r9d
0x1400a595d  xor     r8d, r8d
0x1400a5960  mov     dword ptr [rsp+78h+var_58], 3EAh
0x1400a5968  or      edx, 0FFFFFFFFh
0x1400a596b  mov     rcx, rsi
0x1400a596e  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400a5973  mov     rdx, [rsi+18h]
0x1400a5977  imul    rcx, rbx, 160h
0x1400a597e  mov     rax, [rdx+0C20h]
0x1400a5985  mov     ecx, [rcx+rax+10h]
0x1400a5989  test    bpl, cl
0x1400a598c  jz      loc_1400A5A3F
0x1400a5992  test    byte ptr [rdx+0A0Ch], 8
0x1400a5999  setnz   cl
0x1400a599c  test    dword ptr [rsi+0C48h], 20000h
0x1400a59a6  setz    al
0x1400a59a9  test    al, cl
0x1400a59ab  jz      loc_1400A5A3F
0x1400a59b1  mov     rdx, rdi
0x1400a59b4  mov     ecx, ebp
0x1400a59b6  call    cs:__imp_WdLogSingleEntry1
0x1400a59bd  nop     dword ptr [rax+rax+00h]
0x1400a59c2  mov     rcx, rsi; this
0x1400a59c5  mov     cs:WdLogGlobalForLineNumber, 7670h
0x1400a59cf  call    ?EnsureFlipQueuesSuspendedForMove@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::EnsureFlipQueuesSuspendedForMove(void)
0x1400a59d4  mov     r14, [rsp+78h+arg_8]
0x1400a59dc  mov     rcx, rdi; this
0x1400a59df  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a59e2  call    ?TrimAllMarkedForEvictionAllocations@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_SEGMENT::TrimAllMarkedForEvictionAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a59e7  test    byte ptr [rdi+42h], 1
0x1400a59eb  mov     rcx, rdi; this
0x1400a59ee  jz      short loc_1400A5A24
0x1400a59f0  call    ?GetActiveVprStart@VIDMM_SEGMENT@@QEBA_KXZ; VIDMM_SEGMENT::GetActiveVprStart(void)
0x1400a59f5  mov     r9, rax
0x1400a59f8  call    ?GetActiveVprEnd@VIDMM_SEGMENT@@QEBA_KXZ; VIDMM_SEGMENT::GetActiveVprEnd(void)
0x1400a59fd  mov     rcx, [rdi]
0x1400a5a00  mov     rbx, rax
0x1400a5a03  xor     r8d, r8d
0x1400a5a06  mov     rdx, r14
0x1400a5a09  mov     rax, [rcx+60h]
0x1400a5a0d  mov     rcx, rdi
0x1400a5a10  call    _guard_dispatch_icall
0x1400a5a15  mov     rcx, [rdi]
0x1400a5a18  mov     r8, rbx
0x1400a5a1b  mov     rax, [rcx+60h]
0x1400a5a1f  mov     rcx, rdi
0x1400a5a22  jmp     short loc_1400A5A2E
0x1400a5a24  mov     rax, [rdi]
0x1400a5a27  xor     r8d, r8d
0x1400a5a2a  mov     rax, [rax+60h]
0x1400a5a2e  mov     r9, [rdi+28h]
0x1400a5a32  mov     rdx, r14
0x1400a5a35  call    _guard_dispatch_icall
0x1400a5a3a  jmp     loc_1400A5AF7
0x1400a5a3f  mov     rdx, rdi
0x1400a5a42  mov     ecx, ebp
0x1400a5a44  call    cs:__imp_WdLogSingleEntry1
0x1400a5a4b  nop     dword ptr [rax+rax+00h]
0x1400a5a50  mov     r14, [rsp+78h+arg_8]
0x1400a5a58  lea     rax, [rdi+70h]
0x1400a5a5c  mov     cs:WdLogGlobalForLineNumber, 7695h
0x1400a5a66  mov     rbx, [rax]
0x1400a5a69  cmp     rbx, rax
0x1400a5a6c  jz      short loc_1400A5AEC
0x1400a5a6e  lea     rsi, [rdi+70h]
0x1400a5a72  lea     r15, [rbx-18h]
0x1400a5a76  mov     r13, rbx
0x1400a5a79  mov     rcx, [r15]
0x1400a5a7c  mov     rbx, [rbx]
0x1400a5a7f  mov     rcx, [rcx+10h]
0x1400a5a83  call    cs:__imp_PsIsSystemProcess
0x1400a5a8a  nop     dword ptr [rax+rax+00h]
0x1400a5a8f  test    al, al
0x1400a5a91  jnz     short loc_1400A5ADF
0x1400a5a93  mov     rax, [r15]
0x1400a5a96  mov     rcx, [rax+48h]
0x1400a5a9a  test    byte ptr [rcx+198h], 1
0x1400a5aa1  jnz     short loc_1400A5ADF
0x1400a5aa3  add     r13, 10h
0x1400a5aa7  mov     r15, [r13+0]
0x1400a5aab  jmp     short loc_1400A5ADA
0x1400a5aad  mov     r12, [r15+20h]
0x1400a5ab1  mov     r15, [r15]
0x1400a5ab4  cmp     qword ptr [r12+18h], 0
0x1400a5aba  jz      short loc_1400A5ADA
0x1400a5abc  cmp     qword ptr [r12+0B8h], 0
0x1400a5ac5  jnz     short loc_1400A5ACF
0x1400a5ac7  mov     rcx, r12; this
0x1400a5aca  call    ?PartiallySuspend@VIDMM_DEVICE@@QEAAXXZ; VIDMM_DEVICE::PartiallySuspend(void)
0x1400a5acf  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a5ad2  mov     rcx, r12; this
0x1400a5ad5  call    ?FaultAllAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_DEVICE::FaultAllAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a5ada  cmp     r15, r13
0x1400a5add  jnz     short loc_1400A5AAD
0x1400a5adf  cmp     rbx, rsi
0x1400a5ae2  jnz     short loc_1400A5A72
0x1400a5ae4  mov     rsi, [rsp+78h+arg_0]
0x1400a5aec  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a5aef  mov     rcx, rdi; this
0x1400a5af2  call    ?OldDefragment@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_SEGMENT::OldDefragment(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a5af7  mov     [rsp+78h+var_48], 0; struct _VIDSCH_SYNC_OBJECT *
0x1400a5b00  xor     r9d, r9d; Event
0x1400a5b03  mov     [rsp+78h+var_50], 0; unsigned __int64
0x1400a5b0c  or      r8d, 0FFFFFFFFh; unsigned int
0x1400a5b10  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a5b13  mov     [rsp+78h+var_58], 0; bool
0x1400a5b18  mov     rcx, rsi; this
0x1400a5b1b  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400a5b20  or      r8d, 0FFFFFFFFh; unsigned int
0x1400a5b24  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a5b26  mov     rcx, rsi; this
0x1400a5b29  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a5b2e  test    cs:byte_140086203, bpl
0x1400a5b35  jz      short loc_1400A5B46
0x1400a5b37  mov     r9, rsi
0x1400a5b3a  lea     rdx, EventVidMmEndDefragment
0x1400a5b41  call    McTemplateK0x_EtwWriteTransfer
0x1400a5b46  mov     rbx, [rsp+78h+arg_10]
0x1400a5b4e  add     rsp, 40h
0x1400a5b52  pop     r15
0x1400a5b54  pop     r14
0x1400a5b56  pop     r13
0x1400a5b58  pop     r12
0x1400a5b5a  pop     rdi
0x1400a5b5b  pop     rsi
0x1400a5b5c  pop     rbp
0x1400a5b5d  retn
```
