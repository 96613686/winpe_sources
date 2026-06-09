# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180002f84`
- end: `0x180003088`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003540`
- `0x180003560`
- `0x1800071f0`
- `0x180007290`
- `0x180009060`
- `0x180009120`
- `0x18000b8f0`
- `0x18000d810`
- `0x1800168e0`

## callees

- `0x180002f84`
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
0x180002f84  push    rbx
0x180002f86  push    rbp
0x180002f87  push    rsi
0x180002f88  push    rdi
0x180002f89  push    r14
0x180002f8b  sub     rsp, 30h
0x180002f8f  mov     rsi, r9
0x180002f92  mov     rdi, r8
0x180002f95  mov     rbx, rdx
0x180002f98  mov     r14, rcx
0x180002f9b  test    rcx, rcx
0x180002f9e  jz      loc_180003078
0x180002fa4  test    rdx, rdx
0x180002fa7  jz      loc_180003078
0x180002fad  test    r9, r9
0x180002fb0  jnz     short loc_180002FBC
0x180002fb2  mov     eax, 80004003h
0x180002fb7  jmp     loc_18000307D
0x180002fbc  mov     qword ptr [r9], 0
0x180002fc3  cmp     dword ptr [r8], 0
0x180002fc7  jnz     short loc_180003001
0x180002fc9  cmp     dword ptr [r8+4], 0
0x180002fce  jnz     short loc_180003001
0x180002fd0  cmp     dword ptr [r8+8], 0C0h
0x180002fd8  jnz     short loc_180003001
0x180002fda  cmp     dword ptr [r8+0Ch], 46000000h
0x180002fe2  jnz     short loc_180003001
0x180002fe4  mov     rbx, [rdx+8]
0x180002fe8  add     rbx, r14
0x180002feb  mov     rcx, rbx
0x180002fee  mov     rax, [rbx]
0x180002ff1  mov     rax, [rax+8]
0x180002ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffa  xor     eax, eax
0x180002ffc  mov     [rsi], rbx
0x180002fff  jmp     short loc_18000307D
0x180003001  cmp     qword ptr [rdx+10h], 0
0x180003006  jz      short loc_180003068
0x180003008  mov     rcx, [rbx]
0x18000300b  test    rcx, rcx
0x18000300e  jnz     short loc_180003015
0x180003010  lea     ebp, [rcx+1]
0x180003013  jmp     short loc_180003035
0x180003015  mov     eax, [rdi]
0x180003017  cmp     [rcx], eax
0x180003019  jnz     short loc_18000305D
0x18000301b  mov     eax, [rdi+4]
0x18000301e  cmp     [rcx+4], eax
0x180003021  jnz     short loc_18000305D
0x180003023  mov     eax, [rdi+8]
0x180003026  cmp     [rcx+8], eax
0x180003029  jnz     short loc_18000305D
0x18000302b  mov     eax, [rdi+0Ch]
0x18000302e  cmp     [rcx+0Ch], eax
0x180003031  jnz     short loc_18000305D
0x180003033  xor     ebp, ebp
0x180003035  mov     rax, [rbx+10h]
0x180003039  cmp     rax, 1
0x18000303d  jz      short loc_18000306F
0x18000303f  mov     r9, [rbx+8]
0x180003043  mov     r8, rsi
0x180003046  mov     rdx, rdi
0x180003049  mov     rcx, r14
0x18000304c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003051  test    eax, eax
0x180003053  jz      short loc_18000307D
0x180003055  test    ebp, ebp
0x180003057  jnz     short loc_18000305D
0x180003059  test    eax, eax
0x18000305b  js      short loc_18000307D
0x18000305d  add     rbx, 18h
0x180003061  cmp     qword ptr [rbx+10h], 0
0x180003066  jnz     short loc_180003008
0x180003068  mov     eax, 80004002h
0x18000306d  jmp     short loc_18000307D
0x18000306f  mov     rbx, [rbx+8]
0x180003073  jmp     loc_180002FE8
0x180003078  mov     eax, 80070057h
0x18000307d  add     rsp, 30h
0x180003081  pop     r14
0x180003083  pop     rdi
0x180003084  pop     rsi
0x180003085  pop     rbp
0x180003086  pop     rbx
0x180003087  retn
```
