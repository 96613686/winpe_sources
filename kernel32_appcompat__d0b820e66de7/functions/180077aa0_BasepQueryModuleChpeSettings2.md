# BasepQueryModuleChpeSettings2

- ea: `0x180077aa0`
- end: `0x180077cd2`
- name: `BasepQueryModuleChpeSettings2`
- size: `562`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001cfa0`
- `0x18007771c`
- `0x180077aa0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180077b1e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180077b1e`
- `ntdll!NtClose` at `0x180077c97`
- `ntdll!NtClose` at `0x180077c97`
- `ntdll!RtlFreeUnicodeString` at `0x180077ca7`
- `ntdll!RtlFreeUnicodeString` at `0x180077ca7`
- `ntdll!NtCreateFile` at `0x180077ba9`
- `ntdll!NtCreateFile` at `0x180077ba9`

## pseudocode

```c
__int64 __fastcall BasepQueryModuleChpeSettings2(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        unsigned int *a7,
        int a8,
        __int64 a9,
        __int64 a10)
{
  unsigned int v15; // ebx
  unsigned int *v16; // r14
  _QWORD *v17; // rdi
  void *FileHandle; // [rsp+90h] [rbp-80h] BYREF
  void (__fastcall *v19)(_QWORD *, _QWORD, _QWORD, _QWORD, __int64); // [rsp+98h] [rbp-78h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-18h] BYREF
  __int64 v26; // [rsp+140h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
    return 87;
  *a1 = 0;
  FileHandle = 0;
  v22 = 0;
  LOWORD(v26) = 332;
  v19 = 0;
  IoStatusBlock = 0;
  UnicodeString = 0;
  if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(a2, &UnicodeString, 0, 0) >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0) >= 0 )
    {
      v16 = a7;
      v17 = a6;
      BasepQueryAppCompat(
        0,
        0,
        0,
        (int)FileHandle,
        0,
        a2,
        a4,
        a5,
        (int)a6,
        (int)a7,
        a8,
        a9,
        (__int64)&v21,
        a10,
        (__int64)&v20 + 4,
        (__int64)&v26,
        (__int64)&v22,
        (__int64)&v20);
      if ( v17 && *v17 )
      {
        if ( (int)BasepGetApphelpChpeModSettingsFromQueryResult2AllocProc(&v19) >= 0 )
        {
          v19(a1, (unsigned __int16)v26, *v17, *v16, a3);
          v15 = 0;
        }
        else
        {
          v15 = 127;
        }
      }
      else
      {
        v15 = 1168;
      }
    }
    else
    {
      v15 = 110;
    }
  }
  else
  {
    v15 = 3;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  RtlFreeUnicodeString(&UnicodeString);
  return v15;
}

