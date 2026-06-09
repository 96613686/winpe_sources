# AddPortInformationToPrinterName

- ea: `0x180024418`
- end: `0x1800245a5`
- name: `AddPortInformationToPrinterName`
- size: `397`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800243a8`
- `0x1800c9fbc`

## callees

- `0x180013c90`
- `0x180024418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002457f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002457f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024557`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024557`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800244a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800244a8`
- `SPOOLSS!DllFreeSplMem` at `0x1800244ba`
- `SPOOLSS!DllFreeSplMem` at `0x180024565`
- `SPOOLSS!DllFreeSplMem` at `0x180024574`
- `SPOOLSS!DllFreeSplMem` at `0x180024595`
- `SPOOLSS!DllFreeSplMem` at `0x1800244ba`
- `SPOOLSS!DllFreeSplMem` at `0x180024565`
- `SPOOLSS!DllFreeSplMem` at `0x180024574`
- `SPOOLSS!DllFreeSplMem` at `0x180024595`
- `SPOOLSS!DllAllocSplMem` at `0x18002446f`
- `SPOOLSS!DllAllocSplMem` at `0x18002446f`
- `KERNEL32!RegOpenCurrentUser` at `0x18002445c`
- `KERNEL32!RegOpenCurrentUser` at `0x18002445c`

## pseudocode

```c
__int64 __fastcall AddPortInformationToPrinterName(LPCWSTR lpValue, const WCHAR *a2, _QWORD *a3)
{
  LSTATUS v5; // eax
  LSTATUS ValueW; // edi
  void *pvData; // rbx
  void *v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rcx
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF
  __int64 v13; // [rsp+80h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  *a3 = 0;
  pcbData = 1040;
  phkResult = 0;
  if ( a2 )
    v5 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20019u, &phkResult);
  else
    v5 = RegOpenCurrentUser(0x20019u, &phkResult);
  ValueW = v5;
  if ( v5 )
  {
    pvData = 0;
  }
  else
  {
    while ( 1 )
    {
      pvData = (void *)DllAllocSplMem(pcbData);
      if ( !pvData )
        break;
      ValueW = RegGetValueW(
                 phkResult,
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Devices",
                 lpValue,
                 2u,
                 0,
                 pvData,
                 &pcbData);
      if ( ValueW != 234 )
        goto LABEL_8;
      DllFreeSplMem(pvData);
    }
    ValueW = 8;
  }
LABEL_8:
  v8 = 0;
  if ( ValueW )
  {
    v8 = pvData;
    pvData = 0;
  }
  if ( v8 )
    DllFreeSplMem(v8);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( ValueW )
  {
    v9 = 1801;
  }
  else
  {
    v9 = StrCatAlloc(&v13, lpValue, L",", pvData);
    if ( !v9 )
    {
      *a3 = v13;
      v10 = 0;
      v13 = 0;
      goto LABEL_17;
    }
  }
  v10 = v13;
LABEL_17:
  if ( v10 )
  {
    DllFreeSplMem(v10);
    v13 = 0;
  }
  if ( pvData )
    DllFreeSplMem(pvData);
  return v9;
}

