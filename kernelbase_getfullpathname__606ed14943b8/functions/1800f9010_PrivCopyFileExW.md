# PrivCopyFileExW

- ea: `0x1800f9010`
- end: `0x1800f949d`
- name: `PrivCopyFileExW`
- size: `1165`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x180053c30`
- `0x1800f9010`
- `0x1800f9650`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800f9410`
- `ntdll!RtlFreeUnicodeString` at `0x180198835`
- `ntdll!RtlFreeUnicodeString` at `0x1800f9410`
- `ntdll!RtlFreeUnicodeString` at `0x180198835`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f914b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f914b`
- `ntdll!NtFsControlFile` at `0x1800f92be`
- `ntdll!NtFsControlFile` at `0x1800f92be`
- `ntdll!NtCreateFile` at `0x1800f91e4`
- `ntdll!NtCreateFile` at `0x1800f91e4`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9383`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9452`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9383`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9452`
- `ntdll!NtWaitForSingleObject` at `0x1800f9478`
- `ntdll!NtWaitForSingleObject` at `0x1801987fb`
- `ntdll!NtWaitForSingleObject` at `0x1800f9478`
- `ntdll!NtWaitForSingleObject` at `0x1801987fb`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f90ff`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f93bb`
- `ntdll!RtlSetCurrentTransaction` at `0x1801987b1`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f90ff`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f93bb`
- `ntdll!RtlSetCurrentTransaction` at `0x1801987b1`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f90e6`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f90e6`
- `ntdll!NtCreateEvent` at `0x1800f920c`
- `ntdll!NtCreateEvent` at `0x1800f920c`
- `ntdll!NtClose` at `0x1800f9399`
- `ntdll!NtClose` at `0x1800f9462`
- `ntdll!NtClose` at `0x1800f948c`
- `ntdll!NtClose` at `0x1801987dd`
- `ntdll!NtClose` at `0x18019880e`
- `ntdll!NtClose` at `0x1800f9399`
- `ntdll!NtClose` at `0x1800f9462`
- `ntdll!NtClose` at `0x1800f948c`
- `ntdll!NtClose` at `0x1801987dd`
- `ntdll!NtClose` at `0x18019880e`

## pseudocode

```c
__int64 __fastcall PrivCopyFileExW(
        WCHAR *DosPathName,
        const WCHAR *a2,
        unsigned __int64 a3,
        __int64 a4,
        int *a5,
        unsigned int a6)
{
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  __int64 CurrentTransaction; // rdi
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // esi
  __int64 CreateDisposition; // [rsp+38h] [rbp-150h]
  HANDLE EventHandle; // [rsp+80h] [rbp-108h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-100h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-F8h] BYREF
  HANDLE v19; // [rsp+98h] [rbp-F0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+A0h] [rbp-E8h] BYREF
  unsigned __int64 v21; // [rsp+B0h] [rbp-D8h]
  int *v22; // [rsp+B8h] [rbp-D0h]
  __int64 v23; // [rsp+C0h] [rbp-C8h]
  __int64 v24; // [rsp+C8h] [rbp-C0h]
  __int128 v25; // [rsp+D0h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp-78h] BYREF
  __int64 InputBuffer; // [rsp+120h] [rbp-68h] BYREF
  int v29; // [rsp+128h] [rbp-60h]
  __int128 OutputBuffer; // [rsp+130h] [rbp-58h] BYREF
  __int64 v31; // [rsp+140h] [rbp-48h]

  v23 = a4;
  v21 = a3;
  v22 = a5;
  InputBuffer = 0;
  v29 = 0;
  OutputBuffer = 0;
  v31 = 0;
  FileHandle = (HANDLE)-1LL;
  EventHandle = 0;
  IoStatusBlock = 0;
  NtPathName = 0;
  v19 = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  v25 = 0;
  if ( (a6 & 0x201) == 0x201 || (a6 & 0x20000) != 0 && (a6 & 0x8000) == 0 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v8 = 0;
  v9 = a6 & 0xBFFFFFFF;
  if ( (a6 & 0x40000000) == 0 )
    v9 = a6;
  CurrentTransaction = RtlGetCurrentTransaction();
  v24 = CurrentTransaction;
  RtlSetCurrentTransaction(0);
  if ( (v9 & 0x20000) == 0 )
    goto LABEL_12;
  memset(&ObjectAttributes, 0, 44);
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    goto LABEL_15;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x10040u, 0, 0);
  if ( v11 >= 0 )
  {
    v11 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    if ( v11 >= 0 )
    {
      InputBuffer = 0x3000C0001LL;
      v29 = 1;
      OutputBuffer = 0;
      v31 = 0;
      v13 = NtFsControlFile(
              FileHandle,
              EventHandle,
              0,
              0,
              &IoStatusBlock,
              0x90240u,
              &InputBuffer,
              0xCu,
              &OutputBuffer,
              0x18u);
      if ( v13 != 259 )
      {
        NtClose(EventHandle);
        EventHandle = 0;
        v12 = v13;
        goto LABEL_10;
      }
LABEL_12:
      v25 = v21;
      LODWORD(CreateDisposition) = v9 & 0xBEE4F88F;
      v8 = BasepCopyFileExW(
             DosPathName,
             a2,
             (__int64)&v25,
             v23,
             v22,
             (__int64)EventHandle,
             (__int64)&FileHandle,
             CreateDisposition,
             v9 & 0x411B0770,
             &hObject,
             &v19,
             CurrentTransaction,
             (a6 & 0x40000000) != 0,
             0,
             0,
             0);
      goto LABEL_15;
    }
  }
  v12 = (unsigned int)v11;
LABEL_10:
  BaseSetLastNTError(v12);
LABEL_15:
  RtlSetCurrentTransaction(CurrentTransaction);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( EventHandle )
  {
    NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
  }
  if ( v19 != (HANDLE)-1LL )
    CloseHandle(v19);
  RtlFreeUnicodeString(&NtPathName);
  return v8;
}

