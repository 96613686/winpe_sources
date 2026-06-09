# CreateVolumeID(ushort const *,_volumeid * *,uint *)

- ea: `0x1800023f0`
- end: `0x1800024f7`
- name: `?CreateVolumeID@@YAHPEBGPEAPEAU_volumeid@@PEAI@Z`
- size: `263`
- prototype: `int __fastcall(WCHAR *, struct _volumeid **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001b60`

## callees

- `0x1800023f0`
- `0x1800028c0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024ab`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024ab`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000248a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000248a`

## pseudocode

```c
int __fastcall CreateVolumeID(WCHAR *a1, struct _volumeid **a2, unsigned int *a3)
{
  WCHAR *p_RootPathName; // r9
  __int64 v7; // rax
  __int64 v8; // r10
  WCHAR *v9; // rcx
  int result; // eax
  DWORD v11; // ebx
  UINT DriveTypeW; // eax
  DWORD VolumeSerialNumber; // [rsp+40h] [rbp-238h] BYREF
  WCHAR RootPathName; // [rsp+48h] [rbp-230h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+50h] [rbp-228h] BYREF

  p_RootPathName = &RootPathName;
  VolumeSerialNumber = 0;
  v7 = 2147483646;
  v8 = 4;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *p_RootPathName++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = p_RootPathName - 1;
  if ( v8 )
    v9 = p_RootPathName;
  *v9 = 0;
  result = GetVolumeInformationW(&RootPathName, VolumeNameBuffer, 0x104u, &VolumeSerialNumber, 0, 0, 0, 0);
  if ( result )
  {
    v11 = VolumeSerialNumber;
    DriveTypeW = GetDriveTypeW(&RootPathName);
    return UnifyIVolumeIDInfo(DriveTypeW, v11, VolumeNameBuffer, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800023f0  mov     [rsp+arg_18], rsi
0x1800023f5  push    rdi
0x1800023f6  sub     rsp, 270h
0x1800023fd  mov     rax, cs:__security_cookie
0x180002404  xor     rax, rsp
0x180002407  mov     [rsp+278h+var_18], rax
0x18000240f  mov     rsi, r8
0x180002412  lea     r9, [rsp+278h+RootPathName]
0x180002417  xor     r8d, r8d
0x18000241a  mov     rdi, rdx
0x18000241d  mov     [rsp+278h+VolumeSerialNumber], r8d
0x180002422  mov     rdx, rcx
0x180002425  mov     eax, 7FFFFFFEh
0x18000242a  mov     r10d, 4
0x180002430  test    rax, rax
0x180002433  jz      short loc_180002452
0x180002435  movzx   ecx, word ptr [rdx]
0x180002438  test    cx, cx
0x18000243b  jz      short loc_180002452
0x18000243d  mov     [r9], cx
0x180002441  add     rdx, 2
0x180002445  add     r9, 2
0x180002449  dec     rax
0x18000244c  sub     r10, 1
0x180002450  jnz     short loc_180002430
0x180002452  mov     [rsp+278h+nFileSystemNameSize], r8d; nFileSystemNameSize
0x180002457  lea     rcx, [r9-2]
0x18000245b  mov     [rsp+278h+lpFileSystemNameBuffer], r8; lpFileSystemNameBuffer
0x180002460  lea     rdx, [rsp+278h+VolumeNameBuffer]; lpVolumeNameBuffer
0x180002465  mov     [rsp+278h+lpFileSystemFlags], r8; lpFileSystemFlags
0x18000246a  test    r10, r10
0x18000246d  mov     [rsp+278h+lpMaximumComponentLength], r8; lpMaximumComponentLength
0x180002472  cmovnz  rcx, r9
0x180002476  lea     r9, [rsp+278h+VolumeSerialNumber]; lpVolumeSerialNumber
0x18000247b  mov     [rcx], r8w
0x18000247f  mov     r8d, 104h; nVolumeNameSize
0x180002485  lea     rcx, [rsp+278h+RootPathName]; lpRootPathName
0x18000248a  call    cs:__imp_GetVolumeInformationW
0x180002491  nop     dword ptr [rax+rax+00h]
0x180002496  test    eax, eax
0x180002498  jz      short loc_1800024D5
0x18000249a  mov     [rsp+278h+arg_0], rbx
0x1800024a2  lea     rcx, [rsp+278h+RootPathName]; lpRootPathName
0x1800024a7  mov     ebx, [rsp+278h+VolumeSerialNumber]
0x1800024ab  call    cs:__imp_GetDriveTypeW
0x1800024b2  nop     dword ptr [rax+rax+00h]
0x1800024b7  mov     r9, rdi; struct _ivolumeidW **
0x1800024ba  mov     [rsp+278h+lpMaximumComponentLength], rsi; unsigned int *
0x1800024bf  mov     ecx, eax; unsigned int
0x1800024c1  lea     r8, [rsp+278h+VolumeNameBuffer]; unsigned __int16 *
0x1800024c6  mov     edx, ebx; unsigned int
0x1800024c8  call    ?UnifyIVolumeIDInfo@@YAHIKPEBGPEAPEAU_ivolumeidW@@PEAI@Z; UnifyIVolumeIDInfo(uint,ulong,ushort const *,_ivolumeidW * *,uint *)
0x1800024cd  mov     rbx, [rsp+278h+arg_0]
0x1800024d5  mov     rcx, [rsp+278h+var_18]
0x1800024dd  xor     rcx, rsp; StackCookie
0x1800024e0  call    __security_check_cookie
0x1800024e5  mov     rsi, [rsp+278h+arg_18]
0x1800024ed  add     rsp, 270h
0x1800024f4  pop     rdi
0x1800024f5  retn
```
