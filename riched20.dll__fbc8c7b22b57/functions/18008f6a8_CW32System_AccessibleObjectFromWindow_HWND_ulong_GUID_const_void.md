# CW32System::AccessibleObjectFromWindow(HWND__ *,ulong,_GUID const &,void * *)

- ea: `0x18008f6a8`
- end: `0x18008f70b`
- name: `?AccessibleObjectFromWindow@CW32System@@SAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(HWND, unsigned int, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800636cc`
- `0x1800643b0`
- `0x180064590`
- `0x1800648c0`
- `0x180064db0`
- `0x180064e10`

## callees

- `0x18008f6a8`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x18008f6c8`: `AccessibleObjectFromWindow`

## pseudocode

```c
__int64 __fastcall CW32System::AccessibleObjectFromWindow(HWND a1, unsigned int a2, const struct _GUID *a3, void **a4)
{
  __int64 (__fastcall *v4)(HWND, _QWORD, const struct _GUID *, void **); // rax

  v4 = (__int64 (__fastcall *)(HWND, _QWORD, const struct _GUID *, void **))qword_1800A7590;
  if ( qword_1800A7590 )
    return v4(a1, a2, a3, a4);
  SetProcAddr((FARPROC *)&qword_1800A7590, 2, "AccessibleObjectFromWindow");
  v4 = (__int64 (__fastcall *)(HWND, _QWORD, const struct _GUID *, void **))qword_1800A7590;
  if ( qword_1800A7590 )
    return v4(a1, a2, a3, a4);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x18008f6a8  push    rbx
0x18008f6aa  push    rbp
0x18008f6ab  push    rsi
0x18008f6ac  push    rdi
0x18008f6ad  sub     rsp, 38h
0x18008f6b1  mov     rax, cs:qword_1800A7590
0x18008f6b8  mov     rbx, r9
0x18008f6bb  mov     rdi, r8
0x18008f6be  mov     esi, edx
0x18008f6c0  mov     rbp, rcx
0x18008f6c3  test    rax, rax
0x18008f6c6  jnz     short loc_18008F6F1
0x18008f6c8  lea     r8, aAccessibleobje; "AccessibleObjectFromWindow"
0x18008f6cf  lea     edx, [rax+2]
0x18008f6d2  lea     rcx, qword_1800A7590
0x18008f6d9  call    SetProcAddr
0x18008f6de  mov     rax, cs:qword_1800A7590
0x18008f6e5  test    rax, rax
0x18008f6e8  jnz     short loc_18008F6F1
0x18008f6ea  mov     eax, 80004002h
0x18008f6ef  jmp     short loc_18008F701
0x18008f6f1  mov     r9, rbx
0x18008f6f4  mov     r8, rdi
0x18008f6f7  mov     edx, esi
0x18008f6f9  mov     rcx, rbp
0x18008f6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f701  add     rsp, 38h
0x18008f705  pop     rdi
0x18008f706  pop     rsi
0x18008f707  pop     rbp
0x18008f708  pop     rbx
0x18008f709  retn
```
