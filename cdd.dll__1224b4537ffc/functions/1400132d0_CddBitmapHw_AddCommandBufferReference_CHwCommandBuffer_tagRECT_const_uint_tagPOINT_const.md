# CddBitmapHw::AddCommandBufferReference(CHwCommandBuffer *,tagRECT const *,uint,tagPOINT const *)

- ea: `0x1400132d0`
- end: `0x1400133c0`
- name: `?AddCommandBufferReference@CddBitmapHw@@UEAAXPEAVCHwCommandBuffer@@PEBUtagRECT@@IPEBUtagPOINT@@@Z`
- size: `240`
- prototype: `void(CddBitmapHw *__hidden this, struct CHwCommandBuffer *, const struct tagRECT *, unsigned int, const struct tagPOINT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400132d0`
- `0x1400133d0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140013369`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140013369`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400133a1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400133a1`

## pseudocode

```c
void __fastcall CddBitmapHw::AddCommandBufferReference(
        CddBitmapHw *this,
        struct CHwCommandBuffer *a2,
        const struct tagRECT *a3,
        unsigned int a4,
        const struct tagPOINT *a5)
{
  __int64 v7; // rcx
  __int64 v10; // rdi
  struct CHwCommandBuffer **v11; // r8
  struct CHwCommandBuffer *v12; // rcx
  _OWORD v13[5]; // [rsp+20h] [rbp-58h] BYREF

  v7 = *((_QWORD *)this + 1);
  if ( *(_BYTE *)(v7 + 2719) )
  {
    memset(v13, 0, 48);
    *(_QWORD *)&v13[0] = *(_QWORD *)(v7 + 2488);
    (*(void (__fastcall **)(__int64, _QWORD, _OWORD *))(v7 + 264))(8012, 0, v13);
  }
  v10 = *((unsigned int *)a2 + 2);
  if ( !*((_BYTE *)this + v10 + 44) )
  {
    v11 = (struct CHwCommandBuffer **)*((_QWORD *)a2 + 264);
    if ( *v11 != (struct CHwCommandBuffer *)((char *)a2 + 2104) )
      __fastfail(3u);
    v12 = (CddBitmapHw *)((char *)this + 16 * v10 + 96);
    *(_QWORD *)v12 = (char *)a2 + 2104;
    *((_QWORD *)v12 + 1) = v11;
    *v11 = v12;
    *((_QWORD *)a2 + 264) = v12;
    *((_BYTE *)this + v10 + 44) = 1;
  }
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 147));
  CDirtyRegion::AddRects((CddBitmapHw *)((char *)this + 288 * v10 + 600), a3, a4, a5);
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)this + 147));
}

```

## disassembly

```asm
0x1400132d0  push    rbx
0x1400132d2  push    rbp
0x1400132d3  push    rsi
0x1400132d4  push    rdi
0x1400132d5  push    r14
0x1400132d7  sub     rsp, 50h
0x1400132db  mov     rbx, rcx
0x1400132de  mov     ebp, r9d
0x1400132e1  mov     rcx, [rcx+8]
0x1400132e5  mov     r14, r8
0x1400132e8  mov     rsi, rdx
0x1400132eb  cmp     byte ptr [rcx+0A9Fh], 0
0x1400132f2  jz      short loc_14001332A
0x1400132f4  xorps   xmm0, xmm0
0x1400132f7  lea     r8, [rsp+78h+var_58]
0x1400132fc  movups  [rsp+78h+var_58], xmm0
0x140013301  xor     edx, edx
0x140013303  movups  [rsp+78h+var_48], xmm0
0x140013308  movups  [rsp+78h+var_38], xmm0
0x14001330d  mov     rax, [rcx+9B8h]
0x140013314  mov     qword ptr [rsp+78h+var_58], rax
0x140013319  mov     rax, [rcx+108h]
0x140013320  mov     ecx, 1F4Ch
0x140013325  call    _guard_dispatch_icall
0x14001332a  mov     edi, [rsi+8]
0x14001332d  cmp     byte ptr [rdi+rbx+2Ch], 0
0x140013332  jnz     short loc_140013362
0x140013334  lea     rdx, [rsi+838h]
0x14001333b  mov     r8, [rdx+8]
0x14001333f  cmp     [r8], rdx
0x140013342  jnz     short loc_1400133B9
0x140013344  lea     rcx, [rdi+6]
0x140013348  shl     rcx, 4
0x14001334c  add     rcx, rbx
0x14001334f  mov     [rcx], rdx
0x140013352  mov     [rcx+8], r8
0x140013356  mov     [r8], rcx
0x140013359  mov     [rdx+8], rcx
0x14001335d  mov     byte ptr [rdi+rbx+2Ch], 1
0x140013362  mov     rcx, [rbx+498h]
0x140013369  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140013370  nop     dword ptr [rax+rax+00h]
0x140013375  mov     r9, [rsp+78h+arg_20]; struct tagPOINT *
0x14001337d  lea     rcx, [rdi+rdi*8]
0x140013381  shl     rcx, 5
0x140013385  mov     r8d, ebp; unsigned int
0x140013388  add     rcx, 258h
0x14001338f  mov     rdx, r14; struct tagRECT *
0x140013392  add     rcx, rbx; this
0x140013395  call    ?AddRects@CDirtyRegion@@QEAAXPEBUtagRECT@@IPEBUtagPOINT@@@Z; CDirtyRegion::AddRects(tagRECT const *,uint,tagPOINT const *)
0x14001339a  mov     rcx, [rbx+498h]
0x1400133a1  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400133a8  nop     dword ptr [rax+rax+00h]
0x1400133ad  add     rsp, 50h
0x1400133b1  pop     r14
0x1400133b3  pop     rdi
0x1400133b4  pop     rsi
0x1400133b5  pop     rbp
0x1400133b6  pop     rbx
0x1400133b7  retn
0x1400133b9  mov     ecx, 3
0x1400133be  int     29h; Win8: RtlFailFast(ecx)
```
