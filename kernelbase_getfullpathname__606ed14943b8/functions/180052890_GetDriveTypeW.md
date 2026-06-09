# GetDriveTypeW

- ea: `0x180052890`
- end: `0x180052e37`
- name: `GetDriveTypeW`
- size: `1447`
- prototype: `UINT __stdcall(LPCWSTR lpRootPathName)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180050c30`
- `0x180050cc0`
- `0x180050eb0`
- `0x1800fc530`

## callees

- `0x180052890`
- `0x180052e40`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180052c91`
- `ntdll!RtlInitUnicodeString` at `0x180052c91`
- `ntdll!NtOpenFile` at `0x180052a7c`
- `ntdll!NtOpenFile` at `0x180052bde`
- `ntdll!NtOpenFile` at `0x180052a7c`
- `ntdll!NtOpenFile` at `0x180052bde`
- `ntdll!wcslen` at `0x180052913`
- `ntdll!wcslen` at `0x180052913`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18005292c`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180052ce2`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18005292c`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180052ce2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800529ee`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800529ee`
- `ntdll!NtQueryVolumeInformationFile` at `0x180052c37`
- `ntdll!NtQueryVolumeInformationFile` at `0x180052c37`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180052ae4`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180052ae4`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180052b27`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180052b27`
- `ntdll!wcsncpy_s` at `0x180052d19`
- `ntdll!wcsncpy_s` at `0x180052d19`
- `ntdll!NtClose` at `0x180052b3a`
- `ntdll!NtClose` at `0x180052b65`
- `ntdll!NtClose` at `0x180052c6d`
- `ntdll!NtClose` at `0x180052b3a`
- `ntdll!NtClose` at `0x180052b65`
- `ntdll!NtClose` at `0x180052c6d`
- `ntdll!NtQueryInformationProcess` at `0x18005297c`
- `ntdll!NtQueryInformationProcess` at `0x18005297c`
- `ntdll!RtlFreeHeap` at `0x180052b85`
- `ntdll!RtlFreeHeap` at `0x180052bfe`
- `ntdll!RtlFreeHeap` at `0x180052b85`
- `ntdll!RtlFreeHeap` at `0x180052bfe`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180052dae`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180052dae`

## pseudocode

