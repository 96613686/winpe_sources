# EtwpFreeBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x180010c00`
- end: `0x180010c53`
- name: `?EtwpFreeBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `83`
- prototype: `void __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000416c`
- `0x180007b30`
- `0x18000ece4`
- `0x18000f384`

## callees

- `0x180010c00`
- `0x180010c5c`
- `0x180016010`

## pseudocode

```c
void __fastcall EtwpFreeBuffer(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  char v3; // cl
  signed __int64 *v4; // rdx
  signed __int64 v5; // rax

  v3 = *((_BYTE *)a1 + 552);
  if ( v3 )
  {
    if ( v3 == 1 )
      EtwpFreeRtBuffer(a1, a2);
    else
      (*((void (__fastcall **)(struct _WMI_BUFFER_HEADER *, _QWORD))a1 + 123))(a2, *((_QWORD *)a1 + 124));
  }
  else
  {
    v4 = (signed __int64 *)((char *)a2 + 32);
    do
    {
      v5 = *((_QWORD *)a1 + 120);
      *v4 = v5;
    }
    while ( v5 != _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 120, (signed __int64)v4, v5) );
  }
}

```

## disassembly

```asm
0x180010c00  mov     r8, rcx
0x180010c03  mov     rax, rdx
0x180010c06  mov     cl, [rcx+228h]
0x180010c0c  test    cl, cl
0x180010c0e  jnz     short loc_180010C30
0x180010c10  add     rdx, 20h ; ' '; struct _WMI_BUFFER_HEADER *
0x180010c14  mov     rax, [r8+3C0h]
0x180010c1b  mov     [rdx], rax
0x180010c1e  mov     rcx, rax
0x180010c21  lock cmpxchg [r8+3C0h], rdx
0x180010c2a  cmp     rcx, rax
0x180010c2d  jnz     short loc_180010C14
0x180010c2f  retn
0x180010c30  cmp     cl, 1
0x180010c33  jnz     short loc_180010C3D
0x180010c35  mov     rcx, r8; struct _TRACELOG_CONTEXT *
0x180010c38  jmp     ?EtwpFreeRtBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpFreeRtBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180010c3d  mov     rdx, [r8+3E0h]
0x180010c44  mov     rcx, rax
0x180010c47  mov     rax, [r8+3D8h]
0x180010c4e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
