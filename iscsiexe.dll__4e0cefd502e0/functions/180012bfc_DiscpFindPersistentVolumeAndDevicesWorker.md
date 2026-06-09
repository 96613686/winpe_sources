# DiscpFindPersistentVolumeAndDevicesWorker

- ea: `0x180012bfc`
- end: `0x180012d8e`
- name: `DiscpFindPersistentVolumeAndDevicesWorker`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180013b24`

## callees

- `0x180001410`
- `0x180003198`
- `0x18000325c`
- `0x180012bfc`
- `0x180012fb4`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180012cb1`
- `ISCSIUM!DiscpAllocMemory` at `0x180012cb1`
- `ISCSIUM!DiscpFreeDeviceInterfaceList` at `0x180012d52`
- `ISCSIUM!DiscpFreeDeviceInterfaceList` at `0x180012d52`
- `ISCSIUM!DiscpFreeMemory` at `0x180012d0a`
- `ISCSIUM!DiscpFreeMemory` at `0x180012d0a`
- `ISCSIUM!DiscpEnumerateDeviceInterfaces` at `0x180012c48`
- `ISCSIUM!DiscpEnumerateDeviceInterfaces` at `0x180012c48`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180012ced`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180012ced`

## pseudocode

```c
__int64 __fastcall DiscpFindPersistentVolumeAndDevicesWorker(_QWORD *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  unsigned int i; // edi
  __int64 v5; // r14
  __int64 v6; // rax
  unsigned int v7; // r15d
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  unsigned int j; // edi
  unsigned int v12; // [rsp+30h] [rbp-59h] BYREF
  __int64 v13; // [rsp+38h] [rbp-51h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-49h] BYREF

  v12 = 0;
  v13 = 0;
  v2 = DiscpEnumerateDeviceInterfaces(a1, 0, 0, &v12, &v13);
  if ( v2 )
  {
    if ( v2 == 259 )
      return 0;
  }
  else
  {
    if ( *a1 == *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1 && a1[1] == *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4 )
    {
      v3 = v12;
      for ( i = 0; i < v12; ++i )
      {
        v5 = *(_QWORD *)(96LL * i + v13 + 80);
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)(v5 + 2 * v6 + 4) );
        v7 = v6 + 2;
        v8 = (wchar_t *)DiscpAllocMemory((unsigned int)(2 * (v6 + 2)));
        v9 = v8;
        if ( v8 )
        {
          StringCchCopyW(v8, v7, (STRSAFE_LPCWSTR)(v5 + 4));
          StringCchCatW(v9, v7, L"\\");
          if ( GetVolumeNameForVolumeMountPointW(v9, szVolumeName, 0x32u) && szVolumeName[0] )
            DiscpHandleVolumeOrDeviceArrival(v5 + 4);
          DiscpFreeMemory(v9);
        }
        v3 = v12;
      }
    }
    else
    {
      v3 = v12;
      for ( j = 0; j < v12; ++j )
      {
        DiscpHandleVolumeOrDeviceArrival(*(_QWORD *)(96LL * j + v13 + 80) + 4LL);
        v3 = v12;
      }
    }
    DiscpFreeDeviceInterfaceList(v3, v13);
  }
  return v2;
}

```

## disassembly

