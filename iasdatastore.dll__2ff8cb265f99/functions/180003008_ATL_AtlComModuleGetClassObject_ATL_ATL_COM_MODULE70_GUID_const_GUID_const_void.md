# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003008`
- end: `0x18000310e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800041ac`

## callees

- `0x180003008`
- `0x180010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800030a5`
- `KERNEL32!EnterCriticalSection` at `0x1800030a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800030d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800030d0`

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
  for ( i = (__int64 *)off_180019190[0]; i < (__int64 *)off_180019198; ++i )
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
0x180003008  push    rbx
0x18000300a  push    rbp
0x18000300b  push    rsi
0x18000300c  push    rdi
0x18000300d  push    r14
0x18000300f  sub     rsp, 20h
0x180003013  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000301a  mov     r14, r9
0x18000301d  mov     r9, rdx
0x180003020  mov     rbp, r8
0x180003023  jnz     short loc_18000302F
0x180003025  mov     eax, 8000FFFFh
0x18000302a  jmp     loc_180003103
0x18000302f  test    r14, r14
0x180003032  jnz     short loc_18000303E
0x180003034  mov     eax, 80004003h
0x180003039  jmp     loc_180003103
0x18000303e  mov     qword ptr [r14], 0
0x180003045  xor     ebx, ebx
0x180003047  mov     rcx, cs:off_180019190
0x18000304e  mov     r8, cs:off_180019198
0x180003055  jmp     short loc_18000308E
0x180003057  mov     rsi, [rcx]
0x18000305a  test    rsi, rsi
0x18000305d  jz      short loc_18000308A
0x18000305f  cmp     [rsi+10h], rbx
0x180003063  jz      short loc_18000308A
0x180003065  mov     rdx, [rsi]
0x180003068  mov     eax, [rdx]
0x18000306a  cmp     [r9], eax
0x18000306d  jnz     short loc_18000308A
0x18000306f  mov     eax, [rdx+4]
0x180003072  cmp     [r9+4], eax
0x180003076  jnz     short loc_18000308A
0x180003078  mov     eax, [rdx+8]
0x18000307b  cmp     [r9+8], eax
0x18000307f  jnz     short loc_18000308A
0x180003081  mov     eax, [rdx+0Ch]
0x180003084  cmp     [r9+0Ch], eax
0x180003088  jz      short loc_180003095
0x18000308a  add     rcx, 8
0x18000308e  cmp     rcx, r8
0x180003091  jb      short loc_180003057
0x180003093  jmp     short loc_1800030F1
0x180003095  lea     rdi, [rsi+20h]
0x180003099  cmp     [rdi], rbx
0x18000309c  jnz     short loc_1800030D6
0x18000309e  lea     rcx, CriticalSection; lpCriticalSection
0x1800030a5  call    cs:__imp_EnterCriticalSection
0x1800030ab  cmp     [rdi], rbx
0x1800030ae  jnz     short loc_1800030C9
0x1800030b0  mov     rcx, [rsi+18h]
0x1800030b4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800030bb  mov     rax, [rsi+10h]
0x1800030bf  mov     r8, rdi
0x1800030c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c7  mov     ebx, eax
0x1800030c9  lea     rcx, CriticalSection; lpCriticalSection
0x1800030d0  call    cs:__imp_LeaveCriticalSection
0x1800030d6  mov     rcx, [rdi]
0x1800030d9  test    rcx, rcx
0x1800030dc  jz      short loc_1800030F1
0x1800030de  mov     rax, [rcx]
0x1800030e1  mov     r8, r14
0x1800030e4  mov     rdx, rbp
0x1800030e7  mov     rax, [rax]
0x1800030ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ef  mov     ebx, eax
0x1800030f1  cmp     qword ptr [r14], 0
0x1800030f5  jnz     short loc_180003101
0x1800030f7  test    ebx, ebx
0x1800030f9  mov     eax, 80040111h
0x1800030fe  cmovz   ebx, eax
0x180003101  mov     eax, ebx
0x180003103  add     rsp, 20h
0x180003107  pop     r14
0x180003109  pop     rdi
0x18000310a  pop     rsi
0x18000310b  pop     rbp
0x18000310c  pop     rbx
0x18000310d  retn
```
