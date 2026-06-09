# VIDMM_PROCESS_HEAP::FreeSmallAllocation(_VIDMM_PROCESS_HEAP_ALLOC *)

- ea: `0x1400dadac`
- end: `0x1400db028`
- name: `?FreeSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_ALLOC@@@Z`
- size: `636`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *this, char *Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400b2970`

## callees

- `0x140012ed4`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002f7d0`
- `0x140059030`
- `0x1400dabec`
- `0x1400dadac`
- `0x140107cfc`

## import_xrefs

- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400dae71`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400dae71`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400db001`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400db001`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dadd1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dafd2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dadd1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dafd2`
- `watchdog!WdLogSingleEntry5` at `0x1400dae41`
- `watchdog!WdLogSingleEntry5` at `0x1400dae41`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400dae1c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dadbd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dafc6`

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
  int v21; // [rsp+28h] [rbp-60h]
  __int64 v22; // [rsp+98h] [rbp+10h] BYREF

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
    v7 = WdLogSingleEntry5(0, 270, 21, this, v2, 0);
    WdLogGlobalForLineNumber = 227;
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
  v22 = v14;
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
    LOBYTE(v21) = 1;
    (*(void (__fastcall **)(VIDMM_PROCESS_HEAP *, char *, __int64, _QWORD, int, int))(*(_QWORD *)this + 32LL))(
      this,
      v2,
      v14,
      *(_QWORD *)v9,
      4,
      v21);
    goto LABEL_17;
  }
  v12 = v2 + 56;
  VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
  (*((void (__fastcall **)(__int64, __int64 *, char *, __int64))VirtualMemoryInterface + 2))(-1, &v22, v2 + 56, 0x4000);
LABEL_16:
  v16 = v11;
