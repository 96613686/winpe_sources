# DereferenceVolumeContext

- ea: `0x18000f91c`
- end: `0x18000f968`
- name: `DereferenceVolumeContext`
- size: `76`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180008010`
- `0x1800084f4`
- `0x180008a60`
- `0x180008c10`
- `0x180008d60`
- `0x180009840`
- `0x18000a874`
- `0x18000aa48`
- `0x18000aecc`
- `0x18000bcc8`
- `0x18000c940`
- `0x18000cb40`
- `0x18000ce60`
- `0x18000eac0`
- `0x18000f2e8`
- `0x18000fc50`
- `0x180010e40`
- `0x180010fd0`
- `0x1800110c0`

## import_xrefs

- `FLTMGR!FltObjectDereference` at `0x18000f941`
- `FLTMGR!FltObjectDereference` at `0x18000f950`
- `FLTMGR!FltObjectDereference` at `0x18000f941`
- `FLTMGR!FltObjectDereference` at `0x18000f950`
- `FLTMGR!FltReleaseContext` at `0x18000f932`
- `FLTMGR!FltReleaseContext` at `0x18000f932`

## pseudocode

```c
void __fastcall DereferenceVolumeContext(__int64 a1)
{
  void *v1; // rdi
  void *v2; // rbx

  v1 = *(void **)(a1 + 72);
  v2 = *(void **)(a1 + 64);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 116));
  FltReleaseContext((PFLT_CONTEXT)a1);
  FltObjectDereference(v2);
  FltObjectDereference(v1);
}

```

## disassembly

```asm
0x18000f91c  mov     [rsp+arg_0], rbx
0x18000f921  push    rdi
0x18000f922  sub     rsp, 20h
0x18000f926  mov     rdi, [rcx+48h]
0x18000f92a  mov     rbx, [rcx+40h]
0x18000f92e  lock dec dword ptr [rcx+74h]
0x18000f932  call    cs:__imp_FltReleaseContext
0x18000f939  nop     dword ptr [rax+rax+00h]
0x18000f93e  mov     rcx, rbx; FltObject
0x18000f941  call    cs:__imp_FltObjectDereference
0x18000f948  nop     dword ptr [rax+rax+00h]
0x18000f94d  mov     rcx, rdi; FltObject
0x18000f950  call    cs:__imp_FltObjectDereference
0x18000f957  nop     dword ptr [rax+rax+00h]
0x18000f95c  mov     rbx, [rsp+28h+arg_0]
0x18000f961  add     rsp, 20h
0x18000f965  pop     rdi
0x18000f966  retn
```
