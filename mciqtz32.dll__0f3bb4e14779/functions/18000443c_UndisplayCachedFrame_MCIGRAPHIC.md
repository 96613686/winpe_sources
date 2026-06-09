# UndisplayCachedFrame(_MCIGRAPHIC *)

- ea: `0x18000443c`
- end: `0x18000449e`
- name: `?UndisplayCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000485c`
- `0x180004e58`

## callees

- `0x180001e7c`
- `0x1800041fc`
- `0x180007010`

## pseudocode

```c
unsigned int __fastcall UndisplayCachedFrame(struct _MCIGRAPHIC *a1)
{
  int v2; // eax
  int v3; // ebx

  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 104LL))(*((_QWORD *)a1 + 22), 0xFFFFFFFFLL);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 152LL))(*((_QWORD *)a1 + 22), 0xFFFFFFFFLL);
  *((_DWORD *)a1 + 148) = 0;
  v3 = v2;
  ReleaseCachedFrame(a1);
  return CheckResult(v3);
}

```

## disassembly

```asm
0x18000443c  mov     [rsp+arg_0], rbx
0x180004441  push    rdi
0x180004442  sub     rsp, 20h
0x180004446  mov     rdi, rcx
0x180004449  or      ebx, 0FFFFFFFFh
0x18000444c  mov     rcx, [rcx+0B0h]
0x180004453  mov     edx, ebx
0x180004455  mov     rax, [rcx]
0x180004458  mov     rax, [rax+68h]
0x18000445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004461  mov     rcx, [rdi+0B0h]
0x180004468  mov     edx, ebx
0x18000446a  mov     rax, [rcx]
0x18000446d  mov     rax, [rax+98h]
0x180004474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004479  mov     rcx, rdi; struct _MCIGRAPHIC *
0x18000447c  mov     dword ptr [rdi+250h], 0
0x180004486  mov     ebx, eax
0x180004488  call    ?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; ReleaseCachedFrame(_MCIGRAPHIC *)
0x18000448d  mov     ecx, ebx; int
0x18000448f  mov     rbx, [rsp+28h+arg_0]
0x180004494  add     rsp, 20h
0x180004498  pop     rdi
0x180004499  jmp     ?CheckResult@@YAKJ@Z; CheckResult(long)
```