LABEL_17:
  VIDMM_LINEAR_POOL::Free(*((VIDMM_LINEAR_POOL **)*v11 + 9), *((struct _VIDMM_POOL_BLOCK **)v2 + 3));
  *(_QWORD *)(*((_QWORD *)this + 1) + 184LL) -= *(_QWORD *)v12;
  v18 = (_QWORD *)*((_QWORD *)this + 1);
  v19 = *((unsigned int *)*v11 + 20);
  v20 = *(_QWORD *)v12;
  if ( (_DWORD)v19 == 1 )
  {
    v18[26] -= v20;
  }
  else if ( (_DWORD)v19 == 2 )
  {
    v18[28] -= v20;
  }
  else
  {
    v18[30] -= v20;
  }
  --*(_DWORD *)(*((_QWORD *)v2 + 1) + 24LL);
  if ( (byte_140087201 & 0x10) != 0 )
  {
    McTemplateK0qxxx_EtwWriteTransfer(
      (unsigned int)*v16,
      (unsigned int)&EventDestroyProcessAllocationDetails,
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
0x1400dadac  push    rbx
0x1400dadae  push    rbp
0x1400dadaf  push    rsi
0x1400dadb0  push    rdi
0x1400dadb1  push    r12
0x1400dadb3  push    r13
0x1400dadb5  push    r14
0x1400dadb7  push    r15
0x1400dadb9  sub     rsp, 48h
0x1400dadbd  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400dadc4  xor     esi, esi
0x1400dadc6  mov     rbx, rdx
0x1400dadc9  mov     r14, rcx
0x1400dadcc  cmp     [rax], sil
0x1400dadcf  jz      short loc_1400DAE02
0x1400dadd1  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400dadd8  nop     dword ptr [rax+rax+00h]
0x1400daddd  mov     r8, [rbx+38h]
0x1400dade1  mov     rdx, rbx
0x1400dade4  mov     [rax+18h], r8
0x1400dade8  mov     r8, [rbx+10h]
0x1400dadec  mov     [rax+20h], r8
0x1400dadf0  mov     rcx, [rbx+8]
0x1400dadf4  mov     [rax+28h], rcx
0x1400dadf8  mov     cs:WdLogGlobalForLineNumber, 413h
0x1400dae02  mov     r8d, 38h ; '8'
0x1400dae08  mov     r12, rbx
0x1400dae0b  mov     rcx, rbx
0x1400dae0e  lea     r13d, [r8-28h]
0x1400dae12  lea     eax, [r8-30h]
0x1400dae16  cmp     [rbx+40h], sil
0x1400dae1a  jz      short loc_1400DAE57
0x1400dae1c  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400dae23  mov     dword ptr [rax], 1
0x1400dae29  mov     [rsp+88h+var_60], rsi
0x1400dae2e  lea     r8d, [r13+5]
0x1400dae32  mov     r9, r14
0x1400dae35  mov     [rsp+88h+var_68], rbx
0x1400dae3a  mov     edx, 10Eh
0x1400dae3f  xor     ecx, ecx
0x1400dae41  call    cs:__imp_WdLogSingleEntry5
0x1400dae48  nop     dword ptr [rax+rax+00h]
0x1400dae4d  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400dae57  lea     rdi, [rcx+rax]
0x1400dae5b  lea     rcx, [r14+10h]; this
0x1400dae5f  lea     rbp, [rdx+r8]
0x1400dae63  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400dae68  mov     rcx, [rbx+20h]; SecureHandle
0x1400dae6c  test    rcx, rcx
0x1400dae6f  jz      short loc_1400DAE8B
0x1400dae71  call    cs:__imp_MmUnsecureVirtualMemory
0x1400dae78  nop     dword ptr [rax+rax+00h]
0x1400dae7d  mov     [rbx+20h], rsi
0x1400dae81  lea     r15, [rbx+8]
0x1400dae85  lea     rsi, [rbx+38h]
0x1400dae89  jmp     short loc_1400DAE91
0x1400dae8b  mov     rsi, rbp
0x1400dae8e  mov     r15, rdi
0x1400dae91  mov     rax, [rdi]
0x1400dae94  cmp     dword ptr [rax+18h], 1
0x1400dae98  jz      short loc_1400DAF12
0x1400dae9a  mov     r8, [r12+r13]
0x1400dae9e  add     r8, [rax+20h]
0x1400daea2  mov     [rsp+88h+arg_8], r8
0x1400daeaa  cmp     qword ptr [rax+38h], 0
0x1400daeaf  jnz     short loc_1400DAEE7
0x1400daeb1  cmp     qword ptr [rax+58h], 0
0x1400daeb6  jnz     short loc_1400DAEE1
0x1400daeb8  lea     rsi, [rbx+38h]
0x1400daebc  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400daec1  mov     r9d, 4000h
0x1400daec7  lea     rdx, [rsp+88h+arg_8]
0x1400daecf  mov     r8, rsi
0x1400daed2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400daed6  mov     rax, [rax+10h]
0x1400daeda  call    _guard_dispatch_icall
0x1400daedf  jmp     short loc_1400DAF15
0x1400daee1  lea     rdi, [rbx+8]
0x1400daee5  jmp     short loc_1400DAEED
0x1400daee7  mov     rdi, r15
0x1400daeea  mov     rsi, rbp
0x1400daeed  mov     rax, [r14]
0x1400daef0  mov     rdx, rbx
0x1400daef3  mov     r9, [rbp+0]
0x1400daef7  mov     rcx, r14
0x1400daefa  mov     byte ptr [rsp+88h+var_60], 1
0x1400daeff  mov     dword ptr [rsp+88h+var_68], 4
0x1400daf07  mov     rax, [rax+20h]
0x1400daf0b  call    _guard_dispatch_icall
0x1400daf10  jmp     short loc_1400DAF18
0x1400daf12  mov     rsi, rbp
0x1400daf15  mov     rdi, r15
0x1400daf18  mov     rcx, [r15]
0x1400daf1b  mov     rdx, [rbx+18h]; struct _VIDMM_POOL_BLOCK *
0x1400daf1f  mov     rcx, [rcx+48h]; this
0x1400daf23  call    ?Free@VIDMM_LINEAR_POOL@@QEAAXPEAX@Z; VIDMM_LINEAR_POOL::Free(void *)
0x1400daf28  mov     rcx, [r14+8]
0x1400daf2c  mov     rax, [rsi]
0x1400daf2f  sub     [rcx+0B8h], rax
0x1400daf36  mov     rax, [r15]
0x1400daf39  mov     rcx, [r14+8]
0x1400daf3d  mov     edx, [rax+50h]
0x1400daf40  mov     rax, [rsi]
0x1400daf43  cmp     edx, 1
0x1400daf46  jnz     short loc_1400DAF51
0x1400daf48  sub     [rcx+0D0h], rax
0x1400daf4f  jmp     short loc_1400DAF66
0x1400daf51  cmp     edx, 2
0x1400daf54  jnz     short loc_1400DAF5F
0x1400daf56  sub     [rcx+0E0h], rax
0x1400daf5d  jmp     short loc_1400DAF66
0x1400daf5f  sub     [rcx+0F0h], rax
0x1400daf66  mov     rax, [rbx+8]
0x1400daf6a  dec     dword ptr [rax+18h]
0x1400daf6d  test    cs:byte_140087201, 10h
0x1400daf74  jz      short loc_1400DAFBD
0x1400daf76  mov     rcx, [rdi]
0x1400daf79  lea     rdx, EventDestroyProcessAllocationDetails
0x1400daf80  mov     r9, [r14+8]
0x1400daf84  mov     eax, [rcx+50h]
0x1400daf87  mov     r9d, [r9+18h]
0x1400daf8b  sub     eax, 3
0x1400daf8e  cmp     eax, 3
0x1400daf91  setbe   al
0x1400daf94  neg     al
0x1400daf96  sbb     rax, rax
0x1400daf99  and     eax, 38h
0x1400daf9c  mov     rax, [rax+rcx+20h]
0x1400dafa1  mov     [rsp+88h+var_58], rax
0x1400dafa6  mov     rax, [rbx+38h]
0x1400dafaa  mov     [rsp+88h+var_60], rax
0x1400dafaf  mov     [rsp+88h+var_68], rbx
0x1400dafb4  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400dafb9  lea     rdi, [rbx+8]
0x1400dafbd  mov     rax, [rdi]
0x1400dafc0  cmp     dword ptr [rax+18h], 0
0x1400dafc4  jnz     short loc_1400DAFFA
0x1400dafc6  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400dafcd  cmp     byte ptr [rax], 0
0x1400dafd0  jz      short loc_1400DAFEF
0x1400dafd2  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400dafd9  nop     dword ptr [rax+rax+00h]
0x1400dafde  mov     r8, [rdi]
0x1400dafe1  mov     [rax+18h], r8
0x1400dafe5  mov     cs:WdLogGlobalForLineNumber, 484h
0x1400dafef  mov     rdx, [rdi]; struct _VIDMM_PROCESS_HEAP_BLOCK *
0x1400daff2  mov     rcx, r14; this
0x1400daff5  call    ?FreeBlock@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_BLOCK@@@Z; VIDMM_PROCESS_HEAP::FreeBlock(_VIDMM_PROCESS_HEAP_BLOCK *)
0x1400daffa  lea     rcx, [r14+40h]; Lookaside
0x1400daffe  mov     rdx, rbx; Entry
0x1400db001  call    cs:__imp_ExFreeToPagedLookasideList
0x1400db008  nop     dword ptr [rax+rax+00h]
0x1400db00d  lea     rcx, [r14+10h]; this
0x1400db011  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400db016  add     rsp, 48h
0x1400db01a  pop     r15
0x1400db01c  pop     r14
0x1400db01e  pop     r13
0x1400db020  pop     r12
0x1400db022  pop     rdi
0x1400db023  pop     rsi
0x1400db024  pop     rbp
0x1400db025  pop     rbx
0x1400db026  retn
```
