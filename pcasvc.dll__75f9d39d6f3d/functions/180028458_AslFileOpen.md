# AslFileOpen

- ea: `0x180028458`
- end: `0x18002870f`
- name: `AslFileOpen`
- size: `695`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, PWSTR FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800283d4`

## callees

- `0x180012920`
- `0x180019c84`
- `0x180028458`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800286d2`
- `msvcrt!_wcsnicmp` at `0x1800286d2`
- `ntdll!RtlGetFullPathName_UEx` at `0x18002856d`
- `ntdll!RtlGetFullPathName_UEx` at `0x18002856d`
- `ntdll!RtlInitUnicodeString` at `0x18002849f`
- `ntdll!RtlInitUnicodeString` at `0x18002849f`
- `ntdll!RtlFreeUnicodeString` at `0x180028507`
- `ntdll!RtlFreeUnicodeString` at `0x180028507`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800286ed`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800286ed`
- `ntdll!ZwCreateFile` at `0x18002862f`
- `ntdll!ZwCreateFile` at `0x18002862f`
- `ntdll!RtlAllocateHeap` at `0x1800284ce`
- `ntdll!RtlAllocateHeap` at `0x1800284ce`

## string_xrefs

- `0x1800284e9`: `AslFileOpen`
- `0x18002858a`: `AslFileOpen`
- `0x1800286a7`: `AslFileOpen`
- `0x18002857d`: `Failed to get full path [%x]`
- `0x18002869a`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x1800286fd`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`
- `0x18002863f`: `NtCreateFile failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileOpen(PHANDLE FileHandle, PWSTR FileName)
{
  char v4; // r14
  RTL_PATH_TYPE v5; // esi
  WCHAR *Heap; // rdi
  NTSTATUS FullPathName_UEx; // ebx
  const char *v9; // r9
  int v10; // r8d
  bool v11; // cf
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+E0h] [rbp+67h] BYREF

  *FileHandle = 0;
  InputPathType = RtlPathTypeUnknown;
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
    v4 = 0;
    v5 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v5);
      if ( !Heap )
      {
        AslLogCallPrintf(1, (unsigned int)"AslFileOpen", 1843, (unsigned int)"Out of memory");
        FullPathName_UEx = -1073741801;
        goto LABEL_5;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v5, Heap, 0, &InputPathType);
      if ( FullPathName_UEx < 0 )
      {
        v9 = "Failed to get full path [%x]";
        v10 = 1854;
        goto LABEL_14;
      }
      v11 = InputPathType < (unsigned int)v5;
      if ( InputPathType > (unsigned int)v5 )
      {
        if ( v4 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslFileOpen",
            1862,
            (unsigned int)"RtlGetFullPathName_UEx failed to get full path with larger buffer.");
          FullPathName_UEx = -1073741789;
          goto LABEL_5;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v5 = InputPathType;
        v11 = 0;
      }
      if ( v11 )
        break;
      v4 = 1;
    }
    if ( _wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v9 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v10 = 1885;
        goto LABEL_14;
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
  if ( FullPathName_UEx < 0 )
  {
    v9 = "NtCreateFile failed [%x]";
    v10 = 1910;
LABEL_14:
    AslLogCallPrintf(1, (unsigned int)"AslFileOpen", v10, (_DWORD)v9);
  }
LABEL_5:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return (unsigned int)FullPathName_UEx;
}

```

## disassembly

