# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000cc54`
- end: `0x18000cd59`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `261`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e530`

## callees

- `0x18000798c`
- `0x18000bcc4`
- `0x18000c678`
- `0x18000cc54`
- `0x18000ced4`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::GetClassObject(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v8; // edi
  __int64 v9; // rbx
  ATL::CComModule **v10; // r14
  __int64 *v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = qword_18002A7F8;
  if ( qword_18002A7F8 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2, *(const struct _GUID **)v9) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v12 = 0;
          v11 = qword_180029180;
          v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v11);
          if ( v8 < 0 )
          {
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v11);
            break;
          }
          if ( !*v10 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                   *(_QWORD *)(v9 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v9 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v11);
        }
        this = *v10;
        if ( *v10 )
          v8 = (**(__int64 (__fastcall ***)(ATL::CComModule *, const struct _GUID *, void **))this)(this, a3, a4);
        break;
      }
      v9 += 72;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)ATL::AtlComModuleGetClassObject(this, a2, a3, a4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000cc54  push    rbx
0x18000cc56  push    rbp
0x18000cc57  push    rsi
0x18000cc58  push    rdi
0x18000cc59  push    r14
0x18000cc5b  push    r15
0x18000cc5d  sub     rsp, 38h
0x18000cc61  mov     rsi, r9
0x18000cc64  mov     r15, r8
0x18000cc67  mov     rbp, rdx
0x18000cc6a  test    r9, r9
0x18000cc6d  jnz     short loc_18000CC79
0x18000cc6f  mov     eax, 80004003h
0x18000cc74  jmp     loc_18000CD4C
0x18000cc79  mov     qword ptr [r9], 0
0x18000cc80  xor     edi, edi
0x18000cc82  mov     rbx, cs:qword_18002A7F8
0x18000cc89  test    rbx, rbx
0x18000cc8c  jz      loc_18000CD30
0x18000cc92  mov     rdx, [rbx]; struct _GUID *
0x18000cc95  test    rdx, rdx
0x18000cc98  jz      loc_18000CD30
0x18000cc9e  cmp     [rbx+10h], rdi
0x18000cca2  jz      short loc_18000CCB0
0x18000cca4  mov     rcx, rbp; struct _GUID *
0x18000cca7  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ccac  test    eax, eax
0x18000ccae  jnz     short loc_18000CCB6
0x18000ccb0  add     rbx, 48h ; 'H'
0x18000ccb4  jmp     short loc_18000CC92
0x18000ccb6  lea     r14, [rbx+20h]
0x18000ccba  cmp     [r14], rdi
0x18000ccbd  jnz     short loc_18000CD15
0x18000ccbf  lea     rax, qword_180029180
0x18000ccc6  mov     [rsp+68h+var_40], dil
0x18000cccb  lea     rcx, [rsp+68h+var_48]
0x18000ccd0  mov     [rsp+68h+var_48], rax
0x18000ccd5  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000ccda  mov     edi, eax
0x18000ccdc  test    eax, eax
0x18000ccde  jns     short loc_18000CCEC
0x18000cce0  lea     rcx, [rsp+68h+var_48]
0x18000cce5  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000ccea  jmp     short loc_18000CD30
0x18000ccec  cmp     qword ptr [r14], 0
0x18000ccf0  jnz     short loc_18000CD0B
0x18000ccf2  mov     rcx, [rbx+18h]
0x18000ccf6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000ccfd  mov     rax, [rbx+10h]
0x18000cd01  mov     r8, r14
0x18000cd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd09  mov     edi, eax
0x18000cd0b  lea     rcx, [rsp+68h+var_48]
0x18000cd10  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000cd15  mov     rcx, [r14]
0x18000cd18  test    rcx, rcx
0x18000cd1b  jz      short loc_18000CD30
0x18000cd1d  mov     rax, [rcx]
0x18000cd20  mov     r8, rsi
0x18000cd23  mov     rdx, r15
0x18000cd26  mov     rax, [rax]
0x18000cd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd2e  mov     edi, eax
0x18000cd30  cmp     qword ptr [rsi], 0
0x18000cd34  jnz     short loc_18000CD4A
0x18000cd36  test    edi, edi
0x18000cd38  jnz     short loc_18000CD4A
0x18000cd3a  mov     r9, rsi; void **
0x18000cd3d  mov     r8, r15; struct _GUID *
0x18000cd40  mov     rdx, rbp; struct _GUID *
0x18000cd43  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000cd48  mov     edi, eax
0x18000cd4a  mov     eax, edi
0x18000cd4c  add     rsp, 38h
0x18000cd50  pop     r15
0x18000cd52  pop     r14
0x18000cd54  pop     rdi
0x18000cd55  pop     rsi
0x18000cd56  pop     rbp
0x18000cd57  pop     rbx
0x18000cd58  retn
```
