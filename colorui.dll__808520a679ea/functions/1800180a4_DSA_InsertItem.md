# DSA_InsertItem

- ea: `0x1800180a4`
- end: `0x180018107`
- name: `DSA_InsertItem`
- size: `99`
- prototype: `int __stdcall(HDSA hdsa, int i, const void *pitem)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011050`
- `0x180011a34`
- `0x180011fb4`
- `0x180012228`

## callees

- `0x1800180a4`
- `0x1800183e4`
- `0x180019010`

## pseudocode

```c
int __stdcall DSA_InsertItem(HDSA hdsa, int i, const void *pitem)
{
  __int64 (__fastcall *v3)(HDSA, _QWORD, const void *); // rax

  v3 = (__int64 (__fastcall *)(HDSA, _QWORD, const void *))qword_1800213F8;
  if ( qword_1800213F8 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_1800213F8, (const CHAR *)0x144);
    v3 = (__int64 (__fastcall *)(HDSA, _QWORD, const void *))qword_1800213F8;
  }
  if ( v3 )
    return v3(hdsa, (unsigned int)i, pitem);
  else
    return -1;
}

```

## disassembly

```asm
0x1800180a4  mov     [rsp+arg_0], rbx
0x1800180a9  mov     [rsp+arg_8], rsi
0x1800180ae  push    rdi
0x1800180af  sub     rsp, 20h
0x1800180b3  mov     rax, cs:qword_1800213F8
0x1800180ba  mov     rbx, r8
0x1800180bd  mov     edi, edx
0x1800180bf  mov     rsi, rcx
0x1800180c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800180c6  jnz     short loc_1800180E0
0x1800180c8  mov     edx, 144h
0x1800180cd  lea     rcx, qword_1800213F8
0x1800180d4  call    _GetProcFromComCtl32
0x1800180d9  mov     rax, cs:qword_1800213F8
0x1800180e0  test    rax, rax
0x1800180e3  jz      short loc_1800180F4
0x1800180e5  mov     r8, rbx
0x1800180e8  mov     edx, edi
0x1800180ea  mov     rcx, rsi
0x1800180ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180f2  jmp     short loc_1800180F7
0x1800180f4  or      eax, 0FFFFFFFFh
0x1800180f7  mov     rbx, [rsp+28h+arg_0]
0x1800180fc  mov     rsi, [rsp+28h+arg_8]
0x180018101  add     rsp, 20h
0x180018105  pop     rdi
0x180018106  retn
```