```asm
0x180028458  mov     [rsp-8+arg_8], rbx
0x18002845d  mov     [rsp-8+arg_10], rsi
0x180028462  push    rbp
0x180028463  push    rdi
0x180028464  push    r12
0x180028466  push    r14
0x180028468  push    r15
0x18002846a  lea     rbp, [rsp-37h]
0x18002846f  sub     rsp, 0B0h
0x180028476  xorps   xmm0, xmm0
0x180028479  xor     eax, eax
0x18002847b  mov     [rcx], rax
0x18002847e  mov     r12, rcx
0x180028481  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180028485  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180028489  mov     [rbp+57h+arg_0], eax
0x18002848c  mov     r15, rdx
0x18002848f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180028493  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180028497  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002849b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002849f  call    cs:__imp_RtlInitUnicodeString
0x1800284a5  mov     eax, 8
0x1800284aa  cmp     [rbp+57h+DestinationString.Length], ax
0x1800284ae  ja      loc_180028545
0x1800284b4  xor     r14b, r14b
0x1800284b7  mov     esi, 208h
0x1800284bc  mov     rcx, gs:60h
0x1800284c5  mov     edx, eax; Flags
0x1800284c7  mov     r8d, esi; Size
0x1800284ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800284ce  call    cs:__imp_RtlAllocateHeap
0x1800284d4  mov     rdi, rax
0x1800284d7  test    rax, rax
0x1800284da  jnz     short loc_180028559
0x1800284dc  lea     r9, aOutOfMemory; "Out of memory"
0x1800284e3  mov     r8d, 733h
0x1800284e9  lea     rdx, aAslfileopen; "AslFileOpen"
0x1800284f0  lea     ecx, [rax+1]
0x1800284f3  call    AslLogCallPrintf
0x1800284f8  mov     ebx, 0C0000017h
0x1800284fd  cmp     [rbp+57h+DestinationString.Buffer], r15
0x180028501  jz      short loc_18002850D
0x180028503  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180028507  call    cs:__imp_RtlFreeUnicodeString
0x18002850d  test    rdi, rdi
0x180028510  jz      short loc_180028527
0x180028512  mov     rcx, gs:60h
0x18002851b  mov     rdx, rdi
0x18002851e  mov     rcx, [rcx+30h]
0x180028522  call    AslFree
0x180028527  lea     r11, [rsp+0D0h+var_20]
0x18002852f  mov     eax, ebx
0x180028531  mov     rbx, [r11+38h]
0x180028535  mov     rsi, [r11+40h]
0x180028539  mov     rsp, r11
0x18002853c  pop     r15
0x18002853e  pop     r14
0x180028540  pop     r12
0x180028542  pop     rdi
0x180028543  pop     rbp
0x180028544  retn
0x180028545  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180028549  cmp     word ptr [rax], 5Ch ; '\'
0x18002854d  jz      short loc_1800285A4
0x18002854f  mov     eax, 8
0x180028554  jmp     loc_1800284B4
0x180028559  lea     rax, [rbp+57h+arg_0]
0x18002855d  xor     r9d, r9d; FilePart
0x180028560  mov     r8, rdi; Buffer
0x180028563  mov     [rsp+0D0h+InputPathType], rax; InputPathType
0x180028568  mov     edx, esi; BufferLength
0x18002856a  mov     rcx, r15; FileName
0x18002856d  call    cs:__imp_RtlGetFullPathName_UEx
0x180028573  mov     ebx, eax
0x180028575  test    eax, eax
0x180028577  jns     loc_180028661
0x18002857d  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x180028584  mov     r8d, 73Eh
0x18002858a  lea     rdx, aAslfileopen; "AslFileOpen"
0x180028591  mov     dword ptr [rsp+0D0h+InputPathType], eax
0x180028595  mov     ecx, 1
0x18002859a  call    AslLogCallPrintf
0x18002859f  jmp     loc_1800284FD
0x1800285a4  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800285a9  jnz     loc_180028651
0x1800285af  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800285b4  jnz     short loc_18002854F
0x1800285b6  xor     edi, edi
0x1800285b8  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800285bd  jnz     short loc_18002854F
0x1800285bf  mov     [rsp+0D0h+EaLength], 0; EaLength
0x1800285c7  lea     rax, [rbp+57h+DestinationString]
0x1800285cb  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x1800285d4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800285d8  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x1800285e0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800285e4  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x1800285ec  xorps   xmm0, xmm0
0x1800285ef  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x1800285f7  mov     edx, 80100080h; DesiredAccess
0x1800285fc  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180028604  mov     rcx, r12; FileHandle
0x180028607  mov     [rsp+0D0h+InputPathType], 0; AllocationSize
0x180028610  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028617  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002861f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180028626  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002862a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002862f  call    cs:__imp_ZwCreateFile
0x180028635  mov     ebx, eax
0x180028637  test    eax, eax
0x180028639  jns     loc_1800284FD
0x18002863f  lea     r9, aNtcreatefileFa; "NtCreateFile failed [%x]"
0x180028646  mov     r8d, 776h
0x18002864c  jmp     loc_18002858A
0x180028651  cmp     word ptr [rax+2], 3Fh ; '?'
0x180028656  jnz     loc_18002854F
0x18002865c  jmp     loc_1800285AF
0x180028661  mov     eax, [rbp+57h+arg_0]
0x180028664  cmp     eax, esi
0x180028666  jbe     short loc_18002868B
0x180028668  test    r14b, r14b
0x18002866b  jnz     short loc_18002869A
0x18002866d  mov     rcx, gs:60h
0x180028676  mov     rdx, rdi
0x180028679  mov     rcx, [rcx+30h]
0x18002867d  call    AslFree
0x180028682  mov     eax, [rbp+57h+arg_0]
0x180028685  xor     edi, edi
0x180028687  mov     esi, eax
0x180028689  cmp     eax, eax
0x18002868b  jb      short loc_1800286C2
0x18002868d  mov     r14b, 1
0x180028690  mov     eax, 8
0x180028695  jmp     loc_1800284BC
0x18002869a  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x1800286a1  mov     r8d, 746h
0x1800286a7  lea     rdx, aAslfileopen; "AslFileOpen"
0x1800286ae  mov     ecx, 1
0x1800286b3  call    AslLogCallPrintf
0x1800286b8  mov     ebx, 0C0000023h
0x1800286bd  jmp     loc_1800284FD
0x1800286c2  mov     r8d, 0Ch; MaxCount
0x1800286c8  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x1800286cf  mov     rcx, rdi; String1
0x1800286d2  call    cs:__imp__wcsnicmp
0x1800286d8  test    eax, eax
0x1800286da  jz      loc_1800285BF
0x1800286e0  xor     r9d, r9d
0x1800286e3  lea     rdx, [rbp+57h+DestinationString]
0x1800286e7  xor     r8d, r8d
0x1800286ea  mov     rcx, rdi
0x1800286ed  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800286f3  mov     ebx, eax
0x1800286f5  test    eax, eax
0x1800286f7  jns     loc_1800285BF
0x1800286fd  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180028704  mov     r8d, 75Dh
0x18002870a  jmp     loc_18002858A
```
