# _Cnd_timedwait_for_impl

- ea: `0x1800236f8`
- end: `0x180023735`
- name: `_Cnd_timedwait_for_impl`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f148`

## callees

- `0x1800236d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002371c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002371c`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(struct _Cnd_internal_imp_t *a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // ebx
  DWORD CurrentThreadId; // eax

  --*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = -1;
  v4 = 2 * !_Primitive_wait_for(a1, (struct _Mtx_internal_imp_t *const)a2, a3);
  CurrentThreadId = GetCurrentThreadId();
  ++*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = CurrentThreadId;
  return v4;
}

```

## disassembly

```asm
0x1800236f8  mov     [rsp+arg_0], rbx
0x1800236fd  push    rdi
0x1800236fe  sub     rsp, 20h
0x180023702  dec     dword ptr [rdx+4Ch]
0x180023705  mov     rdi, rdx
0x180023708  mov     dword ptr [rdx+48h], 0FFFFFFFFh
0x18002370f  call    ?_Primitive_wait_for@@YA_NQEAU_Cnd_internal_imp_t@@QEAU_Mtx_internal_imp_t@@I@Z; _Primitive_wait_for(_Cnd_internal_imp_t * const,_Mtx_internal_imp_t * const,uint)
0x180023714  movzx   ebx, al
0x180023717  xor     ebx, 1
0x18002371a  add     ebx, ebx
0x18002371c  call    cs:__imp_GetCurrentThreadId
0x180023722  inc     dword ptr [rdi+4Ch]
0x180023725  mov     [rdi+48h], eax
0x180023728  mov     eax, ebx
0x18002372a  mov     rbx, [rsp+28h+arg_0]
0x18002372f  add     rsp, 20h
0x180023733  pop     rdi
0x180023734  retn
```
