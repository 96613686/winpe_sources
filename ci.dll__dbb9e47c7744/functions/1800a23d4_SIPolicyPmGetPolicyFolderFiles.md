# SIPolicyPmGetPolicyFolderFiles

- ea: `0x1800a23d4`
- end: `0x1800a25f7`
- name: `SIPolicyPmGetPolicyFolderFiles`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007e550`
- `0x1800a225c`

## callees

- `0x18002bf20`
- `0x1800799e8`
- `0x1800a16f0`
- `0x1800a23d4`
- `0x1800e2a9c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a2483`
- `ntoskrnl!ExAllocatePool2` at `0x1800a2483`
- `ntoskrnl!ZwOpenFile` at `0x1800a245d`
- `ntoskrnl!ZwOpenFile` at `0x1800a245d`
- `ntoskrnl!ZwClose` at `0x1800a25a1`
- `ntoskrnl!ZwClose` at `0x1800a25a1`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a24dd`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a24dd`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetPolicyFolderFiles(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  WCHAR *Pool2; // rsi
  struct _UNICODE_STRING *FileName; // r14
  NTSTATUS v11; // ebx
  BOOLEAN RestartScan; // al
  __int64 v13; // rdi
  NTSTATUS v14; // eax
  USHORT v15; // cx
  __int64 v16; // r14
  void *FileHandle; // [rsp+60h] [rbp-79h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-71h] BYREF
  struct _UNICODE_STRING *v20; // [rsp+78h] [rbp-61h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-49h] BYREF
  GUID Guid; // [rsp+C0h] [rbp-19h] BYREF

  FileHandle = 0;
  Pool2 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileName = a3;
  v20 = a3;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v11 >= 0 )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, 592, 1769163075);
    if ( Pool2 )
    {
      RestartScan = 1;
      v13 = 0;
      while ( 1 )
      {
        v14 = ZwQueryDirectoryFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                Pool2,
                0x250u,
                FileDirectoryInformation,
                1u,
                FileName,
                RestartScan);
        v11 = v14;
        if ( v14 < 0 )
          break;
        if ( !IoStatusBlock.Information )
          goto LABEL_20;
        if ( a6 && (unsigned int)v13 >= a7 )
        {
          v11 = -1073741670;
          goto LABEL_21;
        }
        v15 = Pool2[30];
        *(_DWORD *)(&String2.MaximumLength + 1) = 0;
        String2.Length = v15;
        String2.Buffer = Pool2 + 32;
        String2.MaximumLength = v15;
        if ( !a5 || (Guid = 0, (int)SIPolicyIsValidPolicyFileName(&String2, &Guid) >= 0) )
        {
          if ( a6 )
          {
            v16 = a6 + 24 * v13;
            v11 = SIPolicyBuildPath((PCUNICODE_STRING)a2, &String2);
            if ( v11 < 0 )
              goto LABEL_21;
            *(_BYTE *)(v16 + 16) = *(_BYTE *)(a2 + 16);
            *(_BYTE *)(v16 + 17) = *(_BYTE *)(a2 + 17);
            FileName = v20;
          }
          v13 = (unsigned int)(v13 + 1);
        }
        RestartScan = 0;
      }
      if ( v14 == -2147483642 || v14 == -1073741809 )
      {
        v11 = 0;
LABEL_20:
        *a8 = v13;
      }
    }
    else
    {
      v11 = -1073741801;
    }
  }
LABEL_21:
  if ( FileHandle )
    ZwClose(FileHandle);
  SIPolicyFree(Pool2);
  if ( v11 == -1073741772 || (unsigned int)(v11 + 1073741766) <= 1 )
    return (unsigned int)-1073741275;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a23d4  mov     [rsp-8+arg_0], rbx
0x1800a23d9  push    rbp
0x1800a23da  push    rsi
0x1800a23db  push    rdi
0x1800a23dc  push    r12
0x1800a23de  push    r13
0x1800a23e0  push    r14
0x1800a23e2  push    r15
0x1800a23e4  lea     rbp, [rsp-7]
0x1800a23e9  sub     rsp, 0E0h
0x1800a23f0  mov     rax, cs:__security_cookie
0x1800a23f7  xor     rax, rsp
0x1800a23fa  mov     [rbp+37h+var_40], rax
0x1800a23fe  mov     r15, [rbp+37h+arg_28]
0x1800a2402  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800a2406  mov     r12, [rbp+37h+arg_38]
0x1800a240a  xor     ecx, ecx
0x1800a240c  xorps   xmm0, xmm0
0x1800a240f  mov     [rbp+37h+FileHandle], rcx
0x1800a2413  mov     esi, ecx
0x1800a2415  mov     [rbp+37h+ObjectAttributes.RootDirectory], rcx
0x1800a2419  mov     r14, r8
0x1800a241c  mov     [rbp+37h+var_98], r8
0x1800a2420  mov     r13, rdx
0x1800a2423  mov     [rbp+37h+ObjectAttributes.ObjectName], rdx
0x1800a2427  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800a242b  mov     [rsp+110h+OpenOptions], 4021h; OpenOptions
0x1800a2433  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800a2437  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800a243f  mov     edx, 100001h; DesiredAccess
0x1800a2444  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 240h
0x1800a244c  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x1800a2450  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800a2458  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a245d  call    cs:__imp_ZwOpenFile
0x1800a2464  nop     dword ptr [rax+rax+00h]
0x1800a2469  mov     ebx, eax
0x1800a246b  test    eax, eax
0x1800a246d  js      loc_1800A2598
0x1800a2473  mov     edx, 250h
0x1800a2478  mov     ecx, 100h
0x1800a247d  mov     r8d, 69734943h
0x1800a2483  call    cs:__imp_ExAllocatePool2
0x1800a248a  nop     dword ptr [rax+rax+00h]
0x1800a248f  mov     rsi, rax
0x1800a2492  test    rax, rax
0x1800a2495  jnz     short loc_1800A24A1
0x1800a2497  mov     ebx, 0C0000017h
0x1800a249c  jmp     loc_1800A2598
0x1800a24a1  mov     al, 1
0x1800a24a3  xor     edi, edi
0x1800a24a5  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800a24a9  xor     r9d, r9d; ApcContext
0x1800a24ac  mov     [rsp+110h+RestartScan], al; RestartScan
0x1800a24b0  xor     r8d, r8d; ApcRoutine
0x1800a24b3  mov     [rsp+110h+FileName], r14; FileName
0x1800a24b8  lea     rax, [rbp+37h+IoStatusBlock]
0x1800a24bc  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800a24c1  xor     edx, edx; Event
0x1800a24c3  mov     [rsp+110h+FileInformationClass], 1; FileInformationClass
0x1800a24cb  mov     [rsp+110h+Length], 250h; Length
0x1800a24d3  mov     qword ptr [rsp+110h+OpenOptions], rsi; FileInformation
0x1800a24d8  mov     qword ptr [rsp+110h+ShareAccess], rax; IoStatusBlock
0x1800a24dd  call    cs:__imp_ZwQueryDirectoryFile
0x1800a24e4  nop     dword ptr [rax+rax+00h]
0x1800a24e9  mov     ebx, eax
0x1800a24eb  test    eax, eax
0x1800a24ed  js      loc_1800A2584
0x1800a24f3  cmp     [rbp+37h+IoStatusBlock.Information], 0
0x1800a24f8  jz      loc_1800A2594
0x1800a24fe  test    r15, r15
0x1800a2501  jz      short loc_1800A2508
0x1800a2503  cmp     edi, [rbp+37h+arg_30]
0x1800a2506  jnb     short loc_1800A257D
0x1800a2508  cmp     [rbp+37h+arg_20], 0
0x1800a250c  lea     rax, [rsi+40h]
0x1800a2510  movzx   ecx, word ptr [rsi+3Ch]
0x1800a2514  xorps   xmm0, xmm0
0x1800a2517  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x1800a251b  mov     [rbp+37h+String2.Length], cx
0x1800a251f  mov     [rbp+37h+String2.Buffer], rax
0x1800a2523  mov     [rbp+37h+String2.MaximumLength], cx
0x1800a2527  jz      short loc_1800A253E
0x1800a2529  lea     rdx, [rbp+37h+Guid]; Guid
0x1800a252d  lea     rcx, [rbp+37h+String2]; String2
0x1800a2531  movups  xmmword ptr [rbp+37h+Guid.Data1], xmm0
0x1800a2535  call    SIPolicyIsValidPolicyFileName
0x1800a253a  test    eax, eax
0x1800a253c  js      short loc_1800A2576
0x1800a253e  test    r15, r15
0x1800a2541  jz      short loc_1800A2574
0x1800a2543  lea     rcx, [rdi+rdi*2]
0x1800a2547  lea     r14, [r15+rcx*8]
0x1800a254b  mov     rcx, r13; Source
0x1800a254e  mov     r8, r14
0x1800a2551  lea     rdx, [rbp+37h+String2]; PCUNICODE_STRING
0x1800a2555  call    SIPolicyBuildPath
0x1800a255a  mov     ebx, eax
0x1800a255c  test    eax, eax
0x1800a255e  js      short loc_1800A2598
0x1800a2560  mov     al, [r13+10h]
0x1800a2564  mov     [r14+10h], al
0x1800a2568  mov     al, [r13+11h]
0x1800a256c  mov     [r14+11h], al
0x1800a2570  mov     r14, [rbp+37h+var_98]
0x1800a2574  inc     edi
0x1800a2576  xor     al, al
0x1800a2578  jmp     loc_1800A24A5
0x1800a257d  mov     ebx, 0C000009Ah
0x1800a2582  jmp     short loc_1800A2598
0x1800a2584  cmp     eax, 80000006h
0x1800a2589  jz      short loc_1800A2592
0x1800a258b  cmp     eax, 0C000000Fh
0x1800a2590  jnz     short loc_1800A2598
0x1800a2592  xor     ebx, ebx
0x1800a2594  mov     [r12], edi
0x1800a2598  mov     rcx, [rbp+37h+FileHandle]; Handle
0x1800a259c  test    rcx, rcx
0x1800a259f  jz      short loc_1800A25AD
0x1800a25a1  call    cs:__imp_ZwClose
0x1800a25a8  nop     dword ptr [rax+rax+00h]
0x1800a25ad  mov     rcx, rsi
0x1800a25b0  call    SIPolicyFree
0x1800a25b5  cmp     ebx, 0C0000034h
0x1800a25bb  jz      short loc_1800A25C8
0x1800a25bd  lea     eax, [rbx+3FFFFFC6h]
0x1800a25c3  cmp     eax, 1
0x1800a25c6  ja      short loc_1800A25CD
0x1800a25c8  mov     ebx, 0C0000225h
0x1800a25cd  mov     eax, ebx
0x1800a25cf  mov     rcx, [rbp+37h+var_40]
0x1800a25d3  xor     rcx, rsp; StackCookie
0x1800a25d6  call    __security_check_cookie
0x1800a25db  mov     rbx, [rsp+110h+arg_0]
0x1800a25e3  add     rsp, 0E0h
0x1800a25ea  pop     r15
0x1800a25ec  pop     r14
0x1800a25ee  pop     r13
0x1800a25f0  pop     r12
0x1800a25f2  pop     rdi
0x1800a25f3  pop     rsi
0x1800a25f4  pop     rbp
0x1800a25f5  retn
```
