# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800290a8`
- end: `0x180029127`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cdc`
- `0x180028f00`

## callees

- `0x18001f0a4`
- `0x1800290a8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180029101`
- `ADVAPI32!RegCreateKeyExW` at `0x180029101`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4, unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x1800290a8  mov     r11, rsp
0x1800290ab  mov     [r11+20h], r9
0x1800290af  push    rbx
0x1800290b0  sub     rsp, 50h
0x1800290b4  mov     rbx, rcx
0x1800290b7  mov     dword ptr [r11+28h], 0
0x1800290bf  lea     rcx, [r11+28h]
0x1800290c3  mov     qword ptr [r11+20h], 0
0x1800290cb  mov     [r11-18h], rcx
0x1800290cf  mov     rax, r8
0x1800290d2  lea     rcx, [r11+20h]
0x1800290d6  mov     r10, rdx
0x1800290d9  mov     [r11-20h], rcx
0x1800290dd  xor     r9d, r9d; lpClass
0x1800290e0  mov     qword ptr [r11-28h], 0
0x1800290e8  xor     r8d, r8d; Reserved
0x1800290eb  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800290f3  mov     rdx, rax; lpSubKey
0x1800290f6  mov     rcx, r10; hKey
0x1800290f9  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180029101  call    cs:__imp_RegCreateKeyExW
0x180029107  mov     ecx, eax
0x180029109  test    eax, eax
0x18002910b  jnz     short loc_18002911F
0x18002910d  mov     rcx, rbx; this
0x180029110  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029115  mov     ecx, eax
0x180029117  mov     rax, [rsp+58h+arg_18]
0x18002911c  mov     [rbx], rax
0x18002911f  mov     eax, ecx
0x180029121  add     rsp, 50h
0x180029125  pop     rbx
0x180029126  retn
```
