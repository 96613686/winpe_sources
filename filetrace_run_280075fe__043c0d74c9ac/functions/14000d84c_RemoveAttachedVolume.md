# RemoveAttachedVolume

- ea: `0x14000d84c`
- end: `0x14000d8f5`
- name: `RemoveAttachedVolume`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d230`

## callees

- `0x14000d84c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8e0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d860`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d860`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d890`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d890`
- `FLTMGR!FltObjectDereference` at `0x14000d8ac`
- `FLTMGR!FltObjectDereference` at `0x14000d8ac`

## pseudocode

```c
void __fastcall RemoveAttachedVolume(PVOID *a1)
{
  PVOID *i; // rbx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rax

  ExAcquireFastMutex(&FastMutex);
  for ( i = (PVOID *)P; i != &P; i = (PVOID *)*i )
  {
    if ( i == a1 )
    {
      FltObjectDereference(i[2]);
      v3 = (_QWORD *)*((_QWORD *)*i + 1);
      v4 = *v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
        __fastfail(3u);
      *v5 = v4;
      *(_QWORD *)(v4 + 8) = v5;
      ExFreePoolWithTag(i, 0x72744C46u);
      break;
    }
  }
  ExReleaseFastMutex(&FastMutex);
}

```

## disassembly

```asm
0x14000d84c  mov     [rsp+arg_0], rbx
0x14000d851  push    rdi
0x14000d852  sub     rsp, 20h
0x14000d856  mov     rdi, rcx
0x14000d859  lea     rcx, FastMutex; FastMutex
0x14000d860  call    cs:__imp_ExAcquireFastMutex
0x14000d867  nop     dword ptr [rax+rax+00h]
0x14000d86c  mov     rbx, cs:P
0x14000d873  lea     rax, P
0x14000d87a  jmp     short loc_14000D884
0x14000d87c  cmp     rbx, rdi
0x14000d87f  jz      short loc_14000D8A8
0x14000d881  mov     rbx, [rbx]
0x14000d884  cmp     rbx, rax
0x14000d887  jnz     short loc_14000D87C
0x14000d889  lea     rcx, FastMutex; FastMutex
0x14000d890  call    cs:__imp_ExReleaseFastMutex
0x14000d897  nop     dword ptr [rax+rax+00h]
0x14000d89c  mov     rbx, [rsp+28h+arg_0]
0x14000d8a1  add     rsp, 20h
0x14000d8a5  pop     rdi
0x14000d8a6  retn
0x14000d8a8  mov     rcx, [rbx+10h]; FltObject
0x14000d8ac  call    cs:__imp_FltObjectDereference
0x14000d8b3  nop     dword ptr [rax+rax+00h]
0x14000d8b8  mov     rax, [rbx]
0x14000d8bb  mov     rcx, [rax+8]
0x14000d8bf  mov     rdx, [rcx]
0x14000d8c2  cmp     [rdx+8], rcx
0x14000d8c6  jnz     short loc_14000D8EE
0x14000d8c8  mov     rax, [rcx+8]
0x14000d8cc  cmp     [rax], rcx
0x14000d8cf  jnz     short loc_14000D8EE
0x14000d8d1  mov     [rax], rdx
0x14000d8d4  mov     rcx, rbx; P
0x14000d8d7  mov     [rdx+8], rax
0x14000d8db  mov     edx, 72744C46h; Tag
0x14000d8e0  call    cs:__imp_ExFreePoolWithTag
0x14000d8e7  nop     dword ptr [rax+rax+00h]
0x14000d8ec  jmp     short loc_14000D889
0x14000d8ee  mov     ecx, 3
0x14000d8f3  int     29h; Win8: RtlFailFast(ecx)
```
