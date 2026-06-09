# BackupReadAlternateData

- ea: `0x180030220`
- end: `0x1800305b1`
- name: `BackupReadAlternateData`
- size: `913`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x180030710`

## callees

- `0x180030220`
- `0x180030bb4`
- `0x180031108`
- `0x1800698e4`
- `0x18007a7d1`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x180030590`
- `ntdll!_wcsnicmp` at `0x180030590`
- `ntdll!NtOpenFile` at `0x180030303`
- `ntdll!NtOpenFile` at `0x180030303`
- `ntdll!NtQueryInformationFile` at `0x180030420`
- `ntdll!NtQueryInformationFile` at `0x180030420`
- `ntdll!RtlSetLastWin32Error` at `0x180030331`
- `ntdll!RtlSetLastWin32Error` at `0x180030331`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x180030322`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x180030322`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800304ac`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800304ac`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003046b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003046b`

## pseudocode

```c
BOOL __fastcall BackupReadAlternateData(HANDLE FileHandle, __int64 a2, __int64 a3)
{
  HANDLE *v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rsi
  int v9; // eax
  int v11; // eax
  ULONG *v12; // rsi
  __int64 i; // rdx
  NTSTATUS v14; // eax
  HANDLE v15; // rcx
  __int16 v16; // si
  int v17; // esi
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // edx
  struct _IO_STATUS_BLOCK v21; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  __int64 FileInformation; // [rsp+B8h] [rbp+38h] BYREF

  if ( *(_BYTE *)(a2 + 1137) && (*(_DWORD *)(a2 + 1140) & 0x40000) == 0 )
    return 1;
  if ( *(_BYTE *)(a2 + 1129) )
  {
    v11 = *(_DWORD *)(a2 + 1132) & 0x4010;
    v21 = 0;
    if ( v11 != 0x4000 )
    {
      if ( !*(_BYTE *)(a2 + 1128) )
      {
        v12 = (ULONG *)(a2 + 1112);
        for ( i = 1024; (unsigned int)GrowBuffer(v12, i); i = 2 * *v12 )
        {
          v14 = NtQueryInformationFile(FileHandle, &v21, *(PVOID *)(a2 + 1120), *v12, FileStreamInformation);
          if ( v14 >= 0 && v21.Information )
          {
            *(_DWORD *)(a2 + 1108) = 0;
            *(_BYTE *)(a2 + 1128) = 1;
            goto LABEL_33;
          }
          if ( v14 != -2147483643 && v14 != -1073741789 )
            return 1;
        }
        return 0;
      }
LABEL_33:
      v18 = *(unsigned int *)(a2 + 1108);
      v19 = *(_QWORD *)(a2 + 1120);
      *(_QWORD *)(a2 + 1072) = -1;
      *(_BYTE *)(a2 + 1129) = 0;
      if ( *(_DWORD *)(v18 + v19 + 4) >= 4u && *(_WORD *)(v18 + v19 + 26) == 58 )
      {
        v20 = *(_DWORD *)(v18 + v19);
        if ( !v20 )
          return 1;
        *(_DWORD *)(a2 + 1108) = v20 + v18;
      }
      *(_DWORD *)(a2 + 8) = 1;
    }
    return 1;
  }
  v5 = (HANDLE *)(a2 + 1072);
  if ( *(_QWORD *)(a2 + 1072) == -1 )
  {
    v6 = *(unsigned int *)(a2 + 1108);
    v7 = *(_QWORD *)(a2 + 1120);
    *(_QWORD *)(a2 + 8) = 0;
    v8 = v6 + v7;
    memset(&ObjectAttributes.ObjectName, 0, 32);
    v21 = 0;
    *(_OWORD *)&ObjectAttributes.Length = 0;
    IoStatusBlock = 0;
    LOWORD(v21.Status) = *(_WORD *)(v8 + 4);
    WORD1(v21.Pointer) = v21.Status;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
    v9 = *(_DWORD *)(a2 + 1132);
    v21.Information = v8 + 24;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Attributes = 64;
    if ( NtOpenFile(
           (PHANDLE)(a2 + 1072),
           0x100081u,
           &ObjectAttributes,
           &IoStatusBlock,
           7u,
           ((v9 & 0x400) << 11) | 0x4020) < 0 )
    {
      *(_DWORD *)(a2 + 1108) += *(_DWORD *)v8;
      if ( *(_DWORD *)v8 )
      {
        *(_DWORD *)(a2 + 8) = 1;
        *(_BYTE *)(a2 + 1130) = 1;
      }
      goto LABEL_6;
    }
    if ( !LockFile(*v5, 0, 0, 0xFFFFFFFF, 0xFFFFFFFF) )
    {
LABEL_6:
      RtlSetLastWin32Error(0x20u);
      return 0;
    }
    *(_DWORD *)(a2 + 4) = 0;
    *(_DWORD *)(a2 + 16) = *(_DWORD *)(v8 + 4);
    *(_DWORD *)(a2 + 1068) = *(_DWORD *)(v8 + 4) + 20;
    memcpy_0((void *)(a2 + 20), (const void *)(v8 + 24), *(unsigned int *)(v8 + 4));
    if ( *(_DWORD *)v8 )
    {
      *(_DWORD *)(a2 + 1108) += *(_DWORD *)v8;
      *(_BYTE *)(a2 + 1130) = 1;
    }
    if ( *(_DWORD *)(v8 + 4) > 0xCu
      && !_wcsnicmp(
            (const wchar_t *)(v8 + 2 * ((((unsigned __int64)*(unsigned int *)(v8 + 4) - 12) >> 1) + 12)),
            L":$DATA",
            6u) )
    {
      v15 = *v5;
      FileInformation = 0;
      v16 = 0;
      *(_DWORD *)a2 = 4;
      *(_QWORD *)(a2 + 1096) = 0;
      *(_BYTE *)(a2 + 1104) = 0;
      if ( GetFileInformationByHandleEx(v15, FileAttributeTagInfo, &FileInformation, 8u) )
        v16 = FileInformation;
      v17 = v16 & 0x200;
      *(_DWORD *)(a2 + 4) = v17 != 0 ? 8 : 0;
      if ( (*(_BYTE *)(a2 + 1144) || v17) && (unsigned int)BackupGetSparseMap(*v5) )
        *(_QWORD *)(a2 + 8) = 0;
      else
        *(_DWORD *)(a2 + 8) = GetFileSize(*v5, (LPDWORD)(a2 + 12));
    }
    return 1;
  }
  if ( *(_QWORD *)(a2 + 1056) < (__int64)*(unsigned int *)(a2 + 1068) || *(_DWORD *)a2 != 9 && *(_DWORD *)a2 != 4 )
    return 1;
  return BackupReadStream(*(HANDLE *)(a2 + 1072), a2, a3);
}

