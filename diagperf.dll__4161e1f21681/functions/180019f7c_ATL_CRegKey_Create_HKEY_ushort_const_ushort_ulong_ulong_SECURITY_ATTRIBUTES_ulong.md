# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180019f7c`
- end: `0x18001a001`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800193d4`
- `0x180019988`
- `0x18001a008`
- `0x18001a598`
- `0x18001a984`
- `0x18003d1a0`

## callees

- `0x180019f7c`
- `0x18001a56c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019fdb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019fdb`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        unsigned int lpdwDisposition,
        REGSAM samDesired)
{
  unsigned int v7; // ecx
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  lpdwDisposition = 0;
  phkResult = 0;
  v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &phkResult, &lpdwDisposition);
  if ( !v7 )
  {
    v7 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v7;
}

```

## disassembly

```asm
0x180019f7c  mov     rax, rsp
0x180019f7f  mov     [rax+20h], r9
0x180019f83  push    rbx
0x180019f84  sub     rsp, 50h
0x180019f88  mov     dword ptr [rax+28h], 0
0x180019f8f  mov     r10, r8
0x180019f92  mov     qword ptr [rax+20h], 0
0x180019f9a  lea     rax, [rax+28h]
0x180019f9e  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180019fa3  mov     r11, rdx
0x180019fa6  lea     rax, [rsp+58h+arg_18]
0x180019fab  mov     rbx, rcx
0x180019fae  mov     [rsp+58h+phkResult], rax; phkResult
0x180019fb3  xor     r9d, r9d; lpClass
0x180019fb6  mov     eax, [rsp+58h+arg_28]
0x180019fbd  xor     r8d, r8d; Reserved
0x180019fc0  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180019fc9  mov     rdx, r10; lpSubKey
0x180019fcc  mov     [rsp+58h+samDesired], eax; samDesired
0x180019fd0  mov     rcx, r11; hKey
0x180019fd3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180019fdb  call    cs:__imp_RegCreateKeyExW
0x180019fe1  mov     ecx, eax
0x180019fe3  test    eax, eax
0x180019fe5  jnz     short loc_180019FF9
0x180019fe7  mov     rcx, rbx; this
0x180019fea  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019fef  mov     ecx, eax
0x180019ff1  mov     rax, [rsp+58h+arg_18]
0x180019ff6  mov     [rbx], rax
0x180019ff9  mov     eax, ecx
0x180019ffb  add     rsp, 50h
0x180019fff  pop     rbx
0x18001a000  retn
```
