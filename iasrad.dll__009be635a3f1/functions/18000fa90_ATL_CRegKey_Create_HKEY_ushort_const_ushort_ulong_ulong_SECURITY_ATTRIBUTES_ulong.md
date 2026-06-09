# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000fa90`
- end: `0x18000fb0f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800110f4`

## callees

- `0x18000fa64`
- `0x18000fa90`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000fae9`
- `ADVAPI32!RegCreateKeyExW` at `0x18000fae9`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fa90  mov     r11, rsp
0x18000fa93  mov     [r11+20h], r9
0x18000fa97  push    rbx
0x18000fa98  sub     rsp, 50h
0x18000fa9c  mov     rbx, rcx
0x18000fa9f  mov     dword ptr [r11+28h], 0
0x18000faa7  lea     rcx, [r11+28h]
0x18000faab  mov     qword ptr [r11+20h], 0
0x18000fab3  mov     [r11-18h], rcx
0x18000fab7  mov     rax, r8
0x18000faba  lea     rcx, [r11+20h]
0x18000fabe  mov     r10, rdx
0x18000fac1  mov     [r11-20h], rcx
0x18000fac5  xor     r9d, r9d; lpClass
0x18000fac8  mov     qword ptr [r11-28h], 0
0x18000fad0  xor     r8d, r8d; Reserved
0x18000fad3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000fadb  mov     rdx, rax; lpSubKey
0x18000fade  mov     rcx, r10; hKey
0x18000fae1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000fae9  call    cs:__imp_RegCreateKeyExW
0x18000faef  mov     ecx, eax
0x18000faf1  test    eax, eax
0x18000faf3  jnz     short loc_18000FB07
0x18000faf5  mov     rcx, rbx; this
0x18000faf8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fafd  mov     ecx, eax
0x18000faff  mov     rax, [rsp+58h+arg_18]
0x18000fb04  mov     [rbx], rax
0x18000fb07  mov     eax, ecx
0x18000fb09  add     rsp, 50h
0x18000fb0d  pop     rbx
0x18000fb0e  retn
```
