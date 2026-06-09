# VIDMM_PROCESS_HEAP::FreeSmallAllocation(_VIDMM_PROCESS_HEAP_ALLOC *)

- ea: `0x1400d2abc`
- end: `0x1400d2d38`
- name: `?FreeSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_ALLOC@@@Z`
- size: `636`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *__hidden this, PVOID Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400b1420`

## callees

- `0x140013434`
- `0x14002fbac`
- `0x14002fd94`
- `0x140031934`
- `0x140058760`
- `0x1400d28fc`
- `0x1400d2abc`
- `0x1400fd688`

## import_xrefs

- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400d2b81`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400d2b81`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400d2d11`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400d2d11`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d2ae1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d2ce2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d2ae1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d2ce2`
- `watchdog!WdLogSingleEntry5` at `0x1400d2b51`
- `watchdog!WdLogSingleEntry5` at `0x1400d2b51`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400d2b2c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400d2acd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400d2cd6`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_PROCESS_HEAP::FreeSmallAllocation(VIDMM_PROCESS_HEAP *this, char *Entry)
{
  char *v2; // rbx
  _QWORD *v4; // rax
  __int64 v5; // r8
  char *v6; // rcx
  __int64 v7; // rax
  struct _VIDMM_PROCESS_HEAP_BLOCK **v8; // rdi
  char *v9; // rbp
  void *v10; // rcx
  struct _VIDMM_PROCESS_HEAP_BLOCK **v11; // r15
  char *v12; // rsi
  struct _VIDMM_PROCESS_HEAP_BLOCK *v13; // rax
  __int64 v14; // r8
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  struct _VIDMM_PROCESS_HEAP_BLOCK **v16; // rdi
  int v17; // r8d
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  char *v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+28h] [rbp-60h]
  __int64 v23; // [rsp+98h] [rbp+10h] BYREF

  v2 = Entry;
  if ( g_IsInternalReleaseOrDbg )
  {
    v4 = (_QWORD *)WdLogNewEntry5_WdTrace(this, Entry);
    Entry = v2;
    v4[3] = *((_QWORD *)v2 + 7);
    v4[4] = *((_QWORD *)v2 + 2);
    v4[5] = *((_QWORD *)v2 + 1);
    WdLogGlobalForLineNumber = 1043;
  }
  v5 = 56;
  v6 = v2;
  v7 = 8;
  if ( v2[64] )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    v22 = 0;
    v21 = v2;
    v7 = WdLogSingleEntry5(0, 270, 21);
    WdLogGlobalForLineNumber = 222;
  }
  v8 = (struct _VIDMM_PROCESS_HEAP_BLOCK **)&v6[v7];
  v9 = &Entry[v5];
  DXGFASTMUTEX::Acquire((VIDMM_PROCESS_HEAP *)((char *)this + 16));
  v10 = (void *)*((_QWORD *)v2 + 4);
  if ( v10 )
  {
    MmUnsecureVirtualMemory(v10);
    *((_QWORD *)v2 + 4) = 0;
    v11 = (struct _VIDMM_PROCESS_HEAP_BLOCK **)(v2 + 8);
    v12 = v2 + 56;
  }
  else
  {
    v12 = v9;
    v11 = v8;
  }
  v13 = *v8;
  if ( *((_DWORD *)*v8 + 6) == 1 )
  {
    v12 = v9;
    goto LABEL_16;
  }
  v14 = *((_QWORD *)v13 + 4) + *((_QWORD *)v2 + 2);
  v23 = v14;
  if ( *((_QWORD *)v13 + 7) )
  {
    v16 = v11;
    v12 = v9;
    goto LABEL_14;
  }
  if ( *((_QWORD *)v13 + 11) )
  {
    v16 = (struct _VIDMM_PROCESS_HEAP_BLOCK **)(v2 + 8);
LABEL_14:
    LOBYTE(v22) = 1;
    LODWORD(v21) = 4;
    (*(void (__fastcall **)(VIDMM_PROCESS_HEAP *, char *, __int64, _QWORD, char *, __int64))(*(_QWORD *)this + 32LL))(
      this,
      v2,
      v14,
      *(_QWORD *)v9,
      v21,
      v22);
    goto LABEL_17;
  }
  v12 = v2 + 56;
  VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
  (*((void (__fastcall **)(__int64, __int64 *, char *, __int64, char *, __int64))VirtualMemoryInterface + 2))(
    -1,
    &v23,
    v2 + 56,
    0x4000,
    v21,
    v22);
LABEL_16:
  v16 = v11;
LABEL_17:
  VIDMM_LINEAR_POOL::Free(*((VIDMM_LINEAR_POOL **)*v11 + 9), *((struct _VIDMM_POOL_BLOCK **)v2 + 3));
  *(_QWORD *)(*((_QWORD *)this + 1) + 176LL) -= *(_QWORD *)v12;
  v18 = (_QWORD *)*((_QWORD *)this + 1);
  v19 = *((unsigned int *)*v11 + 20);
  v20 = *(_QWORD *)v12;
  if ( (_DWORD)v19 == 1 )
  {
    v18[25] -= v20;
  }
  else if ( (_DWORD)v19 == 2 )
  {
    v18[27] -= v20;
  }
  else
  {
    v18[29] -= v20;
  }
  --*(_DWORD *)(*((_QWORD *)v2 + 1) + 24LL);
  if ( (byte_140086201 & 0x10) != 0 )
  {
    McTemplateK0qxxx_EtwWriteTransfer(
      (unsigned int)*v16,
      (unsigned int)EventDestroyProcessAllocationDetails,
      v17,
      *(_DWORD *)(*((_QWORD *)this + 1) + 24LL),
      (char)v2,
      *((_QWORD *)v2 + 7),
      *(_QWORD *)((char *)*v16 + ((unsigned int)(*((_DWORD *)*v16 + 20) - 3) <= 3 ? 0x38 : 0) + 32));
    v16 = (struct _VIDMM_PROCESS_HEAP_BLOCK **)(v2 + 8);
  }
  if ( !*((_DWORD *)*v16 + 6) )
  {
    if ( g_IsInternalReleaseOrDbg )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace(v18, v19) + 24) = *v16;
      WdLogGlobalForLineNumber = 1156;
    }
    VIDMM_PROCESS_HEAP::FreeBlock(this, *v16);
  }
  ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 64), v2);
  DXGFASTMUTEX::Release((VIDMM_PROCESS_HEAP *)((char *)this + 16));
}

```

