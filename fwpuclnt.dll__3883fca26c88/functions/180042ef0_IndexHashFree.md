# IndexHashFree

- ea: `0x180042ef0`
- end: `0x180042f4c`
- name: `IndexHashFree`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000438c`
- `0x18000cde0`
- `0x180042b08`
- `0x180042ef0`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180042f12`
- `ntdll!RtlDeleteHashTable` at `0x180042f12`

## pseudocode

```c
__int64 __fastcall IndexHashFree(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  IndexHashEmpty(*(_QWORD *)(a1 + 56));
  RtlDeleteHashTable(*(_QWORD *)(a1 + 56));
  WfpCriticalSectionDestroy(a1);
  if ( a3 != -1 )
    WfpMemFree(a1 + 48);
  WfpMemFree(&v6);
  return 0;
}

```

## disassembly

```asm
0x180042ef0  mov     [rsp+arg_8], rbx
0x180042ef5  push    rdi
0x180042ef6  sub     rsp, 20h
0x180042efa  mov     rdi, rcx
0x180042efd  mov     [rsp+28h+arg_0], rcx
0x180042f02  mov     rcx, [rcx+38h]
0x180042f06  mov     ebx, r8d
0x180042f09  call    IndexHashEmpty
0x180042f0e  mov     rcx, [rdi+38h]
0x180042f12  call    cs:__imp_RtlDeleteHashTable
0x180042f19  nop     dword ptr [rax+rax+00h]
0x180042f1e  mov     rcx, rdi
0x180042f21  call    WfpCriticalSectionDestroy
0x180042f26  cmp     ebx, 0FFFFFFFFh
0x180042f29  jz      short loc_180042F34
0x180042f2b  lea     rcx, [rdi+30h]
0x180042f2f  call    WfpMemFree
0x180042f34  lea     rcx, [rsp+28h+arg_0]
0x180042f39  call    WfpMemFree
0x180042f3e  mov     rbx, [rsp+28h+arg_8]
0x180042f43  xor     eax, eax
0x180042f45  add     rsp, 20h
0x180042f49  pop     rdi
0x180042f4a  retn
```
