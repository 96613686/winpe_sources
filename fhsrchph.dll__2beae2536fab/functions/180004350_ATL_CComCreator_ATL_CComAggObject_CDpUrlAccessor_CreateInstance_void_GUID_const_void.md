# ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004350`
- end: `0x1800044d3`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDpUrlAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `387`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004210`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x180004350`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  char *v8; // rax
  _BYTE *v9; // rdi
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  _BYTE *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0xF8u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDpUrlAccessor>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 14) = 7;
      *((_QWORD *)v8 + 13) = 0;
      *((_WORD *)v8 + 44) = 0;
      *((_QWORD *)v8 + 19) = 7;
      *((_QWORD *)v8 + 18) = 0;
      *((_WORD *)v8 + 64) = 0;
      *((_QWORD *)v8 + 24) = 7;
      *((_QWORD *)v8 + 23) = 0;
      *((_WORD *)v8 + 84) = 0;
      *((_QWORD *)v8 + 29) = 7;
      *((_QWORD *)v8 + 28) = 0;
      *((_WORD *)v8 + 104) = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CDpUrlAccessor>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 40));
    if ( v10 >= 0 )
      v9[80] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180004350  mov     [rsp+arg_0], rbx
0x180004355  mov     [rsp+arg_10], r8
0x18000435a  mov     [rsp+arg_8], rdx
0x18000435f  push    rsi
0x180004360  push    rdi
0x180004361  push    r12
0x180004363  push    r14
0x180004365  push    r15
0x180004367  sub     rsp, 30h
0x18000436b  mov     r14, r8
0x18000436e  mov     r15, rdx
0x180004371  mov     r12, rcx
0x180004374  xor     ebx, ebx
0x180004376  test    r8, r8
0x180004379  jnz     short loc_180004385
0x18000437b  mov     eax, 80004003h
0x180004380  jmp     loc_1800044C1
0x180004385  mov     [r8], rbx
0x180004388  mov     esi, 8007000Eh
0x18000438d  mov     [rsp+58h+arg_18], esi
0x180004391  mov     [rsp+58h+var_38], rbx
0x180004396  mov     ecx, 0F8h; Size
0x18000439b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043a0  mov     rdi, rax
0x1800043a3  test    rax, rax
0x1800043a6  jz      loc_180004441
0x1800043ac  mov     [rax+8], ebx
0x1800043af  lea     rax, ??_7?$CComAggObject@VCDpUrlAccessor@@@ATL@@6B@; const ATL::CComAggObject<CDpUrlAccessor>::`vftable'
0x1800043b6  mov     [rdi], rax
0x1800043b9  xorps   xmm0, xmm0
0x1800043bc  xor     eax, eax
0x1800043be  movups  xmmword ptr [rdi+28h], xmm0
0x1800043c2  movups  xmmword ptr [rdi+38h], xmm0
0x1800043c6  mov     [rdi+48h], rax
0x1800043ca  mov     [rdi+50h], bl
0x1800043cd  mov     eax, 7
0x1800043d2  mov     [rdi+70h], rax
0x1800043d6  mov     [rdi+68h], rbx
0x1800043da  mov     [rdi+58h], bx
0x1800043de  mov     [rdi+98h], rax
0x1800043e5  mov     [rdi+90h], rbx
0x1800043ec  mov     [rdi+80h], bx
0x1800043f3  mov     [rdi+0C0h], rax
0x1800043fa  mov     [rdi+0B8h], rbx
0x180004401  mov     [rdi+0A8h], bx
0x180004408  mov     [rdi+0E8h], rax
0x18000440f  mov     [rdi+0E0h], rbx
0x180004416  mov     [rdi+0D0h], bx
0x18000441d  lea     rax, ??_7?$CComContainedObject@VCDpUrlAccessor@@@ATL@@6B@; const ATL::CComContainedObject<CDpUrlAccessor>::`vftable'
0x180004424  mov     [rdi+18h], rax
0x180004428  mov     [rdi+20h], r12
0x18000442c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004433  mov     rax, [rcx]
0x180004436  mov     rax, [rax+8]
0x18000443a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443f  jmp     short loc_180004444
0x180004441  mov     rdi, rbx
0x180004444  mov     [rsp+58h+var_38], rdi
0x180004449  jmp     short loc_180004460
0x18000444b  xor     ebx, ebx
0x18000444d  mov     r14, [rsp+58h+arg_10]
0x180004452  mov     r15, [rsp+58h+arg_8]
0x180004457  mov     esi, [rsp+58h+arg_18]
0x18000445b  mov     rdi, [rsp+58h+var_38]
0x180004460  test    rdi, rdi
0x180004463  jz      short loc_1800044BF
0x180004465  lea     rcx, [rdi+28h]; this
0x180004469  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000446e  mov     ecx, eax
0x180004470  test    eax, eax
0x180004472  js      short loc_180004478
0x180004474  mov     byte ptr [rdi+50h], 1
0x180004478  mov     eax, ebx
0x18000447a  test    ecx, ecx
0x18000447c  cmovs   eax, ecx
0x18000447f  mov     ecx, ebx
0x180004481  test    eax, eax
0x180004483  cmovs   ecx, eax
0x180004486  mov     esi, ebx
0x180004488  test    ecx, ecx
0x18000448a  cmovs   esi, ecx
0x18000448d  test    esi, esi
0x18000448f  jnz     short loc_1800044AB
0x180004491  mov     rax, [rdi]
0x180004494  mov     r8, r14
0x180004497  mov     rdx, r15
0x18000449a  mov     rcx, rdi
0x18000449d  mov     rax, [rax]
0x1800044a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a5  mov     esi, eax
0x1800044a7  test    eax, eax
0x1800044a9  jz      short loc_1800044BF
0x1800044ab  mov     r8, [rdi]
0x1800044ae  mov     edx, 1
0x1800044b3  mov     rcx, rdi
0x1800044b6  mov     rax, [r8+18h]
0x1800044ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bf  mov     eax, esi
0x1800044c1  mov     rbx, [rsp+58h+arg_0]
0x1800044c6  add     rsp, 30h
0x1800044ca  pop     r15
0x1800044cc  pop     r14
0x1800044ce  pop     r12
0x1800044d0  pop     rdi
0x1800044d1  pop     rsi
0x1800044d2  retn
```