```

## disassembly

```asm
0x1800f9010  mov     r11, rsp
0x1800f9013  push    rbx
0x1800f9014  push    rsi
0x1800f9015  push    rdi
0x1800f9016  push    r12
0x1800f9018  push    r13
0x1800f901a  push    r14
0x1800f901c  push    r15
0x1800f901e  sub     rsp, 150h
0x1800f9025  mov     rax, cs:__security_cookie
0x1800f902c  xor     rax, rsp
0x1800f902f  mov     [rsp+188h+var_40], rax
0x1800f9037  mov     [rsp+188h+var_C8], r9
0x1800f903f  mov     [rsp+188h+var_D8], r8
0x1800f9047  mov     r13, rdx
0x1800f904a  mov     r12, rcx
0x1800f904d  mov     rax, [rsp+188h+arg_20]
0x1800f9055  mov     [rsp+188h+var_D0], rax
0x1800f905d  xor     eax, eax
0x1800f905f  mov     [r11-68h], rax
0x1800f9063  mov     [r11-60h], eax
0x1800f9067  xorps   xmm0, xmm0
0x1800f906a  movups  xmmword ptr [r11-58h], xmm0
0x1800f906f  mov     [r11-48h], rax
0x1800f9073  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f9077  mov     [r11-100h], rax
0x1800f907e  xor     esi, esi
0x1800f9080  mov     [r11-108h], rsi
0x1800f9087  movups  xmmword ptr [r11-78h], xmm0
0x1800f908c  xorps   xmm1, xmm1
0x1800f908f  movups  xmmword ptr [rsp+188h+NtPathName.Length], xmm1
0x1800f9097  mov     [r11-0F0h], rax
0x1800f909e  mov     [r11-0F8h], rax
0x1800f90a5  movups  [rsp+188h+var_B8], xmm0
0x1800f90ad  mov     ecx, [rsp+188h+arg_28]
0x1800f90b4  mov     eax, ecx
0x1800f90b6  mov     edx, 201h
0x1800f90bb  and     eax, edx
0x1800f90bd  cmp     eax, edx
0x1800f90bf  jz      loc_1800F944D
0x1800f90c5  bt      ecx, 11h
0x1800f90c9  jb      loc_1800F9443
0x1800f90cf  mov     r14d, esi
0x1800f90d2  mov     ebx, ecx
0x1800f90d4  btr     ebx, 1Eh
0x1800f90d8  bt      ecx, 1Eh
0x1800f90dc  cmovnb  ebx, ecx
0x1800f90df  mov     r15d, esi
0x1800f90e2  setb    r15b
0x1800f90e6  call    cs:__imp_RtlGetCurrentTransaction
0x1800f90ed  nop     dword ptr [rax+rax+00h]
0x1800f90f2  mov     rdi, rax
0x1800f90f5  mov     [rsp+188h+var_C0], rax
0x1800f90fd  xor     ecx, ecx
0x1800f90ff  call    cs:__imp_RtlSetCurrentTransaction
0x1800f9106  nop     dword ptr [rax+rax+00h]
0x1800f910b  nop
0x1800f910c  bt      ebx, 11h
0x1800f9110  jnb     loc_1800F92D9
0x1800f9116  xor     eax, eax
0x1800f9118  mov     dword ptr [rsp+188h+ObjectAttributes+4], eax
0x1800f911f  xorps   xmm0, xmm0
0x1800f9122  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x1800f912a  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x1800f9132  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x1800f913a  xor     r9d, r9d; DirectoryInfo
0x1800f913d  xor     r8d, r8d; NtFileNamePart
0x1800f9140  lea     rdx, [rsp+188h+NtPathName]; NtPathName
0x1800f9148  mov     rcx, r12; DosPathName
0x1800f914b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f9152  nop     dword ptr [rax+rax+00h]
0x1800f9157  test    al, al
0x1800f9159  jz      loc_1800F937E
0x1800f915f  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x1800f916a  mov     [rsp+188h+ObjectAttributes.RootDirectory], rsi
0x1800f9172  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f917d  lea     rax, [rsp+188h+NtPathName]
0x1800f9185  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x1800f918d  xorps   xmm0, xmm0
0x1800f9190  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f9199  mov     [rsp+188h+EaLength], esi; EaLength
0x1800f919d  mov     [rsp+188h+EaBuffer], rsi; EaBuffer
0x1800f91a2  mov     [rsp+188h+CreateOptions], 10040h; CreateOptions
0x1800f91aa  mov     dword ptr [rsp+188h+CreateDisposition], 1; CreateDisposition
0x1800f91b2  mov     [rsp+188h+ShareAccess], 7; ShareAccess
0x1800f91ba  mov     [rsp+188h+FileAttributes], 80h; FileAttributes
0x1800f91c2  mov     [rsp+188h+AllocationSize], rsi; AllocationSize
0x1800f91c7  lea     r9, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x1800f91cf  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800f91d7  mov     edx, 120089h; DesiredAccess
0x1800f91dc  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800f91e4  call    cs:__imp_NtCreateFile
0x1800f91eb  nop     dword ptr [rax+rax+00h]
0x1800f91f0  test    eax, eax
0x1800f91f2  js      short loc_1800F921C
0x1800f91f4  mov     byte ptr [rsp+188h+AllocationSize], sil; InitialState
0x1800f91f9  xor     r9d, r9d; EventType
0x1800f91fc  xor     r8d, r8d; ObjectAttributes
0x1800f91ff  mov     edx, 1F0003h; DesiredAccess
0x1800f9204  lea     rcx, [rsp+188h+EventHandle]; EventHandle
0x1800f920c  call    cs:__imp_NtCreateEvent
0x1800f9213  nop     dword ptr [rax+rax+00h]
0x1800f9218  test    eax, eax
0x1800f921a  jns     short loc_1800F9228
0x1800f921c  mov     ecx, eax
0x1800f921e  call    BaseSetLastNTError
0x1800f9223  jmp     loc_1800F93B8
0x1800f9228  xor     eax, eax
0x1800f922a  mov     [rsp+188h+InputBuffer], rax
0x1800f9232  mov     [rsp+188h+InputBuffer+4], 3
0x1800f923e  mov     eax, 1
0x1800f9243  mov     dword ptr [rsp+188h+InputBuffer], 0C0001h
0x1800f924e  lea     ecx, [rax+0Bh]
0x1800f9251  mov     [rsp+188h+var_60], eax
0x1800f9258  xorps   xmm0, xmm0
0x1800f925b  xor     eax, eax
0x1800f925d  movups  [rsp+188h+OutputBuffer], xmm0
0x1800f9265  mov     [rsp+188h+var_48], rax
0x1800f926d  mov     dword ptr [rsp+188h+EaBuffer], 18h; OutputBufferLength
0x1800f9275  lea     rax, [rsp+188h+OutputBuffer]
0x1800f927d  mov     qword ptr [rsp+188h+CreateOptions], rax; OutputBuffer
0x1800f9282  mov     dword ptr [rsp+188h+CreateDisposition], ecx; InputBufferLength
0x1800f9286  lea     rax, [rsp+188h+InputBuffer]
0x1800f928e  mov     qword ptr [rsp+188h+ShareAccess], rax; InputBuffer
0x1800f9293  mov     [rsp+188h+FileAttributes], 90240h; FsControlCode
0x1800f929b  lea     rax, [rsp+188h+IoStatusBlock]
0x1800f92a3  mov     [rsp+188h+AllocationSize], rax; IoStatusBlock
0x1800f92a8  xor     r9d, r9d; ApcContext
0x1800f92ab  xor     r8d, r8d; ApcRoutine
0x1800f92ae  mov     rdx, [rsp+188h+EventHandle]; Event
0x1800f92b6  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800f92be  call    cs:__imp_NtFsControlFile
0x1800f92c5  nop     dword ptr [rax+rax+00h]
0x1800f92ca  mov     esi, eax
0x1800f92cc  cmp     eax, 103h
0x1800f92d1  jnz     loc_1800F9391
0x1800f92d7  xor     esi, esi
0x1800f92d9  mov     rax, [rsp+188h+var_D8]
0x1800f92e1  mov     qword ptr [rsp+188h+var_B8], rax
0x1800f92e9  mov     qword ptr [rsp+188h+var_B8+8], rsi
0x1800f92f1  mov     eax, ebx
0x1800f92f3  and     eax, 411B0770h
0x1800f92f8  and     ebx, 0BEE4F88Fh
0x1800f92fe  mov     [rsp+188h+var_110], rsi
0x1800f9303  mov     [rsp+188h+var_118], esi
0x1800f9307  mov     [rsp+188h+var_120], esi
0x1800f930b  mov     [rsp+188h+var_128], r15d
0x1800f9310  mov     [rsp+188h+var_130], rdi
0x1800f9315  lea     rcx, [rsp+188h+var_F0]
0x1800f931d  mov     qword ptr [rsp+188h+EaLength], rcx
0x1800f9322  lea     rcx, [rsp+188h+hObject]
0x1800f932a  mov     [rsp+188h+EaBuffer], rcx
0x1800f932f  mov     [rsp+188h+CreateOptions], eax
0x1800f9333  mov     dword ptr [rsp+188h+CreateDisposition], ebx
0x1800f9337  lea     rax, [rsp+188h+FileHandle]
0x1800f933f  mov     qword ptr [rsp+188h+ShareAccess], rax
0x1800f9344  mov     rax, [rsp+188h+EventHandle]
0x1800f934c  mov     qword ptr [rsp+188h+FileAttributes], rax
0x1800f9351  mov     rax, [rsp+188h+var_D0]
0x1800f9359  mov     [rsp+188h+AllocationSize], rax
0x1800f935e  mov     r9, [rsp+188h+var_C8]
0x1800f9366  lea     r8, [rsp+188h+var_B8]
0x1800f936e  mov     rdx, r13
0x1800f9371  mov     rcx, r12
0x1800f9374  call    BasepCopyFileExW
0x1800f9379  mov     r14d, eax
0x1800f937c  jmp     short loc_1800F93B8
0x1800f937e  mov     ecx, 3; LastError
0x1800f9383  call    cs:__imp_RtlSetLastWin32Error
0x1800f938a  nop     dword ptr [rax+rax+00h]
0x1800f938f  jmp     short loc_1800F93B8
0x1800f9391  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800f9399  call    cs:__imp_NtClose
0x1800f93a0  nop     dword ptr [rax+rax+00h]
0x1800f93a5  mov     [rsp+188h+EventHandle], 0
0x1800f93b1  mov     ecx, esi
0x1800f93b3  jmp     loc_1800F921E
0x1800f93b8  mov     rcx, rdi
0x1800f93bb  call    cs:__imp_RtlSetCurrentTransaction
0x1800f93c2  nop     dword ptr [rax+rax+00h]
0x1800f93c7  mov     rcx, [rsp+188h+hObject]; hObject
0x1800f93cf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f93d3  jz      short loc_1800F93DA
0x1800f93d5  call    CloseHandle
0x1800f93da  mov     rcx, [rsp+188h+FileHandle]; Handle
0x1800f93e2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f93e6  jnz     short loc_1800F9462
0x1800f93e8  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800f93f0  test    rcx, rcx
0x1800f93f3  jnz     short loc_1800F9473
0x1800f93f5  mov     rcx, [rsp+188h+var_F0]; hObject
0x1800f93fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f9401  jz      short loc_1800F9408
0x1800f9403  call    CloseHandle
0x1800f9408  lea     rcx, [rsp+188h+NtPathName]; UnicodeString
0x1800f9410  call    cs:__imp_RtlFreeUnicodeString
0x1800f9417  nop     dword ptr [rax+rax+00h]
0x1800f941c  mov     eax, r14d
0x1800f941f  mov     rcx, [rsp+188h+var_40]
0x1800f9427  xor     rcx, rsp; StackCookie
0x1800f942a  call    __security_check_cookie
0x1800f942f  add     rsp, 150h
0x1800f9436  pop     r15
0x1800f9438  pop     r14
0x1800f943a  pop     r13
0x1800f943c  pop     r12
0x1800f943e  pop     rdi
0x1800f943f  pop     rsi
0x1800f9440  pop     rbx
0x1800f9441  retn
0x1800f9443  bt      ecx, 0Fh
0x1800f9447  jb      loc_1800F90CF
0x1800f944d  mov     ecx, 57h ; 'W'; LastError
0x1800f9452  call    cs:__imp_RtlSetLastWin32Error
0x1800f9459  nop     dword ptr [rax+rax+00h]
0x1800f945e  xor     eax, eax
0x1800f9460  jmp     short loc_1800F941F
0x1800f9462  call    cs:__imp_NtClose
0x1800f9469  nop     dword ptr [rax+rax+00h]
0x1800f946e  jmp     loc_1800F93E8
0x1800f9473  xor     r8d, r8d; Timeout
0x1800f9476  xor     edx, edx; Alertable
0x1800f9478  call    cs:__imp_NtWaitForSingleObject
0x1800f947f  nop     dword ptr [rax+rax+00h]
0x1800f9484  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800f948c  call    cs:__imp_NtClose
0x1800f9493  nop     dword ptr [rax+rax+00h]
0x1800f9498  jmp     loc_1800F93F5
0x18019879e  push    rbp
0x1801987a0  sub     rsp, 80h
0x1801987a7  mov     rbp, rdx
0x1801987aa  mov     rcx, [rbp+0C8h]
0x1801987b1  call    cs:__imp_RtlSetCurrentTransaction
0x1801987b8  nop     dword ptr [rax+rax+00h]
0x1801987bd  mov     rcx, [rbp+90h]; hObject
0x1801987c4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801987c8  jz      short loc_1801987D0
0x1801987ca  call    CloseHandle
0x1801987cf  nop
0x1801987d0  mov     rcx, [rbp+88h]; Handle
0x1801987d7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801987db  jz      short loc_1801987EA
0x1801987dd  call    cs:__imp_NtClose
0x1801987e4  nop     dword ptr [rax+rax+00h]
0x1801987e9  nop
0x1801987ea  mov     rcx, [rbp+80h]; Handle
0x1801987f1  test    rcx, rcx
0x1801987f4  jz      short loc_18019881B
0x1801987f6  xor     r8d, r8d; Timeout
0x1801987f9  xor     edx, edx; Alertable
0x1801987fb  call    cs:__imp_NtWaitForSingleObject
0x180198802  nop     dword ptr [rax+rax+00h]
0x180198807  mov     rcx, [rbp+80h]; Handle
0x18019880e  call    cs:__imp_NtClose
0x180198815  nop     dword ptr [rax+rax+00h]
0x18019881a  nop
0x18019881b  mov     rcx, [rbp+98h]; hObject
0x180198822  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180198826  jz      short loc_18019882E
0x180198828  call    CloseHandle
0x18019882d  nop
0x18019882e  lea     rcx, [rbp+0A0h]; UnicodeString
0x180198835  call    cs:__imp_RtlFreeUnicodeString
0x18019883c  nop     dword ptr [rax+rax+00h]
0x180198841  nop
0x180198842  add     rsp, 80h
0x180198849  pop     rbp
0x18019884a  retn
```
