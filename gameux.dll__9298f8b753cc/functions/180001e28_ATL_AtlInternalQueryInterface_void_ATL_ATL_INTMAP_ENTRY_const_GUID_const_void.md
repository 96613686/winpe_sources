# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180001e28`
- end: `0x180001efe`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `int(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180002280`
- `0x180002310`
- `0x180002340`
- `0x180002a80`
- `0x180002b00`
- `0x180002b20`

## callees

- `0x180001e28`
- `0x18000221c`
- `0x180002528`
- `0x180004010`

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
0x180001e28  push    rbx
0x180001e2a  push    rbp
0x180001e2b  push    rsi
0x180001e2c  push    rdi
0x180001e2d  push    r14
0x180001e2f  sub     rsp, 30h
0x180001e33  mov     rdi, r9
0x180001e36  mov     r14, r8
0x180001e39  mov     rbx, rdx
0x180001e3c  mov     rsi, rcx
0x180001e3f  test    rcx, rcx
0x180001e42  jz      loc_180001EEE
0x180001e48  test    rdx, rdx
0x180001e4b  jz      loc_180001EEE
0x180001e51  test    r9, r9
0x180001e54  jnz     short loc_180001E60
0x180001e56  mov     eax, 80004003h
0x180001e5b  jmp     loc_180001EF3
0x180001e60  mov     rcx, r14; struct _GUID *
0x180001e63  mov     qword ptr [r9], 0
0x180001e6a  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180001e6f  test    eax, eax
0x180001e71  jz      short loc_180001E90
0x180001e73  mov     rbx, [rdx+8]
0x180001e77  add     rbx, rsi
0x180001e7a  mov     rcx, rbx
0x180001e7d  mov     rax, [rbx]
0x180001e80  mov     rax, [rax+8]
0x180001e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e89  xor     eax, eax
0x180001e8b  mov     [rdi], rbx
0x180001e8e  jmp     short loc_180001EF3
0x180001e90  mov     r10, [rbx+10h]
0x180001e94  test    r10, r10
0x180001e97  jz      short loc_180001EE7
0x180001e99  mov     rcx, [rbx]
0x180001e9c  test    rcx, rcx
0x180001e9f  jnz     short loc_180001EA6
0x180001ea1  lea     ebp, [rcx+1]
0x180001ea4  jmp     short loc_180001EB4
0x180001ea6  mov     rdx, r14
0x180001ea9  xor     ebp, ebp
0x180001eab  call    InlineIsEqualGUID
0x180001eb0  test    eax, eax
0x180001eb2  jz      short loc_180001EDB
0x180001eb4  cmp     r10, 1
0x180001eb8  jz      short loc_180001EE1
0x180001eba  mov     r9, [rbx+8]
0x180001ebe  mov     r8, rdi
0x180001ec1  mov     rdx, r14
0x180001ec4  mov     rcx, rsi
0x180001ec7  mov     rax, r10
0x180001eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ecf  test    eax, eax
0x180001ed1  jz      short loc_180001EF3
0x180001ed3  test    ebp, ebp
0x180001ed5  jnz     short loc_180001EDB
0x180001ed7  test    eax, eax
0x180001ed9  js      short loc_180001EF3
0x180001edb  add     rbx, 18h
0x180001edf  jmp     short loc_180001E90
0x180001ee1  mov     rbx, [rbx+8]
0x180001ee5  jmp     short loc_180001E77
0x180001ee7  mov     eax, 80004002h
0x180001eec  jmp     short loc_180001EF3
0x180001eee  mov     eax, 80070057h
0x180001ef3  add     rsp, 30h
0x180001ef7  pop     r14
0x180001ef9  pop     rdi
0x180001efa  pop     rsi
0x180001efb  pop     rbp
0x180001efc  pop     rbx
0x180001efd  retn
```