```c
UINT __stdcall GetDriveTypeW(LPCWSTR lpRootPathName)
{
  WCHAR *v2; // rdi
  WCHAR v3; // ax
  int v4; // esi
  int v5; // eax
  __int64 v6; // rcx
  int v7; // ecx
  const WCHAR *v9; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v11; // esi
  NTSTATUS v12; // eax
  USHORT Length; // cx
  NTSTATUS v14; // ebx
  UINT v15; // ebx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  HANDLE FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-C8h] BYREF
  ULONG DataWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 FsInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int128 ProcessInformation; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES v31; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v32; // [rsp+118h] [rbp+18h]
  wchar_t Destination[2]; // [rsp+130h] [rbp+30h] BYREF
  int v34; // [rsp+134h] [rbp+34h]
  WCHAR SourceString[264]; // [rsp+340h] [rbp+240h] BYREF
  char v36; // [rsp+550h] [rbp+450h] BYREF

  FileHandle = 0;
  FsInformation = 0;
  v30 = 0;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  ProcessInformation = 0;
  v29 = 0;
  if ( lpRootPathName )
  {
    if ( lpRootPathName == (LPCWSTR)-1LL )
      return 0;
    v2 = (WCHAR *)lpRootPathName;
    if ( wcslen(lpRootPathName) == 2
      && (unsigned __int16)(RtlUpcaseUnicodeChar(*lpRootPathName) - 65) <= 0x19u
      && lpRootPathName[1] == 58 )
    {
      wcsncpy_s(Destination, 0x104u, lpRootPathName, 2u);
      v2 = Destination;
      v34 = 92;
    }
  }
  else
  {
    v2 = Destination;
    if ( RtlGetCurrentDirectory_U(0x208u, Destination) > 6 )
      HIWORD(v34) = 0;
  }
  v3 = RtlUpcaseUnicodeChar(*v2);
  v4 = v3;
  if ( (unsigned __int16)(v3 - 65) > 0x19u || v2[1] != 58 || v2[2] != 92 || v2[3] )
    goto LABEL_13;
  if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDeviceMap, &ProcessInformation, 0x24u, 0) < 0 )
  {
    ProcessInformation = 0;
    v30 = 0;
    v29 = 0;
  }
  v5 = ProcessInformation;
  v6 = (unsigned int)(v4 - 65);
  if ( !_bittest(&v5, v6) )
    goto LABEL_13;
  v7 = *((unsigned __int8 *)&ProcessInformation + v6 + 4);
  if ( v7 == 3 )
    return 3;
  if ( !v7 )
    return 0;
  v16 = v7 - 2;
  if ( !v16 )
    return 2;
  v17 = v16 - 2;
  if ( !v17 )
    return 4;
  v18 = v17 - 1;
  if ( !v18 )
    return 5;
  if ( v18 == 1 )
    return 6;
LABEL_13:
  v9 = L"\\";
  if ( lpRootPathName )
    v9 = v2;
  if ( !RtlDosPathNameToNtPathName_U(v9, &NtPathName, 0, 0) )
    return 1;
  Buffer = NtPathName.Buffer;
  if ( NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 1] != 92 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    return 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  NtPathName.Length -= 2;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
  if ( v11 == -1073741638 )
  {
    if ( (unsigned int)BasepGetVolumeNameFromReparsePoint(lpRootPathName, SourceString, 0x104u) )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      DestinationString.Buffer[1] = 63;
      DestinationString.Length -= 2;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
  }
  else
  {
    *(_QWORD *)&v31.Length = 48;
    v31.ObjectName = &NtPathName;
    *(_QWORD *)&v31.Attributes = 64;
    v32 = 0;
    SymbolicLinkHandle = 0;
    LinkTarget = 0;
    DataWritten = 0;
    v31.RootDirectory = 0;
    *(_OWORD *)&v31.SecurityDescriptor = 0;
    v12 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &v31);
    Length = NtPathName.Length + 2;
    NtPathName.Length += 2;
    if ( v12 >= 0 )
    {
      LinkTarget.Buffer = (PWSTR)&v36;
      *(_DWORD *)&LinkTarget.Length = 68157440;
      DataWritten = 0;
      v14 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
      NtClose(SymbolicLinkHandle);
      if ( v14 >= 0 )
        goto LABEL_28;
      Length = NtPathName.Length;
    }
    NtPathName.Length = Length - 2;
    if ( v11 >= 0 )
      NtClose(FileHandle);
  }
  v11 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
LABEL_28:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v11 < 0 )
    return 1;
  v15 = 4;
  if ( NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation) < 0 )
  {
LABEL_34:
    v15 = 0;
  }
  else if ( (FsInformation & 0x1000000000LL) == 0 )
  {
    if ( (_DWORD)FsInformation == 8 )
    {
LABEL_32:
      v15 = ((FsInformation & 0x100000000LL) == 0) | 2;
    }
    else
    {
      switch ( (int)FsInformation )
      {
        case 2:
        case 3:
          v15 = 5;
          break;
        case 7:
          goto LABEL_32;
        case 18:
        case 20:
          break;
        case 36:
          v15 = 6;
          break;
        default:
          goto LABEL_34;
      }
    }
  }
  NtClose(FileHandle);
  return v15;
}

```

## disassembly

