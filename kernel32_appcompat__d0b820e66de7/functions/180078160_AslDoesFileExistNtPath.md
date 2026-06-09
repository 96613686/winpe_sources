# AslDoesFileExistNtPath

- ea: `0x180078160`
- end: `0x1800783f5`
- name: `AslDoesFileExistNtPath`
- size: `661`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ef04`

## callees

- `0x18001ef8c`
- `0x18001f138`
- `0x180061df4`
- `0x180078160`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800782c6`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800782c6`
- `ntdll!RtlFreeUnicodeString` at `0x1800783b0`
- `ntdll!RtlFreeUnicodeString` at `0x1800783b0`
- `ntdll!RtlGetFullPathName_UEx` at `0x180078237`
- `ntdll!RtlGetFullPathName_UEx` at `0x180078237`
- `ntdll!ZwClose` at `0x180078356`
- `ntdll!ZwClose` at `0x180078356`
- `ntdll!ZwOpenFile` at `0x18007832c`
- `ntdll!ZwOpenFile` at `0x18007832c`
- `ntdll!RtlInitUnicodeString` at `0x1800781a6`
- `ntdll!RtlInitUnicodeString` at `0x1800781a6`
- `ntdll!RtlAllocateHeap` at `0x18007820b`
- `ntdll!RtlAllocateHeap` at `0x18007820b`

## string_xrefs

- `0x18007828c`: `AslDoesFileExistNtPath`
- `0x180078371`: `AslDoesFileExistNtPath`
- `0x180078397`: `AslDoesFileExistNtPath`
- `0x18007827f`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x180078364`: `Failed to get full path [%x]`
- `0x1800782d6`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

## pseudocode

```c
__int64 __fastcall AslDoesFileExistNtPath(PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v3; // si
  RTL_PATH_TYPE v4; // ebx
  NTSTATUS FullPathName_UEx; // eax
  bool v6; // cf
  const char *v7; // r9
  int v8; // r8d
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  char InputPathType; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  RTL_PATH_TYPE v16; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  FileHandle = 0;
  v16 = RtlPathTypeUnknown;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  if ( DestinationString.Length <= 8u
    || *DestinationString.Buffer != 92
    || DestinationString.Buffer[1] != 92 && DestinationString.Buffer[1] != 63
    || DestinationString.Buffer[2] != 63
    || (Heap = 0, DestinationString.Buffer[3] != 92) )
  {
    v3 = 0;
    v4 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v4);
      if ( !Heap )
      {
        v10 = 0;
        AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", 658, (unsigned int)"Out of memory", InputPathType);
        goto LABEL_28;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v4, Heap, 0, &v16);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "Failed to get full path [%x]";
        v8 = 669;
        goto LABEL_25;
      }
      v6 = v16 < (unsigned int)v4;
      if ( v16 > (unsigned int)v4 )
      {
        if ( v3 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslDoesFileExistNtPath",
            678,
            (unsigned int)"RtlGetFullPathName_UEx failed to get full path with larger buffer.",
            InputPathType);
          goto LABEL_26;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v4 = v16;
        v6 = 0;
      }
      if ( v6 )
        break;
      v3 = 1;
    }
    if ( wcsnicmp_0(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v8 = 701;
LABEL_25:
        AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", v8, (_DWORD)v7, FullPathName_UEx);
        goto LABEL_26;
      }
    }
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  if ( v9 >= 0 )
  {
    v10 = 1;
    ZwClose(FileHandle);
  }
  else if ( v9 == -1073741757 || v9 == -1073741790 )
  {
    v10 = 1;
  }
  else
  {
LABEL_26:
    v10 = 0;
  }
LABEL_28:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v10;
}

```

## disassembly

