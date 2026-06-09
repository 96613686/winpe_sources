# EnsureNoBootableCdDvdInserted(void)

- ea: `0x180042cc4`
- end: `0x180042fa6`
- name: `?EnsureNoBootableCdDvdInserted@@YAJXZ`
- size: `738`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180019ebc`
- `0x180064da0`
- `0x1800ab188`
- `0x1800b1450`
- `0x1800bae5c`
- `0x1800c60fc`

## callees

- `0x180042cc4`
- `0x18005e581`
- `0x18005e58d`
- `0x18011efc2`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180042d86`
- `ntdll!RtlSetThreadErrorMode` at `0x180042f59`
- `ntdll!RtlSetThreadErrorMode` at `0x1801208c4`
- `ntdll!RtlSetThreadErrorMode` at `0x180042d86`
- `ntdll!RtlSetThreadErrorMode` at `0x180042f59`
- `ntdll!RtlSetThreadErrorMode` at `0x1801208c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180120895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180120895`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180042d57`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180042d57`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042eec`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042eec`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180042e61`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x180042e61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042e27`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042e27`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180042de4`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180042de4`

## pseudocode

```c
__int64 EnsureNoBootableCdDvdInserted(void)
{
  __int64 FileW; // rbx
  DWORD LogicalDrives; // esi
  char *v2; // rdi
  int v3; // r14d
  unsigned int v4; // eax
  unsigned int v5; // esi
  DWORD v6; // r15d
  ULONG OldMode; // [rsp+40h] [rbp-A8h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+44h] [rbp-A4h] BYREF
  DWORD SectorsPerCluster; // [rsp+48h] [rbp-A0h] BYREF
  DWORD BytesPerSector; // [rsp+4Ch] [rbp-9Ch] BYREF
  __int64 v12; // [rsp+50h] [rbp-98h]
  char *v13; // [rsp+58h] [rbp-90h]
  DWORD TotalNumberOfClusters; // [rsp+60h] [rbp-88h] BYREF
  DWORD NumberOfBytesRead; // [rsp+64h] [rbp-84h] BYREF
  int v16; // [rsp+68h] [rbp-80h]
  DWORD v17; // [rsp+6Ch] [rbp-7Ch]
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp-78h] BYREF
  WCHAR RootPathName[4]; // [rsp+90h] [rbp-58h] BYREF
  WCHAR FileName[8]; // [rsp+98h] [rbp-50h] BYREF

  wcscpy(RootPathName, L"#:\\");
  wcscpy(FileName, L"\\\\.\\#:");
  memset(&Overlapped, 0, sizeof(Overlapped));
  TotalNumberOfClusters = 0;
  BytesPerSector = 0;
  NumberOfBytesRead = 0;
  FileW = -1;
  v12 = -1;
  LogicalDrives = GetLogicalDrives();
  NumberOfFreeClusters = 0;
  OldMode = 0;
  v2 = 0;
  v13 = 0;
  SectorsPerCluster = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  if ( LogicalDrives )
  {
    v3 = 0;
    v16 = 0;
    v4 = 0;
    while ( v4 < 0x1A && LogicalDrives )
    {
      if ( (LogicalDrives & 1) != 0 )
      {
        RootPathName[0] = v3 + 65;
        if ( GetDriveTypeW(RootPathName) == 5 )
        {
          FileName[4] = v3 + 65;
          FileW = (__int64)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          v12 = FileW;
          if ( FileW != -1 )
          {
            if ( GetDiskFreeSpaceW(
                   RootPathName,
                   &SectorsPerCluster,
                   &BytesPerSector,
                   &NumberOfFreeClusters,
                   &TotalNumberOfClusters) )
            {
              v6 = BytesPerSector;
              v2 = (char *)malloc_0(BytesPerSector);
              v13 = v2;
              if ( !v2 )
              {
                v5 = -2147024882;
                goto LABEL_19;
              }
              Overlapped.Pointer = (PVOID)(17 * v6);
              Overlapped.hEvent = 0;
              if ( ReadFile((HANDLE)FileW, v2, v6, &NumberOfBytesRead, &Overlapped)
                && !memcmp_0(v2 + 7, "EL TORITO SPECIFICATION", 0x17u) )
              {
                v5 = -2144272336;
                goto LABEL_19;
              }
              free_0(v2);
              v2 = 0;
              v13 = 0;
              CloseHandle((HANDLE)FileW);
              FileW = -1;
              v12 = -1;
            }
            else
            {
              CloseHandle((HANDLE)FileW);
              FileW = -1;
              v12 = -1;
            }
          }
        }
      }
      v4 = ++v3;
      v16 = v3;
      LogicalDrives >>= 1;
      v17 = LogicalDrives;
    }
  }
  v5 = 0;
