# CleanupJsonValue(JsonValue * *)

- ea: `0x180002f54`
- end: `0x180002fe9`
- name: `?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z`
- size: `149`
- prototype: `void __fastcall(struct JsonValue **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002e34`
- `0x180002ff0`
- `0x180005a6c`
- `0x180005ef4`
- `0x1800063a0`

## callees

- `0x180002eb0`
- `0x180002f54`
- `0x180002ff0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002f9c`
- `KERNEL32!GetProcessHeap` at `0x180002fc3`
- `KERNEL32!GetProcessHeap` at `0x180002f9c`
- `KERNEL32!GetProcessHeap` at `0x180002fc3`
- `KERNEL32!HeapFree` at `0x180002faa`
- `KERNEL32!HeapFree` at `0x180002fd1`
- `KERNEL32!HeapFree` at `0x180002faa`
- `KERNEL32!HeapFree` at `0x180002fd1`

## pseudocode

```c
void __fastcall CleanupJsonValue(struct JsonValue **a1)
{
  _QWORD *v1; // rdx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rdi
  HANDLE v6; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *(_DWORD *)v1 )
    {
      if ( *(_DWORD *)v1 == 4 )
      {
        CleanupJsonValueList(v1 + 1);
      }
      else if ( *(_DWORD *)v1 == 5 )
      {
        CleanupJsonObject(v1 + 1);
      }
    }
    else
    {
      v3 = (void *)v1[1];
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
        *((_QWORD *)*a1 + 1) = 0;
      }
    }
    v5 = *a1;
    if ( *a1 )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x180002f54  mov     [rsp+arg_0], rbx
0x180002f59  push    rdi
0x180002f5a  sub     rsp, 20h
0x180002f5e  mov     rdx, [rcx]
0x180002f61  mov     rbx, rcx
0x180002f64  test    rdx, rdx
0x180002f67  jz      short loc_180002FDE
0x180002f69  mov     r8d, [rdx]
0x180002f6c  test    r8d, r8d
0x180002f6f  jz      short loc_180002F93
0x180002f71  sub     r8d, 4
0x180002f75  jz      short loc_180002F88
0x180002f77  cmp     r8d, 1
0x180002f7b  jnz     short loc_180002FBB
0x180002f7d  lea     rcx, [rdx+8]
0x180002f81  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x180002f86  jmp     short loc_180002FBB
0x180002f88  lea     rcx, [rdx+8]
0x180002f8c  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x180002f91  jmp     short loc_180002FBB
0x180002f93  mov     rdi, [rdx+8]
0x180002f97  test    rdi, rdi
0x180002f9a  jz      short loc_180002FBB
0x180002f9c  call    cs:__imp_GetProcessHeap
0x180002fa2  mov     r8, rdi; lpMem
0x180002fa5  xor     edx, edx; dwFlags
0x180002fa7  mov     rcx, rax; hHeap
0x180002faa  call    cs:__imp_HeapFree
0x180002fb0  mov     rax, [rbx]
0x180002fb3  mov     qword ptr [rax+8], 0
0x180002fbb  mov     rdi, [rbx]
0x180002fbe  test    rdi, rdi
0x180002fc1  jz      short loc_180002FDE
0x180002fc3  call    cs:__imp_GetProcessHeap
0x180002fc9  mov     r8, rdi; lpMem
0x180002fcc  xor     edx, edx; dwFlags
0x180002fce  mov     rcx, rax; hHeap
0x180002fd1  call    cs:__imp_HeapFree
0x180002fd7  mov     qword ptr [rbx], 0
0x180002fde  mov     rbx, [rsp+28h+arg_0]
0x180002fe3  add     rsp, 20h
0x180002fe7  pop     rdi
0x180002fe8  retn
```
