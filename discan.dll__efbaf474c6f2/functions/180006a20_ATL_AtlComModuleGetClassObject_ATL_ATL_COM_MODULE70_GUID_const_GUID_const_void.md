# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006a20`
- end: `0x180006b2c`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800078b0`

## callees

- `0x180004a74`
- `0x18000697c`
- `0x180006a20`
- `0x18000756c`
- `0x180039010`

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
  for ( i = off_180047850; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180047858; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = qword_180047860;
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
0x180006a20  push    rbx
0x180006a22  push    rbp
0x180006a23  push    rsi
0x180006a24  push    rdi
0x180006a25  push    r14
0x180006a27  sub     rsp, 30h
0x180006a2b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180006a32  mov     r14, r9
0x180006a35  mov     r9, rdx
0x180006a38  mov     rbp, r8
0x180006a3b  jnz     short loc_180006A47
0x180006a3d  mov     eax, 8000FFFFh
0x180006a42  jmp     loc_180006B21
0x180006a47  test    r14, r14
0x180006a4a  jnz     short loc_180006A56
0x180006a4c  mov     eax, 80004003h
0x180006a51  jmp     loc_180006B21
0x180006a56  mov     qword ptr [r14], 0
0x180006a5d  xor     ebx, ebx
0x180006a5f  mov     r8, cs:off_180047850
0x180006a66  cmp     r8, cs:off_180047858
0x180006a6d  jnb     loc_180006B0F
0x180006a73  mov     rdi, [r8]
0x180006a76  test    rdi, rdi
0x180006a79  jz      short loc_180006A90
0x180006a7b  cmp     [rdi+10h], rbx
0x180006a7f  jz      short loc_180006A90
0x180006a81  mov     rdx, [rdi]; struct _GUID *
0x180006a84  mov     rcx, r9; struct _GUID *
0x180006a87  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006a8c  test    eax, eax
0x180006a8e  jnz     short loc_180006A96
0x180006a90  add     r8, 8
0x180006a94  jmp     short loc_180006A66
0x180006a96  lea     rsi, [rdi+20h]
0x180006a9a  cmp     [rsi], rbx
0x180006a9d  jnz     short loc_180006AF4
0x180006a9f  lea     rax, qword_180047860
0x180006aa6  mov     [rsp+58h+var_30], bl
0x180006aaa  lea     rcx, [rsp+58h+var_38]
0x180006aaf  mov     [rsp+58h+var_38], rax
0x180006ab4  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180006ab9  mov     ebx, eax
0x180006abb  test    eax, eax
0x180006abd  jns     short loc_180006ACB
0x180006abf  lea     rcx, [rsp+58h+var_38]
0x180006ac4  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006ac9  jmp     short loc_180006B0F
0x180006acb  cmp     qword ptr [rsi], 0
0x180006acf  jnz     short loc_180006AEA
0x180006ad1  mov     rcx, [rdi+18h]
0x180006ad5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006adc  mov     rax, [rdi+10h]
0x180006ae0  mov     r8, rsi
0x180006ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae8  mov     ebx, eax
0x180006aea  lea     rcx, [rsp+58h+var_38]
0x180006aef  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006af4  mov     rcx, [rsi]
0x180006af7  test    rcx, rcx
0x180006afa  jz      short loc_180006B0F
0x180006afc  mov     rax, [rcx]
0x180006aff  mov     r8, r14
0x180006b02  mov     rdx, rbp
0x180006b05  mov     rax, [rax]
0x180006b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0d  mov     ebx, eax
0x180006b0f  cmp     qword ptr [r14], 0
0x180006b13  jnz     short loc_180006B1F
0x180006b15  test    ebx, ebx
0x180006b17  mov     eax, 80040111h
0x180006b1c  cmovz   ebx, eax
0x180006b1f  mov     eax, ebx
0x180006b21  add     rsp, 30h
0x180006b25  pop     r14
0x180006b27  pop     rdi
0x180006b28  pop     rsi
0x180006b29  pop     rbp
0x180006b2a  pop     rbx
0x180006b2b  retn
```
