# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800152bc`
- end: `0x1800153bf`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `259`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x1800133d0`
- `0x180013efc`
- `0x1800152bc`
- `0x1800155d8`
- `0x180015818`
- `0x18002b010`

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
  void *v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = qword_18003BF38;
  if ( qword_18003BF38 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2, *(const struct _GUID **)v9) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v11 = &unk_18003A160;
          v12 = 0;
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
0x1800152bc  push    rbx
0x1800152be  push    rbp
0x1800152bf  push    rsi
0x1800152c0  push    rdi
0x1800152c1  push    r14
0x1800152c3  push    r15
0x1800152c5  sub     rsp, 38h
0x1800152c9  mov     rsi, r9
0x1800152cc  mov     r15, r8
0x1800152cf  mov     rbp, rdx
0x1800152d2  test    r9, r9
0x1800152d5  jnz     short loc_1800152E1
0x1800152d7  mov     eax, 80004003h
0x1800152dc  jmp     loc_1800153B2
0x1800152e1  mov     qword ptr [r9], 0
0x1800152e8  xor     edi, edi
0x1800152ea  mov     rbx, cs:qword_18003BF38
0x1800152f1  test    rbx, rbx
0x1800152f4  jz      loc_180015396
0x1800152fa  jmp     short loc_180015315
0x1800152fc  cmp     [rbx+10h], rdi
0x180015300  jz      short loc_180015311
0x180015302  mov     rdx, [rbx]; struct _GUID *
0x180015305  mov     rcx, rbp; struct _GUID *
0x180015308  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001530d  test    eax, eax
0x18001530f  jnz     short loc_18001531C
0x180015311  add     rbx, 48h ; 'H'
0x180015315  cmp     [rbx], rdi
0x180015318  jnz     short loc_1800152FC
0x18001531a  jmp     short loc_180015396
0x18001531c  lea     r14, [rbx+20h]
0x180015320  cmp     [r14], rdi
0x180015323  jnz     short loc_18001537B
0x180015325  lea     rax, unk_18003A160
0x18001532c  mov     [rsp+68h+var_48], rax
0x180015331  mov     [rsp+68h+var_40], dil
0x180015336  lea     rcx, [rsp+68h+var_48]
0x18001533b  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180015340  mov     edi, eax
0x180015342  test    eax, eax
0x180015344  jns     short loc_180015352
0x180015346  lea     rcx, [rsp+68h+var_48]
0x18001534b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180015350  jmp     short loc_180015396
0x180015352  cmp     qword ptr [r14], 0
0x180015356  jnz     short loc_180015371
0x180015358  mov     r8, r14
0x18001535b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180015362  mov     rcx, [rbx+18h]
0x180015366  mov     rax, [rbx+10h]
0x18001536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001536f  mov     edi, eax
0x180015371  lea     rcx, [rsp+68h+var_48]
0x180015376  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001537b  mov     rcx, [r14]
0x18001537e  test    rcx, rcx
0x180015381  jz      short loc_180015396
0x180015383  mov     rax, [rcx]
0x180015386  mov     r8, rsi
0x180015389  mov     rdx, r15
0x18001538c  mov     rax, [rax]
0x18001538f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015394  mov     edi, eax
0x180015396  cmp     qword ptr [rsi], 0
0x18001539a  jnz     short loc_1800153B0
0x18001539c  test    edi, edi
0x18001539e  jnz     short loc_1800153B0
0x1800153a0  mov     r9, rsi; void **
0x1800153a3  mov     r8, r15; struct _GUID *
0x1800153a6  mov     rdx, rbp; struct _GUID *
0x1800153a9  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800153ae  mov     edi, eax
0x1800153b0  mov     eax, edi
0x1800153b2  add     rsp, 38h
0x1800153b6  pop     r15
0x1800153b8  pop     r14
0x1800153ba  pop     rdi
0x1800153bb  pop     rsi
0x1800153bc  pop     rbp
0x1800153bd  pop     rbx
0x1800153be  retn
```
