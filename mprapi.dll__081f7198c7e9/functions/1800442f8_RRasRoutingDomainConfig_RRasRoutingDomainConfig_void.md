# RRasRoutingDomainConfig::~RRasRoutingDomainConfig(void)

- ea: `0x1800442f8`
- end: `0x180044365`
- name: `??1RRasRoutingDomainConfig@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18004467c`
- `0x180046ea8`
- `0x180049728`

## callees

- `0x1800442f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004432e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004432e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004433c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004433c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044311`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044311`
- `ntdll!RtlDeleteResource` at `0x18004435e`

## pseudocode

```c
void __fastcall RRasRoutingDomainConfig::~RRasRoutingDomainConfig(RRasRoutingDomainConfig *this)
{
  HKEY v2; // rcx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax

  v2 = (HKEY)*((_QWORD *)this + 103);
  if ( v2 )
  {
    RegCloseKey(v2);
    *((_QWORD *)this + 103) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 74);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)this + 74) = 0;
  }
  RtlDeleteResource((PRTL_RESOURCE)((char *)this + 728));
}

```

## disassembly

```asm
0x1800442f8  mov     [rsp+arg_0], rbx
0x1800442fd  push    rdi
0x1800442fe  sub     rsp, 20h
0x180044302  mov     rbx, rcx
0x180044305  mov     rcx, [rcx+338h]; hKey
0x18004430c  test    rcx, rcx
0x18004430f  jz      short loc_180044322
0x180044311  call    cs:__imp_RegCloseKey
0x180044317  mov     qword ptr [rbx+338h], 0
0x180044322  mov     rdi, [rbx+250h]
0x180044329  test    rdi, rdi
0x18004432c  jz      short loc_18004434D
0x18004432e  call    cs:__imp_GetProcessHeap
0x180044334  mov     r8, rdi; lpMem
0x180044337  xor     edx, edx; dwFlags
0x180044339  mov     rcx, rax; hHeap
0x18004433c  call    cs:__imp_HeapFree
0x180044342  mov     qword ptr [rbx+250h], 0
0x18004434d  lea     rcx, [rbx+2D8h]
0x180044354  mov     rbx, [rsp+28h+arg_0]
0x180044359  add     rsp, 20h
0x18004435d  pop     rdi
0x18004435e  jmp     cs:__imp_RtlDeleteResource
```
