# CreateSystemDirectory

- ea: `0x180006b3c`
- end: `0x180006e0f`
- name: `CreateSystemDirectory`
- size: `723`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, ULONG)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006744`
- `0x18000c8c0`

## callees

- `0x180006b3c`
- `0x180006e18`
- `0x18000b250`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006cba`
- `ntdll!RtlNtStatusToDosError` at `0x180006cba`
- `ntdll!RtlFreeHeap` at `0x180006c60`
- `ntdll!RtlFreeHeap` at `0x180006c60`
- `ntdll!RtlReleaseRelativeName` at `0x180006c42`
- `ntdll!RtlReleaseRelativeName` at `0x180006c42`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180006b99`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180006b99`
- `ntdll!NtClose` at `0x180006d01`
- `ntdll!NtClose` at `0x180006d01`
- `ntdll!NtCreateFile` at `0x180006c30`
- `ntdll!NtCreateFile` at `0x180006c30`

## string_xrefs

- `0x180006c74`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180006da2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall CreateSystemDirectory(const WCHAR *a1, __int64 a2, ULONG a3)
{
  int v6; // edx
  int v7; // r8d
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  int v10; // esi
  int v11; // edx
  int v12; // r8d
  PVOID *v13; // rcx
  int v14; // edx
  ULONG v15; // edi
  int v16; // r8d
  PVOID *v18; // rcx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-39h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+118h] [rbp+7Fh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( RtlDosPathNameToRelativeNtPathName_U(a1, &NtName, 0, &RelativeName) )
  {
    Buffer = NtName.Buffer;
    if ( RelativeName.RelativeName.Length )
    {
      NtName = RelativeName.RelativeName;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    if ( a2 )
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(a2 + 8);
    else
      ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    v10 = NtCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 4u, 3u, a3, 0x4021u, 0, 0);
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( v10 >= 0 )
    {
      NtClose(FileHandle);
      return 0;
    }
    if ( v10 != -1073741771 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_12:
        v15 = RtlNtStatusToDosError(v10);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v16,
            (unsigned int)"Status",
            v10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
            156);
        return v15;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_9:
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
          WPP_SF_S(v13[2], 21, WPP_aa991306b93132f591cbba2128657ece_Traceguids, a1);
        goto LABEL_12;
      }
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v12,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        143);
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  v15 = 3;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"dwReturn",
        3,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        92);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_S(v18[2], 20, WPP_aa991306b93132f591cbba2128657ece_Traceguids, a1);
  }
  return v15;
}

