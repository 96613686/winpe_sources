# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180004228`
- end: `0x1800042ad`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004170`
- `0x180004788`
- `0x180004a1c`

## callees

- `0x180004228`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004295`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004295`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004281`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004281`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0xF003Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    if ( *this )
      v6 = RegCloseKey(*this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x180004228  mov     r11, rsp
0x18000422b  mov     [r11+20h], r9
0x18000422f  push    rbx
0x180004230  sub     rsp, 50h
0x180004234  mov     rbx, rcx
0x180004237  mov     dword ptr [r11+28h], 0
0x18000423f  lea     rcx, [r11+28h]
0x180004243  mov     qword ptr [r11+20h], 0
0x18000424b  mov     [r11-18h], rcx
0x18000424f  mov     rax, r8
0x180004252  lea     rcx, [r11+20h]
0x180004256  mov     r10, rdx
0x180004259  mov     [r11-20h], rcx
0x18000425d  xor     r9d, r9d; lpClass
0x180004260  mov     qword ptr [r11-28h], 0
0x180004268  xor     r8d, r8d; Reserved
0x18000426b  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180004273  mov     rdx, rax; lpSubKey
0x180004276  mov     rcx, r10; hKey
0x180004279  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180004281  call    cs:__imp_RegCreateKeyExW
0x180004287  mov     ecx, eax
0x180004289  test    eax, eax
0x18000428b  jnz     short loc_1800042A5
0x18000428d  cmp     [rbx], rcx
0x180004290  jz      short loc_18000429D
0x180004292  mov     rcx, [rbx]; hKey
0x180004295  call    cs:__imp_RegCloseKey
0x18000429b  mov     ecx, eax
0x18000429d  mov     rax, [rsp+58h+arg_18]
0x1800042a2  mov     [rbx], rax
0x1800042a5  mov     eax, ecx
0x1800042a7  add     rsp, 50h
0x1800042ab  pop     rbx
0x1800042ac  retn
```