```

## disassembly

```asm
0x180077aa0  mov     [rsp-28h+arg_8], rbx
0x180077aa5  mov     [rsp-28h+arg_10], rsi
0x180077aaa  push    rbp
0x180077aab  push    rdi
0x180077aac  push    r12
0x180077aae  push    r14
0x180077ab0  push    r15
0x180077ab2  mov     rbp, rsp
0x180077ab5  sub     rsp, 110h
0x180077abc  xorps   xmm0, xmm0
0x180077abf  xor     eax, eax
0x180077ac1  mov     r12, r9
0x180077ac4  mov     r15, r8
0x180077ac7  mov     rsi, rdx
0x180077aca  mov     rbx, rcx
0x180077acd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180077ad1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180077ad5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180077ad9  test    rcx, rcx
0x180077adc  jnz     short loc_180077AE6
0x180077ade  lea     eax, [rcx+57h]
0x180077ae1  jmp     loc_180077CB5
0x180077ae6  mov     [rcx], rax
0x180077ae9  lea     rdx, [rbp+UnicodeString]
0x180077aed  mov     [rbp+FileHandle], rax
0x180077af1  xorps   xmm1, xmm1
0x180077af4  mov     eax, 14Ch
0x180077af9  mov     [rbp+var_60], 0
0x180077b01  xor     r9d, r9d
0x180077b04  mov     word ptr [rbp+arg_0], ax
0x180077b08  xor     r8d, r8d
0x180077b0b  mov     [rbp+var_78], 0
0x180077b13  mov     rcx, rsi
0x180077b16  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180077b1a  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180077b1e  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180077b25  nop     dword ptr [rax+rax+00h]
0x180077b2a  test    eax, eax
0x180077b2c  jns     short loc_180077B38
0x180077b2e  mov     ebx, 3
0x180077b33  jmp     loc_180077C8E
0x180077b38  mov     [rsp+110h+EaLength], 0; EaLength
0x180077b40  lea     rax, [rbp+UnicodeString]
0x180077b44  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x180077b4d  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180077b51  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x180077b59  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180077b5d  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x180077b65  lea     rcx, [rbp+FileHandle]; FileHandle
0x180077b69  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x180077b71  xorps   xmm0, xmm0
0x180077b74  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180077b7c  mov     edx, 80100080h; DesiredAccess
0x180077b81  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x180077b8a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180077b91  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180077b99  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180077ba0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180077ba4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180077ba9  call    cs:__imp_NtCreateFile
0x180077bb0  nop     dword ptr [rax+rax+00h]
0x180077bb5  test    eax, eax
0x180077bb7  jns     short loc_180077BC3
0x180077bb9  mov     ebx, 6Eh ; 'n'
0x180077bbe  jmp     loc_180077C8E
0x180077bc3  mov     r14, [rbp+arg_30]
0x180077bc7  lea     rax, [rbp+var_70]
0x180077bcb  mov     rdi, [rbp+arg_28]
0x180077bcf  xor     r8d, r8d; int
0x180077bd2  mov     r9, [rbp+FileHandle]; int
0x180077bd6  xor     edx, edx; int
0x180077bd8  mov     [rsp+110h+var_88], rax; __int64
0x180077be0  xor     ecx, ecx; int
0x180077be2  lea     rax, [rbp+var_60]
0x180077be6  mov     [rsp+110h+var_90], rax; __int64
0x180077bee  lea     rax, [rbp+arg_0]
0x180077bf2  mov     [rsp+110h+var_98], rax; __int64
0x180077bf7  lea     rax, [rbp+var_70+4]
0x180077bfb  mov     [rsp+110h+var_A0], rax; __int64
0x180077c00  mov     rax, [rbp+arg_48]
0x180077c04  mov     [rsp+110h+var_A8], rax; __int64
0x180077c09  lea     rax, [rbp+var_68]
0x180077c0d  mov     [rsp+110h+var_B0], rax; __int64
0x180077c12  mov     rax, [rbp+arg_40]
0x180077c16  mov     [rsp+110h+var_B8], rax; __int64
0x180077c1b  mov     rax, qword ptr [rbp+arg_38]
0x180077c1f  mov     qword ptr [rsp+110h+EaLength], rax; int
0x180077c24  mov     rax, [rbp+arg_20]
0x180077c28  mov     [rsp+110h+EaBuffer], r14; int
0x180077c2d  mov     qword ptr [rsp+110h+CreateOptions], rdi; int
0x180077c32  mov     qword ptr [rsp+110h+CreateDisposition], rax; __int64
0x180077c37  mov     qword ptr [rsp+110h+ShareAccess], r12; __int64
0x180077c3c  mov     qword ptr [rsp+110h+FileAttributes], rsi; __int64
0x180077c41  mov     [rsp+110h+AllocationSize], r8; HANDLE
0x180077c46  call    BasepQueryAppCompat
0x180077c4b  test    rdi, rdi
0x180077c4e  jz      short loc_180077C89
0x180077c50  cmp     qword ptr [rdi], 0
0x180077c54  jz      short loc_180077C89
0x180077c56  lea     rcx, [rbp+var_78]
0x180077c5a  call    BasepGetApphelpChpeModSettingsFromQueryResult2AllocProc
0x180077c5f  test    eax, eax
0x180077c61  jns     short loc_180077C6A
0x180077c63  mov     ebx, 7Fh
0x180077c68  jmp     short loc_180077C8E
0x180077c6a  mov     r9d, [r14]
0x180077c6d  mov     rcx, rbx
0x180077c70  mov     r8, [rdi]
0x180077c73  movzx   edx, word ptr [rbp+arg_0]
0x180077c77  mov     rax, [rbp+var_78]
0x180077c7b  mov     [rsp+110h+AllocationSize], r15
0x180077c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c85  xor     ebx, ebx
0x180077c87  jmp     short loc_180077C8E
0x180077c89  mov     ebx, 490h
0x180077c8e  mov     rcx, [rbp+FileHandle]; Handle
0x180077c92  test    rcx, rcx
0x180077c95  jz      short loc_180077CA3
0x180077c97  call    cs:__imp_NtClose
0x180077c9e  nop     dword ptr [rax+rax+00h]
0x180077ca3  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180077ca7  call    cs:__imp_RtlFreeUnicodeString
0x180077cae  nop     dword ptr [rax+rax+00h]
0x180077cb3  mov     eax, ebx
0x180077cb5  lea     r11, [rsp+110h+var_s0]
0x180077cbd  mov     rbx, [r11+38h]
0x180077cc1  mov     rsi, [r11+40h]
0x180077cc5  mov     rsp, r11
0x180077cc8  pop     r15
0x180077cca  pop     r14
0x180077ccc  pop     r12
0x180077cce  pop     rdi
0x180077ccf  pop     rbp
0x180077cd0  retn
```