```asm
0x180012bfc  mov     [rsp-8+arg_8], rbx
0x180012c01  mov     [rsp-8+arg_10], rsi
0x180012c06  push    rbp
0x180012c07  push    rdi
0x180012c08  push    r12
0x180012c0a  push    r14
0x180012c0c  push    r15
0x180012c0e  lea     rbp, [rsp-37h]
0x180012c13  sub     rsp, 0C0h
0x180012c1a  mov     rax, cs:__security_cookie
0x180012c21  xor     rax, rsp
0x180012c24  mov     [rbp+57h+var_30], rax
0x180012c28  xor     r12d, r12d
0x180012c2b  lea     rax, [rbp+57h+var_A8]
0x180012c2f  lea     r9, [rbp+57h+var_B0]
0x180012c33  mov     [rbp+57h+var_B0], r12d
0x180012c37  xor     r8d, r8d
0x180012c3a  mov     [rbp+57h+var_A8], r12
0x180012c3e  xor     edx, edx
0x180012c40  mov     [rsp+0E0h+var_C0], rax
0x180012c45  mov     rdi, rcx
0x180012c48  call    cs:__imp_DiscpEnumerateDeviceInterfaces
0x180012c4e  mov     ebx, eax
0x180012c50  test    eax, eax
0x180012c52  jnz     loc_180012D5A
0x180012c58  mov     rcx, [rdi]
0x180012c5b  cmp     rcx, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x180012c62  jnz     loc_180012D1F
0x180012c68  mov     rcx, [rdi+8]
0x180012c6c  cmp     rcx, qword ptr cs:GUID_DEVINTERFACE_VOLUME.Data4
0x180012c73  jnz     loc_180012D1F
0x180012c79  mov     ecx, [rbp+57h+var_B0]
0x180012c7c  mov     edi, r12d
0x180012c7f  test    ecx, ecx
0x180012c81  jz      loc_180012D4E
0x180012c87  mov     eax, edi
0x180012c89  lea     rcx, [rax+rax*2]
0x180012c8d  mov     rax, [rbp+57h+var_A8]
0x180012c91  shl     rcx, 5
0x180012c95  mov     r14, [rcx+rax+50h]
0x180012c9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012c9e  inc     rax
0x180012ca1  cmp     [r14+rax*2+4], r12w
0x180012ca7  jnz     short loc_180012C9E
0x180012ca9  lea     r15d, [rax+2]
0x180012cad  lea     ecx, [r15+r15]
0x180012cb1  call    cs:__imp_DiscpAllocMemory
0x180012cb7  mov     rsi, rax
0x180012cba  test    rax, rax
0x180012cbd  jz      short loc_180012D10
0x180012cbf  lea     r8, [r14+4]; pszSrc
0x180012cc3  mov     edx, r15d; cchDest
0x180012cc6  mov     rcx, rax; pszDest
0x180012cc9  call    StringCchCopyW
0x180012cce  lea     r8, asc_180020E70; "\\"
0x180012cd5  mov     edx, r15d; cchDest
0x180012cd8  mov     rcx, rsi; pszDest
0x180012cdb  call    StringCchCatW
0x180012ce0  mov     r8d, 32h ; '2'; cchBufferLength
0x180012ce6  lea     rdx, [rbp+57h+szVolumeName]; lpszVolumeName
0x180012cea  mov     rcx, rsi; lpszVolumeMountPoint
0x180012ced  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180012cf3  test    eax, eax
0x180012cf5  jz      short loc_180012D07
0x180012cf7  cmp     [rbp+57h+szVolumeName], r12w
0x180012cfc  jz      short loc_180012D07
0x180012cfe  lea     rcx, [r14+4]
0x180012d02  call    DiscpHandleVolumeOrDeviceArrival
0x180012d07  mov     rcx, rsi
0x180012d0a  call    cs:__imp_DiscpFreeMemory
0x180012d10  mov     ecx, [rbp+57h+var_B0]
0x180012d13  inc     edi
0x180012d15  cmp     edi, ecx
0x180012d17  jb      loc_180012C87
0x180012d1d  jmp     short loc_180012D4E
0x180012d1f  mov     ecx, [rbp+57h+var_B0]
0x180012d22  mov     edi, r12d
0x180012d25  test    ecx, ecx
0x180012d27  jz      short loc_180012D4E
0x180012d29  mov     eax, edi
0x180012d2b  lea     rcx, [rax+rax*2]
0x180012d2f  mov     rax, [rbp+57h+var_A8]
0x180012d33  shl     rcx, 5
0x180012d37  mov     rcx, [rcx+rax+50h]
0x180012d3c  add     rcx, 4
0x180012d40  call    DiscpHandleVolumeOrDeviceArrival
0x180012d45  mov     ecx, [rbp+57h+var_B0]
0x180012d48  inc     edi
0x180012d4a  cmp     edi, ecx
0x180012d4c  jb      short loc_180012D29
0x180012d4e  mov     rdx, [rbp+57h+var_A8]
0x180012d52  call    cs:__imp_DiscpFreeDeviceInterfaceList
0x180012d58  jmp     short loc_180012D64
0x180012d5a  cmp     ebx, 103h
0x180012d60  cmovz   ebx, r12d
0x180012d64  mov     eax, ebx
0x180012d66  mov     rcx, [rbp+57h+var_30]
0x180012d6a  xor     rcx, rsp; StackCookie
0x180012d6d  call    __security_check_cookie
0x180012d72  lea     r11, [rsp+0E0h+var_20]
0x180012d7a  mov     rbx, [r11+38h]
0x180012d7e  mov     rsi, [r11+40h]
0x180012d82  mov     rsp, r11
0x180012d85  pop     r15
0x180012d87  pop     r14
0x180012d89  pop     r12
0x180012d8b  pop     rdi
0x180012d8c  pop     rbp
0x180012d8d  retn
```
