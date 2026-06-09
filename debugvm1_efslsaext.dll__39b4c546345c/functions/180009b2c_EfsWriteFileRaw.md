# EfsWriteFileRaw

- ea: `0x180009b2c`
- end: `0x18000a681`
- name: `EfsWriteFileRaw`
- size: `2901`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007d00`

## callees

- `0x1800064f4`
- `0x180006590`
- `0x18000662c`
- `0x180006708`
- `0x1800068c8`
- `0x180007e6c`
- `0x180008a94`
- `0x180008aec`
- `0x180008bd0`
- `0x180008d38`
- `0x180008e54`
- `0x180008f88`
- `0x180009b2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be5`
- `ntdll!NtWriteFile` at `0x18000a563`
- `ntdll!NtWriteFile` at `0x18000a563`
- `ntdll!NtClose` at `0x180009c02`
- `ntdll!NtClose` at `0x18000a133`
- `ntdll!NtClose` at `0x18000a3a6`
- `ntdll!NtClose` at `0x180009c02`
- `ntdll!NtClose` at `0x18000a133`
- `ntdll!NtClose` at `0x18000a3a6`
- `ntdll!NtCreateFile` at `0x18000a2ca`
- `ntdll!NtCreateFile` at `0x18000a3f9`
- `ntdll!NtCreateFile` at `0x18000a2ca`
- `ntdll!NtCreateFile` at `0x18000a3f9`
- `ntdll!NtFsControlFile` at `0x18000a4fc`
- `ntdll!NtFsControlFile` at `0x18000a4fc`
- `ntdll!RtlNtStatusToDosError` at `0x18000a2f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000a370`
- `ntdll!RtlNtStatusToDosError` at `0x18000a427`
- `ntdll!RtlNtStatusToDosError` at `0x18000a5a6`
- `ntdll!RtlNtStatusToDosError` at `0x18000a2f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000a370`
- `ntdll!RtlNtStatusToDosError` at `0x18000a427`
- `ntdll!RtlNtStatusToDosError` at `0x18000a5a6`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180009bdb`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180009bdb`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180009c9d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180009c9d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009c18`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009c18`

## pseudocode

```c
__int64 __fastcall EfsWriteFileRaw(__int64 a1, void *a2)
{
  char *v4; // r14
  char v5; // dl
  int v6; // r15d
  BOOL VolumeInformationByHandleW; // eax
  ULONG LastError; // ebx
  char *v10; // rax
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // r8d
  char *v15; // r13
  int v16; // edx
  int v17; // ecx
  unsigned int v18; // esi
  unsigned int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // r15d
  signed int v22; // ebx
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // rbx
  char *v26; // r13
  unsigned int v27; // eax
  NTSTATUS v28; // r15d
  char *v29; // r13
  unsigned int v30; // r12d
  unsigned int v31; // ecx
  unsigned int v32; // eax
  int v33; // ecx
  unsigned int v34; // r12d
  unsigned int v35; // eax
  int v36; // ecx
  __int16 v37; // ax
  char *v38; // r13
  ULONG v39; // eax
  NTSTATUS v40; // eax
  int v41; // ecx
  unsigned int v42; // r8d
  int v43; // eax
  int v44; // ecx
  NTSTATUS v45; // eax
  int v46; // ecx
  void *v47; // r13
  ULONG v48; // r12d
  NTSTATUS v49; // eax
  int v50; // ecx
  NTSTATUS v51; // eax
  int v52; // ecx
  char lpMaximumComponentLength; // [rsp+20h] [rbp-138h]
  unsigned int lpMaximumComponentLengtha; // [rsp+20h] [rbp-138h]
  int lpFileSystemFlags; // [rsp+28h] [rbp-130h]
  char v56; // [rsp+60h] [rbp-F8h]
  char v57; // [rsp+61h] [rbp-F7h]
  char v58; // [rsp+62h] [rbp-F6h]
  unsigned int v59; // [rsp+70h] [rbp-E8h] BYREF
  unsigned int v60; // [rsp+74h] [rbp-E4h]
  NTSTATUS v61; // [rsp+78h] [rbp-E0h]
  ULONG ShareAccess; // [rsp+7Ch] [rbp-DCh]
  HANDLE Handle; // [rsp+80h] [rbp-D8h] BYREF
  int v64; // [rsp+88h] [rbp-D0h]
  unsigned int v65; // [rsp+8Ch] [rbp-CCh] BYREF
  int v66; // [rsp+90h] [rbp-C8h]
  void *v67; // [rsp+98h] [rbp-C0h] BYREF
  DWORD FileSystemFlags; // [rsp+A0h] [rbp-B8h] BYREF
  ULONG v69; // [rsp+A4h] [rbp-B4h]
  char *v70; // [rsp+A8h] [rbp-B0h]
  HANDLE *v71; // [rsp+B0h] [rbp-A8h]
  int v72; // [rsp+B8h] [rbp-A0h]
  __int128 v73; // [rsp+C0h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-88h] BYREF
  HANDLE *v75; // [rsp+E0h] [rbp-78h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-70h] BYREF
  char v79; // [rsp+170h] [rbp+18h]
  unsigned __int8 v80; // [rsp+178h] [rbp+20h] BYREF

  v59 = 0;
  v4 = 0;
  IoStatusBlock = 0;
  Handle = 0;
  v73 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v5 = 0;
  v56 = 0;
  FileSystemFlags = 0;
  if ( *(_DWORD *)a1 != 1 || (v6 = *(_DWORD *)(a1 + 4), (v6 & 3) != 1) )
  {
    LastError = 5;
    goto LABEL_6;
  }
  v71 = (HANDLE *)(a1 + 8);
  VolumeInformationByHandleW = GetVolumeInformationByHandleW(*(HANDLE *)(a1 + 8), 0, 0, 0, 0, &FileSystemFlags, 0, 0);
  if ( VolumeInformationByHandleW )
  {
    v66 = v6 & 0x8000;
    LOBYTE(VolumeInformationByHandleW) = 0;
    v64 = VolumeInformationByHandleW;
    if ( (FileSystemFlags & 0x40000) != 0 )
    {
      v57 = 1;
    }
    else
    {
      v57 = 0;
      v64 = (*(_BYTE *)(a1 + 4) & 4) != 0;
    }
    v65 = 73728;
    v10 = (char *)VirtualAlloc(0, 0x12000u, 0x1000u, 4u);
    v4 = v10;
    v67 = v10;
    if ( !v10 )
    {
      fnEfsLogTrace1(v11, (unsigned int)EFS_ERROR_MEMORY, 73728, 11, 89);
      LastError = 14;
      goto LABEL_5;
    }
    v12 = EfspReceivePipeData(v10, 0x46u, a2, &v59);
    LastError = v12;
    if ( v59 != 70 )
    {
      fnEfsLogTrace2(v13, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 70, v59, 11, 110);
      LastError = 11;
      goto LABEL_5;
    }
    if ( v12 )
    {
      lpMaximumComponentLength = 116;
LABEL_21:
      v14 = v12;
LABEL_22:
      fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v14, 11, lpMaximumComponentLength);
      goto LABEL_5;
    }
    v15 = v4 + 4;
    if ( EfspCheckSignature(v4 + 4) != 1
      || EfspCheckSignature(v4 + 24) != 2
      || EfspCheckSignature(v4 + 54) != 3
      || *((_WORD *)v4 + 24) != 6416
      || *(_DWORD *)v4 != 256 )
    {
      LastError = 11;
      goto LABEL_5;
    }
    v18 = *(_DWORD *)(v4 + 66);
    *(_DWORD *)v4 = v18;
    v19 = 2 * v18;
    if ( 2 * v18 < v18 )
    {
      v21 = 0;
      v22 = -2147024362;
      fnEfsLogTrace3(v17, v16, -2147024362, v18, v18, lpFileSystemFlags, 169);
    }
    else
    {
      v20 = v19 + 4096;
      v21 = -1;
      if ( v19 + 4096 >= v19 )
        v21 = v19 + 4096;
      v22 = v20 < v19 ? 0x80070216 : 0;
      if ( v20 < v19 )
        fnEfsLogTrace3(v17, v16, v22, v19, 0, lpFileSystemFlags, 178);
    }
    if ( v22 < 0 || v18 < 4 )
    {
      LastError = 13;
      goto LABEL_5;
    }
    if ( v21 > 0x11FFC )
    {
      v23 = EfspResizeWorkBuffer(v4, 4u, v21, &v67, &v65);
      LastError = v23;
      if ( v23 )
      {
        fnEfsLogTrace1(v24, (unsigned int)EFS_API_ERROR, v23, 11, 198);
LABEL_39:
        v4 = (char *)v67;
        goto LABEL_5;
      }
      v4 = (char *)v67;
      v15 = (char *)v67 + 4;
    }
    v12 = EfspReceivePipeData(v15, v18, a2, &v59);
    LastError = v12;
    if ( v12 )
    {
      lpMaximumComponentLength = -46;
      goto LABEL_21;
    }
    v25 = v59;
    if ( v18 <= v59 )
    {
      v79 = 1;
      if ( v18 != v59 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = v25;
      v60 = *(_DWORD *)&v15[v25 - 4];
    }
    else
    {
      v79 = 0;
      v60 = 0;
    }
    v26 = v15 - 4;
    v80 = 0;
    if ( v18 >= 0x20 )
    {
      v13 = *((_DWORD *)v26 + 2);
      if ( (unsigned int)(v13 - 1) <= 2 )
      {
        v27 = EfslValidateEfsStream(v26, v18, &v80);
LABEL_53:
        LastError = v27;
        goto LABEL_55;
      }
      if ( v13 == 4 )
      {
        v27 = EfsxValidateEfsStream((struct _EFS_DATA_STREAM_HEADER *)v26, v18, &v80);
        goto LABEL_53;
      }
    }
    LastError = 13;
LABEL_55:
    if ( LastError )
    {
      lpMaximumComponentLength = -3;
    }
    else
    {
      if ( v80 )
      {
        v75 = v71;
        v12 = EfspOverwriteEfsAttr(*v71, (struct _EFS_DATA_STREAM_HEADER *)v26);
        LastError = v12;
        if ( !v12 )
        {
          v28 = 0;
          v61 = 0;
          v58 = 0;
          v80 = 1;
          ShareAccess = 0;
          v69 = 0;
          v72 = v66;
          v29 = v4 + 4;
          v70 = v4 + 4;
          while ( v79 )
          {
            v30 = (_DWORD)v29 - (_DWORD)v4;
            v31 = v60;
            if ( v60 > v65 - ((_DWORD)v29 - (_DWORD)v4) )
            {
              v32 = EfspResizeWorkBuffer(v4, v30, v60, &v67, &v65);
              LastError = v32;
              if ( v32 )
              {
                fnEfsLogTrace1(v33, (unsigned int)EFS_API_ERROR, v32, 11, 47);
                goto LABEL_39;
              }
              v4 = (char *)v67;
              v29 = (char *)v67 + v30;
              v70 = v29;
              v31 = v60;
            }
            v12 = EfspReceivePipeData(v29, v31, a2, &v59);
            LastError = v12;
            if ( v12 )
            {
              lpMaximumComponentLength = 69;
              goto LABEL_21;
            }
            v34 = v59;
            if ( v59 >= v60 )
            {
              if ( v59 < 4 )
              {
                fnEfsLogTrace2(v13, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 4, v59, 11, 90);
                LastError = 13;
                v5 = v56;
                goto LABEL_6;
              }
              v60 = *(_DWORD *)&v29[v59 - 4];
            }
            else
            {
              v79 = 0;
              v60 = 0;
            }
            v35 = EfspCheckSignature(v29);
            if ( v35 == 2 )
            {
              v80 = (v29[8] & 1) == 0;
              v37 = *((_WORD *)v29 + 10);
              LOWORD(v73) = v37;
              v38 = v29 + 24;
              *((_QWORD *)&v73 + 1) = v38;
              v5 = v56;
              if ( Handle && !v56 )
              {
                NtClose(Handle);
                v38 = (char *)*((_QWORD *)&v73 + 1);
                v37 = v73;
                v5 = 0;
              }
              Handle = 0;
              if ( v37 == 14
                && *(_QWORD *)v38 == 0x440024003A003ALL
                && *((_DWORD *)v38 + 2) == 5505089
                && *((_WORD *)v38 + 6) == 65 )
              {
                Handle = *v71;
                v56 = 1;
              }
              else if ( v57 )
              {
                if ( !(_BYTE)v64 )
                {
                  if ( (*(_DWORD *)(a1 + 24) & 0x4000) != 0 && !v58 )
                  {
                    LastError = EfspEnablePrivilege(v64);
                    if ( LastError )
                    {
                      v5 = v56;
                      goto LABEL_6;
                    }
                    v58 = 1;
                    v39 = ShareAccess;
                    if ( (*(_DWORD *)(a1 + 28) & 0x10000) != 0 )
                      v39 = 4;
                    ShareAccess = v39;
                    v69 = v39;
                    v37 = v73;
                  }
                  WORD1(v73) = v37;
                  v56 = 0;
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.RootDirectory = *v71;
                  ObjectAttributes.Attributes = 0;
                  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v73;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  v40 = NtCreateFile(
                          &Handle,
                          *(_DWORD *)(a1 + 28),
                          &ObjectAttributes,
                          &IoStatusBlock,
                          0,
                          *(_DWORD *)(a1 + 16),
                          ShareAccess,
                          *(_DWORD *)(a1 + 20),
                          *(_DWORD *)(a1 + 24),
                          0,
                          0);
                  v28 = v40;
                  v61 = v40;
                  if ( v40 < 0 )
                  {
                    fnEfsLogTrace1(v41, (unsigned int)EFS_API_ERROR, v40, 11, 212);
                    LastError = RtlNtStatusToDosError(v28);
                    v5 = 0;
                    goto LABEL_6;
                  }
                  if ( !v66 )
                  {
                    v43 = EfspSendSkFsctl(
                            4 - (v80 != 0),
                            v80 != 0 ? 8388611 : 4,
                            v42,
                            Handle,
                            lpMaximumComponentLengtha);
                    v28 = v43;
                    v61 = v43;
                    if ( v43 < 0 )
                    {
                      fnEfsLogTrace1(v44, (unsigned int)EFS_API_ERROR, v43, 11, 239);
                      LastError = RtlNtStatusToDosError(v28);
                      v5 = 0;
                      goto LABEL_6;
                    }
                    if ( !v80 && (*(_BYTE *)(a1 + 28) & 2) == 0 )
                    {
                      NtClose(Handle);
                      v45 = NtCreateFile(
                              &Handle,
                              *(_DWORD *)(a1 + 28) | 2,
                              &ObjectAttributes,
                              &IoStatusBlock,
                              0,
                              *(_DWORD *)(a1 + 16),
                              ShareAccess,
                              1u,
                              *(_DWORD *)(a1 + 24),
                              0,
                              0);
                      v28 = v45;
                      v61 = v45;
                      if ( v45 < 0 )
                      {
                        fnEfsLogTrace1(v46, (unsigned int)EFS_API_ERROR, v45, 11, 14);
                        LastError = RtlNtStatusToDosError(v28);
                        v5 = 0;
                        goto LABEL_6;
                      }
                    }
                  }
                }
              }
              else if ( !(_BYTE)v64 )
              {
                LastError = 50;
                goto LABEL_6;
              }
              v29 = v4 + 4;
              v70 = v4 + 4;
            }
            else
            {
              if ( v35 != 3 )
              {
                LastError = 1392;
                v5 = v56;
                goto LABEL_6;
              }
              if ( v34 < 0x10 )
              {
                fnEfsLogTrace2(v36, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 4, v34, 11, 50);
                LastError = 13;
                v5 = v56;
                goto LABEL_6;
              }
              v47 = v29 + 12;
              if ( v79 )
                v48 = v34 - 16;
              else
                v48 = v34 - 12;
              if ( v80 && Handle )
              {
                v49 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900DFu, v47, v48, 0, 0);
                v28 = v49;
                v61 = v49;
                if ( v49 < 0 )
                  fnEfsLogTrace1(v50, (unsigned int)EFS_API_ERROR, v49, 11, 85);
              }
              else if ( Handle )
              {
                v51 = NtWriteFile(Handle, 0, 0, 0, &IoStatusBlock, v47, v48, 0, 0);
                v28 = v51;
                v61 = v51;
                if ( v51 < 0 )
                  fnEfsLogTrace1(v52, (unsigned int)EFS_API_ERROR, v51, 11, 104);
                if ( v28 == 259 )
                  __fastfail(7u);
              }
              if ( v28 < 0 )
              {
                LastError = RtlNtStatusToDosError(v28);
                v5 = v56;
                goto LABEL_6;
              }
              v29 = v4 + 4;
              v70 = v4 + 4;
              LastError = 0;
            }
          }
          goto LABEL_5;
        }
        lpMaximumComponentLength = 9;
        goto LABEL_21;
      }
      LastError = 87;
      lpMaximumComponentLength = -10;
    }
    v14 = LastError;
    goto LABEL_22;
  }
  LastError = GetLastError();
