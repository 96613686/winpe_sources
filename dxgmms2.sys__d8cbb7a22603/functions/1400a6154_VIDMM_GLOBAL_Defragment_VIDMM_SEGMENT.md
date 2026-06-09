# VIDMM_GLOBAL::Defragment(VIDMM_SEGMENT *)

- ea: `0x1400a6154`
- end: `0x1400a63ef`
- name: `?Defragment@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_SEGMENT@@@Z`
- size: `667`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_SEGMENT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400cfba8`

## callees

- `0x1400120fc`
- `0x1400478bc`
- `0x1400478e0`
- `0x140059030`
- `0x140096a04`
- `0x14009ecf4`
- `0x1400a00dc`
- `0x1400a6154`
- `0x1400a6558`
- `0x1400a6a34`
- `0x1400b7bb0`
- `0x1400d53e8`
- `0x1400d6ec4`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x1400a6313`
- `ntoskrnl!PsIsSystemProcess` at `0x1400a6313`
- `watchdog!WdLogSingleEntry1` at `0x1400a6195`
- `watchdog!WdLogSingleEntry1` at `0x1400a6246`
- `watchdog!WdLogSingleEntry1` at `0x1400a62d4`
- `watchdog!WdLogSingleEntry1` at `0x1400a6195`
- `watchdog!WdLogSingleEntry1` at `0x1400a6246`
- `watchdog!WdLogSingleEntry1` at `0x1400a62d4`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::Defragment(VIDMM_GLOBAL *this, struct VIDMM_SEGMENT *a2)
{
  VIDMM_GLOBAL *v3; // rsi
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 v6; // rdx
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v7; // r14
  VIDMM_SEGMENT *v8; // rcx
  unsigned __int64 ActiveVprEnd; // rbx
  struct VIDMM_SEGMENT *v10; // rbx
  char *v11; // r15
  struct VIDMM_SEGMENT *v12; // r13
  __int64 v13; // rcx
  _QWORD *v14; // r13
  _QWORD *v15; // r15
  VIDMM_DEVICE *v16; // r12
  __int64 v17; // rcx
  __int64 v18; // r8
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v20; // [rsp+88h] [rbp+10h] BYREF

  v3 = this;
  v4 = *(_QWORD *)(*(_QWORD *)this + 128LL);
  *((_QWORD *)a2 + 63) = v4;
  if ( (*((_DWORD *)this + 786) & 0x4000) != 0 )
  {
    WdLogSingleEntry1(4, a2);
    WdLogGlobalForLineNumber = 30557;
  }
  else
  {
    v5 = *((unsigned __int16 *)a2 + 34);
    if ( (byte_140087203 & 4) != 0 )
      McTemplateK0x_EtwWriteTransfer(this, EventVidMmStartDefragment, v4, this);
    v20 = 0;
    VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 1002, &v20);
    v6 = *((_QWORD *)v3 + 3);
    if ( (*(_DWORD *)(352 * v5 + *(_QWORD *)(v6 + 3120) + 16) & 4) != 0
      && (*(_BYTE *)(v6 + 2588) & 8) != 0
      && (*((_DWORD *)v3 + 786) & 0x20000) == 0 )
    {
      WdLogSingleEntry1(4, a2);
      WdLogGlobalForLineNumber = 30603;
      VIDMM_GLOBAL::EnsureFlipQueuesSuspendedForMove(v3);
      v7 = v20;
      VIDMM_SEGMENT::TrimAllMarkedForEvictionAllocations(a2, v20);
      if ( (*((_BYTE *)a2 + 66) & 1) != 0 )
      {
        VIDMM_SEGMENT::GetActiveVprStart(a2);
        ActiveVprEnd = VIDMM_SEGMENT::GetActiveVprEnd(v8);
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, _QWORD))(*(_QWORD *)a2 + 96LL))(
          a2,
          v7,
          0);
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, unsigned __int64, _QWORD))(*(_QWORD *)a2 + 96LL))(
          a2,
          v7,
          ActiveVprEnd,
          *((_QWORD *)a2 + 5));
      }
      else
      {
        (*(void (__fastcall **)(struct VIDMM_SEGMENT *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, _QWORD, _QWORD))(*(_QWORD *)a2 + 96LL))(
          a2,
          v7,
          0,
          *((_QWORD *)a2 + 5));
      }
    }
    else
    {
      WdLogSingleEntry1(4, a2);
      v7 = v20;
      WdLogGlobalForLineNumber = 30640;
      v10 = (struct VIDMM_SEGMENT *)*((_QWORD *)a2 + 14);
      if ( v10 != (struct VIDMM_SEGMENT *)((char *)a2 + 112) )
      {
        do
        {
          v11 = (char *)v10 - 24;
          v12 = v10;
          v13 = *((_QWORD *)v10 - 3);
          v10 = *(struct VIDMM_SEGMENT **)v10;
          if ( !(unsigned __int8)PsIsSystemProcess(*(_QWORD *)(v13 + 16))
            && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v11 + 80LL) + 408LL) & 1) == 0 )
          {
            v14 = (_QWORD *)((char *)v12 + 16);
            v15 = (_QWORD *)*v14;
            while ( v15 != v14 )
            {
              v16 = (VIDMM_DEVICE *)v15[4];
              v15 = (_QWORD *)*v15;
              if ( *((_QWORD *)v16 + 3) )
              {
                if ( !*((_QWORD *)v16 + 23) )
                  VIDMM_DEVICE::PartiallySuspend(v16);
                VIDMM_DEVICE::FaultAllAllocations(v16, v7);
              }
            }
          }
        }
        while ( v10 != (struct VIDMM_SEGMENT *)((char *)a2 + 112) );
        v3 = this;
      }
      VIDMM_SEGMENT::OldDefragment(a2, v7);
    }
    VIDMM_GLOBAL::EndPreparation(v3, v7, 0xFFFFFFFF, 0, 0, 0, 0);
    VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(v3, 0, 0xFFFFFFFF);
    if ( (byte_140087203 & 4) != 0 )
      McTemplateK0x_EtwWriteTransfer(v17, EventVidMmEndDefragment, v18, v3);
  }
}

