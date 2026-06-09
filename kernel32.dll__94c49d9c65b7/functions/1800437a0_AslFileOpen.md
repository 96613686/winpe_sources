# AslFileOpen

- ea: `0x1800437a0`
- end: `0x180043a35`
- name: `AslFileOpen`
- size: `661`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022250`

## callees

- `0x180021144`
- `0x1800212e4`
- `0x1800437a0`
- `0x18005c414`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800438fd`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800438fd`
- `ntdll!RtlFreeUnicodeString` at `0x1800439f7`
- `ntdll!RtlFreeUnicodeString` at `0x1800439f7`
- `ntdll!RtlGetFullPathName_UEx` at `0x180043869`
- `ntdll!RtlGetFullPathName_UEx` at `0x180043869`
- `ntdll!ZwCreateFile` at `0x18004398b`
- `ntdll!ZwCreateFile` at `0x18004398b`
- `ntdll!RtlInitUnicodeString` at `0x1800437e7`
- `ntdll!RtlInitUnicodeString` at `0x1800437e7`
- `ntdll!RtlAllocateHeap` at `0x180043843`
- `ntdll!RtlAllocateHeap` at `0x180043843`

## string_xrefs

- `0x1800438bc`: `AslFileOpen`
- `0x1800439b3`: `AslFileOpen`
- `0x1800439d7`: `AslFileOpen`
- `0x1800438af`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x1800439a6`: `Failed to get full path [%x]`
- `0x180043909`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`
- `0x180043997`: `NtCreateFile failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileOpen(PHANDLE FileHandle, PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v5; // r14
  RTL_PATH_TYPE v6; // esi
  NTSTATUS FullPathName_UEx; // eax
  unsigned int v8; // ebx
  bool v9; // cf
  const char *v10; // r9
  int v11; // r8d
  char InputPathType; // [rsp+20h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  RTL_PATH_TYPE v17; // [rsp+E0h] [rbp+67h] BYREF

  *FileHandle = 0;
  v17 = RtlPathTypeUnknown;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  if ( DestinationString.Length <= 8u
    || *DestinationString.Buffer != 92
    || DestinationString.Buffer[1] != 92 && DestinationString.Buffer[1] != 63
    || DestinationString.Buffer[2] != 63
    || (Heap = 0, DestinationString.Buffer[3] != 92) )
  {
    v5 = 0;
    v6 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v6);
      if ( !Heap )
      {
        AslLogCallPrintf(1, (unsigned int)"AslFileOpen", 1843, (unsigned int)"Out of memory", InputPathType);
        v8 = -1073741801;
        goto LABEL_24;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v6, Heap, 0, &v17);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "Failed to get full path [%x]";
        v11 = 1854;
        goto LABEL_22;
      }
      v9 = v17 < (unsigned int)v6;
      if ( v17 > (unsigned int)v6 )
      {
        if ( v5 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslFileOpen",
            1862,
            (unsigned int)"RtlGetFullPathName_UEx failed to get full path with larger buffer.",
            InputPathType);
          v8 = -1073741789;
          goto LABEL_24;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v6 = v17;
        v9 = 0;
      }
      if ( v9 )
        break;
      v5 = 1;
    }
    if ( wcsnicmp_0(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v11 = 1885;
        goto LABEL_22;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FullPathName_UEx = ZwCreateFile(
                       FileHandle,
                       0x80100080,
                       &ObjectAttributes,
                       &IoStatusBlock,
                       0,
                       0x80u,
                       1u,
                       1u,
                       0x60u,
                       0,
                       0);
  v8 = FullPathName_UEx;
  if ( FullPathName_UEx < 0 )
  {
    v10 = "NtCreateFile failed [%x]";
    v11 = 1910;
LABEL_22:
    AslLogCallPrintf(1, (unsigned int)"AslFileOpen", v11, (_DWORD)v10, FullPathName_UEx);
  }
LABEL_24:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v8;
}

```

## disassembly

```asm
0x1800437a0  mov     [rsp-8+arg_8], rbx
0x1800437a5  mov     [rsp-8+arg_10], rsi
0x1800437aa  push    rbp
0x1800437ab  push    rdi
0x1800437ac  push    r12
0x1800437ae  push    r14
0x1800437b0  push    r15
0x1800437b2  lea     rbp, [rsp-37h]
0x1800437b7  sub     rsp, 0B0h
0x1800437be  xorps   xmm0, xmm0
0x1800437c1  xor     eax, eax
0x1800437c3  mov     [rcx], rax
0x1800437c6  mov     r12, rcx
0x1800437c9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800437cd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800437d1  mov     [rbp+57h+arg_0], eax
0x1800437d4  mov     r15, rdx
0x1800437d7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800437db  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800437df  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800437e3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800437e7  call    cs:__imp_RtlInitUnicodeString
0x1800437ed  mov     eax, 8
0x1800437f2  cmp     [rbp+57h+DestinationString.Length], ax
0x1800437f6  jbe     short loc_180043829
0x1800437f8  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1800437fc  cmp     word ptr [rax], 5Ch ; '\'
0x180043800  jnz     short loc_180043824
0x180043802  cmp     word ptr [rax+2], 5Ch ; '\'
0x180043807  jz      short loc_180043810
0x180043809  cmp     word ptr [rax+2], 3Fh ; '?'
0x18004380e  jnz     short loc_180043824
0x180043810  cmp     word ptr [rax+4], 3Fh ; '?'
0x180043815  jnz     short loc_180043824
0x180043817  xor     edi, edi
0x180043819  cmp     word ptr [rax+6], 5Ch ; '\'
0x18004381e  jz      loc_18004391B
0x180043824  mov     eax, 8
0x180043829  xor     r14b, r14b
0x18004382c  mov     esi, 208h
0x180043831  mov     rcx, gs:60h
0x18004383a  mov     edx, eax; Flags
0x18004383c  mov     r8d, esi; Size
0x18004383f  mov     rcx, [rcx+30h]; HeapHandle
0x180043843  call    cs:__imp_RtlAllocateHeap
0x180043849  mov     rdi, rax
0x18004384c  test    rax, rax
0x18004384f  jz      loc_1800439CA
0x180043855  lea     rax, [rbp+57h+arg_0]
0x180043859  xor     r9d, r9d; FilePart
0x18004385c  mov     r8, rdi; Buffer
0x18004385f  mov     [rsp+0D0h+InputPathType], rax; InputPathType
0x180043864  mov     edx, esi; BufferLength
0x180043866  mov     rcx, r15; FileName
0x180043869  call    cs:__imp_RtlGetFullPathName_UEx
0x18004386f  mov     ebx, eax
0x180043871  test    eax, eax
0x180043873  js      loc_1800439A6
0x180043879  mov     eax, [rbp+57h+arg_0]
0x18004387c  cmp     eax, esi
0x18004387e  jbe     short loc_1800438A3
0x180043880  test    r14b, r14b
0x180043883  jnz     short loc_1800438AF
0x180043885  mov     rcx, gs:60h
0x18004388e  mov     rdx, rdi
0x180043891  mov     rcx, [rcx+30h]
0x180043895  call    AslFree
0x18004389a  mov     eax, [rbp+57h+arg_0]
0x18004389d  xor     edi, edi
0x18004389f  mov     esi, eax
0x1800438a1  cmp     eax, eax
0x1800438a3  jb      short loc_1800438D7
0x1800438a5  mov     r14b, 1
0x1800438a8  mov     eax, 8
0x1800438ad  jmp     short loc_180043831
0x1800438af  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x1800438b6  mov     r8d, 746h
0x1800438bc  lea     rdx, aAslfileopen; "AslFileOpen"
0x1800438c3  mov     ecx, 1
0x1800438c8  call    AslLogCallPrintf
0x1800438cd  mov     ebx, 0C0000023h
0x1800438d2  jmp     loc_1800439ED
0x1800438d7  mov     r8d, 0Ch; MaxCount
0x1800438dd  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x1800438e4  mov     rcx, rdi; String1
0x1800438e7  call    _wcsnicmp_0
0x1800438ec  test    eax, eax
0x1800438ee  jz      short loc_18004391B
0x1800438f0  xor     r9d, r9d
0x1800438f3  lea     rdx, [rbp+57h+DestinationString]
0x1800438f7  xor     r8d, r8d
0x1800438fa  mov     rcx, rdi
0x1800438fd  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180043903  mov     ebx, eax
0x180043905  test    eax, eax
0x180043907  jns     short loc_18004391B
0x180043909  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180043910  mov     r8d, 75Dh
0x180043916  jmp     loc_1800439B3
0x18004391b  mov     [rsp+0D0h+EaLength], 0; EaLength
0x180043923  lea     rax, [rbp+57h+DestinationString]
0x180043927  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x180043930  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180043934  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x18004393c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180043940  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x180043948  xorps   xmm0, xmm0
0x18004394b  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x180043953  mov     edx, 80100080h; DesiredAccess
0x180043958  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180043960  mov     rcx, r12; FileHandle
0x180043963  mov     [rsp+0D0h+InputPathType], 0; AllocationSize
0x18004396c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180043973  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18004397b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180043982  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180043986  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004398b  call    cs:__imp_ZwCreateFile
0x180043991  mov     ebx, eax
0x180043993  test    eax, eax
0x180043995  jns     short loc_1800439ED
0x180043997  lea     r9, aNtcreatefileFa; "NtCreateFile failed [%x]"
0x18004399e  mov     r8d, 776h
0x1800439a4  jmp     short loc_1800439B3
0x1800439a6  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1800439ad  mov     r8d, 73Eh
0x1800439b3  lea     rdx, aAslfileopen; "AslFileOpen"
0x1800439ba  mov     dword ptr [rsp+0D0h+InputPathType], eax
0x1800439be  mov     ecx, 1
0x1800439c3  call    AslLogCallPrintf
0x1800439c8  jmp     short loc_1800439ED
0x1800439ca  lea     r9, aOutOfMemory; "Out of memory"
0x1800439d1  mov     r8d, 733h
0x1800439d7  lea     rdx, aAslfileopen; "AslFileOpen"
0x1800439de  mov     ecx, 1
0x1800439e3  call    AslLogCallPrintf
0x1800439e8  mov     ebx, 0C0000017h
0x1800439ed  cmp     [rbp+57h+DestinationString.Buffer], r15
0x1800439f1  jz      short loc_1800439FD
0x1800439f3  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800439f7  call    cs:__imp_RtlFreeUnicodeString
0x1800439fd  test    rdi, rdi
0x180043a00  jz      short loc_180043A17
0x180043a02  mov     rcx, gs:60h
0x180043a0b  mov     rdx, rdi
0x180043a0e  mov     rcx, [rcx+30h]
0x180043a12  call    AslFree
0x180043a17  lea     r11, [rsp+0D0h+var_20]
0x180043a1f  mov     eax, ebx
0x180043a21  mov     rbx, [r11+38h]
0x180043a25  mov     rsi, [r11+40h]
0x180043a29  mov     rsp, r11
0x180043a2c  pop     r15
0x180043a2e  pop     r14
0x180043a30  pop     r12
0x180043a32  pop     rdi
0x180043a33  pop     rbp
0x180043a34  retn
```
