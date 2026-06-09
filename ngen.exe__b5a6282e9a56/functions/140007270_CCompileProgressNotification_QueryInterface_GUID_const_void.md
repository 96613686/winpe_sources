# CCompileProgressNotification::QueryInterface(_GUID const &,void * *)

- ea: `0x140007270`
- end: `0x1400072eb`
- name: `?QueryInterface@CCompileProgressNotification@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `123`
- prototype: `__int64 __fastcall(CCompileProgressNotification *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a040`
- `0x14000a050`

## callees

- `0x140007270`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::QueryInterface(
        CCompileProgressNotification *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_ICompileProgressNotification2
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = (void *)(((unsigned __int64)this + 16) & -(__int64)(this != 0));
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ICompileProgressNotification.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ICompileProgressNotification.Data4 )
  {
    *a3 = this;
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x140007270  mov     r9, rcx
0x140007273  test    r8, r8
0x140007276  jnz     short loc_14000727E
0x140007278  mov     eax, 80004003h
0x14000727d  retn
0x14000727e  and     qword ptr [r8], 0
0x140007282  mov     rax, [rdx]
0x140007285  cmp     rax, qword ptr cs:IID_ICompileProgressNotification2.Data1
0x14000728c  jnz     short loc_14000729B
0x14000728e  mov     rax, [rdx+8]
0x140007292  cmp     rax, qword ptr cs:IID_ICompileProgressNotification2.Data4
0x140007299  jz      short loc_1400072B4
0x14000729b  mov     rax, [rdx]
0x14000729e  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1400072a5  jnz     short loc_1400072C6
0x1400072a7  mov     rax, [rdx+8]
0x1400072ab  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1400072b2  jnz     short loc_1400072C6
0x1400072b4  add     rcx, 10h
0x1400072b8  neg     r9
0x1400072bb  sbb     rax, rax
0x1400072be  and     rax, rcx
0x1400072c1  mov     [r8], rax
0x1400072c4  jmp     short loc_1400072E2
0x1400072c6  mov     rax, [rdx]
0x1400072c9  cmp     rax, qword ptr cs:IID_ICompileProgressNotification.Data1
0x1400072d0  jnz     short loc_1400072E5
0x1400072d2  mov     rax, [rdx+8]
0x1400072d6  cmp     rax, qword ptr cs:IID_ICompileProgressNotification.Data4
0x1400072dd  jnz     short loc_1400072E5
0x1400072df  mov     [r8], r9
0x1400072e2  xor     eax, eax
0x1400072e4  retn
0x1400072e5  mov     eax, 80004002h
0x1400072ea  retn
```
