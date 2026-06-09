# SecRegInitializeData

- ea: `0x1400331e4`
- end: `0x14003348b`
- name: `SecRegInitializeData`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400331b8`

## callees

- `0x140011610`
- `0x1400119c0`
- `0x1400331e4`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400332d3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033307`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033337`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033367`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003339f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400333d7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033407`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033437`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033467`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400332d3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033307`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033337`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033367`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003339f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400333d7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033407`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033437`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140033467`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140033227`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140033227`
- `ntoskrnl!KeInitializeEvent` at `0x14003328a`
- `ntoskrnl!KeInitializeEvent` at `0x14003328a`

## pseudocode

```c
__int64 SecRegInitializeData()
{
  PVOID PoolWithTag; // rax
  char *v2; // rcx
  _QWORD *v3; // rax

  if ( qword_140020008 )
    PoolWithTag = (PVOID)((__int64 (__fastcall *)(__int64, __int64, __int64))qword_140020008)(64, 1280, 1683120979);
  else
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x500u, 0x64526353u);
  RegData = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0x500u);
  *(_WORD *)RegData = -5623;
  *((_WORD *)RegData + 1) = 1280;
  v2 = (char *)RegData;
  *((_DWORD *)RegData + 4) = 1;
  *((_QWORD *)v2 + 3) = 0;
  *((_DWORD *)v2 + 8) = 0;
  KeInitializeEvent((PRKEVENT)(v2 + 40), SynchronizationEvent, 0);
  v3 = (char *)RegData + 72;
  *((_QWORD *)RegData + 10) = (char *)RegData + 72;
  *v3 = v3;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 1, 0, 0, 0, 0x38u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 2, 0, 0, 0, 0x58u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 3, 0, 0, 0, 0x38u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 4, 0, 0, 0, 0x40u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 5, 0, 0, 0, 0x28u, 0x73526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 6, 0, 0, 0, 0x230u, 0x6B526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 7, 0, 0, 0, 0x40u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 8, 0, 0, 0, 0x40u, 0x63526353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 9, 0, 0, 0, 0x40u, 0x63526353u, 0);
  return 0;
}

