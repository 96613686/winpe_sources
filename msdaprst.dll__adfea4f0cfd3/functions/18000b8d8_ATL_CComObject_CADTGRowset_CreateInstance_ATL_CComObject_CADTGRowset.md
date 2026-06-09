# ATL::CComObject<CADTGRowset>::CreateInstance(ATL::CComObject<CADTGRowset> * *)

- ea: `0x18000b8d8`
- end: `0x18000b97e`
- name: `?CreateInstance@?$CComObject@VCADTGRowset@@@ATL@@SAJPEAPEAV12@@Z`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e86c`
- `0x180014bd0`

## callees

- `0x180001dd4`
- `0x18000a42c`
- `0x18000b8d8`
- `0x180020e3c`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CADTGRowset>::CreateInstance(CRowset **a1, unsigned int a2)
{
  unsigned int v4; // esi
  CADTGRowset *v5; // rax
  CRowset *v6; // rbx
  unsigned int v7; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = -2147024882;
  v5 = (CADTGRowset *)MMMAlloc(0x2C8u, a2);
  v6 = v5;
  if ( v5 )
  {
    try
    {
      CADTGRowset::CADTGRowset(v5);
      *(_QWORD *)v6 = &ATL::CComObject<CADTGRowset>::`vftable';
      _InterlockedIncrement(&dword_1800464E8);
    }
    catch ( long v7 )
    {
      return v7;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v4 = CRowset::FinalConstruct(v6);
    if ( v4 )
    {
      (*(void (__fastcall **)(CRowset *, __int64))(*(_QWORD *)v6 + 128LL))(v6, 1);
      v6 = 0;
    }
  }
  *a1 = v6;
  return v4;
}

```

## disassembly

```asm
0x18000b8d8  mov     [rsp+arg_8], rbx
0x18000b8dd  mov     [rsp+arg_10], rsi
0x18000b8e2  push    rdi
0x18000b8e3  sub     rsp, 30h
0x18000b8e7  mov     rdi, rcx
0x18000b8ea  test    rcx, rcx
0x18000b8ed  jnz     short loc_18000B8F6
0x18000b8ef  mov     eax, 80004003h
0x18000b8f4  jmp     short loc_18000B96D
0x18000b8f6  mov     qword ptr [rcx], 0
0x18000b8fd  mov     esi, 8007000Eh
0x18000b902  mov     ecx, 2C8h; unsigned int
0x18000b907  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b90c  mov     rbx, rax
0x18000b90f  mov     [rsp+38h+arg_0], rax
0x18000b914  test    rax, rax
0x18000b917  jz      short loc_18000B934
0x18000b919  mov     rcx, rax; this
0x18000b91c  call    ??0CADTGRowset@@QEAA@XZ; CADTGRowset::CADTGRowset(void)
0x18000b921  lea     rax, ??_7?$CComObject@VCADTGRowset@@@ATL@@6B@; const ATL::CComObject<CADTGRowset>::`vftable'
0x18000b928  mov     [rbx], rax
0x18000b92b  lock inc cs:dword_1800464E8
0x18000b932  jmp     short loc_18000B936
0x18000b934  xor     ebx, ebx
0x18000b936  test    rbx, rbx
0x18000b939  jz      short loc_18000B962
0x18000b93b  mov     rcx, rbx; this
0x18000b93e  call    ?FinalConstruct@CRowset@@QEAAJXZ; CRowset::FinalConstruct(void)
0x18000b943  mov     esi, eax
0x18000b945  test    eax, eax
0x18000b947  jz      short loc_18000B962
0x18000b949  mov     r8, [rbx]
0x18000b94c  mov     edx, 1
0x18000b951  mov     rcx, rbx
0x18000b954  mov     rax, [r8+80h]
0x18000b95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b960  xor     ebx, ebx
0x18000b962  mov     [rdi], rbx
0x18000b965  mov     eax, esi
0x18000b967  jmp     short loc_18000B96D
0x18000b969  mov     eax, [rsp+38h+var_18]
0x18000b96d  mov     rbx, [rsp+38h+arg_8]
0x18000b972  mov     rsi, [rsp+38h+arg_10]
0x18000b977  add     rsp, 30h
0x18000b97b  pop     rdi
0x18000b97c  retn
```
