# RemoveCrlPreFetchEntry(_TVO_CACHE_ENTRY *)

- ea: `0x180012f60`
- end: `0x180012f93`
- name: `?RemoveCrlPreFetchEntry@@YAXPEAU_TVO_CACHE_ENTRY@@@Z`
- size: `51`
- prototype: `void __fastcall(struct _TVO_CACHE_ENTRY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008f80`
- `0x180012e1c`
- `0x180012f0c`

## callees

- `0x180012f60`
- `0x18001e660`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180012f8c`

## pseudocode

```c
void __fastcall RemoveCrlPreFetchEntry(struct _TVO_CACHE_ENTRY *a1)
{
  __int64 v2; // rcx
  bool v3; // zf

  v2 = *((_QWORD *)a1 + 18);
  if ( v2 )
  {
    v3 = g_fTVOAgentProcessExit == 0;
    *(_QWORD *)v2 = 0;
    *((_QWORD *)a1 + 18) = 0;
    if ( v3 )
      SubmitThreadpoolWork(*(PTP_WORK *)(v2 + 16));
    else
      FreeCrlPreFetchEntry((_QWORD *)v2);
  }
}

```

## disassembly

```asm
0x180012f60  mov     rax, rcx
0x180012f63  xor     edx, edx
0x180012f65  mov     rcx, [rcx+90h]; hMem
0x180012f6c  test    rcx, rcx
0x180012f6f  jnz     short loc_180012F72
0x180012f71  retn
0x180012f72  cmp     cs:?g_fTVOAgentProcessExit@@3HA, edx; int g_fTVOAgentProcessExit
0x180012f78  mov     [rcx], rdx
0x180012f7b  mov     [rax+90h], rdx
0x180012f82  jnz     ?FreeCrlPreFetchEntry@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; FreeCrlPreFetchEntry(_CRL_PRE_FETCH_ENTRY *)
0x180012f88  mov     rcx, [rcx+10h]
0x180012f8c  jmp     cs:__imp_SubmitThreadpoolWork
```
