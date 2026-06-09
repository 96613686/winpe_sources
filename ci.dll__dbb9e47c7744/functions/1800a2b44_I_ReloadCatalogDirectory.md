# I_ReloadCatalogDirectory

- ea: `0x1800a2b44`
- end: `0x1800a2f92`
- name: `I_ReloadCatalogDirectory`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061984`

## callees

- `0x18000c52c`
- `0x1800a2b44`
- `0x1800a2f98`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2c8e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2c8e`
- `ntoskrnl!ExAllocatePool2` at `0x1800a2c53`
- `ntoskrnl!ExAllocatePool2` at `0x1800a2c53`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2f81`
- `ntoskrnl!ZwOpenFile` at `0x1800a2bfc`
- `ntoskrnl!ZwOpenFile` at `0x1800a2bfc`
- `ntoskrnl!ZwClose` at `0x1800a2c17`
- `ntoskrnl!ZwClose` at `0x1800a2c17`
- `ntoskrnl!qsort` at `0x1800a2d76`
- `ntoskrnl!qsort` at `0x1800a2d76`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a2ce3`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a2ce3`

## pseudocode

```c
__int64 __fastcall I_ReloadCatalogDirectory(
        int a1,
        char a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        UNICODE_STRING *a7,
        _DWORD *a8)
{
  unsigned int *v8; // rdi
  UNICODE_STRING *v9; // r14
  NTSTATUS v10; // esi
  __int64 Pool2; // rax
  _QWORD *v13; // r12
  unsigned int *v14; // r15
  BOOLEAN RestartScan; // bl
  FILE_INFORMATION_CLASS FileInformationClass; // ecx
  NTSTATUS v17; // eax
  unsigned int *i; // rbx
  __int64 v19; // r14
  unsigned int v20; // eax
  _WORD *j; // rcx
  __int64 v22; // rax
  __int64 k; // r12
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  __int64 v29; // [rsp+68h] [rbp-81h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-71h] BYREF
  PCUNICODE_STRING v32; // [rsp+88h] [rbp-61h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-19h] BYREF
  int v38; // [rsp+148h] [rbp+5Fh]
  FILE_INFORMATION_CLASS v40; // [rsp+168h] [rbp+7Fh]

  FileHandle = 0;
  LODWORD(v29) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v8 = 0;
  memset(&ObjectAttributes.Length + 1, 0, 20);
  IoStatusBlock = 0;
  DestinationString = 0;
  SourceString = 0;
  CiGetCurrentSiloState();
  v9 = (UNICODE_STRING *)&stru_18002EFE0;
  ObjectAttributes.Length = 48;
  *a8 = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a7 )
    v9 = a7;
  v32 = v9;
  ObjectAttributes.ObjectName = v9;
  v10 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v10 >= 0 )
  {
    Pool2 = ExAllocatePool2(258, 155648, 1919109443);
    v8 = (unsigned int *)Pool2;
    if ( Pool2 )
    {
      v10 = 0;
      v13 = (_QWORD *)(Pool2 + 153600);
      v14 = 0;
      v38 = 0;
      RestartScan = 1;
      _InterlockedIncrement(&g_ReloadInProgressCount);
      RtlInitUnicodeString(&DestinationString, L"*.cat");
      FileInformationClass = FileIdFullDirectoryInformation;
LABEL_11:
      while ( 1 )
      {
        v40 = FileInformationClass;
        while ( 1 )
        {
          v17 = ZwQueryDirectoryFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  v8,
                  0x25800u,
                  FileInformationClass,
                  v14 != 0,
                  &DestinationString,
                  RestartScan);
          if ( v17 < 0 )
            break;
          if ( v14 )
          {
            SourceString.Buffer = (PWSTR)(v14 + 16);
            SourceString.MaximumLength = *((_WORD *)v14 + 30);
            SourceString.Length = SourceString.MaximumLength;
            v27 = I_ReloadCatalog(
                    a1,
                    0,
                    a4,
                    a5,
                    a6,
                    &SourceString,
                    v32,
                    0,
                    0,
                    (__int64)(v14 + 6),
                    (__int64)(v14 + 8),
                    (__int64)&v29);
            if ( v27 < 0 )
            {
              if ( v27 == -1073741801 || v27 == -1073741670 )
                v10 = v27;
            }
            else
            {
              v28 = v29;
              *a8 |= v29;
              if ( v28 )
                ++v38;
            }
          }
          else
          {
            for ( i = v8; ; i = (unsigned int *)((char *)i + v26) )
            {
              v19 = 0;
              while ( 1 )
              {
                if ( a2 )
                {
                  v20 = i[15] >> 1;
                  if ( v20 >= 0xB )
                  {
                    for ( j = i + 20; j < (_WORD *)i + v20 + 30; ++j )
                    {
                      if ( *j == 126 && j[3] == 45 && j[6] == 126 )
                        goto LABEL_26;
                    }
                  }
                }
                v13[v19] = i;
                v19 = (unsigned int)(v19 + 1);
LABEL_26:
                v22 = *i;
                if ( !(_DWORD)v22 || (_DWORD)v19 == 256 )
                  break;
                i = (unsigned int *)((char *)i + v22);
              }
              qsort(v13, (unsigned int)v19, 8u, I_SortDirectoryInfoByFileId);
              for ( k = 0; (unsigned int)k < (unsigned int)v19; k = (unsigned int)(k + 1) )
              {
                SourceString.Buffer = (PWSTR)(*(_QWORD *)&v8[2 * k + 38400] + 80LL);
                SourceString.MaximumLength = *(_WORD *)(*(_QWORD *)&v8[2 * k + 38400] + 60LL);
                SourceString.Length = SourceString.MaximumLength;
                v24 = I_ReloadCatalog(
                        a1,
                        0,
                        a4,
                        a5,
                        a6,
                        &SourceString,
                        v32,
                        (int)FileHandle,
                        (unsigned int)*(_QWORD *)&v8[2 * k + 38400] + 72,
                        *(_QWORD *)&v8[2 * k + 38400] + 24LL,
                        *(_QWORD *)&v8[2 * k + 38400] + 32LL,
                        (__int64)&v29);
                if ( v24 < 0 )
                {
                  if ( !v38 )
                  {
                    FileInformationClass = FileDirectoryInformation;
                    v13 = v8 + 38400;
                    RestartScan = 1;
                    v14 = v8;
                    goto LABEL_11;
                  }
                  if ( v24 == -1073741670 || v24 == -1073741801 )
                    v10 = v24;
                }
                else
                {
                  v25 = v29;
                  *a8 |= v29;
                  if ( v25 )
                    ++v38;
                }
              }
              v26 = *i;
              v13 = v8 + 38400;
              if ( !(_DWORD)v26 )
                break;
            }
          }
          FileInformationClass = v40;
          RestartScan = 0;
        }
        if ( !RestartScan || v14 )
          break;
        v14 = v8;
        FileInformationClass = FileDirectoryInformation;
      }
      if ( v10 >= 0 && (v17 == -1073741801 || v17 == -1073741670) )
        v10 = v17;
      _InterlockedDecrement(&g_ReloadInProgressCount);
    }
    else
    {
      v10 = -1073741801;
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x72634943u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a2b44  mov     rax, rsp
0x1800a2b47  mov     [rax+20h], r9d
0x1800a2b4b  mov     [rax+18h], r8b
0x1800a2b4f  mov     [rax+10h], dl
0x1800a2b52  mov     [rax+8], rcx
0x1800a2b56  push    rbp
0x1800a2b57  push    rbx
0x1800a2b58  push    rsi
0x1800a2b59  push    rdi
0x1800a2b5a  push    r12
0x1800a2b5c  push    r13
0x1800a2b5e  push    r14
0x1800a2b60  push    r15
0x1800a2b62  lea     rbp, [rax-47h]
0x1800a2b66  sub     rsp, 0E8h
0x1800a2b6d  xorps   xmm0, xmm0
0x1800a2b70  xor     ebx, ebx
0x1800a2b72  xorps   xmm1, xmm1
0x1800a2b75  mov     [rbp+3Fh+FileHandle], rbx
0x1800a2b79  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x1800a2b7d  xor     eax, eax
0x1800a2b7f  mov     dword ptr [rsp+120h+var_C0], ebx
0x1800a2b83  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x1800a2b87  mov     edi, ebx
0x1800a2b89  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x1800a2b8d  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1800a2b91  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x1800a2b95  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x1800a2b99  call    CiGetCurrentSiloState
0x1800a2b9e  mov     rax, [rbp+3Fh+arg_38]
0x1800a2ba5  lea     r14, stru_18002EFE0
0x1800a2bac  xorps   xmm0, xmm0
0x1800a2baf  mov     [rsp+120h+OpenOptions], 4021h; OpenOptions
0x1800a2bb7  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1800a2bbb  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1800a2bc2  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1800a2bc6  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x1800a2bca  mov     [rax], ebx
0x1800a2bcc  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1800a2bd0  mov     rax, [rbp+3Fh+arg_30]
0x1800a2bd4  mov     edx, 100001h; DesiredAccess
0x1800a2bd9  test    rax, rax
0x1800a2bdc  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1800a2be3  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a2be8  cmovnz  r14, rax
0x1800a2bec  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x1800a2bf4  mov     [rbp+3Fh+var_A0], r14
0x1800a2bf8  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x1800a2bfc  call    cs:__imp_ZwOpenFile
0x1800a2c03  nop     dword ptr [rax+rax+00h]
0x1800a2c08  mov     esi, eax
0x1800a2c0a  test    eax, eax
0x1800a2c0c  jns     short loc_1800A2C43
0x1800a2c0e  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1800a2c12  test    rcx, rcx
0x1800a2c15  jz      short loc_1800A2C23
0x1800a2c17  call    cs:__imp_ZwClose
0x1800a2c1e  nop     dword ptr [rax+rax+00h]
0x1800a2c23  test    rdi, rdi
0x1800a2c26  jnz     loc_1800A2F79
0x1800a2c2c  mov     eax, esi
0x1800a2c2e  add     rsp, 0E8h
0x1800a2c35  pop     r15
0x1800a2c37  pop     r14
0x1800a2c39  pop     r13
0x1800a2c3b  pop     r12
0x1800a2c3d  pop     rdi
0x1800a2c3e  pop     rsi
0x1800a2c3f  pop     rbx
0x1800a2c40  pop     rbp
0x1800a2c41  retn
0x1800a2c43  mov     edx, 26000h
0x1800a2c48  mov     ecx, 102h
0x1800a2c4d  mov     r8d, 72634943h
0x1800a2c53  call    cs:__imp_ExAllocatePool2
0x1800a2c5a  nop     dword ptr [rax+rax+00h]
0x1800a2c5f  mov     rdi, rax
0x1800a2c62  test    rax, rax
0x1800a2c65  jz      loc_1800A2F34
0x1800a2c6b  xor     esi, esi
0x1800a2c6d  lea     r12, [rax+25800h]
0x1800a2c74  xor     r15d, r15d
0x1800a2c77  mov     [rbp+3Fh+arg_10], esi
0x1800a2c7a  mov     bl, 1
0x1800a2c7c  lock inc cs:g_ReloadInProgressCount
0x1800a2c83  lea     rdx, aCat; "*.cat"
0x1800a2c8a  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800a2c8e  call    cs:__imp_RtlInitUnicodeString
0x1800a2c95  nop     dword ptr [rax+rax+00h]
0x1800a2c9a  lea     ecx, [rsi+26h]
0x1800a2c9d  mov     r13d, 0C0000017h
0x1800a2ca3  mov     dword ptr [rbp+3Fh+arg_30], ecx
0x1800a2ca6  mov     [rsp+120h+RestartScan], bl; RestartScan
0x1800a2caa  lea     rdx, [rbp+3Fh+DestinationString]
0x1800a2cae  mov     [rsp+120h+FileName], rdx; FileName
0x1800a2cb3  test    r15, r15
0x1800a2cb6  setnz   al
0x1800a2cb9  xor     r9d, r9d; ApcContext
0x1800a2cbc  mov     [rsp+120h+ReturnSingleEntry], al; ReturnSingleEntry
0x1800a2cc0  xor     r8d, r8d; ApcRoutine
0x1800a2cc3  mov     [rsp+120h+FileInformationClass], ecx; FileInformationClass
0x1800a2cc7  lea     rax, [rbp+3Fh+IoStatusBlock]
0x1800a2ccb  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1800a2ccf  xor     edx, edx; Event
0x1800a2cd1  mov     [rsp+120h+Length], 25800h; Length
0x1800a2cd9  mov     qword ptr [rsp+120h+OpenOptions], rdi; FileInformation
0x1800a2cde  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x1800a2ce3  call    cs:__imp_ZwQueryDirectoryFile
0x1800a2cea  nop     dword ptr [rax+rax+00h]
0x1800a2cef  test    eax, eax
0x1800a2cf1  js      loc_1800A2F0C
0x1800a2cf7  test    r15, r15
0x1800a2cfa  jnz     loc_1800A2E7B
0x1800a2d00  mov     rbx, rdi
0x1800a2d03  mov     r13b, [rbp+3Fh+arg_8]
0x1800a2d07  xor     r14d, r14d
0x1800a2d0a  test    r13b, r13b
0x1800a2d0d  jz      short loc_1800A2D48
0x1800a2d0f  mov     eax, [rbx+3Ch]
0x1800a2d12  shr     eax, 1
0x1800a2d14  cmp     eax, 0Bh
0x1800a2d17  jb      short loc_1800A2D48
0x1800a2d19  mov     edx, eax
0x1800a2d1b  lea     rcx, [rbx+50h]
0x1800a2d1f  add     rdx, 0FFFFFFFFFFFFFFF6h
0x1800a2d23  lea     rdx, [rcx+rdx*2]
0x1800a2d27  cmp     rcx, rdx
0x1800a2d2a  jnb     short loc_1800A2D48
0x1800a2d2c  cmp     word ptr [rcx], 7Eh ; '~'
0x1800a2d30  jz      short loc_1800A2D38
0x1800a2d32  add     rcx, 2
0x1800a2d36  jmp     short loc_1800A2D27
0x1800a2d38  cmp     word ptr [rcx+6], 2Dh ; '-'
0x1800a2d3d  jnz     short loc_1800A2D32
0x1800a2d3f  cmp     word ptr [rcx+0Ch], 7Eh ; '~'
0x1800a2d44  jnz     short loc_1800A2D32
0x1800a2d46  jmp     short loc_1800A2D4F
0x1800a2d48  mov     [r12+r14*8], rbx
0x1800a2d4c  inc     r14d
0x1800a2d4f  mov     eax, [rbx]
0x1800a2d51  test    eax, eax
0x1800a2d53  jz      short loc_1800A2D63
0x1800a2d55  cmp     r14d, 100h
0x1800a2d5c  jz      short loc_1800A2D63
0x1800a2d5e  add     rbx, rax
0x1800a2d61  jmp     short loc_1800A2D0A
0x1800a2d63  mov     edx, r14d; NumOfElements
0x1800a2d66  lea     r9, I_SortDirectoryInfoByFileId; PtFuncCompare
0x1800a2d6d  mov     r8d, 8; SizeOfElements
0x1800a2d73  mov     rcx, r12; Base
0x1800a2d76  call    cs:__imp_qsort
0x1800a2d7d  nop     dword ptr [rax+rax+00h]
0x1800a2d82  xor     r12d, r12d
0x1800a2d85  mov     r13d, 0C0000017h
0x1800a2d8b  cmp     r12d, r14d
0x1800a2d8e  jnb     loc_1800A2E60
0x1800a2d94  mov     r9d, [rbp+3Fh+arg_20]; int
0x1800a2d98  lea     r8, [rdi+25800h]
0x1800a2d9f  mov     rax, [r8+r12*8]
0x1800a2da3  add     rax, 50h ; 'P'
0x1800a2da7  mov     [rbp+3Fh+SourceString.Buffer], rax
0x1800a2dab  mov     rax, [r8+r12*8]
0x1800a2daf  movzx   ecx, word ptr [rax+3Ch]
0x1800a2db3  mov     [rbp+3Fh+SourceString.MaximumLength], cx
0x1800a2db7  mov     [rbp+3Fh+SourceString.Length], cx
0x1800a2dbb  mov     rax, [r8+r12*8]
0x1800a2dbf  lea     r8, [rsp+120h+var_C0]
0x1800a2dc4  mov     [rsp+120h+var_C8], r8; __int64
0x1800a2dc9  mov     r8d, [rbp+3Fh+arg_18]; int
0x1800a2dcd  lea     rcx, [rax+20h]
0x1800a2dd1  lea     rdx, [rax+18h]
0x1800a2dd5  mov     qword ptr [rsp+120h+RestartScan], rcx; __int64
0x1800a2dda  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x1800a2dde  add     rax, 48h ; 'H'
0x1800a2de2  mov     [rsp+120h+FileName], rdx; __int64
0x1800a2de7  xor     edx, edx; int
0x1800a2de9  mov     qword ptr [rsp+120h+ReturnSingleEntry], rax; int
0x1800a2dee  mov     rax, [rbp+3Fh+FileHandle]
0x1800a2df2  mov     qword ptr [rsp+120h+FileInformationClass], rax; int
0x1800a2df7  mov     rax, [rbp+3Fh+var_A0]
0x1800a2dfb  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x1800a2e00  lea     rax, [rbp+3Fh+SourceString]
0x1800a2e04  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x1800a2e09  mov     eax, [rbp+3Fh+arg_28]
0x1800a2e0c  mov     [rsp+120h+ShareAccess], eax; int
0x1800a2e10  call    I_ReloadCatalog
0x1800a2e15  test    eax, eax
0x1800a2e17  js      short loc_1800A2E35
0x1800a2e19  mov     eax, dword ptr [rsp+120h+var_C0]
0x1800a2e1d  mov     rcx, [rbp+3Fh+arg_38]
0x1800a2e24  or      [rcx], eax
0x1800a2e26  test    eax, eax
0x1800a2e28  jz      short loc_1800A2E2D
0x1800a2e2a  inc     [rbp+3Fh+arg_10]
0x1800a2e2d  inc     r12d
0x1800a2e30  jmp     loc_1800A2D8B
0x1800a2e35  cmp     [rbp+3Fh+arg_10], 0
0x1800a2e39  jnz     short loc_1800A2E51
0x1800a2e3b  mov     ecx, 1
0x1800a2e40  lea     r12, [rdi+25800h]
0x1800a2e47  mov     bl, cl
0x1800a2e49  mov     r15, rdi
0x1800a2e4c  jmp     loc_1800A2CA3
0x1800a2e51  cmp     eax, 0C000009Ah
0x1800a2e56  jnz     loc_1800A2F3E
0x1800a2e5c  mov     esi, eax
0x1800a2e5e  jmp     short loc_1800A2E2D
0x1800a2e60  mov     eax, [rbx]
0x1800a2e62  lea     r12, [rdi+25800h]
0x1800a2e69  test    eax, eax
0x1800a2e6b  jnz     loc_1800A2F2C
0x1800a2e71  mov     ecx, dword ptr [rbp+3Fh+arg_30]
0x1800a2e74  xor     bl, bl
0x1800a2e76  jmp     loc_1800A2CA6
0x1800a2e7b  mov     r9d, [rbp+3Fh+arg_20]; int
0x1800a2e7f  lea     rax, [r15+40h]
0x1800a2e83  mov     r8d, [rbp+3Fh+arg_18]; int
0x1800a2e87  lea     rdx, [rsp+120h+var_C0]
0x1800a2e8c  mov     [rsp+120h+var_C8], rdx; __int64
0x1800a2e91  lea     rcx, [r15+18h]
0x1800a2e95  mov     [rbp+3Fh+SourceString.Buffer], rax
0x1800a2e99  xor     edx, edx; int
0x1800a2e9b  movzx   eax, word ptr [r15+3Ch]
0x1800a2ea0  mov     [rbp+3Fh+SourceString.MaximumLength], ax
0x1800a2ea4  mov     [rbp+3Fh+SourceString.Length], ax
0x1800a2ea8  lea     rax, [r15+20h]
0x1800a2eac  mov     qword ptr [rsp+120h+RestartScan], rax; __int64
0x1800a2eb1  mov     rax, [rbp+3Fh+var_A0]
0x1800a2eb5  mov     [rsp+120h+FileName], rcx; __int64
0x1800a2eba  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x1800a2ebe  mov     qword ptr [rsp+120h+ReturnSingleEntry], 0; int
0x1800a2ec7  mov     qword ptr [rsp+120h+FileInformationClass], 0; int
0x1800a2ed0  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x1800a2ed5  lea     rax, [rbp+3Fh+SourceString]
0x1800a2ed9  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x1800a2ede  mov     eax, [rbp+3Fh+arg_28]
0x1800a2ee1  mov     [rsp+120h+ShareAccess], eax; int
0x1800a2ee5  call    I_ReloadCatalog
0x1800a2eea  test    eax, eax
0x1800a2eec  js      short loc_1800A2F4C
0x1800a2eee  mov     eax, dword ptr [rsp+120h+var_C0]
0x1800a2ef2  mov     r14, [rbp+3Fh+arg_38]
0x1800a2ef9  or      [r14], eax
0x1800a2efc  test    eax, eax
0x1800a2efe  jz      loc_1800A2E71
0x1800a2f04  inc     [rbp+3Fh+arg_10]
0x1800a2f07  jmp     loc_1800A2E71
0x1800a2f0c  test    bl, bl
0x1800a2f0e  jnz     short loc_1800A2F63
0x1800a2f10  test    esi, esi
0x1800a2f12  js      short loc_1800A2F20
0x1800a2f14  cmp     eax, r13d
0x1800a2f17  jz      short loc_1800A2F75
0x1800a2f19  cmp     eax, 0C000009Ah
0x1800a2f1e  jz      short loc_1800A2F75
0x1800a2f20  lock dec cs:g_ReloadInProgressCount
0x1800a2f27  jmp     loc_1800A2C0E
0x1800a2f2c  add     rbx, rax
0x1800a2f2f  jmp     loc_1800A2D03
0x1800a2f34  mov     esi, 0C0000017h
0x1800a2f39  jmp     loc_1800A2C0E
0x1800a2f3e  cmp     eax, r13d
0x1800a2f41  jz      loc_1800A2E5C
0x1800a2f47  jmp     loc_1800A2E2D
0x1800a2f4c  cmp     eax, r13d
0x1800a2f4f  jz      short loc_1800A2F5C
0x1800a2f51  cmp     eax, 0C000009Ah
0x1800a2f56  jnz     loc_1800A2E71
0x1800a2f5c  mov     esi, eax
0x1800a2f5e  jmp     loc_1800A2E71
0x1800a2f63  test    r15, r15
0x1800a2f66  jnz     short loc_1800A2F10
0x1800a2f68  mov     r15, rdi
0x1800a2f6b  mov     ecx, 1
0x1800a2f70  jmp     loc_1800A2CA3
0x1800a2f75  mov     esi, eax
0x1800a2f77  jmp     short loc_1800A2F20
0x1800a2f79  mov     edx, 72634943h; Tag
0x1800a2f7e  mov     rcx, rdi; P
0x1800a2f81  call    cs:__imp_ExFreePoolWithTag
0x1800a2f88  nop     dword ptr [rax+rax+00h]
0x1800a2f8d  jmp     loc_1800A2C2C
```
