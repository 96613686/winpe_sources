# ATL::CRegKey::Create(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000c3f0`
- end: `0x18000c46f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010624`
- `0x18002b2e0`
- `0x18002dd8c`

## callees

- `0x18000c344`
- `0x18000c3f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c449`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c449`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::Create(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, wchar_t *a4, unsigned int a5)
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
0x18000c3f0  mov     r11, rsp
0x18000c3f3  mov     [r11+20h], r9
0x18000c3f7  push    rbx
0x18000c3f8  sub     rsp, 50h
0x18000c3fc  mov     rbx, rcx
0x18000c3ff  mov     dword ptr [r11+28h], 0
0x18000c407  lea     rcx, [r11+28h]
0x18000c40b  mov     qword ptr [r11+20h], 0
0x18000c413  mov     [r11-18h], rcx
0x18000c417  mov     rax, r8
0x18000c41a  lea     rcx, [r11+20h]
0x18000c41e  mov     r10, rdx
0x18000c421  mov     [r11-20h], rcx
0x18000c425  xor     r9d, r9d; lpClass
0x18000c428  mov     qword ptr [r11-28h], 0
0x18000c430  xor     r8d, r8d; Reserved
0x18000c433  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000c43b  mov     rdx, rax; lpSubKey
0x18000c43e  mov     rcx, r10; hKey
0x18000c441  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000c449  call    cs:__imp_RegCreateKeyExW
0x18000c44f  mov     ecx, eax
0x18000c451  test    eax, eax
0x18000c453  jnz     short loc_18000C467
0x18000c455  mov     rcx, rbx; this
0x18000c458  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c45d  mov     ecx, eax
0x18000c45f  mov     rax, [rsp+58h+arg_18]
0x18000c464  mov     [rbx], rax
0x18000c467  mov     eax, ecx
0x18000c469  add     rsp, 50h
0x18000c46d  pop     rbx
0x18000c46e  retn
```
