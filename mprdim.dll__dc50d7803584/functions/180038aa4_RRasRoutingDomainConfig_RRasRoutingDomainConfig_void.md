# RRasRoutingDomainConfig::~RRasRoutingDomainConfig(void)

- ea: `0x180038aa4`
- end: `0x180038af9`
- name: `??1RRasRoutingDomainConfig@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180038bc0`

## callees

- `0x180038aa4`
- `0x180038eb8`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180038af2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ad0`
- `KERNEL32!GetProcessHeap` at `0x180038ac2`
- `KERNEL32!GetProcessHeap` at `0x180038ac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RRasRoutingDomainConfig::~RRasRoutingDomainConfig(RRasRoutingDomainConfig *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  RRasRoutingDomainConfig::CloseConfigRegKey(this);
  v2 = (void *)*((_QWORD *)this + 74);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_QWORD *)this + 74) = 0;
  }
  RtlDeleteResource((PRTL_RESOURCE)((char *)this + 728));
}

```

## disassembly

```asm
0x180038aa4  mov     [rsp+arg_0], rbx
0x180038aa9  push    rdi
0x180038aaa  sub     rsp, 20h
0x180038aae  mov     rbx, rcx
0x180038ab1  call    ?CloseConfigRegKey@RRasRoutingDomainConfig@@AEAAXXZ; RRasRoutingDomainConfig::CloseConfigRegKey(void)
0x180038ab6  mov     rdi, [rbx+250h]
0x180038abd  test    rdi, rdi
0x180038ac0  jz      short loc_180038AE1
0x180038ac2  call    cs:__imp_GetProcessHeap
0x180038ac8  mov     r8, rdi; lpMem
0x180038acb  xor     edx, edx; dwFlags
0x180038acd  mov     rcx, rax; hHeap
0x180038ad0  call    cs:__imp_HeapFree
0x180038ad6  mov     qword ptr [rbx+250h], 0
0x180038ae1  lea     rcx, [rbx+2D8h]
0x180038ae8  mov     rbx, [rsp+28h+arg_0]
0x180038aed  add     rsp, 20h
0x180038af1  pop     rdi
0x180038af2  jmp     cs:__imp_RtlDeleteResource
```
