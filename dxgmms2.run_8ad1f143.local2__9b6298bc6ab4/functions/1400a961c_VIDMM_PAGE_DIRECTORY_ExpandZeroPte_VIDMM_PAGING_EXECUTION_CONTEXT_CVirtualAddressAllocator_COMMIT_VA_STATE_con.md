# VIDMM_PAGE_DIRECTORY::ExpandZeroPte(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,uint,uint,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,VIDMM_ALLOC * *)

- ea: `0x1400a961c`
- end: `0x1400a98f9`
- name: `?ExpandZeroPte@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@II_K333PEAPEAUVIDMM_ALLOC@@@Z`
- size: `733`
- prototype: `__int64 __usercall@<rax>(VIDMM_PAGE_DIRECTORY *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct CVirtualAddressAllocator *@<r8>, const struct COMMIT_VA_STATE *@<r9>, unsigned int, unsigned int, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64, struct VIDMM_ALLOC **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14009634c`

## callees

- `0x1400045ec`
- `0x140058680`
- `0x140058ac0`
- `0x14009634c`
- `0x1400974b8`
- `0x1400a961c`
- `0x140103b34`
- `0x140105174`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400a96af`
- `watchdog!WdLogSingleEntry0` at `0x1400a979a`
- `watchdog!WdLogSingleEntry0` at `0x1400a97e9`
- `watchdog!WdLogSingleEntry0` at `0x1400a986e`
- `watchdog!WdLogSingleEntry0` at `0x1400a989d`
- `watchdog!WdLogSingleEntry0` at `0x1400a96af`
- `watchdog!WdLogSingleEntry0` at `0x1400a979a`
- `watchdog!WdLogSingleEntry0` at `0x1400a97e9`
- `watchdog!WdLogSingleEntry0` at `0x1400a986e`
- `watchdog!WdLogSingleEntry0` at `0x1400a989d`

## string_xrefs

- `0x1400a96bd`: `Failed to create page table or page directory`

## pseudocode

```c
__int64 __fastcall VIDMM_PAGE_DIRECTORY::ExpandZeroPte(
        VIDMM_PAGE_DIRECTORY *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct CVirtualAddressAllocator *a3,
        const struct COMMIT_VA_STATE *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        unsigned __int64 a10,
        struct VIDMM_ALLOC **a11)
{
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rsi
  int v18; // r8d
  VIDMM_PAGE_DIRECTORY *v20; // r10
  VIDMM_PAGE_TABLE *v21; // r13
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rcx
  int v24; // r14d
  unsigned __int64 v25; // [rsp+28h] [rbp-A9h]
  unsigned __int64 v26; // [rsp+30h] [rbp-A1h]
  VIDMM_PAGE_DIRECTORY *v27; // [rsp+50h] [rbp-81h]
  _QWORD v28[12]; // [rsp+60h] [rbp-71h] BYREF