LABEL_5:
  v5 = v56;
LABEL_6:
  if ( Handle && !v5 )
    NtClose(Handle);
  if ( v4 )
    VirtualFree(v4, 0, 0x8000u);
  return LastError;
}

```

## disassembly

```asm
0x180009b2c  mov     rax, rsp
0x180009b2f  mov     [rax+10h], rdx
0x180009b33  mov     [rax+8], rcx
0x180009b37  push    rbx
0x180009b38  push    rsi
0x180009b39  push    rdi
0x180009b3a  push    r12
0x180009b3c  push    r13
0x180009b3e  push    r14
0x180009b40  push    r15
0x180009b42  sub     rsp, 120h
0x180009b49  mov     r13, rdx
0x180009b4c  mov     rbx, rcx
0x180009b4f  xor     edi, edi
0x180009b51  mov     [rsp+158h+var_E8], edi
0x180009b55  mov     r14d, edi
0x180009b58  xorps   xmm0, xmm0
0x180009b5b  movups  xmmword ptr [rax-88h], xmm0
0x180009b62  mov     [rax-0D8h], rdi
0x180009b69  xorps   xmm1, xmm1
0x180009b6c  movups  xmmword ptr [rax-98h], xmm1
0x180009b73  movups  xmmword ptr [rax-70h], xmm0
0x180009b77  movups  xmmword ptr [rax-60h], xmm0
0x180009b7b  movups  xmmword ptr [rax-50h], xmm0
0x180009b7f  mov     dl, dil
0x180009b82  mov     [rsp+158h+var_F8], dl
0x180009b86  mov     [rax-0B8h], edi
0x180009b8c  lea     esi, [rdi+1]
0x180009b8f  cmp     [rcx], esi
0x180009b91  jnz     loc_18000A677
0x180009b97  mov     r15d, [rcx+4]
0x180009b9b  mov     eax, r15d
0x180009b9e  and     al, 3
0x180009ba0  cmp     al, sil
0x180009ba3  jnz     loc_18000A677
0x180009ba9  lea     rax, [rcx+8]
0x180009bad  mov     [rsp+158h+var_A8], rax
0x180009bb5  mov     [rsp+158h+nFileSystemNameSize], edi; nFileSystemNameSize
0x180009bb9  mov     [rsp+158h+lpFileSystemNameBuffer], rdi; lpFileSystemNameBuffer
0x180009bbe  lea     rcx, [rsp+158h+FileSystemFlags]
0x180009bc6  mov     [rsp+158h+lpFileSystemFlags], rcx; lpFileSystemFlags
0x180009bcb  mov     [rsp+158h+lpMaximumComponentLength], rdi; lpMaximumComponentLength
0x180009bd0  xor     r9d, r9d; lpVolumeSerialNumber
0x180009bd3  xor     r8d, r8d; nVolumeNameSize
0x180009bd6  xor     edx, edx; lpVolumeNameBuffer
0x180009bd8  mov     rcx, [rax]; hFile
0x180009bdb  call    cs:__imp_GetVolumeInformationByHandleW
0x180009be1  test    eax, eax
0x180009be3  jnz     short loc_180009C33
0x180009be5  call    cs:__imp_GetLastError
0x180009beb  mov     ebx, eax
0x180009bed  mov     dl, [rsp+158h+var_F8]
0x180009bf1  mov     rcx, [rsp+158h+Handle]; Handle
0x180009bf9  test    rcx, rcx
0x180009bfc  jz      short loc_180009C08
0x180009bfe  test    dl, dl
0x180009c00  jnz     short loc_180009C08
0x180009c02  call    cs:__imp_NtClose
0x180009c08  test    r14, r14
0x180009c0b  jz      short loc_180009C1E
0x180009c0d  xor     edx, edx; dwSize
0x180009c0f  mov     r8d, 8000h; dwFreeType
0x180009c15  mov     rcx, r14; lpAddress
0x180009c18  call    cs:__imp_VirtualFree
0x180009c1e  mov     eax, ebx
0x180009c20  add     rsp, 120h
0x180009c27  pop     r15
0x180009c29  pop     r14
0x180009c2b  pop     r13
0x180009c2d  pop     r12
0x180009c2f  pop     rdi
0x180009c30  pop     rsi
0x180009c31  pop     rbx
0x180009c32  retn
0x180009c33  and     r15d, 8000h
0x180009c3a  mov     [rsp+158h+var_C8], r15d
0x180009c42  mov     al, dil
0x180009c45  mov     [rsp+158h+var_D0], eax
0x180009c4c  mov     [rsp+158h+var_F4], al
0x180009c50  mov     r12d, 4
0x180009c56  test    [rsp+158h+FileSystemFlags], 40000h
0x180009c61  jz      short loc_180009C6A
0x180009c63  mov     [rsp+158h+var_F7], sil
0x180009c68  jmp     short loc_180009C84
0x180009c6a  mov     [rsp+158h+var_F7], dil
0x180009c6f  test    [rbx+4], r12b
0x180009c73  movzx   eax, al
0x180009c76  cmovnz  eax, esi
0x180009c79  mov     [rsp+158h+var_D0], eax
0x180009c80  mov     [rsp+158h+var_F4], al
0x180009c84  mov     ebx, 12000h
0x180009c89  mov     [rsp+158h+var_CC], ebx
0x180009c90  mov     r9d, r12d; flProtect
0x180009c93  mov     r8d, 1000h; flAllocationType
0x180009c99  mov     edx, ebx; dwSize
0x180009c9b  xor     ecx, ecx; lpAddress
0x180009c9d  call    cs:__imp_VirtualAlloc
0x180009ca3  mov     r14, rax
0x180009ca6  mov     [rsp+158h+var_C0], rax
0x180009cae  test    rax, rax
0x180009cb1  jnz     short loc_180009CD7
0x180009cb3  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 759h
0x180009cbb  lea     r9d, [rax+0Bh]
0x180009cbf  mov     r8d, ebx
0x180009cc2  lea     rdx, EFS_ERROR_MEMORY
0x180009cc9  call    fnEfsLogTrace1
0x180009cce  lea     ebx, [r14+0Eh]
0x180009cd2  jmp     loc_180009BED
0x180009cd7  lea     r9, [rsp+158h+var_E8]; unsigned int *
0x180009cdc  mov     r8, r13; void *
0x180009cdf  mov     r15d, 46h ; 'F'
0x180009ce5  mov     edx, r15d; unsigned int
0x180009ce8  mov     rcx, r14; char *
0x180009ceb  call    ?EfspReceivePipeData@@YAKPEADKPEAXPEAK@Z; EfspReceivePipeData(char *,ulong,void *,ulong *)
0x180009cf0  mov     ebx, eax
0x180009cf2  mov     r9d, [rsp+158h+var_E8]
0x180009cf7  cmp     r9d, r15d
0x180009cfa  jz      short loc_180009D22
0x180009cfc  mov     dword ptr [rsp+158h+lpFileSystemFlags], 76Eh
0x180009d04  lea     esi, [r15-3Bh]
0x180009d08  mov     dword ptr [rsp+158h+lpMaximumComponentLength], esi
0x180009d0c  mov     r8d, r15d
0x180009d0f  lea     rdx, EFS_SECURITY_DATA_TOO_SMALL
0x180009d16  call    fnEfsLogTrace2
0x180009d1b  mov     ebx, esi
0x180009d1d  jmp     loc_180009BED
0x180009d22  test    eax, eax
0x180009d24  jz      short loc_180009D48
0x180009d26  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 774h
0x180009d2e  mov     r9d, 0Bh
0x180009d34  mov     r8d, eax
0x180009d37  lea     rdx, EFS_API_ERROR
0x180009d3e  call    fnEfsLogTrace1
0x180009d43  jmp     loc_180009BED
0x180009d48  lea     r13, [r14+4]
0x180009d4c  mov     rcx, r13; void *
0x180009d4f  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180009d54  cmp     eax, esi
0x180009d56  jnz     loc_18000A66D
0x180009d5c  lea     rcx, [r14+18h]; void *
0x180009d60  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180009d65  cmp     eax, 2
0x180009d68  jnz     loc_18000A66D
0x180009d6e  lea     rcx, [r14+36h]; void *
0x180009d72  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180009d77  cmp     eax, 3
0x180009d7a  jnz     loc_18000A66D
0x180009d80  mov     eax, 1910h
0x180009d85  cmp     ax, [r14+30h]
0x180009d8a  jnz     loc_18000A66D
0x180009d90  cmp     dword ptr [r14], 100h
0x180009d97  jnz     loc_18000A66D
0x180009d9d  mov     esi, [r14+42h]
0x180009da1  mov     [r14], esi
0x180009da4  lea     r9d, [rsi+rsi]
0x180009da8  cmp     r9d, esi
0x180009dab  jb      short loc_180009DE1
0x180009dad  lea     eax, [r9+1000h]
0x180009db4  or      r15d, 0FFFFFFFFh
0x180009db8  cmp     eax, r9d
0x180009dbb  cmovnb  r15d, eax
0x180009dbf  sbb     ebx, ebx
0x180009dc1  and     ebx, 80070216h
0x180009dc7  cmp     eax, r9d
0x180009dca  jnb     short loc_180009E03
0x180009dcc  mov     dword ptr [rsp+158h+lpFileSystemNameBuffer], 7B2h
0x180009dd4  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 1000h
0x180009ddc  mov     r8d, ebx
0x180009ddf  jmp     short loc_180009DFE
0x180009de1  mov     r15d, edi
0x180009de4  mov     ebx, 80070216h
0x180009de9  mov     dword ptr [rsp+158h+lpFileSystemNameBuffer], 7A9h
0x180009df1  mov     dword ptr [rsp+158h+lpMaximumComponentLength], esi
0x180009df5  mov     r9d, esi
0x180009df8  mov     r8d, 80070216h
0x180009dfe  call    fnEfsLogTrace3
0x180009e03  test    ebx, ebx
0x180009e05  js      loc_18000A663
0x180009e0b  cmp     esi, r12d
0x180009e0e  jb      loc_18000A663
0x180009e14  cmp     r15d, 11FFCh
0x180009e1b  jbe     short loc_180009E7C
0x180009e1d  lea     rax, [rsp+158h+var_CC]
0x180009e25  mov     [rsp+158h+lpMaximumComponentLength], rax; unsigned int *
0x180009e2a  lea     r9, [rsp+158h+var_C0]; void **
0x180009e32  mov     r8d, r15d; unsigned int
0x180009e35  mov     edx, r12d; Size
0x180009e38  mov     rcx, r14; Src
0x180009e3b  call    ?EfspResizeWorkBuffer@@YAKPEAXKKPEAPEAXPEAK@Z; EfspResizeWorkBuffer(void *,ulong,ulong,void * *,ulong *)
0x180009e40  mov     ebx, eax
0x180009e42  test    eax, eax
0x180009e44  jz      short loc_180009E70
0x180009e46  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7C6h
0x180009e4e  mov     r9d, 0Bh
0x180009e54  mov     r8d, eax
0x180009e57  lea     rdx, EFS_API_ERROR
0x180009e5e  call    fnEfsLogTrace1
0x180009e63  mov     r14, [rsp+158h+var_C0]
0x180009e6b  jmp     loc_180009BED
0x180009e70  mov     r14, [rsp+158h+var_C0]
0x180009e78  lea     r13, [r14+4]
0x180009e7c  lea     r9, [rsp+158h+var_E8]; unsigned int *
0x180009e81  mov     r8, [rsp+158h+arg_8]; void *
0x180009e89  mov     edx, esi; unsigned int
0x180009e8b  mov     rcx, r13; char *
0x180009e8e  call    ?EfspReceivePipeData@@YAKPEADKPEAXPEAK@Z; EfspReceivePipeData(char *,ulong,void *,ulong *)
0x180009e93  mov     ebx, eax
0x180009e95  test    eax, eax
0x180009e97  jz      short loc_180009EA6
0x180009e99  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7D2h
0x180009ea1  jmp     loc_180009D2E
0x180009ea6  mov     ebx, [rsp+158h+var_E8]
0x180009eaa  cmp     esi, ebx
0x180009eac  jbe     short loc_180009EBC
0x180009eae  mov     [rsp+158h+arg_10], dil
0x180009eb6  mov     [rsp+158h+var_E4], edi
0x180009eba  jmp     short loc_180009ED7
0x180009ebc  mov     [rsp+158h+arg_10], 1
0x180009ec4  jz      short loc_180009ECB
0x180009ec6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009ecb  mov     rsi, rbx
0x180009ece  mov     eax, [rbx+r13-4]
0x180009ed3  mov     [rsp+158h+var_E4], eax
0x180009ed7  add     r13, 0FFFFFFFFFFFFFFFCh
0x180009edb  mov     [rsp+158h+arg_18], dil
0x180009ee3  cmp     esi, 20h ; ' '
0x180009ee6  jb      short loc_180009F23
0x180009ee8  mov     ecx, [r13+8]
0x180009eec  lea     eax, [rcx-1]
0x180009eef  cmp     eax, 2
0x180009ef2  ja      short loc_180009F08
0x180009ef4  lea     r8, [rsp+158h+arg_18]
0x180009efc  mov     edx, esi
0x180009efe  mov     rcx, r13
0x180009f01  call    EfslValidateEfsStream
0x180009f06  jmp     short loc_180009F1F
0x180009f08  cmp     ecx, r12d
0x180009f0b  jnz     short loc_180009F23
0x180009f0d  lea     r8, [rsp+158h+arg_18]; unsigned __int8 *
0x180009f15  mov     edx, esi; unsigned int
0x180009f17  mov     rcx, r13; struct _EFS_DATA_STREAM_HEADER *
0x180009f1a  call    ?EfsxValidateEfsStream@@YAKPEAU_EFS_DATA_STREAM_HEADER@@KPEAE@Z; EfsxValidateEfsStream(_EFS_DATA_STREAM_HEADER *,ulong,uchar *)
0x180009f1f  mov     ebx, eax
0x180009f21  jmp     short loc_180009F28
0x180009f23  mov     ebx, 0Dh
0x180009f28  test    ebx, ebx
0x180009f2a  jnz     short loc_180009F55
0x180009f2c  cmp     [rsp+158h+arg_18], dil
0x180009f34  jnz     short loc_180009F51
0x180009f36  mov     ebx, 57h ; 'W'
0x180009f3b  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7F6h
0x180009f43  mov     r9d, 0Bh
0x180009f49  mov     r8d, ebx
0x180009f4c  jmp     loc_180009D37
0x180009f51  test    ebx, ebx
0x180009f53  jz      short loc_180009F5F
0x180009f55  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7FDh
0x180009f5d  jmp     short loc_180009F43
0x180009f5f  mov     r12, [rsp+158h+var_A8]
0x180009f67  mov     [rsp+158h+var_78], r12
0x180009f6f  mov     rdx, r13; struct _EFS_DATA_STREAM_HEADER *
0x180009f72  mov     rcx, [r12]; FileHandle
0x180009f76  call    ?EfspOverwriteEfsAttr@@YAKPEAXPEAU_EFS_DATA_STREAM_HEADER@@@Z; EfspOverwriteEfsAttr(void *,_EFS_DATA_STREAM_HEADER *)
0x180009f7b  mov     ebx, eax
0x180009f7d  test    eax, eax
0x180009f7f  jz      short loc_180009F8E
0x180009f81  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 809h
0x180009f89  jmp     loc_180009D2E
0x180009f8e  mov     r15d, edi
0x180009f91  mov     [rsp+158h+var_E0], edi
0x180009f95  mov     [rsp+158h+var_F6], dil
0x180009f9a  mov     al, 1
0x180009f9c  mov     [rsp+158h+arg_18], al
0x180009fa3  mov     [rsp+158h+var_F5], al
0x180009fa7  mov     ecx, edi
0x180009fa9  mov     [rsp+158h+ShareAccess], ecx
0x180009fad  mov     [rsp+158h+var_B4], ecx
0x180009fb4  mov     eax, [rsp+158h+var_C8]
0x180009fbb  mov     [rsp+158h+var_A0], eax
0x180009fc2  lea     r13, [r14+4]
0x180009fc6  mov     [rsp+158h+var_B0], r13
0x180009fce  mov     esi, 0Bh
0x180009fd3  cmp     [rsp+158h+arg_10], dil
0x180009fdb  jz      loc_180009BED
0x180009fe1  mov     r12d, r13d
0x180009fe4  sub     r12d, r14d
0x180009fe7  mov     eax, [rsp+158h+var_CC]
0x180009fee  sub     eax, r12d
0x180009ff1  mov     ecx, [rsp+158h+var_E4]
0x180009ff5  cmp     ecx, eax
0x180009ff7  jbe     short loc_18000A04C
0x180009ff9  lea     rax, [rsp+158h+var_CC]
0x18000a001  mov     [rsp+158h+lpMaximumComponentLength], rax; unsigned int *
0x18000a006  lea     r9, [rsp+158h+var_C0]; void **
0x18000a00e  mov     r8d, ecx; unsigned int
0x18000a011  mov     edx, r12d; Size
0x18000a014  mov     rcx, r14; Src
0x18000a017  call    ?EfspResizeWorkBuffer@@YAKPEAXKKPEAPEAXPEAK@Z; EfspResizeWorkBuffer(void *,ulong,ulong,void * *,ulong *)
0x18000a01c  mov     ebx, eax
0x18000a01e  test    eax, eax
  ... truncated ...
```
