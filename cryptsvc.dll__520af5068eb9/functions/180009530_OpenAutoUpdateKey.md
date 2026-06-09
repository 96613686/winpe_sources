# _OpenAutoUpdateKey

- ea: `0x180009530`
- end: `0x1800095d9`
- name: `_OpenAutoUpdateKey`
- size: `169`
- prototype: `HKEY __fastcall(HKEY)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009388`
- `0x180009428`

## callees

- `0x180008330`
- `0x180009530`
- `0x180009854`
- `0x18000d760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009569`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009569`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x1800095a4`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x1800095a4`

## string_xrefs

- `0x180009562`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
HKEY __fastcall OpenAutoUpdateKey(HKEY a1)
{
  LSTATUS v1; // ebx
  LSTATUS AppContainerRegistryHandle; // eax
  HKEY v4; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  phkResult = 0;
  if ( a1 == HKEY_CURRENT_USER )
  {
    if ( (unsigned int)I_CryptIsAppContainerToken(0) )
      AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &v4);
    else
      AppContainerRegistryHandle = RegOpenHKCUEx(&v4);
    v1 = AppContainerRegistryHandle;
    if ( AppContainerRegistryHandle )
    {
LABEL_11:
      phkResult = 0;
      SetLastError(v1);
      return phkResult;
    }
    a1 = v4;
  }
  v1 = RegOpenKeyExW(a1, L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate", 0, 0x20119u, &phkResult);
  if ( v4 )
    RegCloseHKCU();
  if ( v1 )
    goto LABEL_11;
  return phkResult;
}

```

## disassembly

```asm
0x180009530  mov     [rsp+arg_10], rbx
0x180009535  push    rdi
0x180009536  sub     rsp, 30h
0x18000953a  xor     edi, edi
0x18000953c  mov     [rsp+38h+arg_0], rdi
0x180009541  mov     [rsp+38h+arg_8], rdi
0x180009546  cmp     rcx, 0FFFFFFFF80000001h
0x18000954d  jz      short loc_18000958F
0x18000954f  lea     rax, [rsp+38h+arg_8]
0x180009554  mov     r9d, 20119h; samDesired
0x18000955a  xor     r8d, r8d; ulOptions
0x18000955d  mov     [rsp+38h+phkResult], rax; phkResult
0x180009562  lea     rdx, SubKey; "Software\\Microsoft\\SystemCertificates"...
0x180009569  call    cs:__imp_RegOpenKeyExW
0x18000956f  mov     rcx, [rsp+38h+arg_0]
0x180009574  mov     ebx, eax
0x180009576  test    rcx, rcx
0x180009579  jnz     short loc_1800095C3
0x18000957b  test    ebx, ebx
0x18000957d  jnz     short loc_1800095CA
0x18000957f  mov     rax, [rsp+38h+arg_8]
0x180009584  mov     rbx, [rsp+38h+arg_10]
0x180009589  add     rsp, 30h
0x18000958d  pop     rdi
0x18000958e  retn
0x18000958f  xor     ecx, ecx
0x180009591  call    I_CryptIsAppContainerToken
0x180009596  test    eax, eax
0x180009598  jz      short loc_1800095B7
0x18000959a  lea     rdx, [rsp+38h+arg_0]
0x18000959f  mov     ecx, 20019h
0x1800095a4  call    cs:__imp_GetAppContainerRegistryHandle
0x1800095aa  mov     ebx, eax
0x1800095ac  test    eax, eax
0x1800095ae  jnz     short loc_1800095CA
0x1800095b0  mov     rcx, [rsp+38h+arg_0]
0x1800095b5  jmp     short loc_18000954F
0x1800095b7  lea     rcx, [rsp+38h+arg_0]; phkResult
0x1800095bc  call    RegOpenHKCUEx
0x1800095c1  jmp     short loc_1800095AA
0x1800095c3  call    RegCloseHKCU
0x1800095c8  jmp     short loc_18000957B
0x1800095ca  mov     ecx, ebx; dwErrCode
0x1800095cc  mov     [rsp+38h+arg_8], rdi
0x1800095d1  call    cs:__imp_SetLastError
0x1800095d7  jmp     short loc_18000957F
```
