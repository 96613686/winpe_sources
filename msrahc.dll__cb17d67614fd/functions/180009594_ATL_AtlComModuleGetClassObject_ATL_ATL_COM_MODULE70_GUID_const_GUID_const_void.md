# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180009594`
- end: `0x1800096a0`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a65c`

## callees

- `0x180008884`
- `0x180009594`
- `0x18000a994`
- `0x18000a9f0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v5; // r9
  int v8; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // r8
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rdi
  _QWORD *v11; // rsi
  __int64 *v12; // [rsp+20h] [rbp-38h] BYREF
  char v13; // [rsp+28h] [rbp-30h]

  v5 = a2;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_180027590; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180027598; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = qword_1800275A0;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                 *((_QWORD *)v10 + 3),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (__int64)v10 + 32);
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v12);
      }
      if ( *v11 )
        v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v11)(*v11, a3, a4);
      break;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009594  push    rbx
0x180009596  push    rbp
0x180009597  push    rsi
0x180009598  push    rdi
0x180009599  push    r14
0x18000959b  sub     rsp, 30h
0x18000959f  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800095a6  mov     r14, r9
0x1800095a9  mov     r9, rdx
0x1800095ac  mov     rbp, r8
0x1800095af  jnz     short loc_1800095BB
0x1800095b1  mov     eax, 8000FFFFh
0x1800095b6  jmp     loc_180009695
0x1800095bb  test    r14, r14
0x1800095be  jnz     short loc_1800095CA
0x1800095c0  mov     eax, 80004003h
0x1800095c5  jmp     loc_180009695
0x1800095ca  mov     qword ptr [r14], 0
0x1800095d1  xor     ebx, ebx
0x1800095d3  mov     r8, cs:off_180027590
0x1800095da  cmp     r8, cs:off_180027598
0x1800095e1  jnb     loc_180009683
0x1800095e7  mov     rdi, [r8]
0x1800095ea  test    rdi, rdi
0x1800095ed  jz      short loc_180009604
0x1800095ef  cmp     [rdi+10h], rbx
0x1800095f3  jz      short loc_180009604
0x1800095f5  mov     rdx, [rdi]; struct _GUID *
0x1800095f8  mov     rcx, r9; struct _GUID *
0x1800095fb  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009600  test    eax, eax
0x180009602  jnz     short loc_18000960A
0x180009604  add     r8, 8
0x180009608  jmp     short loc_1800095DA
0x18000960a  lea     rsi, [rdi+20h]
0x18000960e  cmp     [rsi], rbx
0x180009611  jnz     short loc_180009668
0x180009613  lea     rax, qword_1800275A0
0x18000961a  mov     [rsp+58h+var_30], bl
0x18000961e  lea     rcx, [rsp+58h+var_38]
0x180009623  mov     [rsp+58h+var_38], rax
0x180009628  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000962d  mov     ebx, eax
0x18000962f  test    eax, eax
0x180009631  jns     short loc_18000963F
0x180009633  lea     rcx, [rsp+58h+var_38]
0x180009638  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000963d  jmp     short loc_180009683
0x18000963f  cmp     qword ptr [rsi], 0
0x180009643  jnz     short loc_18000965E
0x180009645  mov     rcx, [rdi+18h]
0x180009649  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009650  mov     rax, [rdi+10h]
0x180009654  mov     r8, rsi
0x180009657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965c  mov     ebx, eax
0x18000965e  lea     rcx, [rsp+58h+var_38]
0x180009663  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180009668  mov     rcx, [rsi]
0x18000966b  test    rcx, rcx
0x18000966e  jz      short loc_180009683
0x180009670  mov     rax, [rcx]
0x180009673  mov     r8, r14
0x180009676  mov     rdx, rbp
0x180009679  mov     rax, [rax]
0x18000967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009681  mov     ebx, eax
0x180009683  cmp     qword ptr [r14], 0
0x180009687  jnz     short loc_180009693
0x180009689  test    ebx, ebx
0x18000968b  mov     eax, 80040111h
0x180009690  cmovz   ebx, eax
0x180009693  mov     eax, ebx
0x180009695  add     rsp, 30h
0x180009699  pop     r14
0x18000969b  pop     rdi
0x18000969c  pop     rsi
0x18000969d  pop     rbp
0x18000969e  pop     rbx
0x18000969f  retn
```
