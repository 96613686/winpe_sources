# VIDMM_PAGE_DIRECTORY::ExpandLargePagePteWithFix(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,VIDMM_PAGE_TABLE_LEVEL_DESC const *,COMMIT_VA_STATE const *,unsigned __int64,uint,VIDMM_ALLOC * *)

- ea: `0x1400c6150`
- end: `0x1400c6429`
- name: `?ExpandLargePagePteWithFix@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUVIDMM_PAGE_TABLE_LEVEL_DESC@@PEBUCOMMIT_VA_STATE@@_KIPEAPEAUVIDMM_ALLOC@@@Z`
- size: `729`
- prototype: `__int64 __usercall@<rax>(VIDMM_PAGE_DIRECTORY *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct CVirtualAddressAllocator *@<r8>, const struct VIDMM_PAGE_TABLE_LEVEL_DESC *@<r9>, const struct COMMIT_VA_STATE *, unsigned __int64, unsigned int, struct VIDMM_ALLOC **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c610c`

## callees

- `0x140004268`
- `0x14002eebc`
- `0x140059030`
- `0x140059380`
- `0x14009b008`
- `0x14009c8bc`
- `0x14009d31c`
- `0x1400c6150`
- `0x1400f1dcc`
- `0x14010bdd8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c63d4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c63d4`
- `watchdog!WdLogSingleEntry0` at `0x1400c61d0`
- `watchdog!WdLogSingleEntry0` at `0x1400c6238`
- `watchdog!WdLogSingleEntry0` at `0x1400c61d0`
- `watchdog!WdLogSingleEntry0` at `0x1400c6238`
- `watchdog!WdLogSingleEntry1` at `0x1400c6380`
- `watchdog!WdLogSingleEntry1` at `0x1400c6380`

## string_xrefs

- `0x1400c61e1`: `Failed to create a page table`

## pseudocode

