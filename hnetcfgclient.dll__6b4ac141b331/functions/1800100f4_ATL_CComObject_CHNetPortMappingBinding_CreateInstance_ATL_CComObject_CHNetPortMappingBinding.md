# ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(ATL::CComObject<CHNetPortMappingBinding> * *)

- ea: `0x1800100f4`
- end: `0x180010210`
- name: `?CreateInstance@?$CComObject@VCHNetPortMappingBinding@@@ATL@@SAJPEAPEAV12@@Z`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016690`
- `0x18001ad60`
- `0x1800236c0`

## callees

- `0x180001274`
- `0x180008324`
- `0x180009674`
- `0x18000969c`
- `0x1800100f4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800101bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800101bb`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  unsigned int v3; // esi
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  int v6; // ecx
  BSTR v7; // rax
  _DWORD *v9; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x58u);
    v5 = v4;
    if ( v4 )
    {
      v4[2] = 0;
      *((_OWORD *)v4 + 1) = 0;
      *((_OWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 6) = 0;
      *((_BYTE *)v4 + 56) = 0;
      *((_QWORD *)v4 + 8) = 0;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<CHNetPortMappingBinding>::`vftable';
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
    ATL::SafeIncrementReferenceMultiThread(v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 4));
    if ( v6 >= 0 )
    {
      v7 = SysAllocString(L"WQL");
      *((_QWORD *)v5 + 10) = v7;
      v6 = -2147024882;
      if ( v7 )
        v6 = 0;
    }
    v3 = 0;
    if ( v6 < 0 )
      v3 = v6;
    ATL::SafeDecrementReferenceMultiThread(v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 112LL))(v5, 1);
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
0x1800100f4  mov     [rsp+arg_0], rcx
0x1800100f9  push    rbx
0x1800100fa  push    rsi
0x1800100fb  push    rdi
0x1800100fc  push    r14
0x1800100fe  push    r15
0x180010100  sub     rsp, 20h
0x180010104  mov     r14, rcx
0x180010107  xor     ebx, ebx
0x180010109  test    rcx, rcx
0x18001010c  jnz     short loc_180010118
0x18001010e  mov     eax, 80004003h
0x180010113  jmp     loc_180010204
0x180010118  mov     [rcx], rbx
0x18001011b  mov     esi, 8007000Eh
0x180010120  mov     [rsp+48h+arg_8], esi
0x180010124  mov     [rsp+48h+arg_10], rbx
0x180010129  mov     ecx, 58h ; 'X'; Size
0x18001012e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010133  mov     rdi, rax
0x180010136  test    rax, rax
0x180010139  jz      short loc_18001017D
0x18001013b  mov     [rax+8], ebx
0x18001013e  xorps   xmm0, xmm0
0x180010141  xor     eax, eax
0x180010143  movups  xmmword ptr [rdi+10h], xmm0
0x180010147  movups  xmmword ptr [rdi+20h], xmm0
0x18001014b  mov     [rdi+30h], rax
0x18001014f  mov     [rdi+38h], bl
0x180010152  mov     [rdi+40h], rbx
0x180010156  mov     [rdi+48h], rbx
0x18001015a  mov     [rdi+50h], rbx
0x18001015e  lea     rax, ??_7?$CComObject@VCHNetPortMappingBinding@@@ATL@@6B@; const ATL::CComObject<CHNetPortMappingBinding>::`vftable'
0x180010165  mov     [rdi], rax
0x180010168  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001016f  mov     rax, [rcx]
0x180010172  mov     rax, [rax+8]
0x180010176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017b  jmp     short loc_180010180
0x18001017d  mov     rdi, rbx
0x180010180  mov     [rsp+48h+arg_10], rdi
0x180010185  jmp     short loc_180010197
0x180010187  xor     ebx, ebx
0x180010189  mov     r14, [rsp+48h+arg_0]
0x18001018e  mov     esi, [rsp+48h+arg_8]
0x180010192  mov     rdi, [rsp+48h+arg_10]
0x180010197  test    rdi, rdi
0x18001019a  jz      short loc_1800101FF
0x18001019c  lea     rcx, [rdi+8]; volatile int *
0x1800101a0  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800101a5  lea     rcx, [rdi+10h]; this
0x1800101a9  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800101ae  mov     ecx, eax
0x1800101b0  test    eax, eax
0x1800101b2  js      short loc_1800101D0
0x1800101b4  lea     rcx, ?c_wszWQL@@3QBGB; "WQL"
0x1800101bb  call    cs:__imp_SysAllocString
0x1800101c1  mov     [rdi+50h], rax
0x1800101c5  mov     ecx, 8007000Eh
0x1800101ca  test    rax, rax
0x1800101cd  cmovnz  ecx, ebx
0x1800101d0  mov     esi, ebx
0x1800101d2  test    ecx, ecx
0x1800101d4  cmovs   esi, ecx
0x1800101d7  lea     rcx, [rdi+8]; volatile int *
0x1800101db  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800101e0  test    esi, esi
0x1800101e2  jz      short loc_1800101FD
0x1800101e4  mov     rax, [rdi]
0x1800101e7  mov     edx, 1
0x1800101ec  mov     rcx, rdi
0x1800101ef  mov     rax, [rax+70h]
0x1800101f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f8  mov     rdi, rbx
0x1800101fb  jmp     short loc_1800101FF
0x1800101fd  mov     esi, ebx
0x1800101ff  mov     [r14], rdi
0x180010202  mov     eax, esi
0x180010204  add     rsp, 20h
0x180010208  pop     r15
0x18001020a  pop     r14
0x18001020c  pop     rdi
0x18001020d  pop     rsi
0x18001020e  pop     rbx
0x18001020f  retn
```
