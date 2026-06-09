# FatDeleteFcb

- ea: `0x140048184`
- end: `0x1400483b5`
- name: `FatDeleteFcb`
- size: `561`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000363c`
- `0x140025bb8`
- `0x1400268c0`
- `0x140028cc0`
- `0x140029774`
- `0x14002aae8`
- `0x14002adec`
- `0x14002b790`
- `0x14003a3e0`
- `0x140048424`

## callees

- `0x140002ea0`
- `0x14000656c`
- `0x140048184`
- `0x1400492a4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048374`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048374`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14004827e`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14004827e`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140048247`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140048247`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x14004820f`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x14004820f`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140048291`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140048291`
- `ntoskrnl!KeBugCheckEx` at `0x1400481ba`
- `ntoskrnl!KeBugCheckEx` at `0x1400481fb`
- `ntoskrnl!KeBugCheckEx` at `0x1400481ba`
- `ntoskrnl!KeBugCheckEx` at `0x1400481fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048237`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400482f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048310`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004832a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004835d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004838a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048237`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400482f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048310`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004832a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004835d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004838a`

## pseudocode

```c
void __fastcall FatDeleteFcb(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 *v6; // rdx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  struct _ERESOURCE *v10; // rcx
  void *v11; // rcx

  v2 = *a2;
  if ( *(_DWORD *)(*a2 + 232) )
    KeBugCheckEx(0x23u, 0x1C07CDu, 0, 0, 0);
  if ( (unsigned __int16)(*(_WORD *)v2 - 1283) <= 1u )
  {
    v4 = *(void **)(v2 + 408);
    if ( v4 && v4 != (void *)(v2 + 416) )
      ExFreePoolWithTag(v4, 0);
  }
  else
  {
    if ( *(_WORD *)v2 != 1282 )
      KeBugCheckEx(0x23u, 0x1C07D9u, 0, 0, 0);
    FsRtlUninitializeFileLock((PFILE_LOCK)(v2 + 320));
  }
  FsRtlUninitializeOplock((POPLOCK)(v2 + 88));
  if ( (unsigned __int16)(*(_WORD *)v2 - 1282) <= 1u && *(_QWORD *)(v2 + 144) )
  {
    EfsCleanUpCallback(v2 + 144);
    *(_QWORD *)(v2 + 144) = 0;
  }
  FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)v2);
  FsRtlUninitializeLargeMcb((PLARGE_MCB)(v2 + 288));
  if ( *(_WORD *)v2 != 1284 )
  {
    v5 = *(_QWORD *)(v2 + 160);
    if ( *(_QWORD *)(v5 + 8) != v2 + 160 || (v6 = *(__int64 **)(v2 + 168), *v6 != v2 + 160) )
      __fastfail(3u);
    *v6 = v5;
    *(_QWORD *)(v5 + 8) = v6;
  }
  if ( (*(_DWORD *)(v2 + 192) & 0x100) != 0 )
    FatRemoveNames(v5, v2);
  if ( *(_WORD *)v2 != 1284 )
  {
    v7 = *(void **)(v2 + 488);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    v8 = *(void **)(v2 + 536);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
  }
  v9 = *(void **)(v2 + 560);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  FatFreeResource(*(struct _ERESOURCE **)(v2 + 8));
  v10 = *(struct _ERESOURCE **)(v2 + 16);
  if ( v10 != *(struct _ERESOURCE **)(v2 + 8) )
    FatFreeResource(v10);
  v11 = *(void **)(*(_QWORD *)(v2 + 120) + 32LL);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  ExFreeToNPagedLookasideList(&FatNonPagedFcbLookasideList, *(PVOID *)(v2 + 120));
  *(_WORD *)v2 = 0;
  ExFreePoolWithTag((PVOID)v2, 0);
  *a2 = 0;
}

```

## disassembly

