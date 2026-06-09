# BasepQueryModuleChpeSettings

- ea: `0x180077840`
- end: `0x180077a95`
- name: `BasepQueryModuleChpeSettings`
- size: `597`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001cfa0`
- `0x180077764`
- `0x180077840`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800778e4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800778e4`
- `ntdll!NtClose` at `0x180077a53`
- `ntdll!NtClose` at `0x180077a53`
- `ntdll!RtlFreeUnicodeString` at `0x180077a63`
- `ntdll!RtlFreeUnicodeString` at `0x180077a63`
- `ntdll!NtCreateFile` at `0x18007795a`
- `ntdll!NtCreateFile` at `0x18007795a`

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
  void *FileHandle; // [rsp+90h] [rbp-80h] BYREF
  void (__fastcall *v20)(__int64, __int64, _QWORD, _QWORD, _QWORD, __int64); // [rsp+98h] [rbp-78h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-18h] BYREF
  __int64 v27; // [rsp+140h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  if ( !a1 || a2 != 32 )
    return 87;
  v14 = 3;
  v15 = *(_BYTE *)(a1 + 21) & 0xF3;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0x80000000;
  *(_BYTE *)(a1 + 21) = v15 | 3;
  *(_DWORD *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 16) = 0x2000000;
  *(_BYTE *)(a1 + 20) = 108;
  *(_QWORD *)(a1 + 24) = 0;
  FileHandle = 0;
  LOWORD(v27) = 332;
  v23 = 0;
  v20 = 0;
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
        if ( (int)BasepGetApphelpChpeModSettingsFromQueryResultProc(&v20) < 0 )
        {
          v14 = 127;
          goto LABEL_12;
        }
        v20(a1, 32, (unsigned __int16)v27, *v17, *v16, a4);
      }
      v14 = 0;
      goto LABEL_12;
    }
    v14 = 110;
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
0x180077840  mov     [rsp-28h+arg_8], rbx
0x180077845  mov     [rsp-28h+arg_10], rsi
0x18007784a  push    rbp
0x18007784b  push    rdi
0x18007784c  push    r12
0x18007784e  push    r14
0x180077850  push    r15
0x180077852  mov     rbp, rsp
0x180077855  sub     rsp, 110h
0x18007785c  xorps   xmm0, xmm0
0x18007785f  xor     eax, eax
0x180077861  xor     r12d, r12d
0x180077864  mov     r15, r9
0x180077867  mov     rsi, r8
0x18007786a  mov     rdi, rcx
0x18007786d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180077871  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180077875  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180077879  test    rcx, rcx
0x18007787c  jz      loc_180077A73
0x180077882  cmp     edx, 20h ; ' '
0x180077885  jnz     loc_180077A73
0x18007788b  mov     al, [rcx+15h]
0x18007788e  lea     ebx, [rdx-1Dh]
0x180077891  and     al, 0F3h
0x180077893  mov     [rcx], r12
0x180077896  or      al, bl
0x180077898  mov     dword ptr [rcx+8], 80000000h
0x18007789f  mov     [rcx+15h], al
0x1800778a2  lea     rdx, [rbp+UnicodeString]
0x1800778a6  xor     eax, eax
0x1800778a8  mov     [rcx+0Ch], r12d
0x1800778ac  mov     dword ptr [rcx+10h], 2000000h
0x1800778b3  xorps   xmm1, xmm1
0x1800778b6  mov     byte ptr [rcx+14h], 6Ch ; 'l'
0x1800778ba  xor     r9d, r9d
0x1800778bd  mov     [rcx+18h], rax
0x1800778c1  xor     r8d, r8d
0x1800778c4  mov     eax, 14Ch
0x1800778c9  mov     [rbp+FileHandle], r12
0x1800778cd  mov     rcx, rsi
0x1800778d0  mov     word ptr [rbp+arg_0], ax
0x1800778d4  mov     [rbp+var_60], r12
0x1800778d8  mov     [rbp+var_78], r12
0x1800778dc  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800778e0  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x1800778e4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800778eb  nop     dword ptr [rax+rax+00h]
0x1800778f0  test    eax, eax
0x1800778f2  js      loc_180077A4A
0x1800778f8  mov     [rsp+110h+EaLength], r12d; EaLength
0x1800778fd  lea     rax, [rbp+UnicodeString]
0x180077901  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x180077906  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18007790a  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x180077912  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180077916  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18007791e  lea     rcx, [rbp+FileHandle]; FileHandle
0x180077922  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x18007792a  xorps   xmm0, xmm0
0x18007792d  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180077935  mov     edx, 80100080h; DesiredAccess
0x18007793a  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18007793f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180077946  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x18007794a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180077951  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180077955  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007795a  call    cs:__imp_NtCreateFile
0x180077961  nop     dword ptr [rax+rax+00h]
0x180077966  test    eax, eax
0x180077968  jns     short loc_180077974
0x18007796a  lea     ebx, [r12+6Eh]
0x18007796f  jmp     loc_180077A4A
0x180077974  mov     r14, [rbp+arg_38]
0x180077978  lea     rax, [rbp+var_70]
0x18007797c  mov     rbx, [rbp+arg_30]
0x180077980  xor     r8d, r8d; int
0x180077983  mov     r9, [rbp+FileHandle]; int
0x180077987  xor     edx, edx; int
0x180077989  mov     [rsp+110h+var_88], rax; __int64
0x180077991  xor     ecx, ecx; int
0x180077993  lea     rax, [rbp+var_60]
0x180077997  mov     [rsp+110h+var_90], rax; __int64
0x18007799f  lea     rax, [rbp+arg_0]
0x1800779a3  mov     [rsp+110h+var_98], rax; __int64
0x1800779a8  lea     rax, [rbp+var_70+4]
0x1800779ac  mov     [rsp+110h+var_A0], rax; __int64
0x1800779b1  mov     rax, [rbp+arg_50]
0x1800779b8  mov     [rsp+110h+var_A8], rax; __int64
0x1800779bd  lea     rax, [rbp+var_68]
0x1800779c1  mov     [rsp+110h+var_B0], rax; __int64
0x1800779c6  mov     rax, [rbp+arg_48]
0x1800779ca  mov     [rsp+110h+var_B8], rax; __int64
0x1800779cf  mov     rax, qword ptr [rbp+arg_40]
0x1800779d3  mov     qword ptr [rsp+110h+EaLength], rax; int
0x1800779d8  mov     rax, [rbp+arg_28]
0x1800779dc  mov     [rsp+110h+EaBuffer], r14; int
0x1800779e1  mov     qword ptr [rsp+110h+CreateOptions], rbx; int
0x1800779e6  mov     qword ptr [rsp+110h+CreateDisposition], rax; __int64
0x1800779eb  mov     rax, [rbp+arg_20]
0x1800779ef  mov     qword ptr [rsp+110h+ShareAccess], rax; __int64
0x1800779f4  mov     qword ptr [rsp+110h+FileAttributes], rsi; __int64
0x1800779f9  mov     [rsp+110h+AllocationSize], r12; HANDLE
0x1800779fe  call    BasepQueryAppCompat
0x180077a03  test    rbx, rbx
0x180077a06  jz      short loc_180077A47
0x180077a08  cmp     [rbx], r12
0x180077a0b  jz      short loc_180077A47
0x180077a0d  lea     rcx, [rbp+var_78]
0x180077a11  call    BasepGetApphelpChpeModSettingsFromQueryResultProc
0x180077a16  test    eax, eax
0x180077a18  jns     short loc_180077A21
0x180077a1a  mov     ebx, 7Fh
0x180077a1f  jmp     short loc_180077A4A
0x180077a21  mov     ecx, [r14]
0x180077a24  mov     edx, 20h ; ' '
0x180077a29  mov     r9, [rbx]
0x180077a2c  movzx   r8d, word ptr [rbp+arg_0]
0x180077a31  mov     rax, [rbp+var_78]
0x180077a35  mov     qword ptr [rsp+110h+FileAttributes], r15
0x180077a3a  mov     [rsp+110h+AllocationSize], rcx
0x180077a3f  mov     rcx, rdi
0x180077a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a47  mov     ebx, r12d
0x180077a4a  mov     rcx, [rbp+FileHandle]; Handle
0x180077a4e  test    rcx, rcx
0x180077a51  jz      short loc_180077A5F
0x180077a53  call    cs:__imp_NtClose
0x180077a5a  nop     dword ptr [rax+rax+00h]
0x180077a5f  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180077a63  call    cs:__imp_RtlFreeUnicodeString
0x180077a6a  nop     dword ptr [rax+rax+00h]
0x180077a6f  mov     eax, ebx
0x180077a71  jmp     short loc_180077A78
0x180077a73  mov     eax, 57h ; 'W'
0x180077a78  lea     r11, [rsp+110h+var_s0]
0x180077a80  mov     rbx, [r11+38h]
0x180077a84  mov     rsi, [r11+40h]
0x180077a88  mov     rsp, r11
0x180077a8b  pop     r15
0x180077a8d  pop     r14
0x180077a8f  pop     r12
0x180077a91  pop     rdi
0x180077a92  pop     rbp
0x180077a93  retn
```
