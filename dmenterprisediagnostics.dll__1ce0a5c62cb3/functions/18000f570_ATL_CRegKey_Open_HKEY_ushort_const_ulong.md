# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000f570`
- end: `0x18000f5c1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f0d0`
- `0x18001fce4`

## callees

- `0x18000efbc`
- `0x18000f570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f59b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f59b`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x18000f570  push    rbx
0x18000f572  sub     rsp, 40h
0x18000f576  mov     rbx, rcx
0x18000f579  mov     [rsp+48h+var_18], 0
0x18000f582  mov     rax, r8
0x18000f585  lea     rcx, [rsp+48h+var_18]
0x18000f58a  mov     r10, rdx
0x18000f58d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000f592  mov     rcx, r10; hKey
0x18000f595  xor     r8d, r8d; ulOptions
0x18000f598  mov     rdx, rax; lpSubKey
0x18000f59b  call    cs:__imp_RegOpenKeyExW
0x18000f5a1  mov     edx, eax
0x18000f5a3  test    eax, eax
0x18000f5a5  jnz     short loc_18000F5B9
0x18000f5a7  mov     rcx, rbx; this
0x18000f5aa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f5af  mov     edx, eax
0x18000f5b1  mov     rax, [rsp+48h+var_18]
0x18000f5b6  mov     [rbx], rax
0x18000f5b9  mov     eax, edx
0x18000f5bb  add     rsp, 40h
0x18000f5bf  pop     rbx
0x18000f5c0  retn
```
