# CDDPDEV::IsCommandBufferFencePending(unsigned __int64)

- ea: `0x14002e784`
- end: `0x14002e807`
- name: `?IsCommandBufferFencePending@CDDPDEV@@QEAAE_K@Z`
- size: `131`
- prototype: `unsigned __int8(CDDPDEV *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400218e4`
- `0x14002e960`

## callees

- `0x140012e74`
- `0x14002e784`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002e7b9`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002e7b9`
- `watchdog!WdLogSingleEntry0` at `0x14002e7a3`
- `watchdog!WdLogSingleEntry0` at `0x14002e7a3`

## pseudocode

```c
unsigned __int8 __fastcall CDDPDEV::IsCommandBufferFencePending(
        unsigned __int64 this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax

  v5 = this;
  if ( !*(_QWORD *)(this + 12744) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1127;
    v8 = (_QWORD *)WdLogNewEntry5_WdAssertion(v7, v6);
    this = (unsigned int)dword_14003E570;
    v8[3] = gCddImageInfo;
    v8[4] = this;
    v8[5] = 215857758;
    WdLogGlobalForLineNumber = 1127;
  }
  return CDDPDEV::IsMonitoredFencePending((CDDPDEV *)this, a2, *(void **)(v5 + 12744), a4);
}

```

## disassembly

```asm
0x14002e784  mov     [rsp+arg_0], rbx
0x14002e789  push    rdi
0x14002e78a  sub     rsp, 20h
0x14002e78e  cmp     qword ptr [rcx+31C8h], 0
0x14002e796  mov     rdi, rdx
0x14002e799  mov     rbx, rcx
0x14002e79c  jnz     short loc_14002E7EC
0x14002e79e  mov     ecx, 1
0x14002e7a3  call    cs:__imp_WdLogSingleEntry0
0x14002e7aa  nop     dword ptr [rax+rax+00h]
0x14002e7af  mov     cs:WdLogGlobalForLineNumber, 467h
0x14002e7b9  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002e7c0  nop     dword ptr [rax+rax+00h]
0x14002e7c5  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002e7cc  mov     ecx, cs:dword_14003E570; this
0x14002e7d2  mov     [rax+18h], rdx
0x14002e7d6  mov     [rax+20h], rcx
0x14002e7da  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002e7e2  mov     cs:WdLogGlobalForLineNumber, 467h
0x14002e7ec  mov     r8, [rbx+31C8h]; void *
0x14002e7f3  mov     rdx, rdi; unsigned __int64
0x14002e7f6  call    ?IsMonitoredFencePending@CDDPDEV@@QEAAE_KPEAX0@Z; CDDPDEV::IsMonitoredFencePending(unsigned __int64,void *,unsigned __int64)
0x14002e7fb  mov     rbx, [rsp+28h+arg_0]
0x14002e800  add     rsp, 20h
0x14002e804  pop     rdi
0x14002e805  retn
```
