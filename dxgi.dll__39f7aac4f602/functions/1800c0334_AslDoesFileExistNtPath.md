# AslDoesFileExistNtPath

- ea: `0x1800c0334`
- end: `0x1800c0598`
- name: `AslDoesFileExistNtPath`
- size: `612`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800be468`

## callees

- `0x180041774`
- `0x18004281c`
- `0x180076e9c`
- `0x1800c0334`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c037a`
- `ntdll!RtlInitUnicodeString` at `0x1800c037a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800c0485`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800c0485`
- `ntdll!RtlAllocateHeap` at `0x1800c03d9`
- `ntdll!RtlAllocateHeap` at `0x1800c03d9`
- `ntdll!ZwClose` at `0x1800c0506`
- `ntdll!ZwClose` at `0x1800c0506`
- `ntdll!RtlFreeUnicodeString` at `0x1800c055a`
- `ntdll!RtlFreeUnicodeString` at `0x1800c055a`
- `ntdll!ZwOpenFile` at `0x1800c04e2`
- `ntdll!ZwOpenFile` at `0x1800c04e2`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800c03ff`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800c03ff`

## string_xrefs

- `0x1800c050e`: `Failed to get full path [%x]`
- `0x1800c044b`: `AslDoesFileExistNtPath`
- `0x1800c051b`: `AslDoesFileExistNtPath`
- `0x1800c0541`: `AslDoesFileExistNtPath`
- `0x1800c043e`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x1800c048f`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

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
  __int64 v8; // r8
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  RTL_PATH_TYPE *InputPathType; // [rsp+20h] [rbp-60h]
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
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", 658, "Out of memory");
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
            "AslDoesFileExistNtPath",
            678,
            "RtlGetFullPathName_UEx failed to get full path with larger buffer.");
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
    if ( wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v8 = 701;
LABEL_25:
        LODWORD(InputPathType) = FullPathName_UEx;
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", v8, v7, InputPathType);
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
0x1800c0334  mov     [rsp-28h+arg_10], rbx
0x1800c0339  mov     [rsp-28h+arg_18], rsi
0x1800c033e  push    rbp
0x1800c033f  push    rdi
0x1800c0340  push    r12
0x1800c0342  push    r13
0x1800c0344  push    r14
0x1800c0346  mov     rbp, rsp
0x1800c0349  sub     rsp, 80h
0x1800c0350  xorps   xmm0, xmm0
0x1800c0353  xor     eax, eax
0x1800c0355  mov     r14, rcx
0x1800c0358  mov     [rbp+FileHandle], rax
0x1800c035c  mov     rdx, rcx; SourceString
0x1800c035f  mov     [rbp+arg_0], eax
0x1800c0362  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800c0366  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800c036a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800c036e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800c0372  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800c0376  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800c037a  call    cs:__imp_RtlInitUnicodeString
0x1800c0380  mov     r12d, 1
0x1800c0386  lea     r13d, [r12+7]
0x1800c038b  cmp     [rbp+DestinationString.Length], r13w
0x1800c0390  jbe     short loc_1800C03BE
0x1800c0392  mov     rax, [rbp+DestinationString.Buffer]
0x1800c0396  cmp     word ptr [rax], 5Ch ; '\'
0x1800c039a  jnz     short loc_1800C03BE
0x1800c039c  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800c03a1  jz      short loc_1800C03AA
0x1800c03a3  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800c03a8  jnz     short loc_1800C03BE
0x1800c03aa  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800c03af  jnz     short loc_1800C03BE
0x1800c03b1  xor     edi, edi
0x1800c03b3  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800c03b8  jz      loc_1800C049E
0x1800c03be  xor     sil, sil
0x1800c03c1  mov     ebx, 208h
0x1800c03c6  mov     rcx, gs:60h
0x1800c03cf  mov     edx, r13d; Flags
0x1800c03d2  mov     r8d, ebx; Size
0x1800c03d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800c03d9  call    cs:__imp_RtlAllocateHeap
0x1800c03df  mov     rdi, rax
0x1800c03e2  test    rax, rax
0x1800c03e5  jz      loc_1800C0532
0x1800c03eb  lea     rax, [rbp+arg_0]
0x1800c03ef  xor     r9d, r9d; FilePart
0x1800c03f2  mov     r8, rdi; Buffer
0x1800c03f5  mov     [rsp+80h+InputPathType], rax; InputPathType
0x1800c03fa  mov     edx, ebx; BufferLength
0x1800c03fc  mov     rcx, r14; FileName
0x1800c03ff  call    cs:__imp_RtlGetFullPathName_UEx
0x1800c0405  test    eax, eax
0x1800c0407  js      loc_1800C050E
0x1800c040d  mov     eax, [rbp+arg_0]
0x1800c0410  cmp     eax, ebx
0x1800c0412  jbe     short loc_1800C0437
0x1800c0414  test    sil, sil
0x1800c0417  jnz     short loc_1800C043E
0x1800c0419  mov     rcx, gs:60h
0x1800c0422  mov     rdx, rdi
0x1800c0425  mov     rcx, [rcx+30h]
0x1800c0429  call    AslFree
0x1800c042e  mov     eax, [rbp+arg_0]
0x1800c0431  xor     edi, edi
0x1800c0433  mov     ebx, eax
0x1800c0435  cmp     eax, eax
0x1800c0437  jb      short loc_1800C045F
0x1800c0439  mov     sil, r12b
0x1800c043c  jmp     short loc_1800C03C6
0x1800c043e  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x1800c0445  mov     r8d, 2A6h
0x1800c044b  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x1800c0452  mov     ecx, r12d
0x1800c0455  call    AslLogCallPrintf
0x1800c045a  jmp     loc_1800C052E
0x1800c045f  mov     r8d, 0Ch; MaxCount
0x1800c0465  lea     rdx, aSystemroot_0; "\\SystemRoot\\"
0x1800c046c  mov     rcx, rdi; String1
0x1800c046f  call    _wcsnicmp
0x1800c0474  test    eax, eax
0x1800c0476  jz      short loc_1800C049E
0x1800c0478  xor     r9d, r9d
0x1800c047b  lea     rdx, [rbp+DestinationString]
0x1800c047f  xor     r8d, r8d
0x1800c0482  mov     rcx, rdi
0x1800c0485  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800c048b  test    eax, eax
0x1800c048d  jns     short loc_1800C049E
0x1800c048f  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800c0496  mov     r8d, 2BDh
0x1800c049c  jmp     short loc_1800C051B
0x1800c049e  lea     rax, [rbp+DestinationString]
0x1800c04a2  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800c04aa  xorps   xmm0, xmm0
0x1800c04ad  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800c04b1  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800c04b5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800c04bc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800c04c0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800c04c8  mov     edx, 100080h; DesiredAccess
0x1800c04cd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800c04d4  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800c04d8  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x1800c04dd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c04e2  call    cs:__imp_ZwOpenFile
0x1800c04e8  test    eax, eax
0x1800c04ea  jns     short loc_1800C04FF
0x1800c04ec  cmp     eax, 0C0000043h
0x1800c04f1  jz      short loc_1800C04FA
0x1800c04f3  cmp     eax, 0C0000022h
0x1800c04f8  jnz     short loc_1800C052E
0x1800c04fa  mov     ebx, r12d
0x1800c04fd  jmp     short loc_1800C0550
0x1800c04ff  mov     rcx, [rbp+FileHandle]; Handle
0x1800c0503  mov     ebx, r12d
0x1800c0506  call    cs:__imp_ZwClose
0x1800c050c  jmp     short loc_1800C0550
0x1800c050e  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1800c0515  mov     r8d, 29Dh
0x1800c051b  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x1800c0522  mov     dword ptr [rsp+80h+InputPathType], eax
0x1800c0526  mov     ecx, r12d
0x1800c0529  call    AslLogCallPrintf
0x1800c052e  xor     ebx, ebx
0x1800c0530  jmp     short loc_1800C0550
0x1800c0532  xor     ebx, ebx
0x1800c0534  lea     r9, aOutOfMemory; "Out of memory"
0x1800c053b  mov     r8d, 292h
0x1800c0541  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x1800c0548  mov     ecx, r12d
0x1800c054b  call    AslLogCallPrintf
0x1800c0550  cmp     [rbp+DestinationString.Buffer], r14
0x1800c0554  jz      short loc_1800C0560
0x1800c0556  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800c055a  call    cs:__imp_RtlFreeUnicodeString
0x1800c0560  test    rdi, rdi
0x1800c0563  jz      short loc_1800C057A
0x1800c0565  mov     rcx, gs:60h
0x1800c056e  mov     rdx, rdi
0x1800c0571  mov     rcx, [rcx+30h]
0x1800c0575  call    AslFree
0x1800c057a  lea     r11, [rsp+80h+var_s0]
0x1800c0582  mov     eax, ebx
0x1800c0584  mov     rbx, [r11+40h]
0x1800c0588  mov     rsi, [r11+48h]
0x1800c058c  mov     rsp, r11
0x1800c058f  pop     r14
0x1800c0591  pop     r13
0x1800c0593  pop     r12
0x1800c0595  pop     rdi
0x1800c0596  pop     rbp
0x1800c0597  retn
```
