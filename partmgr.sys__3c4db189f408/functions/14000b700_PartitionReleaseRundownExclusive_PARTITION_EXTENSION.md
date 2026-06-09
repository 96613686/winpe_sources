# PartitionReleaseRundownExclusive(_PARTITION_EXTENSION *)

- ea: `0x14000b700`
- end: `0x14000b883`
- name: `?PartitionReleaseRundownExclusive@@YAXPEAU_PARTITION_EXTENSION@@@Z`
- size: `387`
- prototype: `void __fastcall(struct _PARTITION_EXTENSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007f70`
- `0x14000c47c`

## callees

- `0x14000b700`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b7f6`
- `ntoskrnl!KeSetEvent` at `0x14000b7f6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b7de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b7de`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14000b739`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14000b739`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b750`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b750`
- `ntoskrnl!KeReleaseMutex` at `0x14000b80b`
- `ntoskrnl!KeReleaseMutex` at `0x14000b80b`

## pseudocode

```c
void __fastcall PartitionReleaseRundownExclusive(struct _PARTITION_EXTENSION *a1)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v2; // rcx
  char **v3; // rdx
  char *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 i; // rdi
  __int64 *v8; // rdx
  __int64 *v9; // rax
  __int64 *v10; // [rsp+20h] [rbp-30h] BYREF
  char **v11; // [rsp+28h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF

  v2 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 50);
  v11 = (char **)&v10;
  v10 = (__int64 *)&v10;
  memset(&LockHandle, 0, sizeof(LockHandle));
  ExReInitializeRundownProtectionCacheAware(v2);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 56, &LockHandle);
  if ( (__int64 **)v10[1] != &v10
    || (v3 = v11, *v11 != (char *)&v10)
    || (v4 = (char *)a1 + 432,
        *(struct _PARTITION_EXTENSION **)(*((_QWORD *)a1 + 54) + 8LL) != (struct _PARTITION_EXTENSION *)((char *)a1 + 432))
    || **((char ***)a1 + 55) != v4
    || (*v11 = v4,
        v11 = (char **)*((_QWORD *)a1 + 55),
        *v11 = (char *)&v10,
        *((_QWORD *)a1 + 55) = v3,
        v5 = *(_QWORD *)v4,
        *(char **)(*(_QWORD *)v4 + 8LL) != v4)
    || *v3 != v4 )
  {
LABEL_12:
    __fastfail(3u);
  }
  *v3 = (char *)v5;
  *(_QWORD *)(v5 + 8) = v3;
  *((_QWORD *)a1 + 55) = (char *)a1 + 432;
  *(_QWORD *)v4 = v4;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  KeSetEvent((PRKEVENT)a1 + 17, 0, 0);
  KeReleaseMutex((PRKMUTEX)((char *)a1 + 344), 0);
  v6 = *((_QWORD *)a1 + 1);
  for ( i = *(_QWORD *)(v6 + 8); ; (*(void (__fastcall **)(__int64))(i + 8LL * *(unsigned __int8 *)v8[2] + 112))(v6) )
  {
    v8 = v10;
    if ( v10 == (__int64 *)&v10 )
      break;
    if ( (__int64 **)v10[1] != &v10 )
      goto LABEL_12;
    v9 = (__int64 *)*v10;
    if ( *(__int64 **)(*v10 + 8) != v10 )
      goto LABEL_12;
    v10 = (__int64 *)*v10;
    v9[1] = (__int64)&v10;
  }
}

