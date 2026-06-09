# ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004224`
- end: `0x18000434a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDpSearchProtocol@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800041f0`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x180004224`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  char *v8; // rax
  _BYTE *v9; // rbx
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
    v8 = (char *)operator new(0x58u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDpSearchProtocol>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CDpSearchProtocol>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
0x180004224  mov     [rsp+arg_10], r8
0x180004229  mov     [rsp+arg_8], rdx
0x18000422e  push    rbx
0x18000422f  push    rsi
0x180004230  push    rdi
0x180004231  push    r14
0x180004233  push    r15
0x180004235  sub     rsp, 30h
0x180004239  mov     rsi, r8
0x18000423c  mov     r14, rdx
0x18000423f  mov     r15, rcx
0x180004242  test    r8, r8
0x180004245  jnz     short loc_180004251
0x180004247  mov     eax, 80004003h
0x18000424c  jmp     loc_18000433E
0x180004251  mov     qword ptr [r8], 0
0x180004258  mov     edi, 8007000Eh
0x18000425d  mov     [rsp+58h+arg_18], edi
0x180004261  mov     [rsp+58h+var_38], 0
0x18000426a  mov     ecx, 58h ; 'X'; Size
0x18000426f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004274  mov     rbx, rax
0x180004277  test    rbx, rbx
0x18000427a  jz      short loc_1800042C3
0x18000427c  mov     dword ptr [rax+8], 0
0x180004283  lea     rax, ??_7?$CComAggObject@VCDpSearchProtocol@@@ATL@@6B@; const ATL::CComAggObject<CDpSearchProtocol>::`vftable'
0x18000428a  mov     [rbx], rax
0x18000428d  xorps   xmm0, xmm0
0x180004290  xor     eax, eax
0x180004292  movups  xmmword ptr [rbx+28h], xmm0
0x180004296  movups  xmmword ptr [rbx+38h], xmm0
0x18000429a  mov     [rbx+48h], rax
0x18000429e  mov     [rbx+50h], al
0x1800042a1  lea     rax, ??_7?$CComContainedObject@VCDpSearchProtocol@@@ATL@@6B@; const ATL::CComContainedObject<CDpSearchProtocol>::`vftable'
0x1800042a8  mov     [rbx+18h], rax
0x1800042ac  mov     [rbx+20h], r15
0x1800042b0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800042b7  mov     rax, [rcx]
0x1800042ba  mov     rax, [rax+8]
0x1800042be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c3  mov     [rsp+58h+var_38], rbx
0x1800042c8  jmp     short loc_1800042DD
0x1800042ca  mov     rsi, [rsp+58h+arg_10]
0x1800042cf  mov     r14, [rsp+58h+arg_8]
0x1800042d4  mov     edi, [rsp+58h+arg_18]
0x1800042d8  mov     rbx, [rsp+58h+var_38]
0x1800042dd  test    rbx, rbx
0x1800042e0  jz      short loc_18000433C
0x1800042e2  lea     rcx, [rbx+28h]; this
0x1800042e6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800042eb  mov     ecx, eax
0x1800042ed  test    eax, eax
0x1800042ef  js      short loc_1800042F5
0x1800042f1  mov     byte ptr [rbx+50h], 1
0x1800042f5  xor     eax, eax
0x1800042f7  test    ecx, ecx
0x1800042f9  cmovs   eax, ecx
0x1800042fc  xor     ecx, ecx
0x1800042fe  test    eax, eax
0x180004300  cmovs   ecx, eax
0x180004303  xor     edi, edi
0x180004305  test    ecx, ecx
0x180004307  cmovs   edi, ecx
0x18000430a  test    edi, edi
0x18000430c  jnz     short loc_180004328
0x18000430e  mov     rax, [rbx]
0x180004311  mov     r8, rsi
0x180004314  mov     rdx, r14
0x180004317  mov     rcx, rbx
0x18000431a  mov     rax, [rax]
0x18000431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004322  mov     edi, eax
0x180004324  test    eax, eax
0x180004326  jz      short loc_18000433C
0x180004328  mov     r8, [rbx]
0x18000432b  mov     edx, 1
0x180004330  mov     rcx, rbx
0x180004333  mov     rax, [r8+18h]
0x180004337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433c  mov     eax, edi
0x18000433e  add     rsp, 30h
0x180004342  pop     r15
0x180004344  pop     r14
0x180004346  pop     rdi
0x180004347  pop     rsi
0x180004348  pop     rbx
0x180004349  retn
```