```

## disassembly

```asm
0x180030220  mov     [rsp-28h+arg_0], rbx
0x180030225  mov     [rsp-28h+arg_10], rsi
0x18003022a  push    rbp
0x18003022b  push    r12
0x18003022d  push    r13
0x18003022f  push    r14
0x180030231  push    r15
0x180030233  mov     rbp, rsp
0x180030236  sub     rsp, 80h
0x18003023d  xor     r13d, r13d
0x180030240  mov     rbx, rdx
0x180030243  mov     r15, rcx
0x180030246  cmp     [rdx+471h], r13b
0x18003024d  jnz     loc_1800304C3
0x180030253  cmp     [rdx+469h], r13b
0x18003025a  jnz     loc_1800303C5
0x180030260  lea     r14, [rdx+430h]
0x180030267  mov     rax, [r14]
0x18003026a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003026e  jnz     loc_1800303A0
0x180030274  mov     ecx, [rdx+454h]
0x18003027a  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18003027e  mov     rsi, [rdx+460h]
0x180030285  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180030289  xorps   xmm0, xmm0
0x18003028c  mov     [rdx+8], r13
0x180030290  xor     eax, eax
0x180030292  add     rsi, rcx
0x180030295  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180030299  mov     rcx, r14; FileHandle
0x18003029c  movups  xmmword ptr [rbp+var_50], xmm0
0x1800302a0  lea     r12, [rsi+18h]
0x1800302a4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800302a8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800302ac  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800302b0  movzx   eax, word ptr [rsi+4]
0x1800302b4  mov     word ptr [rbp+var_50], ax
0x1800302b8  mov     word ptr [rbp+var_50+2], ax
0x1800302bc  lea     rax, [rbp+var_50]
0x1800302c0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800302c4  mov     eax, [rdx+46Ch]
0x1800302ca  mov     edx, 100081h; DesiredAccess
0x1800302cf  and     eax, 400h
0x1800302d4  mov     [rbp+var_50.Information], r12
0x1800302d8  shl     eax, 0Bh
0x1800302db  or      eax, 4020h
0x1800302e0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800302e7  mov     [rsp+80h+OpenOptions], eax; OpenOptions
0x1800302eb  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x1800302f3  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1800302f7  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800302fe  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180030303  call    cs:__imp_NtOpenFile
0x180030309  test    eax, eax
0x18003030b  js      loc_18003054D
0x180030311  mov     rcx, [r14]; hFile
0x180030314  or      r9d, 0FFFFFFFFh; nNumberOfBytesToLockLow
0x180030318  xor     r8d, r8d; dwFileOffsetHigh
0x18003031b  mov     [rsp+80h+ShareAccess], r9d; nNumberOfBytesToLockHigh
0x180030320  xor     edx, edx; dwFileOffsetLow
0x180030322  call    cs:__imp_LockFile
0x180030328  test    eax, eax
0x18003032a  jnz     short loc_180030356
0x18003032c  mov     ecx, 20h ; ' '; LastError
0x180030331  call    cs:__imp_RtlSetLastWin32Error
0x180030337  xor     eax, eax
0x180030339  lea     r11, [rsp+80h+var_s0]
0x180030341  mov     rbx, [r11+30h]
0x180030345  mov     rsi, [r11+40h]
0x180030349  mov     rsp, r11
0x18003034c  pop     r15
0x18003034e  pop     r14
0x180030350  pop     r13
0x180030352  pop     r12
0x180030354  pop     rbp
0x180030355  retn
0x180030356  mov     [rbx+4], r13d
0x18003035a  lea     rcx, [rbx+14h]; void *
0x18003035e  mov     eax, [rsi+4]
0x180030361  mov     rdx, r12; Src
0x180030364  mov     [rbx+10h], eax
0x180030367  mov     eax, [rsi+4]
0x18003036a  add     eax, 14h
0x18003036d  mov     [rbx+42Ch], eax
0x180030373  mov     r8d, [rsi+4]; Size
0x180030377  call    memcpy_0
0x18003037c  mov     eax, [rsi]
0x18003037e  test    eax, eax
0x180030380  jz      short loc_18003038F
0x180030382  add     [rbx+454h], eax
0x180030388  mov     byte ptr [rbx+46Ah], 1
0x18003038f  cmp     dword ptr [rsi+4], 0Ch
0x180030393  ja      loc_180030571
0x180030399  mov     eax, 1
0x18003039e  jmp     short loc_180030339
0x1800303a0  mov     ecx, [rdx+42Ch]
0x1800303a6  cmp     [rdx+420h], rcx
0x1800303ad  jl      short loc_180030399
0x1800303af  cmp     dword ptr [rdx], 9
0x1800303b2  jnz     loc_1800305A3
0x1800303b8  mov     rcx, rax; hFile
0x1800303bb  call    BackupReadStream
0x1800303c0  jmp     loc_180030339
0x1800303c5  mov     eax, [rdx+46Ch]
0x1800303cb  xorps   xmm0, xmm0
0x1800303ce  and     eax, 4010h
0x1800303d3  movups  xmmword ptr [rbp+var_50], xmm0
0x1800303d7  cmp     eax, 4000h
0x1800303dc  jz      short loc_180030399
0x1800303de  cmp     [rdx+468h], r13b
0x1800303e5  jnz     loc_1800304F0
0x1800303eb  lea     rsi, [rdx+458h]
0x1800303f2  mov     edx, 400h
0x1800303f7  mov     rcx, rsi
0x1800303fa  call    GrowBuffer
0x1800303ff  test    eax, eax
0x180030401  jz      loc_180030337
0x180030407  mov     r9d, [rsi]; Length
0x18003040a  lea     rdx, [rbp+var_50]; IoStatusBlock
0x18003040e  mov     r8, [rbx+460h]; FileInformation
0x180030415  mov     rcx, r15; FileHandle
0x180030418  mov     [rsp+80h+ShareAccess], 16h; FileInformationClass
0x180030420  call    cs:__imp_NtQueryInformationFile
0x180030426  test    eax, eax
0x180030428  jns     loc_1800304D8
0x18003042e  cmp     eax, 80000005h
0x180030433  jnz     loc_18003053D
0x180030439  mov     edx, [rsi]
0x18003043b  add     edx, edx
0x18003043d  jmp     short loc_1800303F7
0x18003043f  mov     rcx, [r14]; hFile
0x180030442  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180030446  mov     r9d, 8; dwBufferSize
0x18003044c  mov     [rbp+FileInformation], r13
0x180030450  mov     esi, r13d
0x180030453  mov     dword ptr [rbx], 4
0x180030459  mov     [rbx+448h], r13
0x180030460  mov     [rbx+450h], r13b
0x180030467  lea     edx, [r9+1]; FileInformationClass
0x18003046b  call    cs:__imp_GetFileInformationByHandleEx
0x180030471  test    eax, eax
0x180030473  cmovnz  esi, dword ptr [rbp+FileInformation]
0x180030477  and     esi, 200h
0x18003047d  mov     eax, esi
0x18003047f  neg     eax
0x180030481  sbb     ecx, ecx
0x180030483  and     ecx, 8
0x180030486  mov     [rbx+4], ecx
0x180030489  cmp     [rbx+478h], r13b
0x180030490  jnz     short loc_180030496
0x180030492  test    esi, esi
0x180030494  jz      short loc_1800304A5
0x180030496  mov     rcx, [r14]; FileHandle
0x180030499  mov     rdx, rbx
0x18003049c  call    BackupGetSparseMap
0x1800304a1  test    eax, eax
0x1800304a3  jnz     short loc_1800304BA
0x1800304a5  mov     rcx, [r14]; hFile
0x1800304a8  lea     rdx, [rbx+0Ch]; lpFileSizeHigh
0x1800304ac  call    cs:__imp_GetFileSize
0x1800304b2  mov     [rbx+8], eax
0x1800304b5  jmp     loc_180030399
0x1800304ba  mov     [rbx+8], r13
0x1800304be  jmp     loc_180030399
0x1800304c3  test    dword ptr [rdx+474h], 40000h
0x1800304cd  jz      loc_180030399
0x1800304d3  jmp     loc_180030253
0x1800304d8  cmp     [rbp+var_50.Information], r13
0x1800304dc  jz      loc_18003042E
0x1800304e2  mov     [rbx+454h], r13d
0x1800304e9  mov     byte ptr [rbx+468h], 1
0x1800304f0  mov     eax, [rbx+454h]
0x1800304f6  mov     rcx, [rbx+460h]
0x1800304fd  mov     qword ptr [rbx+430h], 0FFFFFFFFFFFFFFFFh
0x180030508  mov     [rbx+469h], r13b
0x18003050f  cmp     dword ptr [rax+rcx+4], 4
0x180030514  jb      short loc_180030531
0x180030516  cmp     word ptr [rax+rcx+1Ah], 3Ah ; ':'
0x18003051c  jnz     short loc_180030531
0x18003051e  mov     edx, [rax+rcx]
0x180030521  test    edx, edx
0x180030523  jz      loc_180030399
0x180030529  add     eax, edx
0x18003052b  mov     [rbx+454h], eax
0x180030531  mov     dword ptr [rbx+8], 1
0x180030538  jmp     loc_180030399
0x18003053d  cmp     eax, 0C0000023h
0x180030542  jnz     loc_180030399
0x180030548  jmp     loc_180030439
0x18003054d  mov     eax, [rsi]
0x18003054f  add     [rbx+454h], eax
0x180030555  cmp     [rsi], r13d
0x180030558  jz      loc_18003032C
0x18003055e  mov     dword ptr [rbx+8], 1
0x180030565  mov     byte ptr [rbx+46Ah], 1
0x18003056c  jmp     loc_18003032C
0x180030571  mov     eax, [rsi+4]
0x180030574  lea     rdx, BasepDataAttributeType; ":$DATA"
0x18003057b  sub     rax, 0Ch
0x18003057f  mov     r8d, 6; MaxCount
0x180030585  shr     rax, 1
0x180030588  add     rax, 0Ch
0x18003058c  lea     rcx, [rsi+rax*2]; String1
0x180030590  call    cs:__imp__wcsnicmp
0x180030596  test    eax, eax
0x180030598  jnz     loc_180030399
0x18003059e  jmp     loc_18003043F
0x1800305a3  cmp     dword ptr [rdx], 4
0x1800305a6  jz      loc_1800303B8
0x1800305ac  jmp     loc_180030399
```
