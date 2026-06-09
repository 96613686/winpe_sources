# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800093d0`
- end: `0x1800094d4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a140`
- `0x18000a160`
- `0x18000a180`
- `0x18000a200`
- `0x18000a280`
- `0x18000a2c0`
- `0x18000d68c`
- `0x18000db80`
- `0x180010600`
- `0x180010670`
- `0x1800106e0`
- `0x180010750`
- `0x1800107c0`
- `0x180010830`
- `0x180010890`
- `0x1800108f0`
- `0x180010950`
- `0x1800109b0`
- `0x180010a10`
- `0x180010a30`
- `0x180010a50`
- `0x180010a70`
- `0x180010a90`
- `0x180010ab0`
- `0x180010ad0`

## callees

- `0x1800093d0`
- `0x180014010`

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
0x1800093d0  push    rbx
0x1800093d2  push    rbp
0x1800093d3  push    rsi
0x1800093d4  push    rdi
0x1800093d5  push    r14
0x1800093d7  sub     rsp, 30h
0x1800093db  mov     rsi, r9
0x1800093de  mov     rdi, r8
0x1800093e1  mov     rbx, rdx
0x1800093e4  mov     r14, rcx
0x1800093e7  test    rcx, rcx
0x1800093ea  jz      loc_1800094C4
0x1800093f0  test    rdx, rdx
0x1800093f3  jz      loc_1800094C4
0x1800093f9  test    r9, r9
0x1800093fc  jnz     short loc_180009408
0x1800093fe  mov     eax, 80004003h
0x180009403  jmp     loc_1800094C9
0x180009408  mov     qword ptr [r9], 0
0x18000940f  cmp     dword ptr [r8], 0
0x180009413  jnz     short loc_18000944D
0x180009415  cmp     dword ptr [r8+4], 0
0x18000941a  jnz     short loc_18000944D
0x18000941c  cmp     dword ptr [r8+8], 0C0h
0x180009424  jnz     short loc_18000944D
0x180009426  cmp     dword ptr [r8+0Ch], 46000000h
0x18000942e  jnz     short loc_18000944D
0x180009430  mov     rbx, [rdx+8]
0x180009434  add     rbx, r14
0x180009437  mov     rcx, rbx
0x18000943a  mov     rax, [rbx]
0x18000943d  mov     rax, [rax+8]
0x180009441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009446  xor     eax, eax
0x180009448  mov     [rsi], rbx
0x18000944b  jmp     short loc_1800094C9
0x18000944d  cmp     qword ptr [rdx+10h], 0
0x180009452  jz      short loc_1800094B4
0x180009454  mov     rcx, [rbx]
0x180009457  test    rcx, rcx
0x18000945a  jnz     short loc_180009461
0x18000945c  lea     ebp, [rcx+1]
0x18000945f  jmp     short loc_180009481
0x180009461  mov     eax, [rdi]
0x180009463  cmp     [rcx], eax
0x180009465  jnz     short loc_1800094A9
0x180009467  mov     eax, [rdi+4]
0x18000946a  cmp     [rcx+4], eax
0x18000946d  jnz     short loc_1800094A9
0x18000946f  mov     eax, [rdi+8]
0x180009472  cmp     [rcx+8], eax
0x180009475  jnz     short loc_1800094A9
0x180009477  mov     eax, [rdi+0Ch]
0x18000947a  cmp     [rcx+0Ch], eax
0x18000947d  jnz     short loc_1800094A9
0x18000947f  xor     ebp, ebp
0x180009481  mov     rax, [rbx+10h]
0x180009485  cmp     rax, 1
0x180009489  jz      short loc_1800094BB
0x18000948b  mov     r9, [rbx+8]
0x18000948f  mov     r8, rsi
0x180009492  mov     rdx, rdi
0x180009495  mov     rcx, r14
0x180009498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000949d  test    eax, eax
0x18000949f  jz      short loc_1800094C9
0x1800094a1  test    ebp, ebp
0x1800094a3  jnz     short loc_1800094A9
0x1800094a5  test    eax, eax
0x1800094a7  js      short loc_1800094C9
0x1800094a9  add     rbx, 18h
0x1800094ad  cmp     qword ptr [rbx+10h], 0
0x1800094b2  jnz     short loc_180009454
0x1800094b4  mov     eax, 80004002h
0x1800094b9  jmp     short loc_1800094C9
0x1800094bb  mov     rbx, [rbx+8]
0x1800094bf  jmp     loc_180009434
0x1800094c4  mov     eax, 80070057h
0x1800094c9  add     rsp, 30h
0x1800094cd  pop     r14
0x1800094cf  pop     rdi
0x1800094d0  pop     rsi
0x1800094d1  pop     rbp
0x1800094d2  pop     rbx
0x1800094d3  retn
```
