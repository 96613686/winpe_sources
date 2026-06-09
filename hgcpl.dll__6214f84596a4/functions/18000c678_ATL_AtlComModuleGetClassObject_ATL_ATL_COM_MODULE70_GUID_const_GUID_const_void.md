# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000c678`
- end: `0x18000c784`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `int(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000cc54`

## callees

- `0x18000798c`
- `0x18000bcc4`
- `0x18000c678`
- `0x18000ced4`
- `0x18001a010`

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
  __int64 *i; // r8
  __int64 v10; // rdi
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
  for ( i = off_180029170[0]; i < off_180029178; ++i )
  {
    v10 = *i;
    if ( *i && *(_QWORD *)(v10 + 16) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(v10 + 32) )
      {
        v13 = 0;
        v12 = qword_180029180;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                 *(_QWORD *)(v10 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 v10 + 32);
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v12);
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
0x18000c678  push    rbx
0x18000c67a  push    rbp
0x18000c67b  push    rsi
0x18000c67c  push    rdi
0x18000c67d  push    r14
0x18000c67f  sub     rsp, 30h
0x18000c683  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000c68a  mov     r14, r9
0x18000c68d  mov     r9, rdx
0x18000c690  mov     rbp, r8
0x18000c693  jnz     short loc_18000C69F
0x18000c695  mov     eax, 8000FFFFh
0x18000c69a  jmp     loc_18000C779
0x18000c69f  test    r14, r14
0x18000c6a2  jnz     short loc_18000C6AE
0x18000c6a4  mov     eax, 80004003h
0x18000c6a9  jmp     loc_18000C779
0x18000c6ae  mov     qword ptr [r14], 0
0x18000c6b5  xor     ebx, ebx
0x18000c6b7  mov     r8, cs:off_180029170
0x18000c6be  cmp     r8, cs:off_180029178
0x18000c6c5  jnb     loc_18000C767
0x18000c6cb  mov     rdi, [r8]
0x18000c6ce  test    rdi, rdi
0x18000c6d1  jz      short loc_18000C6E8
0x18000c6d3  cmp     [rdi+10h], rbx
0x18000c6d7  jz      short loc_18000C6E8
0x18000c6d9  mov     rdx, [rdi]; struct _GUID *
0x18000c6dc  mov     rcx, r9; struct _GUID *
0x18000c6df  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000c6e4  test    eax, eax
0x18000c6e6  jnz     short loc_18000C6EE
0x18000c6e8  add     r8, 8
0x18000c6ec  jmp     short loc_18000C6BE
0x18000c6ee  lea     rsi, [rdi+20h]
0x18000c6f2  cmp     [rsi], rbx
0x18000c6f5  jnz     short loc_18000C74C
0x18000c6f7  lea     rax, qword_180029180
0x18000c6fe  mov     [rsp+58h+var_30], bl
0x18000c702  lea     rcx, [rsp+58h+var_38]
0x18000c707  mov     [rsp+58h+var_38], rax
0x18000c70c  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000c711  mov     ebx, eax
0x18000c713  test    eax, eax
0x18000c715  jns     short loc_18000C723
0x18000c717  lea     rcx, [rsp+58h+var_38]
0x18000c71c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000c721  jmp     short loc_18000C767
0x18000c723  cmp     qword ptr [rsi], 0
0x18000c727  jnz     short loc_18000C742
0x18000c729  mov     rcx, [rdi+18h]
0x18000c72d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c734  mov     rax, [rdi+10h]
0x18000c738  mov     r8, rsi
0x18000c73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c740  mov     ebx, eax
0x18000c742  lea     rcx, [rsp+58h+var_38]
0x18000c747  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000c74c  mov     rcx, [rsi]
0x18000c74f  test    rcx, rcx
0x18000c752  jz      short loc_18000C767
0x18000c754  mov     rax, [rcx]
0x18000c757  mov     r8, r14
0x18000c75a  mov     rdx, rbp
0x18000c75d  mov     rax, [rax]
0x18000c760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c765  mov     ebx, eax
0x18000c767  cmp     qword ptr [r14], 0
0x18000c76b  jnz     short loc_18000C777
0x18000c76d  test    ebx, ebx
0x18000c76f  mov     eax, 80040111h
0x18000c774  cmovz   ebx, eax
0x18000c777  mov     eax, ebx
0x18000c779  add     rsp, 30h
0x18000c77d  pop     r14
0x18000c77f  pop     rdi
0x18000c780  pop     rsi
0x18000c781  pop     rbp
0x18000c782  pop     rbx
0x18000c783  retn
```
