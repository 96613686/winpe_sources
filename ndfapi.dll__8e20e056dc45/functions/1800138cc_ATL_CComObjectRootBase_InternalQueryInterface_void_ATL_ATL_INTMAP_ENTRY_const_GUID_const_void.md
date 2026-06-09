# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800138cc`
- end: `0x1800139d0`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014470`
- `0x180014490`
- `0x1800144b0`
- `0x1800144d0`
- `0x180014500`
- `0x180014520`
- `0x180014540`
- `0x180014560`
- `0x180014580`
- `0x1800145a0`
- `0x1800145c0`
- `0x1800145e0`

## callees

- `0x1800138cc`
- `0x180021010`

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
0x1800138cc  push    rbx
0x1800138ce  push    rbp
0x1800138cf  push    rsi
0x1800138d0  push    rdi
0x1800138d1  push    r14
0x1800138d3  sub     rsp, 30h
0x1800138d7  mov     rsi, r9
0x1800138da  mov     rdi, r8
0x1800138dd  mov     rbx, rdx
0x1800138e0  mov     r14, rcx
0x1800138e3  test    rcx, rcx
0x1800138e6  jz      loc_1800139C0
0x1800138ec  test    rdx, rdx
0x1800138ef  jz      loc_1800139C0
0x1800138f5  test    r9, r9
0x1800138f8  jnz     short loc_180013904
0x1800138fa  mov     eax, 80004003h
0x1800138ff  jmp     loc_1800139C5
0x180013904  mov     qword ptr [r9], 0
0x18001390b  cmp     dword ptr [r8], 0
0x18001390f  jnz     short loc_180013949
0x180013911  cmp     dword ptr [r8+4], 0
0x180013916  jnz     short loc_180013949
0x180013918  cmp     dword ptr [r8+8], 0C0h
0x180013920  jnz     short loc_180013949
0x180013922  cmp     dword ptr [r8+0Ch], 46000000h
0x18001392a  jnz     short loc_180013949
0x18001392c  mov     rbx, [rdx+8]
0x180013930  add     rbx, r14
0x180013933  mov     rcx, rbx
0x180013936  mov     rax, [rbx]
0x180013939  mov     rax, [rax+8]
0x18001393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013942  xor     eax, eax
0x180013944  mov     [rsi], rbx
0x180013947  jmp     short loc_1800139C5
0x180013949  cmp     qword ptr [rdx+10h], 0
0x18001394e  jz      short loc_1800139B0
0x180013950  mov     rcx, [rbx]
0x180013953  test    rcx, rcx
0x180013956  jnz     short loc_18001395D
0x180013958  lea     ebp, [rcx+1]
0x18001395b  jmp     short loc_18001397D
0x18001395d  mov     eax, [rdi]
0x18001395f  cmp     [rcx], eax
0x180013961  jnz     short loc_1800139A5
0x180013963  mov     eax, [rdi+4]
0x180013966  cmp     [rcx+4], eax
0x180013969  jnz     short loc_1800139A5
0x18001396b  mov     eax, [rdi+8]
0x18001396e  cmp     [rcx+8], eax
0x180013971  jnz     short loc_1800139A5
0x180013973  mov     eax, [rdi+0Ch]
0x180013976  cmp     [rcx+0Ch], eax
0x180013979  jnz     short loc_1800139A5
0x18001397b  xor     ebp, ebp
0x18001397d  mov     rax, [rbx+10h]
0x180013981  cmp     rax, 1
0x180013985  jz      short loc_1800139B7
0x180013987  mov     r9, [rbx+8]
0x18001398b  mov     r8, rsi
0x18001398e  mov     rdx, rdi
0x180013991  mov     rcx, r14
0x180013994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013999  test    eax, eax
0x18001399b  jz      short loc_1800139C5
0x18001399d  test    ebp, ebp
0x18001399f  jnz     short loc_1800139A5
0x1800139a1  test    eax, eax
0x1800139a3  js      short loc_1800139C5
0x1800139a5  add     rbx, 18h
0x1800139a9  cmp     qword ptr [rbx+10h], 0
0x1800139ae  jnz     short loc_180013950
0x1800139b0  mov     eax, 80004002h
0x1800139b5  jmp     short loc_1800139C5
0x1800139b7  mov     rbx, [rbx+8]
0x1800139bb  jmp     loc_180013930
0x1800139c0  mov     eax, 80070057h
0x1800139c5  add     rsp, 30h
0x1800139c9  pop     r14
0x1800139cb  pop     rdi
0x1800139cc  pop     rsi
0x1800139cd  pop     rbp
0x1800139ce  pop     rbx
0x1800139cf  retn
```
