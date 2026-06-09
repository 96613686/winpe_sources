# ATL::CComCreator<ATL::CComObject<AuditChannel>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f828`
- end: `0x18000f94f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VAuditChannel@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f510`

## callees

- `0x18000d98c`
- `0x18000f828`
- `0x18001033c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<AuditChannel>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  _BYTE *v8; // rdi
  int v9; // ecx
  int v10; // eax
  _BYTE *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x60u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 4) = 0;
      *(_OWORD *)(v7 + 24) = 0;
      *(_OWORD *)(v7 + 40) = 0;
      *((_QWORD *)v7 + 7) = 0;
      v7[64] = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_QWORD *)v7 + 11) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSink'};
      *((_QWORD *)v7 + 1) = &ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSource'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 24));
    if ( v9 >= 0 )
      v8[64] = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f828  mov     [rsp+arg_10], r8
0x18000f82d  mov     [rsp+arg_8], rdx
0x18000f832  mov     [rsp+arg_0], rcx
0x18000f837  push    rsi
0x18000f838  push    rdi
0x18000f839  push    r14
0x18000f83b  push    r15
0x18000f83d  sub     rsp, 28h
0x18000f841  mov     r14, r8
0x18000f844  mov     r15, rdx
0x18000f847  test    r8, r8
0x18000f84a  jnz     short loc_18000F856
0x18000f84c  mov     eax, 80004003h
0x18000f851  jmp     loc_18000F944
0x18000f856  mov     qword ptr [r8], 0
0x18000f85d  mov     esi, 8007000Eh
0x18000f862  mov     dword ptr [rsp+48h+arg_0], esi
0x18000f866  mov     [rsp+48h+arg_18], 0
0x18000f86f  mov     ecx, 60h ; '`'; Size
0x18000f874  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f879  mov     rdi, rax
0x18000f87c  test    rdi, rdi
0x18000f87f  jz      short loc_18000F8D0
0x18000f881  mov     dword ptr [rax+10h], 0
0x18000f888  xorps   xmm0, xmm0
0x18000f88b  xor     eax, eax
0x18000f88d  movups  xmmword ptr [rdi+18h], xmm0
0x18000f891  movups  xmmword ptr [rdi+28h], xmm0
0x18000f895  mov     [rdi+38h], rax
0x18000f899  mov     [rdi+40h], al
0x18000f89c  mov     [rdi+48h], rax
0x18000f8a0  mov     [rdi+50h], rax
0x18000f8a4  mov     [rdi+58h], rax
0x18000f8a8  lea     rax, ??_7?$CComObject@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSink'}
0x18000f8af  mov     [rdi], rax
0x18000f8b2  lea     rax, ??_7?$CComObject@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSource'}
0x18000f8b9  mov     [rdi+8], rax
0x18000f8bd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f8c4  mov     rax, [rcx]
0x18000f8c7  mov     rax, [rax+8]
0x18000f8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d0  mov     [rsp+48h+arg_18], rdi
0x18000f8d5  jmp     short loc_18000F8EA
0x18000f8d7  mov     r14, [rsp+48h+arg_10]
0x18000f8dc  mov     r15, [rsp+48h+arg_8]
0x18000f8e1  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000f8e5  mov     rdi, [rsp+48h+arg_18]
0x18000f8ea  test    rdi, rdi
0x18000f8ed  jz      short loc_18000F942
0x18000f8ef  lea     rcx, [rdi+18h]; this
0x18000f8f3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000f8f8  mov     ecx, eax
0x18000f8fa  test    eax, eax
0x18000f8fc  js      short loc_18000F902
0x18000f8fe  mov     byte ptr [rdi+40h], 1
0x18000f902  xor     eax, eax
0x18000f904  test    ecx, ecx
0x18000f906  cmovs   eax, ecx
0x18000f909  xor     esi, esi
0x18000f90b  test    eax, eax
0x18000f90d  cmovs   esi, eax
0x18000f910  test    esi, esi
0x18000f912  jnz     short loc_18000F92E
0x18000f914  mov     rax, [rdi]
0x18000f917  mov     r8, r14
0x18000f91a  mov     rdx, r15
0x18000f91d  mov     rcx, rdi
0x18000f920  mov     rax, [rax]
0x18000f923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f928  mov     esi, eax
0x18000f92a  test    eax, eax
0x18000f92c  jz      short loc_18000F942
0x18000f92e  mov     r8, [rdi]
0x18000f931  mov     edx, 1
0x18000f936  mov     rcx, rdi
0x18000f939  mov     rax, [r8+28h]
0x18000f93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f942  mov     eax, esi
0x18000f944  add     rsp, 28h
0x18000f948  pop     r15
0x18000f94a  pop     r14
0x18000f94c  pop     rdi
0x18000f94d  pop     rsi
0x18000f94e  retn
```
