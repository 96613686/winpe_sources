# P<UserSecurityContext>::~P<UserSecurityContext>(void)

- ea: `0x1800176d4`
- end: `0x1800176f6`
- name: `??1?$P@VUserSecurityContext@@@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017728`
- `0x18001b088`
- `0x180024e5c`
- `0x180025107`

## callees

- `0x1800176d4`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall P<UserSecurityContext>::~P<UserSecurityContext>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 24LL))(v1, 1);
  return result;
}

```

## disassembly

```asm
0x1800176d4  sub     rsp, 28h
0x1800176d8  mov     rcx, [rcx]
0x1800176db  test    rcx, rcx
0x1800176de  jz      short loc_1800176F1
0x1800176e0  mov     rax, [rcx]
0x1800176e3  mov     edx, 1
0x1800176e8  mov     rax, [rax+18h]
0x1800176ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176f1  add     rsp, 28h
0x1800176f5  retn
```
