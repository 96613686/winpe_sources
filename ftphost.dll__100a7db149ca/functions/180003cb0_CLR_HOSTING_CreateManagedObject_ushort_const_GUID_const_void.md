# CLR_HOSTING::CreateManagedObject(ushort const *,_GUID const &,void * *)

- ea: `0x180003cb0`
- end: `0x180003cd3`
- name: `?CreateManagedObject@CLR_HOSTING@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `35`
- prototype: `__int64 __fastcall(CLR_HOSTING *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003cb0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CLR_HOSTING::CreateManagedObject(
        CLR_HOSTING *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v4)(const unsigned __int16 *, const struct _GUID *, void **); // rax

  v4 = (__int64 (__fastcall *)(const unsigned __int16 *, const struct _GUID *, void **))*((_QWORD *)this - 1);
  if ( v4 )
    return v4(a2, a3, a4);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180003cb0  mov     rax, [rcx-8]
0x180003cb4  mov     r10, r8
0x180003cb7  mov     r11, rdx
0x180003cba  test    rax, rax
0x180003cbd  jnz     short loc_180003CC5
0x180003cbf  mov     eax, 80004001h
0x180003cc4  retn
0x180003cc5  mov     r8, r9
0x180003cc8  mov     rdx, r10
0x180003ccb  mov     rcx, r11
0x180003cce  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
