# ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(ATL::CComObject<CHNetPortMappingProtocol> * *)

- ea: `0x180010218`
- end: `0x180010342`
- name: `?CreateInstance@?$CComObject@VCHNetPortMappingProtocol@@@ATL@@SAJPEAPEAV12@@Z`
- size: `298`
- prototype: `__int64 __fastcall(volatile int **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010350`
- `0x180013ab0`
- `0x1800168a0`
- `0x180024790`

## callees

- `0x180001274`
- `0x180008324`
- `0x180009674`
- `0x18000969c`
- `0x180010218`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800102ed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800102ed`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(volatile int **a1)
{
  volatile int **v1; // r14
  unsigned int v3; // esi
  char *v4; // rax
  volatile int *v5; // rdi
  int v6; // ecx
  BSTR v7; // rax
  volatile int *v9; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x68u);
    v5 = (volatile int *)v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 4) = 0;
      *(_OWORD *)(v4 + 24) = 0;
      *(_OWORD *)(v4 + 40) = 0;
      *((_QWORD *)v4 + 7) = 0;
      v4[64] = 0;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      v4[88] = 0;
      *((_QWORD *)v4 + 12) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<CHNetPortMappingProtocol>::`vftable'{for `IHNetPortMappingProtocol'};
      *((_QWORD *)v4 + 1) = &ATL::CComObject<CHNetPortMappingProtocol>::`vftable'{for `IHNetPrivate'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread(v5 + 4);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 6));
    if ( v6 >= 0 )
    {
      v7 = SysAllocString(L"WQL");
      *((_QWORD *)v5 + 12) = v7;
      v6 = -2147024882;
      if ( v7 )
        v6 = 0;
    }
    v3 = 0;
    if ( v6 < 0 )
      v3 = v6;
    ATL::SafeDecrementReferenceMultiThread(v5 + 4);
    if ( v3 )
    {
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v5 + 96LL))(v5, 1);
      v5 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180010218  mov     [rsp+arg_0], rcx
0x18001021d  push    rbx
0x18001021e  push    rsi
0x18001021f  push    rdi
0x180010220  push    r14
0x180010222  push    r15
0x180010224  sub     rsp, 20h
0x180010228  mov     r14, rcx
0x18001022b  xor     ebx, ebx
0x18001022d  test    rcx, rcx
0x180010230  jnz     short loc_18001023C
0x180010232  mov     eax, 80004003h
0x180010237  jmp     loc_180010336
0x18001023c  mov     [rcx], rbx
0x18001023f  mov     esi, 8007000Eh
0x180010244  mov     [rsp+48h+arg_8], esi
0x180010248  mov     [rsp+48h+arg_10], rbx
0x18001024d  mov     ecx, 68h ; 'h'; Size
0x180010252  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010257  mov     rdi, rax
0x18001025a  test    rax, rax
0x18001025d  jz      short loc_1800102AF
0x18001025f  mov     [rax+10h], ebx
0x180010262  xorps   xmm0, xmm0
0x180010265  xor     eax, eax
0x180010267  movups  xmmword ptr [rdi+18h], xmm0
0x18001026b  movups  xmmword ptr [rdi+28h], xmm0
0x18001026f  mov     [rdi+38h], rax
0x180010273  mov     [rdi+40h], bl
0x180010276  mov     [rdi+48h], rbx
0x18001027a  mov     [rdi+50h], rbx
0x18001027e  mov     [rdi+58h], bl
0x180010281  mov     [rdi+60h], rbx
0x180010285  lea     rax, ??_7?$CComObject@VCHNetPortMappingProtocol@@@ATL@@6BIHNetPortMappingProtocol@@@; const ATL::CComObject<CHNetPortMappingProtocol>::`vftable'{for `IHNetPortMappingProtocol'}
0x18001028c  mov     [rdi], rax
0x18001028f  lea     rax, ??_7?$CComObject@VCHNetPortMappingProtocol@@@ATL@@6BIHNetPrivate@@@; const ATL::CComObject<CHNetPortMappingProtocol>::`vftable'{for `IHNetPrivate'}
0x180010296  mov     [rdi+8], rax
0x18001029a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800102a1  mov     rax, [rcx]
0x1800102a4  mov     rax, [rax+8]
0x1800102a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ad  jmp     short loc_1800102B2
0x1800102af  mov     rdi, rbx
0x1800102b2  mov     [rsp+48h+arg_10], rdi
0x1800102b7  jmp     short loc_1800102C9
0x1800102b9  xor     ebx, ebx
0x1800102bb  mov     r14, [rsp+48h+arg_0]
0x1800102c0  mov     esi, [rsp+48h+arg_8]
0x1800102c4  mov     rdi, [rsp+48h+arg_10]
0x1800102c9  test    rdi, rdi
0x1800102cc  jz      short loc_180010331
0x1800102ce  lea     rcx, [rdi+10h]; volatile int *
0x1800102d2  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800102d7  lea     rcx, [rdi+18h]; this
0x1800102db  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800102e0  mov     ecx, eax
0x1800102e2  test    eax, eax
0x1800102e4  js      short loc_180010302
0x1800102e6  lea     rcx, ?c_wszWQL@@3QBGB; "WQL"
0x1800102ed  call    cs:__imp_SysAllocString
0x1800102f3  mov     [rdi+60h], rax
0x1800102f7  mov     ecx, 8007000Eh
0x1800102fc  test    rax, rax
0x1800102ff  cmovnz  ecx, ebx
0x180010302  mov     esi, ebx
0x180010304  test    ecx, ecx
0x180010306  cmovs   esi, ecx
0x180010309  lea     rcx, [rdi+10h]; volatile int *
0x18001030d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180010312  test    esi, esi
0x180010314  jz      short loc_18001032F
0x180010316  mov     rax, [rdi]
0x180010319  mov     edx, 1
0x18001031e  mov     rcx, rdi
0x180010321  mov     rax, [rax+60h]
0x180010325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001032a  mov     rdi, rbx
0x18001032d  jmp     short loc_180010331
0x18001032f  mov     esi, ebx
0x180010331  mov     [r14], rdi
0x180010334  mov     eax, esi
0x180010336  add     rsp, 20h
0x18001033a  pop     r15
0x18001033c  pop     r14
0x18001033e  pop     rdi
0x18001033f  pop     rsi
0x180010340  pop     rbx
0x180010341  retn
```
