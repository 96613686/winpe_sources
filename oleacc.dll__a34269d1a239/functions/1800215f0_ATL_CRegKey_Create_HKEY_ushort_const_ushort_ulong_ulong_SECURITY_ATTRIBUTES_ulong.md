# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800215f0`
- end: `0x180021675`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e010`
- `0x180022ad0`

## callees

- `0x18001e0a4`
- `0x1800215f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002164f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002164f`

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
0x1800215f0  mov     rax, rsp
0x1800215f3  mov     [rax+20h], r9
0x1800215f7  push    rbx
0x1800215f8  sub     rsp, 50h
0x1800215fc  mov     dword ptr [rax+28h], 0
0x180021603  mov     r10, r8
0x180021606  mov     qword ptr [rax+20h], 0
0x18002160e  lea     rax, [rax+28h]
0x180021612  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180021617  mov     r11, rdx
0x18002161a  lea     rax, [rsp+58h+arg_18]
0x18002161f  mov     rbx, rcx
0x180021622  mov     [rsp+58h+phkResult], rax; phkResult
0x180021627  xor     r9d, r9d; lpClass
0x18002162a  mov     eax, [rsp+58h+arg_28]
0x180021631  xor     r8d, r8d; Reserved
0x180021634  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002163d  mov     rdx, r10; lpSubKey
0x180021640  mov     [rsp+58h+samDesired], eax; samDesired
0x180021644  mov     rcx, r11; hKey
0x180021647  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002164f  call    cs:__imp_RegCreateKeyExW
0x180021655  mov     ecx, eax
0x180021657  test    eax, eax
0x180021659  jnz     short loc_18002166D
0x18002165b  mov     rcx, rbx; this
0x18002165e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021663  mov     ecx, eax
0x180021665  mov     rax, [rsp+58h+arg_18]
0x18002166a  mov     [rbx], rax
0x18002166d  mov     eax, ecx
0x18002166f  add     rsp, 50h
0x180021673  pop     rbx
0x180021674  retn
```
