# CKsOutputPin::GetFormat(_AMMediaType * *)

- ea: `0x180016f60`
- end: `0x180017016`
- name: `?GetFormat@CKsOutputPin@@UEAAJPEAPEAU_AMMediaType@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, struct _AMMediaType **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800129d8`
- `0x180016f60`
- `0x18001ffb0`
- `0x18003e22c`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180016f7c`
- `ole32!CoTaskMemAlloc` at `0x180016f7c`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::GetFormat(CKsOutputPin *this, struct _AMMediaType **a2)
{
  struct _AMMediaType *v4; // rax
  unsigned int *p_Id; // rbx
  int v7; // ebx

  v4 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0((void *)v4, 0, sizeof(struct _AMMediaType));
  p_Id = &this[-1].m_CurrentInterface.Id;
  if ( this->m_pFilter )
  {
    CopyMediaType(*a2, (const struct _AMMediaType *)&this[-1].m_IoQueue);
    if ( p_Id[44] && !(*a2)->cbFormat )
    {
      v7 = -2147024882;
LABEL_9:
      DeleteMediaType(*a2);
      return (unsigned int)v7;
    }
    return 0;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(unsigned int *, _QWORD, _QWORD))(*(_QWORD *)p_Id + 104LL))(
           &this[-1].m_CurrentInterface.Id,
           0,
           *a2);
    if ( v7 < 0 )
      goto LABEL_9;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016f60  mov     [rsp+arg_0], rbx
0x180016f65  mov     [rsp+arg_8], rsi
0x180016f6a  push    rdi
0x180016f6b  sub     rsp, 20h
0x180016f6f  mov     rsi, rcx
0x180016f72  mov     ebx, 58h ; 'X'
0x180016f77  mov     ecx, ebx; cb
0x180016f79  mov     rdi, rdx
0x180016f7c  call    cs:__imp_CoTaskMemAlloc
0x180016f83  nop     dword ptr [rax+rax+00h]
0x180016f88  mov     [rdi], rax
0x180016f8b  test    rax, rax
0x180016f8e  jnz     short loc_180016F97
0x180016f90  mov     eax, 8007000Eh
0x180016f95  jmp     short loc_180017005
0x180016f97  mov     r8, rbx; Size
0x180016f9a  xor     edx, edx; Val
0x180016f9c  mov     rcx, rax; void *
0x180016f9f  call    memset_0
0x180016fa4  lea     rbx, [rsi-1B8h]
0x180016fab  cmp     qword ptr [rbx+208h], 0
0x180016fb3  jz      short loc_180016FE1
0x180016fb5  mov     rcx, [rdi]; struct _AMMediaType *
0x180016fb8  lea     rdx, [rsi-150h]; const struct _AMMediaType *
0x180016fbf  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180016fc4  cmp     dword ptr [rbx+0B0h], 0
0x180016fcb  jz      short loc_180016FDD
0x180016fcd  mov     rax, [rdi]
0x180016fd0  cmp     dword ptr [rax+48h], 0
0x180016fd4  jnz     short loc_180016FDD
0x180016fd6  mov     ebx, 8007000Eh
0x180016fdb  jmp     short loc_180016FFB
0x180016fdd  xor     ebx, ebx
0x180016fdf  jmp     short loc_180017003
0x180016fe1  mov     rax, [rbx]
0x180016fe4  xor     edx, edx
0x180016fe6  mov     r8, [rdi]
0x180016fe9  mov     rcx, rbx
0x180016fec  mov     rax, [rax+68h]
0x180016ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ff5  mov     ebx, eax
0x180016ff7  test    eax, eax
0x180016ff9  jns     short loc_180017003
0x180016ffb  mov     rcx, [rdi]; pv
0x180016ffe  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180017003  mov     eax, ebx
0x180017005  mov     rbx, [rsp+28h+arg_0]
0x18001700a  mov     rsi, [rsp+28h+arg_8]
0x18001700f  add     rsp, 20h
0x180017013  pop     rdi
0x180017014  retn
```
