# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x18001e0c8`
- end: `0x18001e166`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `158`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001db80`

## callees

- `0x180012408`
- `0x18001e0c8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e102`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e102`

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
0x18001e0c8  mov     r11, rsp
0x18001e0cb  mov     [r11+8], rbx
0x18001e0cf  mov     [r11+10h], rsi
0x18001e0d3  push    rdi
0x18001e0d4  sub     rsp, 30h
0x18001e0d8  mov     rdi, rdx
0x18001e0db  mov     qword ptr [r11+20h], 0
0x18001e0e3  xor     edx, edx; pUnkOuter
0x18001e0e5  lea     rax, [r11+20h]
0x18001e0e9  mov     rsi, rcx
0x18001e0ec  mov     [r11-18h], rax
0x18001e0f0  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18001e0f7  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18001e0fe  lea     r8d, [rdx+1]; dwClsContext
0x18001e102  call    cs:__imp_CoCreateInstance
0x18001e108  mov     ebx, eax
0x18001e10a  test    eax, eax
0x18001e10c  js      short loc_18001E154
0x18001e10e  mov     rcx, [rsp+38h+arg_18]
0x18001e113  mov     r9d, 104h
0x18001e119  mov     r8, rdi
0x18001e11c  mov     rdx, rsi
0x18001e11f  mov     rax, [rcx]
0x18001e122  mov     rax, [rax+20h]
0x18001e126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e12b  mov     ebx, eax
0x18001e12d  test    eax, eax
0x18001e12f  jns     short loc_18001E143
0x18001e131  mov     r8, rsi; unsigned __int16 *
0x18001e134  mov     edx, 104h; unsigned __int64
0x18001e139  mov     rcx, rdi; unsigned __int16 *
0x18001e13c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e141  mov     ebx, eax
0x18001e143  mov     rcx, [rsp+38h+arg_18]
0x18001e148  mov     rax, [rcx]
0x18001e14b  mov     rax, [rax+10h]
0x18001e14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e154  mov     rsi, [rsp+38h+arg_8]
0x18001e159  mov     eax, ebx
0x18001e15b  mov     rbx, [rsp+38h+arg_0]
0x18001e160  add     rsp, 30h
0x18001e164  pop     rdi
0x18001e165  retn
```
