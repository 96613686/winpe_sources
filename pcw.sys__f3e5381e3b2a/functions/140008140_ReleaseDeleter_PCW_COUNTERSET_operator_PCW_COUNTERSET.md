# ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)

- ea: `0x140008140`
- end: `0x14000821b`
- name: `??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008c48`
- `0x14000930c`
- `0x14000961c`
- `0x14000b5b0`
- `0x14000b654`
- `0x14000bbb0`
- `0x14000bc80`
- `0x14000c240`
- `0x14000ce18`
- `0x14000ce54`
- `0x14000d2e0`
- `0x14000d460`
- `0x14000d660`

## callees

- `0x140008140`
- `0x14000cddc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140008172`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008172`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400081b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400081ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400081b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400081ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008183`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008183`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400081a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400081de`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400081a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400081de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008203`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008203`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400081c9`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400081c9`

## pseudocode

```c
void __fastcall ReleaseDeleter<PCW_COUNTERSET>::operator()(__int64 a1, __int64 a2)
{
  signed __int32 v2; // eax
  signed __int32 v4; // ett
  __int64 v5; // rbx
  signed __int32 v6; // eax
  __int64 v7; // rcx

  v2 = *(_DWORD *)(a2 + 152);
  while ( v2 > 1 )
  {
    v4 = v2;
    v2 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 152), v2 - 1, v2);
    if ( v4 == v2 )
      return;
  }
  v5 = *(_QWORD *)(a2 + 144);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v5, 0);
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 152), 0xFFFFFFFF);
  v7 = *(_QWORD *)(a2 + 144);
  if ( v6 == 1 )
  {
    RtlRbRemoveNode(v7 + 8, a2);
    ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 144), 0);
    KeLeaveCriticalRegion();
    PCW_COUNTERSET::~PCW_COUNTERSET((PCW_COUNTERSET *)a2);
    ExFreePoolWithTag((PVOID)a2, 0);
  }
  else
  {
    ExReleasePushLockExclusiveEx(v7, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140008140  mov     [rsp+arg_8], rbx
0x140008145  push    rdi
0x140008146  sub     rsp, 20h
0x14000814a  mov     eax, [rdx+98h]
0x140008150  mov     rdi, rdx
0x140008153  jmp     short loc_140008166
0x140008155  lea     ecx, [rax-1]
0x140008158  lock cmpxchg [rdx+98h], ecx
0x140008160  jz      loc_14000820F
0x140008166  cmp     eax, 1
0x140008169  jg      short loc_140008155
0x14000816b  mov     rbx, [rdx+90h]
0x140008172  call    cs:__imp_KeEnterCriticalRegion
0x140008179  nop     dword ptr [rax+rax+00h]
0x14000817e  xor     edx, edx
0x140008180  mov     rcx, rbx
0x140008183  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000818a  nop     dword ptr [rax+rax+00h]
0x14000818f  or      eax, 0FFFFFFFFh
0x140008192  lock xadd [rdi+98h], eax
0x14000819a  mov     rcx, [rdi+90h]
0x1400081a1  cmp     eax, 1
0x1400081a4  jz      short loc_1400081C2
0x1400081a6  xor     edx, edx
0x1400081a8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400081af  nop     dword ptr [rax+rax+00h]
0x1400081b4  call    cs:__imp_KeLeaveCriticalRegion
0x1400081bb  nop     dword ptr [rax+rax+00h]
0x1400081c0  jmp     short loc_14000820F
0x1400081c2  add     rcx, 8
0x1400081c6  mov     rdx, rdi
0x1400081c9  call    cs:__imp_RtlRbRemoveNode
0x1400081d0  nop     dword ptr [rax+rax+00h]
0x1400081d5  mov     rcx, [rdi+90h]
0x1400081dc  xor     edx, edx
0x1400081de  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400081e5  nop     dword ptr [rax+rax+00h]
0x1400081ea  call    cs:__imp_KeLeaveCriticalRegion
0x1400081f1  nop     dword ptr [rax+rax+00h]
0x1400081f6  mov     rcx, rdi; this
0x1400081f9  call    ??1PCW_COUNTERSET@@AEAA@XZ; PCW_COUNTERSET::~PCW_COUNTERSET(void)
0x1400081fe  xor     edx, edx; Tag
0x140008200  mov     rcx, rdi; P
0x140008203  call    cs:__imp_ExFreePoolWithTag
0x14000820a  nop     dword ptr [rax+rax+00h]
0x14000820f  mov     rbx, [rsp+28h+arg_8]
0x140008214  add     rsp, 20h
0x140008218  pop     rdi
0x140008219  retn
```
