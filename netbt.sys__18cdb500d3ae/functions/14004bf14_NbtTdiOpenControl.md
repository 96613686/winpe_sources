# NbtTdiOpenControl

- ea: `0x14004bf14`
- end: `0x14004c19c`
- name: `NbtTdiOpenControl`
- size: `648`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001aa0c`
- `0x14004b7a0`

## callees

- `0x1400400a4`
- `0x140040214`
- `0x1400405d4`
- `0x140042330`
- `0x14004bf14`
- `0x14004cb60`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004c134`
- `ntoskrnl!ZwClose` at `0x14004c134`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14004c087`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14004c087`
- `ntoskrnl!ZwCreateFile` at `0x14004bfed`
- `ntoskrnl!ZwCreateFile` at `0x14004bfed`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004c052`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004c052`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c001`

## pseudocode

```c
__int64 __fastcall NbtTdiOpenControl(__int64 a1)
{
  __int64 result; // rax
  HANDLE *v3; // rdi
  NTSTATUS Status; // ebx
  HANDLE v5; // rcx
  NTSTATUS v6; // eax
  PVOID v7; // r8
  NTSTATUS v8; // eax
  PVOID P[2]; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+17h] BYREF
  PVOID Object; // [rsp+D8h] [rbp+6Fh] BYREF

  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  result = CreateDeviceString(L"Tcp", (PUNICODE_STRING)P);
  if ( (int)result >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    if ( (xmmword_140038420 & 0x10) != 0 )
      WPP_SF_S(1028, 14, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, P[1]);
    v3 = (HANDLE *)(a1 + 648);
    Status = ZwCreateFile((PHANDLE)(a1 + 648), 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 2u, 0, 0, 0);
    ExFreePoolWithTag(P[1], 0);
    if ( (BYTE2(xmmword_140038420) & 2) != 0 )
      WPP_SF_qD(1041, 15, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, *v3, Status);
    if ( Status < 0 )
    {
      if ( (xmmword_140038420 & 0x10) != 0 )
        WPP_SF_d(1028, 19, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, (unsigned int)Status);
      *(_QWORD *)(a1 + 664) = 0;
    }
    else
    {
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status < 0 )
      {
        if ( (xmmword_140038420 & 0x10) != 0 )
          WPP_SF_d(1028, 16, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, (unsigned int)IoStatusBlock.Status);
      }
      else
      {
        v5 = *v3;
        Object = 0;
        v6 = ObReferenceObjectByHandle(v5, 0, 0, 0, &Object, 0);
        v7 = Object;
        Status = v6;
        *(_QWORD *)(a1 + 664) = Object;
        if ( (BYTE2(xmmword_140038420) & 2) != 0 )
          WPP_SF_qqD(1041, 17, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, *v3, v7, v6);
        if ( Status < 0 )
        {
          v8 = ZwClose(*v3);
          if ( (BYTE2(xmmword_140038420) & 2) != 0 )
            WPP_SF_qD(1041, 18, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, *v3, v8);
          *v3 = 0;
        }
        else
        {
          *(_QWORD *)(a1 + 656) = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(a1 + 664));
        }
      }
    }
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x14004bf14  mov     [rsp-8+arg_0], rbx
0x14004bf19  mov     [rsp-8+arg_10], rsi
0x14004bf1e  push    rbp
0x14004bf1f  push    rdi
0x14004bf20  push    r15
0x14004bf22  lea     rbp, [rsp-47h]
0x14004bf27  sub     rsp, 0B0h
0x14004bf2e  xorps   xmm0, xmm0
0x14004bf31  lea     rdx, [rbp+57h+P]; Destination
0x14004bf35  mov     rsi, rcx
0x14004bf38  xor     eax, eax
0x14004bf3a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004bf3e  lea     rcx, aTcp; "Tcp"
0x14004bf45  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004bf49  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14004bf4d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004bf51  movups  xmmword ptr [rbp+57h+P], xmm0
0x14004bf55  call    CreateDeviceString
0x14004bf5a  test    eax, eax
0x14004bf5c  js      loc_14004C09C
0x14004bf62  lea     rax, [rbp+57h+P]
0x14004bf66  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004bf6d  xorps   xmm0, xmm0
0x14004bf70  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004bf74  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004bf79  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14004bf81  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14004bf88  test    byte ptr cs:xmmword_140038420, 10h
0x14004bf8f  lea     r15, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x14004bf96  jnz     loc_14004C0B5
0x14004bf9c  mov     [rsp+0C0h+EaLength], 0; EaLength
0x14004bfa4  lea     rdi, [rsi+288h]
0x14004bfab  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x14004bfb4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14004bfb8  mov     [rsp+0C0h+CreateOptions], 0; CreateOptions
0x14004bfc0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004bfc4  mov     [rsp+0C0h+CreateDisposition], 2; CreateDisposition
0x14004bfcc  mov     edx, 0C0000000h; DesiredAccess
0x14004bfd1  mov     [rsp+0C0h+ShareAccess], 0; ShareAccess
0x14004bfd9  mov     rcx, rdi; FileHandle
0x14004bfdc  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x14004bfe4  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x14004bfed  call    cs:__imp_ZwCreateFile
0x14004bff4  nop     dword ptr [rax+rax+00h]
0x14004bff9  mov     rcx, [rbp+57h+P+8]; P
0x14004bffd  xor     edx, edx; Tag
0x14004bfff  mov     ebx, eax
0x14004c001  call    cs:__imp_ExFreePoolWithTag
0x14004c008  nop     dword ptr [rax+rax+00h]
0x14004c00d  test    byte ptr cs:xmmword_140038420+2, 2
0x14004c014  jnz     loc_14004C0D0
0x14004c01a  test    ebx, ebx
0x14004c01c  js      loc_14004C16E
0x14004c022  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x14004c025  test    ebx, ebx
0x14004c027  js      loc_14004C0EE
0x14004c02d  mov     rcx, [rdi]; Handle
0x14004c030  lea     rax, [rbp+57h+Object]
0x14004c034  mov     qword ptr [rsp+0C0h+FileAttributes], 0; HandleInformation
0x14004c03d  xor     r9d, r9d; AccessMode
0x14004c040  xor     r8d, r8d; ObjectType
0x14004c043  mov     [rsp+0C0h+AllocationSize], rax; Object
0x14004c048  xor     edx, edx; DesiredAccess
0x14004c04a  mov     [rbp+57h+Object], 0
0x14004c052  call    cs:__imp_ObReferenceObjectByHandle
0x14004c059  nop     dword ptr [rax+rax+00h]
0x14004c05e  mov     r8, [rbp+57h+Object]
0x14004c062  mov     ebx, eax
0x14004c064  mov     [rsi+298h], r8
0x14004c06b  test    byte ptr cs:xmmword_140038420+2, 2
0x14004c072  jnz     loc_14004C10E
0x14004c078  test    ebx, ebx
0x14004c07a  js      loc_14004C131
0x14004c080  mov     rcx, [rsi+298h]; FileObject
0x14004c087  call    cs:__imp_IoGetRelatedDeviceObject
0x14004c08e  nop     dword ptr [rax+rax+00h]
0x14004c093  mov     [rsi+290h], rax
0x14004c09a  mov     eax, ebx
0x14004c09c  lea     r11, [rsp+0C0h+var_10]
0x14004c0a4  mov     rbx, [r11+20h]
0x14004c0a8  mov     rsi, [r11+30h]
0x14004c0ac  mov     rsp, r11
0x14004c0af  pop     r15
0x14004c0b1  pop     rdi
0x14004c0b2  pop     rbp
0x14004c0b3  retn
0x14004c0b5  mov     r9, [rbp+57h+P+8]
0x14004c0b9  mov     edx, 0Eh
0x14004c0be  mov     ecx, 404h
0x14004c0c3  mov     r8, r15
0x14004c0c6  call    WPP_SF_S
0x14004c0cb  jmp     loc_14004BF9C
0x14004c0d0  mov     r9, [rdi]
0x14004c0d3  mov     edx, 0Fh
0x14004c0d8  mov     ecx, 411h
0x14004c0dd  mov     dword ptr [rsp+0C0h+AllocationSize], ebx
0x14004c0e1  mov     r8, r15
0x14004c0e4  call    WPP_SF_qD
0x14004c0e9  jmp     loc_14004C01A
0x14004c0ee  test    byte ptr cs:xmmword_140038420, 10h
0x14004c0f5  jz      short loc_14004C09A
0x14004c0f7  mov     edx, 10h
0x14004c0fc  mov     ecx, 404h
0x14004c101  mov     r9d, ebx
0x14004c104  mov     r8, r15
0x14004c107  call    WPP_SF_d
0x14004c10c  jmp     short loc_14004C09A
0x14004c10e  mov     r9, [rdi]
0x14004c111  mov     edx, 11h
0x14004c116  mov     [rsp+0C0h+FileAttributes], ebx
0x14004c11a  mov     ecx, 411h
0x14004c11f  mov     [rsp+0C0h+AllocationSize], r8
0x14004c124  mov     r8, r15
0x14004c127  call    WPP_SF_qqD
0x14004c12c  jmp     loc_14004C078
0x14004c131  mov     rcx, [rdi]; Handle
0x14004c134  call    cs:__imp_ZwClose
0x14004c13b  nop     dword ptr [rax+rax+00h]
0x14004c140  test    byte ptr cs:xmmword_140038420+2, 2
0x14004c147  jz      short loc_14004C162
0x14004c149  mov     r9, [rdi]
0x14004c14c  mov     edx, 12h
0x14004c151  mov     ecx, 411h
0x14004c156  mov     dword ptr [rsp+0C0h+AllocationSize], eax
0x14004c15a  mov     r8, r15
0x14004c15d  call    WPP_SF_qD
0x14004c162  mov     qword ptr [rdi], 0
0x14004c169  jmp     loc_14004C09A
0x14004c16e  test    byte ptr cs:xmmword_140038420, 10h
0x14004c175  jz      short loc_14004C18C
0x14004c177  mov     edx, 13h
0x14004c17c  mov     ecx, 404h
0x14004c181  mov     r9d, ebx
0x14004c184  mov     r8, r15
0x14004c187  call    WPP_SF_d
0x14004c18c  mov     qword ptr [rsi+298h], 0
0x14004c197  jmp     loc_14004C09A
```
