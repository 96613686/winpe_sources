# IsVolumeVirtual(ushort const *,bool *)

- ea: `0x1800d9870`
- end: `0x1800d9a57`
- name: `?IsVolumeVirtual@@YAJPEBGPEA_N@Z`
- size: `487`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800b1450`
- `0x1800c5324`
- `0x1800f19c0`
- `0x1800f1b80`
- `0x1800f42a0`

## callees

- `0x1800050c0`
- `0x1800090c0`
- `0x180023800`
- `0x18005e368`
- `0x1800d9870`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9a26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d99b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d99b5`
- `VirtDisk!GetStorageDependencyInformation` at `0x1800d99df`
- `VirtDisk!GetStorageDependencyInformation` at `0x1800d99df`

## pseudocode

```c
__int64 __fastcall IsVolumeVirtual(const unsigned __int16 *a1, bool *a2)
{
  signed int v5; // ebx
  unsigned int v6; // r10d
  unsigned __int64 v7; // rcx
  HANDLE FileW; // rsi
  signed int StorageDependencyInformation; // eax
  ULONG SizeUsed; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  _STORAGE_DEPENDENCY_INFO StorageDependencyInfo; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(FileName, 0, 0x20Cu);
  v11 = 0;
  StorageDependencyInfo.Version = STORAGE_DEPENDENCY_INFO_VERSION_2;
  memset_0(&StorageDependencyInfo.NumberEntries, 0, 0x44u);
  SizeUsed = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = StringCchCopyW(FileName, 0x106u, a1);
  if ( v5 >= 0 )
  {
    v5 = StringCchLengthW(FileName, v6, &v11);
    if ( v5 >= 0 )
    {
      if ( v11 <= 1 )
      {
        v5 = -2147024809;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
            2147942487LL);
        return (unsigned int)v5;
      }
      if ( FileName[v11 - 1] == 92 )
      {
        v7 = 2 * v11 - 2;
        if ( v7 >= 0x20C )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)FileName + v7) = 0;
      }
      FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
      StorageDependencyInformation = GetStorageDependencyInformation(
                                       FileW,
                                       GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                       0x48u,
                                       &StorageDependencyInfo,
                                       &SizeUsed);
      v5 = StorageDependencyInformation;
      if ( (unsigned int)StorageDependencyInformation <= 1 || StorageDependencyInformation == -1069940715 )
      {
        *a2 = 0;
      }
      else
      {
        if ( StorageDependencyInformation != 122 )
        {
          if ( StorageDependencyInformation > 0 )
            v5 = (unsigned __int16)StorageDependencyInformation | 0x80070000;
          goto LABEL_21;
        }
        *a2 = 1;
      }
      v5 = 0;
LABEL_21:
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d9870  mov     [rsp-8+arg_10], rbx
0x1800d9875  push    rbp
0x1800d9876  push    rsi
0x1800d9877  push    rdi
0x1800d9878  lea     rbp, [rsp-1C0h]
0x1800d9880  sub     rsp, 2C0h
0x1800d9887  mov     rax, cs:__security_cookie
0x1800d988e  xor     rax, rsp
0x1800d9891  mov     [rbp+1D0h+var_20], rax
0x1800d9898  mov     rdi, rdx
0x1800d989b  mov     rbx, rcx
0x1800d989e  mov     esi, 20Ch
0x1800d98a3  lea     rcx, [rbp+1D0h+FileName]; void *
0x1800d98a7  mov     r8d, esi; Size
0x1800d98aa  xor     edx, edx; Val
0x1800d98ac  call    memset_0
0x1800d98b1  xor     edx, edx; Val
0x1800d98b3  mov     [rsp+2D0h+var_288], 0
0x1800d98bc  lea     rcx, [rsp+2D0h+StorageDependencyInfo.NumberEntries]; void *
0x1800d98c1  mov     [rsp+2D0h+StorageDependencyInfo.Version], 2
0x1800d98c9  lea     r8d, [rdx+44h]; Size
0x1800d98cd  call    memset_0
0x1800d98d2  mov     [rsp+2D0h+SizeUsed], 0
0x1800d98da  test    rdi, rdi
0x1800d98dd  jnz     short loc_1800D98E9
0x1800d98df  mov     eax, 80004003h
0x1800d98e4  jmp     loc_1800D9A34
0x1800d98e9  mov     r10d, 106h
0x1800d98ef  mov     byte ptr [rdi], 0
0x1800d98f2  mov     edx, r10d; unsigned __int64
0x1800d98f5  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x1800d98f9  mov     r8, rbx; unsigned __int16 *
0x1800d98fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d9901  mov     ebx, eax
0x1800d9903  test    eax, eax
0x1800d9905  js      loc_1800D9A32
0x1800d990b  lea     r8, [rsp+2D0h+var_288]; unsigned __int64 *
0x1800d9910  mov     edx, r10d; unsigned __int64
0x1800d9913  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x1800d9917  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d991c  mov     ebx, eax
0x1800d991e  test    eax, eax
0x1800d9920  js      loc_1800D9A32
0x1800d9926  mov     rax, [rsp+2D0h+var_288]
0x1800d992b  cmp     rax, 1
0x1800d992f  ja      short loc_1800D9974
0x1800d9931  mov     ebx, 80070057h
0x1800d9936  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d993d  lea     rax, WPP_GLOBAL_Control
0x1800d9944  cmp     rcx, rax
0x1800d9947  jz      loc_1800D9A32
0x1800d994d  test    byte ptr [rcx+1Ch], 40h
0x1800d9951  jz      loc_1800D9A32
0x1800d9957  mov     rcx, [rcx+10h]
0x1800d995b  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d9962  mov     edx, 45h ; 'E'
0x1800d9967  mov     r9d, ebx
0x1800d996a  call    WPP_SF_d
0x1800d996f  jmp     loc_1800D9A32
0x1800d9974  cmp     [rbp+rax*2+1D0h+var_232], 5Ch ; '\'
0x1800d997a  jnz     short loc_1800D9990
0x1800d997c  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1800d9984  cmp     rcx, rsi
0x1800d9987  jnb     short loc_1800D9A03
0x1800d9989  xor     eax, eax
0x1800d998b  mov     [rbp+rcx+1D0h+FileName], ax
0x1800d9990  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x1800d9999  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x1800d999d  mov     r8d, 3; dwShareMode
0x1800d99a3  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d99ab  xor     r9d, r9d; lpSecurityAttributes
0x1800d99ae  mov     [rsp+2D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800d99b3  xor     edx, edx; dwDesiredAccess
0x1800d99b5  call    cs:__imp_CreateFileW
0x1800d99bc  nop     dword ptr [rax+rax+00h]
0x1800d99c1  mov     edx, 1; Flags
0x1800d99c6  lea     r9, [rsp+2D0h+StorageDependencyInfo]; StorageDependencyInfo
0x1800d99cb  mov     rsi, rax
0x1800d99ce  lea     rax, [rsp+2D0h+SizeUsed]
0x1800d99d3  mov     rcx, rsi; ObjectHandle
0x1800d99d6  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax; SizeUsed
0x1800d99db  lea     r8d, [rdx+47h]; StorageDependencyInfoSize
0x1800d99df  call    cs:__imp_GetStorageDependencyInformation
0x1800d99e6  nop     dword ptr [rax+rax+00h]
0x1800d99eb  mov     ebx, eax
0x1800d99ed  cmp     eax, 1
0x1800d99f0  jbe     short loc_1800D9A18
0x1800d99f2  cmp     eax, 0C03A0015h
0x1800d99f7  jz      short loc_1800D9A18
0x1800d99f9  cmp     eax, 7Ah ; 'z'
0x1800d99fc  jnz     short loc_1800D9A09
0x1800d99fe  mov     byte ptr [rdi], 1
0x1800d9a01  jmp     short loc_1800D9A1B
0x1800d9a03  call    __report_rangecheckfailure
0x1800d9a09  test    eax, eax
0x1800d9a0b  jle     short loc_1800D9A1D
0x1800d9a0d  movzx   ebx, ax
0x1800d9a10  or      ebx, 80070000h
0x1800d9a16  jmp     short loc_1800D9A1D
0x1800d9a18  mov     byte ptr [rdi], 0
0x1800d9a1b  xor     ebx, ebx
0x1800d9a1d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800d9a21  jz      short loc_1800D9A32
0x1800d9a23  mov     rcx, rsi; hObject
0x1800d9a26  call    cs:__imp_CloseHandle
0x1800d9a2d  nop     dword ptr [rax+rax+00h]
0x1800d9a32  mov     eax, ebx
0x1800d9a34  mov     rcx, [rbp+1D0h+var_20]
0x1800d9a3b  xor     rcx, rsp; StackCookie
0x1800d9a3e  call    __security_check_cookie
0x1800d9a43  mov     rbx, [rsp+2D0h+arg_10]
0x1800d9a4b  add     rsp, 2C0h
0x1800d9a52  pop     rdi
0x1800d9a53  pop     rsi
0x1800d9a54  pop     rbp
0x1800d9a55  retn
```
