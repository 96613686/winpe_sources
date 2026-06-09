# CleanupJsonKeyValuePair(JsonKeyValuePair * *)

- ea: `0x180002e34`
- end: `0x180002ea9`
- name: `?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z`
- size: `117`
- prototype: `void __fastcall(struct JsonKeyValuePair **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002eb0`
- `0x180005a6c`

## callees

- `0x180002e34`
- `0x180002f54`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002e51`
- `KERNEL32!GetProcessHeap` at `0x180002e83`
- `KERNEL32!GetProcessHeap` at `0x180002e51`
- `KERNEL32!GetProcessHeap` at `0x180002e83`
- `KERNEL32!HeapFree` at `0x180002e5f`
- `KERNEL32!HeapFree` at `0x180002e91`
- `KERNEL32!HeapFree` at `0x180002e5f`
- `KERNEL32!HeapFree` at `0x180002e91`

## pseudocode

```c
void __fastcall CleanupJsonKeyValuePair(void ***a1)
{
  void **v1; // rax
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  void **v5; // rdi
  HANDLE v6; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *v1;
    if ( *v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      **a1 = 0;
    }
    CleanupJsonValue((struct JsonValue **)*a1 + 1);
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
0x180002e34  mov     [rsp+arg_0], rbx
0x180002e39  push    rdi
0x180002e3a  sub     rsp, 20h
0x180002e3e  mov     rax, [rcx]
0x180002e41  mov     rbx, rcx
0x180002e44  test    rax, rax
0x180002e47  jz      short loc_180002E9E
0x180002e49  mov     rdi, [rax]
0x180002e4c  test    rdi, rdi
0x180002e4f  jz      short loc_180002E6F
0x180002e51  call    cs:__imp_GetProcessHeap
0x180002e57  mov     r8, rdi; lpMem
0x180002e5a  xor     edx, edx; dwFlags
0x180002e5c  mov     rcx, rax; hHeap
0x180002e5f  call    cs:__imp_HeapFree
0x180002e65  mov     rax, [rbx]
0x180002e68  mov     qword ptr [rax], 0
0x180002e6f  mov     rcx, [rbx]
0x180002e72  add     rcx, 8; struct JsonValue **
0x180002e76  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180002e7b  mov     rdi, [rbx]
0x180002e7e  test    rdi, rdi
0x180002e81  jz      short loc_180002E9E
0x180002e83  call    cs:__imp_GetProcessHeap
0x180002e89  mov     r8, rdi; lpMem
0x180002e8c  xor     edx, edx; dwFlags
0x180002e8e  mov     rcx, rax; hHeap
0x180002e91  call    cs:__imp_HeapFree
0x180002e97  mov     qword ptr [rbx], 0
0x180002e9e  mov     rbx, [rsp+28h+arg_0]
0x180002ea3  add     rsp, 20h
0x180002ea7  pop     rdi
0x180002ea8  retn
```
