# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a21c`
- end: `0x18000a321`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `261`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bd50`

## callees

- `0x180003bac`
- `0x180008c48`
- `0x180009834`
- `0x18000a21c`
- `0x18000a4f8`
- `0x18000d010`

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
  v9 = qword_180012928;
  if ( qword_180012928 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && (unsigned int)InlineIsEqualGUID(a2) )
      {
        v10 = (ATL::CComModule **)(v9 + 32);
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v11 = qword_1800121C0;
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
0x18000a21c  push    rbx
0x18000a21e  push    rbp
0x18000a21f  push    rsi
0x18000a220  push    rdi
0x18000a221  push    r14
0x18000a223  push    r15
0x18000a225  sub     rsp, 38h
0x18000a229  mov     rsi, r9
0x18000a22c  mov     r15, r8
0x18000a22f  mov     rbp, rdx
0x18000a232  test    r9, r9
0x18000a235  jnz     short loc_18000A241
0x18000a237  mov     eax, 80004003h
0x18000a23c  jmp     loc_18000A314
0x18000a241  mov     qword ptr [r9], 0
0x18000a248  xor     edi, edi
0x18000a24a  mov     rbx, cs:qword_180012928
0x18000a251  test    rbx, rbx
0x18000a254  jz      loc_18000A2F8
0x18000a25a  mov     rdx, [rbx]
0x18000a25d  test    rdx, rdx
0x18000a260  jz      loc_18000A2F8
0x18000a266  cmp     [rbx+10h], rdi
0x18000a26a  jz      short loc_18000A278
0x18000a26c  mov     rcx, rbp
0x18000a26f  call    InlineIsEqualGUID
0x18000a274  test    eax, eax
0x18000a276  jnz     short loc_18000A27E
0x18000a278  add     rbx, 48h ; 'H'
0x18000a27c  jmp     short loc_18000A25A
0x18000a27e  lea     r14, [rbx+20h]
0x18000a282  cmp     [r14], rdi
0x18000a285  jnz     short loc_18000A2DD
0x18000a287  lea     rax, qword_1800121C0
0x18000a28e  mov     [rsp+68h+var_48], rax
0x18000a293  mov     [rsp+68h+var_40], dil
0x18000a298  lea     rcx, [rsp+68h+var_48]
0x18000a29d  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000a2a2  mov     edi, eax
0x18000a2a4  test    eax, eax
0x18000a2a6  jns     short loc_18000A2B4
0x18000a2a8  lea     rcx, [rsp+68h+var_48]
0x18000a2ad  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a2b2  jmp     short loc_18000A2F8
0x18000a2b4  cmp     qword ptr [r14], 0
0x18000a2b8  jnz     short loc_18000A2D3
0x18000a2ba  mov     r8, r14
0x18000a2bd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a2c4  mov     rcx, [rbx+18h]
0x18000a2c8  mov     rax, [rbx+10h]
0x18000a2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d1  mov     edi, eax
0x18000a2d3  lea     rcx, [rsp+68h+var_48]
0x18000a2d8  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a2dd  mov     rcx, [r14]
0x18000a2e0  test    rcx, rcx
0x18000a2e3  jz      short loc_18000A2F8
0x18000a2e5  mov     rax, [rcx]
0x18000a2e8  mov     r8, rsi
0x18000a2eb  mov     rdx, r15
0x18000a2ee  mov     rax, [rax]
0x18000a2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f6  mov     edi, eax
0x18000a2f8  cmp     qword ptr [rsi], 0
0x18000a2fc  jnz     short loc_18000A312
0x18000a2fe  test    edi, edi
0x18000a300  jnz     short loc_18000A312
0x18000a302  mov     r9, rsi; void **
0x18000a305  mov     r8, r15; struct _GUID *
0x18000a308  mov     rdx, rbp; struct _GUID *
0x18000a30b  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000a310  mov     edi, eax
0x18000a312  mov     eax, edi
0x18000a314  add     rsp, 38h
0x18000a318  pop     r15
0x18000a31a  pop     r14
0x18000a31c  pop     rdi
0x18000a31d  pop     rsi
0x18000a31e  pop     rbp
0x18000a31f  pop     rbx
0x18000a320  retn
```
