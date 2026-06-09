# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x180018340`
- end: `0x1800183de`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e00`

## callees

- `0x1800063c4`
- `0x180018340`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001837a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001837a`

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
0x180018340  mov     r11, rsp
0x180018343  mov     [r11+8], rbx
0x180018347  mov     [r11+10h], rsi
0x18001834b  push    rdi
0x18001834c  sub     rsp, 30h
0x180018350  mov     rdi, rdx
0x180018353  mov     qword ptr [r11+20h], 0
0x18001835b  xor     edx, edx; pUnkOuter
0x18001835d  lea     rax, [r11+20h]
0x180018361  mov     rsi, rcx
0x180018364  mov     [r11-18h], rax
0x180018368  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18001836f  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180018376  lea     r8d, [rdx+1]; dwClsContext
0x18001837a  call    cs:__imp_CoCreateInstance
0x180018380  mov     ebx, eax
0x180018382  test    eax, eax
0x180018384  js      short loc_1800183CC
0x180018386  mov     rcx, [rsp+38h+arg_18]
0x18001838b  mov     r9d, 104h
0x180018391  mov     r8, rdi
0x180018394  mov     rdx, rsi
0x180018397  mov     rax, [rcx]
0x18001839a  mov     rax, [rax+20h]
0x18001839e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183a3  mov     ebx, eax
0x1800183a5  test    eax, eax
0x1800183a7  jns     short loc_1800183BB
0x1800183a9  mov     r8, rsi; unsigned __int16 *
0x1800183ac  mov     edx, 104h; unsigned __int64
0x1800183b1  mov     rcx, rdi; unsigned __int16 *
0x1800183b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800183b9  mov     ebx, eax
0x1800183bb  mov     rcx, [rsp+38h+arg_18]
0x1800183c0  mov     rax, [rcx]
0x1800183c3  mov     rax, [rax+10h]
0x1800183c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183cc  mov     rsi, [rsp+38h+arg_8]
0x1800183d1  mov     eax, ebx
0x1800183d3  mov     rbx, [rsp+38h+arg_0]
0x1800183d8  add     rsp, 30h
0x1800183dc  pop     rdi
0x1800183dd  retn
```