LABEL_19:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v2 )
    free_0(v2);
  RtlSetThreadErrorMode(OldMode, 0);
  return v5;
}

```

## disassembly

```asm
0x180042cc4  mov     r11, rsp
0x180042cc7  push    rbx
0x180042cc8  push    rsi
0x180042cc9  push    rdi
0x180042cca  push    r12
0x180042ccc  push    r13
0x180042cce  push    r14
0x180042cd0  push    r15
0x180042cd2  sub     rsp, 0B0h
0x180042cd9  mov     rax, cs:__security_cookie
0x180042ce0  xor     rax, rsp
0x180042ce3  mov     [rsp+0E8h+var_40], rax
0x180042ceb  mov     rax, 5C003A0023h
0x180042cf5  mov     [r11-58h], rax
0x180042cf9  movsd   xmm0, qword ptr cs:asc_1801368D8; "\\\\.\\#:"
0x180042d01  movsd   qword ptr [r11-50h], xmm0
0x180042d07  mov     eax, dword ptr cs:asc_1801368D8+8; "#:"
0x180042d0d  mov     [r11-48h], eax
0x180042d11  movzx   eax, word ptr cs:asc_1801368D8+0Ch; ""
0x180042d18  mov     [r11-44h], ax
0x180042d1d  xor     r12d, r12d
0x180042d20  mov     [rsp+0E8h+NumberOfFreeClusters], r12d
0x180042d25  mov     [rsp+0E8h+OldMode], r12d
0x180042d2a  xorps   xmm0, xmm0
0x180042d2d  movups  xmmword ptr [rsp+0E8h+Overlapped.Internal], xmm0
0x180042d32  movups  xmmword ptr [r11-68h], xmm0
0x180042d37  mov     [rsp+0E8h+SectorsPerCluster], r12d
0x180042d3c  mov     [rsp+0E8h+TotalNumberOfClusters], r12d
0x180042d41  mov     [rsp+0E8h+BytesPerSector], r12d
0x180042d46  mov     [rsp+0E8h+NumberOfBytesRead], r12d
0x180042d4b  or      r13, 0FFFFFFFFFFFFFFFFh
0x180042d4f  mov     rbx, r13
0x180042d52  mov     [rsp+0E8h+var_98], rbx
0x180042d57  call    cs:__imp_GetLogicalDrives
0x180042d5e  nop     dword ptr [rax+rax+00h]
0x180042d63  mov     esi, eax
0x180042d65  mov     [rsp+0E8h+NumberOfFreeClusters], r12d
0x180042d6a  mov     [rsp+0E8h+OldMode], r12d
0x180042d6f  mov     edi, r12d
0x180042d72  mov     [rsp+0E8h+var_90], r12
0x180042d77  mov     [rsp+0E8h+SectorsPerCluster], r12d
0x180042d7c  lea     rdx, [rsp+0E8h+OldMode]; OldMode
0x180042d81  lea     ecx, [r12+10h]; NewMode
0x180042d86  call    cs:__imp_RtlSetThreadErrorMode
0x180042d8d  nop     dword ptr [rax+rax+00h]
0x180042d92  test    esi, esi
0x180042d94  jz      loc_180042E8D
0x180042d9a  mov     r14d, r12d
0x180042d9d  mov     [rsp+0E8h+var_80], r12d
0x180042da2  mov     eax, r12d
0x180042da5  cmp     eax, 1Ah
0x180042da8  jnb     loc_180042E8D
0x180042dae  test    esi, esi
0x180042db0  jz      loc_180042E8D
0x180042db6  test    sil, 1
0x180042dba  jnz     short loc_180042DCF
0x180042dbc  inc     r14d
0x180042dbf  mov     eax, r14d
0x180042dc2  mov     [rsp+0E8h+var_80], r14d
0x180042dc7  shr     esi, 1
0x180042dc9  mov     [rsp+0E8h+var_7C], esi
0x180042dcd  jmp     short loc_180042DA5
0x180042dcf  lea     r15d, [r14+41h]
0x180042dd3  mov     [rsp+0E8h+RootPathName], r15w
0x180042ddc  lea     rcx, [rsp+0E8h+RootPathName]; lpRootPathName
0x180042de4  call    cs:__imp_GetDriveTypeW
0x180042deb  nop     dword ptr [rax+rax+00h]
0x180042df0  cmp     eax, 5
0x180042df3  jnz     short loc_180042DBC
0x180042df5  mov     [rsp+0E8h+var_48], r15w
0x180042dfe  mov     [rsp+0E8h+hTemplateFile], r12; hTemplateFile
0x180042e03  mov     [rsp+0E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180042e0b  mov     [rsp+0E8h+dwCreationDisposition], 3; dwCreationDisposition
0x180042e13  xor     r9d, r9d; lpSecurityAttributes
0x180042e16  mov     edx, 80000000h; dwDesiredAccess
0x180042e1b  lea     r8d, [rax-4]; dwShareMode
0x180042e1f  lea     rcx, [rsp+0E8h+FileName]; lpFileName
0x180042e27  call    cs:__imp_CreateFileW
0x180042e2e  nop     dword ptr [rax+rax+00h]
0x180042e33  mov     rbx, rax
0x180042e36  mov     [rsp+0E8h+var_98], rax
0x180042e3b  cmp     rax, r13
0x180042e3e  jz      short loc_180042E88
0x180042e40  lea     rax, [rsp+0E8h+TotalNumberOfClusters]
0x180042e45  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rax; lpTotalNumberOfClusters
0x180042e4a  lea     r9, [rsp+0E8h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180042e4f  lea     r8, [rsp+0E8h+BytesPerSector]; lpBytesPerSector
0x180042e54  lea     rdx, [rsp+0E8h+SectorsPerCluster]; lpSectorsPerCluster
0x180042e59  lea     rcx, [rsp+0E8h+RootPathName]; lpRootPathName
0x180042e61  call    cs:__imp_GetDiskFreeSpaceW
0x180042e68  nop     dword ptr [rax+rax+00h]
0x180042e6d  test    eax, eax
0x180042e6f  jnz     short loc_180042E95
0x180042e71  mov     rcx, rbx; hObject
0x180042e74  call    cs:__imp_CloseHandle
0x180042e7b  nop     dword ptr [rax+rax+00h]
0x180042e80  mov     rbx, r13
0x180042e83  mov     [rsp+0E8h+var_98], rbx
0x180042e88  jmp     loc_180042DBC
0x180042e8d  mov     esi, r12d
0x180042e90  jmp     loc_180042F49
0x180042e95  mov     r15d, [rsp+0E8h+BytesPerSector]
0x180042e9a  mov     ecx, r15d; Size
0x180042e9d  call    malloc_0
0x180042ea2  mov     rdi, rax
0x180042ea5  mov     [rsp+0E8h+var_90], rax
0x180042eaa  test    rax, rax
0x180042ead  jnz     short loc_180042EB9
0x180042eaf  mov     esi, 8007000Eh
0x180042eb4  jmp     loc_180042F49
0x180042eb9  imul    eax, r15d, 11h
0x180042ebd  mov     dword ptr [rsp+0E8h+Overlapped.10h], eax
0x180042ec4  mov     dword ptr [rsp+0E8h+Overlapped.10h+4], r12d
0x180042ecc  mov     [rsp+0E8h+Overlapped.hEvent], r12
0x180042ed4  lea     rax, [rsp+0E8h+Overlapped]
0x180042ed9  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rax; lpOverlapped
0x180042ede  lea     r9, [rsp+0E8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042ee3  mov     r8d, r15d; nNumberOfBytesToRead
0x180042ee6  mov     rdx, rdi; lpBuffer
0x180042ee9  mov     rcx, rbx; hFile
0x180042eec  call    cs:__imp_ReadFile
0x180042ef3  nop     dword ptr [rax+rax+00h]
0x180042ef8  test    eax, eax
0x180042efa  jz      short loc_180042F1D
0x180042efc  lea     rcx, [rdi+7]; Buf1
0x180042f00  mov     r8d, 17h; Size
0x180042f06  lea     rdx, aElToritoSpecif; "EL TORITO SPECIFICATION"
0x180042f0d  call    memcmp_0
0x180042f12  test    eax, eax
0x180042f14  jnz     short loc_180042F1D
0x180042f16  mov     esi, 80310030h
0x180042f1b  jmp     short loc_180042F49
0x180042f1d  mov     rcx, rdi; Block
0x180042f20  call    free_0
0x180042f25  mov     rdi, r12
0x180042f28  mov     [rsp+0E8h+var_90], r12
0x180042f2d  mov     rcx, rbx; hObject
0x180042f30  call    cs:__imp_CloseHandle
0x180042f37  nop     dword ptr [rax+rax+00h]
0x180042f3c  mov     rbx, r13
0x180042f3f  mov     [rsp+0E8h+var_98], rbx
0x180042f44  jmp     loc_180042DBC
0x180042f49  cmp     rbx, r13
0x180042f4c  jnz     short loc_180042F8B
0x180042f4e  test    rdi, rdi
0x180042f51  jnz     short loc_180042F9C
0x180042f53  xor     edx, edx; OldMode
0x180042f55  mov     ecx, [rsp+0E8h+OldMode]; NewMode
0x180042f59  call    cs:__imp_RtlSetThreadErrorMode
0x180042f60  nop     dword ptr [rax+rax+00h]
0x180042f65  mov     eax, esi
0x180042f67  mov     rcx, [rsp+0E8h+var_40]
0x180042f6f  xor     rcx, rsp; StackCookie
0x180042f72  call    __security_check_cookie
0x180042f77  add     rsp, 0B0h
0x180042f7e  pop     r15
0x180042f80  pop     r14
0x180042f82  pop     r13
0x180042f84  pop     r12
0x180042f86  pop     rdi
0x180042f87  pop     rsi
0x180042f88  pop     rbx
0x180042f89  retn
0x180042f8b  mov     rcx, rbx; hObject
0x180042f8e  call    cs:__imp_CloseHandle
0x180042f95  nop     dword ptr [rax+rax+00h]
0x180042f9a  jmp     short loc_180042F4E
0x180042f9c  mov     rcx, rdi; Block
0x180042f9f  call    free_0
0x180042fa4  jmp     short loc_180042F53
0x180120882  push    rbp
0x180120884  sub     rsp, 40h
0x180120888  mov     rbp, rdx
0x18012088b  mov     rcx, [rbp+50h]; hObject
0x18012088f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180120893  jz      short loc_1801208A9
0x180120895  call    cs:__imp_CloseHandle
0x18012089c  nop     dword ptr [rax+rax+00h]
0x1801208a1  mov     qword ptr [rbp+50h], 0FFFFFFFFFFFFFFFFh
0x1801208a9  mov     rcx, [rbp+58h]; Block
0x1801208ad  test    rcx, rcx
0x1801208b0  jz      short loc_1801208BF
0x1801208b2  call    free_0
0x1801208b7  mov     qword ptr [rbp+58h], 0
0x1801208bf  xor     edx, edx; OldMode
0x1801208c1  mov     ecx, [rbp+40h]; NewMode
0x1801208c4  call    cs:__imp_RtlSetThreadErrorMode
0x1801208cb  nop     dword ptr [rax+rax+00h]
0x1801208d0  nop
0x1801208d1  add     rsp, 40h
0x1801208d5  pop     rbp
0x1801208d6  retn
```
