# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a65c`
- end: `0x18000a761`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c580`

## callees

- `0x180008884`
- `0x180009594`
- `0x18000a65c`
- `0x18000a994`
- `0x18000a9f0`
- `0x18001c010`

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
  v9 = qword_1800280C8;
  if ( qword_1800280C8 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2, *(const struct _GUID **)v9) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v11 = qword_1800275A0;
          v12 = 0;
          v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v11);
          if ( v8 < 0 )
          {
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v11);
            break;
          }
          if ( !*v10 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                   *(_QWORD *)(v9 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v9 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v11);
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
0x18000a65c  push    rbx
0x18000a65e  push    rbp
0x18000a65f  push    rsi
0x18000a660  push    rdi
0x18000a661  push    r14
0x18000a663  push    r15
0x18000a665  sub     rsp, 38h
0x18000a669  mov     rsi, r9
0x18000a66c  mov     r15, r8
0x18000a66f  mov     rbp, rdx
0x18000a672  test    r9, r9
0x18000a675  jnz     short loc_18000A681
0x18000a677  mov     eax, 80004003h
0x18000a67c  jmp     loc_18000A754
0x18000a681  mov     qword ptr [r9], 0
0x18000a688  xor     edi, edi
0x18000a68a  mov     rbx, cs:qword_1800280C8
0x18000a691  test    rbx, rbx
0x18000a694  jz      loc_18000A738
0x18000a69a  mov     rdx, [rbx]; struct _GUID *
0x18000a69d  test    rdx, rdx
0x18000a6a0  jz      loc_18000A738
0x18000a6a6  cmp     [rbx+10h], rdi
0x18000a6aa  jz      short loc_18000A6B8
0x18000a6ac  mov     rcx, rbp; struct _GUID *
0x18000a6af  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000a6b4  test    eax, eax
0x18000a6b6  jnz     short loc_18000A6BE
0x18000a6b8  add     rbx, 48h ; 'H'
0x18000a6bc  jmp     short loc_18000A69A
0x18000a6be  lea     r14, [rbx+20h]
0x18000a6c2  cmp     [r14], rdi
0x18000a6c5  jnz     short loc_18000A71D
0x18000a6c7  lea     rax, qword_1800275A0
0x18000a6ce  mov     [rsp+68h+var_48], rax
0x18000a6d3  mov     [rsp+68h+var_40], dil
0x18000a6d8  lea     rcx, [rsp+68h+var_48]
0x18000a6dd  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000a6e2  mov     edi, eax
0x18000a6e4  test    eax, eax
0x18000a6e6  jns     short loc_18000A6F4
0x18000a6e8  lea     rcx, [rsp+68h+var_48]
0x18000a6ed  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a6f2  jmp     short loc_18000A738
0x18000a6f4  cmp     qword ptr [r14], 0
0x18000a6f8  jnz     short loc_18000A713
0x18000a6fa  mov     r8, r14
0x18000a6fd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a704  mov     rcx, [rbx+18h]
0x18000a708  mov     rax, [rbx+10h]
0x18000a70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a711  mov     edi, eax
0x18000a713  lea     rcx, [rsp+68h+var_48]
0x18000a718  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a71d  mov     rcx, [r14]
0x18000a720  test    rcx, rcx
0x18000a723  jz      short loc_18000A738
0x18000a725  mov     rax, [rcx]
0x18000a728  mov     r8, rsi
0x18000a72b  mov     rdx, r15
0x18000a72e  mov     rax, [rax]
0x18000a731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a736  mov     edi, eax
0x18000a738  cmp     qword ptr [rsi], 0
0x18000a73c  jnz     short loc_18000A752
0x18000a73e  test    edi, edi
0x18000a740  jnz     short loc_18000A752
0x18000a742  mov     r9, rsi; void **
0x18000a745  mov     r8, r15; struct _GUID *
0x18000a748  mov     rdx, rbp; struct _GUID *
0x18000a74b  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000a750  mov     edi, eax
0x18000a752  mov     eax, edi
0x18000a754  add     rsp, 38h
0x18000a758  pop     r15
0x18000a75a  pop     r14
0x18000a75c  pop     rdi
0x18000a75d  pop     rsi
0x18000a75e  pop     rbp
0x18000a75f  pop     rbx
0x18000a760  retn
```
