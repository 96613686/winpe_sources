# CspDllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003648`
- end: `0x18000371c`
- name: `?CspDllGetClassObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003400`

## callees

- `0x180002fd4`
- `0x180003648`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall CspDllGetClassObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rdx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  unsigned int v10; // ebx

  if ( a3 )
    *a3 = 0;
  v5 = 0;
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)&off_1800390D8 + 2 * v5);
    if ( *v6 == *(_QWORD *)&a1->Data1 && v6[1] == *(_QWORD *)a1->Data4 )
      break;
    if ( (int)++v5 >= 2 )
    {
      if ( v5 == 2 )
        return 2147746065LL;
      break;
    }
  }
  v8 = operator new(0x18u);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v8[2] = 1;
  *(_QWORD *)v8 = &CClassFactory::`vftable';
  *((_QWORD *)v8 + 2) = (char *)&off_1800390D8 + 16 * v5;
  v10 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v8)(v8, a2, a3);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  return v10;
}

```

## disassembly

```asm
0x180003648  mov     [rsp+arg_0], rbx
0x18000364d  mov     [rsp+arg_8], rbp
0x180003652  push    rsi
0x180003653  push    rdi
0x180003654  push    r14
0x180003656  sub     rsp, 20h
0x18000365a  mov     rsi, r8
0x18000365d  mov     rbp, rdx
0x180003660  test    r8, r8
0x180003663  jz      short loc_18000366C
0x180003665  mov     qword ptr [r8], 0
0x18000366c  xor     ebx, ebx
0x18000366e  lea     r14, off_1800390D8
0x180003675  mov     eax, ebx
0x180003677  add     rax, rax
0x18000367a  mov     rdx, [r14+rax*8]
0x18000367e  mov     rax, [rdx]
0x180003681  cmp     rax, [rcx]
0x180003684  jnz     short loc_180003690
0x180003686  mov     rax, [rdx+8]
0x18000368a  cmp     rax, [rcx+8]
0x18000368e  jz      short loc_1800036A0
0x180003690  inc     ebx
0x180003692  cmp     ebx, 2
0x180003695  jl      short loc_180003675
0x180003697  jnz     short loc_1800036A0
0x180003699  mov     eax, 80040111h
0x18000369e  jmp     short loc_180003708
0x1800036a0  mov     ecx, 18h; Size
0x1800036a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036aa  mov     [rsp+38h+arg_10], rax
0x1800036af  mov     rdi, rax
0x1800036b2  test    rax, rax
0x1800036b5  jz      short loc_180003703
0x1800036b7  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800036be  mov     dword ptr [rdi+8], 1
0x1800036c5  mov     [rdi], rax
0x1800036c8  mov     eax, ebx
0x1800036ca  shl     rax, 4
0x1800036ce  add     rax, r14
0x1800036d1  mov     [rdi+10h], rax
0x1800036d5  test    rdi, rdi
0x1800036d8  jz      short loc_180003703
0x1800036da  mov     rax, [rdi]
0x1800036dd  mov     r8, rsi
0x1800036e0  mov     rdx, rbp
0x1800036e3  mov     rcx, rdi
0x1800036e6  mov     rax, [rax]
0x1800036e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ee  mov     rdx, [rdi]
0x1800036f1  mov     ebx, eax
0x1800036f3  mov     rcx, rdi
0x1800036f6  mov     rax, [rdx+10h]
0x1800036fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ff  mov     eax, ebx
0x180003701  jmp     short loc_180003708
0x180003703  mov     eax, 8007000Eh
0x180003708  mov     rbx, [rsp+38h+arg_0]
0x18000370d  mov     rbp, [rsp+38h+arg_8]
0x180003712  add     rsp, 20h
0x180003716  pop     r14
0x180003718  pop     rdi
0x180003719  pop     rsi
0x18000371a  retn
```
