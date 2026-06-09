# IsTerminalFolderRedirection(ushort *,bool *)

- ea: `0x1800f05d4`
- end: `0x1800f09f9`
- name: `?IsTerminalFolderRedirection@@YAJPEAGPEA_N@Z`
- size: `1061`
- prototype: `__int64 __fastcall(unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ee320`

## callees

- `0x1800090c0`
- `0x180009130`
- `0x180019128`
- `0x1800f05d4`
- `0x18011f010`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800f081e`
- `ntdll!NtQueryInformationFile` at `0x1800f081e`
- `ntdll!NtOpenFile` at `0x1800f077e`
- `ntdll!NtOpenFile` at `0x1800f077e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f06b1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f06b1`
- `ntdll!NtClose` at `0x1800f08a8`
- `ntdll!NtClose` at `0x1800f09c6`
- `ntdll!NtClose` at `0x1800f08a8`
- `ntdll!NtClose` at `0x1800f09c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800f06c3`
- `ntdll!RtlNtStatusToDosError` at `0x1800f0790`
- `ntdll!RtlNtStatusToDosError` at `0x1800f0830`
- `ntdll!RtlNtStatusToDosError` at `0x1800f06c3`
- `ntdll!RtlNtStatusToDosError` at `0x1800f0790`
- `ntdll!RtlNtStatusToDosError` at `0x1800f0830`

## pseudocode

```c
__int64 __fastcall IsTerminalFolderRedirection(unsigned __int16 *a1, bool *a2)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  signed int v9; // eax
  int v10; // eax
  signed int v11; // eax
  int v12; // eax
  signed int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  void *FileHandle; // [rsp+30h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v20; // [rsp+70h] [rbp+17h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+27h] BYREF

  FileHandle = (void *)-1LL;
  FileInformation = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v20 = 0;
  if ( !a1 )
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v5;
    v7 = 10;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v5;
    v7 = 11;
