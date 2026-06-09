# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000e7c8`
- end: `0x18000e8ce`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012f60`

## callees

- `0x18000e7c8`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e865`
- `KERNEL32!EnterCriticalSection` at `0x18000e865`
- `KERNEL32!LeaveCriticalSection` at `0x18000e890`
- `KERNEL32!LeaveCriticalSection` at `0x18000e890`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_1800243F0[0]; i < off_1800243F8; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x18000e7c8  push    rbx
0x18000e7ca  push    rbp
0x18000e7cb  push    rsi
0x18000e7cc  push    rdi
0x18000e7cd  push    r14
0x18000e7cf  sub     rsp, 20h
0x18000e7d3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000e7da  mov     r14, r9
0x18000e7dd  mov     r9, rdx
0x18000e7e0  mov     rbp, r8
0x18000e7e3  jnz     short loc_18000E7EF
0x18000e7e5  mov     eax, 8000FFFFh
0x18000e7ea  jmp     loc_18000E8C3
0x18000e7ef  test    r14, r14
0x18000e7f2  jnz     short loc_18000E7FE
0x18000e7f4  mov     eax, 80004003h
0x18000e7f9  jmp     loc_18000E8C3
0x18000e7fe  mov     qword ptr [r14], 0
0x18000e805  xor     ebx, ebx
0x18000e807  mov     rcx, cs:off_1800243F0
0x18000e80e  mov     r8, cs:off_1800243F8
0x18000e815  jmp     short loc_18000E84E
0x18000e817  mov     rsi, [rcx]
0x18000e81a  test    rsi, rsi
0x18000e81d  jz      short loc_18000E84A
0x18000e81f  cmp     [rsi+10h], rbx
0x18000e823  jz      short loc_18000E84A
0x18000e825  mov     rdx, [rsi]
0x18000e828  mov     eax, [rdx]
0x18000e82a  cmp     [r9], eax
0x18000e82d  jnz     short loc_18000E84A
0x18000e82f  mov     eax, [rdx+4]
0x18000e832  cmp     [r9+4], eax
0x18000e836  jnz     short loc_18000E84A
0x18000e838  mov     eax, [rdx+8]
0x18000e83b  cmp     [r9+8], eax
0x18000e83f  jnz     short loc_18000E84A
0x18000e841  mov     eax, [rdx+0Ch]
0x18000e844  cmp     [r9+0Ch], eax
0x18000e848  jz      short loc_18000E855
0x18000e84a  add     rcx, 8
0x18000e84e  cmp     rcx, r8
0x18000e851  jb      short loc_18000E817
0x18000e853  jmp     short loc_18000E8B1
0x18000e855  lea     rdi, [rsi+20h]
0x18000e859  cmp     [rdi], rbx
0x18000e85c  jnz     short loc_18000E896
0x18000e85e  lea     rcx, CriticalSection; lpCriticalSection
0x18000e865  call    cs:__imp_EnterCriticalSection
0x18000e86b  cmp     [rdi], rbx
0x18000e86e  jnz     short loc_18000E889
0x18000e870  mov     rcx, [rsi+18h]
0x18000e874  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000e87b  mov     rax, [rsi+10h]
0x18000e87f  mov     r8, rdi
0x18000e882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e887  mov     ebx, eax
0x18000e889  lea     rcx, CriticalSection; lpCriticalSection
0x18000e890  call    cs:__imp_LeaveCriticalSection
0x18000e896  mov     rcx, [rdi]
0x18000e899  test    rcx, rcx
0x18000e89c  jz      short loc_18000E8B1
0x18000e89e  mov     rax, [rcx]
0x18000e8a1  mov     r8, r14
0x18000e8a4  mov     rdx, rbp
0x18000e8a7  mov     rax, [rax]
0x18000e8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8af  mov     ebx, eax
0x18000e8b1  cmp     qword ptr [r14], 0
0x18000e8b5  jnz     short loc_18000E8C1
0x18000e8b7  test    ebx, ebx
0x18000e8b9  mov     eax, 80040111h
0x18000e8be  cmovz   ebx, eax
0x18000e8c1  mov     eax, ebx
0x18000e8c3  add     rsp, 20h
0x18000e8c7  pop     r14
0x18000e8c9  pop     rdi
0x18000e8ca  pop     rsi
0x18000e8cb  pop     rbp
0x18000e8cc  pop     rbx
0x18000e8cd  retn
```
