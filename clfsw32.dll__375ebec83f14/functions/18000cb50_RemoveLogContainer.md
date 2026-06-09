# RemoveLogContainer

- ea: `0x18000cb50`
- end: `0x18000cb8e`
- name: `RemoveLogContainer`
- size: `62`
- prototype: `BOOL __stdcall(HANDLE hLog, LPWSTR pwszContainerPath, BOOL fForce, LPVOID pReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb50`
- `0x18000cba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb61`

## pseudocode

```c
BOOL __stdcall RemoveLogContainer(HANDLE hLog, LPWSTR pwszContainerPath, BOOL fForce, LPVOID pReserved)
{
  LPWSTR rgwszContainerPath; // [rsp+48h] [rbp+10h] BYREF

  rgwszContainerPath = pwszContainerPath;
  if ( pwszContainerPath )
    return RemoveLogContainerSet(hLog, 1u, &rgwszContainerPath, fForce, pReserved);
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18000cb50  mov     [rsp+rgwszContainerPath], rdx
0x18000cb55  sub     rsp, 38h
0x18000cb59  test    rdx, rdx
0x18000cb5c  jnz     short loc_18000CB71
0x18000cb5e  lea     ecx, [rdx+57h]; dwErrCode
0x18000cb61  call    cs:__imp_SetLastError
0x18000cb68  nop     dword ptr [rax+rax+00h]
0x18000cb6d  xor     eax, eax
0x18000cb6f  jmp     short loc_18000CB88
0x18000cb71  mov     [rsp+38h+pReserved], r9; pReserved
0x18000cb76  mov     edx, 1; cContainer
0x18000cb7b  mov     r9d, r8d; fForce
0x18000cb7e  lea     r8, [rsp+38h+rgwszContainerPath]; rgwszContainerPath
0x18000cb83  call    RemoveLogContainerSet
0x18000cb88  add     rsp, 38h
0x18000cb8c  retn
```
