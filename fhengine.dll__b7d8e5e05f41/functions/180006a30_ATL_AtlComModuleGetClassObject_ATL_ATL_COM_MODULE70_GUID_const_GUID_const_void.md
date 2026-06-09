# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006a30`
- end: `0x180006b3c`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x180004f58`
- `0x180006990`
- `0x180006a30`
- `0x18000725c`
- `0x180034010`

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
  for ( i = off_1800401C0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800401C8; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(const struct _GUID **)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = qword_1800401D0;
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
0x180006a30  push    rbx
0x180006a32  push    rbp
0x180006a33  push    rsi
0x180006a34  push    rdi
0x180006a35  push    r14
0x180006a37  sub     rsp, 30h
0x180006a3b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180006a42  mov     r14, r9
0x180006a45  mov     r9, rdx
0x180006a48  mov     rbp, r8
0x180006a4b  jnz     short loc_180006A57
0x180006a4d  mov     eax, 8000FFFFh
0x180006a52  jmp     loc_180006B31
0x180006a57  test    r14, r14
0x180006a5a  jnz     short loc_180006A66
0x180006a5c  mov     eax, 80004003h
0x180006a61  jmp     loc_180006B31
0x180006a66  mov     qword ptr [r14], 0
0x180006a6d  xor     ebx, ebx
0x180006a6f  mov     r8, cs:off_1800401C0
0x180006a76  cmp     r8, cs:off_1800401C8
0x180006a7d  jnb     loc_180006B1F
0x180006a83  mov     rdi, [r8]
0x180006a86  test    rdi, rdi
0x180006a89  jz      short loc_180006AA0
0x180006a8b  cmp     [rdi+10h], rbx
0x180006a8f  jz      short loc_180006AA0
0x180006a91  mov     rdx, [rdi]; struct _GUID *
0x180006a94  mov     rcx, r9; struct _GUID *
0x180006a97  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006a9c  test    eax, eax
0x180006a9e  jnz     short loc_180006AA6
0x180006aa0  add     r8, 8
0x180006aa4  jmp     short loc_180006A76
0x180006aa6  lea     rsi, [rdi+20h]
0x180006aaa  cmp     [rsi], rbx
0x180006aad  jnz     short loc_180006B04
0x180006aaf  lea     rax, qword_1800401D0
0x180006ab6  mov     [rsp+58h+var_30], bl
0x180006aba  lea     rcx, [rsp+58h+var_38]
0x180006abf  mov     [rsp+58h+var_38], rax
0x180006ac4  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180006ac9  mov     ebx, eax
0x180006acb  test    eax, eax
0x180006acd  jns     short loc_180006ADB
0x180006acf  lea     rcx, [rsp+58h+var_38]
0x180006ad4  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006ad9  jmp     short loc_180006B1F
0x180006adb  cmp     qword ptr [rsi], 0
0x180006adf  jnz     short loc_180006AFA
0x180006ae1  mov     rcx, [rdi+18h]
0x180006ae5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006aec  mov     rax, [rdi+10h]
0x180006af0  mov     r8, rsi
0x180006af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af8  mov     ebx, eax
0x180006afa  lea     rcx, [rsp+58h+var_38]
0x180006aff  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006b04  mov     rcx, [rsi]
0x180006b07  test    rcx, rcx
0x180006b0a  jz      short loc_180006B1F
0x180006b0c  mov     rax, [rcx]
0x180006b0f  mov     r8, r14
0x180006b12  mov     rdx, rbp
0x180006b15  mov     rax, [rax]
0x180006b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1d  mov     ebx, eax
0x180006b1f  cmp     qword ptr [r14], 0
0x180006b23  jnz     short loc_180006B2F
0x180006b25  test    ebx, ebx
0x180006b27  mov     eax, 80040111h
0x180006b2c  cmovz   ebx, eax
0x180006b2f  mov     eax, ebx
0x180006b31  add     rsp, 30h
0x180006b35  pop     r14
0x180006b37  pop     rdi
0x180006b38  pop     rsi
0x180006b39  pop     rbp
0x180006b3a  pop     rbx
0x180006b3b  retn
```
