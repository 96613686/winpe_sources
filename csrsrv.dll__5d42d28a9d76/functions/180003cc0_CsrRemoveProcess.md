# CsrRemoveProcess

- ea: `0x180003cc0`
- end: `0x180003dd3`
- name: `CsrRemoveProcess`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003c20`

## callees

- `0x180003cc0`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180003cf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180003cf6`

## pseudocode

```c
int __fastcall CsrRemoveProcess(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  _QWORD *v4; // rcx
  __int64 (__fastcall *v5)(__int64); // rax
  void (__fastcall *v6)(__int64); // rax
  void (__fastcall *v7)(__int64); // rax
  void (__fastcall *v8)(__int64); // rax
  void (__fastcall *v9)(__int64); // rax
  void (__fastcall *v10)(__int64); // rax

  v1 = *(_QWORD *)(a1 + 16);
  v2 = a1 + 16;
  if ( *(_QWORD *)(v1 + 8) != a1 + 16 || (v4 = *(_QWORD **)(a1 + 24), *v4 != v2) )
    __fastfail(3u);
  *v4 = v1;
  *(_QWORD *)(v1 + 8) = v4;
  LODWORD(v5) = RtlLeaveCriticalSection(&CsrProcessStructureLock);
  if ( (*(_DWORD *)(a1 + 92) & 0x1080) == 0 )
  {
    _mm_lfence();
    if ( CsrLoadedServerDll[0] )
    {
      v6 = *(void (__fastcall **)(__int64))(CsrLoadedServerDll[0] + 80);
      if ( v6 )
        v6(a1);
    }
    if ( qword_180010368 )
    {
      v7 = *(void (__fastcall **)(__int64))(qword_180010368 + 80);
      if ( v7 )
        v7(a1);
    }
    if ( qword_180010370 )
    {
      v8 = *(void (__fastcall **)(__int64))(qword_180010370 + 80);
      if ( v8 )
        v8(a1);
    }
    if ( qword_180010378 )
    {
      v9 = *(void (__fastcall **)(__int64))(qword_180010378 + 80);
      if ( v9 )
        v9(a1);
    }
    if ( qword_180010380 )
    {
      v10 = *(void (__fastcall **)(__int64))(qword_180010380 + 80);
      if ( v10 )
        v10(a1);
    }
    LODWORD(v5) = qword_180010388;
    if ( qword_180010388 )
    {
      v5 = *(__int64 (__fastcall **)(__int64))(qword_180010388 + 80);
      if ( v5 )
        LODWORD(v5) = v5(a1);
    }
  }
  return (int)v5;
}

```

## disassembly

```asm
0x180003cc0  push    rbx
0x180003cc2  sub     rsp, 20h
0x180003cc6  mov     rdx, [rcx+10h]
0x180003cca  lea     rax, [rcx+10h]
0x180003cce  mov     rbx, rcx
0x180003cd1  cmp     [rdx+8], rax
0x180003cd5  jnz     loc_180003DCC
0x180003cdb  mov     rcx, [rax+8]
0x180003cdf  cmp     [rcx], rax
0x180003ce2  jnz     loc_180003DCC
0x180003ce8  mov     [rcx], rdx
0x180003ceb  mov     [rdx+8], rcx
0x180003cef  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003cf6  call    cs:__imp_RtlLeaveCriticalSection
0x180003cfd  nop     dword ptr [rax+rax+00h]
0x180003d02  test    dword ptr [rbx+5Ch], 1080h
0x180003d09  jnz     loc_180003DC5
0x180003d0f  lfence
0x180003d12  mov     rax, cs:CsrLoadedServerDll
0x180003d19  test    rax, rax
0x180003d1c  jz      short loc_180003D2F
0x180003d1e  mov     rax, [rax+50h]
0x180003d22  test    rax, rax
0x180003d25  jz      short loc_180003D2F
0x180003d27  mov     rcx, rbx
0x180003d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2f  mov     rax, cs:qword_180010368
0x180003d36  test    rax, rax
0x180003d39  jz      short loc_180003D4C
0x180003d3b  mov     rax, [rax+50h]
0x180003d3f  test    rax, rax
0x180003d42  jz      short loc_180003D4C
0x180003d44  mov     rcx, rbx
0x180003d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4c  mov     rax, cs:qword_180010370
0x180003d53  test    rax, rax
0x180003d56  jz      short loc_180003D69
0x180003d58  mov     rax, [rax+50h]
0x180003d5c  test    rax, rax
0x180003d5f  jz      short loc_180003D69
0x180003d61  mov     rcx, rbx
0x180003d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d69  mov     rax, cs:qword_180010378
0x180003d70  test    rax, rax
0x180003d73  jz      short loc_180003D86
0x180003d75  mov     rax, [rax+50h]
0x180003d79  test    rax, rax
0x180003d7c  jz      short loc_180003D86
0x180003d7e  mov     rcx, rbx
0x180003d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d86  mov     rax, cs:qword_180010380
0x180003d8d  test    rax, rax
0x180003d90  jz      short loc_180003DA3
0x180003d92  mov     rax, [rax+50h]
0x180003d96  test    rax, rax
0x180003d99  jz      short loc_180003DA3
0x180003d9b  mov     rcx, rbx
0x180003d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da3  mov     rax, cs:qword_180010388
0x180003daa  test    rax, rax
0x180003dad  jz      short loc_180003DC5
0x180003daf  mov     rax, [rax+50h]
0x180003db3  test    rax, rax
0x180003db6  jz      short loc_180003DC5
0x180003db8  mov     rcx, rbx
0x180003dbb  add     rsp, 20h
0x180003dbf  pop     rbx
0x180003dc0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc5  add     rsp, 20h
0x180003dc9  pop     rbx
0x180003dca  retn
0x180003dcc  mov     ecx, 3
0x180003dd1  int     29h; Win8: RtlFailFast(ecx)
```
