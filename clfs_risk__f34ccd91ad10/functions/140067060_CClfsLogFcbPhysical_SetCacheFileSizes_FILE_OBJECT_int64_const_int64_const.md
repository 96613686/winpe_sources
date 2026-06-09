# CClfsLogFcbPhysical::SetCacheFileSizes(_FILE_OBJECT *,__int64 const &,__int64 const &)

- ea: `0x140067060`
- end: `0x140067338`
- name: `?SetCacheFileSizes@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@AEB_J1@Z`
- size: `728`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, const __int64 *, const __int64 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400035a8`
- `0x140005f1c`
- `0x140009420`
- `0x1400346c4`
- `0x1400456a0`
- `0x140061230`
- `0x140076e00`

## callees

- `0x140003590`
- `0x140005f00`
- `0x1400075b0`
- `0x14000a8e0`
- `0x140017f20`
- `0x140066e00`
- `0x140067060`
- `0x140067458`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007adbe`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007adbe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400670bd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400670bd`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400672cc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007ae5d`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400672cc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007ae5d`
- `ntoskrnl!KeBugCheckEx` at `0x140067315`
- `ntoskrnl!KeBugCheckEx` at `0x14007ae11`
- `ntoskrnl!KeBugCheckEx` at `0x140067315`
- `ntoskrnl!KeBugCheckEx` at `0x14007ae11`
- `ntoskrnl!CcSetFileSizes` at `0x1400671c9`
- `ntoskrnl!CcSetFileSizes` at `0x1400671c9`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::SetCacheFileSizes(
        union _CLS_LSN *this,
        struct _FILE_OBJECT *a2,
        union _CLS_LSN *a3,
        signed __int64 *a4)
{
  unsigned int v7; // r9d
  struct _CC_FILE_SIZES *v8; // rcx
  signed __int64 ullOffset; // rbx
  signed __int64 v10; // rdx
  union _CLS_LSN *v11; // r13
  unsigned int v12; // eax
  unsigned int cidContainer; // r11d
  unsigned int v14; // r10d
  signed __int64 v15; // r8
  ULONG v16; // r15d
  CLFS_CONTAINER_ID v17; // eax
  CLFS_LSN *plsn; // [rsp+58h] [rbp-78h]
  struct _ERESOURCE *Resource; // [rsp+80h] [rbp-50h]
  char v21[48]; // [rsp+88h] [rbp-48h] BYREF
  BOOLEAN v23; // [rsp+E8h] [rbp+18h]

  if ( (a3->ullOffset & 0x8000000000000000uLL) != 0LL && *a4 < 0 )
    return 0;
  Resource = (struct _ERESOURCE *)&this[150];
  v23 = ExAcquireResourceExclusiveLite((PERESOURCE)&this[150], 1u);
  v8 = (struct _CC_FILE_SIZES *)&this[10];
  ullOffset = this[10].ullOffset;
  plsn = this + 171;
  if ( (a3->ullOffset & 0x8000000000000000uLL) == 0LL )
    this[11] = *a3;
  v10 = *a4;
  if ( *a4 < 0 )
    v10 = ullOffset;
  else
    v8->AllocationSize.QuadPart = v10;
  v11 = this + 60;
  if ( this == (union _CLS_LSN *)-480LL )
    goto LABEL_9;
  if ( CLFS_LSN_NULL.ullOffset != v11->ullOffset )
  {
    if ( CLFS_LSN_INVALID.ullOffset == v11->ullOffset )
    {
      v15 = -1;
LABEL_16:
      if ( v15 >= v10 )
      {
        CClfsLogFcbPhysical::PurgeCacheSection(
          (CClfsLogFcbPhysical *)this,
          (CLFS_LSN *)&CLFS_LSN_NULL,
          (CLFS_LSN *)&CLFS_LSN_NULL,
          v7);
        *plsn = *(CLFS_LSN *)(*(__int64 (__fastcall **)(union _CLS_LSN *, char *))(this->ullOffset + 352))(this, v21);
        if ( ClfsLsnRecordSequence(plsn) )
        {
          v16 = ClfsLsnBlockOffset(plsn);
          v17 = ClfsLsnContainer(plsn);
          *plsn = ClfsLsnCreate(v17, v16, 0);
        }
        this[11].ullOffset = CClfsLogFcbPhysical::LsnToCacheOffset((CClfsLogFcbPhysical *)this, this + 60);
        v8 = (struct _CC_FILE_SIZES *)&this[10];
      }
      goto LABEL_17;
    }
LABEL_9:
    v12 = -1;
    v7 = -1;
    if ( this != (union _CLS_LSN *)-1368LL )
      v7 = this[171].offset.idxRecord & 0xFFFFFE00;
    cidContainer = -1;
    if ( this != (union _CLS_LSN *)-1368LL )
      cidContainer = this[171].offset.cidContainer;
    v14 = -1;
    if ( this != (union _CLS_LSN *)-480LL )
    {
      v14 = v11->offset.idxRecord & 0xFFFFFE00;
      v12 = this[60].offset.cidContainer;
    }
    v15 = v14 + this[87].ullOffset * (v12 - (unsigned __int64)cidContainer) - v7;
    goto LABEL_16;
  }
LABEL_17:
  CcSetFileSizes(a2, v8);
  if ( v23 )
    ExReleaseResourceForThreadLite(Resource, (ERESOURCE_THREAD)KeGetCurrentThread());
  return 0;
}

```

