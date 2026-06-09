# SERVICES_MANAGER::ResetDependencies(void)

- ea: `0x140003cd8`
- end: `0x140003d15`
- name: `?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ`
- size: `61`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140003674`
- `0x140004114`
- `0x1400042d8`
- `0x140004628`

## callees

- `0x140001054`
- `0x140003cd8`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::ResetDependencies(SERVICES_MANAGER *this)
{
  unsigned int v1; // edi
  unsigned int v3; // eax
  __int64 v4; // rdx
  void *v5; // rcx

  v1 = *(_DWORD *)this;
  v3 = *((_DWORD *)this + 2);
  while ( v1 < v3 )
  {
    v4 = v3 - 1;
    v5 = *(void **)(*((_QWORD *)this + 6) + 8 * v4);
    *((_DWORD *)this + 2) = v4;
    operator delete(v5);
    v3 = *((_DWORD *)this + 2);
    ++v1;
  }
  return 0;
}

```

## disassembly

```asm
0x140003cd8  mov     [rsp+arg_0], rbx
0x140003cdd  push    rdi
0x140003cde  sub     rsp, 20h
0x140003ce2  mov     edi, [rcx]
0x140003ce4  mov     rbx, rcx
0x140003ce7  mov     eax, [rcx+8]
0x140003cea  jmp     short loc_140003D04
0x140003cec  lea     edx, [rax-1]
0x140003cef  mov     rax, [rbx+30h]
0x140003cf3  mov     rcx, [rax+rdx*8]; Block
0x140003cf7  mov     [rbx+8], edx
0x140003cfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003cff  mov     eax, [rbx+8]
0x140003d02  inc     edi
0x140003d04  cmp     edi, eax
0x140003d06  jb      short loc_140003CEC
0x140003d08  mov     rbx, [rsp+28h+arg_0]
0x140003d0d  xor     eax, eax
0x140003d0f  add     rsp, 20h
0x140003d13  pop     rdi
0x140003d14  retn
```
