# CiGetBuildExpiryTime

- ea: `0x180097690`
- end: `0x180097950`
- name: `CiGetBuildExpiryTime`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002bef0`
- `0x180096fdc`
- `0x180097690`
- `0x180097958`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180097734`
- `ntoskrnl!KeStackAttachProcess` at `0x180097734`
- `ntoskrnl!ZwOpenFile` at `0x180097783`
- `ntoskrnl!ZwOpenFile` at `0x180097783`
- `ntoskrnl!ZwClose` at `0x1800978e1`
- `ntoskrnl!ZwClose` at `0x180097942`
- `ntoskrnl!ZwClose` at `0x1800978e1`
- `ntoskrnl!ZwClose` at `0x180097942`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800978f1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800978f1`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800978ba`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800978ba`
- `ntoskrnl!ZwCreateSection` at `0x18009781e`
- `ntoskrnl!ZwCreateSection` at `0x18009781e`
- `ntoskrnl!ZwMapViewOfSection` at `0x180097872`
- `ntoskrnl!ZwMapViewOfSection` at `0x180097872`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800977b0`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800977b0`

## string_xrefs

- `0x1800976cb`: `\SystemRoot\System32\ci.dll`

## pseudocode

```c
__int64 __fastcall CiGetBuildExpiryTime(_QWORD *a1)
{
  int v2; // ebx
  int v3; // r8d
  int v5; // [rsp+30h] [rbp-D0h]
  ULONG Win32Protect; // [rsp+48h] [rbp-B8h]
  PVOID BaseAddress; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  void *SectionHandle; // [rsp+90h] [rbp-70h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v12[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v14; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v15; // [rsp+100h] [rbp+0h]
  __int128 v16; // [rsp+110h] [rbp+10h]
  _OWORD FileInformation[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v18; // [rsp+140h] [rbp+40h]
  __int64 v19; // [rsp+150h] [rbp+50h]
  struct _KAPC_STATE ApcState; // [rsp+158h] [rbp+58h] BYREF

  v12[0] = 3670070;
  v12[1] = L"\\SystemRoot\\System32\\ci.dll";
  FileHandle = 0;
  v19 = 0;
  SectionHandle = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  BaseAddress = 0;
  ViewSize = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v18 = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  KeStackAttachProcess(g_CiSystemProcess, &ApcState);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 704;
  v2 = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 1u, 0x60u);
  if ( v2 >= 0 )
  {
    v2 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x38u, FileNetworkOpenInformation);
    if ( v2 >= 0 )
    {
      if ( HIDWORD(v18) || !DWORD2(v18) )
      {
        v2 = -1073741792;
      }
      else
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v2 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
        if ( v2 >= 0 )
        {
          ViewSize = DWORD2(v18);
          BaseAddress = 0;
          v2 = ZwMapViewOfSection(
                 SectionHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &BaseAddress,
                 0,
                 0,
                 0,
                 &ViewSize,
                 ViewUnmap,
                 0,
                 2u);
          if ( v2 >= 0 )
          {
            v2 = CipValidateDataMappedFile(
                   (_DWORD)BaseAddress,
                   DWORD2(v18),
                   v3,
                   1,
                   12,
                   1,
                   v5,
                   0,
                   (__int64)&v14,
                   Win32Protect);
            ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
            if ( v2 >= 0 )
              *a1 = *((_QWORD *)&v16 + 1);
          }
        }
      }
    }
  }
  if ( (_DWORD)v14 )
    I_MincryptFreeChainInfo(v15);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180097690  mov     [rsp-8+arg_8], rbx