## disassembly

```asm
0x1400d2abc  push    rbx
0x1400d2abe  push    rbp
0x1400d2abf  push    rsi
0x1400d2ac0  push    rdi
0x1400d2ac1  push    r12
0x1400d2ac3  push    r13
0x1400d2ac5  push    r14
0x1400d2ac7  push    r15
0x1400d2ac9  sub     rsp, 48h
0x1400d2acd  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400d2ad4  xor     esi, esi
0x1400d2ad6  mov     rbx, rdx
0x1400d2ad9  mov     r14, rcx
0x1400d2adc  cmp     [rax], sil
0x1400d2adf  jz      short loc_1400D2B12
0x1400d2ae1  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400d2ae8  nop     dword ptr [rax+rax+00h]
0x1400d2aed  mov     r8, [rbx+38h]
0x1400d2af1  mov     rdx, rbx
0x1400d2af4  mov     [rax+18h], r8
0x1400d2af8  mov     r8, [rbx+10h]
0x1400d2afc  mov     [rax+20h], r8
0x1400d2b00  mov     rcx, [rbx+8]
0x1400d2b04  mov     [rax+28h], rcx
0x1400d2b08  mov     cs:WdLogGlobalForLineNumber, 413h
0x1400d2b12  mov     r8d, 38h ; '8'
0x1400d2b18  mov     r12, rbx
0x1400d2b1b  mov     rcx, rbx
0x1400d2b1e  lea     r13d, [r8-28h]
0x1400d2b22  lea     eax, [r8-30h]
0x1400d2b26  cmp     [rbx+40h], sil
0x1400d2b2a  jz      short loc_1400D2B67
0x1400d2b2c  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400d2b33  mov     dword ptr [rax], 1
0x1400d2b39  mov     [rsp+88h+var_60], rsi
0x1400d2b3e  lea     r8d, [r13+5]
0x1400d2b42  mov     r9, r14
0x1400d2b45  mov     [rsp+88h+var_68], rbx
0x1400d2b4a  mov     edx, 10Eh
0x1400d2b4f  xor     ecx, ecx
0x1400d2b51  call    cs:__imp_WdLogSingleEntry5
0x1400d2b58  nop     dword ptr [rax+rax+00h]
0x1400d2b5d  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400d2b67  lea     rdi, [rcx+rax]
0x1400d2b6b  lea     rcx, [r14+10h]; this
0x1400d2b6f  lea     rbp, [rdx+r8]
0x1400d2b73  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400d2b78  mov     rcx, [rbx+20h]; SecureHandle
0x1400d2b7c  test    rcx, rcx
0x1400d2b7f  jz      short loc_1400D2B9B
0x1400d2b81  call    cs:__imp_MmUnsecureVirtualMemory
0x1400d2b88  nop     dword ptr [rax+rax+00h]
0x1400d2b8d  mov     [rbx+20h], rsi
0x1400d2b91  lea     r15, [rbx+8]
0x1400d2b95  lea     rsi, [rbx+38h]
0x1400d2b99  jmp     short loc_1400D2BA1
0x1400d2b9b  mov     rsi, rbp
0x1400d2b9e  mov     r15, rdi
0x1400d2ba1  mov     rax, [rdi]
0x1400d2ba4  cmp     dword ptr [rax+18h], 1
0x1400d2ba8  jz      short loc_1400D2C22
0x1400d2baa  mov     r8, [r12+r13]
0x1400d2bae  add     r8, [rax+20h]
0x1400d2bb2  mov     [rsp+88h+arg_8], r8
0x1400d2bba  cmp     qword ptr [rax+38h], 0
0x1400d2bbf  jnz     short loc_1400D2BF7
0x1400d2bc1  cmp     qword ptr [rax+58h], 0
0x1400d2bc6  jnz     short loc_1400D2BF1
0x1400d2bc8  lea     rsi, [rbx+38h]
0x1400d2bcc  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400d2bd1  mov     r9d, 4000h
0x1400d2bd7  lea     rdx, [rsp+88h+arg_8]
0x1400d2bdf  mov     r8, rsi
0x1400d2be2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400d2be6  mov     rax, [rax+10h]
0x1400d2bea  call    _guard_dispatch_icall
0x1400d2bef  jmp     short loc_1400D2C25
0x1400d2bf1  lea     rdi, [rbx+8]
0x1400d2bf5  jmp     short loc_1400D2BFD
0x1400d2bf7  mov     rdi, r15
0x1400d2bfa  mov     rsi, rbp
0x1400d2bfd  mov     rax, [r14]
0x1400d2c00  mov     rdx, rbx
0x1400d2c03  mov     r9, [rbp+0]
0x1400d2c07  mov     rcx, r14
0x1400d2c0a  mov     byte ptr [rsp+88h+var_60], 1
0x1400d2c0f  mov     dword ptr [rsp+88h+var_68], 4
0x1400d2c17  mov     rax, [rax+20h]
0x1400d2c1b  call    _guard_dispatch_icall
0x1400d2c20  jmp     short loc_1400D2C28
0x1400d2c22  mov     rsi, rbp
0x1400d2c25  mov     rdi, r15
0x1400d2c28  mov     rcx, [r15]
0x1400d2c2b  mov     rdx, [rbx+18h]; struct _VIDMM_POOL_BLOCK *
0x1400d2c2f  mov     rcx, [rcx+48h]; this
0x1400d2c33  call    ?Free@VIDMM_LINEAR_POOL@@QEAAXPEAX@Z; VIDMM_LINEAR_POOL::Free(void *)
0x1400d2c38  mov     rcx, [r14+8]
0x1400d2c3c  mov     rax, [rsi]
0x1400d2c3f  sub     [rcx+0B0h], rax
0x1400d2c46  mov     rax, [r15]
0x1400d2c49  mov     rcx, [r14+8]
0x1400d2c4d  mov     edx, [rax+50h]
0x1400d2c50  mov     rax, [rsi]
0x1400d2c53  cmp     edx, 1
0x1400d2c56  jnz     short loc_1400D2C61
0x1400d2c58  sub     [rcx+0C8h], rax
0x1400d2c5f  jmp     short loc_1400D2C76
0x1400d2c61  cmp     edx, 2
0x1400d2c64  jnz     short loc_1400D2C6F
0x1400d2c66  sub     [rcx+0D8h], rax
0x1400d2c6d  jmp     short loc_1400D2C76
0x1400d2c6f  sub     [rcx+0E8h], rax
0x1400d2c76  mov     rax, [rbx+8]
0x1400d2c7a  dec     dword ptr [rax+18h]
0x1400d2c7d  test    cs:byte_140086201, 10h
0x1400d2c84  jz      short loc_1400D2CCD
0x1400d2c86  mov     rcx, [rdi]
0x1400d2c89  lea     rdx, EventDestroyProcessAllocationDetails
0x1400d2c90  mov     r9, [r14+8]
0x1400d2c94  mov     eax, [rcx+50h]
0x1400d2c97  mov     r9d, [r9+18h]
0x1400d2c9b  sub     eax, 3
0x1400d2c9e  cmp     eax, 3
0x1400d2ca1  setbe   al
0x1400d2ca4  neg     al
0x1400d2ca6  sbb     rax, rax
0x1400d2ca9  and     eax, 38h
0x1400d2cac  mov     rax, [rax+rcx+20h]
0x1400d2cb1  mov     [rsp+88h+var_58], rax
0x1400d2cb6  mov     rax, [rbx+38h]
0x1400d2cba  mov     [rsp+88h+var_60], rax
0x1400d2cbf  mov     [rsp+88h+var_68], rbx
0x1400d2cc4  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400d2cc9  lea     rdi, [rbx+8]
0x1400d2ccd  mov     rax, [rdi]
0x1400d2cd0  cmp     dword ptr [rax+18h], 0
0x1400d2cd4  jnz     short loc_1400D2D0A
0x1400d2cd6  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400d2cdd  cmp     byte ptr [rax], 0
0x1400d2ce0  jz      short loc_1400D2CFF
0x1400d2ce2  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400d2ce9  nop     dword ptr [rax+rax+00h]
0x1400d2cee  mov     r8, [rdi]
0x1400d2cf1  mov     [rax+18h], r8
0x1400d2cf5  mov     cs:WdLogGlobalForLineNumber, 484h
0x1400d2cff  mov     rdx, [rdi]; struct _VIDMM_PROCESS_HEAP_BLOCK *
0x1400d2d02  mov     rcx, r14; this
0x1400d2d05  call    ?FreeBlock@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_BLOCK@@@Z; VIDMM_PROCESS_HEAP::FreeBlock(_VIDMM_PROCESS_HEAP_BLOCK *)
0x1400d2d0a  lea     rcx, [r14+40h]; Lookaside
0x1400d2d0e  mov     rdx, rbx; Entry
0x1400d2d11  call    cs:__imp_ExFreeToPagedLookasideList
0x1400d2d18  nop     dword ptr [rax+rax+00h]
0x1400d2d1d  lea     rcx, [r14+10h]; this
0x1400d2d21  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400d2d26  add     rsp, 48h
0x1400d2d2a  pop     r15
0x1400d2d2c  pop     r14
0x1400d2d2e  pop     r13
0x1400d2d30  pop     r12
0x1400d2d32  pop     rdi
0x1400d2d33  pop     rsi
0x1400d2d34  pop     rbp
0x1400d2d35  pop     rbx
0x1400d2d36  retn
```
