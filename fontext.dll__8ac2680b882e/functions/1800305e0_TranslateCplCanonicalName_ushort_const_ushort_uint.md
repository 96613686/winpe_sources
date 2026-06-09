# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x1800305e0`
- end: `0x18003067e`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800300b0`

## callees

- `0x180006624`
- `0x1800305e0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003061a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003061a`

## pseudocode

```c
__int64 __fastcall TranslateCplCanonicalName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *, __int64))(*(_QWORD *)v6 + 32LL))(
           v6,
           a1,
           a2,
           260);
    if ( v4 < 0 )
      v4 = StringCchCopyW(a2, 0x104u, a1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800305e0  mov     r11, rsp
0x1800305e3  mov     [r11+8], rbx
0x1800305e7  mov     [r11+10h], rsi
0x1800305eb  push    rdi
0x1800305ec  sub     rsp, 30h
0x1800305f0  mov     rdi, rdx
0x1800305f3  mov     qword ptr [r11+20h], 0
0x1800305fb  xor     edx, edx; pUnkOuter
0x1800305fd  lea     rax, [r11+20h]
0x180030601  mov     rsi, rcx
0x180030604  mov     [r11-18h], rax
0x180030608  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18003060f  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180030616  lea     r8d, [rdx+1]; dwClsContext
0x18003061a  call    cs:__imp_CoCreateInstance
0x180030620  mov     ebx, eax
0x180030622  test    eax, eax
0x180030624  js      short loc_18003066C
0x180030626  mov     rcx, [rsp+38h+arg_18]
0x18003062b  mov     r9d, 104h
0x180030631  mov     r8, rdi
0x180030634  mov     rdx, rsi
0x180030637  mov     rax, [rcx]
0x18003063a  mov     rax, [rax+20h]
0x18003063e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030643  mov     ebx, eax
0x180030645  test    eax, eax
0x180030647  jns     short loc_18003065B
0x180030649  mov     r8, rsi; unsigned __int16 *
0x18003064c  mov     edx, 104h; unsigned __int64
0x180030651  mov     rcx, rdi; unsigned __int16 *
0x180030654  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030659  mov     ebx, eax
0x18003065b  mov     rcx, [rsp+38h+arg_18]
0x180030660  mov     rax, [rcx]
0x180030663  mov     rax, [rax+10h]
0x180030667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003066c  mov     rsi, [rsp+38h+arg_8]
0x180030671  mov     eax, ebx
0x180030673  mov     rbx, [rsp+38h+arg_0]
0x180030678  add     rsp, 30h
0x18003067c  pop     rdi
0x18003067d  retn
```