  v15 = *((_QWORD *)this + 7);
  v16 = a5;
  if ( (*(_BYTE *)(*((_QWORD *)this + 6) + 16LL * a5) & 2) == 0 )
    v16 = a6;
  v17 = (unsigned int)v16;
  if ( !*(_QWORD *)(v15 + 8 * v16) )
  {
    *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * (unsigned int)v16) = CreatePageTable(a3);
    v15 = *((_QWORD *)this + 7);
    if ( !*(_QWORD *)(v15 + 8 * v17) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 8316;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        v18,
        (unsigned int)L"Failed to create page table or page directory",
        8316,
        0,
        0,
        0);
      return 3221225495LL;
    }
  }
  memset(v28, 0, sizeof(v28));
  BYTE6(v28[9]) = *((_BYTE *)a4 + 78);
  BYTE4(v28[9]) = *((_BYTE *)a4 + 76);
  v28[0] = 3;
  LODWORD(v28[7]) = 6;
  LODWORD(v28[9]) = -2;
  v20 = *(VIDMM_PAGE_DIRECTORY **)(v15 + 8LL * a5);
  v21 = *(VIDMM_PAGE_TABLE **)(v15 + 8 * v17);
  v27 = v20;
  if ( a9 < a7 )
  {
    v22 = a7 - a9;
    v23 = a9 << 12;
    if ( (*(_DWORD *)this & 0x20) != 0 )
    {
      v24 = VIDMM_PAGE_TABLE::CommitVirtualAddressRange(
              v21,
              a2,
              a3,
              (const struct COMMIT_VA_STATE *)v28,
              0,
              v23,
              v22,
              0,
              0,
              a11);
      if ( v24 < 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 8349;
        return (unsigned int)v24;
      }
    }
    else
    {
      v24 = VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(
              v20,
              a2,
              a3,
              (const struct COMMIT_VA_STATE *)v28,
              0,
              v23,
              v22,
              0,
              0,
              a11);
      if ( v24 < 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 8367;
        return (unsigned int)v24;
      }
    }
    v20 = v27;
  }
  if ( a8 < a10 )
  {
    v26 = a10 - a8;
    v25 = a8 << 12;
    if ( (*(_DWORD *)this & 0x20) != 0 )
    {
      v24 = VIDMM_PAGE_TABLE::CommitVirtualAddressRange(
              v21,
              a2,
              a3,
              (const struct COMMIT_VA_STATE *)v28,
              0,
              v25,
              v26,
              0,
              0,
              a11);
      if ( v24 < 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 8390;
        return (unsigned int)v24;
      }
    }
    else
    {
      v24 = VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(
              v20,
              a2,
              a3,
              (const struct COMMIT_VA_STATE *)v28,
              0,
              v25,
              v26,
              0,
              0,
              a11);
      if ( v24 < 0 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 8409;
        return (unsigned int)v24;
      }
    }
  }
  *(_QWORD *)(16 * v17 + *((_QWORD *)this + 6)) &= ~2uLL;
  VIDMM_PAGE_DIRECTORY::SetPageTableInPde(this, a3, v17);
  return 0;
}

