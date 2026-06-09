# DiscpVolumeDeviceNameForVolumeMountPoint

- ea: `0x18000bca8`
- end: `0x18000bda8`
- name: `DiscpVolumeDeviceNameForVolumeMountPoint`
- size: `256`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeMountPoint, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800080b0`

## callees

- `0x18000bca8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bd43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bd43`
- `ISCSIUM!DiscpAllocMemory` at `0x18000bd02`
- `ISCSIUM!DiscpAllocMemory` at `0x18000bd02`
- `ISCSIUM!DiscpFreeDeviceInterfaceList` at `0x18000bd8f`
- `ISCSIUM!DiscpFreeDeviceInterfaceList` at `0x18000bd8f`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bd79`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bd79`
- `ISCSIUM!DiscpDuplicateString` at `0x18000bd66`
- `ISCSIUM!DiscpDuplicateString` at `0x18000bd66`
- `ISCSIUM!DiscpEnumerateDeviceInterfaces` at `0x18000bced`
- `ISCSIUM!DiscpEnumerateDeviceInterfaces` at `0x18000bced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000bd1c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000bd1c`

## pseudocode

```c
__int64 __fastcall DiscpVolumeDeviceNameForVolumeMountPoint(LPCWSTR lpszVolumeMountPoint, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  unsigned int v8; // esi
  __int64 v9; // r14
  DWORD LastError; // eax
  unsigned int v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  v4 = DiscpEnumerateDeviceInterfaces(&GUID_DEVINTERFACE_VOLUME, DiscpVolumeMapCallback, 0, &v12, &v13);
  v5 = v4;
  if ( !v4 )
  {
    v6 = (WCHAR *)DiscpAllocMemory(520);
    v7 = v6;
    if ( !v6 )
    {
      LODWORD(v5) = 8;
      goto LABEL_13;
    }
    if ( GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, v6, 0x104u) )
    {
      v8 = v12;
      v9 = v13;
      if ( !v12 )
      {
LABEL_7:
        LODWORD(v5) = -268500899;
LABEL_11:
        DiscpFreeMemory(v7);
LABEL_13:
        DiscpFreeDeviceInterfaceList(v12, v13);
        return (unsigned int)v5;
      }
      while ( (unsigned int)_o__wcsicmp(v7, *(_QWORD *)(v9 + 96 * v5 + 88)) )
      {
        v5 = (unsigned int)(v5 + 1);
        if ( (unsigned int)v5 >= v8 )
          goto LABEL_7;
      }
      LastError = DiscpDuplicateString(a2, *(_QWORD *)(v9 + 96 * v5 + 80) + 4LL);
    }
    else
    {
      LastError = GetLastError();
    }
    LODWORD(v5) = LastError;
    goto LABEL_11;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000bca8  mov     r11, rsp
0x18000bcab  mov     [r11+8], rbx
0x18000bcaf  push    rbp
0x18000bcb0  push    rsi
0x18000bcb1  push    rdi
0x18000bcb2  push    r14
0x18000bcb4  push    r15
0x18000bcb6  sub     rsp, 30h
0x18000bcba  mov     r15, rdx
0x18000bcbd  mov     qword ptr [r11+20h], 0
0x18000bcc5  mov     rsi, rcx
0x18000bcc8  mov     [rsp+58h+arg_10], 0
0x18000bcd0  lea     rax, [r11+20h]
0x18000bcd4  xor     r8d, r8d
0x18000bcd7  lea     rdx, DiscpVolumeMapCallback
0x18000bcde  mov     [r11-38h], rax
0x18000bce2  lea     rcx, GUID_DEVINTERFACE_VOLUME
0x18000bce9  lea     r9, [r11+18h]
0x18000bced  call    cs:__imp_DiscpEnumerateDeviceInterfaces
0x18000bcf3  mov     ebx, eax
0x18000bcf5  test    eax, eax
0x18000bcf7  jnz     loc_18000BD95
0x18000bcfd  mov     ecx, 208h
0x18000bd02  call    cs:__imp_DiscpAllocMemory
0x18000bd08  mov     rdi, rax
0x18000bd0b  test    rax, rax
0x18000bd0e  jz      short loc_18000BD81
0x18000bd10  mov     r8d, 104h; cchBufferLength
0x18000bd16  mov     rdx, rax; lpszVolumeName
0x18000bd19  mov     rcx, rsi; lpszVolumeMountPoint
0x18000bd1c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000bd22  test    eax, eax
0x18000bd24  jz      short loc_18000BD6E
0x18000bd26  mov     esi, [rsp+58h+arg_10]
0x18000bd2a  mov     r14, [rsp+58h+arg_18]
0x18000bd2f  test    esi, esi
0x18000bd31  jz      short loc_18000BD53
0x18000bd33  lea     rbp, [rbx+rbx*2]
0x18000bd37  mov     rcx, rdi
0x18000bd3a  shl     rbp, 5
0x18000bd3e  mov     rdx, [r14+rbp+58h]
0x18000bd43  call    cs:__imp__o__wcsicmp
0x18000bd49  test    eax, eax
0x18000bd4b  jz      short loc_18000BD5A
0x18000bd4d  inc     ebx
0x18000bd4f  cmp     ebx, esi
0x18000bd51  jb      short loc_18000BD33
0x18000bd53  mov     ebx, 0EFFF005Dh
0x18000bd58  jmp     short loc_18000BD76
0x18000bd5a  mov     rdx, [r14+rbp+50h]
0x18000bd5f  mov     rcx, r15
0x18000bd62  add     rdx, 4
0x18000bd66  call    cs:__imp_DiscpDuplicateString
0x18000bd6c  jmp     short loc_18000BD74
0x18000bd6e  call    cs:__imp_GetLastError
0x18000bd74  mov     ebx, eax
0x18000bd76  mov     rcx, rdi
0x18000bd79  call    cs:__imp_DiscpFreeMemory
0x18000bd7f  jmp     short loc_18000BD86
0x18000bd81  mov     ebx, 8
0x18000bd86  mov     rdx, [rsp+58h+arg_18]
0x18000bd8b  mov     ecx, [rsp+58h+arg_10]
0x18000bd8f  call    cs:__imp_DiscpFreeDeviceInterfaceList
0x18000bd95  mov     eax, ebx
0x18000bd97  mov     rbx, [rsp+58h+arg_0]
0x18000bd9c  add     rsp, 30h
0x18000bda0  pop     r15
0x18000bda2  pop     r14
0x18000bda4  pop     rdi
0x18000bda5  pop     rsi
0x18000bda6  pop     rbp
0x18000bda7  retn
```
