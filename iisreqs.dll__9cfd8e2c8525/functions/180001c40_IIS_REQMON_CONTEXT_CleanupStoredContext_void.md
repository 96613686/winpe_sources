# IIS_REQMON_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001c40`
- end: `0x180001cac`
- name: `?CleanupStoredContext@IIS_REQMON_CONTEXT@@UEAAXXZ`
- size: `108`
- prototype: `void __fastcall(IIS_REQMON_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001c40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c8f`

## pseudocode

```c
void __fastcall IIS_REQMON_CONTEXT::CleanupStoredContext(IIS_REQMON_CONTEXT *this)
{
  _QWORD *v2; // rax
  __int64 v3; // r8
  _QWORD *v4; // rdx

  EnterCriticalSection(&IIS_REQMON_CONTEXT::sm_csRequestList);
  v2 = (_QWORD *)((char *)this + 8);
  v3 = *((_QWORD *)this + 1);
  if ( *(IIS_REQMON_CONTEXT **)(v3 + 8) != (IIS_REQMON_CONTEXT *)((char *)this + 8)
    || (v4 = (_QWORD *)*((_QWORD *)this + 2), (_QWORD *)*v4 != v2) )
  {
    __fastfail(3u);
  }
  --IIS_REQMON_CONTEXT::sm_cRequests;
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  *v2 = 0;
  *((_QWORD *)this + 2) = 0;
  LeaveCriticalSection(&IIS_REQMON_CONTEXT::sm_csRequestList);
  *(_QWORD *)this = &IIS_REQMON_CONTEXT::`vftable';
}

```

## disassembly

```asm
0x180001c40  push    rbx
0x180001c42  sub     rsp, 20h
0x180001c46  mov     rbx, rcx
0x180001c49  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c50  call    cs:__imp_EnterCriticalSection
0x180001c56  lea     rax, [rbx+8]
0x180001c5a  mov     r8, [rax]
0x180001c5d  cmp     [r8+8], rax
0x180001c61  jnz     short loc_180001CA5
0x180001c63  mov     rdx, [rax+8]
0x180001c67  cmp     [rdx], rax
0x180001c6a  jnz     short loc_180001CA5
0x180001c6c  dec     cs:?sm_cRequests@IIS_REQMON_CONTEXT@@2KA; ulong IIS_REQMON_CONTEXT::sm_cRequests
0x180001c72  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c79  mov     [rdx], r8
0x180001c7c  mov     [r8+8], rdx
0x180001c80  mov     qword ptr [rax], 0
0x180001c87  mov     qword ptr [rbx+10h], 0
0x180001c8f  call    cs:__imp_LeaveCriticalSection
0x180001c95  lea     rax, ??_7IIS_REQMON_CONTEXT@@6B@; const IIS_REQMON_CONTEXT::`vftable'
0x180001c9c  mov     [rbx], rax
0x180001c9f  add     rsp, 20h
0x180001ca3  pop     rbx
0x180001ca4  retn
0x180001ca5  mov     ecx, 3
0x180001caa  int     29h; Win8: RtlFailFast(ecx)
```