```asm
0x140048184  mov     [rsp+arg_0], rbx
0x140048189  mov     [rsp+arg_8], rsi
0x14004818e  push    rdi
0x14004818f  sub     rsp, 30h
0x140048193  mov     rbx, [rdx]
0x140048196  mov     rsi, rdx
0x140048199  cmp     dword ptr [rbx+0E8h], 0
0x1400481a0  jz      short loc_1400481C7
0x1400481a2  xor     r9d, r9d; BugCheckParameter3
0x1400481a5  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x1400481ae  xor     r8d, r8d; BugCheckParameter2
0x1400481b1  mov     edx, 1C07CDh; BugCheckParameter1
0x1400481b6  lea     ecx, [r9+23h]; BugCheckCode
0x1400481ba  call    cs:__imp_KeBugCheckEx
0x1400481c7  movzx   ecx, word ptr [rbx]
0x1400481ca  mov     edx, 503h
0x1400481cf  movzx   eax, cx
0x1400481d2  sub     ax, dx
0x1400481d5  lea     edi, [rdx-1]
0x1400481d8  cmp     ax, 1
0x1400481dc  jbe     short loc_14004821D
0x1400481de  cmp     cx, di
0x1400481e1  jz      short loc_140048208
0x1400481e3  xor     r9d, r9d; BugCheckParameter3
0x1400481e6  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x1400481ef  xor     r8d, r8d; BugCheckParameter2
0x1400481f2  mov     edx, 1C07D9h; BugCheckParameter1
0x1400481f7  lea     ecx, [r9+23h]; BugCheckCode
0x1400481fb  call    cs:__imp_KeBugCheckEx
0x140048208  lea     rcx, [rbx+140h]; FileLock
0x14004820f  call    cs:__imp_FsRtlUninitializeFileLock
0x140048216  nop     dword ptr [rax+rax+00h]
0x14004821b  jmp     short loc_140048243
0x14004821d  mov     rcx, [rbx+198h]; P
0x140048224  test    rcx, rcx
0x140048227  jz      short loc_140048243
0x140048229  lea     rax, [rbx+1A0h]
0x140048230  cmp     rcx, rax
0x140048233  jz      short loc_140048243
0x140048235  xor     edx, edx; Tag
0x140048237  call    cs:__imp_ExFreePoolWithTag
0x14004823e  nop     dword ptr [rax+rax+00h]
0x140048243  lea     rcx, [rbx+58h]; Oplock
0x140048247  call    cs:__imp_FsRtlUninitializeOplock
0x14004824e  nop     dword ptr [rax+rax+00h]
0x140048253  movzx   eax, word ptr [rbx]
0x140048256  sub     ax, di
0x140048259  cmp     ax, 1
0x14004825d  ja      short loc_14004827B
0x14004825f  lea     rdi, [rbx+90h]
0x140048266  cmp     qword ptr [rdi], 0
0x14004826a  jz      short loc_14004827B
0x14004826c  mov     rcx, rdi
0x14004826f  call    EfsCleanUpCallback
0x140048274  mov     qword ptr [rdi], 0
0x14004827b  mov     rcx, rbx; AdvancedHeader
0x14004827e  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140048285  nop     dword ptr [rax+rax+00h]
0x14004828a  lea     rcx, [rbx+120h]; Mcb
0x140048291  call    cs:__imp_FsRtlUninitializeLargeMcb
0x140048298  nop     dword ptr [rax+rax+00h]
0x14004829d  mov     edi, 504h
0x1400482a2  cmp     [rbx], di
0x1400482a5  jz      short loc_1400482CF
0x1400482a7  lea     rax, [rbx+0A0h]
0x1400482ae  mov     rcx, [rax]
0x1400482b1  cmp     [rcx+8], rax
0x1400482b5  jnz     loc_1400483AE
0x1400482bb  mov     rdx, [rax+8]
0x1400482bf  cmp     [rdx], rax
0x1400482c2  jnz     loc_1400483AE
0x1400482c8  mov     [rdx], rcx
0x1400482cb  mov     [rcx+8], rdx
0x1400482cf  test    dword ptr [rbx+0C0h], 100h
0x1400482d9  jz      short loc_1400482E3
0x1400482db  mov     rdx, rbx
0x1400482de  call    FatRemoveNames
0x1400482e3  cmp     [rbx], di
0x1400482e6  jz      short loc_14004831C
0x1400482e8  mov     rcx, [rbx+1E8h]; P
0x1400482ef  test    rcx, rcx
0x1400482f2  jz      short loc_140048302
0x1400482f4  xor     edx, edx; Tag
0x1400482f6  call    cs:__imp_ExFreePoolWithTag
0x1400482fd  nop     dword ptr [rax+rax+00h]
0x140048302  mov     rcx, [rbx+218h]; P
0x140048309  test    rcx, rcx
0x14004830c  jz      short loc_14004831C
0x14004830e  xor     edx, edx; Tag
0x140048310  call    cs:__imp_ExFreePoolWithTag
0x140048317  nop     dword ptr [rax+rax+00h]
0x14004831c  mov     rcx, [rbx+230h]; P
0x140048323  test    rcx, rcx
0x140048326  jz      short loc_140048336
0x140048328  xor     edx, edx; Tag
0x14004832a  call    cs:__imp_ExFreePoolWithTag
0x140048331  nop     dword ptr [rax+rax+00h]
0x140048336  mov     rcx, [rbx+8]; Entry
0x14004833a  call    FatFreeResource
0x14004833f  mov     rcx, [rbx+10h]; Entry
0x140048343  cmp     rcx, [rbx+8]
0x140048347  jz      short loc_14004834E
0x140048349  call    FatFreeResource
0x14004834e  mov     rax, [rbx+78h]
0x140048352  mov     rcx, [rax+20h]; P
0x140048356  test    rcx, rcx
0x140048359  jz      short loc_140048369
0x14004835b  xor     edx, edx; Tag
0x14004835d  call    cs:__imp_ExFreePoolWithTag
0x140048364  nop     dword ptr [rax+rax+00h]
0x140048369  mov     rdx, [rbx+78h]; Entry
0x14004836d  lea     rcx, FatNonPagedFcbLookasideList; Lookaside
0x140048374  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004837b  nop     dword ptr [rax+rax+00h]
0x140048380  xor     eax, eax
0x140048382  xor     edx, edx; Tag
0x140048384  mov     rcx, rbx; P
0x140048387  mov     [rbx], ax
0x14004838a  call    cs:__imp_ExFreePoolWithTag
0x140048391  nop     dword ptr [rax+rax+00h]
0x140048396  mov     rbx, [rsp+38h+arg_0]
0x14004839b  mov     qword ptr [rsi], 0
0x1400483a2  mov     rsi, [rsp+38h+arg_8]
0x1400483a7  add     rsp, 30h
0x1400483ab  pop     rdi
0x1400483ac  retn
0x1400483ae  mov     ecx, 3
0x1400483b3  int     29h; Win8: RtlFailFast(ecx)
```
