# GetBinaryTypeW

- ea: `0x18003ca30`
- end: `0x18003cd72`
- name: `GetBinaryTypeW`
- size: `834`
- prototype: `BOOL __stdcall(LPCWSTR lpApplicationName, LPDWORD lpBinaryType)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b0b0`

## callees

- `0x18000f920`
- `0x18003ca30`
- `0x18006afb0`
- `0x18007a7dd`

## import_xrefs

- `ntdll!NtCreateSection` at `0x18003cbc0`
- `ntdll!NtCreateSection` at `0x18003cbc0`
- `ntdll!NtOpenFile` at `0x18003cb6a`
- `ntdll!NtOpenFile` at `0x18003cb6a`
- `ntdll!NtClose` at `0x18003cbd0`
- `ntdll!NtClose` at `0x18003cd6a`
- `ntdll!NtClose` at `0x18007b035`
- `ntdll!NtClose` at `0x18003cbd0`
- `ntdll!NtClose` at `0x18003cd6a`
- `ntdll!NtClose` at `0x18007b035`
- `ntdll!RtlSetLastWin32Error` at `0x18003ccff`
- `ntdll!RtlSetLastWin32Error` at `0x18003ccff`
- `ntdll!NtQuerySection` at `0x18003cbfb`
- `ntdll!NtQuerySection` at `0x18003cbfb`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003cab4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003cab4`
- `ntdll!RtlReleaseRelativeName` at `0x18003cb77`
- `ntdll!RtlReleaseRelativeName` at `0x18003cb77`
- `ntdll!RtlImageNtHeader` at `0x18003ccc4`
- `ntdll!RtlImageNtHeader` at `0x18003ccc4`
- `ntdll!RtlFreeHeap` at `0x18003cd49`
- `ntdll!RtlFreeHeap` at `0x18007b054`
- `ntdll!RtlFreeHeap` at `0x18003cd49`
- `ntdll!RtlFreeHeap` at `0x18007b054`

## pseudocode

```c
BOOL __stdcall GetBinaryTypeW(LPCWSTR lpApplicationName, LPDWORD lpBinaryType)
{
  PWSTR Buffer; // rsi
  DWORD v5; // ebx
  HANDLE ContainingDirectory; // rax
  NTSTATUS v7; // edi
  __int64 v8; // rcx
  BOOL v9; // edi
  NTSTATUS Section; // eax
  int IsDosApplication; // eax
  PIMAGE_NT_HEADERS v12; // rax
  int v13; // eax
  struct _UNICODE_STRING NtName; // [rsp+48h] [rbp-D0h] BYREF
  PWSTR v16; // [rsp+58h] [rbp-C0h]
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+60h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE SectionInformation[32]; // [rsp+C0h] [rbp-58h] BYREF
  int v21; // [rsp+E0h] [rbp-38h]
  __int16 v22; // [rsp+ECh] [rbp-2Ch]
  __int16 v23; // [rsp+F0h] [rbp-28h]
  void *SectionHandle; // [rsp+130h] [rbp+18h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+20h] BYREF

  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&ObjectAttributes, 0, 44);
  Buffer = 0;
  v16 = 0;
  FileHandle = 0;
  SectionHandle = 0;
  IoStatusBlock = 0;
  v5 = 6;
  memset_0(SectionInformation, 0, 0x40u);
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpApplicationName, &NtName, 0, &RelativeName) )
  {
    v8 = 3221225523LL;
    goto LABEL_7;
  }
  Buffer = NtName.Buffer;
  v16 = NtName.Buffer;
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
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100020u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  RtlReleaseRelativeName(&RelativeName);
  if ( v7 < 0 )
    goto LABEL_6;
  v7 = NtCreateSection(&SectionHandle, 0xF001Fu, 0, 0, 0x10u, 0x1000000u, FileHandle);
  NtClose(FileHandle);
  if ( v7 < 0 )
  {
    SectionHandle = 0;
    if ( v7 != -1073741541 )
    {
      if ( v7 == -1073741521 )
      {
        IsDosApplication = BaseIsDosApplication(&NtName, 3221225775LL);
        if ( IsDosApplication )
        {
          v9 = 1;
          v5 = 1;
          if ( IsDosApplication == 3 )
            v5 = 3;
          goto LABEL_37;
        }
LABEL_6:
        v8 = (unsigned int)v7;
LABEL_7:
        BaseSetLastNTError(v8);
LABEL_8:
        v9 = 0;
        goto LABEL_38;
      }
      if ( v7 != -1073741520 )
      {
        switch ( v7 )
        {
          case -1073741519:
            v5 = 2;
            break;
          case -1073740967:
            v5 = 0;
            break;
          case -1073740966:
            break;
          default:
            goto LABEL_6;
        }
        v9 = 1;
        goto LABEL_37;
      }
    }
    v9 = 1;
    v5 = 1;
    goto LABEL_37;
  }
  v9 = 1;
  Section = NtQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
  if ( Section < 0 )
  {
    v8 = (unsigned int)Section;
    goto LABEL_7;
  }
  if ( (v22 & 0x2000) != 0 )
    goto LABEL_33;
  v12 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  if ( v23 == v12->FileHeader.Machine )
  {
    v13 = 6;
    if ( v21 == 7 )
      v13 = 4;
    v5 = v13;
    goto LABEL_37;
  }
  if ( v23 != 332 )
  {
LABEL_33:
    RtlSetLastWin32Error(0xC1u);
    goto LABEL_8;
  }
  v5 = 0;
  if ( v21 == 7 )
    v5 = 4;
