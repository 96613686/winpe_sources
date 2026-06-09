# pUtilGetSystemDriveClusterSize

- ea: `0x18000880c`
- end: `0x1800088d1`
- name: `pUtilGetSystemDriveClusterSize`
- size: `197`
- prototype: `ULONG __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006dc4`
- `0x180007dec`

## callees

- `0x18000880c`
- `0x180008e30`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800088b2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800088b2`
- `KERNEL32!GetWindowsDirectoryW` at `0x180008834`
- `KERNEL32!GetWindowsDirectoryW` at `0x180008834`
- `KERNEL32!GetDiskFreeSpaceW` at `0x18000887d`
- `KERNEL32!GetDiskFreeSpaceW` at `0x18000887d`
- `KERNEL32!GetLastError` at `0x180008887`
- `KERNEL32!GetLastError` at `0x180008887`

## pseudocode

```c
ULONG __fastcall pUtilGetSystemDriveClusterSize(_DWORD *a1)
{
  UINT WindowsDirectoryW; // eax
  ULONG result; // eax
  unsigned __int64 v4; // rcx
  DWORD BytesPerSector; // [rsp+30h] [rbp-238h] BYREF
  DWORD SectorsPerCluster[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( !WindowsDirectoryW )
    return GetLastError();
  if ( WindowsDirectoryW >= 0x104 )
    return 13;
  SectorsPerCluster[0] = 0;
  BytesPerSector = 0;
  *a1 = 0;
  if ( !GetDiskFreeSpaceW(Buffer, SectorsPerCluster, &BytesPerSector, 0, 0) )
    return GetLastError();
  v4 = SectorsPerCluster[0] * (unsigned __int64)BytesPerSector;
  if ( v4 > 0xFFFFFFFF )
  {
    *a1 = -1;
    return RtlNtStatusToDosErrorNoTeb(-1073741675);
  }
  else
  {
    result = 0;
    *a1 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000880c  push    rbx
0x18000880e  sub     rsp, 260h
0x180008815  mov     rax, cs:__security_cookie
0x18000881c  xor     rax, rsp
0x18000881f  mov     [rsp+268h+var_18], rax
0x180008827  mov     rbx, rcx
0x18000882a  mov     edx, 104h; uSize
0x18000882f  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180008834  call    cs:__imp_GetWindowsDirectoryW
0x18000883a  test    eax, eax
0x18000883c  jz      short loc_180008887
0x18000883e  cmp     eax, 104h
0x180008843  jb      short loc_18000884C
0x180008845  mov     eax, 0Dh
0x18000884a  jmp     short loc_1800088B8
0x18000884c  xor     r9d, r9d; lpNumberOfFreeClusters
0x18000884f  mov     [rsp+268h+SectorsPerCluster], 0
0x180008857  lea     r8, [rsp+268h+BytesPerSector]; lpBytesPerSector
0x18000885c  mov     [rsp+268h+BytesPerSector], 0
0x180008864  lea     rdx, [rsp+268h+SectorsPerCluster]; lpSectorsPerCluster
0x180008869  mov     dword ptr [rbx], 0
0x18000886f  lea     rcx, [rsp+268h+Buffer]; lpRootPathName
0x180008874  mov     [rsp+268h+lpTotalNumberOfClusters], 0; lpTotalNumberOfClusters
0x18000887d  call    cs:__imp_GetDiskFreeSpaceW
0x180008883  test    eax, eax
0x180008885  jnz     short loc_18000888F
0x180008887  call    cs:__imp_GetLastError
0x18000888d  jmp     short loc_1800088B8
0x18000888f  mov     eax, [rsp+268h+SectorsPerCluster]
0x180008893  mov     ecx, [rsp+268h+BytesPerSector]
0x180008897  imul    rcx, rax
0x18000889b  mov     eax, 0FFFFFFFFh
0x1800088a0  cmp     rcx, rax
0x1800088a3  ja      short loc_1800088AB
0x1800088a5  xor     eax, eax
0x1800088a7  mov     [rbx], ecx
0x1800088a9  jmp     short loc_1800088B8
0x1800088ab  mov     ecx, 0C0000095h; Status
0x1800088b0  mov     [rbx], eax
0x1800088b2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800088b8  mov     rcx, [rsp+268h+var_18]
0x1800088c0  xor     rcx, rsp; StackCookie
0x1800088c3  call    __security_check_cookie
0x1800088c8  add     rsp, 260h
0x1800088cf  pop     rbx
0x1800088d0  retn
```