```

## disassembly

```asm
0x1400a961c  push    rbp
0x1400a961e  push    rbx
0x1400a961f  push    rsi
0x1400a9620  push    rdi
0x1400a9621  push    r12
0x1400a9623  push    r13
0x1400a9625  push    r14
0x1400a9627  push    r15
0x1400a9629  lea     rbp, [rsp-7]
0x1400a962e  sub     rsp, 0D8h
0x1400a9635  mov     rax, cs:__security_cookie
0x1400a963c  xor     rax, rsp
0x1400a963f  mov     [rbp+3Fh+var_50], rax
0x1400a9643  mov     r12, [rbp+3Fh+arg_50]
0x1400a964a  mov     rbx, rcx
0x1400a964d  mov     r15, rdx
0x1400a9650  mov     r13, r9
0x1400a9653  mov     edx, [rbp+3Fh+arg_20]
0x1400a9656  mov     rdi, r8
0x1400a9659  mov     ecx, edx
0x1400a965b  mov     [rsp+110h+var_C0], rdx
0x1400a9660  mov     rax, [rbx+30h]
0x1400a9664  add     rcx, rcx
0x1400a9667  mov     r14, [rbx+38h]
0x1400a966b  test    byte ptr [rax+rcx*8], 2
0x1400a966f  mov     eax, edx
0x1400a9671  cmovz   eax, [rbp+3Fh+arg_28]
0x1400a9675  mov     esi, eax
0x1400a9677  cmp     qword ptr [r14+rax*8], 0
0x1400a967c  jnz     short loc_1400A96F7
0x1400a967e  cmp     esi, edx
0x1400a9680  mov     rcx, rdi; struct CVirtualAddressAllocator *
0x1400a9683  mov     edx, [rbx]
0x1400a9685  setnbe  r8b
0x1400a9689  shr     edx, 8
0x1400a968c  and     edx, 1Fh
0x1400a968f  xor     r9d, r9d
0x1400a9692  call    CreatePageTable
0x1400a9697  mov     rcx, [rbx+38h]
0x1400a969b  mov     [rcx+rsi*8], rax
0x1400a969f  mov     r14, [rbx+38h]
0x1400a96a3  cmp     qword ptr [r14+rsi*8], 0
0x1400a96a8  jnz     short loc_1400A96F7
0x1400a96aa  mov     ecx, 1
0x1400a96af  call    cs:__imp_WdLogSingleEntry0
0x1400a96b6  nop     dword ptr [rax+rax+00h]
0x1400a96bb  xor     ecx, ecx
0x1400a96bd  lea     r9, aFailedToCreate_17; "Failed to create page table or page dir"...
0x1400a96c4  mov     qword ptr [rsp+110h+var_D8], rcx
0x1400a96c9  mov     eax, 207Ch
0x1400a96ce  mov     [rsp+110h+var_E0], rcx
0x1400a96d3  mov     edx, 40000h
0x1400a96d8  mov     [rsp+110h+var_E8], rcx
0x1400a96dd  mov     [rsp+110h+var_F0], rax
0x1400a96e2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400a96e8  call    DxgkLogInternalTriageEvent
0x1400a96ed  mov     eax, 0C0000017h
0x1400a96f2  jmp     loc_1400A98D8
0x1400a96f7  xor     edx, edx; Val
0x1400a96f9  lea     rcx, [rbp+3Fh+var_B0]; void *
0x1400a96fd  lea     r8d, [rdx+60h]; Size
0x1400a9701  call    memset
0x1400a9706  mov     al, [r13+4Eh]
0x1400a970a  mov     r10, [rsp+110h+var_C0]
0x1400a970f  mov     rcx, [rbp+3Fh+arg_40]
0x1400a9716  mov     rdx, [rbp+3Fh+arg_30]
0x1400a971a  mov     [rbp+3Fh+var_62], al
0x1400a971d  mov     al, [r13+4Ch]
0x1400a9721  mov     [rbp+3Fh+var_64], al
0x1400a9724  mov     [rbp+3Fh+var_B0], 3
0x1400a972c  mov     [rbp+3Fh+var_78], 6
0x1400a9733  mov     [rbp+3Fh+var_68], 0FFFFFFFEh
0x1400a973a  mov     r10, [r14+r10*8]
0x1400a973e  mov     r13, [r14+rsi*8]
0x1400a9742  mov     [rsp+110h+var_C0], r10
0x1400a9747  cmp     rcx, rdx
0x1400a974a  jnb     loc_1400A9806
0x1400a9750  mov     eax, [rbx]
0x1400a9752  lea     r9, [rbp+3Fh+var_B0]; struct COMMIT_VA_STATE *
0x1400a9756  sub     rdx, rcx
0x1400a9759  mov     [rsp+110h+var_C8], r12; struct VIDMM_ALLOC **
0x1400a975e  shl     rcx, 0Ch
0x1400a9762  mov     r8, rdi; struct CVirtualAddressAllocator *
0x1400a9765  test    al, 20h
0x1400a9767  jz      short loc_1400A97B8
0x1400a9769  xor     eax, eax
0x1400a976b  mov     [rsp+110h+var_D0], al; bool
0x1400a976f  mov     qword ptr [rsp+110h+var_D8], rax; unsigned __int64
0x1400a9774  mov     [rsp+110h+var_E0], rdx; unsigned __int64
0x1400a9779  mov     rdx, r15; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a977c  mov     [rsp+110h+var_E8], rcx; unsigned __int64
0x1400a9781  mov     rcx, r13; this
0x1400a9784  mov     [rsp+110h+var_F0], rax; unsigned __int64
0x1400a9789  call    ?CommitVirtualAddressRange@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400a978e  mov     r14d, eax
0x1400a9791  test    eax, eax
0x1400a9793  jns     short loc_1400A9801
0x1400a9795  mov     ecx, 3
0x1400a979a  call    cs:__imp_WdLogSingleEntry0
0x1400a97a1  nop     dword ptr [rax+rax+00h]
0x1400a97a6  mov     cs:WdLogGlobalForLineNumber, 209Dh
0x1400a97b0  mov     eax, r14d
0x1400a97b3  jmp     loc_1400A98D8
0x1400a97b8  xor     eax, eax
0x1400a97ba  mov     [rsp+110h+var_D0], al; bool
0x1400a97be  mov     qword ptr [rsp+110h+var_D8], rax; unsigned int
0x1400a97c3  mov     [rsp+110h+var_E0], rdx; unsigned __int64
0x1400a97c8  mov     rdx, r15; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a97cb  mov     [rsp+110h+var_E8], rcx; unsigned __int64
0x1400a97d0  mov     rcx, r10; this
0x1400a97d3  mov     [rsp+110h+var_F0], rax; unsigned __int64
0x1400a97d8  call    ?CommitVirtualAddressRange@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400a97dd  mov     r14d, eax
0x1400a97e0  test    eax, eax
0x1400a97e2  jns     short loc_1400A9801
0x1400a97e4  mov     ecx, 3
0x1400a97e9  call    cs:__imp_WdLogSingleEntry0
0x1400a97f0  nop     dword ptr [rax+rax+00h]
0x1400a97f5  mov     cs:WdLogGlobalForLineNumber, 20AFh
0x1400a97ff  jmp     short loc_1400A97B0
0x1400a9801  mov     r10, [rsp+110h+var_C0]
0x1400a9806  mov     rcx, [rbp+3Fh+arg_38]
0x1400a980d  mov     r8, [rbp+3Fh+arg_48]
0x1400a9814  cmp     rcx, r8
0x1400a9817  jnb     loc_1400A98B8
0x1400a981d  mov     eax, [rbx]
0x1400a981f  lea     r9, [rbp+3Fh+var_B0]; struct COMMIT_VA_STATE *
0x1400a9823  mov     [rsp+110h+var_C8], r12; struct VIDMM_ALLOC **
0x1400a9828  sub     r8, rcx
0x1400a982b  mov     [rsp+110h+var_D0], 0; bool
0x1400a9830  mov     rdx, r15; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a9833  mov     qword ptr [rsp+110h+var_D8], 0; unsigned int
0x1400a983c  mov     [rsp+110h+var_E0], r8; unsigned __int64
0x1400a9841  mov     r8, rdi; struct CVirtualAddressAllocator *
0x1400a9844  shl     rcx, 0Ch
0x1400a9848  mov     [rsp+110h+var_E8], rcx; unsigned __int64
0x1400a984d  mov     [rsp+110h+var_F0], 0; unsigned __int64
0x1400a9856  test    al, 20h
0x1400a9858  jz      short loc_1400A9889
0x1400a985a  mov     rcx, r13; this
0x1400a985d  call    ?CommitVirtualAddressRange@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400a9862  mov     r14d, eax
0x1400a9865  test    eax, eax
0x1400a9867  jns     short loc_1400A98B8
0x1400a9869  mov     ecx, 3
0x1400a986e  call    cs:__imp_WdLogSingleEntry0
0x1400a9875  nop     dword ptr [rax+rax+00h]
0x1400a987a  mov     cs:WdLogGlobalForLineNumber, 20C6h
0x1400a9884  jmp     loc_1400A97B0
0x1400a9889  mov     rcx, r10; this
0x1400a988c  call    ?CommitVirtualAddressRange@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400a9891  mov     r14d, eax
0x1400a9894  test    eax, eax
0x1400a9896  jns     short loc_1400A98B8
0x1400a9898  mov     ecx, 3
0x1400a989d  call    cs:__imp_WdLogSingleEntry0
0x1400a98a4  nop     dword ptr [rax+rax+00h]
0x1400a98a9  mov     cs:WdLogGlobalForLineNumber, 20D9h
0x1400a98b3  jmp     loc_1400A97B0
0x1400a98b8  mov     rax, [rbx+30h]
0x1400a98bc  mov     r9, rsi
0x1400a98bf  shl     r9, 4
0x1400a98c3  mov     r8d, esi; unsigned int
0x1400a98c6  mov     rdx, rdi; struct CVirtualAddressAllocator *
0x1400a98c9  mov     rcx, rbx; this
0x1400a98cc  and     qword ptr [r9+rax], 0FFFFFFFFFFFFFFFDh
0x1400a98d1  call    ?SetPageTableInPde@VIDMM_PAGE_DIRECTORY@@QEAAXPEAVCVirtualAddressAllocator@@I@Z; VIDMM_PAGE_DIRECTORY::SetPageTableInPde(CVirtualAddressAllocator *,uint)
0x1400a98d6  xor     eax, eax
0x1400a98d8  mov     rcx, [rbp+3Fh+var_50]
0x1400a98dc  xor     rcx, rsp; StackCookie
0x1400a98df  call    __security_check_cookie
0x1400a98e4  add     rsp, 0D8h
0x1400a98eb  pop     r15
0x1400a98ed  pop     r14
0x1400a98ef  pop     r13
0x1400a98f1  pop     r12
0x1400a98f3  pop     rdi
0x1400a98f4  pop     rsi
0x1400a98f5  pop     rbx
0x1400a98f6  pop     rbp
0x1400a98f7  retn
```