0x180097695  mov     [rsp-8+arg_10], rsi
0x18009769a  push    rbp
0x18009769b  push    rdi
0x18009769c  push    r14
0x18009769e  lea     rbp, [rsp-90h]
0x1800976a6  sub     rsp, 190h
0x1800976ad  mov     rax, cs:__security_cookie
0x1800976b4  xor     rax, rsp
0x1800976b7  mov     [rbp+0A0h+var_18], rax
0x1800976be  xorps   xmm0, xmm0
0x1800976c1  mov     [rbp+0A0h+var_D0], 380036h
0x1800976c9  xor     esi, esi
0x1800976cb  lea     rax, aSystemrootSyst_1; "\\SystemRoot\\System32\\ci.dll"
0x1800976d2  mov     [rbp+0A0h+var_C8], rax
0x1800976d6  lea     rdx, [rbp+0A0h+ApcState]; ApcState
0x1800976da  xor     eax, eax
0x1800976dc  mov     [rbp+0A0h+FileHandle], rsi
0x1800976e0  mov     rdi, rcx
0x1800976e3  mov     [rbp+0A0h+var_50], rax
0x1800976e7  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x1800976ee  mov     r14d, 38h ; '8'
0x1800976f4  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1800976f8  mov     [rbp+0A0h+SectionHandle], rsi
0x1800976fc  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink], xmm0
0x180097700  mov     [rbp+0A0h+BaseAddress], rsi
0x180097704  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink+10h], xmm0
0x180097708  mov     [rbp+0A0h+ViewSize], rsi
0x18009770c  movups  xmmword ptr [rbp+0A0h+ApcState.Process], xmm0
0x180097710  movups  [rbp+0A0h+FileInformation], xmm0
0x180097714  movups  [rbp+0A0h+var_70], xmm0
0x180097718  movups  [rbp+0A0h+var_60], xmm0
0x18009771c  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x180097720  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x180097724  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x180097728  movups  [rbp+0A0h+var_B0], xmm0
0x18009772c  movups  [rbp+0A0h+var_A0], xmm0
0x180097730  movups  [rbp+0A0h+var_90], xmm0
0x180097734  call    cs:__imp_KeStackAttachProcess
0x18009773b  nop     dword ptr [rax+rax+00h]
0x180097740  lea     rax, [rbp+0A0h+var_D0]
0x180097744  mov     [rsp+1A0h+OpenOptions], 60h ; '`'; OpenOptions
0x18009774c  xorps   xmm0, xmm0
0x18009774f  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x180097753  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x180097757  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18009775e  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x180097762  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x180097766  mov     edx, 80000000h; DesiredAccess
0x18009776b  mov     [rbp+0A0h+ObjectAttributes.Attributes], 2C0h
0x180097772  lea     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x180097776  mov     [rsp+1A0h+ShareAccess], 1; ShareAccess
0x18009777e  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180097783  call    cs:__imp_ZwOpenFile
0x18009778a  nop     dword ptr [rax+rax+00h]
0x18009778f  mov     ebx, eax
0x180097791  test    eax, eax
0x180097793  js      loc_1800978CA
0x180097799  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x18009779d  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x1800977a1  mov     r9d, r14d; Length
0x1800977a4  mov     [rsp+1A0h+ShareAccess], 22h ; '"'; FileInformationClass
0x1800977ac  lea     rdx, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800977b0  call    cs:__imp_ZwQueryInformationFile
0x1800977b7  nop     dword ptr [rax+rax+00h]
0x1800977bc  mov     ebx, eax
0x1800977be  test    eax, eax
0x1800977c0  js      loc_1800978CA
0x1800977c6  cmp     dword ptr [rbp+0A0h+var_60+0Ch], esi
0x1800977c9  jnz     loc_18009793B
0x1800977cf  cmp     dword ptr [rbp+0A0h+var_60+8], esi
0x1800977d2  jz      loc_18009793B
0x1800977d8  mov     rax, [rbp+0A0h+FileHandle]
0x1800977dc  lea     r14d, [rsi+2]
0x1800977e0  mov     [rsp+1A0h+var_170], rax; FileHandle
0x1800977e5  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800977e9  xorps   xmm0, xmm0
0x1800977ec  mov     [rsp+1A0h+OpenOptions], 8000000h; AllocationAttributes
0x1800977f4  xor     r9d, r9d; MaximumSize
0x1800977f7  mov     [rsp+1A0h+ShareAccess], r14d; SectionPageProtection
0x1800977fc  lea     edx, [rsi+4]; DesiredAccess
0x1800977ff  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x180097806  lea     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x18009780a  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x18009780e  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x180097815  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rsi
0x180097819  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009781e  call    cs:__imp_ZwCreateSection
0x180097825  nop     dword ptr [rax+rax+00h]
0x18009782a  mov     ebx, eax
0x18009782c  test    eax, eax
0x18009782e  js      loc_1800978CA
0x180097834  mov     eax, dword ptr [rbp+0A0h+var_60+8]
0x180097837  lea     r8, [rbp+0A0h+BaseAddress]; BaseAddress
0x18009783b  mov     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x18009783f  xor     r9d, r9d; ZeroBits
0x180097842  mov     [rsp+1A0h+Win32Protect], r14d; Win32Protect
0x180097847  mov     [rsp+1A0h+AllocationType], esi; AllocationType
0x18009784b  mov     [rsp+1A0h+InheritDisposition], r14d; InheritDisposition
0x180097850  or      r14, 0FFFFFFFFFFFFFFFFh
0x180097854  mov     [rbp+0A0h+ViewSize], rax
0x180097858  mov     rdx, r14; ProcessHandle
0x18009785b  lea     rax, [rbp+0A0h+ViewSize]
0x18009785f  mov     [rbp+0A0h+BaseAddress], rsi
0x180097863  mov     [rsp+1A0h+var_170], rax; ViewSize
0x180097868  mov     qword ptr [rsp+1A0h+OpenOptions], rsi; SectionOffset
0x18009786d  mov     qword ptr [rsp+1A0h+ShareAccess], rsi; CommitSize
0x180097872  call    cs:__imp_ZwMapViewOfSection
0x180097879  nop     dword ptr [rax+rax+00h]
0x18009787e  mov     ebx, eax
0x180097880  test    eax, eax
0x180097882  js      short loc_1800978CA
0x180097884  mov     edx, dword ptr [rbp+0A0h+var_60+8]
0x180097887  lea     rax, [rbp+0A0h+var_B0]
0x18009788b  mov     rcx, [rbp+0A0h+BaseAddress]
0x18009788f  lea     r9d, [rsi+1]
0x180097893  mov     [rsp+1A0h+var_138], rsi
0x180097898  mov     qword ptr [rsp+1A0h+AllocationType], rax
0x18009789d  mov     qword ptr [rsp+1A0h+InheritDisposition], rsi
0x1800978a2  mov     byte ptr [rsp+1A0h+OpenOptions], 1
0x1800978a7  mov     byte ptr [rsp+1A0h+ShareAccess], 0Ch
0x1800978ac  call    CipValidateDataMappedFile
0x1800978b1  mov     rdx, [rbp+0A0h+BaseAddress]; BaseAddress
0x1800978b5  mov     rcx, r14; ProcessHandle
0x1800978b8  mov     ebx, eax
0x1800978ba  call    cs:__imp_ZwUnmapViewOfSection
0x1800978c1  nop     dword ptr [rax+rax+00h]
0x1800978c6  test    ebx, ebx
0x1800978c8  jns     short loc_180097932
0x1800978ca  cmp     dword ptr [rbp+0A0h+var_B0], esi
0x1800978cd  jnz     short loc_180097927
0x1800978cf  mov     rcx, [rbp+0A0h+SectionHandle]; Handle
0x1800978d3  test    rcx, rcx
0x1800978d6  jnz     short loc_180097942
0x1800978d8  mov     rcx, [rbp+0A0h+FileHandle]; Handle
0x1800978dc  test    rcx, rcx
0x1800978df  jz      short loc_1800978ED
0x1800978e1  call    cs:__imp_ZwClose
0x1800978e8  nop     dword ptr [rax+rax+00h]
0x1800978ed  lea     rcx, [rbp+0A0h+ApcState]; ApcState
0x1800978f1  call    cs:__imp_KeUnstackDetachProcess
0x1800978f8  nop     dword ptr [rax+rax+00h]
0x1800978fd  mov     eax, ebx
0x1800978ff  mov     rcx, [rbp+0A0h+var_18]
0x180097906  xor     rcx, rsp; StackCookie
0x180097909  call    __security_check_cookie
0x18009790e  lea     r11, [rsp+1A0h+var_10]
0x180097916  mov     rbx, [r11+28h]
0x18009791a  mov     rsi, [r11+30h]
0x18009791e  mov     rsp, r11
0x180097921  pop     r14
0x180097923  pop     rdi
0x180097924  pop     rbp
0x180097925  retn
0x180097927  mov     rcx, qword ptr [rbp+0A0h+var_A0]
0x18009792b  call    I_MincryptFreeChainInfo
0x180097930  jmp     short loc_1800978CF
0x180097932  mov     rax, qword ptr [rbp+0A0h+var_90+8]
0x180097936  mov     [rdi], rax
0x180097939  jmp     short loc_1800978CA
0x18009793b  mov     ebx, 0C0000020h
0x180097940  jmp     short loc_1800978CA
0x180097942  call    cs:__imp_ZwClose
0x180097949  nop     dword ptr [rax+rax+00h]
0x18009794e  jmp     short loc_1800978D8
```
