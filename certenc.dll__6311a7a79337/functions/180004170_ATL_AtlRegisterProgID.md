# ATL::AtlRegisterProgID

- ea: `0x180004170`
- end: `0x18000421f`
- name: `ATL::AtlRegisterProgID`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004788`

## callees

- `0x180004170`
- `0x180004228`
- `0x180004a1c`
- `0x180004a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004207`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004207`

## string_xrefs

- `0x1800041ca`: `CLSID`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterProgID(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const BYTE *a3,
        unsigned __int16 *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+20h] [rbp-48h]
  HKEY hKey[5]; // [rsp+40h] [rbp-28h] BYREF

  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create(hKey, HKEY_CLASSES_ROOT, a2, a4, v9);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v7;
  }
  else
  {
    ATL::CRegKey::SetValue(hKey, a3, 0);
    ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"CLSID", a1, 0);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180004170  mov     rax, rsp
0x180004173  mov     [rax+8], rbx
0x180004177  mov     [rax+10h], rsi
0x18000417b  push    rdi
0x18000417c  sub     rsp, 60h
0x180004180  mov     rdi, r8
0x180004183  mov     qword ptr [rax-28h], 0
0x18000418b  mov     r8, rdx; unsigned __int16 *
0x18000418e  mov     qword ptr [rax-20h], 0
0x180004196  mov     rsi, rcx
0x180004199  mov     qword ptr [rax-18h], 0
0x1800041a1  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x1800041a8  lea     rcx, [rax-28h]; this
0x1800041ac  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800041b1  mov     ebx, eax
0x1800041b3  test    eax, eax
0x1800041b5  jnz     short loc_1800041F2
0x1800041b7  xor     r8d, r8d; unsigned __int16 *
0x1800041ba  lea     rcx, [rsp+68h+hKey]; this
0x1800041bf  mov     rdx, rdi; unsigned __int16 *
0x1800041c2  call    ?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetValue(ushort const *,ushort const *)
0x1800041c7  xor     r9d, r9d; unsigned __int16 *
0x1800041ca  lea     rdx, aClsid; "CLSID"
0x1800041d1  mov     r8, rsi; unsigned __int16 *
0x1800041d4  lea     rcx, [rsp+68h+hKey]; this
0x1800041d9  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x1800041de  mov     rcx, [rsp+68h+hKey]; hKey
0x1800041e3  test    rcx, rcx
0x1800041e6  jz      short loc_1800041EE
0x1800041e8  call    cs:__imp_RegCloseKey
0x1800041ee  xor     eax, eax
0x1800041f0  jmp     short loc_18000420F
0x1800041f2  jle     short loc_1800041FD
0x1800041f4  movzx   ebx, ax
0x1800041f7  or      ebx, 80070000h
0x1800041fd  mov     rcx, [rsp+68h+hKey]; hKey
0x180004202  test    rcx, rcx
0x180004205  jz      short loc_18000420D
0x180004207  call    cs:__imp_RegCloseKey
0x18000420d  mov     eax, ebx
0x18000420f  mov     rbx, [rsp+68h+arg_0]
0x180004214  mov     rsi, [rsp+68h+arg_8]
0x180004219  add     rsp, 60h
0x18000421d  pop     rdi
0x18000421e  retn
```
