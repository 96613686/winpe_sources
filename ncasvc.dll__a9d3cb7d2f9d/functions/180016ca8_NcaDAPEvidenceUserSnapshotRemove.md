# NcaDAPEvidenceUserSnapshotRemove

- ea: `0x180016ca8`
- end: `0x180016d31`
- name: `NcaDAPEvidenceUserSnapshotRemove`
- size: `137`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017610`
- `0x180017bc8`

## callees

- `0x180015e80`
- `0x180016ca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016cbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016cbb`

## pseudocode

```c
void __fastcall NcaDAPEvidenceUserSnapshotRemove(int a1)
{
  struct NCA_DAP_USER_EVSNPSHT_ *i; // rax
  struct NCA_DAP_USER_EVSNPSHT_ *v3; // rbx
  struct NCA_DAP_USER_EVSNPSHT_ *v4; // rcx
  struct NCA_DAP_USER_EVSNPSHT_ **v5; // rdx

  EnterCriticalSection(&gNcaDapEvSnpshot);
  for ( i = qword_180029528; ; i = *(struct NCA_DAP_USER_EVSNPSHT_ **)i )
  {
    v3 = 0;
    if ( i == (struct NCA_DAP_USER_EVSNPSHT_ *)&qword_180029528 )
      break;
    v3 = i;
    v4 = *(struct NCA_DAP_USER_EVSNPSHT_ **)i;
    if ( *((_DWORD *)i + 153) == a1 )
    {
      if ( *((struct NCA_DAP_USER_EVSNPSHT_ **)v4 + 1) != i
        || (v5 = (struct NCA_DAP_USER_EVSNPSHT_ **)*((_QWORD *)i + 1), *v5 != i) )
      {
        __fastfail(3u);
      }
      *v5 = v4;
      *((_QWORD *)v4 + 1) = v5;
      break;
    }
  }
  LeaveCriticalSection(&gNcaDapEvSnpshot);
  NcaDAPEvidenceUserSnapshotDestroy(v3);
}

```

## disassembly

```asm
0x180016ca8  mov     [rsp+arg_0], rbx
0x180016cad  push    rdi
0x180016cae  sub     rsp, 20h
0x180016cb2  mov     edi, ecx
0x180016cb4  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180016cbb  call    cs:__imp_EnterCriticalSection
0x180016cc2  nop     dword ptr [rax+rax+00h]
0x180016cc7  mov     rax, cs:qword_180029528
0x180016cce  xor     ebx, ebx
0x180016cd0  lea     rcx, qword_180029528
0x180016cd7  cmp     rax, rcx
0x180016cda  jz      short loc_180016D05
0x180016cdc  mov     rbx, rax
0x180016cdf  mov     rcx, [rax]
0x180016ce2  cmp     [rax+264h], edi
0x180016ce8  jz      short loc_180016CEF
0x180016cea  mov     rax, rcx
0x180016ced  jmp     short loc_180016CCE
0x180016cef  cmp     [rcx+8], rax
0x180016cf3  jnz     short loc_180016D2A
0x180016cf5  mov     rdx, [rax+8]
0x180016cf9  cmp     [rdx], rax
0x180016cfc  jnz     short loc_180016D2A
0x180016cfe  mov     [rdx], rcx
0x180016d01  mov     [rcx+8], rdx
0x180016d05  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180016d0c  call    cs:__imp_LeaveCriticalSection
0x180016d13  nop     dword ptr [rax+rax+00h]
0x180016d18  mov     rcx, rbx; lpMem
0x180016d1b  mov     rbx, [rsp+28h+arg_0]
0x180016d20  add     rsp, 20h
0x180016d24  pop     rdi
0x180016d25  jmp     ?NcaDAPEvidenceUserSnapshotDestroy@@YAXPEAUNCA_DAP_USER_EVSNPSHT_@@@Z; NcaDAPEvidenceUserSnapshotDestroy(NCA_DAP_USER_EVSNPSHT_ *)
0x180016d2a  mov     ecx, 3
0x180016d2f  int     29h; Win8: RtlFailFast(ecx)
```
