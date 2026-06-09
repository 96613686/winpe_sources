# ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002c18`
- end: `0x180002d26`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002bf0`

## callees

- `0x18000115c`
- `0x180002c18`
- `0x180002f5c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  ATL::CAtlModule *v9; // rcx
  volatile signed __int32 *v10; // rdi
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // ecx
  signed __int32 v14; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x48u);
  v8 = v7;
  if ( v7 )
  {
    v9 = ATL::_pAtlModule;
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *((_QWORD *)v7 + 8) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable';
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = v8 + 2;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v11 = *v10;
    }
    while ( v11 != _InterlockedCompareExchange(v10, v11 + 1, v11) );
    v12 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 4));
    if ( v12 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v6 = 0;
    if ( v13 < 0 )
      v6 = v13;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v14 = *v10;
    }
    while ( v14 != _InterlockedCompareExchange(v10, v14 - 1, v14) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180002c18  push    rbx
0x180002c1a  push    rbp
0x180002c1b  push    rsi
0x180002c1c  push    rdi
0x180002c1d  push    r12
0x180002c1f  push    r14
0x180002c21  sub     rsp, 28h
0x180002c25  mov     r14, r8
0x180002c28  mov     rbp, rdx
0x180002c2b  test    r8, r8
0x180002c2e  jnz     short loc_180002C3A
0x180002c30  mov     eax, 80004003h
0x180002c35  jmp     loc_180002D19
0x180002c3a  mov     ecx, 48h ; 'H'; Size
0x180002c3f  mov     qword ptr [r8], 0
0x180002c46  mov     esi, 8007000Eh
0x180002c4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c50  mov     rbx, rax
0x180002c53  test    rax, rax
0x180002c56  jz      loc_180002D17
0x180002c5c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c63  xorps   xmm0, xmm0
0x180002c66  mov     dword ptr [rax+8], 0
0x180002c6d  xor     eax, eax
0x180002c6f  movups  xmmword ptr [rbx+10h], xmm0
0x180002c73  movups  xmmword ptr [rbx+20h], xmm0
0x180002c77  mov     [rbx+30h], rax
0x180002c7b  mov     [rbx+38h], al
0x180002c7e  mov     [rbx+40h], rax
0x180002c82  lea     rax, ??_7?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@6B@; const ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable'
0x180002c89  mov     [rbx], rax
0x180002c8c  mov     rax, [rcx]
0x180002c8f  mov     rax, [rax+8]
0x180002c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c98  lea     rdi, [rbx+8]
0x180002c9c  mov     r12d, 7FFFFFFFh
0x180002ca2  jmp     short loc_180002CAD
0x180002ca4  lea     ecx, [rax+1]
0x180002ca7  lock cmpxchg [rdi], ecx
0x180002cab  jz      short loc_180002CB4
0x180002cad  mov     eax, [rdi]
0x180002caf  cmp     eax, r12d
0x180002cb2  jnz     short loc_180002CA4
0x180002cb4  lea     rcx, [rdi+8]; this
0x180002cb8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002cbd  test    eax, eax
0x180002cbf  js      short loc_180002CC5
0x180002cc1  mov     byte ptr [rdi+30h], 1
0x180002cc5  xor     ecx, ecx
0x180002cc7  test    eax, eax
0x180002cc9  cmovs   ecx, eax
0x180002ccc  xor     esi, esi
0x180002cce  test    ecx, ecx
0x180002cd0  cmovs   esi, ecx
0x180002cd3  jmp     short loc_180002CDE
0x180002cd5  lea     ecx, [rax-1]
0x180002cd8  lock cmpxchg [rdi], ecx
0x180002cdc  jz      short loc_180002CE5
0x180002cde  mov     eax, [rdi]
0x180002ce0  cmp     eax, r12d
0x180002ce3  jnz     short loc_180002CD5
0x180002ce5  test    esi, esi
0x180002ce7  jnz     short loc_180002D03
0x180002ce9  mov     rax, [rbx]
0x180002cec  mov     r8, r14
0x180002cef  mov     rdx, rbp
0x180002cf2  mov     rcx, rbx
0x180002cf5  mov     rax, [rax]
0x180002cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfd  mov     esi, eax
0x180002cff  test    eax, eax
0x180002d01  jz      short loc_180002D17
0x180002d03  mov     r8, [rbx]
0x180002d06  mov     edx, 1
0x180002d0b  mov     rcx, rbx
0x180002d0e  mov     rax, [r8+38h]
0x180002d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d17  mov     eax, esi
0x180002d19  add     rsp, 28h
0x180002d1d  pop     r14
0x180002d1f  pop     r12
0x180002d21  pop     rdi
0x180002d22  pop     rsi
0x180002d23  pop     rbp
0x180002d24  pop     rbx
0x180002d25  retn
```
