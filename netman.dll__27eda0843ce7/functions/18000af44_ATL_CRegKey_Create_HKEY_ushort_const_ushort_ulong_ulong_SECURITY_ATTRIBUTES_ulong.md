# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000af44`
- end: `0x18000afdb`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `151`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d38`

## callees

- `0x180001710`
- `0x18000aeb8`
- `0x18000af44`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000afa8`
- `ADVAPI32!RegCreateKeyExW` at `0x18000afa8`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4)
{
  unsigned int v5; // ecx
  HKEY v7; // [rsp+50h] [rbp-28h] BYREF
  DWORD v8; // [rsp+58h] [rbp-20h] BYREF

  v8 = 0;
  v7 = 0;
  v5 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v7, &v8);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x18000af44  mov     r11, rsp
0x18000af47  push    rbx
0x18000af48  sub     rsp, 70h
0x18000af4c  mov     rax, cs:__security_cookie
0x18000af53  xor     rax, rsp
0x18000af56  mov     [rsp+78h+var_18], rax
0x18000af5b  mov     rbx, rcx
0x18000af5e  mov     [rsp+78h+var_20], 0
0x18000af66  lea     rcx, [r11-20h]
0x18000af6a  mov     qword ptr [r11-28h], 0
0x18000af72  mov     [r11-38h], rcx
0x18000af76  mov     r10, r8
0x18000af79  lea     rcx, [r11-28h]
0x18000af7d  mov     rax, rdx
0x18000af80  mov     [r11-40h], rcx
0x18000af84  xor     r9d, r9d; lpClass
0x18000af87  mov     qword ptr [r11-48h], 0
0x18000af8f  xor     r8d, r8d; Reserved
0x18000af92  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18000af9a  mov     rdx, r10; lpSubKey
0x18000af9d  mov     rcx, rax; hKey
0x18000afa0  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000afa8  call    cs:__imp_RegCreateKeyExW
0x18000afae  mov     ecx, eax
0x18000afb0  test    eax, eax
0x18000afb2  jnz     short loc_18000AFC6
0x18000afb4  mov     rcx, rbx; this
0x18000afb7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000afbc  mov     ecx, eax
0x18000afbe  mov     rax, [rsp+78h+var_28]
0x18000afc3  mov     [rbx], rax
0x18000afc6  mov     eax, ecx
0x18000afc8  mov     rcx, [rsp+78h+var_18]
0x18000afcd  xor     rcx, rsp; StackCookie
0x18000afd0  call    __security_check_cookie
0x18000afd5  add     rsp, 70h
0x18000afd9  pop     rbx
0x18000afda  retn
```
