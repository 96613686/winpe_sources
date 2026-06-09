# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000962c`
- end: `0x180009702`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `int(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `43`
- callee_count: `4`
- tags: ``

## callers

- `0x18000987c`
- `0x180009af0`
- `0x18000a460`
- `0x18000c9fc`
- `0x180010360`
- `0x1800103c0`
- `0x180010420`
- `0x180010480`
- `0x180010530`
- `0x180010590`
- `0x1800105f0`
- `0x180010650`
- `0x1800106b0`
- `0x180010710`
- `0x180010770`
- `0x1800107d0`
- `0x180010840`
- `0x1800108b0`
- `0x180010930`
- `0x180010a60`
- `0x180010ad0`
- `0x180010b40`
- `0x180010bb0`
- `0x180010c20`
- `0x180010c90`
- `0x180010d00`
- `0x180010d70`
- `0x180010d90`
- `0x180010dc0`
- `0x180010df0`
- `0x180010e30`
- `0x180010ed0`
- `0x180010f00`
- `0x180010f30`
- `0x180010f60`
- `0x180010f90`
- `0x180010fc0`
- `0x180010ff0`
- `0x180011020`
- `0x180012c94`
- `0x18002443c`
- `0x180024950`
- `0x180026110`

## callees

- `0x180008fb0`
- `0x18000962c`
- `0x18000a1e4`
- `0x180029010`

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
        if ( !(unsigned int)InlineIsEqualGUID(*(_QWORD *)v6, a3) )
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
0x18000962c  push    rbx
0x18000962e  push    rbp
0x18000962f  push    rsi
0x180009630  push    rdi
0x180009631  push    r14
0x180009633  sub     rsp, 30h
0x180009637  mov     rdi, r9
0x18000963a  mov     r14, r8
0x18000963d  mov     rbx, rdx
0x180009640  mov     rsi, rcx
0x180009643  test    rcx, rcx
0x180009646  jz      loc_1800096F2
0x18000964c  test    rdx, rdx
0x18000964f  jz      loc_1800096F2
0x180009655  test    r9, r9
0x180009658  jnz     short loc_180009664
0x18000965a  mov     eax, 80004003h
0x18000965f  jmp     loc_1800096F7
0x180009664  mov     rcx, r14; struct _GUID *
0x180009667  mov     qword ptr [r9], 0
0x18000966e  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180009673  test    eax, eax
0x180009675  jz      short loc_180009694
0x180009677  mov     rbx, [rdx+8]
0x18000967b  add     rbx, rsi
0x18000967e  mov     rcx, rbx
0x180009681  mov     rax, [rbx]
0x180009684  mov     rax, [rax+8]
0x180009688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968d  xor     eax, eax
0x18000968f  mov     [rdi], rbx
0x180009692  jmp     short loc_1800096F7
0x180009694  mov     r10, [rbx+10h]
0x180009698  test    r10, r10
0x18000969b  jz      short loc_1800096EB
0x18000969d  mov     rcx, [rbx]
0x1800096a0  test    rcx, rcx
0x1800096a3  jnz     short loc_1800096AA
0x1800096a5  lea     ebp, [rcx+1]
0x1800096a8  jmp     short loc_1800096B8
0x1800096aa  mov     rdx, r14
0x1800096ad  xor     ebp, ebp
0x1800096af  call    InlineIsEqualGUID
0x1800096b4  test    eax, eax
0x1800096b6  jz      short loc_1800096DF
0x1800096b8  cmp     r10, 1
0x1800096bc  jz      short loc_1800096E5
0x1800096be  mov     r9, [rbx+8]
0x1800096c2  mov     r8, rdi
0x1800096c5  mov     rdx, r14
0x1800096c8  mov     rcx, rsi
0x1800096cb  mov     rax, r10
0x1800096ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d3  test    eax, eax
0x1800096d5  jz      short loc_1800096F7
0x1800096d7  test    ebp, ebp
0x1800096d9  jnz     short loc_1800096DF
0x1800096db  test    eax, eax
0x1800096dd  js      short loc_1800096F7
0x1800096df  add     rbx, 18h
0x1800096e3  jmp     short loc_180009694
0x1800096e5  mov     rbx, [rbx+8]
0x1800096e9  jmp     short loc_18000967B
0x1800096eb  mov     eax, 80004002h
0x1800096f0  jmp     short loc_1800096F7
0x1800096f2  mov     eax, 80070057h
0x1800096f7  add     rsp, 30h
0x1800096fb  pop     r14
0x1800096fd  pop     rdi
0x1800096fe  pop     rsi
0x1800096ff  pop     rbp
0x180009700  pop     rbx
0x180009701  retn
```
