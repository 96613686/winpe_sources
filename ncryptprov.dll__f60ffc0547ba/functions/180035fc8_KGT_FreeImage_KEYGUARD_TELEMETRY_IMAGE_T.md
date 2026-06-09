# KGT_FreeImage(KEYGUARD_TELEMETRY_IMAGE_T *)

- ea: `0x180035fc8`
- end: `0x180036009`
- name: `?KGT_FreeImage@@YAXPEAUKEYGUARD_TELEMETRY_IMAGE_T@@@Z`
- size: `65`
- prototype: `void __fastcall(struct KEYGUARD_TELEMETRY_IMAGE_T *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b754`
- `0x180040040`

## callees

- `0x180035fc8`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180035fd5`
- `ntdll!RtlDeleteCriticalSection` at `0x180035fd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ffd`

## pseudocode

```c
void __fastcall KGT_FreeImage(struct KEYGUARD_TELEMETRY_IMAGE_T *a1)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  if ( *(_QWORD *)a1 )
    LocalFree(*(HLOCAL *)a1);
  LocalFree(a1);
}

```

## disassembly

```asm
0x180035fc8  push    rbx
0x180035fca  sub     rsp, 20h
0x180035fce  mov     rbx, rcx
0x180035fd1  add     rcx, 18h; CriticalSection
0x180035fd5  call    cs:__imp_RtlDeleteCriticalSection
0x180035fdc  nop     dword ptr [rax+rax+00h]
0x180035fe1  mov     rcx, [rbx]; hMem
0x180035fe4  test    rcx, rcx
0x180035fe7  jz      short loc_180035FF5
0x180035fe9  call    cs:__imp_LocalFree
0x180035ff0  nop     dword ptr [rax+rax+00h]
0x180035ff5  mov     rcx, rbx
0x180035ff8  add     rsp, 20h
0x180035ffc  pop     rbx
0x180035ffd  jmp     cs:__imp_LocalFree
```
