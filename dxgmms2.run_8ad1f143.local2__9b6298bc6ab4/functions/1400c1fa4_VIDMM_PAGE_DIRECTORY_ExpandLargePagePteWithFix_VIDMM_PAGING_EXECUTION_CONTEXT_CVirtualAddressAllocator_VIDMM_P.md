# VIDMM_PAGE_DIRECTORY::ExpandLargePagePteWithFix(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,VIDMM_PAGE_TABLE_LEVEL_DESC const *,COMMIT_VA_STATE const *,unsigned __int64,uint,VIDMM_ALLOC * *)

- ea: `0x1400c1fa4`
- end: `0x1400c227d`
- name: `?ExpandLargePagePteWithFix@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUVIDMM_PAGE_TABLE_LEVEL_DESC@@PEBUCOMMIT_VA_STATE@@_KIPEAPEAUVIDMM_ALLOC@@@Z`
- size: `729`
- prototype: `__int64 __usercall@<rax>(VIDMM_PAGE_DIRECTORY *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct CVirtualAddressAllocator *@<r8>, const struct VIDMM_PAGE_TABLE_LEVEL_DESC *@<r9>, const struct COMMIT_VA_STATE *, unsigned __int64, unsigned int, struct VIDMM_ALLOC **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c1f60`

## callees

- `0x1400045ec`
- `0x1400311ac`
- `0x140058760`
- `0x140058ac0`
- `0x1400974b8`
- `0x140098d74`
- `0x1400997d4`
- `0x1400c1fa4`
- `0x140103b34`
- `0x140105174`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c2228`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c2228`
- `watchdog!WdLogSingleEntry0` at `0x1400c2024`
- `watchdog!WdLogSingleEntry0` at `0x1400c208c`
- `watchdog!WdLogSingleEntry0` at `0x1400c2024`
- `watchdog!WdLogSingleEntry0` at `0x1400c208c`
- `watchdog!WdLogSingleEntry1` at `0x1400c21d4`
- `watchdog!WdLogSingleEntry1` at `0x1400c21d4`

## string_xrefs

