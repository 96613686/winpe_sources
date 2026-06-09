# BasepQueryModuleChpeSettings

- ea: `0x18006fc40`
- end: `0x18006fe7e`
- name: `BasepQueryModuleChpeSettings`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001f130`
- `0x18002eafc`
- `0x18006fc40`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x18006fe16`
- `ntdll!RtlDecodeSystemPointer` at `0x18006fe16`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006fcd9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006fcd9`
- `ntdll!NtClose` at `0x18006fe4e`
- `ntdll!NtClose` at `0x18006fe4e`
- `ntdll!RtlFreeUnicodeString` at `0x18006fe58`
- `ntdll!RtlFreeUnicodeString` at `0x18006fe58`
- `ntdll!NtCreateFile` at `0x18006fd58`
- `ntdll!NtCreateFile` at `0x18006fd58`

## pseudocode

```c
__int64 __fastcall BasepQueryModuleChpeSettings(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int *a8,
        int a9,
        __int64 a10,
        __int64 a11)
{
  unsigned int v14; // ebx
  char v15; // al
  unsigned int *v16; // r14
  _QWORD *v17; // rbx
  PVOID v18; // rax
  void *FileHandle; // [rsp+90h] [rbp-80h] BYREF
  __int64 v21; // [rsp+98h] [rbp-78h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-68h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v27; // [rsp+140h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  if ( !a1 || a2 != 32 )
    return 87;
  *(_QWORD *)a1 = 0;
  v14 = 3;
  *(_DWORD *)(a1 + 12) = 0;
  v15 = *(_BYTE *)(a1 + 21) & 0xF3;
  *(_DWORD *)(a1 + 8) = 0x80000000;
  *(_DWORD *)(a1 + 16) = 0x2000000;
  *(_BYTE *)(a1 + 21) = v15 | 3;
  *(_BYTE *)(a1 + 20) = 108;
  *(_QWORD *)(a1 + 24) = 0;
  FileHandle = 0;
  v23 = 0;
  LOWORD(v27) = 332;
  IoStatusBlock = 0;
  UnicodeString = 0;
  if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0) >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0) >= 0 )
    {
      v16 = a8;
      v17 = a7;
      BasepQueryAppCompat(
        0,
        0,
        0,
        (int)FileHandle,
        0,
        a3,
        a5,
        a6,
        (int)a7,
        (int)a8,
        a9,
        a10,
        (__int64)&v22,
        a11,
        (__int64)&v21 + 4,
        (__int64)&v27,
        (__int64)&v23,
        (__int64)&v21);
      if ( v17 && *v17 )
      {
        if ( (int)BasepInitializeApphelpGlobals() < 0 || (v18 = RtlDecodeSystemPointer(qword_1800B6060)) == 0 )
        {
          v14 = 127;
          goto LABEL_12;
        }
        ((void (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, __int64))v18)(
          a1,
          32,
          (unsigned __int16)v27,
          *v17,
          *v16,
          a4);
      }
      v14 = 0;
    }
    else
    {
      v14 = 110;
    }
  }
LABEL_12:
  if ( FileHandle )
    NtClose(FileHandle);
  RtlFreeUnicodeString(&UnicodeString);
  return v14;
}

