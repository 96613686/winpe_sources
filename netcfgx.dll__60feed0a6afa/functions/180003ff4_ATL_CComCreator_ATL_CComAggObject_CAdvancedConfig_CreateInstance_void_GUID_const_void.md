# ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003ff4`
- end: `0x18000411a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCAdvancedConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003fe0`

## callees

- `0x180003ff4`
- `0x18000465c`
- `0x180007d38`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  char *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // ecx
  int v11; // eax
  int v12; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)MemAlloc(0x58u);
  v9 = (struct _RTL_CRITICAL_SECTION *)v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CAdvancedConfig>::`vftable';
    *(_OWORD *)(v8 + 40) = 0;
    *(_OWORD *)(v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8[80] = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CAdvancedConfig>::`vftable';
    *((_QWORD *)v8 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init(v9 + 1);
    if ( v10 >= 0 )
      LOBYTE(v9[2].DebugInfo) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7
      || (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                 v9,
                 a2,
                 a3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v9->DebugInfo->ProcessLocksList.Blink)(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003ff4  mov     [rsp+arg_10], r8
0x180003ff9  mov     [rsp+arg_8], rdx
0x180003ffe  push    rbx
0x180003fff  push    rsi
0x180004000  push    rdi
0x180004001  push    r14
0x180004003  push    r15
0x180004005  sub     rsp, 30h
0x180004009  mov     rsi, r8
0x18000400c  mov     r14, rdx
0x18000400f  mov     r15, rcx
0x180004012  test    r8, r8
0x180004015  jnz     short loc_180004021
0x180004017  mov     eax, 80004003h
0x18000401c  jmp     loc_18000410E
0x180004021  mov     qword ptr [r8], 0
0x180004028  mov     edi, 8007000Eh
0x18000402d  mov     [rsp+58h+arg_18], edi
0x180004031  mov     ecx, 58h ; 'X'; unsigned __int64
0x180004036  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000403b  mov     rbx, rax
0x18000403e  mov     [rsp+58h+var_38], rax
0x180004043  test    rax, rax
0x180004046  jz      short loc_180004091
0x180004048  mov     dword ptr [rax+8], 0
0x18000404f  lea     rax, ??_7?$CComAggObject@VCAdvancedConfig@@@ATL@@6B@; const ATL::CComAggObject<CAdvancedConfig>::`vftable'
0x180004056  mov     [rbx], rax
0x180004059  xorps   xmm0, xmm0
0x18000405c  xor     eax, eax
0x18000405e  movups  xmmword ptr [rbx+28h], xmm0
0x180004062  movups  xmmword ptr [rbx+38h], xmm0
0x180004066  mov     [rbx+48h], rax
0x18000406a  mov     [rbx+50h], al
0x18000406d  lea     rax, ??_7?$CComContainedObject@VCAdvancedConfig@@@ATL@@6B@; const ATL::CComContainedObject<CAdvancedConfig>::`vftable'
0x180004074  mov     [rbx+18h], rax
0x180004078  mov     [rbx+20h], r15
0x18000407c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004083  mov     rax, [rcx]
0x180004086  mov     rax, [rax+8]
0x18000408a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408f  jmp     short loc_180004093
0x180004091  xor     ebx, ebx
0x180004093  mov     [rsp+58h+var_38], rbx
0x180004098  jmp     short loc_1800040AD
0x18000409a  mov     rsi, [rsp+58h+arg_10]
0x18000409f  mov     r14, [rsp+58h+arg_8]
0x1800040a4  mov     edi, [rsp+58h+arg_18]
0x1800040a8  mov     rbx, [rsp+58h+var_38]
0x1800040ad  test    rbx, rbx
0x1800040b0  jz      short loc_18000410C
0x1800040b2  lea     rcx, [rbx+28h]; this
0x1800040b6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800040bb  mov     ecx, eax
0x1800040bd  test    eax, eax
0x1800040bf  js      short loc_1800040C5
0x1800040c1  mov     byte ptr [rbx+50h], 1
0x1800040c5  xor     eax, eax
0x1800040c7  test    ecx, ecx
0x1800040c9  cmovs   eax, ecx
0x1800040cc  xor     ecx, ecx
0x1800040ce  test    eax, eax
0x1800040d0  cmovs   ecx, eax
0x1800040d3  xor     edi, edi
0x1800040d5  test    ecx, ecx
0x1800040d7  cmovs   edi, ecx
0x1800040da  test    edi, edi
0x1800040dc  jnz     short loc_1800040F8
0x1800040de  mov     rax, [rbx]
0x1800040e1  mov     r8, rsi
0x1800040e4  mov     rdx, r14
0x1800040e7  mov     rcx, rbx
0x1800040ea  mov     rax, [rax]
0x1800040ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f2  mov     edi, eax
0x1800040f4  test    eax, eax
0x1800040f6  jz      short loc_18000410C
0x1800040f8  mov     r8, [rbx]
0x1800040fb  mov     edx, 1
0x180004100  mov     rcx, rbx
0x180004103  mov     rax, [r8+18h]
0x180004107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410c  mov     eax, edi
0x18000410e  add     rsp, 30h
0x180004112  pop     r15
0x180004114  pop     r14
0x180004116  pop     rdi
0x180004117  pop     rsi
0x180004118  pop     rbx
0x180004119  retn
```