LABEL_37:
  *lpBinaryType = v5;
LABEL_38:
  if ( SectionHandle )
    NtClose(SectionHandle);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  return v9;
}

```

## disassembly

```asm
0x18003ca30  mov     r11, rsp
0x18003ca33  mov     [r11+8], rbx
0x18003ca37  mov     [r11+10h], rsi
0x18003ca3b  push    rdi
0x18003ca3c  push    r14
0x18003ca3e  push    r15
0x18003ca40  sub     rsp, 100h
0x18003ca47  mov     r14, rdx
0x18003ca4a  mov     rdi, rcx
0x18003ca4d  xorps   xmm0, xmm0
0x18003ca50  movups  xmmword ptr [rsp+118h+NtName.Length], xmm0
0x18003ca55  xorps   xmm1, xmm1
0x18003ca58  movups  xmmword ptr [rsp+118h+RelativeName.RelativeName.Length], xmm1
0x18003ca5d  movups  xmmword ptr [rsp+118h+RelativeName.ContainingDirectory], xmm1
0x18003ca62  xor     eax, eax
0x18003ca64  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x18003ca6c  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x18003ca74  movups  xmmword ptr [r11-7Ch], xmm0
0x18003ca79  xor     r15d, r15d
0x18003ca7c  mov     esi, r15d
0x18003ca7f  mov     [rsp+118h+var_C0], r15
0x18003ca84  mov     [r11+20h], r15
0x18003ca88  mov     [r11+18h], r15
0x18003ca8c  movups  xmmword ptr [r11-68h], xmm0
0x18003ca91  lea     ebx, [rax+6]
0x18003ca94  xor     edx, edx; Val
0x18003ca96  lea     r8d, [rax+40h]; Size
0x18003ca9a  lea     rcx, [r11-58h]; void *
0x18003ca9e  call    memset_0
0x18003caa3  nop
0x18003caa4  lea     r9, [rsp+118h+RelativeName]; RelativeName
0x18003caa9  xor     r8d, r8d; PartName
0x18003caac  lea     rdx, [rsp+118h+NtName]; NtName
0x18003cab1  mov     rcx, rdi; DosName
0x18003cab4  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18003caba  test    al, al
0x18003cabc  jz      loc_18003CC10
0x18003cac2  mov     rsi, [rsp+118h+NtName.Buffer]
0x18003cac7  mov     [rsp+118h+var_C0], rsi
0x18003cacc  movzx   eax, [rsp+118h+RelativeName.RelativeName.Length]
0x18003cad1  test    ax, ax
0x18003cad4  jnz     short loc_18003CAE0
0x18003cad6  mov     eax, r15d
0x18003cad9  mov     [rsp+118h+RelativeName.ContainingDirectory], rax
0x18003cade  jmp     short loc_18003CB06
0x18003cae0  mov     [rsp+118h+NtName.Length], ax
0x18003cae5  mov     eax, dword ptr [rsp+118h+RelativeName.RelativeName.MaximumLength]
0x18003cae9  mov     dword ptr [rsp+118h+NtName.MaximumLength], eax
0x18003caed  movzx   eax, word ptr [rsp+118h+RelativeName.RelativeName+6]
0x18003caf2  mov     word ptr [rsp+118h+NtName+6], ax
0x18003caf7  mov     rax, [rsp+118h+RelativeName.RelativeName.Buffer]
0x18003cafc  mov     [rsp+118h+NtName.Buffer], rax
0x18003cb01  mov     rax, [rsp+118h+RelativeName.ContainingDirectory]
0x18003cb06  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x18003cb11  mov     [rsp+118h+ObjectAttributes.RootDirectory], rax
0x18003cb19  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x18003cb24  lea     rax, [rsp+118h+NtName]
0x18003cb29  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x18003cb31  xorps   xmm0, xmm0
0x18003cb34  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003cb3d  mov     [rsp+118h+OpenOptions], 60h ; '`'; OpenOptions
0x18003cb45  mov     [rsp+118h+ShareAccess], 5; ShareAccess
0x18003cb4d  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x18003cb55  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x18003cb5d  mov     edx, 100020h; DesiredAccess
0x18003cb62  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x18003cb6a  call    cs:__imp_NtOpenFile
0x18003cb70  mov     edi, eax
0x18003cb72  lea     rcx, [rsp+118h+RelativeName]; RelativeName
0x18003cb77  call    cs:__imp_RtlReleaseRelativeName
0x18003cb7d  test    edi, edi
0x18003cb7f  jns     short loc_18003CB90
0x18003cb81  mov     ecx, edi
0x18003cb83  call    BaseSetLastNTError
0x18003cb88  mov     edi, r15d
0x18003cb8b  jmp     loc_18003CD25
0x18003cb90  mov     rax, [rsp+118h+FileHandle]
0x18003cb98  mov     [rsp+118h+var_E8], rax; FileHandle
0x18003cb9d  mov     [rsp+118h+OpenOptions], 1000000h; AllocationAttributes
0x18003cba5  mov     [rsp+118h+ShareAccess], 10h; SectionPageProtection
0x18003cbad  xor     r9d, r9d; MaximumSize
0x18003cbb0  xor     r8d, r8d; ObjectAttributes
0x18003cbb3  mov     edx, 0F001Fh; DesiredAccess
0x18003cbb8  lea     rcx, [rsp+118h+SectionHandle]; SectionHandle
0x18003cbc0  call    cs:__imp_NtCreateSection
0x18003cbc6  mov     edi, eax
0x18003cbc8  mov     rcx, [rsp+118h+FileHandle]; Handle
0x18003cbd0  call    cs:__imp_NtClose
0x18003cbd6  test    edi, edi
0x18003cbd8  js      short loc_18003CC1A
0x18003cbda  mov     qword ptr [rsp+118h+ShareAccess], r15; ResultLength
0x18003cbdf  mov     r9d, 40h ; '@'; Length
0x18003cbe5  lea     r8, [rsp+118h+SectionInformation]; SectionInformation
0x18003cbed  lea     edi, [r9-3Fh]
0x18003cbf1  mov     edx, edi; SectionInformationClass
0x18003cbf3  mov     rcx, [rsp+118h+SectionHandle]; SectionHandle
0x18003cbfb  call    cs:__imp_NtQuerySection
0x18003cc01  test    eax, eax
0x18003cc03  jns     loc_18003CCA8
0x18003cc09  mov     ecx, eax
0x18003cc0b  jmp     loc_18003CB83
0x18003cc10  mov     ecx, 0C0000033h
0x18003cc15  jmp     loc_18003CB83
0x18003cc1a  mov     [rsp+118h+SectionHandle], r15
0x18003cc22  cmp     edi, 0C000011Bh
0x18003cc28  jz      short loc_18003CC9F
0x18003cc2a  cmp     edi, 0C000012Fh
0x18003cc30  jz      short loc_18003CC6F
0x18003cc32  cmp     edi, 0C0000130h
0x18003cc38  jz      short loc_18003CC9F
0x18003cc3a  cmp     edi, 0C0000131h
0x18003cc40  jz      short loc_18003CC5C
0x18003cc42  cmp     edi, 0C0000359h
0x18003cc48  jz      short loc_18003CC57
0x18003cc4a  cmp     edi, 0C000035Ah
0x18003cc50  jz      short loc_18003CC61
0x18003cc52  jmp     loc_18003CB81
0x18003cc57  mov     ebx, r15d
0x18003cc5a  jmp     short loc_18003CC61
0x18003cc5c  mov     ebx, 2
0x18003cc61  mov     [rsp+118h+var_D8], ebx
0x18003cc65  mov     edi, 1
0x18003cc6a  jmp     loc_18003CD22
0x18003cc6f  mov     edx, edi
0x18003cc71  lea     rcx, [rsp+118h+NtName]
0x18003cc76  call    BaseIsDosApplication
0x18003cc7b  mov     [rsp+118h+var_D8], eax
0x18003cc7f  test    eax, eax
0x18003cc81  jz      loc_18003CB81
0x18003cc87  mov     edi, 1
0x18003cc8c  mov     ebx, edi
0x18003cc8e  lea     ecx, [rdi+2]
0x18003cc91  cmp     eax, ecx
0x18003cc93  cmovz   ebx, ecx
0x18003cc96  mov     [rsp+118h+var_D8], ebx
0x18003cc9a  jmp     loc_18003CD22
0x18003cc9f  mov     edi, 1
0x18003cca4  mov     ebx, edi
0x18003cca6  jmp     short loc_18003CC96
0x18003cca8  mov     eax, 2000h
0x18003ccad  test    [rsp+118h+var_2C], ax
0x18003ccb5  jnz     short loc_18003CCFA
0x18003ccb7  mov     rcx, gs:60h
0x18003ccc0  mov     rcx, [rcx+10h]; BaseAddress
0x18003ccc4  call    cs:__imp_RtlImageNtHeader
0x18003ccca  movzx   ecx, [rsp+118h+var_28]
0x18003ccd2  cmp     cx, [rax+4]
0x18003ccd6  jz      short loc_18003CD0A
0x18003ccd8  mov     eax, 14Ch
0x18003ccdd  cmp     cx, ax
0x18003cce0  jnz     short loc_18003CCFA
0x18003cce2  mov     ebx, r15d
0x18003cce5  mov     [rsp+118h+var_D8], ebx
0x18003cce9  cmp     [rsp+118h+var_38], 7
0x18003ccf1  jnz     short loc_18003CD22
0x18003ccf3  mov     ebx, 4
0x18003ccf8  jmp     short loc_18003CC96
0x18003ccfa  mov     ecx, 0C1h; LastError
0x18003ccff  call    cs:__imp_RtlSetLastWin32Error
0x18003cd05  jmp     loc_18003CB88
0x18003cd0a  mov     eax, ebx
0x18003cd0c  mov     ebx, 4
0x18003cd11  cmp     [rsp+118h+var_38], 7
0x18003cd19  cmovz   eax, ebx
0x18003cd1c  mov     ebx, eax
0x18003cd1e  mov     [rsp+118h+var_D8], eax
0x18003cd22  mov     [r14], ebx
0x18003cd25  mov     rcx, [rsp+118h+SectionHandle]; Handle
0x18003cd2d  test    rcx, rcx
0x18003cd30  jnz     short loc_18003CD6A
0x18003cd32  test    rsi, rsi
0x18003cd35  jz      short loc_18003CD4F
0x18003cd37  mov     rcx, gs:60h
0x18003cd40  mov     r8, rsi; P
0x18003cd43  xor     edx, edx; Flags
0x18003cd45  mov     rcx, [rcx+30h]; HeapHandle
0x18003cd49  call    cs:__imp_RtlFreeHeap
0x18003cd4f  mov     eax, edi
0x18003cd51  lea     r11, [rsp+118h+var_18]
0x18003cd59  mov     rbx, [r11+20h]
0x18003cd5d  mov     rsi, [r11+28h]
0x18003cd61  mov     rsp, r11
0x18003cd64  pop     r15
0x18003cd66  pop     r14
0x18003cd68  pop     rdi
0x18003cd69  retn
0x18003cd6a  call    cs:__imp_NtClose
0x18003cd70  jmp     short loc_18003CD32
0x18007b020  push    rbp
0x18007b022  sub     rsp, 40h
0x18007b026  mov     rbp, rdx
0x18007b029  mov     rcx, [rbp+130h]; Handle
0x18007b030  test    rcx, rcx
0x18007b033  jz      short loc_18007B03C
0x18007b035  call    cs:__imp_NtClose
0x18007b03b  nop
0x18007b03c  mov     r8, [rbp+58h]; P
0x18007b040  test    r8, r8
0x18007b043  jz      short loc_18007B05B
0x18007b045  mov     rcx, gs:60h
0x18007b04e  xor     edx, edx; Flags
0x18007b050  mov     rcx, [rcx+30h]; HeapHandle
0x18007b054  call    cs:__imp_RtlFreeHeap
0x18007b05a  nop
0x18007b05b  add     rsp, 40h
0x18007b05f  pop     rbp
0x18007b060  retn
```
