# CArray<IDiskQuotaUser *>::~CArray<IDiskQuotaUser *>(void)

- ea: `0x180007698`
- end: `0x1800076f8`
- name: `??1?$CArray@PEAUIDiskQuotaUser@@@@UEAA@XZ`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d30`
- `0x18000c8c4`
- `0x18001d702`

## callees

- `0x180007698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800076f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076c5`

## pseudocode

```c
void __fastcall CArray<IDiskQuotaUser *>::~CArray<IDiskQuotaUser *>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  void *v3; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  *(_QWORD *)a1 = &CArray<IDiskQuotaUser *>::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v3 = *(void **)(a1 + 24);
  if ( v3 )
    LocalFree(v3);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x180007698  mov     [rsp+arg_0], rbx
0x18000769d  push    rdi
0x18000769e  sub     rsp, 20h
0x1800076a2  lea     rax, ??_7?$CArray@PEAUIDiskQuotaUser@@@@6B@; const CArray<IDiskQuotaUser *>::`vftable'
0x1800076a9  mov     rbx, rcx
0x1800076ac  lea     rdi, [rcx+20h]
0x1800076b0  mov     [rcx], rax
0x1800076b3  mov     rcx, rdi; lpCriticalSection
0x1800076b6  call    cs:__imp_EnterCriticalSection
0x1800076bc  mov     rcx, [rbx+18h]; hMem
0x1800076c0  test    rcx, rcx
0x1800076c3  jz      short loc_1800076CB
0x1800076c5  call    cs:__imp_LocalFree
0x1800076cb  mov     rcx, rdi; lpCriticalSection
0x1800076ce  mov     qword ptr [rbx+18h], 0
0x1800076d6  mov     qword ptr [rbx+8], 0
0x1800076de  call    cs:__imp_LeaveCriticalSection
0x1800076e4  mov     rcx, rdi
0x1800076e7  mov     rbx, [rsp+28h+arg_0]
0x1800076ec  add     rsp, 20h
0x1800076f0  pop     rdi
0x1800076f1  jmp     cs:__imp_DeleteCriticalSection
```
