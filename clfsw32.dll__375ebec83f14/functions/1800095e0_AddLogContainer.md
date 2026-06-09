# AddLogContainer

- ea: `0x1800095e0`
- end: `0x180009622`
- name: `AddLogContainer`
- size: `66`
- prototype: `BOOL __stdcall(HANDLE hLog, PULONGLONG pcbContainer, LPWSTR pwszContainerPath, LPVOID pReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800095e0`
- `0x180009630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095f5`

## pseudocode

```c
BOOL __stdcall AddLogContainer(HANDLE hLog, PULONGLONG pcbContainer, LPWSTR pwszContainerPath, LPVOID pReserved)
{
  LPWSTR rgwszContainerPath; // [rsp+50h] [rbp+18h] BYREF

  rgwszContainerPath = pwszContainerPath;
  if ( pwszContainerPath )
    return AddLogContainerSet(hLog, 1u, pcbContainer, &rgwszContainerPath, pReserved);
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x1800095e0  mov     [rsp+rgwszContainerPath], r8
0x1800095e5  sub     rsp, 38h
0x1800095e9  mov     rax, rdx
0x1800095ec  test    r8, r8
0x1800095ef  jnz     short loc_180009605
0x1800095f1  lea     ecx, [r8+57h]; dwErrCode
0x1800095f5  call    cs:__imp_SetLastError
0x1800095fc  nop     dword ptr [rax+rax+00h]
0x180009601  xor     eax, eax
0x180009603  jmp     short loc_18000961C
0x180009605  mov     [rsp+38h+pReserved], r9; pReserved
0x18000960a  mov     edx, 1; cContainer
0x18000960f  lea     r9, [rsp+38h+rgwszContainerPath]; rgwszContainerPath
0x180009614  mov     r8, rax; pcbContainer
0x180009617  call    AddLogContainerSet
0x18000961c  add     rsp, 38h
0x180009620  retn
```