```

## disassembly

```asm
0x180024418  push    rbp
0x18002441a  push    rbx
0x18002441b  push    rsi
0x18002441c  push    rdi
0x18002441d  push    r14
0x18002441f  mov     rbp, rsp
0x180024422  sub     rsp, 40h
0x180024426  mov     [rbp+arg_10], 0
0x18002442e  mov     rsi, r8
0x180024431  mov     qword ptr [r8], 0
0x180024438  mov     r14, rcx
0x18002443b  mov     [rbp+arg_8], 410h
0x180024442  mov     [rbp+phkResult], 0
0x18002444a  test    rdx, rdx
0x18002444d  jnz     loc_18002453E
0x180024453  lea     rdx, [rbp+phkResult]; phkResult
0x180024457  mov     ecx, 20019h; samDesired
0x18002445c  call    cs:__imp_RegOpenCurrentUser
0x180024462  mov     edi, eax
0x180024464  test    eax, eax
0x180024466  jnz     loc_18002456D
0x18002446c  mov     ecx, [rbp+arg_8]
0x18002446f  call    cs:__imp_DllAllocSplMem
0x180024475  mov     rbx, rax
0x180024478  test    rax, rax
0x18002447b  jz      short loc_1800244C2
0x18002447d  mov     rcx, [rbp+phkResult]; hkey
0x180024481  lea     rax, [rbp+arg_8]
0x180024485  mov     [rsp+40h+pcbData], rax; pcbData
0x18002448a  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x180024491  mov     [rsp+40h+pvData], rbx; pvData
0x180024496  mov     r9d, 2; dwFlags
0x18002449c  mov     r8, r14; lpValue
0x18002449f  mov     [rsp+40h+pdwType], 0; pdwType
0x1800244a8  call    cs:__imp_RegGetValueW
0x1800244ae  mov     edi, eax
0x1800244b0  cmp     eax, 0EAh
0x1800244b5  jnz     short loc_1800244C7
0x1800244b7  mov     rcx, rbx
0x1800244ba  call    cs:__imp_DllFreeSplMem
0x1800244c0  jmp     short loc_18002446C
0x1800244c2  mov     edi, 8
0x1800244c7  xor     ecx, ecx
0x1800244c9  test    edi, edi
0x1800244cb  cmovnz  rcx, rbx
0x1800244cf  xor     eax, eax
0x1800244d1  test    edi, edi
0x1800244d3  cmovnz  rbx, rax
0x1800244d7  test    rcx, rcx
0x1800244da  jnz     loc_180024574
0x1800244e0  mov     rcx, [rbp+phkResult]; hKey
0x1800244e4  test    rcx, rcx
0x1800244e7  jnz     loc_18002457F
0x1800244ed  test    edi, edi
0x1800244ef  jnz     loc_18002458A
0x1800244f5  mov     r9, rbx
0x1800244f8  mov     [rsp+40h+pdwType], 0
0x180024501  lea     r8, Delimiter; ","
0x180024508  mov     rdx, r14
0x18002450b  lea     rcx, [rbp+arg_10]
0x18002450f  call    StrCatAlloc
0x180024514  mov     edi, eax
0x180024516  test    eax, eax
0x180024518  jnz     short loc_18002458F
0x18002451a  mov     rcx, [rbp+arg_10]
0x18002451e  mov     [rsi], rcx
0x180024521  xor     ecx, ecx
0x180024523  mov     [rbp+arg_10], rcx
0x180024527  test    rcx, rcx
0x18002452a  jnz     short loc_180024595
0x18002452c  test    rbx, rbx
0x18002452f  jnz     short loc_180024562
0x180024531  mov     eax, edi
0x180024533  add     rsp, 40h
0x180024537  pop     r14
0x180024539  pop     rdi
0x18002453a  pop     rsi
0x18002453b  pop     rbx
0x18002453c  pop     rbp
0x18002453d  retn
0x18002453e  lea     rax, [rbp+phkResult]
0x180024542  mov     r9d, 20019h; samDesired
0x180024548  xor     r8d, r8d; ulOptions
0x18002454b  mov     [rsp+40h+pdwType], rax; phkResult
0x180024550  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180024557  call    cs:__imp_RegOpenKeyExW
0x18002455d  jmp     loc_180024462
0x180024562  mov     rcx, rbx
0x180024565  call    cs:__imp_DllFreeSplMem
0x18002456b  jmp     short loc_180024531
0x18002456d  xor     ebx, ebx
0x18002456f  jmp     loc_1800244C7
0x180024574  call    cs:__imp_DllFreeSplMem
0x18002457a  jmp     loc_1800244E0
0x18002457f  call    cs:__imp_RegCloseKey
0x180024585  jmp     loc_1800244ED
0x18002458a  mov     edi, 709h
0x18002458f  mov     rcx, [rbp+arg_10]
0x180024593  jmp     short loc_180024527
0x180024595  call    cs:__imp_DllFreeSplMem
0x18002459b  mov     [rbp+arg_10], 0
0x1800245a3  jmp     short loc_18002452C
```
