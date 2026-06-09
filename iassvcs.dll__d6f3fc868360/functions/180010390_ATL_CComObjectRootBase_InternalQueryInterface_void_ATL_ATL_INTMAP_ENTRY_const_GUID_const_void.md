# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180010390`
- end: `0x180010494`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010d30`
- `0x180010d60`
- `0x180010d90`

## callees

- `0x180010390`
- `0x180019010`

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
0x180010390  push    rbx
0x180010392  push    rbp
0x180010393  push    rsi
0x180010394  push    rdi
0x180010395  push    r14
0x180010397  sub     rsp, 30h
0x18001039b  mov     rsi, r9
0x18001039e  mov     rdi, r8
0x1800103a1  mov     rbx, rdx
0x1800103a4  mov     r14, rcx
0x1800103a7  test    rcx, rcx
0x1800103aa  jz      loc_180010484
0x1800103b0  test    rdx, rdx
0x1800103b3  jz      loc_180010484
0x1800103b9  test    r9, r9
0x1800103bc  jnz     short loc_1800103C8
0x1800103be  mov     eax, 80004003h
0x1800103c3  jmp     loc_180010489
0x1800103c8  mov     qword ptr [r9], 0
0x1800103cf  cmp     dword ptr [r8], 0
0x1800103d3  jnz     short loc_18001040D
0x1800103d5  cmp     dword ptr [r8+4], 0
0x1800103da  jnz     short loc_18001040D
0x1800103dc  cmp     dword ptr [r8+8], 0C0h
0x1800103e4  jnz     short loc_18001040D
0x1800103e6  cmp     dword ptr [r8+0Ch], 46000000h
0x1800103ee  jnz     short loc_18001040D
0x1800103f0  mov     rbx, [rdx+8]
0x1800103f4  add     rbx, r14
0x1800103f7  mov     rcx, rbx
0x1800103fa  mov     rax, [rbx]
0x1800103fd  mov     rax, [rax+8]
0x180010401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010406  xor     eax, eax
0x180010408  mov     [rsi], rbx
0x18001040b  jmp     short loc_180010489
0x18001040d  cmp     qword ptr [rdx+10h], 0
0x180010412  jz      short loc_180010474
0x180010414  mov     rcx, [rbx]
0x180010417  test    rcx, rcx
0x18001041a  jnz     short loc_180010421
0x18001041c  lea     ebp, [rcx+1]
0x18001041f  jmp     short loc_180010441
0x180010421  mov     eax, [rdi]
0x180010423  cmp     [rcx], eax
0x180010425  jnz     short loc_180010469
0x180010427  mov     eax, [rdi+4]
0x18001042a  cmp     [rcx+4], eax
0x18001042d  jnz     short loc_180010469
0x18001042f  mov     eax, [rdi+8]
0x180010432  cmp     [rcx+8], eax
0x180010435  jnz     short loc_180010469
0x180010437  mov     eax, [rdi+0Ch]
0x18001043a  cmp     [rcx+0Ch], eax
0x18001043d  jnz     short loc_180010469
0x18001043f  xor     ebp, ebp
0x180010441  mov     rax, [rbx+10h]
0x180010445  cmp     rax, 1
0x180010449  jz      short loc_18001047B
0x18001044b  mov     r9, [rbx+8]
0x18001044f  mov     r8, rsi
0x180010452  mov     rdx, rdi
0x180010455  mov     rcx, r14
0x180010458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001045d  test    eax, eax
0x18001045f  jz      short loc_180010489
0x180010461  test    ebp, ebp
0x180010463  jnz     short loc_180010469
0x180010465  test    eax, eax
0x180010467  js      short loc_180010489
0x180010469  add     rbx, 18h
0x18001046d  cmp     qword ptr [rbx+10h], 0
0x180010472  jnz     short loc_180010414
0x180010474  mov     eax, 80004002h
0x180010479  jmp     short loc_180010489
0x18001047b  mov     rbx, [rbx+8]
0x18001047f  jmp     loc_1800103F4
0x180010484  mov     eax, 80070057h
0x180010489  add     rsp, 30h
0x18001048d  pop     r14
0x18001048f  pop     rdi
0x180010490  pop     rsi
0x180010491  pop     rbp
0x180010492  pop     rbx
0x180010493  retn
```
