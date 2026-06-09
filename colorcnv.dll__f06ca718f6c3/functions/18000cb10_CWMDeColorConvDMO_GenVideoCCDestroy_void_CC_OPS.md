# CWMDeColorConvDMO::GenVideoCCDestroy(void * *,CC_OPS)

- ea: `0x18000cb10`
- end: `0x18000cba7`
- name: `?GenVideoCCDestroy@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800040b0`
- `0x18000828c`
- `0x18000c760`
- `0x18000cbb0`
- `0x18000e160`

## callees

- `0x18000a6d0`
- `0x18000cb10`
- `0x18001005c`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::GenVideoCCDestroy(__int64 a1, struct DIRECTCOLORCONVFRM **a2, int a3)
{
  struct DIRECTCOLORCONVFRM *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx

  if ( a3 )
  {
    if ( a3 != 2 )
      return 2147500037LL;
    v5 = *a2;
    FinishThreads(*a2);
    if ( *(_QWORD *)v5 )
    {
      operator delete(*(void **)v5);
      *(_QWORD *)v5 = 0;
    }
    v6 = (void *)*((_QWORD *)v5 + 1);
    if ( v6 )
    {
      operator delete(v6);
      *((_QWORD *)v5 + 1) = 0;
    }
    v7 = (void *)*((_QWORD *)v5 + 14);
    if ( v7 )
    {
      operator delete(v7);
      *((_QWORD *)v5 + 14) = 0;
      *((_DWORD *)v5 + 30) = 0;
    }
    if ( v5 )
      operator delete(v5);
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000cb10  mov     [rsp+arg_0], rbx
0x18000cb15  push    rdi
0x18000cb16  sub     rsp, 20h
0x18000cb1a  mov     rdi, rdx
0x18000cb1d  test    r8d, r8d
0x18000cb20  jz      short loc_18000CB93
0x18000cb22  cmp     r8d, 2
0x18000cb26  jz      short loc_18000CB2F
0x18000cb28  mov     eax, 80004005h
0x18000cb2d  jmp     short loc_18000CB9C
0x18000cb2f  mov     rbx, [rdx]
0x18000cb32  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x18000cb35  call    ?FinishThreads@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; FinishThreads(DIRECTCOLORCONVFRM *)
0x18000cb3a  mov     rcx, [rbx]; void *
0x18000cb3d  test    rcx, rcx
0x18000cb40  jz      short loc_18000CB4E
0x18000cb42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cb47  mov     qword ptr [rbx], 0
0x18000cb4e  mov     rcx, [rbx+8]; void *
0x18000cb52  test    rcx, rcx
0x18000cb55  jz      short loc_18000CB64
0x18000cb57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cb5c  mov     qword ptr [rbx+8], 0
0x18000cb64  mov     rcx, [rbx+70h]; void *
0x18000cb68  test    rcx, rcx
0x18000cb6b  jz      short loc_18000CB81
0x18000cb6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cb72  mov     qword ptr [rbx+70h], 0
0x18000cb7a  mov     dword ptr [rbx+78h], 0
0x18000cb81  test    rbx, rbx
0x18000cb84  jz      short loc_18000CB93
0x18000cb86  mov     edx, 3C58h; unsigned __int64
0x18000cb8b  mov     rcx, rbx; void *
0x18000cb8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cb93  mov     qword ptr [rdi], 0
0x18000cb9a  xor     eax, eax
0x18000cb9c  mov     rbx, [rsp+28h+arg_0]
0x18000cba1  add     rsp, 20h
0x18000cba5  pop     rdi
0x18000cba6  retn
```
