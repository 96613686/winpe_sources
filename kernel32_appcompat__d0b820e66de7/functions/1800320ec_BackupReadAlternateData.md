# BackupReadAlternateData

- ea: `0x1800320ec`
- end: `0x1800324a8`
- name: `BackupReadAlternateData`
- size: `956`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x180032610`

## callees

- `0x1800320ec`
- `0x180032ac8`
- `0x180033054`
- `0x180070a9c`
- `0x180082751`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x180032481`
- `ntdll!_wcsnicmp` at `0x180032481`
- `ntdll!NtOpenFile` at `0x1800321cf`
- `ntdll!NtOpenFile` at `0x1800321cf`
- `ntdll!NtQueryInformationFile` at `0x1800322ff`
- `ntdll!NtQueryInformationFile` at `0x1800322ff`
- `ntdll!RtlSetLastWin32Error` at `0x180032209`
- `ntdll!RtlSetLastWin32Error` at `0x180032209`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x1800321f4`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x1800321f4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180032397`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180032397`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180032350`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180032350`

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
0x1800320ec  mov     [rsp-28h+arg_0], rbx
0x1800320f1  mov     [rsp-28h+arg_10], rsi
0x1800320f6  push    rbp
0x1800320f7  push    r12
0x1800320f9  push    r13
0x1800320fb  push    r14
0x1800320fd  push    r15
0x1800320ff  mov     rbp, rsp
0x180032102  sub     rsp, 80h
0x180032109  xor     r13d, r13d
0x18003210c  mov     rbx, rdx
0x18003210f  mov     r15, rcx
0x180032112  cmp     [rdx+471h], r13b
0x180032119  jnz     loc_1800323B4
0x18003211f  cmp     [rdx+469h], r13b
0x180032126  jnz     loc_1800322A4
0x18003212c  lea     r14, [rdx+430h]
0x180032133  mov     rax, [r14]
0x180032136  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003213a  jnz     loc_18003227F
0x180032140  mov     ecx, [rdx+454h]
0x180032146  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18003214a  mov     rsi, [rdx+460h]
0x180032151  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180032155  xorps   xmm0, xmm0
0x180032158  mov     [rdx+8], r13
0x18003215c  xor     eax, eax
0x18003215e  add     rsi, rcx
0x180032161  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180032165  mov     rcx, r14; FileHandle
0x180032168  movups  xmmword ptr [rbp+var_50], xmm0
0x18003216c  lea     r12, [rsi+18h]
0x180032170  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180032174  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180032178  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18003217c  movzx   eax, word ptr [rsi+4]
0x180032180  mov     word ptr [rbp+var_50], ax
0x180032184  mov     word ptr [rbp+var_50+2], ax
0x180032188  lea     rax, [rbp+var_50]
0x18003218c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180032190  mov     eax, [rdx+46Ch]
0x180032196  mov     edx, 100081h; DesiredAccess
0x18003219b  and     eax, 400h
0x1800321a0  mov     [rbp+var_50.Information], r12
0x1800321a4  shl     eax, 0Bh
0x1800321a7  or      eax, 4020h
0x1800321ac  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800321b3  mov     [rsp+80h+OpenOptions], eax; OpenOptions
0x1800321b7  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x1800321bf  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1800321c3  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800321ca  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800321cf  call    cs:__imp_NtOpenFile
0x1800321d6  nop     dword ptr [rax+rax+00h]
0x1800321db  test    eax, eax
0x1800321dd  js      loc_18003243E
0x1800321e3  mov     rcx, [r14]; hFile
0x1800321e6  or      r9d, 0FFFFFFFFh; nNumberOfBytesToLockLow
0x1800321ea  xor     r8d, r8d; dwFileOffsetHigh
0x1800321ed  mov     [rsp+80h+ShareAccess], r9d; nNumberOfBytesToLockHigh
0x1800321f2  xor     edx, edx; dwFileOffsetLow
0x1800321f4  call    cs:__imp_LockFile
0x1800321fb  nop     dword ptr [rax+rax+00h]
0x180032200  test    eax, eax
0x180032202  jnz     short loc_180032235
0x180032204  mov     ecx, 20h ; ' '; LastError
0x180032209  call    cs:__imp_RtlSetLastWin32Error
0x180032210  nop     dword ptr [rax+rax+00h]
0x180032215  xor     eax, eax
0x180032217  lea     r11, [rsp+80h+var_s0]
0x18003221f  mov     rbx, [r11+30h]
0x180032223  mov     rsi, [r11+40h]
0x180032227  mov     rsp, r11
0x18003222a  pop     r15
0x18003222c  pop     r14
0x18003222e  pop     r13
0x180032230  pop     r12
0x180032232  pop     rbp
0x180032233  retn
0x180032235  mov     [rbx+4], r13d
0x180032239  lea     rcx, [rbx+14h]; void *
0x18003223d  mov     eax, [rsi+4]
0x180032240  mov     rdx, r12; Src
0x180032243  mov     [rbx+10h], eax
0x180032246  mov     eax, [rsi+4]
0x180032249  add     eax, 14h
0x18003224c  mov     [rbx+42Ch], eax
0x180032252  mov     r8d, [rsi+4]; Size
0x180032256  call    memcpy_0
0x18003225b  mov     eax, [rsi]
0x18003225d  test    eax, eax
0x18003225f  jz      short loc_18003226E
0x180032261  add     [rbx+454h], eax
0x180032267  mov     byte ptr [rbx+46Ah], 1
0x18003226e  cmp     dword ptr [rsi+4], 0Ch
0x180032272  ja      loc_180032462
0x180032278  mov     eax, 1
0x18003227d  jmp     short loc_180032217
0x18003227f  mov     ecx, [rdx+42Ch]
0x180032285  cmp     [rdx+420h], rcx
0x18003228c  jl      short loc_180032278
0x18003228e  cmp     dword ptr [rdx], 9
0x180032291  jnz     loc_18003249A
0x180032297  mov     rcx, rax; hFile
0x18003229a  call    BackupReadStream
0x18003229f  jmp     loc_180032217
0x1800322a4  mov     eax, [rdx+46Ch]
0x1800322aa  xorps   xmm0, xmm0
0x1800322ad  and     eax, 4010h
0x1800322b2  movups  xmmword ptr [rbp+var_50], xmm0
0x1800322b6  cmp     eax, 4000h
0x1800322bb  jz      short loc_180032278
0x1800322bd  cmp     [rdx+468h], r13b
0x1800322c4  jnz     loc_1800323E1
0x1800322ca  lea     rsi, [rdx+458h]
0x1800322d1  mov     edx, 400h
0x1800322d6  mov     rcx, rsi
0x1800322d9  call    GrowBuffer
0x1800322de  test    eax, eax
0x1800322e0  jz      loc_180032215
0x1800322e6  mov     r9d, [rsi]; Length
0x1800322e9  lea     rdx, [rbp+var_50]; IoStatusBlock
0x1800322ed  mov     r8, [rbx+460h]; FileInformation
0x1800322f4  mov     rcx, r15; FileHandle
0x1800322f7  mov     [rsp+80h+ShareAccess], 16h; FileInformationClass
0x1800322ff  call    cs:__imp_NtQueryInformationFile
0x180032306  nop     dword ptr [rax+rax+00h]
0x18003230b  test    eax, eax
0x18003230d  jns     loc_1800323C9
0x180032313  cmp     eax, 80000005h
0x180032318  jnz     loc_18003242E
0x18003231e  mov     edx, [rsi]
0x180032320  add     edx, edx
0x180032322  jmp     short loc_1800322D6
0x180032324  mov     rcx, [r14]; hFile
0x180032327  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18003232b  mov     r9d, 8; dwBufferSize
0x180032331  mov     [rbp+FileInformation], r13
0x180032335  mov     esi, r13d
0x180032338  mov     dword ptr [rbx], 4
0x18003233e  mov     [rbx+448h], r13
0x180032345  mov     [rbx+450h], r13b
0x18003234c  lea     edx, [r9+1]; FileInformationClass
0x180032350  call    cs:__imp_GetFileInformationByHandleEx
0x180032357  nop     dword ptr [rax+rax+00h]
0x18003235c  test    eax, eax
0x18003235e  cmovnz  esi, dword ptr [rbp+FileInformation]
0x180032362  and     esi, 200h
0x180032368  mov     eax, esi
0x18003236a  neg     eax
0x18003236c  sbb     ecx, ecx
0x18003236e  and     ecx, 8
0x180032371  mov     [rbx+4], ecx
0x180032374  cmp     [rbx+478h], r13b
0x18003237b  jnz     short loc_180032381
0x18003237d  test    esi, esi
0x18003237f  jz      short loc_180032390
0x180032381  mov     rcx, [r14]; FileHandle
0x180032384  mov     rdx, rbx
0x180032387  call    BackupGetSparseMap
0x18003238c  test    eax, eax
0x18003238e  jnz     short loc_1800323AB
0x180032390  mov     rcx, [r14]; hFile
0x180032393  lea     rdx, [rbx+0Ch]; lpFileSizeHigh
0x180032397  call    cs:__imp_GetFileSize
0x18003239e  nop     dword ptr [rax+rax+00h]
0x1800323a3  mov     [rbx+8], eax
0x1800323a6  jmp     loc_180032278
0x1800323ab  mov     [rbx+8], r13
0x1800323af  jmp     loc_180032278
0x1800323b4  test    dword ptr [rdx+474h], 40000h
0x1800323be  jz      loc_180032278
0x1800323c4  jmp     loc_18003211F
0x1800323c9  cmp     [rbp+var_50.Information], r13
0x1800323cd  jz      loc_180032313
0x1800323d3  mov     [rbx+454h], r13d
0x1800323da  mov     byte ptr [rbx+468h], 1
0x1800323e1  mov     eax, [rbx+454h]
0x1800323e7  mov     rcx, [rbx+460h]
0x1800323ee  mov     qword ptr [rbx+430h], 0FFFFFFFFFFFFFFFFh
0x1800323f9  mov     [rbx+469h], r13b
0x180032400  cmp     dword ptr [rax+rcx+4], 4
0x180032405  jb      short loc_180032422
0x180032407  cmp     word ptr [rax+rcx+1Ah], 3Ah ; ':'
0x18003240d  jnz     short loc_180032422
0x18003240f  mov     edx, [rax+rcx]
0x180032412  test    edx, edx
0x180032414  jz      loc_180032278
0x18003241a  add     eax, edx
0x18003241c  mov     [rbx+454h], eax
0x180032422  mov     dword ptr [rbx+8], 1
0x180032429  jmp     loc_180032278
0x18003242e  cmp     eax, 0C0000023h
0x180032433  jnz     loc_180032278
0x180032439  jmp     loc_18003231E
0x18003243e  mov     eax, [rsi]
0x180032440  add     [rbx+454h], eax
0x180032446  cmp     [rsi], r13d
0x180032449  jz      loc_180032204
0x18003244f  mov     dword ptr [rbx+8], 1
0x180032456  mov     byte ptr [rbx+46Ah], 1
0x18003245d  jmp     loc_180032204
0x180032462  mov     eax, [rsi+4]
0x180032465  lea     rdx, BasepDataAttributeType; ":$DATA"
0x18003246c  sub     rax, 0Ch
0x180032470  mov     r8d, 6; MaxCount
0x180032476  shr     rax, 1
0x180032479  add     rax, 0Ch
0x18003247d  lea     rcx, [rsi+rax*2]; String1
0x180032481  call    cs:__imp__wcsnicmp
0x180032488  nop     dword ptr [rax+rax+00h]
0x18003248d  test    eax, eax
0x18003248f  jnz     loc_180032278
0x180032495  jmp     loc_180032324
0x18003249a  cmp     dword ptr [rdx], 4
0x18003249d  jz      loc_180032297
0x1800324a3  jmp     loc_180032278
```
