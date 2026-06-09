# ActiveScriptError::FreeStackTrace(CallStack &)

- ea: `0x18043b90c`
- end: `0x18043b98c`
- name: `?FreeStackTrace@ActiveScriptError@@CAXAEAUCallStack@@@Z`
- size: `128`
- prototype: `void __fastcall(struct CallStack *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1803ff528`
- `0x18043b714`

## callees

- `0x18043b90c`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043b94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043b969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043b94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043b969`

## pseudocode

```c
void __fastcall ActiveScriptError::FreeStackTrace(struct CallStack *a1)
{
  unsigned int v2; // esi
  LPVOID *i; // rbx
  __int64 v4; // rbp
  __int64 v5; // rcx

  v2 = 0;
  for ( i = (LPVOID *)((char *)a1 + 8); v2 < *(_DWORD *)a1; ++v2 )
  {
    v4 = 32LL * v2;
    v5 = *(_QWORD *)((char *)*i + v4 + 24);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    CoTaskMemFree(*(LPVOID *)((char *)*i + v4 + 8));
  }
  if ( *i )
    CoTaskMemFree(*i);
  *i = 0;
  *(_DWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18043b90c  mov     [rsp+arg_0], rcx
0x18043b911  push    rbx
0x18043b912  push    rbp
0x18043b913  push    rsi
0x18043b914  push    rdi
0x18043b915  sub     rsp, 28h
0x18043b919  mov     rdi, [rsp+48h+arg_0]
0x18043b91e  xor     esi, esi
0x18043b920  lea     rbx, [rdi+8]
0x18043b924  cmp     [rdi], esi
0x18043b926  jbe     short loc_18043B961
0x18043b928  mov     rax, [rbx]
0x18043b92b  mov     ebp, esi
0x18043b92d  shl     rbp, 5
0x18043b931  mov     rcx, [rax+rbp+18h]
0x18043b936  test    rcx, rcx
0x18043b939  jz      short loc_18043B947
0x18043b93b  mov     rax, [rcx]
0x18043b93e  mov     rax, [rax+10h]
0x18043b942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043b947  mov     rcx, [rbx]
0x18043b94a  mov     rcx, [rcx+rbp+8]; pv
0x18043b94f  call    cs:__imp_CoTaskMemFree
0x18043b956  nop     dword ptr [rax+rax+00h]
0x18043b95b  inc     esi
0x18043b95d  cmp     esi, [rdi]
0x18043b95f  jb      short loc_18043B928
0x18043b961  mov     rcx, [rbx]; pv
0x18043b964  test    rcx, rcx
0x18043b967  jz      short loc_18043B975
0x18043b969  call    cs:__imp_CoTaskMemFree
0x18043b970  nop     dword ptr [rax+rax+00h]
0x18043b975  mov     qword ptr [rbx], 0
0x18043b97c  mov     dword ptr [rdi], 0
0x18043b982  add     rsp, 28h
0x18043b986  pop     rdi
0x18043b987  pop     rsi
0x18043b988  pop     rbp
0x18043b989  pop     rbx
0x18043b98a  retn
```
