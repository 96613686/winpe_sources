# CSafeReg::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001ae60`
- end: `0x18001aeb4`
- name: `?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `84`
- prototype: `int(CSafeReg *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004b7c`
- `0x18000839c`
- `0x18000af00`
- `0x18000d814`
- `0x18000e664`
- `0x18000e908`
- `0x180010f80`
- `0x1800130a8`
- `0x1800131b8`
- `0x18001435c`
- `0x180016084`
- `0x180016ffc`
- `0x180018580`
- `0x180018dd0`
- `0x18001acd0`
- `0x18001f9cc`
- `0x18001fcf0`

## callees

- `0x18001ae60`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001ae8b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ae8b`

## pseudocode

```c
__int64 __fastcall CSafeReg::Open(CSafeReg *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  LSTATUS v5; // eax
  unsigned int v6; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(a2, a3, 0, a4, &phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    *(_QWORD *)this = phkResult;
  }
  return v6;
}

```

## disassembly

```asm
0x18001ae60  push    rbx
0x18001ae62  sub     rsp, 40h
0x18001ae66  mov     rbx, rcx
0x18001ae69  mov     [rsp+48h+var_18], 0
0x18001ae72  mov     rax, r8
0x18001ae75  lea     rcx, [rsp+48h+var_18]
0x18001ae7a  mov     r10, rdx
0x18001ae7d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001ae82  mov     rcx, r10; hKey
0x18001ae85  xor     r8d, r8d; ulOptions
0x18001ae88  mov     rdx, rax; lpSubKey
0x18001ae8b  call    cs:__imp_RegOpenKeyExW
0x18001ae91  mov     edx, eax
0x18001ae93  test    eax, eax
0x18001ae95  jnz     short loc_18001AEA1
0x18001ae97  mov     rax, [rsp+48h+var_18]
0x18001ae9c  mov     [rbx], rax
0x18001ae9f  jmp     short loc_18001AEAC
0x18001aea1  jle     short loc_18001AEAC
0x18001aea3  movzx   edx, ax
0x18001aea6  or      edx, 80070000h
0x18001aeac  mov     eax, edx
0x18001aeae  add     rsp, 40h
0x18001aeb2  pop     rbx
0x18001aeb3  retn
```
