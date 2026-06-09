# ExpandPathName

- ea: `0x180021488`
- end: `0x180021605`
- name: `ExpandPathName`
- size: `381`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021e3c`
- `0x18002210c`
- `0x1800222c0`

## callees

- `0x1800022d6`
- `0x180007e10`
- `0x18001ec80`
- `0x180021010`
- `0x180021488`
- `0x180023c4e`

## import_xrefs

- `msvcrt!wcschr` at `0x1800214a8`
- `msvcrt!wcschr` at `0x1800214a8`

## pseudocode

```c
wchar_t *__fastcall ExpandPathName(wchar_t *a1, __int64 a2, _QWORD *a3)
{
  wchar_t *v5; // rax
  __int64 v6; // r15
  wchar_t *v7; // r12
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rbp
  char *v10; // r14
  wchar_t *v11; // rdx
  size_t v12; // r8
  char *v13; // rcx
  _BYTE pExceptionObject[104]; // [rsp+20h] [rbp-68h] BYREF

  v5 = wcschr(a1, 0x2Cu);
  v6 = a2;
  if ( a1[a2] == 46 && ((v7 = &a1[v6], a1[v6 + 1] == 92) || v7[1] == 47) )
  {
    if ( v5 )
      v8 = v5 - a1;
    else
      v8 = mqwcslen(a1);
    v9 = g_dwComputerNameLen + a2;
    if ( g_dwComputerNameLen + v8 >= v8 )
      v9 = g_dwComputerNameLen + v8;
    v10 = (char *)MmAllocate(saturated_mul(v9, 2u));
    memcpy_0(v10, a1, 2 * a2);
    memcpy_0(&v10[v6 * 2], g_lpwcsComputerName, 2LL * g_dwComputerNameLen);
    v11 = v7 + 1;
    v12 = 2 * (v8 - a2) - 2;
    v13 = &v10[2 * a2 + 2 * g_dwComputerNameLen];
  }
  else
  {
    if ( !v5 )
      return a1;
    if ( v5 == a1 )
    {
      bad_document::bad_document((bad_document *)pExceptionObject, a1);
      throw (bad_format_name *)pExceptionObject;
    }
    v9 = v5 - a1 + 1;
    v10 = (char *)MmAllocate(saturated_mul(v9, 2u));
    v12 = 2 * v9 - 2;
    v11 = a1;
    v13 = v10;
  }
  memcpy_0(v13, v11, v12);
  *(_WORD *)&v10[2 * v9 - 2] = 0;
  *a3 = v10;
  return (wchar_t *)v10;
}

