# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180002224`
- end: `0x180002328`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002370`
- `0x180002390`

## callees

- `0x180002224`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x180002224  push    rbx
0x180002226  push    rbp
0x180002227  push    rsi
0x180002228  push    rdi
0x180002229  push    r14
0x18000222b  sub     rsp, 30h
0x18000222f  mov     rsi, r9
0x180002232  mov     rdi, r8
0x180002235  mov     rbx, rdx
0x180002238  mov     r14, rcx
0x18000223b  test    rcx, rcx
0x18000223e  jz      loc_180002318
0x180002244  test    rdx, rdx
0x180002247  jz      loc_180002318
0x18000224d  test    r9, r9
0x180002250  jnz     short loc_18000225C
0x180002252  mov     eax, 80004003h
0x180002257  jmp     loc_18000231D
0x18000225c  mov     qword ptr [r9], 0
0x180002263  cmp     dword ptr [r8], 0
0x180002267  jnz     short loc_1800022A1
0x180002269  cmp     dword ptr [r8+4], 0
0x18000226e  jnz     short loc_1800022A1
0x180002270  cmp     dword ptr [r8+8], 0C0h
0x180002278  jnz     short loc_1800022A1
0x18000227a  cmp     dword ptr [r8+0Ch], 46000000h
0x180002282  jnz     short loc_1800022A1
0x180002284  mov     rbx, [rdx+8]
0x180002288  add     rbx, r14
0x18000228b  mov     rcx, rbx
0x18000228e  mov     rax, [rbx]
0x180002291  mov     rax, [rax+8]
0x180002295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229a  xor     eax, eax
0x18000229c  mov     [rsi], rbx
0x18000229f  jmp     short loc_18000231D
0x1800022a1  cmp     qword ptr [rdx+10h], 0
0x1800022a6  jz      short loc_180002308
0x1800022a8  mov     rcx, [rbx]
0x1800022ab  test    rcx, rcx
0x1800022ae  jnz     short loc_1800022B5
0x1800022b0  lea     ebp, [rcx+1]
0x1800022b3  jmp     short loc_1800022D5
0x1800022b5  mov     eax, [rdi]
0x1800022b7  cmp     [rcx], eax
0x1800022b9  jnz     short loc_1800022FD
0x1800022bb  mov     eax, [rdi+4]
0x1800022be  cmp     [rcx+4], eax
0x1800022c1  jnz     short loc_1800022FD
0x1800022c3  mov     eax, [rdi+8]
0x1800022c6  cmp     [rcx+8], eax
0x1800022c9  jnz     short loc_1800022FD
0x1800022cb  mov     eax, [rdi+0Ch]
0x1800022ce  cmp     [rcx+0Ch], eax
0x1800022d1  jnz     short loc_1800022FD
0x1800022d3  xor     ebp, ebp
0x1800022d5  mov     rax, [rbx+10h]
0x1800022d9  cmp     rax, 1
0x1800022dd  jz      short loc_18000230F
0x1800022df  mov     r9, [rbx+8]
0x1800022e3  mov     r8, rsi
0x1800022e6  mov     rdx, rdi
0x1800022e9  mov     rcx, r14
0x1800022ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f1  test    eax, eax
0x1800022f3  jz      short loc_18000231D
0x1800022f5  test    ebp, ebp
0x1800022f7  jnz     short loc_1800022FD
0x1800022f9  test    eax, eax
0x1800022fb  js      short loc_18000231D
0x1800022fd  add     rbx, 18h
0x180002301  cmp     qword ptr [rbx+10h], 0
0x180002306  jnz     short loc_1800022A8
0x180002308  mov     eax, 80004002h
0x18000230d  jmp     short loc_18000231D
0x18000230f  mov     rbx, [rbx+8]
0x180002313  jmp     loc_180002288
0x180002318  mov     eax, 80070057h
0x18000231d  add     rsp, 30h
0x180002321  pop     r14
0x180002323  pop     rdi
0x180002324  pop     rsi
0x180002325  pop     rbp
0x180002326  pop     rbx
0x180002327  retn
```
