# LuafvCreateUserStorePath

- ea: `0x140018030`
- end: `0x14001819b`
- name: `LuafvCreateUserStorePath`
- size: `363`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, void *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400175f8`
- `0x140019ac0`

## callees

- `0x14001758c`
- `0x140018030`
- `0x14001dd40`

## import_xrefs

- `FLTMGR!FltClose` at `0x140018139`
- `FLTMGR!FltClose` at `0x140018139`
- `FLTMGR!FltCreateFileEx2` at `0x140018123`
- `FLTMGR!FltCreateFileEx2` at `0x140018123`

## pseudocode

```c
__int64 __fastcall LuafvCreateUserStorePath(PFLT_INSTANCE Instance, void *a2, __int64 a3)
{
  struct _ACL *v3; // rbx
  ULONG Flags; // ecx
  struct _UNICODE_STRING *v8; // rax
  NTSTATUS v9; // edi
  __int64 result; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  struct _ACL *v13; // [rsp+F0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v3 = 0;
  v13 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( *(_BYTE *)(a3 + 80) )
  {
    Flags = 257;
  }
  else
  {
    result = LuafvCreateUserStoreSecurityDescriptor(*(_QWORD *)(a3 + 16), &v13);
    if ( (int)result < 0 )
      return result;
    v3 = v13;
    Flags = 256;
  }
  if ( a2 )
    v8 = (struct _UNICODE_STRING *)(*(_QWORD *)(a3 + 16) + 88LL);
  else
    v8 = (struct _UNICODE_STRING *)(a3 + 40);
  ObjectAttributes.ObjectName = v8;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v3;
  ObjectAttributes.SecurityQualityOfService = 0;
  v9 = FltCreateFileEx2(
         LuafvDriverData,
         Instance,
         &FileHandle,
         0,
         0x1C0000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x10u,
         3u,
         3u,
         0x21u,
         0,
         0,
         Flags,
         0);
  if ( v9 >= 0 )
    FltClose(FileHandle);
  if ( v3 )
    LuafvFreePool(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140018030  mov     [rsp-8+arg_0], rbx
0x140018035  mov     [rsp-8+arg_8], rsi
0x14001803a  push    rbp
0x14001803b  push    rdi
0x14001803c  push    r14
0x14001803e  lea     rbp, [rsp-47h]
0x140018043  sub     rsp, 0C0h
0x14001804a  xorps   xmm0, xmm0
0x14001804d  mov     [rbp+57h+FileHandle], 0
0x140018055  xor     ebx, ebx
0x140018057  xor     eax, eax
0x140018059  mov     rdi, r8
0x14001805c  mov     rsi, rdx
0x14001805f  mov     r14, rcx
0x140018062  mov     [rbp+57h+arg_10], rbx
0x140018066  movups  xmmword ptr [rbp+57h+var_40.ObjectName], xmm0
0x14001806a  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x14001806e  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x140018072  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140018076  cmp     [r8+50h], al
0x14001807a  jz      loc_140018172
0x140018080  mov     ecx, 101h
0x140018085  test    rsi, rsi
0x140018088  jnz     loc_140018165
0x14001808e  lea     rax, [rdi+28h]
0x140018092  mov     [rsp+0D0h+DriverContext], 0; DriverContext
0x14001809b  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14001809f  mov     [rsp+0D0h+Flags], ecx; Flags
0x1400180a3  xor     r9d, r9d; FileObject
0x1400180a6  mov     rcx, cs:LuafvDriverData; Filter
0x1400180ad  mov     rdx, r14; Instance
0x1400180b0  mov     [rsp+0D0h+EaLength], 0; EaLength
0x1400180b8  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x1400180c1  mov     [rsp+0D0h+CreateOptions], 21h ; '!'; CreateOptions
0x1400180c9  mov     [rbp+57h+var_40.ObjectName], rax
0x1400180cd  mov     eax, 3
0x1400180d2  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x1400180d6  mov     [rsp+0D0h+ShareAccess], eax; ShareAccess
0x1400180da  lea     rax, [rbp+57h+var_50]
0x1400180de  mov     [rsp+0D0h+FileAttributes], 10h; FileAttributes
0x1400180e6  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x1400180ef  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x1400180f4  lea     rax, [rbp+57h+var_40]
0x1400180f8  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x1400180fd  mov     [rsp+0D0h+DesiredAccess], 1C0000h; DesiredAccess
0x140018105  mov     [rbp+57h+var_40.Length], 30h ; '0'
0x14001810c  mov     [rbp+57h+var_40.RootDirectory], rsi
0x140018110  mov     [rbp+57h+var_40.Attributes], 240h
0x140018117  mov     [rbp+57h+var_40.SecurityDescriptor], rbx
0x14001811b  mov     [rbp+57h+var_40.SecurityQualityOfService], 0
0x140018123  call    cs:__imp_FltCreateFileEx2
0x14001812a  nop     dword ptr [rax+rax+00h]
0x14001812f  mov     edi, eax
0x140018131  test    eax, eax
0x140018133  js      short loc_140018145
0x140018135  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140018139  call    cs:__imp_FltClose
0x140018140  nop     dword ptr [rax+rax+00h]
0x140018145  test    rbx, rbx
0x140018148  jnz     short loc_140018191
0x14001814a  mov     eax, edi
0x14001814c  lea     r11, [rsp+0D0h+var_10]
0x140018154  mov     rbx, [r11+20h]
0x140018158  mov     rsi, [r11+28h]
0x14001815c  mov     rsp, r11
0x14001815f  pop     r14
0x140018161  pop     rdi
0x140018162  pop     rbp
0x140018163  retn
0x140018165  mov     rax, [rdi+10h]
0x140018169  add     rax, 58h ; 'X'
0x14001816d  jmp     loc_140018092
0x140018172  mov     rcx, [r8+10h]
0x140018176  lea     rdx, [rbp+57h+arg_10]
0x14001817a  call    LuafvCreateUserStoreSecurityDescriptor
0x14001817f  test    eax, eax
0x140018181  js      short loc_14001814C
0x140018183  mov     rbx, [rbp+57h+arg_10]
0x140018187  mov     ecx, 100h
0x14001818c  jmp     loc_140018085
0x140018191  mov     rcx, rbx
0x140018194  call    LuafvFreePool
0x140018199  jmp     short loc_14001814A
```
