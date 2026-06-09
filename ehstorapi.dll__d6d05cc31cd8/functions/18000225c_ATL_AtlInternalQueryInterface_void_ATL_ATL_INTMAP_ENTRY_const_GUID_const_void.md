# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000225c`
- end: `0x180002332`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `int(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180003790`
- `0x180005f50`
- `0x180008200`
- `0x18000a9a0`
- `0x18000a9c0`

## callees

- `0x18000225c`
- `0x180003488`
- `0x180003bac`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::AtlInternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  char *v11; // rbx
  __int64 (__fastcall *v12)(char *, const struct _GUID *, char **, _QWORD); // r10
  int v13; // ebp

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !(unsigned int)ATL::InlineIsEqualUnknown(a3) )
  {
    while ( 1 )
    {
      v12 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
      if ( !v12 )
        return 2147500034LL;
      if ( *(_QWORD *)v6 )
      {
        v13 = 0;
        if ( !(unsigned int)InlineIsEqualGUID(*(_QWORD *)v6) )
          goto LABEL_16;
      }
      else
      {
        v13 = 1;
      }
      if ( v12 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      {
        v10 = *((_QWORD *)v6 + 1);
        goto LABEL_7;
      }
      result = v12(a1, a3, a4, *((_QWORD *)v6 + 1));
      if ( !(_DWORD)result || !v13 && (int)result < 0 )
        return result;
LABEL_16:
      v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    }
  }
  v10 = *(_QWORD *)(v9 + 8);
LABEL_7:
  v11 = &a1[v10];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  result = 0;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x18000225c  push    rbx
0x18000225e  push    rbp
0x18000225f  push    rsi
0x180002260  push    rdi
0x180002261  push    r14
0x180002263  sub     rsp, 30h
0x180002267  mov     rdi, r9
0x18000226a  mov     r14, r8
0x18000226d  mov     rbx, rdx
0x180002270  mov     rsi, rcx
0x180002273  test    rcx, rcx
0x180002276  jz      loc_180002322
0x18000227c  test    rdx, rdx
0x18000227f  jz      loc_180002322
0x180002285  test    r9, r9
0x180002288  jnz     short loc_180002294
0x18000228a  mov     eax, 80004003h
0x18000228f  jmp     loc_180002327
0x180002294  mov     rcx, r14; struct _GUID *
0x180002297  mov     qword ptr [r9], 0
0x18000229e  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800022a3  test    eax, eax
0x1800022a5  jz      short loc_1800022C4
0x1800022a7  mov     rbx, [rdx+8]
0x1800022ab  add     rbx, rsi
0x1800022ae  mov     rcx, rbx
0x1800022b1  mov     rax, [rbx]
0x1800022b4  mov     rax, [rax+8]
0x1800022b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bd  xor     eax, eax
0x1800022bf  mov     [rdi], rbx
0x1800022c2  jmp     short loc_180002327
0x1800022c4  mov     r10, [rbx+10h]
0x1800022c8  test    r10, r10
0x1800022cb  jz      short loc_18000231B
0x1800022cd  mov     rcx, [rbx]
0x1800022d0  test    rcx, rcx
0x1800022d3  jnz     short loc_1800022DA
0x1800022d5  lea     ebp, [rcx+1]
0x1800022d8  jmp     short loc_1800022E8
0x1800022da  mov     rdx, r14
0x1800022dd  xor     ebp, ebp
0x1800022df  call    InlineIsEqualGUID
0x1800022e4  test    eax, eax
0x1800022e6  jz      short loc_18000230F
0x1800022e8  cmp     r10, 1
0x1800022ec  jz      short loc_180002315
0x1800022ee  mov     r9, [rbx+8]
0x1800022f2  mov     r8, rdi
0x1800022f5  mov     rdx, r14
0x1800022f8  mov     rcx, rsi
0x1800022fb  mov     rax, r10
0x1800022fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002303  test    eax, eax
0x180002305  jz      short loc_180002327
0x180002307  test    ebp, ebp
0x180002309  jnz     short loc_18000230F
0x18000230b  test    eax, eax
0x18000230d  js      short loc_180002327
0x18000230f  add     rbx, 18h
0x180002313  jmp     short loc_1800022C4
0x180002315  mov     rbx, [rbx+8]
0x180002319  jmp     short loc_1800022AB
0x18000231b  mov     eax, 80004002h
0x180002320  jmp     short loc_180002327
0x180002322  mov     eax, 80070057h
0x180002327  add     rsp, 30h
0x18000232b  pop     r14
0x18000232d  pop     rdi
0x18000232e  pop     rsi
0x18000232f  pop     rbp
0x180002330  pop     rbx
0x180002331  retn
```