```c
__int64 __fastcall VIDMM_PAGE_DIRECTORY::ExpandLargePagePteWithFix(
        VIDMM_PAGE_DIRECTORY *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct CVirtualAddressAllocator *a3,
        const struct VIDMM_PAGE_TABLE_LEVEL_DESC *a4,
        const struct COMMIT_VA_STATE *a5,
        unsigned __int64 a6,
        unsigned int a7,
        struct VIDMM_ALLOC **a8)
{
  __int64 v8; // rax
  const struct COMMIT_VA_STATE *v10; // r14
  unsigned __int64 v13; // r9
  VIDMM_PAGE_TABLE *PageTable; // r12
  int v15; // ecx
  int v16; // r8d
  int v17; // edi
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v18; // r14
  __int64 v19; // r13
  __int64 *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // r15
  unsigned __int64 v24; // rax
  __int64 v25; // r10
  _QWORD *VidMmGlobalAllocFromOwner; // rax
  unsigned __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // r10d
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // r8d
  _QWORD v34[20]; // [rsp+50h] [rbp-61h] BYREF
  struct VIDMM_ALLOC *v35; // [rsp+100h] [rbp+4Fh] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v36; // [rsp+108h] [rbp+57h]
  __int64 v37; // [rsp+110h] [rbp+5Fh]
  const struct VIDMM_PAGE_TABLE_LEVEL_DESC *v38; // [rsp+118h] [rbp+67h]

  v38 = a4;
  v36 = a2;
  v8 = *((_QWORD *)a3 + 12);
  ++*((_DWORD *)this + 1);
  v10 = a5;
  v35 = 0;
  v37 = v8;
  PageTable = (VIDMM_PAGE_TABLE *)CreatePageTable(a3);
  if ( !PageTable )
  {
    _InterlockedIncrement(&dword_1400877D8);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 7730;
    DxgkLogInternalTriageEvent(v15, 262145, v16, (unsigned int)L"Failed to create a page table", 7730, 0, 0, 0);
    v17 = -1073741801;
    goto LABEL_11;
  }
  v17 = VIDMM_PAGE_TABLE::EnsureResident(PageTable, a2, a3, v13, &v35);
  if ( v17 >= 0 )
  {
    v19 = 8LL * a7;
    v20 = *(__int64 **)(*((_QWORD *)this + 7) + v19);
    if ( v20 )
    {
      memset(v34, 0, 0x60u);
      v21 = *v20;
      v22 = *((_QWORD *)this + 6);
      v23 = 16LL * a7;
      LODWORD(v34[7]) = *((_DWORD *)v20 + 2);
      v34[6] = v21;
      v24 = *(_QWORD *)(v23 + v22);
      v34[0] = v24 & 0xFFFFFFFFFFFFFBFFuLL;
      v25 = (v24 >> 5) & 0x1F;
      v34[2] = v20[2];
      BYTE6(v34[9]) = *((_BYTE *)v10 + 78);
      LOBYTE(v24) = (*(_DWORD *)this & 0x40) != 0;
      LODWORD(v34[9]) = v25;
      BYTE4(v34[9]) = v24;
      BYTE5(v34[9]) = *((_BYTE *)v10 + 77);
      VidMmGlobalAllocFromOwner = (_QWORD *)GetVidMmGlobalAllocFromOwner(LODWORD(v34[7]), v21);
      if ( VidMmGlobalAllocFromOwner )
      {
        v30 = *(_QWORD *)(*(_QWORD *)(v37 + 36480) + 8LL
                                                   * ((*(_DWORD *)(*VidMmGlobalAllocFromOwner + 60LL) >> 2) & 0x3F));
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v30 + 392LL))(
                v30,
                *VidMmGlobalAllocFromOwner,
                v29,
                *(_QWORD *)(v23 + v28 + 8) << 12);
      }
      v18 = v36;
      v31 = VIDMM_PAGE_TABLE::CommitVirtualAddressRange(
              PageTable,
              v36,
              a3,
              (const struct COMMIT_VA_STATE *)v34,
              v27,
              a6,
              *((_QWORD *)v38 + 5),
              *(_QWORD *)(v23 + *((_QWORD *)this + 6) + 8) << 12,
              0,
              &v35);
      v17 = v31;
      if ( v31 < 0 )
      {
        WdLogSingleEntry1(3, v31);
        WdLogGlobalForLineNumber = 7819;
        goto LABEL_10;
      }
      ExFreeToPagedLookasideList(
        (PPAGED_LOOKASIDE_LIST)(*((_QWORD *)a3 + 12) + 36544LL),
        *(PVOID *)(*((_QWORD *)this + 7) + v19));
      *(_QWORD *)(*((_QWORD *)this + 7) + v19) = 0;
      *(_QWORD *)(v23 + *((_QWORD *)this + 6)) &= ~0x400uLL;
    }
    v32 = a7;
    *(_QWORD *)(*((_QWORD *)this + 7) + v19) = PageTable;
    VIDMM_PAGE_DIRECTORY::SetPageTableInPde(this, a3, v32);
    v17 = 0;
    goto LABEL_15;
  }
  WdLogSingleEntry0(3);
  v18 = v36;
  WdLogGlobalForLineNumber = 7753;
LABEL_10:
  VIDMM_PAGE_TABLE::DestroyPageTable(PageTable, v18, a3, a6);
LABEL_11:
  if ( v35 )
    *a8 = (struct VIDMM_ALLOC *)*((_QWORD *)this + 4);
LABEL_15:
  --*((_DWORD *)this + 1);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400c6150  mov     [rsp-8+arg_18], r9
0x1400c6155  mov     [rsp-8+arg_8], rdx
0x1400c615a  push    rbp
0x1400c615b  push    rbx
0x1400c615c  push    rsi
0x1400c615d  push    rdi
0x1400c615e  push    r12
0x1400c6160  push    r13
0x1400c6162  push    r14
0x1400c6164  push    r15
0x1400c6166  lea     rbp, [rsp-7]
0x1400c616b  sub     rsp, 0B8h
0x1400c6172  mov     rax, [r8+60h]
0x1400c6176  mov     rsi, r8
0x1400c6179  inc     dword ptr [rcx+4]
0x1400c617c  xor     r15d, r15d
0x1400c617f  mov     r14, [rbp+3Fh+arg_20]
0x1400c6183  mov     rdi, rdx
0x1400c6186  mov     edx, [rcx]
0x1400c6188  mov     rbx, rcx
0x1400c618b  mov     r8d, edx
0x1400c618e  mov     [rbp+3Fh+arg_0], r15
0x1400c6192  shr     r8d, 6
0x1400c6196  mov     [rbp+3Fh+arg_10], rax
0x1400c619a  test    r8b, 1
0x1400c619e  jz      short loc_1400C61A9
0x1400c61a0  mov     r9b, 1
0x1400c61a3  cmp     [r14+4Eh], r15b
0x1400c61a7  jnz     short loc_1400C61AC
0x1400c61a9  mov     r9b, r15b
0x1400c61ac  shr     edx, 8
0x1400c61af  and     r8b, 1
0x1400c61b3  and     edx, 1Fh
0x1400c61b6  mov     rcx, rsi; struct CVirtualAddressAllocator *
0x1400c61b9  call    CreatePageTable
0x1400c61be  mov     r12, rax
0x1400c61c1  test    rax, rax
0x1400c61c4  jnz     short loc_1400C6216
0x1400c61c6  lock inc cs:dword_1400877D8
0x1400c61cd  lea     ecx, [rax+6]
0x1400c61d0  call    cs:__imp_WdLogSingleEntry0
0x1400c61d7  nop     dword ptr [rax+rax+00h]
0x1400c61dc  mov     [rsp+0F0h+var_B8], r15
0x1400c61e1  lea     r9, aFailedToCreate_28; "Failed to create a page table"
0x1400c61e8  mov     eax, 1E32h
0x1400c61ed  mov     [rsp+0F0h+var_C0], r15
0x1400c61f2  mov     [rsp+0F0h+var_C8], r15
0x1400c61f7  mov     edx, 40001h
0x1400c61fc  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c6202  mov     [rsp+0F0h+var_D0], rax
0x1400c6207  call    DxgkLogInternalTriageEvent
0x1400c620c  mov     edi, 0C0000017h
0x1400c6211  jmp     loc_1400C63AB
0x1400c6216  lea     rax, [rbp+3Fh+arg_0]
0x1400c621a  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c621d  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c6220  mov     [rsp+0F0h+var_D0], rax; struct VIDMM_ALLOC **
0x1400c6225  mov     rcx, r12; this
0x1400c6228  call    ?EnsureResident@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@_KPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::EnsureResident(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,unsigned __int64,VIDMM_ALLOC * *)
0x1400c622d  mov     edi, eax
0x1400c622f  test    eax, eax
0x1400c6231  jns     short loc_1400C6257
0x1400c6233  mov     ecx, 3
0x1400c6238  call    cs:__imp_WdLogSingleEntry0
0x1400c623f  nop     dword ptr [rax+rax+00h]
0x1400c6244  mov     r14, [rbp+3Fh+arg_8]
0x1400c6248  mov     cs:WdLogGlobalForLineNumber, 1E49h
0x1400c6252  jmp     loc_1400C6399
0x1400c6257  mov     r15d, [rbp+3Fh+arg_30]
0x1400c625b  mov     rax, [rbx+38h]
0x1400c625f  lea     r13, ds:0[r15*8]
0x1400c6267  mov     rdi, [rax+r13]
0x1400c626b  test    rdi, rdi
0x1400c626e  jz      loc_1400C63F6
0x1400c6274  xor     edx, edx; Val
0x1400c6276  lea     rcx, [rbp+3Fh+var_A0]; void *
0x1400c627a  lea     r8d, [rdx+60h]; Size
0x1400c627e  call    memset
0x1400c6283  mov     rdx, [rdi]
0x1400c6286  mov     ecx, [rdi+8]
0x1400c6289  mov     r9, [rbx+30h]
0x1400c628d  shl     r15, 4
0x1400c6291  mov     [rbp+3Fh+var_68], ecx
0x1400c6294  mov     [rbp+3Fh+var_70], rdx
0x1400c6298  mov     r8, [r15+r9]
0x1400c629c  mov     rax, r8
0x1400c629f  shr     r8, 5
0x1400c62a3  btr     rax, 0Ah
0x1400c62a8  and     r8d, 1Fh
0x1400c62ac  mov     [rbp+3Fh+var_A0], rax
0x1400c62b0  mov     r10d, r8d
0x1400c62b3  mov     rax, [rdi+10h]
0x1400c62b7  mov     [rbp+3Fh+var_90], rax
0x1400c62bb  mov     al, [r14+4Eh]
0x1400c62bf  mov     [rbp+3Fh+var_52], al
0x1400c62c2  mov     eax, [rbx]
0x1400c62c4  shr     eax, 6
0x1400c62c7  and     al, 1
0x1400c62c9  mov     [rbp+3Fh+var_58], r8d
0x1400c62cd  mov     [rbp+3Fh+var_54], al
0x1400c62d0  xor     r8d, r8d
0x1400c62d3  mov     rax, r14
0x1400c62d6  mov     al, [rax+4Dh]
0x1400c62d9  mov     [rbp+3Fh+var_53], al
0x1400c62dc  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1400c62e1  test    rax, rax
0x1400c62e4  jz      short loc_1400C6320
0x1400c62e6  mov     rdx, [rax]
0x1400c62e9  mov     r8d, r10d
0x1400c62ec  mov     r9, [r15+r9+8]
0x1400c62f1  mov     rax, [rbp+3Fh+arg_10]
0x1400c62f5  shl     r9, 0Ch
0x1400c62f9  mov     ecx, [rdx+3Ch]
0x1400c62fc  shr     rcx, 2
0x1400c6300  mov     rax, [rax+8E80h]
0x1400c6307  and     ecx, 3Fh
0x1400c630a  mov     rcx, [rax+rcx*8]
0x1400c630e  mov     rax, [rcx]
0x1400c6311  mov     rax, [rax+188h]
0x1400c6318  call    _guard_dispatch_icall
0x1400c631d  mov     r8, rax
0x1400c6320  mov     rcx, [rbx+30h]
0x1400c6324  lea     rax, [rbp+3Fh+arg_0]
0x1400c6328  mov     r14, [rbp+3Fh+arg_8]
0x1400c632c  lea     r9, [rbp+3Fh+var_A0]; struct COMMIT_VA_STATE *
0x1400c6330  mov     [rsp+0F0h+var_A8], rax; struct VIDMM_ALLOC **
0x1400c6335  mov     [rsp+0F0h+var_B0], 0; bool
0x1400c633a  mov     rdx, [r15+rcx+8]
0x1400c633f  mov     rcx, [rbp+3Fh+arg_18]
0x1400c6343  shl     rdx, 0Ch
0x1400c6347  mov     [rsp+0F0h+var_B8], rdx; unsigned __int64
0x1400c634c  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c634f  mov     rcx, [rcx+28h]
0x1400c6353  mov     [rsp+0F0h+var_C0], rcx; unsigned __int64
0x1400c6358  mov     rcx, [rbp+3Fh+arg_28]
0x1400c635c  mov     [rsp+0F0h+var_C8], rcx; unsigned __int64
0x1400c6361  mov     rcx, r12; this
0x1400c6364  mov     [rsp+0F0h+var_D0], r8; unsigned __int64
0x1400c6369  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c636c  call    ?CommitVirtualAddressRange@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400c6371  movsxd  rdi, eax
0x1400c6374  test    eax, eax
0x1400c6376  jns     short loc_1400C63C1
0x1400c6378  mov     rdx, rdi
0x1400c637b  mov     ecx, 3
0x1400c6380  call    cs:__imp_WdLogSingleEntry1
0x1400c6387  nop     dword ptr [rax+rax+00h]
0x1400c638c  xor     r15d, r15d
0x1400c638f  mov     cs:WdLogGlobalForLineNumber, 1E8Bh
0x1400c6399  mov     r9, [rbp+3Fh+arg_28]; unsigned __int64
0x1400c639d  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c63a0  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c63a3  mov     rcx, r12; this
0x1400c63a6  call    ?DestroyPageTable@VIDMM_PAGE_TABLE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@_K@Z; VIDMM_PAGE_TABLE::DestroyPageTable(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,unsigned __int64)
0x1400c63ab  cmp     [rbp+3Fh+arg_0], r15
0x1400c63af  jz      short loc_1400C640F
0x1400c63b1  mov     rax, [rbp+3Fh+arg_38]
0x1400c63b8  mov     rcx, [rbx+20h]
0x1400c63bc  mov     [rax], rcx
0x1400c63bf  jmp     short loc_1400C640F
0x1400c63c1  mov     rdx, [rbx+38h]
0x1400c63c5  mov     rcx, [rsi+60h]
0x1400c63c9  add     rcx, 8EC0h; Lookaside
0x1400c63d0  mov     rdx, [rdx+r13]; Entry
0x1400c63d4  call    cs:__imp_ExFreeToPagedLookasideList
0x1400c63db  nop     dword ptr [rax+rax+00h]
0x1400c63e0  mov     rax, [rbx+38h]
0x1400c63e4  mov     qword ptr [rax+r13], 0
0x1400c63ec  mov     rax, [rbx+30h]
0x1400c63f0  btr     qword ptr [r15+rax], 0Ah
0x1400c63f6  mov     rax, [rbx+38h]
0x1400c63fa  mov     rdx, rsi; struct CVirtualAddressAllocator *
0x1400c63fd  mov     r8d, [rbp+3Fh+arg_30]; unsigned int
0x1400c6401  mov     rcx, rbx; this
0x1400c6404  mov     [rax+r13], r12
0x1400c6408  call    ?SetPageTableInPde@VIDMM_PAGE_DIRECTORY@@QEAAXPEAVCVirtualAddressAllocator@@I@Z; VIDMM_PAGE_DIRECTORY::SetPageTableInPde(CVirtualAddressAllocator *,uint)
0x1400c640d  xor     edi, edi
0x1400c640f  dec     dword ptr [rbx+4]
0x1400c6412  mov     eax, edi
0x1400c6414  add     rsp, 0B8h
0x1400c641b  pop     r15
0x1400c641d  pop     r14
0x1400c641f  pop     r13
0x1400c6421  pop     r12
0x1400c6423  pop     rdi
0x1400c6424  pop     rsi
0x1400c6425  pop     rbx
0x1400c6426  pop     rbp
0x1400c6427  retn
```
