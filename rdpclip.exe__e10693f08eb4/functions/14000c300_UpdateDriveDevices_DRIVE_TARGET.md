# UpdateDriveDevices(DRIVE_TARGET *)

- ea: `0x14000c300`
- end: `0x14000c5a5`
- name: `?UpdateDriveDevices@@YAXPEAUDRIVE_TARGET@@@Z`
- size: `677`
- prototype: `void __fastcall(struct DRIVE_TARGET *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000bfa4`
- `0x14000c5b0`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x14000a6c0`
- `0x14000c300`
- `0x14000c7cc`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c548`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14000c375`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14000c375`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14000c513`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14000c513`
- `ntdll!NtCreateFile` at `0x14000c40e`
- `ntdll!NtCreateFile` at `0x14000c40e`
- `ntdll!NtClose` at `0x14000c41e`
- `ntdll!NtClose` at `0x14000c41e`
- `ntdll!RtlInitUnicodeString` at `0x14000c3ac`
- `ntdll!RtlInitUnicodeString` at `0x14000c3ac`

## pseudocode

```c
void __fastcall UpdateDriveDevices(struct DRIVE_TARGET *a1)
{
  unsigned __int16 v1; // di
  __int64 v2; // rsi
  NTSTATUS v3; // ebx
  PVOID *v4; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // eax
  char v7; // bl
  unsigned int v8; // eax
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-11h] BYREF
  WCHAR DeviceName; // [rsp+B8h] [rbp-1h] BYREF
  int v14; // [rsp+BAh] [rbp+1h]

  v14 = 58;
  memset_0(&g_Targets, 0, 0x2F14u);
  v1 = 0;
  v2 = 0;
  do
  {
    DeviceName = v1 + 68;
    QueryDosDeviceW(&DeviceName, (LPWSTR)&dword_140088AA4[131 * v2], 0x104u);
    if ( *((_WORD *)&g_Targets + 262 * v2 + 2) )
    {
      FileHandle = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      DestinationString = 0;
      IoStatusBlock = 0;
      RtlInitUnicodeString(&DestinationString, (PCWSTR)&dword_140088AA4[131 * v2]);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v3 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
      if ( v3 < 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
            CurrentThreadActivityIdPrefix,
            v3);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 == -1073741772 || v3 == -1073741810 )
        {
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
          {
            RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&dword_140088AA4[131 * v2], (__int64)&DeviceName);
          }
          if ( DefineDosDeviceW(2u, &DeviceName, 0) )
          {
            *((_WORD *)&g_Targets + 262 * v2 + 2) = 0;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = LastError;
            v8 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
              v8,
              (__int64)&DeviceName,
              v7);
          }
        }
      }
      else
      {
        NtClose(FileHandle);
      }
    }
    ++v1;
    ++v2;
  }
  while ( v1 < 0x17u );
}

```

## disassembly

