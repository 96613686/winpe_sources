# ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b28`
- end: `0x180009c77`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWFPClientsHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009b00`

## callees

- `0x180001250`
- `0x1800042bc`
- `0x180009b28`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  char *v7; // rax
  char *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  char *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x48u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 4) = 0;
      *(_OWORD *)(v7 + 24) = 0;
      *(_OWORD *)(v7 + 40) = 0;
      *((_QWORD *)v7 + 7) = 0;
      v7[64] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagExtensibleHelper'};
      *((_QWORD *)v7 + 1) = &ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagHelperInfo'};
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
      v9 = *((_DWORD *)v8 + 4);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 24));
    if ( v10 >= 0 )
      v8[64] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *((_DWORD *)v8 + 4);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009b28  mov     [rsp+arg_10], r8
0x180009b2d  mov     [rsp+arg_8], rdx
0x180009b32  mov     [rsp+arg_0], rcx
0x180009b37  push    rbx
0x180009b38  push    rsi
0x180009b39  push    rdi
0x180009b3a  push    r14
0x180009b3c  push    r15
0x180009b3e  sub     rsp, 20h
0x180009b42  mov     rsi, r8
0x180009b45  mov     r14, rdx
0x180009b48  test    r8, r8
0x180009b4b  jnz     short loc_180009B57
0x180009b4d  mov     eax, 80004003h
0x180009b52  jmp     loc_180009C6B
0x180009b57  mov     qword ptr [r8], 0
0x180009b5e  mov     edi, 8007000Eh
0x180009b63  mov     dword ptr [rsp+48h+arg_0], edi
0x180009b67  mov     [rsp+48h+arg_18], 0
0x180009b70  mov     ecx, 48h ; 'H'; Size
0x180009b75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b7a  mov     rbx, rax
0x180009b7d  test    rbx, rbx
0x180009b80  jz      short loc_180009BC5
0x180009b82  mov     dword ptr [rax+10h], 0
0x180009b89  xorps   xmm0, xmm0
0x180009b8c  xor     eax, eax
0x180009b8e  movups  xmmword ptr [rbx+18h], xmm0
0x180009b92  movups  xmmword ptr [rbx+28h], xmm0
0x180009b96  mov     [rbx+38h], rax
0x180009b9a  mov     [rbx+40h], al
0x180009b9d  lea     rax, ??_7?$CComObject@VCWFPClientsHelperClass@@@ATL@@6BINetDiagExtensibleHelper@@@; const ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagExtensibleHelper'}
0x180009ba4  mov     [rbx], rax
0x180009ba7  lea     rax, ??_7?$CComObject@VCWFPClientsHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180009bae  mov     [rbx+8], rax
0x180009bb2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009bb9  mov     rax, [rcx]
0x180009bbc  mov     rax, [rax+8]
0x180009bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc5  mov     [rsp+48h+arg_18], rbx
0x180009bca  jmp     short loc_180009BDF
0x180009bcc  mov     rsi, [rsp+48h+arg_10]
0x180009bd1  mov     r14, [rsp+48h+arg_8]
0x180009bd6  mov     edi, dword ptr [rsp+48h+arg_0]
0x180009bda  mov     rbx, [rsp+48h+arg_18]
0x180009bdf  test    rbx, rbx
0x180009be2  jz      loc_180009C69
0x180009be8  mov     r15d, 7FFFFFFFh
0x180009bee  jmp     short loc_180009BFA
0x180009bf0  lea     ecx, [rax+1]
0x180009bf3  lock cmpxchg [rbx+10h], ecx
0x180009bf8  jz      short loc_180009C02
0x180009bfa  mov     eax, [rbx+10h]
0x180009bfd  cmp     eax, r15d
0x180009c00  jnz     short loc_180009BF0
0x180009c02  lea     rcx, [rbx+18h]; this
0x180009c06  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009c0b  mov     ecx, eax
0x180009c0d  test    eax, eax
0x180009c0f  js      short loc_180009C15
0x180009c11  mov     byte ptr [rbx+40h], 1
0x180009c15  xor     eax, eax
0x180009c17  test    ecx, ecx
0x180009c19  cmovs   eax, ecx
0x180009c1c  xor     edi, edi
0x180009c1e  test    eax, eax
0x180009c20  cmovs   edi, eax
0x180009c23  jmp     short loc_180009C2F
0x180009c25  lea     ecx, [rax-1]
0x180009c28  lock cmpxchg [rbx+10h], ecx
0x180009c2d  jz      short loc_180009C37
0x180009c2f  mov     eax, [rbx+10h]
0x180009c32  cmp     eax, r15d
0x180009c35  jnz     short loc_180009C25
0x180009c37  test    edi, edi
0x180009c39  jnz     short loc_180009C55
0x180009c3b  mov     rax, [rbx]
0x180009c3e  mov     r8, rsi
0x180009c41  mov     rdx, r14
0x180009c44  mov     rcx, rbx
0x180009c47  mov     rax, [rax]
0x180009c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c4f  mov     edi, eax
0x180009c51  test    eax, eax
0x180009c53  jz      short loc_180009C69
0x180009c55  mov     r8, [rbx]
0x180009c58  mov     edx, 1
0x180009c5d  mov     rcx, rbx
0x180009c60  mov     rax, [r8+20h]
0x180009c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c69  mov     eax, edi
0x180009c6b  add     rsp, 20h
0x180009c6f  pop     r15
0x180009c71  pop     r14
0x180009c73  pop     rdi
0x180009c74  pop     rsi
0x180009c75  pop     rbx
0x180009c76  retn
```
