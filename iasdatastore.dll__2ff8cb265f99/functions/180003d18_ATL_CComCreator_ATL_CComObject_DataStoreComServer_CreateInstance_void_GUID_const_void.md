# ATL::CComCreator<ATL::CComObject<DataStoreComServer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003d18`
- end: `0x180003e19`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VDataStoreComServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x180002310`
- `0x180003d18`
- `0x18000433c`
- `0x1800067a8`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<DataStoreComServer>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  DataStoreComServer *v7; // rax
  DataStoreComServer *v8; // rbx
  int v9; // ecx
  int v10; // eax
  DataStoreComServer *v13; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (DataStoreComServer *)operator new(0x50u);
    v8 = v7;
    if ( v7 )
    {
      DataStoreComServer::DataStoreComServer(v7);
      *(_QWORD *)v8 = &ATL::CComObject<DataStoreComServer>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v8 + 16));
    if ( v9 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(DataStoreComServer *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(DataStoreComServer *, __int64))(*(_QWORD *)v8 + 96LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003d18  mov     [rsp+arg_10], r8
0x180003d1d  mov     [rsp+arg_8], rdx
0x180003d22  mov     [rsp+arg_0], rcx
0x180003d27  push    rbx
0x180003d28  push    rsi
0x180003d29  push    rdi
0x180003d2a  push    r14
0x180003d2c  sub     rsp, 38h
0x180003d30  mov     rsi, r8
0x180003d33  mov     r14, rdx
0x180003d36  test    r8, r8
0x180003d39  jnz     short loc_180003D45
0x180003d3b  mov     eax, 80004003h
0x180003d40  jmp     loc_180003E0F
0x180003d45  mov     qword ptr [r8], 0
0x180003d4c  mov     edi, 8007000Eh
0x180003d51  mov     dword ptr [rsp+58h+arg_0], edi
0x180003d55  mov     [rsp+58h+arg_18], 0
0x180003d5e  mov     ecx, 50h ; 'P'; Size
0x180003d63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003d68  mov     rbx, rax
0x180003d6b  mov     [rsp+58h+var_38], rax
0x180003d70  test    rbx, rbx
0x180003d73  jz      short loc_180003D9B
0x180003d75  mov     rcx, rax; this
0x180003d78  call    ??0DataStoreComServer@@QEAA@XZ; DataStoreComServer::DataStoreComServer(void)
0x180003d7d  lea     rax, ??_7?$CComObject@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObject<DataStoreComServer>::`vftable'
0x180003d84  mov     [rbx], rax
0x180003d87  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d8e  mov     rax, [rcx]
0x180003d91  mov     rax, [rax+8]
0x180003d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9a  nop
0x180003d9b  mov     [rsp+58h+arg_18], rbx
0x180003da0  jmp     short loc_180003DB5
0x180003da2  mov     rsi, [rsp+58h+arg_10]
0x180003da7  mov     r14, [rsp+58h+arg_8]
0x180003dac  mov     edi, dword ptr [rsp+58h+arg_0]
0x180003db0  mov     rbx, [rsp+58h+arg_18]
0x180003db5  test    rbx, rbx
0x180003db8  jz      short loc_180003E0D
0x180003dba  lea     rcx, [rbx+10h]; this
0x180003dbe  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003dc3  mov     ecx, eax
0x180003dc5  test    eax, eax
0x180003dc7  js      short loc_180003DCD
0x180003dc9  mov     byte ptr [rbx+38h], 1
0x180003dcd  xor     eax, eax
0x180003dcf  test    ecx, ecx
0x180003dd1  cmovs   eax, ecx
0x180003dd4  xor     edi, edi
0x180003dd6  test    eax, eax
0x180003dd8  cmovs   edi, eax
0x180003ddb  test    edi, edi
0x180003ddd  jnz     short loc_180003DF9
0x180003ddf  mov     rax, [rbx]
0x180003de2  mov     r8, rsi
0x180003de5  mov     rdx, r14
0x180003de8  mov     rcx, rbx
0x180003deb  mov     rax, [rax]
0x180003dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df3  mov     edi, eax
0x180003df5  test    eax, eax
0x180003df7  jz      short loc_180003E0D
0x180003df9  mov     r8, [rbx]
0x180003dfc  mov     edx, 1
0x180003e01  mov     rcx, rbx
0x180003e04  mov     rax, [r8+60h]
0x180003e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0d  mov     eax, edi
0x180003e0f  add     rsp, 38h
0x180003e13  pop     r14
0x180003e15  pop     rdi
0x180003e16  pop     rsi
0x180003e17  pop     rbx
0x180003e18  retn
```
