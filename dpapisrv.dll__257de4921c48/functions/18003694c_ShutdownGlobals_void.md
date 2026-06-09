# ShutdownGlobals(void)

- ea: `0x18003694c`
- end: `0x180036a10`
- name: `?ShutdownGlobals@@YAKXZ`
- size: `196`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800283c4`

## callees

- `0x18003694c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003695c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003695c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003697f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003697f`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369b0`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369d6`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369fc`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369b0`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369d6`
- `ntdll!RtlDeleteCriticalSection` at `0x1800369fc`

## pseudocode

```c
__int64 ShutdownGlobals(void)
{
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( dword_18004CCB4 )
  {
    dword_18004CCB4 = 0;
    RtlDeleteCriticalSection(&stru_18004C978);
  }
  if ( dword_18004CCA8 )
  {
    dword_18004CCA8 = 0;
    RtlDeleteCriticalSection(&CriticalSection);
  }
  if ( dword_18004CCB8 )
  {
    dword_18004CCB8 = 0;
    RtlDeleteCriticalSection(&stru_18004C940);
  }
  return 0;
}

```

## disassembly

```asm
0x18003694c  sub     rsp, 28h
0x180036950  mov     rcx, cs:hKey; hKey
0x180036957  test    rcx, rcx
0x18003695a  jz      short loc_180036973
0x18003695c  call    cs:__imp_RegCloseKey
0x180036963  nop     dword ptr [rax+rax+00h]
0x180036968  mov     cs:hKey, 0
0x180036973  mov     rcx, cs:hObject; hObject
0x18003697a  test    rcx, rcx
0x18003697d  jz      short loc_180036996
0x18003697f  call    cs:__imp_CloseHandle
0x180036986  nop     dword ptr [rax+rax+00h]
0x18003698b  mov     cs:hObject, 0
0x180036996  cmp     cs:dword_18004CCB4, 0
0x18003699d  jz      short loc_1800369BC
0x18003699f  lea     rcx, stru_18004C978; CriticalSection
0x1800369a6  mov     cs:dword_18004CCB4, 0
0x1800369b0  call    cs:__imp_RtlDeleteCriticalSection
0x1800369b7  nop     dword ptr [rax+rax+00h]
0x1800369bc  cmp     cs:dword_18004CCA8, 0
0x1800369c3  jz      short loc_1800369E2
0x1800369c5  lea     rcx, CriticalSection; CriticalSection
0x1800369cc  mov     cs:dword_18004CCA8, 0
0x1800369d6  call    cs:__imp_RtlDeleteCriticalSection
0x1800369dd  nop     dword ptr [rax+rax+00h]
0x1800369e2  cmp     cs:dword_18004CCB8, 0
0x1800369e9  jz      short loc_180036A08
0x1800369eb  lea     rcx, stru_18004C940; CriticalSection
0x1800369f2  mov     cs:dword_18004CCB8, 0
0x1800369fc  call    cs:__imp_RtlDeleteCriticalSection
0x180036a03  nop     dword ptr [rax+rax+00h]
0x180036a08  xor     eax, eax
0x180036a0a  add     rsp, 28h
0x180036a0e  retn
```
