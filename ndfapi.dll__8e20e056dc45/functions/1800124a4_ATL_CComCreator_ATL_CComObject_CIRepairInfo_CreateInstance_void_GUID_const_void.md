# ATL::CComCreator<ATL::CComObject<CIRepairInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800124a4`
- end: `0x1800125de`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016810`

## callees

- `0x1800018c0`
- `0x1800058fc`
- `0x1800124a4`
- `0x18001d5d0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIRepairInfo>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  char *v6; // rax
  _BYTE *v7; // rbx
  int v8; // ecx
  int v9; // eax
  _BYTE *v10; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (char *)operator new(0x68u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      v6[56] = 0;
      *(_QWORD *)v6 = &CIRepairInfo::`vftable';
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)(v6 + 96));
      *(_QWORD *)v7 = &ATL::CComObject<CIRepairInfo>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v10;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 >= 0 )
      v7[56] = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5
      || (v5 = (**(__int64 (__fastcall ***)(_BYTE *, GUID *, _QWORD *))v7)(
                 v7,
                 &GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba,
                 v3)) != 0 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v7 + 120LL))(v7, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800124a4  mov     [rsp+arg_10], r8
0x1800124a9  mov     [rsp+arg_8], rdx
0x1800124ae  mov     [rsp+arg_0], rcx
0x1800124b3  push    rbx
0x1800124b4  push    rsi
0x1800124b5  push    r14
0x1800124b7  sub     rsp, 20h
0x1800124bb  mov     r14, r8
0x1800124be  test    r8, r8
0x1800124c1  jnz     short loc_1800124CD
0x1800124c3  mov     eax, 80004003h
0x1800124c8  jmp     loc_1800125D5
0x1800124cd  mov     qword ptr [r8], 0
0x1800124d4  mov     esi, 8007000Eh
0x1800124d9  mov     dword ptr [rsp+38h+arg_8], esi
0x1800124dd  mov     [rsp+38h+arg_0], 0
0x1800124e6  mov     ecx, 68h ; 'h'; Size
0x1800124eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800124f0  mov     rbx, rax
0x1800124f3  mov     [rsp+38h+arg_18], rax
0x1800124f8  test    rbx, rbx
0x1800124fb  jz      short loc_180012562
0x1800124fd  mov     dword ptr [rax+8], 0
0x180012504  xorps   xmm0, xmm0
0x180012507  xor     eax, eax
0x180012509  movups  xmmword ptr [rbx+10h], xmm0
0x18001250d  movups  xmmword ptr [rbx+20h], xmm0
0x180012511  mov     [rbx+30h], rax
0x180012515  mov     [rbx+38h], al
0x180012518  lea     rax, ??_7CIRepairInfo@@6B@; const CIRepairInfo::`vftable'
0x18001251f  mov     [rbx], rax
0x180012522  mov     qword ptr [rbx+40h], 0
0x18001252a  mov     qword ptr [rbx+48h], 0
0x180012532  mov     qword ptr [rbx+50h], 0
0x18001253a  lea     rcx, [rbx+60h]; this
0x18001253e  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x180012543  nop
0x180012544  lea     rax, ??_7?$CComObject@VCIRepairInfo@@@ATL@@6B@; const ATL::CComObject<CIRepairInfo>::`vftable'
0x18001254b  mov     [rbx], rax
0x18001254e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012555  mov     rax, [rcx]
0x180012558  mov     rax, [rax+8]
0x18001255c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012561  nop
0x180012562  mov     [rsp+38h+arg_0], rbx
0x180012567  jmp     short loc_180012577
0x180012569  mov     r14, [rsp+38h+arg_10]
0x18001256e  mov     esi, dword ptr [rsp+38h+arg_8]
0x180012572  mov     rbx, [rsp+38h+arg_0]
0x180012577  test    rbx, rbx
0x18001257a  jz      short loc_1800125D3
0x18001257c  lea     rcx, [rbx+10h]; this
0x180012580  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180012585  mov     ecx, eax
0x180012587  test    eax, eax
0x180012589  js      short loc_18001258F
0x18001258b  mov     byte ptr [rbx+38h], 1
0x18001258f  xor     eax, eax
0x180012591  test    ecx, ecx
0x180012593  cmovs   eax, ecx
0x180012596  xor     esi, esi
0x180012598  test    eax, eax
0x18001259a  cmovs   esi, eax
0x18001259d  test    esi, esi
0x18001259f  jnz     short loc_1800125BF
0x1800125a1  mov     rax, [rbx]
0x1800125a4  mov     r8, r14
0x1800125a7  lea     rdx, _GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba
0x1800125ae  mov     rcx, rbx
0x1800125b1  mov     rax, [rax]
0x1800125b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b9  mov     esi, eax
0x1800125bb  test    eax, eax
0x1800125bd  jz      short loc_1800125D3
0x1800125bf  mov     r8, [rbx]
0x1800125c2  mov     edx, 1
0x1800125c7  mov     rcx, rbx
0x1800125ca  mov     rax, [r8+78h]
0x1800125ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d3  mov     eax, esi
0x1800125d5  add     rsp, 20h
0x1800125d9  pop     r14
0x1800125db  pop     rsi
0x1800125dc  pop     rbx
0x1800125dd  retn
```
