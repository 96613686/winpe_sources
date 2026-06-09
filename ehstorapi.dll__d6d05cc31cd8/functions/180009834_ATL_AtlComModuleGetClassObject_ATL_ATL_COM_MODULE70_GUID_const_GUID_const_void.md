# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180009834`
- end: `0x180009940`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a21c`

## callees

- `0x180003bac`
- `0x180008c48`
- `0x180009834`
- `0x18000a4f8`
- `0x18000d010`

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
  for ( i = (__int64 *)off_1800121B0[0]; i < (__int64 *)off_1800121B8; ++i )
  {
    v10 = *i;
    if ( *i && *(_QWORD *)(v10 + 16) && (unsigned int)InlineIsEqualGUID(v5) )
    {
      v11 = (_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(v10 + 32) )
      {
        v13 = 0;
        v12 = qword_1800121C0;
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
0x180009834  push    rbx
0x180009836  push    rbp
0x180009837  push    rsi
0x180009838  push    rdi
0x180009839  push    r14
0x18000983b  sub     rsp, 30h
0x18000983f  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180009846  mov     r14, r9
0x180009849  mov     r9, rdx
0x18000984c  mov     rbp, r8
0x18000984f  jnz     short loc_18000985B
0x180009851  mov     eax, 8000FFFFh
0x180009856  jmp     loc_180009935
0x18000985b  test    r14, r14
0x18000985e  jnz     short loc_18000986A
0x180009860  mov     eax, 80004003h
0x180009865  jmp     loc_180009935
0x18000986a  mov     qword ptr [r14], 0
0x180009871  xor     ebx, ebx
0x180009873  mov     r8, cs:off_1800121B0
0x18000987a  cmp     r8, cs:off_1800121B8
0x180009881  jnb     loc_180009923
0x180009887  mov     rdi, [r8]
0x18000988a  test    rdi, rdi
0x18000988d  jz      short loc_1800098A4
0x18000988f  cmp     [rdi+10h], rbx
0x180009893  jz      short loc_1800098A4
0x180009895  mov     rdx, [rdi]
0x180009898  mov     rcx, r9
0x18000989b  call    InlineIsEqualGUID
0x1800098a0  test    eax, eax
0x1800098a2  jnz     short loc_1800098AA
0x1800098a4  add     r8, 8
0x1800098a8  jmp     short loc_18000987A
0x1800098aa  lea     rsi, [rdi+20h]
0x1800098ae  cmp     [rsi], rbx
0x1800098b1  jnz     short loc_180009908
0x1800098b3  lea     rax, qword_1800121C0
0x1800098ba  mov     [rsp+58h+var_30], bl
0x1800098be  lea     rcx, [rsp+58h+var_38]
0x1800098c3  mov     [rsp+58h+var_38], rax
0x1800098c8  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800098cd  mov     ebx, eax
0x1800098cf  test    eax, eax
0x1800098d1  jns     short loc_1800098DF
0x1800098d3  lea     rcx, [rsp+58h+var_38]
0x1800098d8  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800098dd  jmp     short loc_180009923
0x1800098df  cmp     qword ptr [rsi], 0
0x1800098e3  jnz     short loc_1800098FE
0x1800098e5  mov     rcx, [rdi+18h]
0x1800098e9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800098f0  mov     rax, [rdi+10h]
0x1800098f4  mov     r8, rsi
0x1800098f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fc  mov     ebx, eax
0x1800098fe  lea     rcx, [rsp+58h+var_38]
0x180009903  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180009908  mov     rcx, [rsi]
0x18000990b  test    rcx, rcx
0x18000990e  jz      short loc_180009923
0x180009910  mov     rax, [rcx]
0x180009913  mov     r8, r14
0x180009916  mov     rdx, rbp
0x180009919  mov     rax, [rax]
0x18000991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009921  mov     ebx, eax
0x180009923  cmp     qword ptr [r14], 0
0x180009927  jnz     short loc_180009933
0x180009929  test    ebx, ebx
0x18000992b  mov     eax, 80040111h
0x180009930  cmovz   ebx, eax
0x180009933  mov     eax, ebx
0x180009935  add     rsp, 30h
0x180009939  pop     r14
0x18000993b  pop     rdi
0x18000993c  pop     rsi
0x18000993d  pop     rbp
0x18000993e  pop     rbx
0x18000993f  retn
```
