# AslDoesFileExistNtPath

- ea: `0x18007053c`
- end: `0x1800707a0`
- name: `AslDoesFileExistNtPath`
- size: `612`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004a8d8`

## callees

- `0x180021144`
- `0x1800212e4`
- `0x18005c414`
- `0x18007053c`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007068d`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007068d`
- `ntdll!RtlFreeUnicodeString` at `0x180070762`
- `ntdll!RtlFreeUnicodeString` at `0x180070762`
- `ntdll!RtlGetFullPathName_UEx` at `0x180070607`
- `ntdll!RtlGetFullPathName_UEx` at `0x180070607`
- `ntdll!ZwClose` at `0x18007070e`
- `ntdll!ZwClose` at `0x18007070e`
- `ntdll!ZwOpenFile` at `0x1800706ea`
- `ntdll!ZwOpenFile` at `0x1800706ea`
- `ntdll!RtlInitUnicodeString` at `0x180070582`
- `ntdll!RtlInitUnicodeString` at `0x180070582`
- `ntdll!RtlAllocateHeap` at `0x1800705e1`
- `ntdll!RtlAllocateHeap` at `0x1800705e1`

## string_xrefs

- `0x180070653`: `AslDoesFileExistNtPath`
- `0x180070723`: `AslDoesFileExistNtPath`
- `0x180070749`: `AslDoesFileExistNtPath`
- `0x180070646`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x180070716`: `Failed to get full path [%x]`
- `0x180070697`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

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
0x18007053c  mov     [rsp-28h+arg_10], rbx
0x180070541  mov     [rsp-28h+arg_18], rsi
0x180070546  push    rbp
0x180070547  push    rdi
0x180070548  push    r12
0x18007054a  push    r13
0x18007054c  push    r14
0x18007054e  mov     rbp, rsp
0x180070551  sub     rsp, 80h
0x180070558  xorps   xmm0, xmm0
0x18007055b  xor     eax, eax
0x18007055d  mov     r14, rcx
0x180070560  mov     [rbp+FileHandle], rax
0x180070564  mov     rdx, rcx; SourceString
0x180070567  mov     [rbp+arg_0], eax
0x18007056a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007056e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180070572  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180070576  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007057a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007057e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180070582  call    cs:__imp_RtlInitUnicodeString
0x180070588  mov     r12d, 1
0x18007058e  lea     r13d, [r12+7]
0x180070593  cmp     [rbp+DestinationString.Length], r13w
0x180070598  jbe     short loc_1800705C6
0x18007059a  mov     rax, [rbp+DestinationString.Buffer]
0x18007059e  cmp     word ptr [rax], 5Ch ; '\'
0x1800705a2  jnz     short loc_1800705C6
0x1800705a4  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800705a9  jz      short loc_1800705B2
0x1800705ab  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800705b0  jnz     short loc_1800705C6
0x1800705b2  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800705b7  jnz     short loc_1800705C6
0x1800705b9  xor     edi, edi
0x1800705bb  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800705c0  jz      loc_1800706A6
0x1800705c6  xor     sil, sil
0x1800705c9  mov     ebx, 208h
0x1800705ce  mov     rcx, gs:60h
0x1800705d7  mov     edx, r13d; Flags
0x1800705da  mov     r8d, ebx; Size
0x1800705dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800705e1  call    cs:__imp_RtlAllocateHeap
0x1800705e7  mov     rdi, rax
0x1800705ea  test    rax, rax
0x1800705ed  jz      loc_18007073A
0x1800705f3  lea     rax, [rbp+arg_0]
0x1800705f7  xor     r9d, r9d; FilePart
0x1800705fa  mov     r8, rdi; Buffer
0x1800705fd  mov     [rsp+80h+InputPathType], rax; InputPathType
0x180070602  mov     edx, ebx; BufferLength
0x180070604  mov     rcx, r14; FileName
0x180070607  call    cs:__imp_RtlGetFullPathName_UEx
0x18007060d  test    eax, eax
0x18007060f  js      loc_180070716
0x180070615  mov     eax, [rbp+arg_0]
0x180070618  cmp     eax, ebx
0x18007061a  jbe     short loc_18007063F
0x18007061c  test    sil, sil
0x18007061f  jnz     short loc_180070646
0x180070621  mov     rcx, gs:60h
0x18007062a  mov     rdx, rdi
0x18007062d  mov     rcx, [rcx+30h]
0x180070631  call    AslFree
0x180070636  mov     eax, [rbp+arg_0]
0x180070639  xor     edi, edi
0x18007063b  mov     ebx, eax
0x18007063d  cmp     eax, eax
0x18007063f  jb      short loc_180070667
0x180070641  mov     sil, r12b
0x180070644  jmp     short loc_1800705CE
0x180070646  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x18007064d  mov     r8d, 2A6h
0x180070653  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18007065a  mov     ecx, r12d
0x18007065d  call    AslLogCallPrintf
0x180070662  jmp     loc_180070736
0x180070667  mov     r8d, 0Ch; MaxCount
0x18007066d  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x180070674  mov     rcx, rdi; String1
0x180070677  call    _wcsnicmp_0
0x18007067c  test    eax, eax
0x18007067e  jz      short loc_1800706A6
0x180070680  xor     r9d, r9d
0x180070683  lea     rdx, [rbp+DestinationString]
0x180070687  xor     r8d, r8d
0x18007068a  mov     rcx, rdi
0x18007068d  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180070693  test    eax, eax
0x180070695  jns     short loc_1800706A6
0x180070697  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18007069e  mov     r8d, 2BDh
0x1800706a4  jmp     short loc_180070723
0x1800706a6  lea     rax, [rbp+DestinationString]
0x1800706aa  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800706b2  xorps   xmm0, xmm0
0x1800706b5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800706b9  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800706bd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800706c4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800706c8  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800706d0  mov     edx, 100080h; DesiredAccess
0x1800706d5  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800706dc  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800706e0  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x1800706e5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800706ea  call    cs:__imp_ZwOpenFile
0x1800706f0  test    eax, eax
0x1800706f2  jns     short loc_180070707
0x1800706f4  cmp     eax, 0C0000043h
0x1800706f9  jz      short loc_180070702
0x1800706fb  cmp     eax, 0C0000022h
0x180070700  jnz     short loc_180070736
0x180070702  mov     ebx, r12d
0x180070705  jmp     short loc_180070758
0x180070707  mov     rcx, [rbp+FileHandle]; Handle
0x18007070b  mov     ebx, r12d
0x18007070e  call    cs:__imp_ZwClose
0x180070714  jmp     short loc_180070758
0x180070716  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18007071d  mov     r8d, 29Dh
0x180070723  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18007072a  mov     dword ptr [rsp+80h+InputPathType], eax
0x18007072e  mov     ecx, r12d
0x180070731  call    AslLogCallPrintf
0x180070736  xor     ebx, ebx
0x180070738  jmp     short loc_180070758
0x18007073a  xor     ebx, ebx
0x18007073c  lea     r9, aOutOfMemory; "Out of memory"
0x180070743  mov     r8d, 292h
0x180070749  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180070750  mov     ecx, r12d
0x180070753  call    AslLogCallPrintf
0x180070758  cmp     [rbp+DestinationString.Buffer], r14
0x18007075c  jz      short loc_180070768
0x18007075e  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180070762  call    cs:__imp_RtlFreeUnicodeString
0x180070768  test    rdi, rdi
0x18007076b  jz      short loc_180070782
0x18007076d  mov     rcx, gs:60h
0x180070776  mov     rdx, rdi
0x180070779  mov     rcx, [rcx+30h]
0x18007077d  call    AslFree
0x180070782  lea     r11, [rsp+80h+var_s0]
0x18007078a  mov     eax, ebx
0x18007078c  mov     rbx, [r11+40h]
0x180070790  mov     rsi, [r11+48h]
0x180070794  mov     rsp, r11
0x180070797  pop     r14
0x180070799  pop     r13
0x18007079b  pop     r12
0x18007079d  pop     rdi
0x18007079e  pop     rbp
0x18007079f  retn
```
