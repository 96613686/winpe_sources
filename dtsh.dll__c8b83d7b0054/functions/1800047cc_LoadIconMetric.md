# LoadIconMetric

- ea: `0x1800047cc`
- end: `0x18000482e`
- name: `LoadIconMetric`
- size: `98`
- prototype: `HRESULT __stdcall(HINSTANCE hinst, PCWSTR pszName, int lims, HICON *phico)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003b00`

## callees

- `0x1800047cc`
- `0x18000489c`
- `0x180005010`

## pseudocode

```c
HRESULT __stdcall LoadIconMetric(HINSTANCE hinst, PCWSTR pszName, int lims, HICON *phico)
{
  __int64 (__fastcall *v4)(HINSTANCE, PCWSTR, _QWORD, HICON *); // rax

  v4 = (__int64 (__fastcall *)(HINSTANCE, PCWSTR, _QWORD, HICON *))qword_180009158;
  if ( qword_180009158 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180009158, "LoadIconMetric");
    v4 = (__int64 (__fastcall *)(HINSTANCE, PCWSTR, _QWORD, HICON *))qword_180009158;
  }
  if ( v4 )
    return v4(hinst, pszName, (unsigned int)lims, phico);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x1800047cc  push    rbx
0x1800047ce  push    rbp
0x1800047cf  push    rsi
0x1800047d0  push    rdi
0x1800047d1  sub     rsp, 38h
0x1800047d5  mov     rax, cs:qword_180009158
0x1800047dc  mov     rbx, r9
0x1800047df  mov     edi, r8d
0x1800047e2  mov     rsi, rdx
0x1800047e5  mov     rbp, rcx
0x1800047e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800047ec  jnz     short loc_180004808
0x1800047ee  lea     rdx, aLoadiconmetric; "LoadIconMetric"
0x1800047f5  lea     rcx, qword_180009158
0x1800047fc  call    _GetProcFromComCtl32
0x180004801  mov     rax, cs:qword_180009158
0x180004808  test    rax, rax
0x18000480b  jz      short loc_180004820
0x18000480d  mov     r9, rbx
0x180004810  mov     r8d, edi
0x180004813  mov     rdx, rsi
0x180004816  mov     rcx, rbp
0x180004819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481e  jmp     short loc_180004825
0x180004820  mov     eax, 80004005h
0x180004825  add     rsp, 38h
0x180004829  pop     rdi
0x18000482a  pop     rsi
0x18000482b  pop     rbp
0x18000482c  pop     rbx
0x18000482d  retn
```
