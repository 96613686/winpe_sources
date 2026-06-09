# BasepQueryModuleChpeSettings2

- ea: `0x18006fe90`
- end: `0x1800700ad`
- name: `BasepQueryModuleChpeSettings2`
- size: `541`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001f130`
- `0x18002eafc`
- `0x18006fe90`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDecodeSystemPointer` at `0x180070044`
- `ntdll!RtlDecodeSystemPointer` at `0x180070044`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006ff08`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006ff08`
- `ntdll!NtClose` at `0x18007007f`
- `ntdll!NtClose` at `0x18007007f`
- `ntdll!RtlFreeUnicodeString` at `0x180070089`
- `ntdll!RtlFreeUnicodeString` at `0x180070089`
- `ntdll!NtCreateFile` at `0x18006ff8d`
- `ntdll!NtCreateFile` at `0x18006ff8d`

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
  PVOID v18; // rax
  void *FileHandle; // [rsp+90h] [rbp-69h] BYREF
  __int64 v20; // [rsp+98h] [rbp-61h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-59h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-51h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-9h] BYREF
  __int64 v26; // [rsp+130h] [rbp+37h] BYREF

  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
    return 87;
  *a1 = 0;
  FileHandle = 0;
  v22 = 0;
  LOWORD(v26) = 332;
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
        if ( (int)BasepInitializeApphelpGlobals() >= 0 && (v18 = RtlDecodeSystemPointer(qword_1800B6068)) != 0 )
        {
          ((void (__fastcall *)(_QWORD *, _QWORD, _QWORD, _QWORD, __int64))v18)(
            a1,
            (unsigned __int16)v26,
            *v17,
            *v16,
            a3);
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
0x18006fe90  mov     [rsp-8+arg_8], rbx
0x18006fe95  mov     [rsp-8+arg_10], rsi
0x18006fe9a  push    rbp
0x18006fe9b  push    rdi
0x18006fe9c  push    r12
0x18006fe9e  push    r14
0x18006fea0  push    r15
0x18006fea2  lea     rbp, [rsp-7]
0x18006fea7  sub     rsp, 100h
0x18006feae  xorps   xmm0, xmm0
0x18006feb1  xor     eax, eax
0x18006feb3  mov     r12, r9
0x18006feb6  mov     r15, r8
0x18006feb9  mov     rsi, rdx
0x18006febc  mov     rbx, rcx
0x18006febf  movups  xmmword ptr [rbp+27h+ObjectAttributes.ObjectName], xmm0
0x18006fec3  movups  xmmword ptr [rbp+27h+ObjectAttributes+1Ch], xmm0
0x18006fec7  movups  xmmword ptr [rbp+27h+ObjectAttributes.Length], xmm0
0x18006fecb  test    rcx, rcx
0x18006fece  jnz     short loc_18006FED8
0x18006fed0  lea     eax, [rcx+57h]
0x18006fed3  jmp     loc_180070091
0x18006fed8  mov     [rcx], rax
0x18006fedb  lea     rdx, [rbp+27h+UnicodeString]
0x18006fedf  mov     [rbp+27h+FileHandle], rax
0x18006fee3  xorps   xmm1, xmm1
0x18006fee6  mov     eax, 14Ch
0x18006feeb  mov     [rbp+27h+var_78], 0
0x18006fef3  xor     r9d, r9d
0x18006fef6  mov     word ptr [rbp+27h+arg_0], ax
0x18006fefa  xor     r8d, r8d
0x18006fefd  mov     rcx, rsi
0x18006ff00  movups  xmmword ptr [rbp+27h+IoStatusBlock], xmm0
0x18006ff04  movups  xmmword ptr [rbp+27h+UnicodeString.Length], xmm1
0x18006ff08  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006ff0e  test    eax, eax
0x18006ff10  jns     short loc_18006FF1C
0x18006ff12  mov     ebx, 3
0x18006ff17  jmp     loc_180070076
0x18006ff1c  mov     [rsp+120h+EaLength], 0; EaLength
0x18006ff24  lea     rax, [rbp+27h+UnicodeString]
0x18006ff28  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x18006ff31  lea     r9, [rbp+27h+IoStatusBlock]; IoStatusBlock
0x18006ff35  mov     [rsp+120h+CreateOptions], 60h ; '`'; CreateOptions
0x18006ff3d  lea     r8, [rbp+27h+ObjectAttributes]; ObjectAttributes
0x18006ff41  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x18006ff49  lea     rcx, [rbp+27h+FileHandle]; FileHandle
0x18006ff4d  mov     [rsp+120h+ShareAccess], 5; ShareAccess
0x18006ff55  xorps   xmm0, xmm0
0x18006ff58  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x18006ff60  mov     edx, 80100080h; DesiredAccess
0x18006ff65  mov     [rsp+120h+AllocationSize], 0; AllocationSize
0x18006ff6e  mov     [rbp+27h+ObjectAttributes.Length], 30h ; '0'
0x18006ff75  mov     [rbp+27h+ObjectAttributes.RootDirectory], 0
0x18006ff7d  mov     [rbp+27h+ObjectAttributes.Attributes], 40h ; '@'
0x18006ff84  mov     [rbp+27h+ObjectAttributes.ObjectName], rax
0x18006ff88  movdqu  xmmword ptr [rbp+27h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006ff8d  call    cs:__imp_NtCreateFile
0x18006ff93  test    eax, eax
0x18006ff95  jns     short loc_18006FFA1
0x18006ff97  mov     ebx, 6Eh ; 'n'
0x18006ff9c  jmp     loc_180070076
0x18006ffa1  mov     r14, [rbp+27h+arg_30]
0x18006ffa5  lea     rax, [rbp+27h+var_88]
0x18006ffa9  mov     rdi, [rbp+27h+arg_28]
0x18006ffad  xor     r8d, r8d; int
0x18006ffb0  mov     r9, [rbp+27h+FileHandle]; int
0x18006ffb4  xor     edx, edx; int
0x18006ffb6  mov     [rsp+120h+var_98], rax; __int64
0x18006ffbe  xor     ecx, ecx; int
0x18006ffc0  lea     rax, [rbp+27h+var_78]
0x18006ffc4  mov     [rsp+120h+var_A0], rax; __int64
0x18006ffcc  lea     rax, [rbp+27h+arg_0]
0x18006ffd0  mov     [rsp+120h+var_A8], rax; __int64
0x18006ffd5  lea     rax, [rbp+27h+var_88+4]
0x18006ffd9  mov     [rsp+120h+var_B0], rax; __int64
0x18006ffde  mov     rax, [rbp+27h+arg_48]
0x18006ffe2  mov     [rsp+120h+var_B8], rax; __int64
0x18006ffe7  lea     rax, [rbp+27h+var_80]
0x18006ffeb  mov     [rsp+120h+var_C0], rax; __int64
0x18006fff0  mov     rax, [rbp+27h+arg_40]
0x18006fff4  mov     [rsp+120h+var_C8], rax; __int64
0x18006fff9  mov     rax, qword ptr [rbp+27h+arg_38]
0x18006fffd  mov     qword ptr [rsp+120h+EaLength], rax; int
0x180070002  mov     rax, [rbp+27h+arg_20]
0x180070006  mov     [rsp+120h+EaBuffer], r14; int
0x18007000b  mov     qword ptr [rsp+120h+CreateOptions], rdi; int
0x180070010  mov     qword ptr [rsp+120h+CreateDisposition], rax; __int64
0x180070015  mov     qword ptr [rsp+120h+ShareAccess], r12; __int64
0x18007001a  mov     qword ptr [rsp+120h+FileAttributes], rsi; __int64
0x18007001f  mov     [rsp+120h+AllocationSize], r8; HANDLE
0x180070024  call    BasepQueryAppCompat
0x180070029  test    rdi, rdi
0x18007002c  jz      short loc_180070071
0x18007002e  cmp     qword ptr [rdi], 0
0x180070032  jz      short loc_180070071
0x180070034  call    BasepInitializeApphelpGlobals
0x180070039  test    eax, eax
0x18007003b  js      short loc_18007006A
0x18007003d  mov     rcx, cs:qword_1800B6068; Pointer
0x180070044  call    cs:__imp_RtlDecodeSystemPointer
0x18007004a  test    rax, rax
0x18007004d  jz      short loc_18007006A
0x18007004f  mov     r9d, [r14]
0x180070052  mov     rcx, rbx
0x180070055  mov     r8, [rdi]
0x180070058  movzx   edx, word ptr [rbp+27h+arg_0]
0x18007005c  mov     [rsp+120h+AllocationSize], r15
0x180070061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070066  xor     ebx, ebx
0x180070068  jmp     short loc_180070076
0x18007006a  mov     ebx, 7Fh
0x18007006f  jmp     short loc_180070076
0x180070071  mov     ebx, 490h
0x180070076  mov     rcx, [rbp+27h+FileHandle]; Handle
0x18007007a  test    rcx, rcx
0x18007007d  jz      short loc_180070085
0x18007007f  call    cs:__imp_NtClose
0x180070085  lea     rcx, [rbp+27h+UnicodeString]; UnicodeString
0x180070089  call    cs:__imp_RtlFreeUnicodeString
0x18007008f  mov     eax, ebx
0x180070091  lea     r11, [rsp+120h+var_20]
0x180070099  mov     rbx, [r11+38h]
0x18007009d  mov     rsi, [r11+40h]
0x1800700a1  mov     rsp, r11
0x1800700a4  pop     r15
0x1800700a6  pop     r14
0x1800700a8  pop     r12
0x1800700aa  pop     rdi
0x1800700ab  pop     rbp
0x1800700ac  retn
```
