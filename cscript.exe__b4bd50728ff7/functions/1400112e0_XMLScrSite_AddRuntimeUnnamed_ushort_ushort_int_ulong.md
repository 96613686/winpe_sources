# XMLScrSite::AddRuntimeUnnamed(ushort *,ushort *,int,ulong)

- ea: `0x1400112e0`
- end: `0x1400113a9`
- name: `?AddRuntimeUnnamed@XMLScrSite@@UEAAJPEAG0HK@Z`
- size: `201`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400112e0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRuntimeUnnamed(
        XMLScrSite *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 2);
  v12 = 0;
  v11[0] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v5 + 624) + 128LL))(*(_QWORD *)(v5 + 624), &v12);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v12)(v12, &IID_IWshRuntime, v11);
    if ( v9 >= 0 )
      v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned __int16 *, _QWORD, unsigned int))(*(_QWORD *)v11[0] + 32LL))(
             v11[0],
             a2,
             a3,
             a4,
             a5);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400112e0  push    rbx
0x1400112e2  push    rbp
0x1400112e3  push    rsi
0x1400112e4  push    rdi
0x1400112e5  sub     rsp, 48h
0x1400112e9  mov     rax, [rcx+10h]
0x1400112ed  mov     rbp, rdx
0x1400112f0  mov     [rsp+68h+arg_0], 0
0x1400112f9  lea     rdx, [rsp+68h+arg_0]
0x1400112fe  mov     [rsp+68h+var_38], 0
0x140011307  mov     edi, r9d
0x14001130a  mov     rsi, r8
0x14001130d  mov     rcx, [rax+270h]
0x140011314  mov     rax, [rcx]
0x140011317  mov     rax, [rax+80h]
0x14001131e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011323  mov     ebx, eax
0x140011325  test    eax, eax
0x140011327  js      short loc_140011372
0x140011329  mov     rcx, [rsp+68h+arg_0]
0x14001132e  lea     r8, [rsp+68h+var_38]
0x140011333  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14001133a  mov     rax, [rcx]
0x14001133d  mov     rax, [rax]
0x140011340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011345  mov     ebx, eax
0x140011347  test    eax, eax
0x140011349  js      short loc_140011372
0x14001134b  mov     rcx, [rsp+68h+var_38]
0x140011350  mov     r9d, edi
0x140011353  mov     edx, [rsp+68h+arg_20]
0x14001135a  mov     r8, rsi
0x14001135d  mov     [rsp+68h+var_48], edx
0x140011361  mov     rdx, rbp
0x140011364  mov     rax, [rcx]
0x140011367  mov     rax, [rax+20h]
0x14001136b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011370  mov     ebx, eax
0x140011372  mov     rcx, [rsp+68h+arg_0]
0x140011377  test    rcx, rcx
0x14001137a  jz      short loc_140011388
0x14001137c  mov     rax, [rcx]
0x14001137f  mov     rax, [rax+10h]
0x140011383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011388  mov     rcx, [rsp+68h+var_38]
0x14001138d  test    rcx, rcx
0x140011390  jz      short loc_14001139E
0x140011392  mov     rax, [rcx]
0x140011395  mov     rax, [rax+10h]
0x140011399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001139e  mov     eax, ebx
0x1400113a0  add     rsp, 48h
0x1400113a4  pop     rdi
0x1400113a5  pop     rsi
0x1400113a6  pop     rbp
0x1400113a7  pop     rbx
0x1400113a8  retn
```
