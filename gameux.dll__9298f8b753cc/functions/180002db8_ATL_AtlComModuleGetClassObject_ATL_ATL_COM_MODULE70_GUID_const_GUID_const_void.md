# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180002db8`
- end: `0x180002ec4`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002ff0`

## callees

- `0x180002528`
- `0x180002cb0`
- `0x180002db8`
- `0x180002f5c`
- `0x180004010`

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
  _RTL_CRITICAL_SECTION *v12; // [rsp+20h] [rbp-38h] BYREF
  char v13; // [rsp+28h] [rbp-30h]

  v5 = a2;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_1800070B0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800070B8; ++i )
  {
    v10 = *i;
    if ( *i && *((_QWORD *)v10 + 2) && (unsigned int)InlineIsEqualGUID(v5, *(_QWORD *)v10) )
    {
      v11 = (_QWORD *)((char *)v10 + 32);
      if ( !*((_QWORD *)v10 + 4) )
      {
        v13 = 0;
        v12 = &stru_1800070C0;
        v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v12);
        if ( v8 < 0 )
        {
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v12);
          break;
        }
        if ( !*v11 )
          v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                 *((_QWORD *)v10 + 3),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (__int64)v10 + 32);
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
0x180002db8  push    rbx
0x180002dba  push    rbp
0x180002dbb  push    rsi
0x180002dbc  push    rdi
0x180002dbd  push    r14
0x180002dbf  sub     rsp, 30h
0x180002dc3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180002dca  mov     r14, r9
0x180002dcd  mov     r9, rdx
0x180002dd0  mov     rbp, r8
0x180002dd3  jnz     short loc_180002DDF
0x180002dd5  mov     eax, 8000FFFFh
0x180002dda  jmp     loc_180002EB9
0x180002ddf  test    r14, r14
0x180002de2  jnz     short loc_180002DEE
0x180002de4  mov     eax, 80004003h
0x180002de9  jmp     loc_180002EB9
0x180002dee  mov     qword ptr [r14], 0
0x180002df5  xor     ebx, ebx
0x180002df7  mov     r8, cs:off_1800070B0
0x180002dfe  cmp     r8, cs:off_1800070B8
0x180002e05  jnb     loc_180002EA7
0x180002e0b  mov     rdi, [r8]
0x180002e0e  test    rdi, rdi
0x180002e11  jz      short loc_180002E28
0x180002e13  cmp     [rdi+10h], rbx
0x180002e17  jz      short loc_180002E28
0x180002e19  mov     rdx, [rdi]
0x180002e1c  mov     rcx, r9
0x180002e1f  call    InlineIsEqualGUID
0x180002e24  test    eax, eax
0x180002e26  jnz     short loc_180002E2E
0x180002e28  add     r8, 8
0x180002e2c  jmp     short loc_180002DFE
0x180002e2e  lea     rsi, [rdi+20h]
0x180002e32  cmp     [rsi], rbx
0x180002e35  jnz     short loc_180002E8C
0x180002e37  lea     rax, stru_1800070C0
0x180002e3e  mov     [rsp+58h+var_30], bl
0x180002e42  lea     rcx, [rsp+58h+var_38]
0x180002e47  mov     [rsp+58h+var_38], rax
0x180002e4c  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180002e51  mov     ebx, eax
0x180002e53  test    eax, eax
0x180002e55  jns     short loc_180002E63
0x180002e57  lea     rcx, [rsp+58h+var_38]
0x180002e5c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180002e61  jmp     short loc_180002EA7
0x180002e63  cmp     qword ptr [rsi], 0
0x180002e67  jnz     short loc_180002E82
0x180002e69  mov     rcx, [rdi+18h]
0x180002e6d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002e74  mov     rax, [rdi+10h]
0x180002e78  mov     r8, rsi
0x180002e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e80  mov     ebx, eax
0x180002e82  lea     rcx, [rsp+58h+var_38]
0x180002e87  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180002e8c  mov     rcx, [rsi]
0x180002e8f  test    rcx, rcx
0x180002e92  jz      short loc_180002EA7
0x180002e94  mov     rax, [rcx]
0x180002e97  mov     r8, r14
0x180002e9a  mov     rdx, rbp
0x180002e9d  mov     rax, [rax]
0x180002ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea5  mov     ebx, eax
0x180002ea7  cmp     qword ptr [r14], 0
0x180002eab  jnz     short loc_180002EB7
0x180002ead  test    ebx, ebx
0x180002eaf  mov     eax, 80040111h
0x180002eb4  cmovz   ebx, eax
0x180002eb7  mov     eax, ebx
0x180002eb9  add     rsp, 30h
0x180002ebd  pop     r14
0x180002ebf  pop     rdi
0x180002ec0  pop     rsi
0x180002ec1  pop     rbp
0x180002ec2  pop     rbx
0x180002ec3  retn
```