```

## disassembly

```asm
0x180006b3c  mov     [rsp-8+arg_0], rbx
0x180006b41  mov     [rsp-8+arg_8], rsi
0x180006b46  push    rbp
0x180006b47  push    rdi
0x180006b48  push    r12
0x180006b4a  push    r14
0x180006b4c  push    r15
0x180006b4e  lea     rbp, [rsp-37h]
0x180006b53  sub     rsp, 0D0h
0x180006b5a  xorps   xmm0, xmm0
0x180006b5d  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x180006b61  mov     edi, r8d
0x180006b64  mov     rbx, rdx
0x180006b67  xorps   xmm1, xmm1
0x180006b6a  lea     rdx, [rbp+57h+NtName]; NtName
0x180006b6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006b72  xor     r12d, r12d
0x180006b75  xor     eax, eax
0x180006b77  xor     r8d, r8d; PartName
0x180006b7a  mov     [rbp+57h+FileHandle], r12
0x180006b7e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180006b82  mov     r15, rcx
0x180006b85  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006b89  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180006b8d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180006b91  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x180006b95  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x180006b99  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180006ba0  nop     dword ptr [rax+rax+00h]
0x180006ba5  test    al, al
0x180006ba7  jz      loc_180006D38
0x180006bad  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180006bb1  mov     r14, [rbp+57h+NtName.Buffer]
0x180006bb5  test    ax, ax
0x180006bb8  jnz     loc_180006D7B
0x180006bbe  mov     eax, r12d
0x180006bc1  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180006bc5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180006bc9  lea     rax, [rbp+57h+NtName]
0x180006bcd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006bd1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006bd8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180006bdf  test    rbx, rbx
0x180006be2  jz      loc_180006D2F
0x180006be8  mov     rax, [rbx+8]
0x180006bec  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180006bf0  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x180006bf5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180006bf9  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x180006bfe  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006c02  mov     [rsp+0F0h+CreateOptions], 4021h; CreateOptions
0x180006c0a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180006c0e  mov     [rsp+0F0h+CreateDisposition], edi; CreateDisposition
0x180006c12  mov     edx, 100001h; DesiredAccess
0x180006c17  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x180006c1f  mov     [rsp+0F0h+FileAttributes], 4; FileAttributes
0x180006c27  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x180006c2c  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x180006c30  call    cs:__imp_NtCreateFile
0x180006c37  nop     dword ptr [rax+rax+00h]
0x180006c3c  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180006c40  mov     esi, eax
0x180006c42  call    cs:__imp_RtlReleaseRelativeName
0x180006c49  nop     dword ptr [rax+rax+00h]
0x180006c4e  mov     rcx, gs:60h
0x180006c57  mov     r8, r14; P
0x180006c5a  xor     edx, edx; Flags
0x180006c5c  mov     rcx, [rcx+30h]; HeapHandle
0x180006c60  call    cs:__imp_RtlFreeHeap
0x180006c67  nop     dword ptr [rax+rax+00h]
0x180006c6c  test    esi, esi
0x180006c6e  jns     loc_180006CFD
0x180006c74  lea     r14, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006c7b  lea     rbx, WPP_GLOBAL_Control
0x180006c82  cmp     esi, 0C0000035h
0x180006c88  jnz     loc_180006DCF
0x180006c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c95  cmp     rcx, rbx
0x180006c98  jz      short loc_180006CB8
0x180006c9a  test    byte ptr [rcx+1Ch], 2
0x180006c9e  jz      short loc_180006CB8
0x180006ca0  mov     rcx, [rcx+10h]
0x180006ca4  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180006cab  mov     edx, 15h
0x180006cb0  mov     r9, r15
0x180006cb3  call    WPP_SF_S
0x180006cb8  mov     ecx, esi; Status
0x180006cba  call    cs:__imp_RtlNtStatusToDosError
0x180006cc1  nop     dword ptr [rax+rax+00h]
0x180006cc6  mov     edi, eax
0x180006cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ccf  cmp     rcx, rbx
0x180006cd2  jz      short loc_180006D10
0x180006cd4  test    byte ptr [rcx+1Ch], 1
0x180006cd8  jz      short loc_180006D10
0x180006cda  mov     rcx, [rcx+10h]
0x180006cde  lea     r9, aStatus; "Status"
0x180006ce5  mov     [rsp+0F0h+ShareAccess], 0F9Ch
0x180006ced  mov     qword ptr [rsp+0F0h+FileAttributes], r14
0x180006cf2  mov     dword ptr [rsp+0F0h+AllocationSize], esi
0x180006cf6  call    WPP_SF_sDsd
0x180006cfb  jmp     short loc_180006D10
0x180006cfd  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180006d01  call    cs:__imp_NtClose
0x180006d08  nop     dword ptr [rax+rax+00h]
0x180006d0d  mov     edi, r12d
0x180006d10  lea     r11, [rsp+0F0h+var_20]
0x180006d18  mov     eax, edi
0x180006d1a  mov     rbx, [r11+30h]
0x180006d1e  mov     rsi, [r11+38h]
0x180006d22  mov     rsp, r11
0x180006d25  pop     r15
0x180006d27  pop     r14
0x180006d29  pop     r12
0x180006d2b  pop     rdi
0x180006d2c  pop     rbp
0x180006d2d  retn
0x180006d2f  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x180006d33  jmp     loc_180006BF0
0x180006d38  mov     edi, 3
0x180006d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d44  lea     rbx, WPP_GLOBAL_Control
0x180006d4b  cmp     rcx, rbx
0x180006d4e  jz      short loc_180006D10
0x180006d50  test    byte ptr [rcx+1Ch], 1
0x180006d54  jnz     short loc_180006D9E
0x180006d56  cmp     rcx, rbx
0x180006d59  jz      short loc_180006D10
0x180006d5b  test    byte ptr [rcx+1Ch], 1
0x180006d5f  jz      short loc_180006D10
0x180006d61  mov     rcx, [rcx+10h]
0x180006d65  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180006d6c  mov     edx, 14h
0x180006d71  mov     r9, r15
0x180006d74  call    WPP_SF_S
0x180006d79  jmp     short loc_180006D10
0x180006d7b  mov     [rbp+57h+NtName.Length], ax
0x180006d7f  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180006d82  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x180006d85  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180006d89  mov     word ptr [rbp+57h+NtName+6], ax
0x180006d8d  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180006d91  mov     [rbp+57h+NtName.Buffer], rax
0x180006d95  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180006d99  jmp     loc_180006BC5
0x180006d9e  mov     rcx, [rcx+10h]
0x180006da2  lea     r14, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006da9  mov     [rsp+0F0h+ShareAccess], 0F5Ch
0x180006db1  lea     r9, aDwreturn; "dwReturn"
0x180006db8  mov     qword ptr [rsp+0F0h+FileAttributes], r14
0x180006dbd  mov     dword ptr [rsp+0F0h+AllocationSize], edi
0x180006dc1  call    WPP_SF_sDsd
0x180006dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dcd  jmp     short loc_180006D56
0x180006dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dd6  cmp     rcx, rbx
0x180006dd9  jz      loc_180006CB8
0x180006ddf  test    byte ptr [rcx+1Ch], 1
0x180006de3  jz      loc_180006C95
0x180006de9  mov     rcx, [rcx+10h]
0x180006ded  lea     r9, aStatus; "Status"
0x180006df4  mov     [rsp+0F0h+ShareAccess], 0F8Fh
0x180006dfc  mov     qword ptr [rsp+0F0h+FileAttributes], r14
0x180006e01  mov     dword ptr [rsp+0F0h+AllocationSize], esi
0x180006e05  call    WPP_SF_sDsd
0x180006e0a  jmp     loc_180006C8E
```
