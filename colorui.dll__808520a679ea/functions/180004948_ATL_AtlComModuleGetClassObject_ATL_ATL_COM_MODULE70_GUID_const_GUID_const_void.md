# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180004948`
- end: `0x180004a4e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b7b0`

## callees

- `0x180004948`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800049e5`
- `KERNEL32!EnterCriticalSection` at `0x1800049e5`
- `KERNEL32!LeaveCriticalSection` at `0x180004a10`
- `KERNEL32!LeaveCriticalSection` at `0x180004a10`

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
  for ( i = off_1800212A0[0]; i < off_1800212A8; ++i )
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
            EnterCriticalSection(&stru_1800212B0);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_1800212B0);
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
0x180004948  push    rbx
0x18000494a  push    rbp
0x18000494b  push    rsi
0x18000494c  push    rdi
0x18000494d  push    r14
0x18000494f  sub     rsp, 20h
0x180004953  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000495a  mov     r14, r9
0x18000495d  mov     r9, rdx
0x180004960  mov     rbp, r8
0x180004963  jnz     short loc_18000496F
0x180004965  mov     eax, 8000FFFFh
0x18000496a  jmp     loc_180004A43
0x18000496f  test    r14, r14
0x180004972  jnz     short loc_18000497E
0x180004974  mov     eax, 80004003h
0x180004979  jmp     loc_180004A43
0x18000497e  mov     qword ptr [r14], 0
0x180004985  xor     ebx, ebx
0x180004987  mov     rcx, cs:off_1800212A0
0x18000498e  mov     r8, cs:off_1800212A8
0x180004995  jmp     short loc_1800049CE
0x180004997  mov     rsi, [rcx]
0x18000499a  test    rsi, rsi
0x18000499d  jz      short loc_1800049CA
0x18000499f  cmp     [rsi+10h], rbx
0x1800049a3  jz      short loc_1800049CA
0x1800049a5  mov     rdx, [rsi]
0x1800049a8  mov     eax, [rdx]
0x1800049aa  cmp     [r9], eax
0x1800049ad  jnz     short loc_1800049CA
0x1800049af  mov     eax, [rdx+4]
0x1800049b2  cmp     [r9+4], eax
0x1800049b6  jnz     short loc_1800049CA
0x1800049b8  mov     eax, [rdx+8]
0x1800049bb  cmp     [r9+8], eax
0x1800049bf  jnz     short loc_1800049CA
0x1800049c1  mov     eax, [rdx+0Ch]
0x1800049c4  cmp     [r9+0Ch], eax
0x1800049c8  jz      short loc_1800049D5
0x1800049ca  add     rcx, 8
0x1800049ce  cmp     rcx, r8
0x1800049d1  jb      short loc_180004997
0x1800049d3  jmp     short loc_180004A31
0x1800049d5  lea     rdi, [rsi+20h]
0x1800049d9  cmp     [rdi], rbx
0x1800049dc  jnz     short loc_180004A16
0x1800049de  lea     rcx, stru_1800212B0; lpCriticalSection
0x1800049e5  call    cs:__imp_EnterCriticalSection
0x1800049eb  cmp     [rdi], rbx
0x1800049ee  jnz     short loc_180004A09
0x1800049f0  mov     rcx, [rsi+18h]
0x1800049f4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800049fb  mov     rax, [rsi+10h]
0x1800049ff  mov     r8, rdi
0x180004a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a07  mov     ebx, eax
0x180004a09  lea     rcx, stru_1800212B0; lpCriticalSection
0x180004a10  call    cs:__imp_LeaveCriticalSection
0x180004a16  mov     rcx, [rdi]
0x180004a19  test    rcx, rcx
0x180004a1c  jz      short loc_180004A31
0x180004a1e  mov     rax, [rcx]
0x180004a21  mov     r8, r14
0x180004a24  mov     rdx, rbp
0x180004a27  mov     rax, [rax]
0x180004a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2f  mov     ebx, eax
0x180004a31  cmp     qword ptr [r14], 0
0x180004a35  jnz     short loc_180004A41
0x180004a37  test    ebx, ebx
0x180004a39  mov     eax, 80040111h
0x180004a3e  cmovz   ebx, eax
0x180004a41  mov     eax, ebx
0x180004a43  add     rsp, 20h
0x180004a47  pop     r14
0x180004a49  pop     rdi
0x180004a4a  pop     rsi
0x180004a4b  pop     rbp
0x180004a4c  pop     rbx
0x180004a4d  retn
```