- `0x1400c2035`: `Failed to create a page table`

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
    _InterlockedIncrement(&dword_1400867F8);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 7729;
    DxgkLogInternalTriageEvent(v15, 262145, v16, (unsigned int)L"Failed to create a page table", 7729, 0, 0, 0);
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
        WdLogGlobalForLineNumber = 7818;
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
  WdLogGlobalForLineNumber = 7752;
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
0x1400c1fa4  mov     [rsp-8+arg_18], r9
0x1400c1fa9  mov     [rsp-8+arg_8], rdx
0x1400c1fae  push    rbp
0x1400c1faf  push    rbx
0x1400c1fb0  push    rsi
0x1400c1fb1  push    rdi
0x1400c1fb2  push    r12
0x1400c1fb4  push    r13
0x1400c1fb6  push    r14
0x1400c1fb8  push    r15
0x1400c1fba  lea     rbp, [rsp-7]
0x1400c1fbf  sub     rsp, 0B8h
0x1400c1fc6  mov     rax, [r8+60h]
0x1400c1fca  mov     rsi, r8
0x1400c1fcd  inc     dword ptr [rcx+4]
0x1400c1fd0  xor     r15d, r15d
0x1400c1fd3  mov     r14, [rbp+3Fh+arg_20]
0x1400c1fd7  mov     rdi, rdx
0x1400c1fda  mov     edx, [rcx]
0x1400c1fdc  mov     rbx, rcx
0x1400c1fdf  mov     r8d, edx
0x1400c1fe2  mov     [rbp+3Fh+arg_0], r15
0x1400c1fe6  shr     r8d, 6
0x1400c1fea  mov     [rbp+3Fh+arg_10], rax
0x1400c1fee  test    r8b, 1
0x1400c1ff2  jz      short loc_1400C1FFD
0x1400c1ff4  mov     r9b, 1
0x1400c1ff7  cmp     [r14+4Eh], r15b
0x1400c1ffb  jnz     short loc_1400C2000
0x1400c1ffd  mov     r9b, r15b
0x1400c2000  shr     edx, 8
0x1400c2003  and     r8b, 1
0x1400c2007  and     edx, 1Fh
0x1400c200a  mov     rcx, rsi; struct CVirtualAddressAllocator *
0x1400c200d  call    CreatePageTable
0x1400c2012  mov     r12, rax
0x1400c2015  test    rax, rax
0x1400c2018  jnz     short loc_1400C206A
0x1400c201a  lock inc cs:dword_1400867F8
0x1400c2021  lea     ecx, [rax+6]
0x1400c2024  call    cs:__imp_WdLogSingleEntry0
0x1400c202b  nop     dword ptr [rax+rax+00h]
0x1400c2030  mov     [rsp+0F0h+var_B8], r15
0x1400c2035  lea     r9, aFailedToCreate_28; "Failed to create a page table"
0x1400c203c  mov     eax, 1E31h
0x1400c2041  mov     [rsp+0F0h+var_C0], r15
0x1400c2046  mov     [rsp+0F0h+var_C8], r15
0x1400c204b  mov     edx, 40001h
0x1400c2050  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c2056  mov     [rsp+0F0h+var_D0], rax
0x1400c205b  call    DxgkLogInternalTriageEvent
0x1400c2060  mov     edi, 0C0000017h
0x1400c2065  jmp     loc_1400C21FF
0x1400c206a  lea     rax, [rbp+3Fh+arg_0]
0x1400c206e  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c2071  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c2074  mov     [rsp+0F0h+var_D0], rax; struct VIDMM_ALLOC **
0x1400c2079  mov     rcx, r12; this
0x1400c207c  call    ?EnsureResident@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@_KPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::EnsureResident(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,unsigned __int64,VIDMM_ALLOC * *)
0x1400c2081  mov     edi, eax
0x1400c2083  test    eax, eax
0x1400c2085  jns     short loc_1400C20AB
0x1400c2087  mov     ecx, 3
0x1400c208c  call    cs:__imp_WdLogSingleEntry0
0x1400c2093  nop     dword ptr [rax+rax+00h]
0x1400c2098  mov     r14, [rbp+3Fh+arg_8]
0x1400c209c  mov     cs:WdLogGlobalForLineNumber, 1E48h
0x1400c20a6  jmp     loc_1400C21ED
0x1400c20ab  mov     r15d, [rbp+3Fh+arg_30]
0x1400c20af  mov     rax, [rbx+38h]
0x1400c20b3  lea     r13, ds:0[r15*8]
0x1400c20bb  mov     rdi, [rax+r13]
0x1400c20bf  test    rdi, rdi
0x1400c20c2  jz      loc_1400C224A
0x1400c20c8  xor     edx, edx; Val
0x1400c20ca  lea     rcx, [rbp+3Fh+var_A0]; void *
0x1400c20ce  lea     r8d, [rdx+60h]; Size
0x1400c20d2  call    memset
0x1400c20d7  mov     rdx, [rdi]
0x1400c20da  mov     ecx, [rdi+8]
0x1400c20dd  mov     r9, [rbx+30h]
0x1400c20e1  shl     r15, 4
0x1400c20e5  mov     [rbp+3Fh+var_68], ecx
0x1400c20e8  mov     [rbp+3Fh+var_70], rdx
0x1400c20ec  mov     r8, [r15+r9]
0x1400c20f0  mov     rax, r8
0x1400c20f3  shr     r8, 5
0x1400c20f7  btr     rax, 0Ah
0x1400c20fc  and     r8d, 1Fh
0x1400c2100  mov     [rbp+3Fh+var_A0], rax
0x1400c2104  mov     r10d, r8d
0x1400c2107  mov     rax, [rdi+10h]
0x1400c210b  mov     [rbp+3Fh+var_90], rax
0x1400c210f  mov     al, [r14+4Eh]
0x1400c2113  mov     [rbp+3Fh+var_52], al
0x1400c2116  mov     eax, [rbx]
0x1400c2118  shr     eax, 6
0x1400c211b  and     al, 1
0x1400c211d  mov     [rbp+3Fh+var_58], r8d
0x1400c2121  mov     [rbp+3Fh+var_54], al
0x1400c2124  xor     r8d, r8d
0x1400c2127  mov     rax, r14
0x1400c212a  mov     al, [rax+4Dh]
0x1400c212d  mov     [rbp+3Fh+var_53], al
0x1400c2130  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1400c2135  test    rax, rax
0x1400c2138  jz      short loc_1400C2174
0x1400c213a  mov     rdx, [rax]
0x1400c213d  mov     r8d, r10d
0x1400c2140  mov     r9, [r15+r9+8]
0x1400c2145  mov     rax, [rbp+3Fh+arg_10]
0x1400c2149  shl     r9, 0Ch
0x1400c214d  mov     ecx, [rdx+3Ch]
0x1400c2150  shr     rcx, 2
0x1400c2154  mov     rax, [rax+8E80h]
0x1400c215b  and     ecx, 3Fh
0x1400c215e  mov     rcx, [rax+rcx*8]
0x1400c2162  mov     rax, [rcx]
0x1400c2165  mov     rax, [rax+188h]
0x1400c216c  call    _guard_dispatch_icall
0x1400c2171  mov     r8, rax
0x1400c2174  mov     rcx, [rbx+30h]
0x1400c2178  lea     rax, [rbp+3Fh+arg_0]
0x1400c217c  mov     r14, [rbp+3Fh+arg_8]
0x1400c2180  lea     r9, [rbp+3Fh+var_A0]; struct COMMIT_VA_STATE *
0x1400c2184  mov     [rsp+0F0h+var_A8], rax; struct VIDMM_ALLOC **
0x1400c2189  mov     [rsp+0F0h+var_B0], 0; bool
0x1400c218e  mov     rdx, [r15+rcx+8]
0x1400c2193  mov     rcx, [rbp+3Fh+arg_18]
0x1400c2197  shl     rdx, 0Ch
0x1400c219b  mov     [rsp+0F0h+var_B8], rdx; unsigned __int64
0x1400c21a0  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c21a3  mov     rcx, [rcx+28h]
0x1400c21a7  mov     [rsp+0F0h+var_C0], rcx; unsigned __int64
0x1400c21ac  mov     rcx, [rbp+3Fh+arg_28]
0x1400c21b0  mov     [rsp+0F0h+var_C8], rcx; unsigned __int64
0x1400c21b5  mov     rcx, r12; this
0x1400c21b8  mov     [rsp+0F0h+var_D0], r8; unsigned __int64
0x1400c21bd  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c21c0  call    ?CommitVirtualAddressRange@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_TABLE::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)
0x1400c21c5  movsxd  rdi, eax
0x1400c21c8  test    eax, eax
0x1400c21ca  jns     short loc_1400C2215
0x1400c21cc  mov     rdx, rdi
0x1400c21cf  mov     ecx, 3
0x1400c21d4  call    cs:__imp_WdLogSingleEntry1
0x1400c21db  nop     dword ptr [rax+rax+00h]
0x1400c21e0  xor     r15d, r15d
0x1400c21e3  mov     cs:WdLogGlobalForLineNumber, 1E8Ah
0x1400c21ed  mov     r9, [rbp+3Fh+arg_28]; unsigned __int64
0x1400c21f1  mov     r8, rsi; struct CVirtualAddressAllocator *
0x1400c21f4  mov     rdx, r14; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c21f7  mov     rcx, r12; this
0x1400c21fa  call    ?DestroyPageTable@VIDMM_PAGE_TABLE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@_K@Z; VIDMM_PAGE_TABLE::DestroyPageTable(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,unsigned __int64)
0x1400c21ff  cmp     [rbp+3Fh+arg_0], r15
0x1400c2203  jz      short loc_1400C2263
0x1400c2205  mov     rax, [rbp+3Fh+arg_38]
0x1400c220c  mov     rcx, [rbx+20h]
0x1400c2210  mov     [rax], rcx
0x1400c2213  jmp     short loc_1400C2263
0x1400c2215  mov     rdx, [rbx+38h]
0x1400c2219  mov     rcx, [rsi+60h]
0x1400c221d  add     rcx, 8EC0h; Lookaside
0x1400c2224  mov     rdx, [rdx+r13]; Entry
0x1400c2228  call    cs:__imp_ExFreeToPagedLookasideList
0x1400c222f  nop     dword ptr [rax+rax+00h]
0x1400c2234  mov     rax, [rbx+38h]
0x1400c2238  mov     qword ptr [rax+r13], 0
0x1400c2240  mov     rax, [rbx+30h]
0x1400c2244  btr     qword ptr [r15+rax], 0Ah
0x1400c224a  mov     rax, [rbx+38h]
0x1400c224e  mov     rdx, rsi; struct CVirtualAddressAllocator *
0x1400c2251  mov     r8d, [rbp+3Fh+arg_30]; unsigned int
0x1400c2255  mov     rcx, rbx; this
0x1400c2258  mov     [rax+r13], r12
0x1400c225c  call    ?SetPageTableInPde@VIDMM_PAGE_DIRECTORY@@QEAAXPEAVCVirtualAddressAllocator@@I@Z; VIDMM_PAGE_DIRECTORY::SetPageTableInPde(CVirtualAddressAllocator *,uint)
0x1400c2261  xor     edi, edi
0x1400c2263  dec     dword ptr [rbx+4]
0x1400c2266  mov     eax, edi
0x1400c2268  add     rsp, 0B8h
0x1400c226f  pop     r15
0x1400c2271  pop     r14
0x1400c2273  pop     r13
0x1400c2275  pop     r12
0x1400c2277  pop     rdi
0x1400c2278  pop     rsi
0x1400c2279  pop     rbx
0x1400c227a  pop     rbp
0x1400c227b  retn
```