LABEL_10:
    v4 = v5;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v4);
    goto LABEL_60;
  }
  *a2 = 1;
  v8 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &v20, 0, 0);
  if ( v8 < 0 )
  {
    v9 = RtlNtStatusToDosError(v8);
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_60;
    v7 = 13;
    goto LABEL_10;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 1u, 0x200000u);
  if ( v10 < 0 )
  {
    v11 = RtlNtStatusToDosError(v10);
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_60;
    v7 = 15;
    goto LABEL_10;
  }
  v12 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v12 < 0 )
  {
    v13 = RtlNtStatusToDosError(v12);
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_60;
    v7 = 17;
    goto LABEL_10;
  }
  if ( NtClose(FileHandle) >= 0 )
    FileHandle = (void *)-1LL;
  if ( (FileInformation & 0x10) == 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = 2147942487LL;
    v5 = -2147024809;
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_60;
    v7 = 19;
    goto LABEL_5;
  }
  v5 = 0;
  if ( (FileInformation & 0x400) != 0 )
  {
    if ( (FileInformation & 0x2000000000000000LL) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
      goto LABEL_60;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_52;
    v15 = 21;
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_52;
    v15 = 20;
  }
  WPP_SF_S(v14[2], v15, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
LABEL_52:
  *a2 = 0;
LABEL_60:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  return v5;
}

```

## disassembly

```asm
0x1800f05d4  mov     [rsp-8+arg_10], rbx
0x1800f05d9  mov     [rsp-8+arg_18], rsi
0x1800f05de  push    rbp
0x1800f05df  push    rdi
0x1800f05e0  push    r14
0x1800f05e2  lea     rbp, [rsp-47h]
0x1800f05e7  sub     rsp, 0A0h
0x1800f05ee  mov     rax, cs:__security_cookie
0x1800f05f5  xor     rax, rsp
0x1800f05f8  mov     [rbp+57h+var_20], rax
0x1800f05fc  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f0604  xorps   xmm0, xmm0
0x1800f0607  mov     [rbp+57h+FileInformation], 0
0x1800f060f  mov     rsi, rdx
0x1800f0612  mov     r14, rcx
0x1800f0615  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800f0619  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f061d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f0621  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f0625  movups  [rbp+57h+var_40], xmm0
0x1800f0629  test    rcx, rcx
0x1800f062c  jnz     short loc_1800F0671
0x1800f062e  mov     r9d, 80070057h
0x1800f0634  mov     ebx, r9d
0x1800f0637  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f063e  lea     rdi, WPP_GLOBAL_Control
0x1800f0645  cmp     rcx, rdi
0x1800f0648  jz      loc_1800F09D2
0x1800f064e  test    byte ptr [rcx+1Ch], 40h
0x1800f0652  jz      loc_1800F09D2
0x1800f0658  lea     edx, [r14+0Ah]
0x1800f065c  mov     rcx, [rcx+10h]
0x1800f0660  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f0667  call    WPP_SF_d
0x1800f066c  jmp     loc_1800F09BC
0x1800f0671  test    rsi, rsi
0x1800f0674  jnz     short loc_1800F06A4
0x1800f0676  mov     ebx, 80004003h
0x1800f067b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0682  lea     rdi, WPP_GLOBAL_Control
0x1800f0689  cmp     rcx, rdi
0x1800f068c  jz      loc_1800F09D2
0x1800f0692  test    byte ptr [rcx+1Ch], 40h
0x1800f0696  jz      loc_1800F09D2
0x1800f069c  lea     edx, [rsi+0Bh]
0x1800f069f  mov     r9d, ebx
0x1800f06a2  jmp     short loc_1800F065C
0x1800f06a4  mov     byte ptr [rdx], 1
0x1800f06a7  xor     r9d, r9d
0x1800f06aa  lea     rdx, [rbp+57h+var_40]
0x1800f06ae  xor     r8d, r8d
0x1800f06b1  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800f06b8  nop     dword ptr [rax+rax+00h]
0x1800f06bd  test    eax, eax
0x1800f06bf  jns     short loc_1800F0737
0x1800f06c1  mov     ecx, eax; Status
0x1800f06c3  call    cs:__imp_RtlNtStatusToDosError
0x1800f06ca  nop     dword ptr [rax+rax+00h]
0x1800f06cf  mov     ebx, eax
0x1800f06d1  test    eax, eax
0x1800f06d3  jle     short loc_1800F06DE
0x1800f06d5  movzx   ebx, ax
0x1800f06d8  or      ebx, 80070000h
0x1800f06de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f06e5  lea     rdi, WPP_GLOBAL_Control
0x1800f06ec  cmp     rcx, rdi
0x1800f06ef  jz      loc_1800F09BC
0x1800f06f5  test    byte ptr [rcx+1Ch], 2
0x1800f06f9  jz      short loc_1800F071A
0x1800f06fb  mov     rcx, [rcx+10h]
0x1800f06ff  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f0706  mov     edx, 0Ch
0x1800f070b  mov     r9d, ebx
0x1800f070e  call    WPP_SF_D
0x1800f0713  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f071a  cmp     rcx, rdi
0x1800f071d  jz      loc_1800F09BC
0x1800f0723  test    byte ptr [rcx+1Ch], 40h
0x1800f0727  jz      loc_1800F09BC
0x1800f072d  mov     edx, 0Dh
0x1800f0732  jmp     loc_1800F069F
0x1800f0737  lea     rax, [rbp+57h+var_40]
0x1800f073b  mov     [rsp+0B0h+OpenOptions], 200000h; OpenOptions
0x1800f0743  xorps   xmm0, xmm0
0x1800f0746  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f074a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f074e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f0755  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f0759  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800f0761  mov     edx, 80h; DesiredAccess
0x1800f0766  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f076d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f0771  mov     [rsp+0B0h+ShareAccess], 1; ShareAccess
0x1800f0779  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f077e  call    cs:__imp_NtOpenFile
0x1800f0785  nop     dword ptr [rax+rax+00h]
0x1800f078a  test    eax, eax
0x1800f078c  jns     short loc_1800F0804
0x1800f078e  mov     ecx, eax; Status
0x1800f0790  call    cs:__imp_RtlNtStatusToDosError
0x1800f0797  nop     dword ptr [rax+rax+00h]
0x1800f079c  mov     ebx, eax
0x1800f079e  test    eax, eax
0x1800f07a0  jle     short loc_1800F07AB
0x1800f07a2  movzx   ebx, ax
0x1800f07a5  or      ebx, 80070000h
0x1800f07ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f07b2  lea     rdi, WPP_GLOBAL_Control
0x1800f07b9  cmp     rcx, rdi
0x1800f07bc  jz      loc_1800F09BC
0x1800f07c2  test    byte ptr [rcx+1Ch], 2
0x1800f07c6  jz      short loc_1800F07E7
0x1800f07c8  mov     rcx, [rcx+10h]
0x1800f07cc  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f07d3  mov     edx, 0Eh
0x1800f07d8  mov     r9d, ebx
0x1800f07db  call    WPP_SF_D
0x1800f07e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f07e7  cmp     rcx, rdi
0x1800f07ea  jz      loc_1800F09BC
0x1800f07f0  test    byte ptr [rcx+1Ch], 40h
0x1800f07f4  jz      loc_1800F09BC
0x1800f07fa  mov     edx, 0Fh
0x1800f07ff  jmp     loc_1800F069F
0x1800f0804  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f0808  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800f080c  mov     r9d, 8; Length
0x1800f0812  mov     [rsp+0B0h+ShareAccess], 23h ; '#'; FileInformationClass
0x1800f081a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f081e  call    cs:__imp_NtQueryInformationFile
0x1800f0825  nop     dword ptr [rax+rax+00h]
0x1800f082a  test    eax, eax
0x1800f082c  jns     short loc_1800F08A4
0x1800f082e  mov     ecx, eax; Status
0x1800f0830  call    cs:__imp_RtlNtStatusToDosError
0x1800f0837  nop     dword ptr [rax+rax+00h]
0x1800f083c  mov     ebx, eax
0x1800f083e  test    eax, eax
0x1800f0840  jle     short loc_1800F084B
0x1800f0842  movzx   ebx, ax
0x1800f0845  or      ebx, 80070000h
0x1800f084b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0852  lea     rdi, WPP_GLOBAL_Control
0x1800f0859  cmp     rcx, rdi
0x1800f085c  jz      loc_1800F09BC
0x1800f0862  test    byte ptr [rcx+1Ch], 2
0x1800f0866  jz      short loc_1800F0887
0x1800f0868  mov     rcx, [rcx+10h]
0x1800f086c  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f0873  mov     edx, 10h
0x1800f0878  mov     r9d, ebx
0x1800f087b  call    WPP_SF_D
0x1800f0880  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0887  cmp     rcx, rdi
0x1800f088a  jz      loc_1800F09BC
0x1800f0890  test    byte ptr [rcx+1Ch], 40h
0x1800f0894  jz      loc_1800F09BC
0x1800f089a  mov     edx, 11h
0x1800f089f  jmp     loc_1800F069F
0x1800f08a4  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f08a8  call    cs:__imp_NtClose
0x1800f08af  nop     dword ptr [rax+rax+00h]
0x1800f08b4  test    eax, eax
0x1800f08b6  js      short loc_1800F08C0
0x1800f08b8  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f08c0  test    byte ptr [rbp+57h+FileInformation], 10h
0x1800f08c4  jnz     short loc_1800F0924
0x1800f08c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f08cd  lea     rdi, WPP_GLOBAL_Control
0x1800f08d4  cmp     rcx, rdi
0x1800f08d7  jz      short loc_1800F08FE
0x1800f08d9  test    byte ptr [rcx+1Ch], 2
0x1800f08dd  jz      short loc_1800F08FE
0x1800f08df  mov     rcx, [rcx+10h]
0x1800f08e3  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f08ea  mov     edx, 12h
0x1800f08ef  mov     r9, r14
0x1800f08f2  call    WPP_SF_S
0x1800f08f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f08fe  mov     r9d, 80070057h
0x1800f0904  mov     ebx, r9d
0x1800f0907  cmp     rcx, rdi
0x1800f090a  jz      loc_1800F09BC
0x1800f0910  test    byte ptr [rcx+1Ch], 40h
0x1800f0914  jz      loc_1800F09BC
0x1800f091a  mov     edx, 13h
0x1800f091f  jmp     loc_1800F065C
0x1800f0924  xor     ebx, ebx
0x1800f0926  test    dword ptr [rbp+57h+FileInformation], 400h
0x1800f092d  jnz     short loc_1800F0962
0x1800f092f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0936  lea     rdi, WPP_GLOBAL_Control
0x1800f093d  cmp     rcx, rdi
0x1800f0940  jz      short loc_1800F095E
0x1800f0942  test    byte ptr [rcx+1Ch], 8
0x1800f0946  jz      short loc_1800F095E
0x1800f0948  lea     edx, [rbx+14h]
0x1800f094b  mov     rcx, [rcx+10h]
0x1800f094f  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f0956  mov     r9, r14
0x1800f0959  call    WPP_SF_S
0x1800f095e  mov     [rsi], bl
0x1800f0960  jmp     short loc_1800F09BC
0x1800f0962  test    dword ptr [rbp+57h+FileInformation+4], 20000000h
0x1800f0969  jnz     short loc_1800F098B
0x1800f096b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0972  lea     rdi, WPP_GLOBAL_Control
0x1800f0979  cmp     rcx, rdi
0x1800f097c  jz      short loc_1800F095E
0x1800f097e  test    byte ptr [rcx+1Ch], 8
0x1800f0982  jz      short loc_1800F095E
0x1800f0984  mov     edx, 15h
0x1800f0989  jmp     short loc_1800F094B
0x1800f098b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0992  lea     rdi, WPP_GLOBAL_Control
0x1800f0999  cmp     rcx, rdi
0x1800f099c  jz      short loc_1800F09BC
0x1800f099e  test    byte ptr [rcx+1Ch], 8
0x1800f09a2  jz      short loc_1800F09BC
0x1800f09a4  mov     rcx, [rcx+10h]
0x1800f09a8  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f09af  mov     edx, 16h
0x1800f09b4  mov     r9, r14
0x1800f09b7  call    WPP_SF_S
0x1800f09bc  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f09c0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f09c4  jz      short loc_1800F09D2
0x1800f09c6  call    cs:__imp_NtClose
0x1800f09cd  nop     dword ptr [rax+rax+00h]
0x1800f09d2  mov     eax, ebx
0x1800f09d4  mov     rcx, [rbp+57h+var_20]
0x1800f09d8  xor     rcx, rsp; StackCookie
0x1800f09db  call    __security_check_cookie
0x1800f09e0  lea     r11, [rsp+0B0h+var_10]
0x1800f09e8  mov     rbx, [r11+30h]
0x1800f09ec  mov     rsi, [r11+38h]
0x1800f09f0  mov     rsp, r11
0x1800f09f3  pop     r14
0x1800f09f5  pop     rdi
0x1800f09f6  pop     rbp
0x1800f09f7  retn
```