```asm
0x180052890  mov     [rsp-8+arg_10], rbx
0x180052895  mov     [rsp-8+arg_18], rsi
0x18005289a  push    rbp
0x18005289b  push    rdi
0x18005289c  push    r14
0x18005289e  lea     rbp, [rsp-870h]
0x1800528a6  sub     rsp, 970h
0x1800528ad  mov     rax, cs:__security_cookie
0x1800528b4  xor     rax, rsp
0x1800528b7  mov     [rbp+880h+var_20], rax
0x1800528be  xorps   xmm0, xmm0
0x1800528c1  xor     r14d, r14d
0x1800528c4  xorps   xmm1, xmm1
0x1800528c7  mov     [rsp+980h+FileHandle], r14
0x1800528cc  xor     eax, eax
0x1800528ce  mov     [rsp+980h+FsInformation], r14
0x1800528d3  mov     [rbp+880h+var_8A0], rax
0x1800528d7  mov     rbx, rcx
0x1800528da  movups  xmmword ptr [rbp+880h+ObjectAttributes.ObjectName], xmm0
0x1800528de  movups  xmmword ptr [rbp+880h+ObjectAttributes+1Ch], xmm0
0x1800528e2  movups  xmmword ptr [rsp+980h+ObjectAttributes.Length], xmm0
0x1800528e7  movups  xmmword ptr [rsp+980h+NtPathName.Length], xmm0
0x1800528ec  movups  xmmword ptr [rsp+980h+DestinationString.Length], xmm1
0x1800528f1  movups  xmmword ptr [rbp+880h+IoStatusBlock], xmm0
0x1800528f5  movups  [rbp+880h+ProcessInformation], xmm1
0x1800528f9  movups  [rbp+880h+var_8B0], xmm1
0x1800528fd  test    rcx, rcx
0x180052900  jz      loc_180052DA1
0x180052906  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005290a  jz      loc_180052CD8
0x180052910  mov     rdi, rcx
0x180052913  call    cs:__imp_wcslen
0x18005291a  nop     dword ptr [rax+rax+00h]
0x18005291f  cmp     rax, 2
0x180052923  jz      loc_180052CDF
0x180052929  movzx   ecx, word ptr [rdi]; Source
0x18005292c  call    cs:__imp_RtlUpcaseUnicodeChar
0x180052933  nop     dword ptr [rax+rax+00h]
0x180052938  movzx   esi, ax
0x18005293b  lea     ecx, [rsi-41h]
0x18005293e  cmp     cx, 19h
0x180052942  ja      loc_1800529D5
0x180052948  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18005294d  jnz     loc_1800529D5
0x180052953  cmp     word ptr [rdi+4], 5Ch ; '\'
0x180052958  jnz     short loc_1800529D5
0x18005295a  cmp     [rdi+6], r14w
0x18005295f  jnz     short loc_1800529D5
0x180052961  mov     r9d, 24h ; '$'; ProcessInformationLength
0x180052967  mov     [rsp+980h+ReturnLength], r14; ReturnLength
0x18005296c  lea     r8, [rbp+880h+ProcessInformation]; ProcessInformation
0x180052970  mov     edx, 17h; ProcessInformationClass
0x180052975  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005297c  call    cs:__imp_NtQueryInformationProcess
0x180052983  nop     dword ptr [rax+rax+00h]
0x180052988  test    eax, eax
0x18005298a  js      loc_180052DCD
0x180052990  mov     eax, dword ptr [rbp+880h+ProcessInformation]
0x180052993  mov     ecx, esi
0x180052995  add     ecx, 0FFFFFFBFh
0x180052998  bt      eax, ecx
0x18005299b  jnb     short loc_1800529D5
0x18005299d  movzx   ecx, byte ptr [rbp+rcx+880h+ProcessInformation+4]
0x1800529a2  cmp     ecx, 3
0x1800529a5  jnz     loc_180052D6C
0x1800529ab  mov     eax, ecx
0x1800529ad  mov     rcx, [rbp+880h+var_20]
0x1800529b4  xor     rcx, rsp; StackCookie
0x1800529b7  call    __security_check_cookie
0x1800529bc  lea     r11, [rsp+980h+var_10]
0x1800529c4  mov     rbx, [r11+30h]
0x1800529c8  mov     rsi, [r11+38h]
0x1800529cc  mov     rsp, r11
0x1800529cf  pop     r14
0x1800529d1  pop     rdi
0x1800529d2  pop     rbp
0x1800529d3  retn
0x1800529d5  test    rbx, rbx
0x1800529d8  lea     rcx, asc_18029DEC8; "\\"
0x1800529df  lea     rdx, [rsp+980h+NtPathName]; NtPathName
0x1800529e4  cmovnz  rcx, rdi; DosPathName
0x1800529e8  xor     r9d, r9d; DirectoryInfo
0x1800529eb  xor     r8d, r8d; NtFileNamePart
0x1800529ee  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800529f5  nop     dword ptr [rax+rax+00h]
0x1800529fa  test    al, al
0x1800529fc  jz      loc_180052B91
0x180052a02  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180052a07  mov     rdi, [rsp+980h+NtPathName.Buffer]
0x180052a0c  mov     eax, ecx
0x180052a0e  shr     rax, 1
0x180052a11  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180052a17  jnz     loc_180052B73
0x180052a1d  lea     rax, [rsp+980h+NtPathName]
0x180052a22  mov     [rsp+980h+arg_8], r15
0x180052a2a  xorps   xmm0, xmm0
0x180052a2d  mov     [rsp+980h+OpenOptions], 60h ; '`'; OpenOptions
0x180052a35  mov     r15d, 0FFFEh
0x180052a3b  mov     [rsp+980h+ObjectAttributes.Length], 30h ; '0'
0x180052a43  add     cx, r15w
0x180052a47  mov     [rsp+980h+ObjectAttributes.RootDirectory], r14
0x180052a4c  mov     [rsp+980h+NtPathName.Length], cx
0x180052a51  lea     r9, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180052a55  lea     rcx, [rsp+980h+FileHandle]; FileHandle
0x180052a5a  mov     [rbp+880h+ObjectAttributes.Attributes], 40h ; '@'
0x180052a61  lea     r8, [rsp+980h+ObjectAttributes]; ObjectAttributes
0x180052a66  mov     [rbp+880h+ObjectAttributes.ObjectName], rax
0x180052a6a  mov     edx, 100080h; DesiredAccess
0x180052a6f  mov     dword ptr [rsp+980h+ReturnLength], 3; ShareAccess
0x180052a77  movdqu  xmmword ptr [rbp+880h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052a7c  call    cs:__imp_NtOpenFile
0x180052a83  nop     dword ptr [rax+rax+00h]
0x180052a88  mov     esi, eax
0x180052a8a  cmp     eax, 0C00000BAh
0x180052a8f  jz      loc_180052B9B
0x180052a95  movzx   eax, [rsp+980h+NtPathName.Length]
0x180052a9a  lea     r8, [rbp+880h+var_898]; ObjectAttributes
0x180052a9e  xorps   xmm0, xmm0
0x180052aa1  mov     [rsp+980h+NtPathName.Length], ax
0x180052aa6  lea     rax, [rsp+980h+NtPathName]
0x180052aab  mov     qword ptr [rbp+880h+var_898.Length], 30h ; '0'
0x180052ab3  mov     edx, 1; DesiredAccess
0x180052ab8  mov     [rbp+880h+var_898.ObjectName], rax
0x180052abc  lea     rcx, [rsp+980h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180052ac1  mov     qword ptr [rbp+880h+var_898.Attributes], 40h ; '@'
0x180052ac9  movups  [rbp+880h+var_868], xmm0
0x180052acd  mov     [rsp+980h+SymbolicLinkHandle], r14
0x180052ad2  movups  xmmword ptr [rbp+880h+LinkTarget.Length], xmm0
0x180052ad6  mov     [rsp+980h+DataWritten], r14d
0x180052adb  mov     [rbp+880h+var_898.RootDirectory], r14
0x180052adf  movdqu  xmmword ptr [rbp+880h+var_898.SecurityDescriptor], xmm0
0x180052ae4  call    cs:__imp_NtOpenSymbolicLinkObject
0x180052aeb  nop     dword ptr [rax+rax+00h]
0x180052af0  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180052af5  add     cx, 2
0x180052af9  mov     [rsp+980h+NtPathName.Length], cx
0x180052afe  test    eax, eax
0x180052b00  js      short loc_180052B53
0x180052b02  mov     rcx, [rsp+980h+SymbolicLinkHandle]; SymLinkObjHandle
0x180052b07  lea     rax, [rbp+880h+var_430]
0x180052b0e  lea     r8, [rsp+980h+DataWritten]; DataWritten
0x180052b13  mov     [rbp+880h+LinkTarget.Buffer], rax
0x180052b17  lea     rdx, [rbp+880h+LinkTarget]; LinkTarget
0x180052b1b  mov     dword ptr [rbp+880h+LinkTarget.Length], 4100000h
0x180052b22  mov     [rsp+980h+DataWritten], r14d
0x180052b27  call    cs:__imp_NtQuerySymbolicLinkObject
0x180052b2e  nop     dword ptr [rax+rax+00h]
0x180052b33  mov     rcx, [rsp+980h+SymbolicLinkHandle]; Handle
0x180052b38  mov     ebx, eax
0x180052b3a  call    cs:__imp_NtClose
0x180052b41  nop     dword ptr [rax+rax+00h]
0x180052b46  test    ebx, ebx
0x180052b48  jns     loc_180052BEC
0x180052b4e  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180052b53  add     cx, r15w
0x180052b57  mov     [rsp+980h+NtPathName.Length], cx
0x180052b5c  test    esi, esi
0x180052b5e  js      short loc_180052BBB
0x180052b60  mov     rcx, [rsp+980h+FileHandle]; Handle
0x180052b65  call    cs:__imp_NtClose
0x180052b6c  nop     dword ptr [rax+rax+00h]
0x180052b71  jmp     short loc_180052BBB
0x180052b73  mov     rcx, gs:60h
0x180052b7c  mov     r8, rdi; P
0x180052b7f  xor     edx, edx; Flags
0x180052b81  mov     rcx, [rcx+30h]; HeapHandle
0x180052b85  call    cs:__imp_RtlFreeHeap
0x180052b8c  nop     dword ptr [rax+rax+00h]
0x180052b91  mov     eax, 1
0x180052b96  jmp     loc_1800529AD
0x180052b9b  xor     r9d, r9d
0x180052b9e  lea     rdx, [rbp+880h+SourceString]; void *
0x180052ba5  mov     r8d, 104h; cchFilePath
0x180052bab  mov     rcx, rbx; lpFileName
0x180052bae  call    BasepGetVolumeNameFromReparsePoint
0x180052bb3  test    eax, eax
0x180052bb5  jnz     loc_180052C85
0x180052bbb  mov     [rsp+980h+OpenOptions], 20h ; ' '; OpenOptions
0x180052bc3  lea     r9, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180052bc7  lea     r8, [rsp+980h+ObjectAttributes]; ObjectAttributes
0x180052bcc  mov     dword ptr [rsp+980h+ReturnLength], 3; ShareAccess
0x180052bd4  mov     edx, 100080h; DesiredAccess
0x180052bd9  lea     rcx, [rsp+980h+FileHandle]; FileHandle
0x180052bde  call    cs:__imp_NtOpenFile
0x180052be5  nop     dword ptr [rax+rax+00h]
0x180052bea  mov     esi, eax
0x180052bec  mov     rcx, gs:60h
0x180052bf5  mov     r8, rdi; P
0x180052bf8  xor     edx, edx; Flags
0x180052bfa  mov     rcx, [rcx+30h]; HeapHandle
0x180052bfe  call    cs:__imp_RtlFreeHeap
0x180052c05  nop     dword ptr [rax+rax+00h]
0x180052c0a  mov     r15, [rsp+980h+arg_8]
0x180052c12  test    esi, esi
0x180052c14  js      loc_180052B91
0x180052c1a  mov     rcx, [rsp+980h+FileHandle]; FileHandle
0x180052c1f  lea     r8, [rsp+980h+FsInformation]; FsInformation
0x180052c24  mov     ebx, 4
0x180052c29  lea     rdx, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180052c2d  mov     r9d, 8; Length
0x180052c33  mov     dword ptr [rsp+980h+ReturnLength], ebx; FsInformationClass
0x180052c37  call    cs:__imp_NtQueryVolumeInformationFile
0x180052c3e  nop     dword ptr [rax+rax+00h]
0x180052c43  test    eax, eax
0x180052c45  js      short def_180052D5C; jumptable 0000000180052D5C default case, cases 4-6,8-17,19,21-35
0x180052c47  mov     edx, dword ptr [rsp+980h+FsInformation+4]
0x180052c4b  test    dl, 10h
0x180052c4e  jnz     short loc_180052C68; jumptable 0000000180052D5C cases 18,20
0x180052c50  mov     eax, dword ptr [rsp+980h+FsInformation]
0x180052c54  cmp     eax, 8
0x180052c57  jnz     loc_180052D35
0x180052c5d  movzx   ebx, dl; jumptable 0000000180052D5C case 7
0x180052c60  not     bl
0x180052c62  and     ebx, 1
0x180052c65  or      ebx, 2
0x180052c68  mov     rcx, [rsp+980h+FileHandle]; jumptable 0000000180052D5C cases 18,20
0x180052c6d  call    cs:__imp_NtClose
0x180052c74  nop     dword ptr [rax+rax+00h]
0x180052c79  mov     eax, ebx
0x180052c7b  jmp     loc_1800529AD
0x180052c80  mov     ebx, r14d; jumptable 0000000180052D5C default case, cases 4-6,8-17,19,21-35
0x180052c83  jmp     short loc_180052C68; jumptable 0000000180052D5C cases 18,20
0x180052c85  lea     rdx, [rbp+880h+SourceString]; SourceString
0x180052c8c  lea     rcx, [rsp+980h+DestinationString]; DestinationString
0x180052c91  call    cs:__imp_RtlInitUnicodeString
0x180052c98  nop     dword ptr [rax+rax+00h]
0x180052c9d  mov     rax, [rsp+980h+DestinationString.Buffer]
0x180052ca2  xorps   xmm0, xmm0
0x180052ca5  mov     word ptr [rax+2], 3Fh ; '?'
0x180052cab  lea     rax, [rsp+980h+DestinationString]
0x180052cb0  add     [rsp+980h+DestinationString.Length], r15w
0x180052cb6  mov     [rbp+880h+ObjectAttributes.ObjectName], rax
0x180052cba  mov     [rsp+980h+ObjectAttributes.Length], 30h ; '0'
0x180052cc2  mov     [rsp+980h+ObjectAttributes.RootDirectory], r14
0x180052cc7  mov     [rbp+880h+ObjectAttributes.Attributes], 40h ; '@'
0x180052cce  movdqu  xmmword ptr [rbp+880h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052cd3  jmp     loc_180052BBB
0x180052cd8  xor     eax, eax
0x180052cda  jmp     loc_1800529AD
0x180052cdf  movzx   ecx, word ptr [rbx]; Source
0x180052ce2  call    cs:__imp_RtlUpcaseUnicodeChar
0x180052ce9  nop     dword ptr [rax+rax+00h]
0x180052cee  sub     ax, 41h ; 'A'
0x180052cf2  cmp     ax, 19h
0x180052cf6  ja      loc_180052929
0x180052cfc  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180052d01  jnz     loc_180052929
0x180052d07  mov     r9d, 2; MaxCount
0x180052d0d  lea     rcx, [rbp+880h+Destination]; Destination
0x180052d11  mov     r8, rbx; Source
0x180052d14  mov     edx, 104h; SizeInWords
0x180052d19  call    cs:__imp_wcsncpy_s
0x180052d20  nop     dword ptr [rax+rax+00h]
0x180052d25  lea     rdi, [rbp+880h+Destination]
0x180052d29  mov     [rbp+880h+var_84C], 5Ch ; '\'
0x180052d30  jmp     loc_180052929
0x180052d35  add     eax, 0FFFFFFFEh; switch 35 cases
0x180052d38  cmp     eax, 22h
0x180052d3b  ja      def_180052D5C; jumptable 0000000180052D5C default case, cases 4-6,8-17,19,21-35
0x180052d41  lea     r8, __ImageBase
0x180052d48  movzx   eax, ds:(byte_180052E14 - 180000000h)[r8+rax]
0x180052d51  mov     ecx, ds:(jpt_180052D5C - 180000000h)[r8+rax*4]
0x180052d59  add     rcx, r8
0x180052d5c  jmp     rcx; switch jump
0x180052d62  mov     ebx, 5; jumptable 0000000180052D5C cases 2,3
0x180052d67  jmp     loc_180052C68; jumptable 0000000180052D5C cases 18,20
0x180052d6c  test    ecx, ecx
0x180052d6e  jz      loc_180052CD8
0x180052d74  sub     ecx, 2
0x180052d77  jz      short loc_180052D88
0x180052d79  sub     ecx, 2
0x180052d7c  jnz     short loc_180052D92
0x180052d7e  mov     eax, 4
0x180052d83  jmp     loc_1800529AD
0x180052d88  mov     eax, 2
0x180052d8d  jmp     loc_1800529AD
0x180052d92  sub     ecx, 1
0x180052d95  jnz     short loc_180052DE3
0x180052d97  mov     eax, 5
0x180052d9c  jmp     loc_1800529AD
0x180052da1  lea     rdx, [rbp+880h+Destination]; Buffer
0x180052da5  mov     ecx, 208h; MaximumLength
0x180052daa  lea     rdi, [rbp+880h+Destination]
0x180052dae  call    cs:__imp_RtlGetCurrentDirectory_U
0x180052db5  nop     dword ptr [rax+rax+00h]
0x180052dba  cmp     eax, 6
0x180052dbd  jbe     loc_180052929
0x180052dc3  mov     word ptr [rbp+880h+var_84C+2], r14w
0x180052dc8  jmp     loc_180052929
0x180052dcd  xorps   xmm0, xmm0
0x180052dd0  xor     eax, eax
0x180052dd2  movups  [rbp+880h+ProcessInformation], xmm0
0x180052dd6  mov     [rbp+880h+var_8A0], rax
0x180052dda  movups  [rbp+880h+var_8B0], xmm0
0x180052dde  jmp     loc_180052990
0x180052de3  cmp     ecx, 1
0x180052de6  jnz     loc_1800529D5
0x180052dec  mov     eax, 6
0x180052df1  jmp     loc_1800529AD
0x180052df6  mov     ebx, 6; jumptable 0000000180052D5C case 36
  ... truncated ...
```
