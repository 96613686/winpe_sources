# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x14000627c`
- end: `0x140006380`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400076d0`
- `0x1400076f0`
- `0x14000b710`

## callees

- `0x14000627c`
- `0x140010010`

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
0x14000627c  push    rbx
0x14000627e  push    rbp
0x14000627f  push    rsi
0x140006280  push    rdi
0x140006281  push    r14
0x140006283  sub     rsp, 30h
0x140006287  mov     rsi, r9
0x14000628a  mov     rdi, r8
0x14000628d  mov     rbx, rdx
0x140006290  mov     r14, rcx
0x140006293  test    rcx, rcx
0x140006296  jz      loc_140006370
0x14000629c  test    rdx, rdx
0x14000629f  jz      loc_140006370
0x1400062a5  test    r9, r9
0x1400062a8  jnz     short loc_1400062B4
0x1400062aa  mov     eax, 80004003h
0x1400062af  jmp     loc_140006375
0x1400062b4  mov     qword ptr [r9], 0
0x1400062bb  cmp     dword ptr [r8], 0
0x1400062bf  jnz     short loc_1400062F9
0x1400062c1  cmp     dword ptr [r8+4], 0
0x1400062c6  jnz     short loc_1400062F9
0x1400062c8  cmp     dword ptr [r8+8], 0C0h
0x1400062d0  jnz     short loc_1400062F9
0x1400062d2  cmp     dword ptr [r8+0Ch], 46000000h
0x1400062da  jnz     short loc_1400062F9
0x1400062dc  mov     rbx, [rdx+8]
0x1400062e0  add     rbx, r14
0x1400062e3  mov     rcx, rbx
0x1400062e6  mov     rax, [rbx]
0x1400062e9  mov     rax, [rax+8]
0x1400062ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f2  xor     eax, eax
0x1400062f4  mov     [rsi], rbx
0x1400062f7  jmp     short loc_140006375
0x1400062f9  cmp     qword ptr [rdx+10h], 0
0x1400062fe  jz      short loc_140006360
0x140006300  mov     rcx, [rbx]
0x140006303  test    rcx, rcx
0x140006306  jnz     short loc_14000630D
0x140006308  lea     ebp, [rcx+1]
0x14000630b  jmp     short loc_14000632D
0x14000630d  mov     eax, [rdi]
0x14000630f  cmp     [rcx], eax
0x140006311  jnz     short loc_140006355
0x140006313  mov     eax, [rdi+4]
0x140006316  cmp     [rcx+4], eax
0x140006319  jnz     short loc_140006355
0x14000631b  mov     eax, [rdi+8]
0x14000631e  cmp     [rcx+8], eax
0x140006321  jnz     short loc_140006355
0x140006323  mov     eax, [rdi+0Ch]
0x140006326  cmp     [rcx+0Ch], eax
0x140006329  jnz     short loc_140006355
0x14000632b  xor     ebp, ebp
0x14000632d  mov     rax, [rbx+10h]
0x140006331  cmp     rax, 1
0x140006335  jz      short loc_140006367
0x140006337  mov     r9, [rbx+8]
0x14000633b  mov     r8, rsi
0x14000633e  mov     rdx, rdi
0x140006341  mov     rcx, r14
0x140006344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006349  test    eax, eax
0x14000634b  jz      short loc_140006375
0x14000634d  test    ebp, ebp
0x14000634f  jnz     short loc_140006355
0x140006351  test    eax, eax
0x140006353  js      short loc_140006375
0x140006355  add     rbx, 18h
0x140006359  cmp     qword ptr [rbx+10h], 0
0x14000635e  jnz     short loc_140006300
0x140006360  mov     eax, 80004002h
0x140006365  jmp     short loc_140006375
0x140006367  mov     rbx, [rbx+8]
0x14000636b  jmp     loc_1400062E0
0x140006370  mov     eax, 80070057h
0x140006375  add     rsp, 30h
0x140006379  pop     r14
0x14000637b  pop     rdi
0x14000637c  pop     rsi
0x14000637d  pop     rbp
0x14000637e  pop     rbx
0x14000637f  retn
```