```

## disassembly

```asm
0x1400a6154  mov     [rsp+arg_10], rbx
0x1400a6159  mov     [rsp+arg_0], rcx
0x1400a615e  push    rbp
0x1400a615f  push    rsi
0x1400a6160  push    rdi
0x1400a6161  push    r12
0x1400a6163  push    r13
0x1400a6165  push    r14
0x1400a6167  push    r15
0x1400a6169  sub     rsp, 40h
0x1400a616d  mov     rax, [rcx]
0x1400a6170  mov     rdi, rdx
0x1400a6173  mov     rsi, rcx
0x1400a6176  mov     r8, [rax+80h]
0x1400a617d  mov     [rdx+1F8h], r8
0x1400a6184  test    dword ptr [rcx+0C48h], 4000h
0x1400a618e  jz      short loc_1400A61B0
0x1400a6190  mov     ecx, 4
0x1400a6195  call    cs:__imp_WdLogSingleEntry1
0x1400a619c  nop     dword ptr [rax+rax+00h]
0x1400a61a1  mov     cs:WdLogGlobalForLineNumber, 775Dh
0x1400a61ab  jmp     loc_1400A63D6
0x1400a61b0  movzx   ebx, word ptr [rdx+44h]
0x1400a61b4  mov     ebp, 4
0x1400a61b9  test    cs:byte_140087203, bpl
0x1400a61c0  jz      short loc_1400A61D1
0x1400a61c2  mov     r9, rsi
0x1400a61c5  lea     rdx, EventVidMmStartDefragment
0x1400a61cc  call    McTemplateK0x_EtwWriteTransfer
0x1400a61d1  lea     rax, [rsp+78h+arg_8]
0x1400a61d9  mov     [rsp+78h+arg_8], 0
0x1400a61e5  mov     [rsp+78h+var_50], rax
0x1400a61ea  xor     r9d, r9d
0x1400a61ed  xor     r8d, r8d
0x1400a61f0  mov     dword ptr [rsp+78h+var_58], 3EAh
0x1400a61f8  or      edx, 0FFFFFFFFh
0x1400a61fb  mov     rcx, rsi
0x1400a61fe  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400a6203  mov     rdx, [rsi+18h]
0x1400a6207  imul    rcx, rbx, 160h
0x1400a620e  mov     rax, [rdx+0C30h]
0x1400a6215  mov     ecx, [rcx+rax+10h]
0x1400a6219  test    bpl, cl
0x1400a621c  jz      loc_1400A62CF
0x1400a6222  test    byte ptr [rdx+0A1Ch], 8
0x1400a6229  setnz   cl
0x1400a622c  test    dword ptr [rsi+0C48h], 20000h
0x1400a6236  setz    al
0x1400a6239  test    al, cl
0x1400a623b  jz      loc_1400A62CF
0x1400a6241  mov     rdx, rdi
0x1400a6244  mov     ecx, ebp
0x1400a6246  call    cs:__imp_WdLogSingleEntry1
0x1400a624d  nop     dword ptr [rax+rax+00h]
0x1400a6252  mov     rcx, rsi; this
0x1400a6255  mov     cs:WdLogGlobalForLineNumber, 778Bh
0x1400a625f  call    ?EnsureFlipQueuesSuspendedForMove@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::EnsureFlipQueuesSuspendedForMove(void)
0x1400a6264  mov     r14, [rsp+78h+arg_8]
0x1400a626c  mov     rcx, rdi; this
0x1400a626f  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a6272  call    ?TrimAllMarkedForEvictionAllocations@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_SEGMENT::TrimAllMarkedForEvictionAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a6277  test    byte ptr [rdi+42h], 1
0x1400a627b  mov     rcx, rdi; this
0x1400a627e  jz      short loc_1400A62B4
0x1400a6280  call    ?GetActiveVprStart@VIDMM_SEGMENT@@QEBA_KXZ; VIDMM_SEGMENT::GetActiveVprStart(void)
0x1400a6285  mov     r9, rax
0x1400a6288  call    ?GetActiveVprEnd@VIDMM_SEGMENT@@QEBA_KXZ; VIDMM_SEGMENT::GetActiveVprEnd(void)
0x1400a628d  mov     rcx, [rdi]
0x1400a6290  mov     rbx, rax
0x1400a6293  xor     r8d, r8d
0x1400a6296  mov     rdx, r14
0x1400a6299  mov     rax, [rcx+60h]
0x1400a629d  mov     rcx, rdi
0x1400a62a0  call    _guard_dispatch_icall
0x1400a62a5  mov     rcx, [rdi]
0x1400a62a8  mov     r8, rbx
0x1400a62ab  mov     rax, [rcx+60h]
0x1400a62af  mov     rcx, rdi
0x1400a62b2  jmp     short loc_1400A62BE
0x1400a62b4  mov     rax, [rdi]
0x1400a62b7  xor     r8d, r8d
0x1400a62ba  mov     rax, [rax+60h]
0x1400a62be  mov     r9, [rdi+28h]
0x1400a62c2  mov     rdx, r14
0x1400a62c5  call    _guard_dispatch_icall
0x1400a62ca  jmp     loc_1400A6387
0x1400a62cf  mov     rdx, rdi
0x1400a62d2  mov     ecx, ebp
0x1400a62d4  call    cs:__imp_WdLogSingleEntry1
0x1400a62db  nop     dword ptr [rax+rax+00h]
0x1400a62e0  mov     r14, [rsp+78h+arg_8]
0x1400a62e8  lea     rax, [rdi+70h]
0x1400a62ec  mov     cs:WdLogGlobalForLineNumber, 77B0h
0x1400a62f6  mov     rbx, [rax]
0x1400a62f9  cmp     rbx, rax
0x1400a62fc  jz      short loc_1400A637C
0x1400a62fe  lea     rsi, [rdi+70h]
0x1400a6302  lea     r15, [rbx-18h]
0x1400a6306  mov     r13, rbx
0x1400a6309  mov     rcx, [r15]
0x1400a630c  mov     rbx, [rbx]
0x1400a630f  mov     rcx, [rcx+10h]
0x1400a6313  call    cs:__imp_PsIsSystemProcess
0x1400a631a  nop     dword ptr [rax+rax+00h]
0x1400a631f  test    al, al
0x1400a6321  jnz     short loc_1400A636F
0x1400a6323  mov     rax, [r15]
0x1400a6326  mov     rcx, [rax+50h]
0x1400a632a  test    byte ptr [rcx+198h], 1
0x1400a6331  jnz     short loc_1400A636F
0x1400a6333  add     r13, 10h
0x1400a6337  mov     r15, [r13+0]
0x1400a633b  jmp     short loc_1400A636A
0x1400a633d  mov     r12, [r15+20h]
0x1400a6341  mov     r15, [r15]
0x1400a6344  cmp     qword ptr [r12+18h], 0
0x1400a634a  jz      short loc_1400A636A
0x1400a634c  cmp     qword ptr [r12+0B8h], 0
0x1400a6355  jnz     short loc_1400A635F
0x1400a6357  mov     rcx, r12; this
0x1400a635a  call    ?PartiallySuspend@VIDMM_DEVICE@@QEAAXXZ; VIDMM_DEVICE::PartiallySuspend(void)
0x1400a635f  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a6362  mov     rcx, r12; this
0x1400a6365  call    ?FaultAllAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_DEVICE::FaultAllAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a636a  cmp     r15, r13
0x1400a636d  jnz     short loc_1400A633D
0x1400a636f  cmp     rbx, rsi
0x1400a6372  jnz     short loc_1400A6302
0x1400a6374  mov     rsi, [rsp+78h+arg_0]
0x1400a637c  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a637f  mov     rcx, rdi; this
0x1400a6382  call    ?OldDefragment@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_SEGMENT::OldDefragment(VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400a6387  mov     [rsp+78h+var_48], 0; struct _VIDSCH_SYNC_OBJECT *
0x1400a6390  xor     r9d, r9d; struct _KEVENT *
0x1400a6393  mov     [rsp+78h+var_50], 0; unsigned __int64
0x1400a639c  or      r8d, 0FFFFFFFFh; unsigned int
0x1400a63a0  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a63a3  mov     [rsp+78h+var_58], 0; bool
0x1400a63a8  mov     rcx, rsi; this
0x1400a63ab  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400a63b0  or      r8d, 0FFFFFFFFh; unsigned int
0x1400a63b4  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a63b6  mov     rcx, rsi; this
0x1400a63b9  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a63be  test    cs:byte_140087203, bpl
0x1400a63c5  jz      short loc_1400A63D6
0x1400a63c7  mov     r9, rsi
0x1400a63ca  lea     rdx, EventVidMmEndDefragment
0x1400a63d1  call    McTemplateK0x_EtwWriteTransfer
0x1400a63d6  mov     rbx, [rsp+78h+arg_10]
0x1400a63de  add     rsp, 40h
0x1400a63e2  pop     r15
0x1400a63e4  pop     r14
0x1400a63e6  pop     r13
0x1400a63e8  pop     r12
0x1400a63ea  pop     rdi
0x1400a63eb  pop     rsi
0x1400a63ec  pop     rbp
0x1400a63ed  retn
```