```asm
0x14000c300  push    rbp
0x14000c302  push    rbx
0x14000c303  push    rsi
0x14000c304  push    rdi
0x14000c305  push    r12
0x14000c307  push    r13
0x14000c309  push    r14
0x14000c30b  push    r15
0x14000c30d  lea     rbp, [rsp-1Fh]
0x14000c312  sub     rsp, 0D8h
0x14000c319  mov     rax, cs:__security_cookie
0x14000c320  xor     rax, rsp
0x14000c323  mov     [rbp+57h+var_50], rax
0x14000c327  lea     rbx, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000c32e  mov     [rbp+57h+var_56], 3Ah ; ':'
0x14000c335  mov     rcx, rbx; void *
0x14000c338  xor     edx, edx; Val
0x14000c33a  mov     r8d, 2F14h; Size
0x14000c340  call    memset_0
0x14000c345  xor     r12d, r12d
0x14000c348  mov     edi, r12d
0x14000c34b  mov     esi, r12d
0x14000c34e  lea     r13d, [r12+1]
0x14000c353  lea     eax, [rdi+44h]
0x14000c356  mov     r8d, 104h; ucchMax
0x14000c35c  imul    r14, rsi, 20Ch
0x14000c363  lea     r15, [rbx+4]
0x14000c367  mov     [rbp+57h+DeviceName], ax
0x14000c36b  add     r15, r14
0x14000c36e  lea     rcx, [rbp+57h+DeviceName]; lpDeviceName
0x14000c372  mov     rdx, r15; lpTargetPath
0x14000c375  call    cs:__imp_QueryDosDeviceW
0x14000c37b  cmp     [r14+rbx+4], r12w
0x14000c381  jz      loc_14000C42B
0x14000c387  xorps   xmm0, xmm0
0x14000c38a  mov     [rbp+57h+FileHandle], r12
0x14000c38e  xorps   xmm1, xmm1
0x14000c391  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000c395  mov     rdx, r15; SourceString
0x14000c398  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000c39c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000c3a0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c3a4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000c3a8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14000c3ac  call    cs:__imp_RtlInitUnicodeString
0x14000c3b2  mov     [rsp+110h+EaLength], r12d; EaLength
0x14000c3b7  lea     rax, [rbp+57h+DestinationString]
0x14000c3bb  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14000c3c0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000c3c4  mov     [rsp+110h+CreateOptions], 20h ; ' '; CreateOptions
0x14000c3cc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000c3d0  mov     [rsp+110h+CreateDisposition], r13d; CreateDisposition
0x14000c3d5  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000c3d9  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x14000c3e1  xorps   xmm0, xmm0
0x14000c3e4  mov     [rsp+110h+FileAttributes], r12d; FileAttributes
0x14000c3e9  mov     edx, 100080h; DesiredAccess
0x14000c3ee  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x14000c3f3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000c3fa  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14000c3fe  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14000c405  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000c409  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c40e  call    cs:__imp_NtCreateFile
0x14000c414  mov     ebx, eax
0x14000c416  test    eax, eax
0x14000c418  js      short loc_14000C45C
0x14000c41a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000c41e  call    cs:__imp_NtClose
0x14000c424  lea     rbx, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000c42b  add     di, r13w
0x14000c42f  add     rsi, r13
0x14000c432  cmp     di, 17h
0x14000c436  jb      loc_14000C353
0x14000c43c  mov     rcx, [rbp+57h+var_50]
0x14000c440  xor     rcx, rsp; StackCookie
0x14000c443  call    __security_check_cookie
0x14000c448  add     rsp, 0D8h
0x14000c44f  pop     r15
0x14000c451  pop     r14
0x14000c453  pop     r13
0x14000c455  pop     r12
0x14000c457  pop     rdi
0x14000c458  pop     rsi
0x14000c459  pop     rbx
0x14000c45a  pop     rbp
0x14000c45b  retn
0x14000c45c  mov     rax, cs:WPP_GLOBAL_Control
0x14000c463  lea     rcx, WPP_GLOBAL_Control
0x14000c46a  cmp     rax, rcx
0x14000c46d  jz      short loc_14000C4B1
0x14000c46f  test    [rax+1Ch], r13b
0x14000c473  jz      short loc_14000C4B1
0x14000c475  cmp     byte ptr [rax+19h], 2
0x14000c479  jb      short loc_14000C4B1
0x14000c47b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c480  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c487  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000c48e  mov     edx, 0Ah
0x14000c493  mov     dword ptr [rsp+110h+AllocationSize], ebx
0x14000c497  mov     r9d, eax
0x14000c49a  mov     rcx, [rcx+10h]
0x14000c49e  call    WPP_SF_Dd
0x14000c4a3  mov     rax, cs:WPP_GLOBAL_Control
0x14000c4aa  lea     rcx, WPP_GLOBAL_Control
0x14000c4b1  cmp     ebx, 0C0000034h
0x14000c4b7  jz      short loc_14000C4C5
0x14000c4b9  cmp     ebx, 0C000000Eh
0x14000c4bf  jnz     loc_14000C424
0x14000c4c5  cmp     rax, rcx
0x14000c4c8  jz      short loc_14000C508
0x14000c4ca  test    [rax+1Ch], r13b
0x14000c4ce  jz      short loc_14000C508
0x14000c4d0  cmp     byte ptr [rax+19h], 4
0x14000c4d4  jb      short loc_14000C508
0x14000c4d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c4db  lea     rcx, [rbp+57h+DeviceName]
0x14000c4df  mov     edx, 0Bh
0x14000c4e4  mov     qword ptr [rsp+110h+FileAttributes], rcx; __int64
0x14000c4e9  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000c4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4f7  mov     r9d, eax
0x14000c4fa  mov     [rsp+110h+AllocationSize], r15; __int64
0x14000c4ff  mov     rcx, [rcx+10h]; LoggerHandle
0x14000c503  call    WPP_SF_DSS
0x14000c508  xor     r8d, r8d; lpTargetPath
0x14000c50b  lea     rdx, [rbp+57h+DeviceName]; lpDeviceName
0x14000c50f  lea     ecx, [r8+2]; dwFlags
0x14000c513  call    cs:__imp_DefineDosDeviceW
0x14000c519  test    eax, eax
0x14000c51b  jnz     short loc_14000C593
0x14000c51d  mov     rax, cs:WPP_GLOBAL_Control
0x14000c524  lea     rcx, WPP_GLOBAL_Control
0x14000c52b  cmp     rax, rcx
0x14000c52e  jz      loc_14000C424
0x14000c534  test    [rax+1Ch], r13b
0x14000c538  jz      loc_14000C424
0x14000c53e  cmp     byte ptr [rax+19h], 2
0x14000c542  jb      loc_14000C424
0x14000c548  call    cs:__imp_GetLastError
0x14000c54e  mov     ebx, eax
0x14000c550  test    eax, eax
0x14000c552  jle     short loc_14000C55D
0x14000c554  movzx   ebx, ax
0x14000c557  or      ebx, 80070000h
0x14000c55d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c562  lea     rcx, [rbp+57h+DeviceName]
0x14000c566  mov     [rsp+110h+FileAttributes], ebx
0x14000c56a  mov     [rsp+110h+AllocationSize], rcx
0x14000c56f  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000c576  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c57d  mov     edx, 0Ch
0x14000c582  mov     r9d, eax
0x14000c585  mov     rcx, [rcx+10h]
0x14000c589  call    WPP_SF_DSD
0x14000c58e  jmp     loc_14000C424
0x14000c593  lea     rbx, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000c59a  mov     [r14+rbx+4], r12w
0x14000c5a0  jmp     loc_14000C42B
```
