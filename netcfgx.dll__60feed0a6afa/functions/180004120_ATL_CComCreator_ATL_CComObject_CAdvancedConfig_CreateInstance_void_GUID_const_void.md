# ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004120`
- end: `0x18000422e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCAdvancedConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `270`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003fe0`

## callees

- `0x180004120`
- `0x18000465c`
- `0x180007d38`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // ecx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = MemAlloc(0x40u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CAdvancedConfig>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 4));
    if ( v9 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004120  mov     [rsp+arg_10], r8
0x180004125  mov     [rsp+arg_8], rdx
0x18000412a  mov     [rsp+arg_0], rcx
0x18000412f  push    rbx
0x180004130  push    rsi
0x180004131  push    rdi
0x180004132  push    r14
0x180004134  sub     rsp, 28h
0x180004138  mov     rsi, r8
0x18000413b  mov     r14, rdx
0x18000413e  test    r8, r8
0x180004141  jnz     short loc_18000414D
0x180004143  mov     eax, 80004003h
0x180004148  jmp     loc_180004224
0x18000414d  mov     qword ptr [r8], 0
0x180004154  mov     edi, 8007000Eh
0x180004159  mov     dword ptr [rsp+48h+arg_0], edi
0x18000415d  mov     ecx, 40h ; '@'; unsigned __int64
0x180004162  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180004167  mov     rbx, rax
0x18000416a  mov     [rsp+48h+arg_18], rax
0x18000416f  test    rax, rax
0x180004172  jz      short loc_1800041AE
0x180004174  mov     dword ptr [rax+8], 0
0x18000417b  xorps   xmm0, xmm0
0x18000417e  xor     eax, eax
0x180004180  movups  xmmword ptr [rbx+10h], xmm0
0x180004184  movups  xmmword ptr [rbx+20h], xmm0
0x180004188  mov     [rbx+30h], rax
0x18000418c  mov     [rbx+38h], al
0x18000418f  lea     rax, ??_7?$CComObject@VCAdvancedConfig@@@ATL@@6B@; const ATL::CComObject<CAdvancedConfig>::`vftable'
0x180004196  mov     [rbx], rax
0x180004199  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800041a0  mov     rax, [rcx]
0x1800041a3  mov     rax, [rax+8]
0x1800041a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ac  jmp     short loc_1800041B0
0x1800041ae  xor     ebx, ebx
0x1800041b0  mov     [rsp+48h+arg_18], rbx
0x1800041b5  jmp     short loc_1800041CA
0x1800041b7  mov     rsi, [rsp+48h+arg_10]
0x1800041bc  mov     r14, [rsp+48h+arg_8]
0x1800041c1  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800041c5  mov     rbx, [rsp+48h+arg_18]
0x1800041ca  test    rbx, rbx
0x1800041cd  jz      short loc_180004222
0x1800041cf  lea     rcx, [rbx+10h]; this
0x1800041d3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800041d8  mov     ecx, eax
0x1800041da  test    eax, eax
0x1800041dc  js      short loc_1800041E2
0x1800041de  mov     byte ptr [rbx+38h], 1
0x1800041e2  xor     eax, eax
0x1800041e4  test    ecx, ecx
0x1800041e6  cmovs   eax, ecx
0x1800041e9  xor     edi, edi
0x1800041eb  test    eax, eax
0x1800041ed  cmovs   edi, eax
0x1800041f0  test    edi, edi
0x1800041f2  jnz     short loc_18000420E
0x1800041f4  mov     rax, [rbx]
0x1800041f7  mov     r8, rsi
0x1800041fa  mov     rdx, r14
0x1800041fd  mov     rcx, rbx
0x180004200  mov     rax, [rax]
0x180004203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004208  mov     edi, eax
0x18000420a  test    eax, eax
0x18000420c  jz      short loc_180004222
0x18000420e  mov     r8, [rbx]
0x180004211  mov     edx, 1
0x180004216  mov     rcx, rbx
0x180004219  mov     rax, [r8+20h]
0x18000421d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004222  mov     eax, edi
0x180004224  add     rsp, 28h
0x180004228  pop     r14
0x18000422a  pop     rdi
0x18000422b  pop     rsi
0x18000422c  pop     rbx
0x18000422d  retn
```
