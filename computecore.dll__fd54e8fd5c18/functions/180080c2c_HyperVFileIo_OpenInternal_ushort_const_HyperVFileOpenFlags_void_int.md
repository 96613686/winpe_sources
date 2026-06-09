# HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)

- ea: `0x180080c2c`
- end: `0x180080f6c`
- name: `?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z`
- size: `832`
- prototype: `signed int __fastcall(__int64, __int16, void **, BOOL *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007e070`
- `0x180080840`
- `0x1800811b0`

## callees

- `0x1800067c0`
- `0x180007dbc`
- `0x180007e24`
- `0x180066284`
- `0x180080c2c`
- `0x180081f2c`
- `0x180082140`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180080ed4`
- `ntdll!RtlFreeHeap` at `0x180080f0c`
- `ntdll!RtlFreeHeap` at `0x180080ed4`
- `ntdll!RtlFreeHeap` at `0x180080f0c`
- `ntdll!NtCreateFile` at `0x180080dc7`
- `ntdll!NtCreateFile` at `0x180080e18`
- `ntdll!NtCreateFile` at `0x180080dc7`
- `ntdll!NtCreateFile` at `0x180080e18`
- `ntdll!RtlNtStatusToDosError` at `0x180080cf2`
- `ntdll!RtlNtStatusToDosError` at `0x180080ee0`
- `ntdll!RtlNtStatusToDosError` at `0x180080cf2`
- `ntdll!RtlNtStatusToDosError` at `0x180080ee0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180080ce4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180080ce4`

## pseudocode

```c
signed int __fastcall HyperVFileIo::OpenInternal(__int64 a1, __int16 a2, void **a3, BOOL *a4)
{
  ULONG ShareAccess; // edi
  char v7; // si
  signed int result; // eax
  ULONG CreateDisposition; // r12d
  unsigned int v10; // r15d
  NTSTATUS v11; // eax
  PVOID v12; // rbx
  int v13; // eax
  bool v14; // zf
  BOOL v15; // eax
  int IsDebugTraceEnabled; // edi
  _DWORD *v17; // rcx
  signed int v18; // eax
  unsigned int v19; // edi
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  PVOID P[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  int v26; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+CCh] [rbp-34h]
  _DWORD EaBuffer[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v29[28]; // [rsp+E0h] [rbp-20h] BYREF
  int v30; // [rsp+FCh] [rbp-4h]

  *a3 = (void *)-1LL;
  FileHandle = (void *)-1LL;
  *a4 = 0;
  ShareAccess = (a2 & 8) != 0 ? 1 : 3;
  if ( (a2 & 0x40) != 0 )
  {
    if ( (a2 & 8) != 0 )
      return -2147024809;
    ShareAccess |= 4u;
  }
  v7 = 1;
  if ( (a2 & 0x20) != 0 && (a2 & 3) != 0 )
    return -2147024809;
  CreateDisposition = *((_DWORD *)qword_1800BE828 + (a2 & 3));
  v10 = (a2 & 0x20) != 0 ? 0xFFFFFEFE : 0;
  *(_OWORD *)P = 0;
  v11 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, 0);
  if ( v11 >= 0 )
  {
    v12 = P[1];
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.SecurityQualityOfService = &v26;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.SecurityDescriptor = 0;
    v27 = 0;
    v26 = 12;
    IoStatusBlock = 0;
    if ( (a2 & 0x1000) == 0
      || (EaBuffer[0] = 0,
          v29[27] = 0,
          v30 = 0,
          strcpy(v29, "SmbDisableHandleDurability"),
          EaBuffer[1] = 6656,
          v13 = NtCreateFile(
                  &FileHandle,
                  v10 + 1048963,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0x80u,
                  ShareAccess,
                  CreateDisposition,
                  0x840u,
                  EaBuffer,
                  0x28u),
          v13 == -1073741808)
      || v13 == -1073741745 )
    {
      v13 = NtCreateFile(
              &FileHandle,
              v10 + 1048963,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              ShareAccess,
              CreateDisposition,
              0x840u,
              0,
              0);
    }
    if ( v13 < 0 )
    {
      v18 = RtlNtStatusToDosError(v13);
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      if ( v12 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      return v19;
    }
    else
    {
      v14 = (IoStatusBlock.Information & 0xFFFFFFFFFFFFFFFCuLL) == 0;
      *a3 = FileHandle;
      v15 = v14 && IoStatusBlock.Information != 1;
      *a4 = v15;
      IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC000u);
      v17 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
      if ( !v17 || !*v17 )
        v7 = 0;
      if ( IsDebugTraceEnabled || v7 )
      {
        if ( dword_1800E4824 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 16LL) )
        {
          Init_thread_header(&dword_1800E4824);
          if ( dword_1800E4824 == -1 )
          {
            byte_1800E24C4 = IsDebugTraceEnabled != 0;
            byte_1800E24C5 = v7;
            Init_thread_footer(&dword_1800E4824);
          }
        }
        HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1800E24B0, a1);
      }
      if ( v12 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      return 0;
    }
  }
  else
  {
    result = RtlNtStatusToDosError(v11);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180080c2c  push    rbp
0x180080c2e  push    rbx
0x180080c2f  push    rsi
0x180080c30  push    rdi
0x180080c31  push    r12
0x180080c33  push    r13
0x180080c35  push    r14
0x180080c37  push    r15
0x180080c39  lea     rbp, [rsp-18h]
0x180080c3e  sub     rsp, 118h
0x180080c45  mov     rax, cs:__security_cookie
0x180080c4c  xor     rax, rsp
0x180080c4f  mov     [rbp+50h+var_50], rax
0x180080c53  mov     r10, rcx
0x180080c56  mov     [rsp+150h+var_E8], rcx
0x180080c5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180080c5f  mov     [rsp+150h+var_F0], r9
0x180080c64  mov     [r8], rcx
0x180080c67  mov     r13, r8
0x180080c6a  mov     [rsp+150h+FileHandle], rcx
0x180080c6f  mov     r14d, edx
0x180080c72  mov     ecx, edx
0x180080c74  mov     dword ptr [r9], 0
0x180080c7b  and     ecx, 8
0x180080c7e  mov     eax, ecx
0x180080c80  neg     eax
0x180080c82  sbb     edi, edi
0x180080c84  and     edi, 0FFFFFFFEh
0x180080c87  add     edi, 3
0x180080c8a  test    dl, 40h
0x180080c8d  jz      short loc_180080C96
0x180080c8f  test    ecx, ecx
0x180080c91  jnz     short loc_180080CAD
0x180080c93  or      edi, 4
0x180080c96  mov     eax, r14d
0x180080c99  mov     ecx, r14d
0x180080c9c  and     eax, 3
0x180080c9f  mov     esi, 1
0x180080ca4  and     ecx, 20h
0x180080ca7  jz      short loc_180080CB7
0x180080ca9  cmp     eax, esi
0x180080cab  jb      short loc_180080CB7
0x180080cad  mov     eax, 80070057h
0x180080cb2  jmp     loc_180080F14
0x180080cb7  neg     ecx
0x180080cb9  lea     r12, qword_1800BE828
0x180080cc0  mov     r12d, [r12+rax*4]
0x180080cc4  lea     rdx, [rsp+150h+P]
0x180080cc9  sbb     r15d, r15d
0x180080ccc  xorps   xmm0, xmm0
0x180080ccf  xor     r9d, r9d
0x180080cd2  xor     r8d, r8d
0x180080cd5  mov     rcx, r10
0x180080cd8  and     r15d, 0FFFFFEFEh
0x180080cdf  movups  xmmword ptr [rsp+150h+P], xmm0
0x180080ce4  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180080cea  xor     ecx, ecx
0x180080cec  test    eax, eax
0x180080cee  jns     short loc_180080D0D
0x180080cf0  mov     ecx, eax; Status
0x180080cf2  call    cs:__imp_RtlNtStatusToDosError
0x180080cf8  test    eax, eax
0x180080cfa  jle     loc_180080F14
0x180080d00  movzx   eax, ax
0x180080d03  or      eax, 80070000h
0x180080d08  jmp     loc_180080F14
0x180080d0d  mov     rbx, [rbp+50h+P+8]
0x180080d11  lea     rax, [rsp+150h+P]
0x180080d16  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x180080d1a  lea     rax, [rbp+50h+var_88]
0x180080d1e  mov     [rbp+50h+ObjectAttributes.SecurityQualityOfService], rax
0x180080d22  xorps   xmm0, xmm0
0x180080d25  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x180080d2d  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x180080d35  mov     [rbp+50h+ObjectAttributes.RootDirectory], rcx
0x180080d39  mov     [rbp+50h+ObjectAttributes.SecurityDescriptor], rcx
0x180080d3d  mov     [rbp+50h+var_84], rcx
0x180080d41  mov     [rbp+50h+var_88], 0Ch
0x180080d48  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x180080d4c  bt      r14d, 0Ch
0x180080d51  jnb     loc_180080DDD
0x180080d57  movups  xmm1, cs:xmmword_1800BE838+0Ah
0x180080d5e  mov     [rsp+150h+EaLength], 28h ; '('; EaLength
0x180080d66  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x180080d6a  movups  xmmword ptr [rbp+50h+var_74], xmm0
0x180080d6e  xor     eax, eax
0x180080d70  mov     [rbp+50h+var_78], ecx
0x180080d73  movups  xmmword ptr [rbp+50h+var_74+10h], xmm0
0x180080d77  mov     [rbp+50h+var_54], eax
0x180080d7a  lea     rax, [rbp+50h+var_78]
0x180080d7e  movups  xmm0, cs:xmmword_1800BE838
0x180080d85  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x180080d8a  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x180080d8e  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x180080d96  lea     edx, [r15+100183h]; DesiredAccess
0x180080d9d  mov     [rsp+150h+CreateDisposition], r12d; CreateDisposition
0x180080da2  mov     [rsp+150h+ShareAccess], edi; ShareAccess
0x180080da6  movups  xmmword ptr [rbp+50h+var_74+4], xmm0
0x180080daa  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x180080db2  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x180080db7  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x180080dbc  mov     dword ptr [rbp+50h+var_74], 1A00h
0x180080dc3  movups  xmmword ptr [rbp+50h+var_74+0Eh], xmm1
0x180080dc7  call    cs:__imp_NtCreateFile
0x180080dcd  cmp     eax, 0C0000010h
0x180080dd2  jz      short loc_180080DDB
0x180080dd4  cmp     eax, 0C000004Fh
0x180080dd9  jnz     short loc_180080E1E
0x180080ddb  xor     ecx, ecx
0x180080ddd  mov     [rsp+150h+EaLength], ecx; EaLength
0x180080de1  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x180080de5  mov     [rsp+150h+EaBuffer], rcx; EaBuffer
0x180080dea  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x180080dee  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x180080df6  lea     edx, [r15+100183h]; DesiredAccess
0x180080dfd  mov     [rsp+150h+CreateDisposition], r12d; CreateDisposition
0x180080e02  mov     [rsp+150h+ShareAccess], edi; ShareAccess
0x180080e06  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x180080e0e  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x180080e13  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x180080e18  call    cs:__imp_NtCreateFile
0x180080e1e  test    eax, eax
0x180080e20  js      loc_180080EDE
0x180080e26  test    [rbp+50h+IoStatusBlock.Information], 0FFFFFFFFFFFFFFFCh
0x180080e2e  mov     rax, [rsp+150h+FileHandle]
0x180080e33  mov     [r13+0], rax
0x180080e37  jnz     short loc_180080E43
0x180080e39  cmp     [rbp+50h+IoStatusBlock.Information], rsi
0x180080e3d  jz      short loc_180080E43
0x180080e3f  mov     eax, esi
0x180080e41  jmp     short loc_180080E45
0x180080e43  xor     eax, eax
0x180080e45  mov     rcx, [rsp+150h+var_F0]
0x180080e4a  mov     r15d, 0C000h
0x180080e50  mov     [rcx], eax
0x180080e52  mov     ecx, r15d; unsigned __int16
0x180080e55  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180080e5a  test    eax, eax
0x180080e5c  mov     edi, eax
0x180080e5e  setnz   r14b
0x180080e62  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180080e67  mov     rcx, [rax+8]
0x180080e6b  test    rcx, rcx
0x180080e6e  jz      short loc_180080E76
0x180080e70  mov     ecx, [rcx]
0x180080e72  test    ecx, ecx
0x180080e74  jnz     short loc_180080E79
0x180080e76  xor     sil, sil
0x180080e79  test    edi, edi
0x180080e7b  jnz     short loc_180080E82
0x180080e7d  test    sil, sil
0x180080e80  jz      short loc_180080EBD
0x180080e82  mov     ecx, cs:_tls_index
0x180080e88  mov     rax, gs:58h
0x180080e91  mov     edx, 10h
0x180080e96  mov     rax, [rax+rcx*8]
0x180080e9a  mov     ecx, [rdx+rax]
0x180080e9d  cmp     cs:dword_1800E4824, ecx
0x180080ea3  jg      loc_180080F34
0x180080ea9  mov     r8, [rsp+150h+var_E8]
0x180080eae  lea     rdx, off_1800E24B0; struct HvsDebugTraceParameters *
0x180080eb5  mov     ecx, r15d; unsigned int
0x180080eb8  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180080ebd  test    rbx, rbx
0x180080ec0  jz      short loc_180080EDA
0x180080ec2  mov     rcx, gs:60h
0x180080ecb  mov     r8, rbx; P
0x180080ece  xor     edx, edx; Flags
0x180080ed0  mov     rcx, [rcx+30h]; HeapHandle
0x180080ed4  call    cs:__imp_RtlFreeHeap
0x180080eda  xor     eax, eax
0x180080edc  jmp     short loc_180080F14
0x180080ede  mov     ecx, eax; Status
0x180080ee0  call    cs:__imp_RtlNtStatusToDosError
0x180080ee6  mov     edi, eax
0x180080ee8  test    eax, eax
0x180080eea  jle     short loc_180080EF5
0x180080eec  movzx   edi, ax
0x180080eef  or      edi, 80070000h
0x180080ef5  test    rbx, rbx
0x180080ef8  jz      short loc_180080F12
0x180080efa  mov     rcx, gs:60h
0x180080f03  mov     r8, rbx; P
0x180080f06  xor     edx, edx; Flags
0x180080f08  mov     rcx, [rcx+30h]; HeapHandle
0x180080f0c  call    cs:__imp_RtlFreeHeap
0x180080f12  mov     eax, edi
0x180080f14  mov     rcx, [rbp+50h+var_50]
0x180080f18  xor     rcx, rsp; StackCookie
0x180080f1b  call    __security_check_cookie
0x180080f20  add     rsp, 118h
0x180080f27  pop     r15
0x180080f29  pop     r14
0x180080f2b  pop     r13
0x180080f2d  pop     r12
0x180080f2f  pop     rdi
0x180080f30  pop     rsi
0x180080f31  pop     rbx
0x180080f32  pop     rbp
0x180080f33  retn
0x180080f34  lea     rcx, dword_1800E4824
0x180080f3b  call    _Init_thread_header
0x180080f40  cmp     cs:dword_1800E4824, 0FFFFFFFFh
0x180080f47  jnz     loc_180080EA9
0x180080f4d  lea     rcx, dword_1800E4824
0x180080f54  mov     cs:byte_1800E24C4, r14b
0x180080f5b  mov     cs:byte_1800E24C5, sil
0x180080f62  call    _Init_thread_footer
0x180080f67  jmp     loc_180080EA9
```
