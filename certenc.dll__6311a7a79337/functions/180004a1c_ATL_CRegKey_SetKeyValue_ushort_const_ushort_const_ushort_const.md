# ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)

- ea: `0x180004a1c`
- end: `0x180004a93`
- name: `?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z`
- size: `119`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004170`
- `0x180004788`

## callees

- `0x180004228`
- `0x180004a1c`
- `0x180004a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7b`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::SetKeyValue(
        HKEY *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-48h]
  HKEY hKey[5]; // [rsp+40h] [rbp-28h] BYREF

  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create(hKey, *this, a2, a4, v8);
  if ( !v6 )
    v6 = ATL::CRegKey::SetValue(hKey, a3, a4);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v6;
}

```

## disassembly

```asm
0x180004a1c  mov     rax, rsp
0x180004a1f  mov     [rax+8], rbx
0x180004a23  mov     [rax+10h], rsi
0x180004a27  push    rdi
0x180004a28  sub     rsp, 60h
0x180004a2c  mov     rsi, r8
0x180004a2f  mov     qword ptr [rax-28h], 0
0x180004a37  mov     r8, rdx; unsigned __int16 *
0x180004a3a  mov     qword ptr [rax-20h], 0
0x180004a42  mov     rdx, [rcx]; HKEY
0x180004a45  mov     rdi, r9
0x180004a48  lea     rcx, [rax-28h]; this
0x180004a4c  mov     qword ptr [rax-18h], 0
0x180004a54  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180004a59  mov     ebx, eax
0x180004a5b  test    eax, eax
0x180004a5d  jnz     short loc_180004A71
0x180004a5f  mov     r8, rdi; unsigned __int16 *
0x180004a62  lea     rcx, [rsp+68h+hKey]; this
0x180004a67  mov     rdx, rsi; unsigned __int16 *
0x180004a6a  call    ?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetValue(ushort const *,ushort const *)
0x180004a6f  mov     ebx, eax
0x180004a71  mov     rcx, [rsp+68h+hKey]; hKey
0x180004a76  test    rcx, rcx
0x180004a79  jz      short loc_180004A81
0x180004a7b  call    cs:__imp_RegCloseKey
0x180004a81  mov     rsi, [rsp+68h+arg_8]
0x180004a86  mov     eax, ebx
0x180004a88  mov     rbx, [rsp+68h+arg_0]
0x180004a8d  add     rsp, 60h
0x180004a91  pop     rdi
0x180004a92  retn
```