```

## disassembly

```asm
0x18006fc40  push    rbp
0x18006fc42  push    rbx
0x18006fc43  push    rsi
0x18006fc44  push    rdi
0x18006fc45  push    r14
0x18006fc47  push    r15
0x18006fc49  lea     rbp, [rsp+8]
0x18006fc4e  sub     rsp, 108h
0x18006fc55  xorps   xmm0, xmm0
0x18006fc58  xor     eax, eax
0x18006fc5a  mov     r15, r9
0x18006fc5d  mov     rsi, r8
0x18006fc60  mov     rdi, rcx
0x18006fc63  movups  xmmword ptr [rbp+20h+ObjectAttributes.ObjectName], xmm0
0x18006fc67  movups  xmmword ptr [rbp+20h+ObjectAttributes+1Ch], xmm0
0x18006fc6b  movups  xmmword ptr [rbp+20h+ObjectAttributes.Length], xmm0
0x18006fc6f  test    rcx, rcx
0x18006fc72  jz      loc_18006FE69
0x18006fc78  cmp     edx, 20h ; ' '
0x18006fc7b  jnz     loc_18006FE69
0x18006fc81  mov     [rcx], rax
0x18006fc84  lea     ebx, [rdx-1Dh]
0x18006fc87  mov     [rcx+0Ch], eax
0x18006fc8a  lea     rdx, [rbp+20h+UnicodeString]
0x18006fc8e  mov     al, [rcx+15h]
0x18006fc91  xorps   xmm1, xmm1
0x18006fc94  and     al, 0F3h
0x18006fc96  mov     dword ptr [rcx+8], 80000000h
0x18006fc9d  or      al, bl
0x18006fc9f  mov     dword ptr [rcx+10h], 2000000h
0x18006fca6  mov     [rcx+15h], al
0x18006fca9  xor     r9d, r9d
0x18006fcac  xor     eax, eax
0x18006fcae  mov     byte ptr [rcx+14h], 6Ch ; 'l'
0x18006fcb2  mov     [rcx+18h], rax
0x18006fcb6  xor     r8d, r8d
0x18006fcb9  mov     [rbp+20h+FileHandle], rax
0x18006fcbd  mov     rcx, rsi
0x18006fcc0  mov     eax, 14Ch
0x18006fcc5  mov     [rbp+20h+var_88], 0
0x18006fccd  mov     word ptr [rbp+20h+arg_0], ax
0x18006fcd1  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x18006fcd5  movups  xmmword ptr [rbp+20h+UnicodeString.Length], xmm1
0x18006fcd9  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006fcdf  test    eax, eax
0x18006fce1  js      loc_18006FE45
0x18006fce7  mov     [rsp+130h+EaLength], 0; EaLength
0x18006fcef  lea     rax, [rbp+20h+UnicodeString]
0x18006fcf3  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x18006fcfc  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x18006fd00  mov     [rsp+130h+CreateOptions], 60h ; '`'; CreateOptions
0x18006fd08  lea     r8, [rbp+20h+ObjectAttributes]; ObjectAttributes
0x18006fd0c  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x18006fd14  lea     rcx, [rbp+20h+FileHandle]; FileHandle
0x18006fd18  mov     [rsp+130h+ShareAccess], 5; ShareAccess
0x18006fd20  xorps   xmm0, xmm0
0x18006fd23  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x18006fd2b  mov     edx, 80100080h; DesiredAccess
0x18006fd30  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x18006fd39  mov     [rbp+20h+ObjectAttributes.Length], 30h ; '0'
0x18006fd40  mov     [rbp+20h+ObjectAttributes.RootDirectory], 0
0x18006fd48  mov     [rbp+20h+ObjectAttributes.Attributes], 40h ; '@'
0x18006fd4f  mov     [rbp+20h+ObjectAttributes.ObjectName], rax
0x18006fd53  movdqu  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fd58  call    cs:__imp_NtCreateFile
0x18006fd5e  test    eax, eax
0x18006fd60  jns     short loc_18006FD6C
0x18006fd62  mov     ebx, 6Eh ; 'n'
0x18006fd67  jmp     loc_18006FE45
0x18006fd6c  mov     r14, [rbp+20h+arg_38]
0x18006fd70  lea     rax, [rbp+20h+var_98]
0x18006fd74  mov     rbx, [rbp+20h+arg_30]
0x18006fd78  xor     r8d, r8d; int
0x18006fd7b  mov     r9, [rbp+20h+FileHandle]; int
0x18006fd7f  xor     edx, edx; int
0x18006fd81  mov     [rsp+130h+var_A8], rax; __int64
0x18006fd89  xor     ecx, ecx; int
0x18006fd8b  lea     rax, [rbp+20h+var_88]
0x18006fd8f  mov     [rsp+130h+var_B0], rax; __int64
0x18006fd97  lea     rax, [rbp+20h+arg_0]
0x18006fd9b  mov     [rsp+130h+var_B8], rax; __int64
0x18006fda0  lea     rax, [rbp+20h+var_98+4]
0x18006fda4  mov     [rsp+130h+var_C0], rax; __int64
0x18006fda9  mov     rax, [rbp+20h+arg_50]
0x18006fdb0  mov     [rsp+130h+var_C8], rax; __int64
0x18006fdb5  lea     rax, [rbp+20h+var_90]
0x18006fdb9  mov     [rsp+130h+var_D0], rax; __int64
0x18006fdbe  mov     rax, [rbp+20h+arg_48]
0x18006fdc2  mov     [rsp+130h+var_D8], rax; __int64
0x18006fdc7  mov     rax, qword ptr [rbp+20h+arg_40]
0x18006fdcb  mov     qword ptr [rsp+130h+EaLength], rax; int
0x18006fdd0  mov     rax, [rbp+20h+arg_28]
0x18006fdd4  mov     [rsp+130h+EaBuffer], r14; int
0x18006fdd9  mov     qword ptr [rsp+130h+CreateOptions], rbx; int
0x18006fdde  mov     qword ptr [rsp+130h+CreateDisposition], rax; __int64
0x18006fde3  mov     rax, [rbp+20h+arg_20]
0x18006fde7  mov     qword ptr [rsp+130h+ShareAccess], rax; __int64
0x18006fdec  mov     qword ptr [rsp+130h+FileAttributes], rsi; __int64
0x18006fdf1  mov     [rsp+130h+AllocationSize], r8; HANDLE
0x18006fdf6  call    BasepQueryAppCompat
0x18006fdfb  test    rbx, rbx
0x18006fdfe  jz      short loc_18006FE43
0x18006fe00  cmp     qword ptr [rbx], 0
0x18006fe04  jz      short loc_18006FE43
0x18006fe06  call    BasepInitializeApphelpGlobals
0x18006fe0b  test    eax, eax
0x18006fe0d  js      short loc_18006FE62
0x18006fe0f  mov     rcx, cs:qword_1800B6060; Pointer
0x18006fe16  call    cs:__imp_RtlDecodeSystemPointer
0x18006fe1c  test    rax, rax
0x18006fe1f  jz      short loc_18006FE62
0x18006fe21  mov     ecx, [r14]
0x18006fe24  mov     edx, 20h ; ' '
0x18006fe29  mov     r9, [rbx]
0x18006fe2c  movzx   r8d, word ptr [rbp+20h+arg_0]
0x18006fe31  mov     qword ptr [rsp+130h+FileAttributes], r15
0x18006fe36  mov     [rsp+130h+AllocationSize], rcx
0x18006fe3b  mov     rcx, rdi
0x18006fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe43  xor     ebx, ebx
0x18006fe45  mov     rcx, [rbp+20h+FileHandle]; Handle
0x18006fe49  test    rcx, rcx
0x18006fe4c  jz      short loc_18006FE54
0x18006fe4e  call    cs:__imp_NtClose
0x18006fe54  lea     rcx, [rbp+20h+UnicodeString]; UnicodeString
0x18006fe58  call    cs:__imp_RtlFreeUnicodeString
0x18006fe5e  mov     eax, ebx
0x18006fe60  jmp     short loc_18006FE6E
0x18006fe62  mov     ebx, 7Fh
0x18006fe67  jmp     short loc_18006FE45
0x18006fe69  mov     eax, 57h ; 'W'
0x18006fe6e  add     rsp, 108h
0x18006fe75  pop     r15
0x18006fe77  pop     r14
0x18006fe79  pop     rdi
0x18006fe7a  pop     rsi
0x18006fe7b  pop     rbx
0x18006fe7c  pop     rbp
0x18006fe7d  retn
```
