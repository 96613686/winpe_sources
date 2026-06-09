# RegScan::RegScan(RegScan *)

- ea: `0x18004fc3c`
- end: `0x18004fdb5`
- name: `??0RegScan@@QEAA@PEAV0@@Z`
- size: `377`
- prototype: `RegScan *__fastcall(RegScan *__hidden this, struct RegScan *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eaf8`
- `0x1800514a0`

## callees

- `0x18004fc3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fcdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fcdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fd76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fda2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fda2`

## string_xrefs

- `0x18004fccb`: `SOFTWARE\Microsoft\COM3`

## pseudocode

```c
RegScan *__fastcall RegScan::RegScan(RegScan *this, struct RegScan *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  *((_QWORD *)this + 12) = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 1024;
  *(_QWORD *)((char *)this + 124) = 1024;
  *(_QWORD *)((char *)this + 132) = 0;
  *(_QWORD *)((char *)this + 140) = 0;
  *((_DWORD *)this + 37) = 0;
  if ( a2 )
  {
    *((_QWORD *)this + 12) = a2;
  }
  else
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3", 0, 0x20019u, &hKey) )
    {
      if ( !hKey )
        return this;
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(HKEY_LOCAL_MACHINE, L"RegScanMaxKeys", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4 )
      {
        v3 = Data;
        if ( *((_DWORD *)this + 30) > Data )
          v3 = *((_DWORD *)this + 30);
        *((_DWORD *)this + 30) = v3;
      }
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(HKEY_LOCAL_MACHINE, L"RegScanMaxValues", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4 )
      {
        v4 = Data;
        if ( *((_DWORD *)this + 31) > Data )
          v4 = *((_DWORD *)this + 31);
        *((_DWORD *)this + 31) = v4;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return this;
}

```

## disassembly

```asm
0x18004fc3c  push    rbp
0x18004fc3e  push    rbx
0x18004fc3f  push    rdi
0x18004fc40  push    r14
0x18004fc42  mov     rbp, rsp
0x18004fc45  sub     rsp, 38h
0x18004fc49  xor     edi, edi
0x18004fc4b  mov     [rcx+60h], rcx
0x18004fc4f  mov     [rcx], rdi
0x18004fc52  mov     eax, 400h
0x18004fc57  mov     [rcx+8], edi
0x18004fc5a  mov     rbx, rcx
0x18004fc5d  mov     [rcx+10h], rdi
0x18004fc61  mov     [rcx+18h], edi
0x18004fc64  mov     [rcx+20h], rdi
0x18004fc68  mov     [rcx+28h], rdi
0x18004fc6c  mov     [rcx+30h], rdi
0x18004fc70  mov     [rcx+38h], rdi
0x18004fc74  mov     [rcx+40h], rdi
0x18004fc78  mov     [rcx+48h], edi
0x18004fc7b  mov     [rcx+50h], rdi
0x18004fc7f  mov     [rcx+58h], rdi
0x18004fc83  mov     [rcx+68h], rdi
0x18004fc87  mov     [rcx+70h], rdi
0x18004fc8b  mov     [rcx+78h], eax
0x18004fc8e  mov     [rcx+7Ch], rax
0x18004fc92  mov     [rcx+84h], rdi
0x18004fc99  mov     [rcx+8Ch], rdi
0x18004fca0  mov     [rcx+94h], edi
0x18004fca6  test    rdx, rdx
0x18004fca9  jz      short loc_18004FCB4
0x18004fcab  mov     [rcx+60h], rdx
0x18004fcaf  jmp     loc_18004FDA8
0x18004fcb4  lea     rax, [rbp+hKey]
0x18004fcb8  mov     [rbp+hKey], rdi
0x18004fcbc  mov     r14, 0FFFFFFFF80000002h
0x18004fcc3  mov     [rsp+38h+phkResult], rax; phkResult
0x18004fcc8  mov     rcx, r14; hKey
0x18004fccb  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\COM3"
0x18004fcd2  mov     r9d, 20019h; samDesired
0x18004fcd8  xor     r8d, r8d; ulOptions
0x18004fcdb  call    cs:__imp_RegOpenKeyExW
0x18004fce1  test    eax, eax
0x18004fce3  jnz     loc_18004FD99
0x18004fce9  cmp     [rbp+hKey], rdi
0x18004fced  jz      loc_18004FDA8
0x18004fcf3  lea     rax, [rbp+cbData]
0x18004fcf7  mov     [rbp+Type], edi
0x18004fcfa  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004fcff  lea     r9, [rbp+Type]; lpType
0x18004fd03  lea     rax, [rbp+Data]
0x18004fd07  mov     [rbp+Data], edi
0x18004fd0a  xor     r8d, r8d; lpReserved
0x18004fd0d  mov     [rsp+38h+phkResult], rax; lpData
0x18004fd12  lea     rdx, aRegscanmaxkeys; "RegScanMaxKeys"
0x18004fd19  mov     [rbp+cbData], 4
0x18004fd20  mov     rcx, r14; hKey
0x18004fd23  call    cs:__imp_RegQueryValueExW
0x18004fd29  test    eax, eax
0x18004fd2b  jnz     short loc_18004FD46
0x18004fd2d  cmp     [rbp+Type], 4
0x18004fd31  jnz     short loc_18004FD46
0x18004fd33  cmp     [rbp+cbData], 4
0x18004fd37  jnz     short loc_18004FD46
0x18004fd39  mov     eax, [rbp+Data]
0x18004fd3c  cmp     [rbx+78h], eax
0x18004fd3f  cmova   eax, [rbx+78h]
0x18004fd43  mov     [rbx+78h], eax
0x18004fd46  lea     rax, [rbp+cbData]
0x18004fd4a  mov     [rbp+Type], edi
0x18004fd4d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004fd52  lea     r9, [rbp+Type]; lpType
0x18004fd56  lea     rax, [rbp+Data]
0x18004fd5a  mov     [rbp+Data], edi
0x18004fd5d  xor     r8d, r8d; lpReserved
0x18004fd60  mov     [rsp+38h+phkResult], rax; lpData
0x18004fd65  lea     rdx, aRegscanmaxvalu; "RegScanMaxValues"
0x18004fd6c  mov     [rbp+cbData], 4
0x18004fd73  mov     rcx, r14; hKey
0x18004fd76  call    cs:__imp_RegQueryValueExW
0x18004fd7c  test    eax, eax
0x18004fd7e  jnz     short loc_18004FD99
0x18004fd80  cmp     [rbp+Type], 4
0x18004fd84  jnz     short loc_18004FD99
0x18004fd86  cmp     [rbp+cbData], 4
0x18004fd8a  jnz     short loc_18004FD99
0x18004fd8c  mov     eax, [rbp+Data]
0x18004fd8f  cmp     [rbx+7Ch], eax
0x18004fd92  cmova   eax, [rbx+7Ch]
0x18004fd96  mov     [rbx+7Ch], eax
0x18004fd99  mov     rcx, [rbp+hKey]; hKey
0x18004fd9d  test    rcx, rcx
0x18004fda0  jz      short loc_18004FDA8
0x18004fda2  call    cs:__imp_RegCloseKey
0x18004fda8  mov     rax, rbx
0x18004fdab  add     rsp, 38h
0x18004fdaf  pop     r14
0x18004fdb1  pop     rdi
0x18004fdb2  pop     rbx
0x18004fdb3  pop     rbp
0x18004fdb4  retn
```
