# CipAuthRootLoadCTLsFromCrypt32Dll

- ea: `0x18006027c`
- end: `0x180060538`
- name: `CipAuthRootLoadCTLsFromCrypt32Dll`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dd2fc`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18006027c`
- `0x18009b314`
- `0x18009b7b0`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x1800603af`
- `ntoskrnl!FsRtlGetFileSize` at `0x1800603af`
- `ntoskrnl!ExAllocatePool2` at `0x18006048d`
- `ntoskrnl!ExAllocatePool2` at `0x18006048d`
- `ntoskrnl!ZwClose` at `0x1800604d2`
- `ntoskrnl!ZwClose` at `0x1800604d2`
- `ntoskrnl!ObfDereferenceObject` at `0x1800604bc`
- `ntoskrnl!ObfDereferenceObject` at `0x1800604bc`
- `ntoskrnl!ZwCreateFile` at `0x18006034f`
- `ntoskrnl!ZwCreateFile` at `0x18006034f`
- `ntoskrnl!IoFileObjectType` at `0x180060365`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006038e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006038e`
- `ntoskrnl!LdrResSearchResource` at `0x180060457`
- `ntoskrnl!LdrResSearchResource` at `0x180060457`

## string_xrefs

- `0x1800602b8`: `\SystemRoot\SystemResources\crypt32.dll.mun`

## pseudocode

