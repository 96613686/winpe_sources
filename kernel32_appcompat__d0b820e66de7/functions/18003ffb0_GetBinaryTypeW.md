# GetBinaryTypeW

- ea: `0x18003ffb0`
- end: `0x18004032f`
- name: `GetBinaryTypeW`
- size: `895`
- prototype: `BOOL __stdcall(LPCWSTR lpApplicationName, LPDWORD lpBinaryType)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800723f0`

## callees

- `0x18000ccf0`
- `0x18003ffb0`
- `0x1800722e0`
- `0x18008275d`

## import_xrefs

- `ntdll!NtCreateSection` at `0x180040152`
- `ntdll!NtCreateSection` at `0x180040152`
- `ntdll!NtOpenFile` at `0x1800400f0`
- `ntdll!NtOpenFile` at `0x1800400f0`
- `ntdll!NtClose` at `0x180040168`
- `ntdll!NtClose` at `0x180040321`
- `ntdll!NtClose` at `0x180083087`
- `ntdll!NtClose` at `0x180040168`
- `ntdll!NtClose` at `0x180040321`
- `ntdll!NtClose` at `0x180083087`
- `ntdll!RtlSetLastWin32Error` at `0x1800402a9`
- `ntdll!RtlSetLastWin32Error` at `0x1800402a9`
- `ntdll!NtQuerySection` at `0x180040199`
- `ntdll!NtQuerySection` at `0x180040199`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180040034`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180040034`
- `ntdll!RtlReleaseRelativeName` at `0x180040103`
- `ntdll!RtlReleaseRelativeName` at `0x180040103`
- `ntdll!RtlImageNtHeader` at `0x180040268`
- `ntdll!RtlImageNtHeader` at `0x180040268`
- `ntdll!RtlFreeHeap` at `0x1800402f9`
- `ntdll!RtlFreeHeap` at `0x1800830ac`
- `ntdll!RtlFreeHeap` at `0x1800402f9`
- `ntdll!RtlFreeHeap` at `0x1800830ac`

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
0x18003ffb0  mov     r11, rsp
0x18003ffb3  mov     [r11+8], rbx
0x18003ffb7  mov     [r11+10h], rsi
0x18003ffbb  push    rdi
0x18003ffbc  push    r14
0x18003ffbe  push    r15
0x18003ffc0  sub     rsp, 100h
0x18003ffc7  mov     r14, rdx
0x18003ffca  mov     rdi, rcx
0x18003ffcd  xorps   xmm0, xmm0
0x18003ffd0  movups  xmmword ptr [rsp+118h+NtName.Length], xmm0
0x18003ffd5  xorps   xmm1, xmm1
0x18003ffd8  movups  xmmword ptr [rsp+118h+RelativeName.RelativeName.Length], xmm1
0x18003ffdd  movups  xmmword ptr [rsp+118h+RelativeName.ContainingDirectory], xmm1
0x18003ffe2  xor     eax, eax
0x18003ffe4  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x18003ffec  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x18003fff4  movups  xmmword ptr [r11-7Ch], xmm0
0x18003fff9  xor     r15d, r15d
0x18003fffc  mov     esi, r15d
0x18003ffff  mov     [rsp+118h+var_C0], r15
0x180040004  mov     [r11+20h], r15
0x180040008  mov     [r11+18h], r15
0x18004000c  movups  xmmword ptr [r11-68h], xmm0
0x180040011  lea     ebx, [rax+6]
0x180040014  xor     edx, edx; Val
0x180040016  lea     r8d, [rax+40h]; Size
0x18004001a  lea     rcx, [r11-58h]; void *
0x18004001e  call    memset_0
0x180040023  nop
0x180040024  lea     r9, [rsp+118h+RelativeName]; RelativeName
0x180040029  xor     r8d, r8d; PartName
0x18004002c  lea     rdx, [rsp+118h+NtName]; NtName
0x180040031  mov     rcx, rdi; DosName
0x180040034  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18004003b  nop     dword ptr [rax+rax+00h]
0x180040040  test    al, al
0x180040042  jz      loc_1800401B4
0x180040048  mov     rsi, [rsp+118h+NtName.Buffer]
0x18004004d  mov     [rsp+118h+var_C0], rsi
0x180040052  movzx   eax, [rsp+118h+RelativeName.RelativeName.Length]
0x180040057  test    ax, ax
0x18004005a  jnz     short loc_180040066
0x18004005c  mov     eax, r15d
0x18004005f  mov     [rsp+118h+RelativeName.ContainingDirectory], rax
0x180040064  jmp     short loc_18004008C
0x180040066  mov     [rsp+118h+NtName.Length], ax
0x18004006b  mov     eax, dword ptr [rsp+118h+RelativeName.RelativeName.MaximumLength]
0x18004006f  mov     dword ptr [rsp+118h+NtName.MaximumLength], eax
0x180040073  movzx   eax, word ptr [rsp+118h+RelativeName.RelativeName+6]
0x180040078  mov     word ptr [rsp+118h+NtName+6], ax
0x18004007d  mov     rax, [rsp+118h+RelativeName.RelativeName.Buffer]
0x180040082  mov     [rsp+118h+NtName.Buffer], rax
0x180040087  mov     rax, [rsp+118h+RelativeName.ContainingDirectory]
0x18004008c  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x180040097  mov     [rsp+118h+ObjectAttributes.RootDirectory], rax
0x18004009f  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x1800400aa  lea     rax, [rsp+118h+NtName]
0x1800400af  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x1800400b7  xorps   xmm0, xmm0
0x1800400ba  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800400c3  mov     [rsp+118h+OpenOptions], 60h ; '`'; OpenOptions
0x1800400cb  mov     [rsp+118h+ShareAccess], 5; ShareAccess
0x1800400d3  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800400db  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x1800400e3  mov     edx, 100020h; DesiredAccess
0x1800400e8  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x1800400f0  call    cs:__imp_NtOpenFile
0x1800400f7  nop     dword ptr [rax+rax+00h]
0x1800400fc  mov     edi, eax
0x1800400fe  lea     rcx, [rsp+118h+RelativeName]; RelativeName
0x180040103  call    cs:__imp_RtlReleaseRelativeName
0x18004010a  nop     dword ptr [rax+rax+00h]
0x18004010f  test    edi, edi
0x180040111  jns     short loc_180040122
0x180040113  mov     ecx, edi
0x180040115  call    BaseSetLastNTError
0x18004011a  mov     edi, r15d
0x18004011d  jmp     loc_1800402D5
0x180040122  mov     rax, [rsp+118h+FileHandle]
0x18004012a  mov     [rsp+118h+var_E8], rax; FileHandle
0x18004012f  mov     [rsp+118h+OpenOptions], 1000000h; AllocationAttributes
0x180040137  mov     [rsp+118h+ShareAccess], 10h; SectionPageProtection
0x18004013f  xor     r9d, r9d; MaximumSize
0x180040142  xor     r8d, r8d; ObjectAttributes
0x180040145  mov     edx, 0F001Fh; DesiredAccess
0x18004014a  lea     rcx, [rsp+118h+SectionHandle]; SectionHandle
0x180040152  call    cs:__imp_NtCreateSection
0x180040159  nop     dword ptr [rax+rax+00h]
0x18004015e  mov     edi, eax
0x180040160  mov     rcx, [rsp+118h+FileHandle]; Handle
0x180040168  call    cs:__imp_NtClose
0x18004016f  nop     dword ptr [rax+rax+00h]
0x180040174  test    edi, edi
0x180040176  js      short loc_1800401BE
0x180040178  mov     qword ptr [rsp+118h+ShareAccess], r15; ResultLength
0x18004017d  mov     r9d, 40h ; '@'; Length
0x180040183  lea     r8, [rsp+118h+SectionInformation]; SectionInformation
0x18004018b  lea     edi, [r9-3Fh]
0x18004018f  mov     edx, edi; SectionInformationClass
0x180040191  mov     rcx, [rsp+118h+SectionHandle]; SectionHandle
0x180040199  call    cs:__imp_NtQuerySection
0x1800401a0  nop     dword ptr [rax+rax+00h]
0x1800401a5  test    eax, eax
0x1800401a7  jns     loc_18004024C
0x1800401ad  mov     ecx, eax
0x1800401af  jmp     loc_180040115
0x1800401b4  mov     ecx, 0C0000033h
0x1800401b9  jmp     loc_180040115
0x1800401be  mov     [rsp+118h+SectionHandle], r15
0x1800401c6  cmp     edi, 0C000011Bh
0x1800401cc  jz      short loc_180040243
0x1800401ce  cmp     edi, 0C000012Fh
0x1800401d4  jz      short loc_180040213
0x1800401d6  cmp     edi, 0C0000130h
0x1800401dc  jz      short loc_180040243
0x1800401de  cmp     edi, 0C0000131h
0x1800401e4  jz      short loc_180040200
0x1800401e6  cmp     edi, 0C0000359h
0x1800401ec  jz      short loc_1800401FB
0x1800401ee  cmp     edi, 0C000035Ah
0x1800401f4  jz      short loc_180040205
0x1800401f6  jmp     loc_180040113
0x1800401fb  mov     ebx, r15d
0x1800401fe  jmp     short loc_180040205
0x180040200  mov     ebx, 2
0x180040205  mov     [rsp+118h+var_D8], ebx
0x180040209  mov     edi, 1
0x18004020e  jmp     loc_1800402D2
0x180040213  mov     edx, edi
0x180040215  lea     rcx, [rsp+118h+NtName]
0x18004021a  call    BaseIsDosApplication
0x18004021f  mov     [rsp+118h+var_D8], eax
0x180040223  test    eax, eax
0x180040225  jz      loc_180040113
0x18004022b  mov     edi, 1
0x180040230  mov     ebx, edi
0x180040232  lea     ecx, [rdi+2]
0x180040235  cmp     eax, ecx
0x180040237  cmovz   ebx, ecx
0x18004023a  mov     [rsp+118h+var_D8], ebx
0x18004023e  jmp     loc_1800402D2
0x180040243  mov     edi, 1
0x180040248  mov     ebx, edi
0x18004024a  jmp     short loc_18004023A
0x18004024c  mov     eax, 2000h
0x180040251  test    [rsp+118h+var_2C], ax
0x180040259  jnz     short loc_1800402A4
0x18004025b  mov     rcx, gs:60h
0x180040264  mov     rcx, [rcx+10h]; BaseAddress
0x180040268  call    cs:__imp_RtlImageNtHeader
0x18004026f  nop     dword ptr [rax+rax+00h]
0x180040274  movzx   ecx, [rsp+118h+var_28]
0x18004027c  cmp     cx, [rax+4]
0x180040280  jz      short loc_1800402BA
0x180040282  mov     eax, 14Ch
0x180040287  cmp     cx, ax
0x18004028a  jnz     short loc_1800402A4
0x18004028c  mov     ebx, r15d
0x18004028f  mov     [rsp+118h+var_D8], ebx
0x180040293  cmp     [rsp+118h+var_38], 7
0x18004029b  jnz     short loc_1800402D2
0x18004029d  mov     ebx, 4
0x1800402a2  jmp     short loc_18004023A
0x1800402a4  mov     ecx, 0C1h; LastError
0x1800402a9  call    cs:__imp_RtlSetLastWin32Error
0x1800402b0  nop     dword ptr [rax+rax+00h]
0x1800402b5  jmp     loc_18004011A
0x1800402ba  mov     eax, ebx
0x1800402bc  mov     ebx, 4
0x1800402c1  cmp     [rsp+118h+var_38], 7
0x1800402c9  cmovz   eax, ebx
0x1800402cc  mov     ebx, eax
0x1800402ce  mov     [rsp+118h+var_D8], eax
0x1800402d2  mov     [r14], ebx
0x1800402d5  mov     rcx, [rsp+118h+SectionHandle]; Handle
0x1800402dd  test    rcx, rcx
0x1800402e0  jnz     short loc_180040321
0x1800402e2  test    rsi, rsi
0x1800402e5  jz      short loc_180040305
0x1800402e7  mov     rcx, gs:60h
0x1800402f0  mov     r8, rsi; P
0x1800402f3  xor     edx, edx; Flags
0x1800402f5  mov     rcx, [rcx+30h]; HeapHandle
0x1800402f9  call    cs:__imp_RtlFreeHeap
0x180040300  nop     dword ptr [rax+rax+00h]
0x180040305  mov     eax, edi
0x180040307  lea     r11, [rsp+118h+var_18]
0x18004030f  mov     rbx, [r11+20h]
0x180040313  mov     rsi, [r11+28h]
0x180040317  mov     rsp, r11
0x18004031a  pop     r15
0x18004031c  pop     r14
0x18004031e  pop     rdi
0x18004031f  retn
0x180040321  call    cs:__imp_NtClose
0x180040328  nop     dword ptr [rax+rax+00h]
0x18004032d  jmp     short loc_1800402E2
0x180083072  push    rbp
0x180083074  sub     rsp, 40h
0x180083078  mov     rbp, rdx
0x18008307b  mov     rcx, [rbp+130h]; Handle
0x180083082  test    rcx, rcx
0x180083085  jz      short loc_180083094
0x180083087  call    cs:__imp_NtClose
0x18008308e  nop     dword ptr [rax+rax+00h]
0x180083093  nop
0x180083094  mov     r8, [rbp+58h]; P
0x180083098  test    r8, r8
0x18008309b  jz      short loc_1800830B9
0x18008309d  mov     rcx, gs:60h
0x1800830a6  xor     edx, edx; Flags
0x1800830a8  mov     rcx, [rcx+30h]; HeapHandle
0x1800830ac  call    cs:__imp_RtlFreeHeap
0x1800830b3  nop     dword ptr [rax+rax+00h]
0x1800830b8  nop
0x1800830b9  add     rsp, 40h
0x1800830bd  pop     rbp
0x1800830be  retn
```
