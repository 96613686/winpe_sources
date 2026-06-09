# PuInitializeDisk(ushort const *,PU_DISK_PROPERTIES *,_PARTITION_STYLE)

- ea: `0x1801a4df0`
- end: `0x1801a503d`
- name: `?PuInitializeDisk@@YAJPEBGPEAVPU_DISK_PROPERTIES@@W4_PARTITION_STYLE@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct PU_DISK_PROPERTIES *, enum _PARTITION_STYLE)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801168e0`

## callees

- `0x18019a4a4`
- `0x18019cd40`
- `0x18019d030`
- `0x1801a4df0`
- `0x1801a59d0`
- `0x1801a5fb4`
- `0x1801a984c`
- `0x1801a9f98`
- `0x1801aa088`
- `0x1801aac84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a4f2d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801a4e19`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801a4f92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801a4e19`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801a4f92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a5021`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a4e75`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a4e75`

## string_xrefs

- `0x1801a4eac`: `CreateFile`
- `0x1801a4f71`: `PuWriteBootCode`
- `0x1801a4f49`: `PuCreateMSRPartition`
- `0x1801a4f09`: `PuCreateDisk`

## pseudocode

```c
__int64 __fastcall PuInitializeDisk(LPCWSTR lpFileName, struct PU_DISK_PROPERTIES *a2, unsigned int a3)
{
  __int64 FileW; // rsi
  signed int v7; // ebx
  const char *v8; // rdi
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  int v12; // eax
  int v13; // ecx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-58h] BYREF
  LARGE_INTEGER v16; // [rsp+48h] [rbp-50h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]

  FileW = -1;
  PU_TIMER::PU_TIMER((PU_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)a2 + 80) || *((_DWORD *)a2 + 55) != 2 )
  {
    v7 = -2147220992;
    v8 = "Not an unallocated disk";
  }
  else if ( a3 <= 1 )
  {
    v7 = 0;
    FileW = (__int64)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
      goto LABEL_41;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "CreateFile";
    }
    else
    {
LABEL_41:
      if ( (unsigned int)PuPerformBandManagement(a2) && (v7 = ActivateBandCapability((void *)FileW), v7 < 0) )
      {
        v8 = "ActivateBandCapability";
      }
      else
      {
        if ( (unsigned int)PuCreateDisk((HANDLE)FileW, (enum _PARTITION_STYLE)a3) )
          goto LABEL_23;
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 >= 0 )
        {
LABEL_23:
          if ( a3 != 1 || (unsigned int)PuIsWinPE() || (unsigned int)PuCreateMSRPartition((HANDLE)FileW) )
            goto LABEL_25;
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          if ( v7 >= 0 )
          {
LABEL_25:
            v8 = 0;
            v12 = PuWriteBootCode((HANDLE)FileW, a2);
            if ( v12 )
            {
              if ( v12 > 0 )
                v7 = (unsigned __int16)v12 | 0x80070000;
              else
                v7 = v12;
              v8 = "PuWriteBootCode";
            }
          }
          else
          {
            v8 = "PuCreateMSRPartition";
          }
        }
        else
        {
          v8 = "PuCreateDisk";
        }
      }
    }
  }
  else
  {
    v7 = -2147220991;
    v8 = "Invalid partition style";
  }
  QueryPerformanceCounter(&v16);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 1) != 0 )
      McTemplateU0sqqsd_EventWriteTransfer(
        v13,
        (unsigned int)InitializeDiskFailed,
        (unsigned int)"PuInitializeDisk",
        *((_DWORD *)a2 + 15),
        a3,
        (__int64)v8,
        v7);
  }
  else if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 2) != 0 )
  {
    McTemplateU0sqqx_EventWriteTransfer(
      v13,
      (unsigned int)InitializeDiskSucceeded,
      (unsigned int)"PuInitializeDisk",
      *((_DWORD *)a2 + 15),
      a3,
      1000000 * (v16.QuadPart - PerformanceCount.QuadPart) / v17);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801a4df0  push    rbx
0x1801a4df2  push    rbp
0x1801a4df3  push    rsi
0x1801a4df4  push    rdi
0x1801a4df5  push    r12
0x1801a4df7  push    r14
0x1801a4df9  sub     rsp, 68h
0x1801a4dfd  mov     rdi, rcx
0x1801a4e00  mov     r14d, r8d
0x1801a4e03  lea     rcx, [rsp+98h+PerformanceCount]; this
0x1801a4e08  mov     rbp, rdx
0x1801a4e0b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801a4e0f  call    ??0PU_TIMER@@QEAA@XZ; PU_TIMER::PU_TIMER(void)
0x1801a4e14  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x1801a4e19  call    cs:__imp_QueryPerformanceCounter
0x1801a4e20  nop     dword ptr [rax+rax+00h]
0x1801a4e25  cmp     dword ptr [rbp+140h], 0
0x1801a4e2c  jnz     loc_1801A4F81
0x1801a4e32  cmp     dword ptr [rbp+0DCh], 2
0x1801a4e39  jnz     loc_1801A4F81
0x1801a4e3f  cmp     r14d, 1
0x1801a4e43  jbe     short loc_1801A4E56
0x1801a4e45  mov     ebx, 80040201h
0x1801a4e4a  lea     rdi, aInvalidPartiti; "Invalid partition style"
0x1801a4e51  jmp     loc_1801A4F8D
0x1801a4e56  xor     ebx, ebx
0x1801a4e58  xor     r9d, r9d; lpSecurityAttributes
0x1801a4e5b  mov     [rsp+98h+hTemplateFile], rbx; hTemplateFile
0x1801a4e60  mov     edx, 0C0000000h; dwDesiredAccess
0x1801a4e65  mov     [rsp+98h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1801a4e69  mov     rcx, rdi; lpFileName
0x1801a4e6c  lea     r8d, [rbx+3]; dwShareMode
0x1801a4e70  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801a4e75  call    cs:__imp_CreateFileW
0x1801a4e7c  nop     dword ptr [rax+rax+00h]
0x1801a4e81  mov     rsi, rax
0x1801a4e84  mov     r12d, 80070000h
0x1801a4e8a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a4e8e  jnz     short loc_1801A4EB8
0x1801a4e90  call    cs:__imp_GetLastError
0x1801a4e97  nop     dword ptr [rax+rax+00h]
0x1801a4e9c  mov     ebx, eax
0x1801a4e9e  test    eax, eax
0x1801a4ea0  jle     short loc_1801A4EA8
0x1801a4ea2  movzx   ebx, ax
0x1801a4ea5  or      ebx, r12d
0x1801a4ea8  test    ebx, ebx
0x1801a4eaa  jns     short loc_1801A4EB8
0x1801a4eac  lea     rdi, aCreatefile; "CreateFile"
0x1801a4eb3  jmp     loc_1801A4F8D
0x1801a4eb8  mov     rcx, rbp; struct PU_DISK_PROPERTIES *
0x1801a4ebb  call    ?PuPerformBandManagement@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuPerformBandManagement(PU_DISK_PROPERTIES *)
0x1801a4ec0  test    eax, eax
0x1801a4ec2  jz      short loc_1801A4EDE
0x1801a4ec4  mov     rcx, rsi; void *
0x1801a4ec7  call    ?ActivateBandCapability@@YAJPEAX@Z; ActivateBandCapability(void *)
0x1801a4ecc  mov     ebx, eax
0x1801a4ece  test    eax, eax
0x1801a4ed0  jns     short loc_1801A4EDE
0x1801a4ed2  lea     rdi, aActivatebandca; "ActivateBandCapability"
0x1801a4ed9  jmp     loc_1801A4F8D
0x1801a4ede  mov     edx, r14d; enum _PARTITION_STYLE
0x1801a4ee1  mov     rcx, rsi; hDevice
0x1801a4ee4  call    ?PuCreateDisk@@YAHPEAXW4_PARTITION_STYLE@@@Z; PuCreateDisk(void *,_PARTITION_STYLE)
0x1801a4ee9  test    eax, eax
0x1801a4eeb  jnz     short loc_1801A4F12
0x1801a4eed  call    cs:__imp_GetLastError
0x1801a4ef4  nop     dword ptr [rax+rax+00h]
0x1801a4ef9  mov     ebx, eax
0x1801a4efb  test    eax, eax
0x1801a4efd  jle     short loc_1801A4F05
0x1801a4eff  movzx   ebx, ax
0x1801a4f02  or      ebx, r12d
0x1801a4f05  test    ebx, ebx
0x1801a4f07  jns     short loc_1801A4F12
0x1801a4f09  lea     rdi, aPucreatedisk; "PuCreateDisk"
0x1801a4f10  jmp     short loc_1801A4F8D
0x1801a4f12  cmp     r14d, 1
0x1801a4f16  jnz     short loc_1801A4F52
0x1801a4f18  call    ?PuIsWinPE@@YAHXZ; PuIsWinPE(void)
0x1801a4f1d  test    eax, eax
0x1801a4f1f  jnz     short loc_1801A4F52
0x1801a4f21  mov     rcx, rsi; hDevice
0x1801a4f24  call    ?PuCreateMSRPartition@@YAHPEAX@Z; PuCreateMSRPartition(void *)
0x1801a4f29  test    eax, eax
0x1801a4f2b  jnz     short loc_1801A4F52
0x1801a4f2d  call    cs:__imp_GetLastError
0x1801a4f34  nop     dword ptr [rax+rax+00h]
0x1801a4f39  mov     ebx, eax
0x1801a4f3b  test    eax, eax
0x1801a4f3d  jle     short loc_1801A4F45
0x1801a4f3f  movzx   ebx, ax
0x1801a4f42  or      ebx, r12d
0x1801a4f45  test    ebx, ebx
0x1801a4f47  jns     short loc_1801A4F52
0x1801a4f49  lea     rdi, aPucreatemsrpar; "PuCreateMSRPartition"
0x1801a4f50  jmp     short loc_1801A4F8D
0x1801a4f52  mov     rdx, rbp; struct PU_DISK_PROPERTIES *
0x1801a4f55  mov     rcx, rsi; hFile
0x1801a4f58  xor     edi, edi
0x1801a4f5a  call    ?PuWriteBootCode@@YAKPEAXPEAVPU_DISK_PROPERTIES@@@Z; PuWriteBootCode(void *,PU_DISK_PROPERTIES *)
0x1801a4f5f  test    eax, eax
0x1801a4f61  jz      short loc_1801A4F8D
0x1801a4f63  jg      short loc_1801A4F69
0x1801a4f65  mov     ebx, eax
0x1801a4f67  jmp     short loc_1801A4F6F
0x1801a4f69  movzx   ebx, ax
0x1801a4f6c  or      ebx, r12d
0x1801a4f6f  test    ebx, ebx
0x1801a4f71  lea     rax, aPuwritebootcod; "PuWriteBootCode"
0x1801a4f78  cmovns  rax, rdi
0x1801a4f7c  mov     rdi, rax
0x1801a4f7f  jmp     short loc_1801A4F8D
0x1801a4f81  mov     ebx, 80040200h
0x1801a4f86  lea     rdi, aNotAnUnallocat; "Not an unallocated disk"
0x1801a4f8d  lea     rcx, [rsp+98h+var_50]; lpPerformanceCount
0x1801a4f92  call    cs:__imp_QueryPerformanceCounter
0x1801a4f99  nop     dword ptr [rax+rax+00h]
0x1801a4f9e  test    ebx, ebx
0x1801a4fa0  js      short loc_1801A4FE6
0x1801a4fa2  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 2
0x1801a4fa9  jz      short loc_1801A5014
0x1801a4fab  mov     rax, qword ptr [rsp+98h+var_50]
0x1801a4fb0  lea     r8, aPuinitializedi; "PuInitializeDisk"
0x1801a4fb7  sub     rax, qword ptr [rsp+98h+PerformanceCount]
0x1801a4fbc  mov     r9d, [rbp+3Ch]
0x1801a4fc0  imul    rax, 0F4240h
0x1801a4fc7  cqo
0x1801a4fc9  idiv    [rsp+98h+var_48]
0x1801a4fce  lea     rdx, InitializeDiskSucceeded
0x1801a4fd5  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax
0x1801a4fda  mov     [rsp+98h+dwCreationDisposition], r14d
0x1801a4fdf  call    McTemplateU0sqqx_EventWriteTransfer
0x1801a4fe4  jmp     short loc_1801A5014
0x1801a4fe6  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 1
0x1801a4fed  jz      short loc_1801A5014
0x1801a4fef  mov     r9d, [rbp+3Ch]
0x1801a4ff3  lea     r8, aPuinitializedi; "PuInitializeDisk"
0x1801a4ffa  mov     dword ptr [rsp+98h+hTemplateFile], ebx
0x1801a4ffe  lea     rdx, InitializeDiskFailed
0x1801a5005  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x1801a500a  mov     [rsp+98h+dwCreationDisposition], r14d
0x1801a500f  call    McTemplateU0sqqsd_EventWriteTransfer
0x1801a5014  lea     rax, [rsi-1]
0x1801a5018  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801a501c  ja      short loc_1801A502D
0x1801a501e  mov     rcx, rsi; hObject
0x1801a5021  call    cs:__imp_CloseHandle
0x1801a5028  nop     dword ptr [rax+rax+00h]
0x1801a502d  mov     eax, ebx
0x1801a502f  add     rsp, 68h
0x1801a5033  pop     r14
0x1801a5035  pop     r12
0x1801a5037  pop     rdi
0x1801a5038  pop     rsi
0x1801a5039  pop     rbp
0x1801a503a  pop     rbx
0x1801a503b  retn
```
