# GetFixedPackedInterceptor(_GUID const &,void * *)

- ea: `0x180002314`
- end: `0x1800023d1`
- name: `?GetFixedPackedInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `189`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002970`

## callees

- `0x180002078`
- `0x180002314`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180002328`
- `ole32!CoTaskMemAlloc` at `0x180002328`

## pseudocode

```c
__int64 __fastcall GetFixedPackedInterceptor(const struct _GUID *a1, void **a2)
{
  TFixedPackedSchemaInterceptor *v4; // rax
  TFixedPackedSchemaInterceptor *v5; // rbx
  unsigned int v6; // edx
  int v7; // edi

  v4 = (TFixedPackedSchemaInterceptor *)CoTaskMemAlloc(0x80u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  *((_QWORD *)v4 + 4) = 0;
  *(_QWORD *)v4 = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableInterceptor'};
  *((_DWORD *)v4 + 10) = 0;
  *((_QWORD *)v4 + 1) = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableRead2'};
  *((_DWORD *)v4 + 11) = -1;
  *((_QWORD *)v4 + 2) = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableAdvanced'};
  *((_QWORD *)v4 + 6) = 0;
  *((_QWORD *)v4 + 3) = &qword_180046000;
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 8) = 0;
  *((_QWORD *)v4 + 9) = 0;
  *((_QWORD *)v4 + 10) = 0;
  *((_QWORD *)v4 + 11) = 0;
  *((_QWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 13) = 0;
  *((_QWORD *)v4 + 14) = 0;
  *((_QWORD *)v4 + 15) = 0;
  v7 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))v4)(v4, a1, a2);
  if ( v7 < 0 )
    TFixedPackedSchemaInterceptor::`scalar deleting destructor'(v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002314  push    rbx
0x180002316  push    rbp
0x180002317  push    rsi
0x180002318  push    rdi
0x180002319  sub     rsp, 28h
0x18000231d  mov     rsi, rcx
0x180002320  mov     rdi, rdx
0x180002323  mov     ecx, 80h; cb
0x180002328  call    cs:__imp_CoTaskMemAlloc
0x18000232e  xor     ebp, ebp
0x180002330  mov     rbx, rax
0x180002333  test    rax, rax
0x180002336  jz      loc_1800023C3
0x18000233c  mov     [rbx+20h], rbp
0x180002340  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableInterceptor@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableInterceptor'}
0x180002347  mov     [rbx], rax
0x18000234a  mov     r8, rdi
0x18000234d  mov     [rbx+28h], ebp
0x180002350  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableRead2@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableRead2'}
0x180002357  mov     [rbx+8], rax
0x18000235b  mov     rdx, rsi
0x18000235e  mov     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180002365  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableAdvanced@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableAdvanced'}
0x18000236c  mov     [rbx+10h], rax
0x180002370  mov     rcx, rbx
0x180002373  mov     [rbx+30h], rbp
0x180002377  lea     rax, qword_180046000
0x18000237e  mov     [rbx+18h], rax
0x180002382  mov     [rbx+38h], rbp
0x180002386  mov     [rbx+40h], rbp
0x18000238a  mov     [rbx+48h], rbp
0x18000238e  mov     [rbx+50h], rbp
0x180002392  mov     [rbx+58h], rbp
0x180002396  mov     [rbx+60h], rbp
0x18000239a  mov     [rbx+68h], rbp
0x18000239e  mov     [rbx+70h], rbp
0x1800023a2  mov     [rbx+78h], rbp
0x1800023a6  mov     rax, [rbx]
0x1800023a9  mov     rax, [rax]
0x1800023ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b1  mov     edi, eax
0x1800023b3  test    eax, eax
0x1800023b5  jns     short loc_1800023BF
0x1800023b7  mov     rcx, rbx; this
0x1800023ba  call    ??_GTFixedPackedSchemaInterceptor@@QEAAPEAXI@Z; TFixedPackedSchemaInterceptor::`scalar deleting destructor'(uint)
0x1800023bf  mov     eax, edi
0x1800023c1  jmp     short loc_1800023C8
0x1800023c3  mov     eax, 8007000Eh
0x1800023c8  add     rsp, 28h
0x1800023cc  pop     rdi
0x1800023cd  pop     rsi
0x1800023ce  pop     rbp
0x1800023cf  pop     rbx
0x1800023d0  retn
```