```asm
0x180078160  mov     [rsp-28h+arg_10], rbx
0x180078165  mov     [rsp-28h+arg_18], rsi
0x18007816a  push    rbp
0x18007816b  push    rdi
0x18007816c  push    r12
0x18007816e  push    r13
0x180078170  push    r14
0x180078172  mov     rbp, rsp
0x180078175  sub     rsp, 80h
0x18007817c  xorps   xmm0, xmm0
0x18007817f  xor     eax, eax
0x180078181  mov     r14, rcx
0x180078184  mov     [rbp+FileHandle], rax
0x180078188  mov     rdx, rcx; SourceString
0x18007818b  mov     [rbp+arg_0], eax
0x18007818e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180078192  lea     rcx, [rbp+DestinationString]; DestinationString
0x180078196  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18007819a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007819e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800781a2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800781a6  call    cs:__imp_RtlInitUnicodeString
0x1800781ad  nop     dword ptr [rax+rax+00h]
0x1800781b2  mov     r12d, 1
0x1800781b8  lea     r13d, [r12+7]
0x1800781bd  cmp     [rbp+DestinationString.Length], r13w
0x1800781c2  jbe     short loc_1800781F0
0x1800781c4  mov     rax, [rbp+DestinationString.Buffer]
0x1800781c8  cmp     word ptr [rax], 5Ch ; '\'
0x1800781cc  jnz     short loc_1800781F0
0x1800781ce  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800781d3  jz      short loc_1800781DC
0x1800781d5  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800781da  jnz     short loc_1800781F0
0x1800781dc  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800781e1  jnz     short loc_1800781F0
0x1800781e3  xor     edi, edi
0x1800781e5  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800781ea  jz      loc_1800782E8
0x1800781f0  xor     sil, sil
0x1800781f3  mov     ebx, 208h
0x1800781f8  mov     rcx, gs:60h
0x180078201  mov     edx, r13d; Flags
0x180078204  mov     r8d, ebx; Size
0x180078207  mov     rcx, [rcx+30h]; HeapHandle
0x18007820b  call    cs:__imp_RtlAllocateHeap
0x180078212  nop     dword ptr [rax+rax+00h]
0x180078217  mov     rdi, rax
0x18007821a  test    rax, rax
0x18007821d  jz      loc_180078388
0x180078223  lea     rax, [rbp+arg_0]
0x180078227  xor     r9d, r9d; FilePart
0x18007822a  mov     r8, rdi; Buffer
0x18007822d  mov     [rsp+80h+InputPathType], rax; InputPathType
0x180078232  mov     edx, ebx; BufferLength
0x180078234  mov     rcx, r14; FileName
0x180078237  call    cs:__imp_RtlGetFullPathName_UEx
0x18007823e  nop     dword ptr [rax+rax+00h]
0x180078243  test    eax, eax
0x180078245  js      loc_180078364
0x18007824b  mov     eax, [rbp+arg_0]
0x18007824e  cmp     eax, ebx
0x180078250  jbe     short loc_180078275
0x180078252  test    sil, sil
0x180078255  jnz     short loc_18007827F
0x180078257  mov     rcx, gs:60h
0x180078260  mov     rdx, rdi
0x180078263  mov     rcx, [rcx+30h]
0x180078267  call    AslFree
0x18007826c  mov     eax, [rbp+arg_0]
0x18007826f  xor     edi, edi
0x180078271  mov     ebx, eax
0x180078273  cmp     eax, eax
0x180078275  jb      short loc_1800782A0
0x180078277  mov     sil, r12b
0x18007827a  jmp     loc_1800781F8
0x18007827f  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x180078286  mov     r8d, 2A6h
0x18007828c  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180078293  mov     ecx, r12d
0x180078296  call    AslLogCallPrintf
0x18007829b  jmp     loc_180078384
0x1800782a0  mov     r8d, 0Ch; MaxCount
0x1800782a6  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x1800782ad  mov     rcx, rdi; String1
0x1800782b0  call    _wcsnicmp_0
0x1800782b5  test    eax, eax
0x1800782b7  jz      short loc_1800782E8
0x1800782b9  xor     r9d, r9d
0x1800782bc  lea     rdx, [rbp+DestinationString]
0x1800782c0  xor     r8d, r8d
0x1800782c3  mov     rcx, rdi
0x1800782c6  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800782cd  nop     dword ptr [rax+rax+00h]
0x1800782d2  test    eax, eax
0x1800782d4  jns     short loc_1800782E8
0x1800782d6  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800782dd  mov     r8d, 2BDh
0x1800782e3  jmp     loc_180078371
0x1800782e8  lea     rax, [rbp+DestinationString]
0x1800782ec  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800782f4  xorps   xmm0, xmm0
0x1800782f7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800782fb  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800782ff  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180078306  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007830a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180078312  mov     edx, 100080h; DesiredAccess
0x180078317  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007831e  lea     rcx, [rbp+FileHandle]; FileHandle
0x180078322  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x180078327  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007832c  call    cs:__imp_ZwOpenFile
0x180078333  nop     dword ptr [rax+rax+00h]
0x180078338  test    eax, eax
0x18007833a  jns     short loc_18007834F
0x18007833c  cmp     eax, 0C0000043h
0x180078341  jz      short loc_18007834A
0x180078343  cmp     eax, 0C0000022h
0x180078348  jnz     short loc_180078384
0x18007834a  mov     ebx, r12d
0x18007834d  jmp     short loc_1800783A6
0x18007834f  mov     rcx, [rbp+FileHandle]; Handle
0x180078353  mov     ebx, r12d
0x180078356  call    cs:__imp_ZwClose
0x18007835d  nop     dword ptr [rax+rax+00h]
0x180078362  jmp     short loc_1800783A6
0x180078364  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18007836b  mov     r8d, 29Dh
0x180078371  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180078378  mov     dword ptr [rsp+80h+InputPathType], eax
0x18007837c  mov     ecx, r12d
0x18007837f  call    AslLogCallPrintf
0x180078384  xor     ebx, ebx
0x180078386  jmp     short loc_1800783A6
0x180078388  xor     ebx, ebx
0x18007838a  lea     r9, aOutOfMemory; "Out of memory"
0x180078391  mov     r8d, 292h
0x180078397  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18007839e  mov     ecx, r12d
0x1800783a1  call    AslLogCallPrintf
0x1800783a6  cmp     [rbp+DestinationString.Buffer], r14
0x1800783aa  jz      short loc_1800783BC
0x1800783ac  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800783b0  call    cs:__imp_RtlFreeUnicodeString
0x1800783b7  nop     dword ptr [rax+rax+00h]
0x1800783bc  test    rdi, rdi
0x1800783bf  jz      short loc_1800783D6
0x1800783c1  mov     rcx, gs:60h
0x1800783ca  mov     rdx, rdi
0x1800783cd  mov     rcx, [rcx+30h]
0x1800783d1  call    AslFree
0x1800783d6  lea     r11, [rsp+80h+var_s0]
0x1800783de  mov     eax, ebx
0x1800783e0  mov     rbx, [r11+40h]
0x1800783e4  mov     rsi, [r11+48h]
0x1800783e8  mov     rsp, r11
0x1800783eb  pop     r14
0x1800783ed  pop     r13
0x1800783ef  pop     r12
0x1800783f1  pop     rdi
0x1800783f2  pop     rbp
0x1800783f3  retn
```
