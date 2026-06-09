# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x180030a28`
- end: `0x180030ac6`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800304e0`

## callees

- `0x180008178`
- `0x180030a28`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030a62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030a62`

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
0x180030a28  mov     r11, rsp
0x180030a2b  mov     [r11+8], rbx
0x180030a2f  mov     [r11+10h], rsi
0x180030a33  push    rdi
0x180030a34  sub     rsp, 30h
0x180030a38  mov     rdi, rdx
0x180030a3b  mov     qword ptr [r11+20h], 0
0x180030a43  xor     edx, edx; pUnkOuter
0x180030a45  lea     rax, [r11+20h]
0x180030a49  mov     rsi, rcx
0x180030a4c  mov     [r11-18h], rax
0x180030a50  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180030a57  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180030a5e  lea     r8d, [rdx+1]; dwClsContext
0x180030a62  call    cs:__imp_CoCreateInstance
0x180030a68  mov     ebx, eax
0x180030a6a  test    eax, eax
0x180030a6c  js      short loc_180030AB4
0x180030a6e  mov     rcx, [rsp+38h+arg_18]
0x180030a73  mov     r9d, 104h
0x180030a79  mov     r8, rdi
0x180030a7c  mov     rdx, rsi
0x180030a7f  mov     rax, [rcx]
0x180030a82  mov     rax, [rax+20h]
0x180030a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a8b  mov     ebx, eax
0x180030a8d  test    eax, eax
0x180030a8f  jns     short loc_180030AA3
0x180030a91  mov     r8, rsi; unsigned __int16 *
0x180030a94  mov     edx, 104h; unsigned __int64
0x180030a99  mov     rcx, rdi; unsigned __int16 *
0x180030a9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030aa1  mov     ebx, eax
0x180030aa3  mov     rcx, [rsp+38h+arg_18]
0x180030aa8  mov     rax, [rcx]
0x180030aab  mov     rax, [rax+10h]
0x180030aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ab4  mov     rsi, [rsp+38h+arg_8]
0x180030ab9  mov     eax, ebx
0x180030abb  mov     rbx, [rsp+38h+arg_0]
0x180030ac0  add     rsp, 30h
0x180030ac4  pop     rdi
0x180030ac5  retn
```
