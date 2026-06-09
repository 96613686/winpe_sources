# ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800044dc`
- end: `0x180004620`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDpSearchProtocol@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800041f0`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x1800044dc`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  _DWORD *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x40u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CDpSearchProtocol>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = v8[2];
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = v8[2];
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange(v8 + 2, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 64LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800044dc  mov     [rsp+arg_10], r8
0x1800044e1  mov     [rsp+arg_8], rdx
0x1800044e6  mov     [rsp+arg_0], rcx
0x1800044eb  push    rbx
0x1800044ec  push    rsi
0x1800044ed  push    rdi
0x1800044ee  push    r14
0x1800044f0  push    r15
0x1800044f2  sub     rsp, 20h
0x1800044f6  mov     rsi, r8
0x1800044f9  mov     r14, rdx
0x1800044fc  test    r8, r8
0x1800044ff  jnz     short loc_18000450B
0x180004501  mov     eax, 80004003h
0x180004506  jmp     loc_180004614
0x18000450b  mov     qword ptr [r8], 0
0x180004512  mov     edi, 8007000Eh
0x180004517  mov     dword ptr [rsp+48h+arg_0], edi
0x18000451b  mov     [rsp+48h+arg_18], 0
0x180004524  mov     ecx, 40h ; '@'; Size
0x180004529  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000452e  mov     rbx, rax
0x180004531  test    rbx, rbx
0x180004534  jz      short loc_18000456E
0x180004536  mov     dword ptr [rax+8], 0
0x18000453d  xorps   xmm0, xmm0
0x180004540  xor     eax, eax
0x180004542  movups  xmmword ptr [rbx+10h], xmm0
0x180004546  movups  xmmword ptr [rbx+20h], xmm0
0x18000454a  mov     [rbx+30h], rax
0x18000454e  mov     [rbx+38h], al
0x180004551  lea     rax, ??_7?$CComObject@VCDpSearchProtocol@@@ATL@@6B@; const ATL::CComObject<CDpSearchProtocol>::`vftable'
0x180004558  mov     [rbx], rax
0x18000455b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004562  mov     rax, [rcx]
0x180004565  mov     rax, [rax+8]
0x180004569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456e  mov     [rsp+48h+arg_18], rbx
0x180004573  jmp     short loc_180004588
0x180004575  mov     rsi, [rsp+48h+arg_10]
0x18000457a  mov     r14, [rsp+48h+arg_8]
0x18000457f  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004583  mov     rbx, [rsp+48h+arg_18]
0x180004588  test    rbx, rbx
0x18000458b  jz      loc_180004612
0x180004591  mov     r15d, 7FFFFFFFh
0x180004597  jmp     short loc_1800045A3
0x180004599  lea     ecx, [rax+1]
0x18000459c  lock cmpxchg [rbx+8], ecx
0x1800045a1  jz      short loc_1800045AB
0x1800045a3  mov     eax, [rbx+8]
0x1800045a6  cmp     eax, r15d
0x1800045a9  jnz     short loc_180004599
0x1800045ab  lea     rcx, [rbx+10h]; this
0x1800045af  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800045b4  mov     ecx, eax
0x1800045b6  test    eax, eax
0x1800045b8  js      short loc_1800045BE
0x1800045ba  mov     byte ptr [rbx+38h], 1
0x1800045be  xor     eax, eax
0x1800045c0  test    ecx, ecx
0x1800045c2  cmovs   eax, ecx
0x1800045c5  xor     edi, edi
0x1800045c7  test    eax, eax
0x1800045c9  cmovs   edi, eax
0x1800045cc  jmp     short loc_1800045D8
0x1800045ce  lea     ecx, [rax-1]
0x1800045d1  lock cmpxchg [rbx+8], ecx
0x1800045d6  jz      short loc_1800045E0
0x1800045d8  mov     eax, [rbx+8]
0x1800045db  cmp     eax, r15d
0x1800045de  jnz     short loc_1800045CE
0x1800045e0  test    edi, edi
0x1800045e2  jnz     short loc_1800045FE
0x1800045e4  mov     rax, [rbx]
0x1800045e7  mov     r8, rsi
0x1800045ea  mov     rdx, r14
0x1800045ed  mov     rcx, rbx
0x1800045f0  mov     rax, [rax]
0x1800045f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f8  mov     edi, eax
0x1800045fa  test    eax, eax
0x1800045fc  jz      short loc_180004612
0x1800045fe  mov     r8, [rbx]
0x180004601  mov     edx, 1
0x180004606  mov     rcx, rbx
0x180004609  mov     rax, [r8+40h]
0x18000460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004612  mov     eax, edi
0x180004614  add     rsp, 20h
0x180004618  pop     r15
0x18000461a  pop     r14
0x18000461c  pop     rdi
0x18000461d  pop     rsi
0x18000461e  pop     rbx
0x18000461f  retn
```
