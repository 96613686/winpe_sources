# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180002f0c`
- end: `0x180003010`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003470`
- `0x180003490`

## callees

- `0x180002f0c`
- `0x180017010`

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
0x180002f0c  push    rbx
0x180002f0e  push    rbp
0x180002f0f  push    rsi
0x180002f10  push    rdi
0x180002f11  push    r14
0x180002f13  sub     rsp, 30h
0x180002f17  mov     rsi, r9
0x180002f1a  mov     rdi, r8
0x180002f1d  mov     rbx, rdx
0x180002f20  mov     r14, rcx
0x180002f23  test    rcx, rcx
0x180002f26  jz      loc_180003000
0x180002f2c  test    rdx, rdx
0x180002f2f  jz      loc_180003000
0x180002f35  test    r9, r9
0x180002f38  jnz     short loc_180002F44
0x180002f3a  mov     eax, 80004003h
0x180002f3f  jmp     loc_180003005
0x180002f44  mov     qword ptr [r9], 0
0x180002f4b  cmp     dword ptr [r8], 0
0x180002f4f  jnz     short loc_180002F89
0x180002f51  cmp     dword ptr [r8+4], 0
0x180002f56  jnz     short loc_180002F89
0x180002f58  cmp     dword ptr [r8+8], 0C0h
0x180002f60  jnz     short loc_180002F89
0x180002f62  cmp     dword ptr [r8+0Ch], 46000000h
0x180002f6a  jnz     short loc_180002F89
0x180002f6c  mov     rbx, [rdx+8]
0x180002f70  add     rbx, r14
0x180002f73  mov     rcx, rbx
0x180002f76  mov     rax, [rbx]
0x180002f79  mov     rax, [rax+8]
0x180002f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f82  xor     eax, eax
0x180002f84  mov     [rsi], rbx
0x180002f87  jmp     short loc_180003005
0x180002f89  cmp     qword ptr [rdx+10h], 0
0x180002f8e  jz      short loc_180002FF0
0x180002f90  mov     rcx, [rbx]
0x180002f93  test    rcx, rcx
0x180002f96  jnz     short loc_180002F9D
0x180002f98  lea     ebp, [rcx+1]
0x180002f9b  jmp     short loc_180002FBD
0x180002f9d  mov     eax, [rdi]
0x180002f9f  cmp     [rcx], eax
0x180002fa1  jnz     short loc_180002FE5
0x180002fa3  mov     eax, [rdi+4]
0x180002fa6  cmp     [rcx+4], eax
0x180002fa9  jnz     short loc_180002FE5
0x180002fab  mov     eax, [rdi+8]
0x180002fae  cmp     [rcx+8], eax
0x180002fb1  jnz     short loc_180002FE5
0x180002fb3  mov     eax, [rdi+0Ch]
0x180002fb6  cmp     [rcx+0Ch], eax
0x180002fb9  jnz     short loc_180002FE5
0x180002fbb  xor     ebp, ebp
0x180002fbd  mov     rax, [rbx+10h]
0x180002fc1  cmp     rax, 1
0x180002fc5  jz      short loc_180002FF7
0x180002fc7  mov     r9, [rbx+8]
0x180002fcb  mov     r8, rsi
0x180002fce  mov     rdx, rdi
0x180002fd1  mov     rcx, r14
0x180002fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd9  test    eax, eax
0x180002fdb  jz      short loc_180003005
0x180002fdd  test    ebp, ebp
0x180002fdf  jnz     short loc_180002FE5
0x180002fe1  test    eax, eax
0x180002fe3  js      short loc_180003005
0x180002fe5  add     rbx, 18h
0x180002fe9  cmp     qword ptr [rbx+10h], 0
0x180002fee  jnz     short loc_180002F90
0x180002ff0  mov     eax, 80004002h
0x180002ff5  jmp     short loc_180003005
0x180002ff7  mov     rbx, [rbx+8]
0x180002ffb  jmp     loc_180002F70
0x180003000  mov     eax, 80070057h
0x180003005  add     rsp, 30h
0x180003009  pop     r14
0x18000300b  pop     rdi
0x18000300c  pop     rsi
0x18000300d  pop     rbp
0x18000300e  pop     rbx
0x18000300f  retn
```
