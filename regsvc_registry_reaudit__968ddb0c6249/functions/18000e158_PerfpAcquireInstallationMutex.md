# PerfpAcquireInstallationMutex

- ea: `0x18000e158`
- end: `0x18000e1a0`
- name: `PerfpAcquireInstallationMutex`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006bc0`

## callees

- `0x18000dd34`
- `0x18000e158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e187`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e187`

## pseudocode

```c
__int64 PerfpAcquireInstallationMutex()
{
  HANDLE v0; // rcx
  unsigned int v1; // ecx
  DWORD v2; // eax
  HANDLE hHandle; // [rsp+30h] [rbp+8h] BYREF

  v0 = hMutex;
  hHandle = hMutex;
  if ( hMutex )
    goto LABEL_4;
  v1 = PerfpInitializeInstallationMutex(&hHandle);
  if ( !v1 )
  {
    v0 = hHandle;
LABEL_4:
    v2 = WaitForSingleObject(v0, 0xEA60u);
    return (v2 & 0xFFFFFF7F) != 0 ? v2 : 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000e158  sub     rsp, 28h
0x18000e15c  mov     rcx, cs:hMutex
0x18000e163  mov     [rsp+28h+hHandle], rcx
0x18000e168  test    rcx, rcx
0x18000e16b  jnz     short loc_18000E182
0x18000e16d  lea     rcx, [rsp+28h+hHandle]
0x18000e172  call    PerfpInitializeInstallationMutex
0x18000e177  mov     ecx, eax
0x18000e179  test    eax, eax
0x18000e17b  jnz     short loc_18000E199
0x18000e17d  mov     rcx, [rsp+28h+hHandle]; hHandle
0x18000e182  mov     edx, 0EA60h; dwMilliseconds
0x18000e187  call    cs:__imp_WaitForSingleObject
0x18000e18d  mov     ecx, eax
0x18000e18f  btr     ecx, 7
0x18000e193  neg     ecx
0x18000e195  sbb     ecx, ecx
0x18000e197  and     ecx, eax
0x18000e199  mov     eax, ecx
0x18000e19b  add     rsp, 28h
0x18000e19f  retn
```