## disassembly

```asm
0x140067060  mov     [rsp+FileObject], rdx
0x140067065  mov     [rsp+arg_0], rcx
0x14006706a  push    rbx
0x14006706b  push    rsi
0x14006706c  push    rdi
0x14006706d  push    r12
0x14006706f  push    r13
0x140067071  push    r14
0x140067073  push    r15
0x140067075  sub     rsp, 80h
0x14006707c  mov     r13, r9
0x14006707f  mov     r15, r8
0x140067082  mov     r12, rcx
0x140067085  xor     r14d, r14d
0x140067088  mov     [rsp+0B8h+var_70], r14
0x14006708d  mov     [rsp+0B8h+var_68], r14
0x140067092  cmp     [r8], r14
0x140067095  jl      loc_1400672EF
0x14006709b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400670a2  mov     [rsp+0B8h+var_60], rax
0x1400670a7  mov     [rsp+0B8h+var_88], r14d
0x1400670ac  lea     rax, [rcx+4B0h]
0x1400670b3  mov     [rsp+0B8h+Resource], rax
0x1400670b8  mov     dl, 1; Wait
0x1400670ba  mov     rcx, rax; Resource
0x1400670bd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400670c4  nop     dword ptr [rax+rax+00h]
0x1400670c9  mov     [rsp+0B8h+arg_10], al
0x1400670d0  lea     rcx, [r12+50h]
0x1400670d5  mov     [rsp+0B8h+var_58], rcx
0x1400670da  mov     rbx, [rcx]
0x1400670dd  mov     [rsp+0B8h+var_70], rbx
0x1400670e2  lea     rdx, [r12+58h]
0x1400670e7  mov     [rsp+0B8h+var_80], rdx
0x1400670ec  mov     rdi, [rdx]
0x1400670ef  mov     [rsp+0B8h+var_68], rdi
0x1400670f4  lea     r8, [r12+558h]
0x1400670fc  mov     [rsp+0B8h+plsn], r8
0x140067101  mov     rsi, [r8]
0x140067104  mov     [rsp+0B8h+var_60], rsi
0x140067109  mov     rax, [r15]
0x14006710c  test    rax, rax
0x14006710f  js      short loc_140067114
0x140067111  mov     [rdx], rax
0x140067114  mov     rdx, [r13+0]
0x140067118  test    rdx, rdx
0x14006711b  js      loc_14006726D
0x140067121  mov     [rcx], rdx
0x140067124  lea     r13, [r12+1E0h]
0x14006712c  test    r13, r13
0x14006712f  jz      short loc_140067154
0x140067131  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140067138  cmp     rax, [r13+0]
0x14006713c  jz      short loc_1400671B9
0x14006713e  test    r13, r13
0x140067141  jz      short loc_140067154
0x140067143  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14006714a  cmp     rax, [r13+0]
0x14006714e  jz      loc_140067275
0x140067154  mov     eax, 0FFFFFFFFh
0x140067159  mov     r9d, eax
0x14006715c  test    r8, r8
0x14006715f  jz      short loc_14006716B
0x140067161  mov     r9d, [r8]
0x140067164  and     r9d, 0FFFFFE00h; unsigned __int8
0x14006716b  mov     r11d, eax
0x14006716e  test    r8, r8
0x140067171  jz      short loc_140067177
0x140067173  mov     r11d, [r8+4]
0x140067177  mov     r15, [r12+2B8h]
0x14006717f  mov     r10d, eax
0x140067182  test    r13, r13
0x140067185  jz      short loc_14006719B
0x140067187  mov     r10d, [r13+0]
0x14006718b  and     r10d, 0FFFFFE00h
0x140067192  test    r13, r13
0x140067195  jz      short loc_14006719B
0x140067197  mov     eax, [r13+4]
0x14006719b  mov     r8d, eax
0x14006719e  mov     eax, r11d
0x1400671a1  sub     r8, rax
0x1400671a4  imul    r8, r15
0x1400671a8  mov     eax, r9d
0x1400671ab  sub     r8, rax
0x1400671ae  mov     eax, r10d
0x1400671b1  add     r8, rax
0x1400671b4  cmp     r8, rdx
0x1400671b7  jge     short loc_14006720A
0x1400671b9  mov     r13, [rsp+0B8h+var_80]
0x1400671be  mov     rdx, rcx; FileSizes
0x1400671c1  mov     rcx, [rsp+0B8h+FileObject]; FileObject
0x1400671c9  call    cs:__imp_CcSetFileSizes
0x1400671d0  nop     dword ptr [rax+rax+00h]
0x1400671d5  mov     r15d, [rsp+0B8h+var_88]
0x1400671da  jmp     loc_1400672AD
0x1400671df  mov     r15d, eax
0x1400671e2  mov     [rsp+0B8h+var_88], eax
0x1400671e6  xor     r14d, r14d
0x1400671e9  mov     r12, [rsp+0B8h+arg_0]
0x1400671f1  mov     rbx, [rsp+0B8h+var_70]
0x1400671f6  mov     rdi, [rsp+0B8h+var_68]
0x1400671fb  mov     rsi, [rsp+0B8h+var_60]
0x140067200  mov     r13, [rsp+0B8h+var_80]
0x140067205  jmp     loc_1400672AD
0x14006720a  lea     r8, CLFS_LSN_NULL; CLFS_LSN *
0x140067211  lea     rdx, CLFS_LSN_NULL; plsn
0x140067218  mov     rcx, r12; this
0x14006721b  call    ?PurgeCacheSection@CClfsLogFcbPhysical@@AEAAEAEBT_CLS_LSN@@0E@Z; CClfsLogFcbPhysical::PurgeCacheSection(_CLS_LSN const &,_CLS_LSN const &,uchar)
0x140067220  mov     rax, [r12]
0x140067224  mov     rax, [rax+160h]
0x14006722b  lea     rdx, [rsp+0B8h+var_48]
0x140067230  mov     rcx, r12
0x140067233  call    _guard_dispatch_icall
0x140067238  mov     rcx, [rax]
0x14006723b  mov     r15, [rsp+0B8h+plsn]
0x140067240  mov     [r15], rcx
0x140067243  mov     rcx, r15; plsn
0x140067246  call    ClfsLsnRecordSequence
0x14006724b  test    eax, eax
0x14006724d  jnz     short loc_140067281
0x14006724f  mov     rdx, r13; union _CLS_LSN *
0x140067252  mov     rcx, r12; this
0x140067255  call    ?LsnToCacheOffset@CClfsLogFcbPhysical@@AEAA_KAEBT_CLS_LSN@@@Z; CClfsLogFcbPhysical::LsnToCacheOffset(_CLS_LSN const &)
0x14006725a  mov     r13, [rsp+0B8h+var_80]
0x14006725f  mov     [r13+0], rax
0x140067263  mov     rcx, [rsp+0B8h+var_58]
0x140067268  jmp     loc_1400671BE
0x14006726d  mov     rdx, rbx
0x140067270  jmp     loc_140067124
0x140067275  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14006727c  jmp     loc_1400671B4
0x140067281  mov     rcx, r15; plsn
0x140067284  call    ClfsLsnBlockOffset
0x140067289  mov     r15d, eax
0x14006728c  mov     rcx, [rsp+0B8h+plsn]; plsn
0x140067291  call    ClfsLsnContainer
0x140067296  xor     r8d, r8d; cRecord
0x140067299  mov     edx, r15d; offBlock
0x14006729c  mov     ecx, eax; cidContainer
0x14006729e  call    ClfsLsnCreate
0x1400672a3  mov     rcx, [rsp+0B8h+plsn]
0x1400672a8  mov     [rcx], rax
0x1400672ab  jmp     short loc_14006724F
0x1400672ad  movzx   eax, [rsp+0B8h+arg_10]
0x1400672b5  test    r15d, r15d
0x1400672b8  js      short loc_1400672FC
0x1400672ba  test    al, al
0x1400672bc  jz      short loc_1400672D8
0x1400672be  mov     rdx, gs:188h; ResourceThreadId
0x1400672c7  mov     rcx, [rsp+0B8h+Resource]; Resource
0x1400672cc  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400672d3  nop     dword ptr [rax+rax+00h]
0x1400672d8  mov     eax, r15d
0x1400672db  add     rsp, 80h
0x1400672e2  pop     r15
0x1400672e4  pop     r14
0x1400672e6  pop     r13
0x1400672e8  pop     r12
0x1400672ea  pop     rdi
0x1400672eb  pop     rsi
0x1400672ec  pop     rbx
0x1400672ed  retn
0x1400672ef  cmp     [r9], r14
0x1400672f2  jge     loc_14006709B
0x1400672f8  xor     eax, eax
0x1400672fa  jmp     short loc_1400672DB
0x1400672fc  test    al, al
0x1400672fe  jnz     short loc_140067322
0x140067300  mov     [rsp+0B8h+BugCheckParameter4], r14; BugCheckParameter4
0x140067305  xor     r9d, r9d; BugCheckParameter3
0x140067308  mov     r8, r12; BugCheckParameter2
0x14006730b  mov     edx, 3Fh ; '?'; BugCheckParameter1
0x140067310  mov     ecx, 0C1F5h; BugCheckCode
0x140067315  call    cs:__imp_KeBugCheckEx
0x140067322  mov     rcx, [rsp+0B8h+var_58]
0x140067327  mov     [rcx], rbx
0x14006732a  mov     [r13+0], rdi
0x14006732e  mov     rcx, [rsp+0B8h+plsn]
0x140067333  mov     [rcx], rsi
0x140067336  jmp     short loc_1400672BA
0x14007adb0  push    rbp
0x14007adb2  sub     rsp, 30h
0x14007adb6  mov     rbp, rdx
0x14007adb9  mov     rcx, [rcx]
0x14007adbc  mov     ecx, [rcx]; Exception
0x14007adbe  call    cs:__imp_FsRtlIsNtstatusExpected
0x14007adc5  nop     dword ptr [rax+rax+00h]
0x14007adca  xor     ecx, ecx
0x14007adcc  test    al, al
0x14007adce  setnz   cl
0x14007add1  mov     eax, ecx
0x14007add3  add     rsp, 30h
0x14007add7  pop     rbp
0x14007add8  retn
0x14007adda  push    rbp
0x14007addc  sub     rsp, 30h
0x14007ade0  mov     rbp, rdx
0x14007ade3  movzx   edx, byte ptr [rbp+0D0h]
0x14007adea  cmp     dword ptr [rbp+30h], 0
0x14007adee  jge     short loc_14007AE42
0x14007adf0  test    dl, dl
0x14007adf2  jnz     short loc_14007AE1E
0x14007adf4  mov     [rsp+38h+var_18], 0; BugCheckParameter4
0x14007adfd  xor     r9d, r9d; BugCheckParameter3
0x14007ae00  mov     r8, [rbp+0C0h]; BugCheckParameter2
0x14007ae07  mov     edx, 3Fh ; '?'; BugCheckParameter1
0x14007ae0c  mov     ecx, 0C1F5h; BugCheckCode
0x14007ae11  call    cs:__imp_KeBugCheckEx
0x14007ae1e  mov     rcx, [rbp+0C0h]
0x14007ae25  mov     rax, [rbp+48h]
0x14007ae29  mov     [rcx+50h], rax
0x14007ae2d  mov     rax, [rbp+50h]
0x14007ae31  mov     [rcx+58h], rax
0x14007ae35  mov     rax, [rbp+58h]
0x14007ae39  mov     [rcx+558h], rax
0x14007ae40  jmp     short loc_14007AE49
0x14007ae42  mov     rcx, [rbp+0C0h]
0x14007ae49  test    dl, dl
0x14007ae4b  jz      short loc_14007AE6A
0x14007ae4d  mov     rdx, gs:188h; ResourceThreadId
0x14007ae56  add     rcx, 4B0h; Resource
0x14007ae5d  call    cs:__imp_ExReleaseResourceForThreadLite
0x14007ae64  nop     dword ptr [rax+rax+00h]
0x14007ae69  nop
0x14007ae6a  add     rsp, 30h
0x14007ae6e  pop     rbp
0x14007ae6f  retn
```
