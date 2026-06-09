# MarkFileUnsafe(ushort const *)

- ea: `0x1800095e0`
- end: `0x1800096d1`
- name: `?MarkFileUnsafe@@YAJPEBG@Z`
- size: `241`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007934`
- `0x180007cf8`
- `0x1800098ac`
- `0x180009bc8`
- `0x180009dd8`

## callees

- `0x1800095e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009613`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009613`

## pseudocode

```c
__int64 __fastcall MarkFileUnsafe(const unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rcx
  LPVOID v4; // rcx
  LPVOID v6; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v2 = CoCreateInstance(&CLSID_PersistentZoneIdentifier, 0, 1u, &GUID_cd45f185_1b21_48e2_967b_ead743a8914e, &v6);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v6 + 32LL))(v6, 3);
    if ( v2 >= 0 )
    {
      v7 = 0;
      v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v6)(
             v6,
             &GUID_0000010b_0000_0000_c000_000000000046,
             &v7);
      if ( v2 >= 0 )
        v2 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v7 + 48LL))(v7, a1, 1);
      v3 = v7;
      if ( v7 )
      {
        v7 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
    }
  }
  v4 = v6;
  if ( v6 )
  {
    v6 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800095e0  mov     r11, rsp
0x1800095e3  mov     [r11+8], rbx
0x1800095e7  push    rdi
0x1800095e8  sub     rsp, 30h
0x1800095ec  xor     edx, edx; pUnkOuter
0x1800095ee  mov     qword ptr [r11+10h], 0
0x1800095f6  mov     rdi, rcx
0x1800095f9  lea     rax, [r11+10h]
0x1800095fd  lea     r9, _GUID_cd45f185_1b21_48e2_967b_ead743a8914e; riid
0x180009604  mov     [r11-18h], rax
0x180009608  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x18000960f  lea     r8d, [rdx+1]; dwClsContext
0x180009613  call    cs:__imp_CoCreateInstance
0x180009619  mov     ebx, eax
0x18000961b  test    eax, eax
0x18000961d  js      loc_1800096A5
0x180009623  mov     rcx, [rsp+38h+arg_8]
0x180009628  mov     edx, 3
0x18000962d  mov     rax, [rcx]
0x180009630  mov     rax, [rax+20h]
0x180009634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009639  mov     ebx, eax
0x18000963b  test    eax, eax
0x18000963d  js      short loc_1800096A5
0x18000963f  mov     rcx, [rsp+38h+arg_8]
0x180009644  lea     r8, [rsp+38h+arg_10]
0x180009649  mov     [rsp+38h+arg_10], 0
0x180009652  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180009659  mov     rax, [rcx]
0x18000965c  mov     rax, [rax]
0x18000965f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009664  mov     ebx, eax
0x180009666  test    eax, eax
0x180009668  js      short loc_180009686
0x18000966a  mov     rcx, [rsp+38h+arg_10]
0x18000966f  mov     r8d, 1
0x180009675  mov     rdx, rdi
0x180009678  mov     rax, [rcx]
0x18000967b  mov     rax, [rax+30h]
0x18000967f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009684  mov     ebx, eax
0x180009686  mov     rcx, [rsp+38h+arg_10]
0x18000968b  test    rcx, rcx
0x18000968e  jz      short loc_1800096A5
0x180009690  mov     [rsp+38h+arg_10], 0
0x180009699  mov     rax, [rcx]
0x18000969c  mov     rax, [rax+10h]
0x1800096a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a5  mov     rcx, [rsp+38h+arg_8]
0x1800096aa  test    rcx, rcx
0x1800096ad  jz      short loc_1800096C4
0x1800096af  mov     [rsp+38h+arg_8], 0
0x1800096b8  mov     rax, [rcx]
0x1800096bb  mov     rax, [rax+10h]
0x1800096bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c4  mov     eax, ebx
0x1800096c6  mov     rbx, [rsp+38h+arg_0]
0x1800096cb  add     rsp, 30h
0x1800096cf  pop     rdi
0x1800096d0  retn
```