```

## disassembly

```asm
0x14000b700  mov     [rsp-8+arg_0], rbx
0x14000b705  mov     [rsp-8+arg_8], rdi
0x14000b70a  push    rbp
0x14000b70b  mov     rbp, rsp
0x14000b70e  sub     rsp, 50h
0x14000b712  xor     eax, eax
0x14000b714  mov     rbx, rcx
0x14000b717  mov     rcx, [rcx+190h]; RunRefCacheAware
0x14000b71e  xorps   xmm0, xmm0
0x14000b721  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000b725  lea     rax, [rbp+var_30]
0x14000b729  mov     [rbp+var_28], rax
0x14000b72d  lea     rax, [rbp+var_30]
0x14000b731  mov     [rbp+var_30], rax
0x14000b735  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000b739  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14000b740  nop     dword ptr [rax+rax+00h]
0x14000b745  lea     rcx, [rbx+1C0h]; SpinLock
0x14000b74c  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000b750  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000b757  nop     dword ptr [rax+rax+00h]
0x14000b75c  mov     rax, [rbp+var_30]
0x14000b760  lea     rcx, [rbp+var_30]
0x14000b764  cmp     [rax+8], rcx
0x14000b768  jnz     loc_14000B86B
0x14000b76e  mov     rdx, [rbp+var_28]
0x14000b772  lea     rax, [rbp+var_30]
0x14000b776  cmp     [rdx], rax
0x14000b779  jnz     loc_14000B86B
0x14000b77f  lea     rcx, [rbx+1B0h]
0x14000b786  mov     rax, [rcx]
0x14000b789  cmp     [rax+8], rcx
0x14000b78d  jnz     loc_14000B86B
0x14000b793  mov     rax, [rcx+8]
0x14000b797  cmp     [rax], rcx
0x14000b79a  jnz     loc_14000B86B
0x14000b7a0  mov     [rdx], rcx
0x14000b7a3  lea     r8, [rbp+var_30]
0x14000b7a7  mov     rax, [rcx+8]
0x14000b7ab  mov     [rbp+var_28], rax
0x14000b7af  mov     [rax], r8
0x14000b7b2  mov     [rcx+8], rdx
0x14000b7b6  mov     rax, [rcx]
0x14000b7b9  cmp     [rax+8], rcx
0x14000b7bd  jnz     loc_14000B86B
0x14000b7c3  cmp     [rdx], rcx
0x14000b7c6  jnz     loc_14000B86B
0x14000b7cc  mov     [rdx], rax
0x14000b7cf  mov     [rax+8], rdx
0x14000b7d3  mov     [rcx+8], rcx
0x14000b7d7  mov     [rcx], rcx
0x14000b7da  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000b7de  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000b7e5  nop     dword ptr [rax+rax+00h]
0x14000b7ea  lea     rcx, [rbx+198h]; Event
0x14000b7f1  xor     r8d, r8d; Wait
0x14000b7f4  xor     edx, edx; Increment
0x14000b7f6  call    cs:__imp_KeSetEvent
0x14000b7fd  nop     dword ptr [rax+rax+00h]
0x14000b802  lea     rcx, [rbx+158h]; Mutex
0x14000b809  xor     edx, edx; Wait
0x14000b80b  call    cs:__imp_KeReleaseMutex
0x14000b812  nop     dword ptr [rax+rax+00h]
0x14000b817  mov     rbx, [rbx+8]
0x14000b81b  mov     rdi, [rbx+8]
0x14000b81f  mov     rdx, [rbp+var_30]
0x14000b823  lea     rax, [rbp+var_30]
0x14000b827  cmp     rdx, rax
0x14000b82a  jz      short loc_14000B872
0x14000b82c  lea     rax, [rbp+var_30]
0x14000b830  cmp     [rdx+8], rax
0x14000b834  jnz     short loc_14000B86B
0x14000b836  mov     rax, [rdx]
0x14000b839  cmp     [rax+8], rdx
0x14000b83d  jnz     short loc_14000B86B
0x14000b83f  mov     [rbp+var_30], rax
0x14000b843  lea     rcx, [rbp+var_30]
0x14000b847  mov     [rax+8], rcx
0x14000b84b  add     rdx, 0FFFFFFFFFFFFFF58h
0x14000b852  mov     rax, [rdx+0B8h]
0x14000b859  movzx   ecx, byte ptr [rax]
0x14000b85c  mov     rax, [rdi+rcx*8+70h]
0x14000b861  mov     rcx, rbx
0x14000b864  call    _guard_dispatch_icall
0x14000b869  jmp     short loc_14000B81F
0x14000b86b  mov     ecx, 3
0x14000b870  int     29h; Win8: RtlFailFast(ecx)
0x14000b872  mov     rbx, [rsp+50h+arg_0]
0x14000b877  mov     rdi, [rsp+50h+arg_8]
0x14000b87c  add     rsp, 50h
0x14000b880  pop     rbp
0x14000b881  retn
```
