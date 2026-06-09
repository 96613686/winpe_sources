# CClfsContainer::Remove(_UNICODE_STRING &)

- ea: `0x14003ee68`
- end: `0x14003eff3`
- name: `?Remove@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003ed2c`

## callees

- `0x140017f20`
- `0x14003ee68`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003efb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14007e55a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003efb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14007e55a`
- `ntoskrnl!ZwClose` at `0x14003efc9`
- `ntoskrnl!ZwClose` at `0x14007e572`
- `ntoskrnl!ZwClose` at `0x14003efc9`
- `ntoskrnl!ZwClose` at `0x14007e572`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ef5d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003ef5d`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14003ef18`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14003ef18`

## pseudocode

```c
__int64 __fastcall CClfsContainer::Remove(CClfsContainer *this, struct _UNICODE_STRING *a2)
{
  HANDLE *v3; // rsi
  NTSTATUS v4; // edi
  HANDLE v5; // rcx
  struct _IO_STATUS_BLOCK v7; // [rsp+88h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES v8; // [rsp+98h] [rbp-50h] BYREF
  PVOID Object; // [rsp+F8h] [rbp+10h] BYREF

  v7.Pointer = 0;
  v7.Information = 0;
  *(_QWORD *)&v8.Length = 48;
  *(_QWORD *)&v8.Attributes = 576;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  v8.RootDirectory = 0;
  v8.ObjectName = a2;
  *(_OWORD *)&v8.SecurityDescriptor = 0;
  v3 = (HANDLE *)((char *)this + 32);
  v4 = IoCreateFileSpecifyDeviceObjectHint(
         (PHANDLE)this + 4,
         0xC0000000,
         &v8,
         &v7,
         0,
         0x80u,
         1u,
         1u,
         0x800Eu,
         0,
         0,
         CreateFileTypeNone,
         0,
         0x101u,
         0);
  if ( v4 >= 0 )
  {
    v5 = *v3;
    Object = 0;
    v4 = ObReferenceObjectByHandle(v5, 3u, 0, 0, &Object, 0);
    *((_QWORD *)this + 6) = Object;
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(CClfsContainer *))(*(_QWORD *)this + 24LL))(this);
    else
      *((_QWORD *)this + 6) = 0;
  }
  else
  {
    *v3 = 0;
  }
  if ( v4 < 0 )
  {
    if ( *v3 )
    {
      if ( *((_QWORD *)this + 6) )
      {
        ObfDereferenceObject(*((PVOID *)this + 6));
        *((_QWORD *)this + 6) = 0;
      }
      ZwClose(*v3);
    }
    *v3 = 0;
    *((_QWORD *)this + 1) = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003ee68  mov     r11, rsp
0x14003ee6b  mov     [r11+18h], rbx
0x14003ee6f  mov     [r11+8], rcx
0x14003ee73  push    rsi
0x14003ee74  push    rdi
0x14003ee75  push    r14
0x14003ee77  sub     rsp, 0D0h
0x14003ee7e  mov     rbx, rcx
0x14003ee81  xor     r14d, r14d
0x14003ee84  mov     [r11-68h], r14d
0x14003ee88  mov     [r11-60h], r14
0x14003ee8c  xor     eax, eax
0x14003ee8e  mov     [r11-58h], r14
0x14003ee92  mov     qword ptr [r11-50h], 30h ; '0'
0x14003ee9a  mov     qword ptr [r11-38h], 240h
0x14003eea2  mov     [rcx+8], r14
0x14003eea6  mov     [rcx+40h], r14d
0x14003eeaa  mov     [rcx+18h], r14
0x14003eeae  mov     [rcx+10h], r14
0x14003eeb2  mov     [r11-48h], r14
0x14003eeb6  mov     [r11-40h], rdx
0x14003eeba  xorps   xmm0, xmm0
0x14003eebd  movdqu  xmmword ptr [r11-30h], xmm0
0x14003eec3  lea     rsi, [rcx+20h]
0x14003eec7  mov     [r11-78h], r14
0x14003eecb  mov     [rsp+0E8h+Options], 101h; Options
0x14003eed3  mov     [rsp+0E8h+InternalParameters], r14; InternalParameters
0x14003eed8  mov     [rsp+0E8h+CreateFileType], r14d; CreateFileType
0x14003eedd  mov     [rsp+0E8h+EaLength], r14d; EaLength
0x14003eee2  mov     [rsp+0E8h+EaBuffer], r14; EaBuffer
0x14003eee7  mov     [rsp+0E8h+CreateOptions], 800Eh; CreateOptions
0x14003eeef  lea     eax, [r14+1]
0x14003eef3  mov     [rsp+0E8h+Disposition], eax; Disposition
0x14003eef7  mov     [rsp+0E8h+ShareAccess], eax; ShareAccess
0x14003eefb  mov     [rsp+0E8h+FileAttributes], 80h; FileAttributes
0x14003ef03  mov     [rsp+0E8h+AllocationSize], r14; AllocationSize
0x14003ef08  lea     r9, [r11-60h]; IoStatusBlock
0x14003ef0c  lea     r8, [r11-50h]; ObjectAttributes
0x14003ef10  mov     edx, 0C0000000h; DesiredAccess
0x14003ef15  mov     rcx, rsi; FileHandle
0x14003ef18  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x14003ef1f  nop     dword ptr [rax+rax+00h]
0x14003ef24  mov     edi, eax
0x14003ef26  mov     [rsp+0E8h+var_68], eax
0x14003ef2d  test    eax, eax
0x14003ef2f  jns     short loc_14003EF36
0x14003ef31  mov     [rsi], r14
0x14003ef34  jmp     short loc_14003EFA0
0x14003ef36  mov     rcx, [rsi]; Handle
0x14003ef39  mov     [rsp+0E8h+Object], r14
0x14003ef41  mov     qword ptr [rsp+0E8h+FileAttributes], r14; HandleInformation
0x14003ef46  lea     rax, [rsp+0E8h+Object]
0x14003ef4e  mov     [rsp+0E8h+AllocationSize], rax; Object
0x14003ef53  xor     r9d, r9d; AccessMode
0x14003ef56  xor     r8d, r8d; ObjectType
0x14003ef59  lea     edx, [r9+3]; DesiredAccess
0x14003ef5d  call    cs:__imp_ObReferenceObjectByHandle
0x14003ef64  nop     dword ptr [rax+rax+00h]
0x14003ef69  mov     edi, eax
0x14003ef6b  mov     rax, [rsp+0E8h+Object]
0x14003ef73  mov     [rbx+30h], rax
0x14003ef77  mov     [rsp+0E8h+var_68], edi
0x14003ef7e  test    edi, edi
0x14003ef80  jns     short loc_14003EF88
0x14003ef82  mov     [rbx+30h], r14
0x14003ef86  jmp     short loc_14003EFA0
0x14003ef88  mov     rax, [rbx]
0x14003ef8b  mov     rax, [rax+18h]
0x14003ef8f  mov     rcx, rbx
0x14003ef92  call    _guard_dispatch_icall
0x14003ef97  mov     edi, eax
0x14003ef99  mov     [rsp+0E8h+var_68], eax
0x14003efa0  test    edi, edi
0x14003efa2  jns     short loc_14003EFDC
0x14003efa4  cmp     [rsi], r14
0x14003efa7  jz      short loc_14003EFD5
0x14003efa9  mov     rax, [rbx+30h]
0x14003efad  test    rax, rax
0x14003efb0  jz      short loc_14003EFC6
0x14003efb2  mov     rcx, [rbx+30h]; Object
0x14003efb6  call    cs:__imp_ObfDereferenceObject
0x14003efbd  nop     dword ptr [rax+rax+00h]
0x14003efc2  mov     [rbx+30h], r14
0x14003efc6  mov     rcx, [rsi]; Handle
0x14003efc9  call    cs:__imp_ZwClose
0x14003efd0  nop     dword ptr [rax+rax+00h]
0x14003efd5  mov     [rsi], r14
0x14003efd8  mov     [rbx+8], r14
0x14003efdc  mov     eax, edi
0x14003efde  mov     rbx, [rsp+0E8h+arg_10]
0x14003efe6  add     rsp, 0D0h
0x14003efed  pop     r14
0x14003efef  pop     rdi
0x14003eff0  pop     rsi
0x14003eff1  retn
0x14007e529  push    rbx
0x14007e52b  push    rbp
0x14007e52c  sub     rsp, 88h
0x14007e533  mov     rbp, rdx
0x14007e536  cmp     dword ptr [rbp+80h], 0
0x14007e53d  jge     short loc_14007E58F
0x14007e53f  mov     rbx, [rbp+0F0h]
0x14007e546  cmp     qword ptr [rbx+20h], 0
0x14007e54b  jz      short loc_14007E57F
0x14007e54d  mov     rax, [rbx+30h]
0x14007e551  test    rax, rax
0x14007e554  jz      short loc_14007E56E
0x14007e556  mov     rcx, [rbx+30h]; Object
0x14007e55a  call    cs:__imp_ObfDereferenceObject
0x14007e561  nop     dword ptr [rax+rax+00h]
0x14007e566  mov     qword ptr [rbx+30h], 0
0x14007e56e  mov     rcx, [rbx+20h]; Handle
0x14007e572  call    cs:__imp_ZwClose
0x14007e579  nop     dword ptr [rax+rax+00h]
0x14007e57e  nop
0x14007e57f  mov     qword ptr [rbx+20h], 0
0x14007e587  mov     qword ptr [rbx+8], 0
0x14007e58f  add     rsp, 88h
0x14007e596  pop     rbp
0x14007e597  pop     rbx
0x14007e598  retn
```