```

## disassembly

```asm
0x1400331e4  mov     [rsp+arg_0], rbx
0x1400331e9  mov     [rsp+arg_8], rbp
0x1400331ee  mov     [rsp+arg_10], rsi
0x1400331f3  push    rdi
0x1400331f4  sub     rsp, 40h
0x1400331f8  mov     rax, cs:qword_140020008
0x1400331ff  xor     esi, esi
0x140033201  mov     ebx, 500h
0x140033206  mov     ebp, 40h ; '@'
0x14003320b  mov     r8d, 64526353h; Tag
0x140033211  mov     edx, ebx; NumberOfBytes
0x140033213  test    rax, rax
0x140033216  jz      short loc_140033222
0x140033218  mov     ecx, ebp
0x14003321a  call    cs:__guard_dispatch_icall_fptr
0x140033220  jmp     short loc_140033233
0x140033222  mov     ecx, 200h; PoolType
0x140033227  call    cs:__imp_ExAllocatePoolWithTag
0x14003322e  nop     dword ptr [rax+rax+00h]
0x140033233  mov     cs:RegData, rax
0x14003323a  test    rax, rax
0x14003323d  jnz     short loc_140033249
0x14003323f  mov     eax, 0C000009Ah
0x140033244  jmp     loc_140033475
0x140033249  mov     r8, rbx; Size
0x14003324c  xor     edx, edx; Val
0x14003324e  mov     rcx, rax; void *
0x140033251  call    memset
0x140033256  mov     rax, cs:RegData
0x14003325d  mov     edx, 1; Type
0x140033262  xor     r8d, r8d; State
0x140033265  mov     word ptr [rax], 0EA09h
0x14003326a  mov     rax, cs:RegData
0x140033271  mov     [rax+2], bx
0x140033275  mov     rcx, cs:RegData
0x14003327c  mov     [rcx+10h], edx
0x14003327f  mov     [rcx+18h], rsi
0x140033283  mov     [rcx+20h], esi
0x140033286  add     rcx, 28h ; '('; Event
0x14003328a  call    cs:__imp_KeInitializeEvent
0x140033291  nop     dword ptr [rax+rax+00h]
0x140033296  mov     rax, cs:RegData
0x14003329d  mov     edi, 63526353h
0x1400332a2  add     rax, 48h ; 'H'
0x1400332a6  mov     [rsp+48h+Depth], si; Depth
0x1400332ab  mov     ebx, 38h ; '8'
0x1400332b0  mov     [rsp+48h+Tag], edi; Tag
0x1400332b4  xor     r9d, r9d; Flags
0x1400332b7  mov     [rsp+48h+Size], rbx; Size
0x1400332bc  xor     r8d, r8d; Free
0x1400332bf  xor     edx, edx; Allocate
0x1400332c1  mov     [rax+8], rax
0x1400332c5  mov     [rax], rax
0x1400332c8  mov     rcx, cs:RegData
0x1400332cf  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400332d3  call    cs:__imp_ExInitializePagedLookasideList
0x1400332da  nop     dword ptr [rax+rax+00h]
0x1400332df  mov     rcx, cs:RegData
0x1400332e6  xor     r9d, r9d; Flags
0x1400332e9  mov     [rsp+48h+Depth], si; Depth
0x1400332ee  add     rcx, 100h; Lookaside
0x1400332f5  mov     [rsp+48h+Tag], edi; Tag
0x1400332f9  xor     r8d, r8d; Free
0x1400332fc  xor     edx, edx; Allocate
0x1400332fe  mov     [rsp+48h+Size], 58h ; 'X'; Size
0x140033307  call    cs:__imp_ExInitializePagedLookasideList
0x14003330e  nop     dword ptr [rax+rax+00h]
0x140033313  mov     rcx, cs:RegData
0x14003331a  xor     r9d, r9d; Flags
0x14003331d  mov     [rsp+48h+Depth], si; Depth
0x140033322  add     rcx, 180h; Lookaside
0x140033329  mov     [rsp+48h+Tag], edi; Tag
0x14003332d  xor     r8d, r8d; Free
0x140033330  xor     edx, edx; Allocate
0x140033332  mov     [rsp+48h+Size], rbx; Size
0x140033337  call    cs:__imp_ExInitializePagedLookasideList
0x14003333e  nop     dword ptr [rax+rax+00h]
0x140033343  mov     rcx, cs:RegData
0x14003334a  xor     r9d, r9d; Flags
0x14003334d  mov     [rsp+48h+Depth], si; Depth
0x140033352  add     rcx, 200h; Lookaside
0x140033359  mov     [rsp+48h+Tag], edi; Tag
0x14003335d  xor     r8d, r8d; Free
0x140033360  xor     edx, edx; Allocate
0x140033362  mov     [rsp+48h+Size], rbp; Size
0x140033367  call    cs:__imp_ExInitializePagedLookasideList
0x14003336e  nop     dword ptr [rax+rax+00h]
0x140033373  mov     rcx, cs:RegData
0x14003337a  xor     r9d, r9d; Flags
0x14003337d  mov     [rsp+48h+Depth], si; Depth
0x140033382  add     rcx, 280h; Lookaside
0x140033389  mov     [rsp+48h+Tag], 73526353h; Tag
0x140033391  xor     r8d, r8d; Free
0x140033394  xor     edx, edx; Allocate
0x140033396  mov     [rsp+48h+Size], 28h ; '('; Size
0x14003339f  call    cs:__imp_ExInitializePagedLookasideList
0x1400333a6  nop     dword ptr [rax+rax+00h]
0x1400333ab  mov     rcx, cs:RegData
0x1400333b2  xor     r9d, r9d; Flags
0x1400333b5  mov     [rsp+48h+Depth], si; Depth
0x1400333ba  add     rcx, 300h; Lookaside
0x1400333c1  mov     [rsp+48h+Tag], 6B526353h; Tag
0x1400333c9  xor     r8d, r8d; Free
0x1400333cc  xor     edx, edx; Allocate
0x1400333ce  mov     [rsp+48h+Size], 230h; Size
0x1400333d7  call    cs:__imp_ExInitializePagedLookasideList
0x1400333de  nop     dword ptr [rax+rax+00h]
0x1400333e3  mov     rcx, cs:RegData
0x1400333ea  mov     [rsp+48h+Depth], si; Depth
0x1400333ef  add     rcx, 380h; Lookaside
0x1400333f6  mov     [rsp+48h+Tag], edi; Tag
0x1400333fa  mov     [rsp+48h+Size], rbp; Size
0x1400333ff  xor     r9d, r9d; Flags
0x140033402  xor     r8d, r8d; Free
0x140033405  xor     edx, edx; Allocate
0x140033407  call    cs:__imp_ExInitializePagedLookasideList
0x14003340e  nop     dword ptr [rax+rax+00h]
0x140033413  mov     rcx, cs:RegData
0x14003341a  xor     r9d, r9d; Flags
0x14003341d  mov     [rsp+48h+Depth], si; Depth
0x140033422  add     rcx, 400h; Lookaside
0x140033429  mov     [rsp+48h+Tag], edi; Tag
0x14003342d  xor     r8d, r8d; Free
0x140033430  xor     edx, edx; Allocate
0x140033432  mov     [rsp+48h+Size], rbp; Size
0x140033437  call    cs:__imp_ExInitializePagedLookasideList
0x14003343e  nop     dword ptr [rax+rax+00h]
0x140033443  mov     rcx, cs:RegData
0x14003344a  xor     r9d, r9d; Flags
0x14003344d  mov     [rsp+48h+Depth], si; Depth
0x140033452  add     rcx, 480h; Lookaside
0x140033459  mov     [rsp+48h+Tag], edi; Tag
0x14003345d  xor     r8d, r8d; Free
0x140033460  xor     edx, edx; Allocate
0x140033462  mov     [rsp+48h+Size], rbp; Size
0x140033467  call    cs:__imp_ExInitializePagedLookasideList
0x14003346e  nop     dword ptr [rax+rax+00h]
0x140033473  xor     eax, eax
0x140033475  mov     rbx, [rsp+48h+arg_0]
0x14003347a  mov     rbp, [rsp+48h+arg_8]
0x14003347f  mov     rsi, [rsp+48h+arg_10]
0x140033484  add     rsp, 40h
0x140033488  pop     rdi
0x140033489  retn
```
