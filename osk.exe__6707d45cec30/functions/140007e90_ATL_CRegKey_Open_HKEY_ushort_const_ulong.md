# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x140007e90`
- end: `0x140007ee1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `22`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e16c`
- `0x14001706c`
- `0x140017378`
- `0x1400179b0`
- `0x140017ac0`
- `0x14001c940`
- `0x14001cc50`
- `0x14001d3ac`
- `0x14001dae4`
- `0x14001eb30`
- `0x14001ec2c`
- `0x14001ed8c`
- `0x14001ef2c`
- `0x14001f060`
- `0x14001f728`
- `0x140020374`
- `0x140021068`
- `0x14002180c`
- `0x1400227c0`
- `0x1400237b8`
- `0x1400252a8`
- `0x140025400`

## callees

- `0x140005c90`
- `0x140007e90`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140007ebb`
- `ADVAPI32!RegOpenKeyExW` at `0x140007ebb`

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
0x140007e90  push    rbx
0x140007e92  sub     rsp, 40h
0x140007e96  mov     rbx, rcx
0x140007e99  mov     [rsp+48h+var_18], 0
0x140007ea2  mov     rax, r8
0x140007ea5  lea     rcx, [rsp+48h+var_18]
0x140007eaa  mov     r10, rdx
0x140007ead  mov     [rsp+48h+phkResult], rcx; phkResult
0x140007eb2  mov     rcx, r10; hKey
0x140007eb5  xor     r8d, r8d; ulOptions
0x140007eb8  mov     rdx, rax; lpSubKey
0x140007ebb  call    cs:__imp_RegOpenKeyExW
0x140007ec1  mov     edx, eax
0x140007ec3  test    eax, eax
0x140007ec5  jnz     short loc_140007ED9
0x140007ec7  mov     rcx, rbx; this
0x140007eca  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140007ecf  mov     edx, eax
0x140007ed1  mov     rax, [rsp+48h+var_18]
0x140007ed6  mov     [rbx], rax
0x140007ed9  mov     eax, edx
0x140007edb  add     rsp, 40h
0x140007edf  pop     rbx
0x140007ee0  retn
```
