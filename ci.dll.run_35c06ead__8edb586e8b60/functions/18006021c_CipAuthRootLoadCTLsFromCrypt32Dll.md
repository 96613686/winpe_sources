# CipAuthRootLoadCTLsFromCrypt32Dll

- ea: `0x18006021c`
- end: `0x1800604d8`
- name: `CipAuthRootLoadCTLsFromCrypt32Dll`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dd30c`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18006021c`
- `0x1800a0654`
- `0x1800a0af0`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x18006034f`
- `ntoskrnl!FsRtlGetFileSize` at `0x18006034f`
- `ntoskrnl!ExAllocatePool2` at `0x18006042d`
- `ntoskrnl!ExAllocatePool2` at `0x18006042d`
- `ntoskrnl!ZwClose` at `0x180060472`
- `ntoskrnl!ZwClose` at `0x180060472`
- `ntoskrnl!ObfDereferenceObject` at `0x18006045c`
- `ntoskrnl!ObfDereferenceObject` at `0x18006045c`
- `ntoskrnl!ZwCreateFile` at `0x1800602ef`
- `ntoskrnl!ZwCreateFile` at `0x1800602ef`
- `ntoskrnl!IoFileObjectType` at `0x180060305`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006032e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006032e`
- `ntoskrnl!LdrResSearchResource` at `0x1800603f7`
- `ntoskrnl!LdrResSearchResource` at `0x1800603f7`

## string_xrefs

