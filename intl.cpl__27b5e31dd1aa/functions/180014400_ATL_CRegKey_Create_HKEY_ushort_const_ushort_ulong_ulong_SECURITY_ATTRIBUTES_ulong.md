# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180014400`
- end: `0x18001447f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001646c`

## callees

- `0x1800143d4`
- `0x180014400`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014459`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014459`

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
0x180014400  mov     r11, rsp
0x180014403  mov     [r11+20h], r9
0x180014407  push    rbx
0x180014408  sub     rsp, 50h
0x18001440c  mov     rbx, rcx
0x18001440f  mov     dword ptr [r11+28h], 0
0x180014417  lea     rcx, [r11+28h]
0x18001441b  mov     qword ptr [r11+20h], 0
0x180014423  mov     [r11-18h], rcx
0x180014427  mov     rax, r8
0x18001442a  lea     rcx, [r11+20h]
0x18001442e  mov     r10, rdx
0x180014431  mov     [r11-20h], rcx
0x180014435  xor     r9d, r9d; lpClass
0x180014438  mov     qword ptr [r11-28h], 0
0x180014440  xor     r8d, r8d; Reserved
0x180014443  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18001444b  mov     rdx, rax; lpSubKey
0x18001444e  mov     rcx, r10; hKey
0x180014451  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180014459  call    cs:__imp_RegCreateKeyExW
0x18001445f  mov     ecx, eax
0x180014461  test    eax, eax
0x180014463  jnz     short loc_180014477
0x180014465  mov     rcx, rbx; this
0x180014468  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001446d  mov     ecx, eax
0x18001446f  mov     rax, [rsp+58h+arg_18]
0x180014474  mov     [rbx], rax
0x180014477  mov     eax, ecx
0x180014479  add     rsp, 50h
0x18001447d  pop     rbx
0x18001447e  retn
```
