# CFveApiBase::CheckVolumeNameMountPoint(ushort const *,ushort * *)

- ea: `0x18007b318`
- end: `0x18007b5ae`
- name: `?CheckVolumeNameMountPoint@CFveApiBase@@SAJPEBGPEAPEAG@Z`
- size: `662`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180009790`
- `0x180009b20`

## callees

- `0x1800050c0`
- `0x18000ba30`
- `0x18000ca50`
- `0x180023800`
- `0x18007b318`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18007b38c`
- `ntdll!RtlSetThreadErrorMode` at `0x18007b572`
- `ntdll!RtlSetThreadErrorMode` at `0x180123b8c`
- `ntdll!RtlSetThreadErrorMode` at `0x18007b38c`
- `ntdll!RtlSetThreadErrorMode` at `0x18007b572`
- `ntdll!RtlSetThreadErrorMode` at `0x180123b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b50e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007b457`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007b457`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007b560`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180123b73`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007b560`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180123b73`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007b49c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007b49c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18007b4fe`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18007b4fe`

## pseudocode

```c
__int64 __fastcall CFveApiBase::CheckVolumeNameMountPoint(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 FirstFileW; // r15
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // rsi
  signed int v7; // ebx
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int64 v10; // r14
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  unsigned __int64 v14; // [rsp+28h] [rbp-2B0h] BYREF
  unsigned __int16 *v15; // [rsp+30h] [rbp-2A8h]
  unsigned __int16 *v16; // [rsp+38h] [rbp-2A0h]
  __int64 v17; // [rsp+40h] [rbp-298h]
  ULONG OldMode; // [rsp+48h] [rbp-290h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-288h] BYREF

  OldMode = 0;
  FirstFileW = -1;
  v17 = -1;
  v14 = 0;
  v5 = 0;
  v16 = 0;
  v6 = 0;
  v15 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  RtlSetThreadErrorMode(0x10u, &OldMode);
  v7 = StringCchLengthW(a1, 0x104u, &v14);
  if ( v7 >= 0 )
  {
    if ( v14 < 2 )
    {
      v7 = -2147024809;
      goto LABEL_23;
    }
    v8 = v14 + 2;
    v9 = (unsigned __int16 *)CFveApiBase::FastAlloc(2 * (v14 + 2));
    v5 = v9;
    v16 = v9;
    if ( !v9 )
    {
LABEL_6:
      v7 = -2147024882;
      goto LABEL_23;
    }
    v7 = StringCchCopyW(v9, v8, a1);
    if ( v7 >= 0 )
    {
      v7 = StringCchLengthW(v5, 0x104u, &v14);
      if ( v7 >= 0 )
      {
        v10 = v14;
        if ( v5[v14 - 1] == 92 )
        {
          v5[v14 - 1] = 0;
          v14 = --v10;
        }
        FileAttributesW = GetFileAttributesW(v5);
        if ( FileAttributesW == -1 )
          goto LABEL_12;
        if ( (FileAttributesW & 0x400) == 0 )
          goto LABEL_13;
        FirstFileW = (__int64)FindFirstFileW(v5, &FindFileData);
        v17 = FirstFileW;
        if ( FirstFileW == -1 )
        {
LABEL_12:
          GetLastError();
LABEL_13:
          v7 = 1;
          goto LABEL_23;
        }
        if ( FindFileData.dwReserved0 != -1610612733 )
          goto LABEL_13;
        if ( !a2 )
          goto LABEL_23;
        v6 = (unsigned __int16 *)CFveApiBase::FastAlloc(0x64u);
        v15 = v6;
        if ( !v6 )
          goto LABEL_6;
        v5[v10] = 92;
        v14 = v10 + 1;
        v5[v14] = 0;
        if ( GetVolumeNameForVolumeMountPointW(v5, v6, 0x32u) )
        {
          *a2 = v6;
          v6 = 0;
          v15 = 0;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
LABEL_23:
  if ( v5 )
    CFveApiBase::FastFree(v5);
  if ( v6 )
    CFveApiBase::FastFree(v6);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  RtlSetThreadErrorMode(OldMode, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007b318  mov     [rsp+arg_10], rbx
0x18007b31d  mov     [rsp+arg_18], rsi
0x18007b322  push    rdi
0x18007b323  push    r12
0x18007b325  push    r13
0x18007b327  push    r14
0x18007b329  push    r15
0x18007b32b  sub     rsp, 2B0h
0x18007b332  mov     rax, cs:__security_cookie
0x18007b339  xor     rax, rsp
0x18007b33c  mov     [rsp+2D8h+var_38], rax
0x18007b344  mov     r12, rdx
0x18007b347  mov     r14, rcx
0x18007b34a  mov     [rsp+2D8h+OldMode], 0
0x18007b352  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007b356  mov     [rsp+2D8h+var_298], r15
0x18007b35b  mov     [rsp+2D8h+var_2B0], 0
0x18007b364  xor     edi, edi
0x18007b366  mov     [rsp+2D8h+var_2A0], rdi
0x18007b36b  xor     esi, esi
0x18007b36d  mov     [rsp+2D8h+var_2A8], rsi
0x18007b372  xor     edx, edx; Val
0x18007b374  mov     r8d, 250h; Size
0x18007b37a  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18007b37f  call    memset_0
0x18007b384  lea     rdx, [rsp+2D8h+OldMode]; OldMode
0x18007b389  lea     ecx, [rdi+10h]; NewMode
0x18007b38c  call    cs:__imp_RtlSetThreadErrorMode
0x18007b393  nop     dword ptr [rax+rax+00h]
0x18007b398  nop
0x18007b399  lea     r8, [rsp+2D8h+var_2B0]; unsigned __int64 *
0x18007b39e  mov     r13d, 104h
0x18007b3a4  mov     edx, r13d; unsigned __int64
0x18007b3a7  mov     rcx, r14; unsigned __int16 *
0x18007b3aa  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007b3af  mov     ebx, eax
0x18007b3b1  mov     [rsp+2D8h+var_2B8], eax
0x18007b3b5  test    eax, eax
0x18007b3b7  js      loc_18007B53D
0x18007b3bd  mov     rax, [rsp+2D8h+var_2B0]
0x18007b3c2  cmp     rax, 2
0x18007b3c6  jnb     short loc_18007B3D6
0x18007b3c8  mov     ebx, 80070057h
0x18007b3cd  mov     [rsp+2D8h+var_2B8], ebx
0x18007b3d1  jmp     loc_18007B53D
0x18007b3d6  lea     rbx, [rax+2]
0x18007b3da  lea     rcx, [rbx+rbx]; unsigned __int64
0x18007b3de  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18007b3e3  mov     rdi, rax
0x18007b3e6  mov     [rsp+2D8h+var_2A0], rax
0x18007b3eb  test    rax, rax
0x18007b3ee  jnz     short loc_18007B3F7
0x18007b3f0  mov     ebx, 8007000Eh
0x18007b3f5  jmp     short loc_18007B3CD
0x18007b3f7  mov     r8, r14; unsigned __int16 *
0x18007b3fa  mov     rdx, rbx; unsigned __int64
0x18007b3fd  mov     rcx, rdi; unsigned __int16 *
0x18007b400  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b405  mov     ebx, eax
0x18007b407  mov     [rsp+2D8h+var_2B8], eax
0x18007b40b  test    eax, eax
0x18007b40d  js      loc_18007B53D
0x18007b413  lea     r8, [rsp+2D8h+var_2B0]; unsigned __int64 *
0x18007b418  mov     rdx, r13; unsigned __int64
0x18007b41b  mov     rcx, rdi; unsigned __int16 *
0x18007b41e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007b423  mov     ebx, eax
0x18007b425  mov     [rsp+2D8h+var_2B8], eax
0x18007b429  test    eax, eax
0x18007b42b  js      loc_18007B53D
0x18007b431  mov     r14, [rsp+2D8h+var_2B0]
0x18007b436  mov     r13d, 5Ch ; '\'
0x18007b43c  cmp     [rdi+r14*2-2], r13w
0x18007b442  jnz     short loc_18007B454
0x18007b444  xor     eax, eax
0x18007b446  mov     [rdi+r14*2-2], ax
0x18007b44c  dec     r14
0x18007b44f  mov     [rsp+2D8h+var_2B0], r14
0x18007b454  mov     rcx, rdi; lpFileName
0x18007b457  call    cs:__imp_GetFileAttributesW
0x18007b45e  nop     dword ptr [rax+rax+00h]
0x18007b463  cmp     eax, 0FFFFFFFFh
0x18007b466  jnz     short loc_18007B48E
0x18007b468  call    cs:__imp_GetLastError
0x18007b46f  nop     dword ptr [rax+rax+00h]
0x18007b474  test    eax, eax
0x18007b476  jle     short loc_18007B480
0x18007b478  movzx   eax, ax
0x18007b47b  or      eax, 80070000h
0x18007b480  mov     [rsp+2D8h+var_2B8], eax
0x18007b484  mov     ebx, 1
0x18007b489  jmp     loc_18007B3CD
0x18007b48e  bt      eax, 0Ah
0x18007b492  jnb     short loc_18007B484
0x18007b494  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18007b499  mov     rcx, rdi; lpFileName
0x18007b49c  call    cs:__imp_FindFirstFileW
0x18007b4a3  nop     dword ptr [rax+rax+00h]
0x18007b4a8  mov     r15, rax
0x18007b4ab  mov     [rsp+2D8h+var_298], rax
0x18007b4b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b4b4  jz      short loc_18007B468
0x18007b4b6  cmp     [rsp+2D8h+FindFileData.dwReserved0], 0A0000003h
0x18007b4be  jnz     short loc_18007B484
0x18007b4c0  test    r12, r12
0x18007b4c3  jz      short loc_18007B53D
0x18007b4c5  mov     ecx, 64h ; 'd'; unsigned __int64
0x18007b4ca  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18007b4cf  mov     rsi, rax
0x18007b4d2  mov     [rsp+2D8h+var_2A8], rax
0x18007b4d7  test    rax, rax
0x18007b4da  jz      loc_18007B3F0
0x18007b4e0  mov     [rdi+r14*2], r13w
0x18007b4e5  inc     r14
0x18007b4e8  mov     [rsp+2D8h+var_2B0], r14
0x18007b4ed  xor     eax, eax
0x18007b4ef  mov     [rdi+r14*2], ax
0x18007b4f4  lea     r8d, [rax+32h]; cchBufferLength
0x18007b4f8  mov     rdx, rsi; lpszVolumeName
0x18007b4fb  mov     rcx, rdi; lpszVolumeMountPoint
0x18007b4fe  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18007b505  nop     dword ptr [rax+rax+00h]
0x18007b50a  test    eax, eax
0x18007b50c  jnz     short loc_18007B532
0x18007b50e  call    cs:__imp_GetLastError
0x18007b515  nop     dword ptr [rax+rax+00h]
0x18007b51a  mov     ebx, eax
0x18007b51c  test    eax, eax
0x18007b51e  jle     loc_18007B3CD
0x18007b524  movzx   ebx, ax
0x18007b527  or      ebx, 80070000h
0x18007b52d  jmp     loc_18007B3CD
0x18007b532  mov     [r12], rsi
0x18007b536  xor     esi, esi
0x18007b538  mov     [rsp+2D8h+var_2A8], rsi
0x18007b53d  test    rdi, rdi
0x18007b540  jz      short loc_18007B54A
0x18007b542  mov     rcx, rdi; lpMem
0x18007b545  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007b54a  test    rsi, rsi
0x18007b54d  jz      short loc_18007B557
0x18007b54f  mov     rcx, rsi; lpMem
0x18007b552  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007b557  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18007b55b  jz      short loc_18007B56C
0x18007b55d  mov     rcx, r15; hFindFile
0x18007b560  call    cs:__imp_FindClose
0x18007b567  nop     dword ptr [rax+rax+00h]
0x18007b56c  xor     edx, edx; OldMode
0x18007b56e  mov     ecx, [rsp+2D8h+OldMode]; NewMode
0x18007b572  call    cs:__imp_RtlSetThreadErrorMode
0x18007b579  nop     dword ptr [rax+rax+00h]
0x18007b57e  mov     eax, ebx
0x18007b580  mov     rcx, [rsp+2D8h+var_38]
0x18007b588  xor     rcx, rsp; StackCookie
0x18007b58b  call    __security_check_cookie
0x18007b590  lea     r11, [rsp+2D8h+var_28]
0x18007b598  mov     rbx, [r11+40h]
0x18007b59c  mov     rsi, [r11+48h]
0x18007b5a0  mov     rsp, r11
0x18007b5a3  pop     r15
0x18007b5a5  pop     r14
0x18007b5a7  pop     r13
0x18007b5a9  pop     r12
0x18007b5ab  pop     rdi
0x18007b5ac  retn
0x180123b34  push    rbp
0x180123b36  sub     rsp, 20h
0x180123b3a  mov     rbp, rdx
0x180123b3d  mov     rcx, [rbp+38h]; lpMem
0x180123b41  test    rcx, rcx
0x180123b44  jz      short loc_180123B53
0x180123b46  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180123b4b  mov     qword ptr [rbp+38h], 0
0x180123b53  mov     rcx, [rbp+30h]; lpMem
0x180123b57  test    rcx, rcx
0x180123b5a  jz      short loc_180123B69
0x180123b5c  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180123b61  mov     qword ptr [rbp+30h], 0
0x180123b69  mov     rcx, [rbp+40h]; hFindFile
0x180123b6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180123b71  jz      short loc_180123B87
0x180123b73  call    cs:__imp_FindClose
0x180123b7a  nop     dword ptr [rax+rax+00h]
0x180123b7f  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x180123b87  xor     edx, edx; OldMode
0x180123b89  mov     ecx, [rbp+48h]; NewMode
0x180123b8c  call    cs:__imp_RtlSetThreadErrorMode
0x180123b93  nop     dword ptr [rax+rax+00h]
0x180123b98  nop
0x180123b99  add     rsp, 20h
0x180123b9d  pop     rbp
0x180123b9e  retn
```