- `0x180060258`: `\SystemRoot\SystemResources\crypt32.dll.mun`

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
0x18006021c  mov     [rsp-8+arg_10], rbx
0x180060221  mov     [rsp-8+arg_18], rsi
0x180060226  push    rbp
0x180060227  push    rdi
0x180060228  push    r12
0x18006022a  push    r14
0x18006022c  push    r15
0x18006022e  lea     rbp, [rsp-30h]
0x180060233  sub     rsp, 130h
0x18006023a  mov     rax, cs:__security_cookie
0x180060241  xor     rax, rsp
0x180060244  mov     [rbp+50h+var_28], rax
0x180060248  xor     r12d, r12d
0x18006024b  mov     [rbp+50h+var_C0], 580056h
0x180060253  mov     [rsp+150h+EaLength], r12d; EaLength
0x180060258  lea     rax, aSystemrootSyst_4; "\\SystemRoot\\SystemResources\\crypt32."...
0x18006025f  xorps   xmm0, xmm0
0x180060262  mov     [rsp+150h+EaBuffer], r12; EaBuffer
0x180060267  mov     [rsp+150h+CreateOptions], 40h ; '@'; CreateOptions
0x18006026f  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x180060273  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x18006027b  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x18006027f  mov     [rbp+50h+var_B8], rax
0x180060283  mov     r14, rdx
0x180060286  mov     [rsp+150h+ShareAccess], 1; ShareAccess
0x18006028e  lea     rax, [rbp+50h+var_C0]
0x180060292  mov     r15, rcx
0x180060295  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x18006029d  mov     edx, 80000000h; DesiredAccess
0x1800602a2  mov     [rsp+150h+AllocationSize], r12; AllocationSize
0x1800602a7  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1800602ac  mov     [rsp+150h+var_E0], r12
0x1800602b1  mov     esi, r12d
0x1800602b4  mov     [rsp+150h+FileHandle], r12
0x1800602b9  mov     qword ptr [rbp+50h+FileSize], r12
0x1800602bd  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1800602c1  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x1800602c9  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 240h
0x1800602d1  movups  xmmword ptr [rbp+50h+var_70], xmm0
0x1800602d5  mov     [rsp+150h+Src], r12
0x1800602da  movups  [rbp+50h+var_60], xmm0
0x1800602de  mov     [rbp+50h+ObjectAttributes.RootDirectory], r12
0x1800602e2  movups  [rbp+50h+var_50], xmm0
0x1800602e6  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1800602ea  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800602ef  call    cs:__imp_ZwCreateFile
0x1800602f6  nop     dword ptr [rax+rax+00h]
0x1800602fb  mov     ebx, eax
0x1800602fd  test    eax, eax
0x1800602ff  js      loc_180060468
0x180060305  mov     r8, cs:__imp_IoFileObjectType
0x18006030c  lea     rax, [rbp+50h+Object]
0x180060310  mov     rcx, [rsp+150h+FileHandle]; Handle
0x180060315  lea     edx, [r12+1]; DesiredAccess
0x18006031a  mov     qword ptr [rsp+150h+FileAttributes], r12; HandleInformation
0x18006031f  xor     r9d, r9d; AccessMode
0x180060322  mov     [rbp+50h+Object], r12
0x180060326  mov     r8, [r8]; ObjectType
0x180060329  mov     [rsp+150h+AllocationSize], rax; Object
0x18006032e  call    cs:__imp_ObReferenceObjectByHandle
0x180060335  nop     dword ptr [rax+rax+00h]
0x18006033a  mov     rdi, [rbp+50h+Object]
0x18006033e  mov     ebx, eax
0x180060340  test    eax, eax
0x180060342  js      loc_180060446
0x180060348  lea     rdx, [rbp+50h+FileSize]; FileSize
0x18006034c  mov     rcx, rdi; FileObject
0x18006034f  call    cs:__imp_FsRtlGetFileSize
0x180060356  nop     dword ptr [rax+rax+00h]
0x18006035b  mov     ebx, eax
0x18006035d  test    eax, eax
0x18006035f  js      loc_180060454
0x180060365  mov     r8, qword ptr [rbp+50h+FileSize]; int
0x180060369  mov     eax, 0FFFFFFFFh
0x18006036e  cmp     r8, rax
0x180060371  ja      loc_1800604CE
0x180060377  lea     rax, [rsp+150h+var_E0]
0x18006037c  mov     r9b, 1; int
0x18006037f  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x180060384  xor     edx, edx; int
0x180060386  lea     rax, [rbp+50h+var_70]
0x18006038a  mov     rcx, rdi; int
0x18006038d  mov     [rsp+150h+AllocationSize], rax; PHANDLE
0x180060392  call    CiReadFileOpen
0x180060397  mov     rsi, [rsp+150h+var_E0]
0x18006039c  mov     ebx, eax
0x18006039e  test    eax, eax
0x1800603a0  js      loc_180060446
0x1800603a6  mov     qword ptr [rsp+150h+CreateDisposition], r12
0x1800603ab  lea     rax, aAuthrootstl; "AUTHROOTSTL"
0x1800603b2  mov     [rbp+50h+var_40], rax
0x1800603b6  lea     r8d, [r12+3]
0x1800603bb  lea     rax, [rsp+150h+Size]
0x1800603c0  mov     qword ptr [rsp+150h+ShareAccess], r12
0x1800603c5  mov     qword ptr [rsp+150h+FileAttributes], rax
0x1800603ca  lea     rdx, [rbp+50h+var_40]
0x1800603ce  lea     rax, [rsp+150h+Src]
0x1800603d3  mov     [rbp+50h+var_38], 3FCh
0x1800603db  mov     r9d, 1210h
0x1800603e1  mov     [rsp+150h+AllocationSize], rax
0x1800603e6  mov     rcx, rsi
0x1800603e9  mov     [rbp+50h+var_30], r12
0x1800603ed  mov     [rsp+150h+Src], r12
0x1800603f2  mov     [rsp+150h+Size], r12
0x1800603f7  call    cs:__imp_LdrResSearchResource
0x1800603fe  nop     dword ptr [rax+rax+00h]
0x180060403  mov     ebx, eax
0x180060405  test    eax, eax
0x180060407  js      short loc_180060446
0x180060409  mov     rcx, [rsp+150h+Size]
0x18006040e  mov     edx, 0FFFFFFFEh
0x180060413  lea     rax, [rcx-1]
0x180060417  cmp     rax, rdx
0x18006041a  ja      loc_1800604C4
0x180060420  mov     edx, ecx
0x180060422  mov     r8d, 63734943h
0x180060428  mov     ecx, 102h
0x18006042d  call    cs:__imp_ExAllocatePool2
0x180060434  nop     dword ptr [rax+rax+00h]
0x180060439  mov     [r15], rax
0x18006043c  test    rax, rax
0x18006043f  jnz     short loc_1800604A9
0x180060441  mov     ebx, 0C0000017h
0x180060446  test    rsi, rsi
0x180060449  jz      short loc_180060454
0x18006044b  lea     rcx, [rbp+50h+var_70]
0x18006044f  call    CiReadFileClose
0x180060454  test    rdi, rdi
0x180060457  jz      short loc_180060468
0x180060459  mov     rcx, rdi; Object
0x18006045c  call    cs:__imp_ObfDereferenceObject
0x180060463  nop     dword ptr [rax+rax+00h]
0x180060468  mov     rcx, [rsp+150h+FileHandle]; Handle
0x18006046d  test    rcx, rcx
0x180060470  jz      short loc_18006047E
0x180060472  call    cs:__imp_ZwClose
0x180060479  nop     dword ptr [rax+rax+00h]
0x18006047e  mov     eax, ebx
0x180060480  mov     rcx, [rbp+50h+var_28]
0x180060484  xor     rcx, rsp; StackCookie
0x180060487  call    __security_check_cookie
0x18006048c  lea     r11, [rsp+150h+var_20]
0x180060494  mov     rbx, [r11+40h]
0x180060498  mov     rsi, [r11+48h]
0x18006049c  mov     rsp, r11
0x18006049f  pop     r15
0x1800604a1  pop     r14
0x1800604a3  pop     r12
0x1800604a5  pop     rdi
0x1800604a6  pop     rbp
0x1800604a7  retn
0x1800604a9  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x1800604ae  mov     rcx, rax; void *
0x1800604b1  mov     rdx, [rsp+150h+Src]; Src
0x1800604b6  call    memmove
0x1800604bb  mov     eax, dword ptr [rsp+150h+Size]
0x1800604bf  mov     [r14], eax
0x1800604c2  jmp     short loc_180060446
0x1800604c4  mov     ebx, 0C000007Bh
0x1800604c9  jmp     loc_180060446
0x1800604ce  mov     ebx, 0C000007Bh
0x1800604d3  jmp     loc_180060454
```
