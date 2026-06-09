# GetFixedTableInterceptor(_GUID const &,void * *)

- ea: `0x1800023d8`
- end: `0x1800024a9`
- name: `?GetFixedTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002970`

## callees

- `0x180002010`
- `0x1800023d8`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800023ec`
- `ole32!CoTaskMemAlloc` at `0x1800023ec`

## pseudocode

```c
__int64 __fastcall GetFixedTableInterceptor(const struct _GUID *a1, void **a2)
{
  char *v4; // rax
  CSDTFxd *v5; // rbx
  unsigned int v6; // edx
  int v7; // edi

  v4 = (char *)CoTaskMemAlloc(0xA0u);
  v5 = (CSDTFxd *)v4;
  if ( !v4 )
    return 2147942414LL;
  v4[24] = 0;
  *(_QWORD *)v4 = &CSDTFxd::`vftable'{for `ISimpleTableInterceptor'};
  *((_DWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 1) = &CSDTFxd::`vftable'{for `ISimpleTableRead2'};
  *(_QWORD *)(v4 + 36) = 0;
  *((_QWORD *)v4 + 2) = &CSDTFxd::`vftable'{for `ISimpleTableAdvanced'};
  *(_QWORD *)(v4 + 44) = 0;
  *(_QWORD *)(v4 + 52) = 0;
  *((_QWORD *)v4 + 8) = 0;
  *((_QWORD *)v4 + 9) = 0;
  *((_QWORD *)v4 + 10) = 0;
  *((_QWORD *)v4 + 11) = 0;
  *((_QWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 13) = 0;
  *((_QWORD *)v4 + 14) = 0;
  *((_QWORD *)v4 + 15) = 0;
  *((_QWORD *)v4 + 16) = 0;
  *((_QWORD *)v4 + 17) = 0;
  *((_DWORD *)v4 + 36) = 0;
  *((_QWORD *)v4 + 19) = &g_aFixedTableHeap;
  v7 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))v4)(v4, a1, a2);
  if ( v7 < 0 )
    CSDTFxd::`scalar deleting destructor'(v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800023d8  push    rbx
0x1800023da  push    rbp
0x1800023db  push    rsi
0x1800023dc  push    rdi
0x1800023dd  sub     rsp, 28h
0x1800023e1  mov     rsi, rcx
0x1800023e4  mov     rdi, rdx
0x1800023e7  mov     ecx, 0A0h; cb
0x1800023ec  call    cs:__imp_CoTaskMemAlloc
0x1800023f2  xor     ebp, ebp
0x1800023f4  mov     rbx, rax
0x1800023f7  test    rax, rax
0x1800023fa  jz      loc_18000249B
0x180002400  mov     [rbx+18h], bpl
0x180002404  lea     rax, ??_7CSDTFxd@@6BISimpleTableInterceptor@@@; const CSDTFxd::`vftable'{for `ISimpleTableInterceptor'}
0x18000240b  mov     [rbx], rax
0x18000240e  mov     r8, rdi
0x180002411  mov     [rbx+1Ch], ebp
0x180002414  lea     rax, ??_7CSDTFxd@@6BISimpleTableRead2@@@; const CSDTFxd::`vftable'{for `ISimpleTableRead2'}
0x18000241b  mov     [rbx+8], rax
0x18000241f  mov     rdx, rsi
0x180002422  mov     [rbx+24h], rbp
0x180002426  lea     rax, ??_7CSDTFxd@@6BISimpleTableAdvanced@@@; const CSDTFxd::`vftable'{for `ISimpleTableAdvanced'}
0x18000242d  mov     [rbx+10h], rax
0x180002431  mov     rcx, rbx
0x180002434  mov     [rbx+2Ch], rbp
0x180002438  lea     rax, ?g_aFixedTableHeap@@3PAKA; ulong near * g_aFixedTableHeap
0x18000243f  mov     [rbx+34h], rbp
0x180002443  mov     [rbx+40h], rbp
0x180002447  mov     [rbx+48h], rbp
0x18000244b  mov     [rbx+50h], rbp
0x18000244f  mov     [rbx+58h], rbp
0x180002453  mov     [rbx+60h], rbp
0x180002457  mov     [rbx+68h], rbp
0x18000245b  mov     [rbx+70h], rbp
0x18000245f  mov     [rbx+78h], rbp
0x180002463  mov     [rbx+80h], rbp
0x18000246a  mov     [rbx+88h], rbp
0x180002471  mov     [rbx+90h], ebp
0x180002477  mov     [rbx+98h], rax
0x18000247e  mov     rax, [rbx]
0x180002481  mov     rax, [rax]
0x180002484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002489  mov     edi, eax
0x18000248b  test    eax, eax
0x18000248d  jns     short loc_180002497
0x18000248f  mov     rcx, rbx; this
0x180002492  call    ??_GCSDTFxd@@QEAAPEAXI@Z; CSDTFxd::`scalar deleting destructor'(uint)
0x180002497  mov     eax, edi
0x180002499  jmp     short loc_1800024A0
0x18000249b  mov     eax, 8007000Eh
0x1800024a0  add     rsp, 28h
0x1800024a4  pop     rdi
0x1800024a5  pop     rsi
0x1800024a6  pop     rbp
0x1800024a7  pop     rbx
0x1800024a8  retn
```
