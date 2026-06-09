# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180004f70`
- end: `0x180004fef`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007e04`

## callees

- `0x180004f44`
- `0x180004f70`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180004fc9`
- `ADVAPI32!RegCreateKeyExW` at `0x180004fc9`

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
0x180004f70  mov     r11, rsp
0x180004f73  mov     [r11+20h], r9
0x180004f77  push    rbx
0x180004f78  sub     rsp, 50h
0x180004f7c  mov     rbx, rcx
0x180004f7f  mov     dword ptr [r11+28h], 0
0x180004f87  lea     rcx, [r11+28h]
0x180004f8b  mov     qword ptr [r11+20h], 0
0x180004f93  mov     [r11-18h], rcx
0x180004f97  mov     rax, r8
0x180004f9a  lea     rcx, [r11+20h]
0x180004f9e  mov     r10, rdx
0x180004fa1  mov     [r11-20h], rcx
0x180004fa5  xor     r9d, r9d; lpClass
0x180004fa8  mov     qword ptr [r11-28h], 0
0x180004fb0  xor     r8d, r8d; Reserved
0x180004fb3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180004fbb  mov     rdx, rax; lpSubKey
0x180004fbe  mov     rcx, r10; hKey
0x180004fc1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180004fc9  call    cs:__imp_RegCreateKeyExW
0x180004fcf  mov     ecx, eax
0x180004fd1  test    eax, eax
0x180004fd3  jnz     short loc_180004FE7
0x180004fd5  mov     rcx, rbx; this
0x180004fd8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004fdd  mov     ecx, eax
0x180004fdf  mov     rax, [rsp+58h+arg_18]
0x180004fe4  mov     [rbx], rax
0x180004fe7  mov     eax, ecx
0x180004fe9  add     rsp, 50h
0x180004fed  pop     rbx
0x180004fee  retn
```