```

## disassembly

```asm
0x180021488  mov     [rsp+arg_10], r8
0x18002148d  push    rbx
0x18002148e  push    rbp
0x18002148f  push    rsi
0x180021490  push    rdi
0x180021491  push    r12
0x180021493  push    r13
0x180021495  push    r14
0x180021497  push    r15
0x180021499  sub     rsp, 48h
0x18002149d  mov     r13, rdx
0x1800214a0  mov     rdi, rcx
0x1800214a3  mov     edx, 2Ch ; ','; Ch
0x1800214a8  call    cs:__imp_wcschr
0x1800214ae  lea     r15, ds:0[r13*2]
0x1800214b6  mov     rbx, rax
0x1800214b9  cmp     word ptr [r15+rdi], 2Eh ; '.'
0x1800214bf  jnz     loc_180021575
0x1800214c5  lea     r12, [r15+rdi]
0x1800214c9  cmp     word ptr [r12+2], 5Ch ; '\'
0x1800214d0  jz      short loc_1800214DF
0x1800214d2  cmp     word ptr [r12+2], 2Fh ; '/'
0x1800214d9  jnz     loc_180021575
0x1800214df  xor     esi, esi
0x1800214e1  test    rbx, rbx
0x1800214e4  jz      short loc_1800214EE
0x1800214e6  sub     rbx, rdi
0x1800214e9  sar     rbx, 1
0x1800214ec  jmp     short loc_1800214F8
0x1800214ee  mov     rcx, rdi; wchar_t *
0x1800214f1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800214f6  mov     ebx, eax
0x1800214f8  mov     eax, cs:?g_dwComputerNameLen@@3KA; ulong g_dwComputerNameLen
0x1800214fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021502  mov     rcx, r8
0x180021505  lea     rdx, [rax+rbx]
0x180021509  lea     rbp, [rax+r13]
0x18002150d  cmp     rdx, rbx
0x180021510  lea     eax, [r8+3]
0x180021514  cmovnb  rcx, rdx
0x180021518  cmovnb  rbp, rcx
0x18002151c  mul     rbp
0x18002151f  cmovb   rax, r8
0x180021523  mov     rcx, rax; unsigned __int64
0x180021526  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002152b  mov     r8, r15; Size
0x18002152e  mov     rdx, rdi; Src
0x180021531  mov     rcx, rax; void *
0x180021534  mov     r14, rax
0x180021537  call    memcpy_0
0x18002153c  mov     r8d, cs:?g_dwComputerNameLen@@3KA; ulong g_dwComputerNameLen
0x180021543  lea     rcx, [r15+r14]; void *
0x180021547  mov     rdx, cs:?g_lpwcsComputerName@@3PEA_WEA; Src
0x18002154e  add     r8, r8; Size
0x180021551  call    memcpy_0
0x180021556  mov     ecx, cs:?g_dwComputerNameLen@@3KA; ulong g_dwComputerNameLen
0x18002155c  lea     rdx, [r12+2]
0x180021561  sub     rbx, r13
0x180021564  add     rcx, r13
0x180021567  lea     r8, ds:0FFFFFFFFFFFFFFFEh[rbx*2]
0x18002156f  lea     rcx, [r14+rcx*2]
0x180021573  jmp     short loc_1800215DB
0x180021575  xor     esi, esi
0x180021577  test    rbx, rbx
0x18002157a  jnz     short loc_180021581
0x18002157c  mov     rax, rdi
0x18002157f  jmp     short loc_1800215F4
0x180021581  cmp     rbx, rdi
0x180021584  jnz     short loc_1800215A5
0x180021586  mov     rdx, rdi; wchar_t *
0x180021589  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18002158e  call    ??0bad_document@@QEAA@PEB_W@Z; bad_document::bad_document(wchar_t const *)
0x180021593  lea     rdx, _TI2?AVbad_format_name@@; pThrowInfo
0x18002159a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002159f  call    _CxxThrowException_0
0x1800215a5  sub     rbx, rdi
0x1800215a8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800215af  sar     rbx, 1
0x1800215b2  mov     eax, 2
0x1800215b7  lea     rbp, [rbx+1]
0x1800215bb  mul     rbp
0x1800215be  cmovb   rax, r8
0x1800215c2  mov     rcx, rax; unsigned __int64
0x1800215c5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800215ca  mov     r14, rax
0x1800215cd  lea     r8, ds:0FFFFFFFFFFFFFFFEh[rbp*2]; Size
0x1800215d5  mov     rdx, rdi; Src
0x1800215d8  mov     rcx, rax; void *
0x1800215db  call    memcpy_0
0x1800215e0  mov     rax, [rsp+88h+arg_10]
0x1800215e8  mov     [r14+rbp*2-2], si
0x1800215ee  mov     [rax], r14
0x1800215f1  mov     rax, r14
0x1800215f4  add     rsp, 48h
0x1800215f8  pop     r15
0x1800215fa  pop     r14
0x1800215fc  pop     r13
0x1800215fe  pop     r12
0x180021600  pop     rdi
0x180021601  pop     rsi
0x180021602  pop     rbp
0x180021603  pop     rbx
0x180021604  retn
```