```c
__int64 __fastcall CipAuthRootLoadCTLsFromCrypt32Dll(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rsi
  NTSTATUS v5; // ebx
  NTSTATUS v6; // eax
  PVOID v7; // rdi
  int v8; // r9d
  int FileOpen; // eax
  void *Pool2; // rax
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v18[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  void *v21[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]
  __int128 v23; // [rsp+100h] [rbp+0h]
  _QWORD v24[3]; // [rsp+110h] [rbp+10h] BYREF

  v18[0] = 5767254;
  v18[1] = L"\\SystemRoot\\SystemResources\\crypt32.dll.mun";
  v14 = 0;
  v4 = 0;
  FileHandle = 0;
  FileSize.QuadPart = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)v21 = 0;
  Src = 0;
  v22 = 0;
  ObjectAttributes.RootDirectory = 0;
  v23 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x40u, 0, 0);
  if ( v5 < 0 )
    goto LABEL_14;
  Object = 0;
  v6 = ObReferenceObjectByHandle(FileHandle, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  v7 = Object;
  v5 = v6;
  if ( v6 < 0 )
    goto LABEL_10;
  v5 = FsRtlGetFileSize((PFILE_OBJECT)Object, &FileSize);
  if ( v5 >= 0 )
  {
    if ( FileSize.QuadPart <= 0xFFFFFFFFuLL )
    {
      LOBYTE(v8) = 1;
      FileOpen = CiReadFileOpen((int)v7, 0, FileSize.LowPart, v8, v21, (__int64)&v14);
      v4 = v14;
      v5 = FileOpen;
      if ( FileOpen >= 0 )
      {
        v24[0] = L"AUTHROOTSTL";
        v24[1] = 1020;
        v24[2] = 0;
        Src = 0;
        Size = 0;
        v5 = LdrResSearchResource(v14, v24, 3, 4624, &Src, &Size, 0, 0);
        if ( v5 >= 0 )
        {
          if ( Size - 1 > 0xFFFFFFFE )
          {
            v5 = -1073741701;
          }
          else
          {
            Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1668499779);
            *a1 = Pool2;
            if ( Pool2 )
            {
              memmove(Pool2, Src, (unsigned int)Size);
              *a2 = Size;
            }
            else
            {
              v5 = -1073741801;
            }
          }
        }
      }
LABEL_10:
      if ( v4 )
        CiReadFileClose(v21);
      goto LABEL_12;
    }
    v5 = -1073741701;
  }
LABEL_12:
  if ( v7 )
    ObfDereferenceObject(v7);
LABEL_14:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006027c  mov     [rsp-8+arg_10], rbx
0x180060281  mov     [rsp-8+arg_18], rsi
0x180060286  push    rbp
0x180060287  push    rdi
0x180060288  push    r12
0x18006028a  push    r14
0x18006028c  push    r15
0x18006028e  lea     rbp, [rsp-30h]
0x180060293  sub     rsp, 130h
0x18006029a  mov     rax, cs:__security_cookie
0x1800602a1  xor     rax, rsp
0x1800602a4  mov     [rbp+50h+var_28], rax
0x1800602a8  xor     r12d, r12d
0x1800602ab  mov     [rbp+50h+var_C0], 580056h
0x1800602b3  mov     [rsp+150h+EaLength], r12d; EaLength
0x1800602b8  lea     rax, aSystemrootSyst_4; "\\SystemRoot\\SystemResources\\crypt32."...
0x1800602bf  xorps   xmm0, xmm0
0x1800602c2  mov     [rsp+150h+EaBuffer], r12; EaBuffer
0x1800602c7  mov     [rsp+150h+CreateOptions], 40h ; '@'; CreateOptions
0x1800602cf  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1800602d3  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x1800602db  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1800602df  mov     [rbp+50h+var_B8], rax
0x1800602e3  mov     r14, rdx
0x1800602e6  mov     [rsp+150h+ShareAccess], 1; ShareAccess
0x1800602ee  lea     rax, [rbp+50h+var_C0]
0x1800602f2  mov     r15, rcx
0x1800602f5  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1800602fd  mov     edx, 80000000h; DesiredAccess
0x180060302  mov     [rsp+150h+AllocationSize], r12; AllocationSize
0x180060307  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x18006030c  mov     [rsp+150h+var_E0], r12
0x180060311  mov     esi, r12d
0x180060314  mov     [rsp+150h+FileHandle], r12
0x180060319  mov     qword ptr [rbp+50h+FileSize], r12
0x18006031d  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x180060321  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x180060329  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 240h
0x180060331  movups  xmmword ptr [rbp+50h+var_70], xmm0
0x180060335  mov     [rsp+150h+Src], r12
0x18006033a  movups  [rbp+50h+var_60], xmm0
0x18006033e  mov     [rbp+50h+ObjectAttributes.RootDirectory], r12
0x180060342  movups  [rbp+50h+var_50], xmm0
0x180060346  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x18006034a  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006034f  call    cs:__imp_ZwCreateFile
0x180060356  nop     dword ptr [rax+rax+00h]
0x18006035b  mov     ebx, eax
0x18006035d  test    eax, eax
0x18006035f  js      loc_1800604C8
0x180060365  mov     r8, cs:__imp_IoFileObjectType
0x18006036c  lea     rax, [rbp+50h+Object]
0x180060370  mov     rcx, [rsp+150h+FileHandle]; Handle
0x180060375  lea     edx, [r12+1]; DesiredAccess
0x18006037a  mov     qword ptr [rsp+150h+FileAttributes], r12; HandleInformation
0x18006037f  xor     r9d, r9d; AccessMode
0x180060382  mov     [rbp+50h+Object], r12
0x180060386  mov     r8, [r8]; ObjectType
0x180060389  mov     [rsp+150h+AllocationSize], rax; Object
0x18006038e  call    cs:__imp_ObReferenceObjectByHandle
0x180060395  nop     dword ptr [rax+rax+00h]
0x18006039a  mov     rdi, [rbp+50h+Object]
0x18006039e  mov     ebx, eax
0x1800603a0  test    eax, eax
0x1800603a2  js      loc_1800604A6
0x1800603a8  lea     rdx, [rbp+50h+FileSize]; FileSize
0x1800603ac  mov     rcx, rdi; FileObject
0x1800603af  call    cs:__imp_FsRtlGetFileSize
0x1800603b6  nop     dword ptr [rax+rax+00h]
0x1800603bb  mov     ebx, eax
0x1800603bd  test    eax, eax
0x1800603bf  js      loc_1800604B4
0x1800603c5  mov     r8, qword ptr [rbp+50h+FileSize]; int
0x1800603c9  mov     eax, 0FFFFFFFFh
0x1800603ce  cmp     r8, rax
0x1800603d1  ja      loc_18006052E
0x1800603d7  lea     rax, [rsp+150h+var_E0]
0x1800603dc  mov     r9b, 1; int
0x1800603df  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x1800603e4  xor     edx, edx; int
0x1800603e6  lea     rax, [rbp+50h+var_70]
0x1800603ea  mov     rcx, rdi; int
0x1800603ed  mov     [rsp+150h+AllocationSize], rax; PHANDLE
0x1800603f2  call    CiReadFileOpen
0x1800603f7  mov     rsi, [rsp+150h+var_E0]
0x1800603fc  mov     ebx, eax
0x1800603fe  test    eax, eax
0x180060400  js      loc_1800604A6
0x180060406  mov     qword ptr [rsp+150h+CreateDisposition], r12
0x18006040b  lea     rax, aAuthrootstl; "AUTHROOTSTL"
0x180060412  mov     [rbp+50h+var_40], rax
0x180060416  lea     r8d, [r12+3]
0x18006041b  lea     rax, [rsp+150h+Size]
0x180060420  mov     qword ptr [rsp+150h+ShareAccess], r12
0x180060425  mov     qword ptr [rsp+150h+FileAttributes], rax
0x18006042a  lea     rdx, [rbp+50h+var_40]
0x18006042e  lea     rax, [rsp+150h+Src]
0x180060433  mov     [rbp+50h+var_38], 3FCh
0x18006043b  mov     r9d, 1210h
0x180060441  mov     [rsp+150h+AllocationSize], rax
0x180060446  mov     rcx, rsi
0x180060449  mov     [rbp+50h+var_30], r12
0x18006044d  mov     [rsp+150h+Src], r12
0x180060452  mov     [rsp+150h+Size], r12
0x180060457  call    cs:__imp_LdrResSearchResource
0x18006045e  nop     dword ptr [rax+rax+00h]
0x180060463  mov     ebx, eax
0x180060465  test    eax, eax
0x180060467  js      short loc_1800604A6
0x180060469  mov     rcx, [rsp+150h+Size]
0x18006046e  mov     edx, 0FFFFFFFEh
0x180060473  lea     rax, [rcx-1]
0x180060477  cmp     rax, rdx
0x18006047a  ja      loc_180060524
0x180060480  mov     edx, ecx
0x180060482  mov     r8d, 63734943h
0x180060488  mov     ecx, 102h
0x18006048d  call    cs:__imp_ExAllocatePool2
0x180060494  nop     dword ptr [rax+rax+00h]
0x180060499  mov     [r15], rax
0x18006049c  test    rax, rax
0x18006049f  jnz     short loc_180060509
0x1800604a1  mov     ebx, 0C0000017h
0x1800604a6  test    rsi, rsi
0x1800604a9  jz      short loc_1800604B4
0x1800604ab  lea     rcx, [rbp+50h+var_70]
0x1800604af  call    CiReadFileClose
0x1800604b4  test    rdi, rdi
0x1800604b7  jz      short loc_1800604C8
0x1800604b9  mov     rcx, rdi; Object
0x1800604bc  call    cs:__imp_ObfDereferenceObject
0x1800604c3  nop     dword ptr [rax+rax+00h]
0x1800604c8  mov     rcx, [rsp+150h+FileHandle]; Handle
0x1800604cd  test    rcx, rcx
0x1800604d0  jz      short loc_1800604DE
0x1800604d2  call    cs:__imp_ZwClose
0x1800604d9  nop     dword ptr [rax+rax+00h]
0x1800604de  mov     eax, ebx
0x1800604e0  mov     rcx, [rbp+50h+var_28]
0x1800604e4  xor     rcx, rsp; StackCookie
0x1800604e7  call    __security_check_cookie
0x1800604ec  lea     r11, [rsp+150h+var_20]
0x1800604f4  mov     rbx, [r11+40h]
0x1800604f8  mov     rsi, [r11+48h]
0x1800604fc  mov     rsp, r11
0x1800604ff  pop     r15
0x180060501  pop     r14
0x180060503  pop     r12
0x180060505  pop     rdi
0x180060506  pop     rbp
0x180060507  retn
0x180060509  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18006050e  mov     rcx, rax; void *
0x180060511  mov     rdx, [rsp+150h+Src]; Src
0x180060516  call    memmove
0x18006051b  mov     eax, dword ptr [rsp+150h+Size]
0x18006051f  mov     [r14], eax
0x180060522  jmp     short loc_1800604A6
0x180060524  mov     ebx, 0C000007Bh
0x180060529  jmp     loc_1800604A6
0x18006052e  mov     ebx, 0C000007Bh
0x180060533  jmp     loc_1800604B4
```
