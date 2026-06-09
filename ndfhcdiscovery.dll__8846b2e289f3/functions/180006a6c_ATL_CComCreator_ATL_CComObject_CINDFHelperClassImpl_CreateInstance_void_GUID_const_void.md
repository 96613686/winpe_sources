# ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006a6c`
- end: `0x180006b7c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCINDFHelperClassImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `272`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007260`
- `0x180008a20`
- `0x18000b2f0`

## callees

- `0x1800012e0`
- `0x180006a6c`
- `0x1800079f0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  int v8; // ecx
  int v9; // eax
  _DWORD *v10; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = operator new(0x48u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_BYTE *)v6 + 56) = 0;
      *((_QWORD *)v6 + 8) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<CINDFHelperClassImpl>::`vftable';
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 4));
    if ( v8 >= 0 )
      *((_BYTE *)v7 + 56) = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5
      || (v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(
                 v7,
                 &GUID_3ae836f6_bb90_41a1_9fa4_f9b285b82d6f,
                 v3)) != 0 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 152LL))(v7, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006a6c  mov     [rsp+arg_10], r8
0x180006a71  mov     [rsp+arg_8], rdx
0x180006a76  mov     [rsp+arg_0], rcx
0x180006a7b  push    rsi
0x180006a7c  push    rdi
0x180006a7d  push    r14
0x180006a7f  sub     rsp, 20h
0x180006a83  mov     r14, r8
0x180006a86  test    r8, r8
0x180006a89  jnz     short loc_180006A95
0x180006a8b  mov     eax, 80004003h
0x180006a90  jmp     loc_180006B72
0x180006a95  mov     qword ptr [r8], 0
0x180006a9c  mov     esi, 8007000Eh
0x180006aa1  mov     dword ptr [rsp+38h+arg_8], esi
0x180006aa5  mov     [rsp+38h+arg_0], 0
0x180006aae  mov     ecx, 48h ; 'H'; Size
0x180006ab3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ab8  mov     rdi, rax
0x180006abb  test    rdi, rdi
0x180006abe  jz      short loc_180006AFC
0x180006ac0  mov     dword ptr [rax+8], 0
0x180006ac7  xorps   xmm0, xmm0
0x180006aca  xor     eax, eax
0x180006acc  movups  xmmword ptr [rdi+10h], xmm0
0x180006ad0  movups  xmmword ptr [rdi+20h], xmm0
0x180006ad4  mov     [rdi+30h], rax
0x180006ad8  mov     [rdi+38h], al
0x180006adb  mov     [rdi+40h], rax
0x180006adf  lea     rax, ??_7?$CComObject@VCINDFHelperClassImpl@@@ATL@@6B@; const ATL::CComObject<CINDFHelperClassImpl>::`vftable'
0x180006ae6  mov     [rdi], rax
0x180006ae9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006af0  mov     rax, [rcx]
0x180006af3  mov     rax, [rax+8]
0x180006af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afc  mov     [rsp+38h+arg_0], rdi
0x180006b01  jmp     short loc_180006B11
0x180006b03  mov     r14, [rsp+38h+arg_10]
0x180006b08  mov     esi, dword ptr [rsp+38h+arg_8]
0x180006b0c  mov     rdi, [rsp+38h+arg_0]
0x180006b11  test    rdi, rdi
0x180006b14  jz      short loc_180006B70
0x180006b16  lea     rcx, [rdi+10h]; this
0x180006b1a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006b1f  mov     ecx, eax
0x180006b21  test    eax, eax
0x180006b23  js      short loc_180006B29
0x180006b25  mov     byte ptr [rdi+38h], 1
0x180006b29  xor     eax, eax
0x180006b2b  test    ecx, ecx
0x180006b2d  cmovs   eax, ecx
0x180006b30  xor     esi, esi
0x180006b32  test    eax, eax
0x180006b34  cmovs   esi, eax
0x180006b37  test    esi, esi
0x180006b39  jnz     short loc_180006B59
0x180006b3b  mov     rax, [rdi]
0x180006b3e  mov     r8, r14
0x180006b41  lea     rdx, _GUID_3ae836f6_bb90_41a1_9fa4_f9b285b82d6f
0x180006b48  mov     rcx, rdi
0x180006b4b  mov     rax, [rax]
0x180006b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b53  mov     esi, eax
0x180006b55  test    eax, eax
0x180006b57  jz      short loc_180006B70
0x180006b59  mov     r8, [rdi]
0x180006b5c  mov     edx, 1
0x180006b61  mov     rcx, rdi
0x180006b64  mov     rax, [r8+98h]
0x180006b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b70  mov     eax, esi
0x180006b72  add     rsp, 20h
0x180006b76  pop     r14
0x180006b78  pop     rdi
0x180006b79  pop     rsi
0x180006b7a  retn
```
