# CWMWriterInputPin::BuildInputTypeList(void)

- ea: `0x1800138bc`
- end: `0x180013a3e`
- name: `?BuildInputTypeList@CWMWriterInputPin@@QEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013354`
- `0x180015218`

## callees

- `0x180001460`
- `0x1800138bc`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180013998`
- `ole32!CoTaskMemAlloc` at `0x180013998`
- `ole32!CoTaskMemFree` at `0x180013924`
- `ole32!CoTaskMemFree` at `0x180013924`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::BuildInputTypeList(CWMWriterInputPin *this)
{
  _DWORD *v1; // rsi
  int i; // ebp
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // rbp
  __int64 v9; // rcx
  LPVOID v10; // rax
  unsigned int j; // ebp
  unsigned int v13; // [rsp+30h] [rbp-38h] BYREF

  v1 = (_DWORD *)((char *)this + 432);
  if ( *((_QWORD *)this + 55) )
  {
    for ( i = 0; i < *v1; *(_QWORD *)(*((_QWORD *)this + 55) + 8 * v4) = 0 )
    {
      v4 = i;
      v5 = *(_QWORD *)(*((_QWORD *)this + 55) + 8LL * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      ++i;
    }
    CoTaskMemFree(*((LPVOID *)this + 55));
    *((_QWORD *)this + 55) = 0;
  }
  v6 = *((_QWORD *)this + 43);
  v7 = 0;
  *v1 = 0;
  v13 = 0;
  if ( !*(_DWORD *)(v6 + 232) )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**(_QWORD **)(v6 + 312) + 72LL))(
           *(_QWORD *)(v6 + 312),
           *((unsigned int *)this + 99),
           &v13);
    if ( v7 >= 0 )
    {
      v8 = *((_QWORD *)this + 56);
      v9 = v13 + 1;
      if ( !v8 )
        v9 = v13;
      v10 = CoTaskMemAlloc(8 * v9);
      *((_QWORD *)this + 55) = v10;
      if ( !v10 )
        return 2147942414LL;
      if ( v8 )
      {
        v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID))this + 56))(
               *((_QWORD *)this + 56),
               &IID_IWMMediaProps,
               v10);
        if ( v7 >= 0 )
          ++*v1;
      }
      for ( j = 0; (int)j < (int)v13; ++j )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 43) + 312LL)
                                                                        + 80LL))(
               *(_QWORD *)(*((_QWORD *)this + 43) + 312LL),
               *((unsigned int *)this + 99),
               j,
               *((_QWORD *)this + 55) + 8LL * *((unsigned int *)this + 108));
        if ( v7 < 0 )
          break;
        ++*v1;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800138bc  push    rbx
0x1800138be  push    rbp
0x1800138bf  push    rsi
0x1800138c0  push    rdi
0x1800138c1  sub     rsp, 48h
0x1800138c5  mov     rax, cs:__security_cookie
0x1800138cc  xor     rax, rsp
0x1800138cf  mov     [rsp+68h+var_30], rax
0x1800138d4  cmp     qword ptr [rcx+1B8h], 0
0x1800138dc  lea     rsi, [rcx+1B0h]
0x1800138e3  mov     rdi, rcx
0x1800138e6  jz      short loc_180013935
0x1800138e8  xor     ebp, ebp
0x1800138ea  cmp     [rsi], ebp
0x1800138ec  jle     short loc_18001391D
0x1800138ee  mov     rax, [rdi+1B8h]
0x1800138f5  movsxd  rbx, ebp
0x1800138f8  mov     rcx, [rax+rbx*8]
0x1800138fc  mov     rax, [rcx]
0x1800138ff  mov     rax, [rax+10h]
0x180013903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013908  mov     rax, [rdi+1B8h]
0x18001390f  inc     ebp
0x180013911  mov     qword ptr [rax+rbx*8], 0
0x180013919  cmp     ebp, [rsi]
0x18001391b  jl      short loc_1800138EE
0x18001391d  mov     rcx, [rdi+1B8h]; pv
0x180013924  call    cs:__imp_CoTaskMemFree
0x18001392a  mov     qword ptr [rdi+1B8h], 0
0x180013935  mov     rcx, [rdi+158h]
0x18001393c  xor     ebx, ebx
0x18001393e  mov     dword ptr [rsi], 0
0x180013944  mov     [rsp+68h+var_38], 0
0x18001394c  cmp     [rcx+0E8h], ebx
0x180013952  jnz     loc_180013A26
0x180013958  mov     rcx, [rcx+138h]
0x18001395f  lea     r8, [rsp+68h+var_38]
0x180013964  mov     edx, [rdi+18Ch]
0x18001396a  mov     rax, [rcx]
0x18001396d  mov     rax, [rax+48h]
0x180013971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013976  mov     ebx, eax
0x180013978  test    eax, eax
0x18001397a  js      loc_180013A26
0x180013980  mov     edx, [rsp+68h+var_38]
0x180013984  mov     rbp, [rdi+1C0h]
0x18001398b  test    rbp, rbp
0x18001398e  lea     ecx, [rdx+1]
0x180013991  cmovz   ecx, edx
0x180013994  shl     rcx, 3; cb
0x180013998  call    cs:__imp_CoTaskMemAlloc
0x18001399e  mov     [rdi+1B8h], rax
0x1800139a5  mov     r8, rax
0x1800139a8  test    rax, rax
0x1800139ab  jnz     short loc_1800139B4
0x1800139ad  mov     eax, 8007000Eh
0x1800139b2  jmp     short loc_180013A28
0x1800139b4  test    rbp, rbp
0x1800139b7  jz      short loc_1800139DA
0x1800139b9  mov     rcx, [rdi+1C0h]
0x1800139c0  lea     rdx, IID_IWMMediaProps
0x1800139c7  mov     rax, [rcx]
0x1800139ca  mov     rax, [rax]
0x1800139cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d2  mov     ebx, eax
0x1800139d4  test    eax, eax
0x1800139d6  js      short loc_1800139DA
0x1800139d8  inc     dword ptr [rsi]
0x1800139da  xor     ebp, ebp
0x1800139dc  cmp     [rsp+68h+var_38], ebp
0x1800139e0  jle     short loc_180013A26
0x1800139e2  mov     rax, [rdi+158h]
0x1800139e9  mov     edx, [rdi+1B0h]
0x1800139ef  mov     rcx, [rax+138h]
0x1800139f6  mov     rax, [rdi+1B8h]
0x1800139fd  mov     r8, [rcx]
0x180013a00  lea     r9, [rax+rdx*8]
0x180013a04  mov     edx, [rdi+18Ch]
0x180013a0a  mov     rax, [r8+50h]
0x180013a0e  mov     r8d, ebp
0x180013a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a16  mov     ebx, eax
0x180013a18  test    eax, eax
0x180013a1a  js      short loc_180013A26
0x180013a1c  inc     dword ptr [rsi]
0x180013a1e  inc     ebp
0x180013a20  cmp     ebp, [rsp+68h+var_38]
0x180013a24  jl      short loc_1800139E2
0x180013a26  mov     eax, ebx
0x180013a28  mov     rcx, [rsp+68h+var_30]
0x180013a2d  xor     rcx, rsp; StackCookie
0x180013a30  call    __security_check_cookie
0x180013a35  add     rsp, 48h
0x180013a39  pop     rdi
0x180013a3a  pop     rsi
0x180013a3b  pop     rbp
0x180013a3c  pop     rbx
0x180013a3d  retn
```
