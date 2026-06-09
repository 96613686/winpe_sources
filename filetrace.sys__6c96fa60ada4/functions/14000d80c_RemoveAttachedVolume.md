# RemoveAttachedVolume

- ea: `0x14000d80c`
- end: `0x14000d8b5`
- name: `RemoveAttachedVolume`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d1f0`

## callees

- `0x14000d80c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d8a0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d820`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d820`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d850`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d850`
- `FLTMGR!FltObjectDereference` at `0x14000d86c`
- `FLTMGR!FltObjectDereference` at `0x14000d86c`

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
0x14000d80c  mov     [rsp+arg_0], rbx
0x14000d811  push    rdi
0x14000d812  sub     rsp, 20h
0x14000d816  mov     rdi, rcx
0x14000d819  lea     rcx, FastMutex; FastMutex
0x14000d820  call    cs:__imp_ExAcquireFastMutex
0x14000d827  nop     dword ptr [rax+rax+00h]
0x14000d82c  mov     rbx, cs:P
0x14000d833  lea     rax, P
0x14000d83a  jmp     short loc_14000D844
0x14000d83c  cmp     rbx, rdi
0x14000d83f  jz      short loc_14000D868
0x14000d841  mov     rbx, [rbx]
0x14000d844  cmp     rbx, rax
0x14000d847  jnz     short loc_14000D83C
0x14000d849  lea     rcx, FastMutex; FastMutex
0x14000d850  call    cs:__imp_ExReleaseFastMutex
0x14000d857  nop     dword ptr [rax+rax+00h]
0x14000d85c  mov     rbx, [rsp+28h+arg_0]
0x14000d861  add     rsp, 20h
0x14000d865  pop     rdi
0x14000d866  retn
0x14000d868  mov     rcx, [rbx+10h]; FltObject
0x14000d86c  call    cs:__imp_FltObjectDereference
0x14000d873  nop     dword ptr [rax+rax+00h]
0x14000d878  mov     rax, [rbx]
0x14000d87b  mov     rcx, [rax+8]
0x14000d87f  mov     rdx, [rcx]
0x14000d882  cmp     [rdx+8], rcx
0x14000d886  jnz     short loc_14000D8AE
0x14000d888  mov     rax, [rcx+8]
0x14000d88c  cmp     [rax], rcx
0x14000d88f  jnz     short loc_14000D8AE
0x14000d891  mov     [rax], rdx
0x14000d894  mov     rcx, rbx; P
0x14000d897  mov     [rdx+8], rax
0x14000d89b  mov     edx, 72744C46h; Tag
0x14000d8a0  call    cs:__imp_ExFreePoolWithTag
0x14000d8a7  nop     dword ptr [rax+rax+00h]
0x14000d8ac  jmp     short loc_14000D849
0x14000d8ae  mov     ecx, 3
0x14000d8b3  int     29h; Win8: RtlFailFast(ecx)
```
