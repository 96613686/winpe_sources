# EfsWriteFileRaw

- ea: `0x180065c90`
- end: `0x18006681f`
- name: `EfsWriteFileRaw`
- size: `2959`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010be0`

## callees

- `0x1800264e0`
- `0x180063698`
- `0x18006389c`
- `0x180063a0c`
- `0x180063cf8`
- `0x180063d54`
- `0x180063f74`
- `0x18006441c`
- `0x180064620`
- `0x18006476c`
- `0x180065c90`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d4e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180065d44`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180065d44`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065e04`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065e04`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065d81`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065d81`
- `ntdll!NtClose` at `0x180065d6b`
- `ntdll!NtClose` at `0x18006627c`
- `ntdll!NtClose` at `0x180066515`
- `ntdll!NtClose` at `0x180065d6b`
- `ntdll!NtClose` at `0x18006627c`
- `ntdll!NtClose` at `0x180066515`
- `ntdll!NtWriteFile` at `0x1800666e8`
- `ntdll!NtWriteFile` at `0x1800666e8`
- `ntdll!NtFsControlFile` at `0x18006667a`
- `ntdll!NtFsControlFile` at `0x18006667a`
- `ntdll!NtCreateFile` at `0x18006642b`
- `ntdll!NtCreateFile` at `0x180066568`
- `ntdll!NtCreateFile` at `0x18006642b`
- `ntdll!NtCreateFile` at `0x180066568`
- `ntdll!RtlNtStatusToDosError` at `0x180066460`
- `ntdll!RtlNtStatusToDosError` at `0x1800664df`
- `ntdll!RtlNtStatusToDosError` at `0x18006659d`
- `ntdll!RtlNtStatusToDosError` at `0x180066732`
- `ntdll!RtlNtStatusToDosError` at `0x180066460`
- `ntdll!RtlNtStatusToDosError` at `0x1800664df`
- `ntdll!RtlNtStatusToDosError` at `0x18006659d`
- `ntdll!RtlNtStatusToDosError` at `0x180066732`

## pseudocode

```c
__int64 __fastcall EfsWriteFileRaw(__int64 a1, void *a2)
{
  char *v4; // r14
  char v5; // dl
  int v6; // r15d
  BOOL v7; // ecx
  ULONG LastError; // ebx
  bool v10; // cl
  char *v11; // rax
  unsigned int v12; // eax
  int v13; // ecx
  char *v14; // r13
  int v15; // ecx
  unsigned int v16; // r15d
  unsigned int v17; // r9d
  unsigned int v18; // eax
  unsigned int v19; // r12d
  signed int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rbx
  char v24; // r12
  NTSTATUS v25; // r15d
  char *v26; // r13
  unsigned int v27; // r12d
  unsigned int v28; // ecx
  unsigned int v29; // eax
  int v30; // ecx
  unsigned int v31; // r12d
  unsigned int v32; // eax
  int v33; // ecx
  __int16 v34; // dx
  char *v35; // r13
  __int64 v36; // rcx
  ULONG v37; // eax
  NTSTATUS v38; // eax
  unsigned int v39; // r8d
  int v40; // eax
  NTSTATUS v41; // eax
  void *v42; // r13
  ULONG v43; // r12d
  NTSTATUS v44; // eax
  NTSTATUS v45; // eax
  char lpMaximumComponentLength; // [rsp+20h] [rbp-138h]
  unsigned int lpMaximumComponentLengtha; // [rsp+20h] [rbp-138h]
  char v48; // [rsp+60h] [rbp-F8h]
  char v49; // [rsp+61h] [rbp-F7h] BYREF
  char v50; // [rsp+62h] [rbp-F6h]
  char v51; // [rsp+63h] [rbp-F5h]
  char v52; // [rsp+64h] [rbp-F4h]
  bool v53; // [rsp+65h] [rbp-F3h]
  int v54; // [rsp+68h] [rbp-F0h]
  char v55; // [rsp+6Ch] [rbp-ECh]
  unsigned int v56; // [rsp+70h] [rbp-E8h] BYREF
  unsigned int v57; // [rsp+74h] [rbp-E4h]
  NTSTATUS v58; // [rsp+78h] [rbp-E0h]
  ULONG ShareAccess; // [rsp+7Ch] [rbp-DCh]
  HANDLE Handle; // [rsp+80h] [rbp-D8h] BYREF
  BOOL v61; // [rsp+88h] [rbp-D0h]
  unsigned int v62; // [rsp+8Ch] [rbp-CCh] BYREF
  int v63; // [rsp+90h] [rbp-C8h]
  void *v64; // [rsp+98h] [rbp-C0h] BYREF
  DWORD FileSystemFlags; // [rsp+A0h] [rbp-B8h] BYREF
  ULONG v66; // [rsp+A4h] [rbp-B4h]
  char *v67; // [rsp+A8h] [rbp-B0h]
  HANDLE *v68; // [rsp+B0h] [rbp-A8h]
  int v69; // [rsp+B8h] [rbp-A0h]
  __int128 v70; // [rsp+C0h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-88h] BYREF
  HANDLE *v72; // [rsp+E0h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-70h] BYREF
  char v76; // [rsp+170h] [rbp+18h]
  bool v77; // [rsp+178h] [rbp+20h]

  v56 = 0;
  v4 = 0;
  IoStatusBlock = 0;
  Handle = 0;
  v70 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v5 = 0;
  v48 = 0;
  v49 = 0;
  FileSystemFlags = 0;
  if ( *(_DWORD *)a1 != 1 || (v6 = *(_DWORD *)(a1 + 4), (v6 & 3) != 1) )
  {
    LastError = 5;
    goto LABEL_6;
  }
  v68 = (HANDLE *)(a1 + 8);
  if ( GetVolumeInformationByHandleW(*(HANDLE *)(a1 + 8), 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
  {
    v63 = v6 & 0x8000;
    LOBYTE(v7) = 0;
    v61 = v7;
    v53 = 0;
    if ( (FileSystemFlags & 0x40000) != 0 )
    {
      v50 = 1;
    }
    else
    {
      v50 = 0;
      v10 = (*(_BYTE *)(a1 + 4) & 4) != 0;
      v61 = v10;
      v53 = v10;
    }
    v62 = 73728;
    v11 = (char *)VirtualAlloc(0, 0x12000u, 0x1000u, 4u);
    v4 = v11;
    v64 = v11;
    if ( v11 )
    {
      v12 = EfspReceivePipeData(v11, 0x46u, a2, &v56);
      LastError = v12;
      if ( v56 == 70 )
      {
        if ( v12 )
        {
          lpMaximumComponentLength = 116;
        }
        else
        {
          v14 = v4 + 4;
          if ( EfspCheckSignature(v4 + 4) != 1
            || EfspCheckSignature(v4 + 24) != 2
            || EfspCheckSignature(v4 + 54) != 3
            || *((_WORD *)v4 + 24) != 6416
            || *(_DWORD *)v4 != 256 )
          {
            LastError = 11;
            goto LABEL_5;
          }
          v16 = *(_DWORD *)(v4 + 66);
          *(_DWORD *)v4 = v16;
          v17 = 2 * v16;
          if ( 2 * v16 < v16 )
          {
            v19 = 0;
            v20 = -2147024362;
            fnEfsLogTrace3(v15, (unsigned int)EFS_API_ERROR_2, -2147024362, v16, v16, 11, 169);
          }
          else
          {
            v18 = v17 + 4096;
            v19 = -1;
            if ( v17 + 4096 >= v17 )
              v19 = v17 + 4096;
            v20 = v18 < v17 ? 0x80070216 : 0;
            if ( v18 < v17 )
              fnEfsLogTrace3(v15, (unsigned int)EFS_API_ERROR_2, v20, v17, 0, 11, 178);
          }
          if ( v20 < 0 || v16 < 4 )
          {
            LastError = 13;
            goto LABEL_5;
          }
          if ( v19 > 0x11FFC )
          {
            v21 = EfspResizeWorkBuffer(v4, 4u, v19, &v64, &v62);
            LastError = v21;
            if ( v21 )
            {
              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 11, 198);
LABEL_38:
              v4 = (char *)v64;
              goto LABEL_5;
            }
            v4 = (char *)v64;
            v14 = (char *)v64 + 4;
          }
          v12 = EfspReceivePipeData(v14, v16, a2, &v56);
          LastError = v12;
          if ( v12 )
          {
            lpMaximumComponentLength = -46;
          }
          else
          {
            v23 = v56;
            if ( v16 <= v56 )
            {
              v24 = 1;
              v76 = 1;
              if ( v16 != v56 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v22);
              v16 = v23;
              v57 = *(_DWORD *)&v14[v23 - 4];
            }
            else
            {
              v24 = 0;
              v76 = 0;
              v57 = 0;
            }
            v12 = EfsValidateEfsStream((const struct _EFS_DATA_STREAM_HEADER *)(v14 - 4), v16, &v49);
            LastError = v12;
            if ( v12 )
            {
              lpMaximumComponentLength = -3;
            }
            else
            {
              if ( !v49 )
              {
                LastError = 87;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 11, 246);
                goto LABEL_5;
              }
              v72 = v68;
              v12 = EfspOverwriteEfsAttr(*v68, (struct _EFS_DATA_STREAM_HEADER *)(v14 - 4));
              LastError = v12;
              if ( !v12 )
              {
                v25 = 0;
                v58 = 0;
                v51 = 0;
                v77 = 1;
                v52 = 1;
                ShareAccess = 0;
                v66 = 0;
                v69 = v63;
                v26 = v4 + 4;
                v67 = v4 + 4;
                while ( v24 )
                {
                  v27 = (_DWORD)v26 - (_DWORD)v4;
                  v28 = v57;
                  if ( v57 > v62 - ((_DWORD)v26 - (_DWORD)v4) )
                  {
                    v29 = EfspResizeWorkBuffer(v4, v27, v57, &v64, &v62);
                    LastError = v29;
                    if ( v29 )
                    {
                      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v29, 11, 47);
                      goto LABEL_38;
                    }
                    v4 = (char *)v64;
                    v26 = (char *)v64 + v27;
                    v67 = v26;
                    v28 = v57;
                  }
                  v12 = EfspReceivePipeData(v26, v28, a2, &v56);
                  LastError = v12;
                  if ( v12 )
                  {
                    lpMaximumComponentLength = 69;
                    goto LABEL_21;
                  }
                  v31 = v56;
                  if ( v56 >= v57 )
                  {
                    if ( v56 < 4 )
                    {
                      fnEfsLogTrace2(v30, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 4, v56, 11, 90);
                      LastError = 13;
                      v54 = 13;
                      v5 = v48;
                      goto LABEL_6;
                    }
                    v57 = *(_DWORD *)&v26[v56 - 4];
                  }
                  else
                  {
                    v76 = 0;
                    v55 = 0;
                    v57 = 0;
                  }
                  v32 = EfspCheckSignature(v26);
                  if ( v32 == 2 )
                  {
                    v77 = (v26[8] & 1) == 0;
                    v52 = v77;
                    v34 = *((_WORD *)v26 + 10);
                    LOWORD(v70) = v34;
                    v35 = v26 + 24;
                    *((_QWORD *)&v70 + 1) = v35;
                    if ( Handle && !v48 )
                    {
                      NtClose(Handle);
                      v35 = (char *)*((_QWORD *)&v70 + 1);
                      v34 = v70;
                    }
                    Handle = 0;
                    if ( v34 != 14 )
                      goto LABEL_77;
                    v36 = *(_QWORD *)v35 - 0x440024003A003ALL;
                    if ( *(_QWORD *)v35 == 0x440024003A003ALL )
                    {
                      v36 = *((unsigned int *)v35 + 2) - 5505089LL;
                      if ( *((_DWORD *)v35 + 2) == 5505089 )
                        v36 = *((unsigned __int16 *)v35 + 6) - 65LL;
                    }
                    if ( v36 )
                    {
LABEL_77:
                      if ( v50 )
                      {
                        if ( !v61 )
                        {
                          if ( (*(_DWORD *)(a1 + 24) & 0x4000) != 0 && !v51 )
                          {
                            LastError = EfspEnablePrivilege(18);
                            v54 = LastError;
                            if ( LastError )
                            {
                              v5 = v48;
                              goto LABEL_6;
                            }
                            v51 = 1;
                            v37 = ShareAccess;
                            if ( (*(_DWORD *)(a1 + 28) & 0x10000) != 0 )
                              v37 = 4;
                            ShareAccess = v37;
                            v66 = v37;
                            v34 = v70;
                          }
                          WORD1(v70) = v34;
                          v48 = 0;
                          ObjectAttributes.Length = 48;
                          ObjectAttributes.RootDirectory = *v68;
                          ObjectAttributes.Attributes = 0;
                          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v70;
                          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                          v38 = NtCreateFile(
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
                          v25 = v38;
                          v58 = v38;
                          if ( v38 < 0 )
                          {
                            fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v38, 11, 212);
                            LastError = RtlNtStatusToDosError(v25);
                            v54 = LastError;
                            v5 = 0;
                            goto LABEL_6;
                          }
                          if ( !v63 )
                          {
                            v40 = EfspSendSkFsctl(4 - v77, v77 ? 8388611 : 4, v39, Handle, lpMaximumComponentLengtha);
                            v25 = v40;
                            v58 = v40;
                            if ( v40 < 0 )
                            {
                              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v40, 11, 239);
                              LastError = RtlNtStatusToDosError(v25);
                              v54 = LastError;
                              v5 = 0;
                              goto LABEL_6;
                            }
                            if ( !v77 && (*(_BYTE *)(a1 + 28) & 2) == 0 )
                            {
                              NtClose(Handle);
                              v41 = NtCreateFile(
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
                              v25 = v41;
                              v58 = v41;
                              if ( v41 < 0 )
                              {
                                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v41, 11, 14);
                                LastError = RtlNtStatusToDosError(v25);
                                v54 = LastError;
                                v5 = 0;
                                goto LABEL_6;
                              }
                            }
                          }
                        }
                      }
                      else if ( !v61 )
                      {
                        LastError = 50;
                        v54 = 50;
                        v5 = v48;
                        goto LABEL_6;
                      }
                    }
                    else
                    {
                      Handle = *v68;
                      v48 = 1;
                    }
                    v26 = v4 + 4;
                    v67 = v4 + 4;
                    v24 = v76;
                  }
                  else
                  {
                    if ( v32 != 3 )
                    {
                      LastError = 1392;
                      v54 = 1392;
                      v5 = v48;
                      goto LABEL_6;
                    }
                    if ( v31 < 0x10 )
                    {
                      fnEfsLogTrace2(v33, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 4, v31, 11, 50);
                      LastError = 13;
                      v54 = 13;
                      v5 = v48;
                      goto LABEL_6;
                    }
                    v42 = v26 + 12;
                    if ( v76 )
                      v43 = v31 - 16;
                    else
                      v43 = v31 - 12;
                    if ( v77 && Handle )
                    {
                      v44 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900DFu, v42, v43, 0, 0);
                      v25 = v44;
                      v58 = v44;
                      if ( v44 < 0 )
                        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v44, 11, 85);
                    }
                    else if ( Handle )
                    {
                      v45 = NtWriteFile(Handle, 0, 0, 0, &IoStatusBlock, v42, v43, 0, 0);
                      v25 = v45;
                      v58 = v45;
                      if ( v45 < 0 )
                        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v45, 11, 104);
                      if ( v25 == 259 )
                        __fastfail(7u);
                    }
                    if ( v25 < 0 )
                    {
                      LastError = RtlNtStatusToDosError(v25);
                      v54 = LastError;
                      v5 = v48;
                      goto LABEL_6;
                    }
                    v26 = v4 + 4;
                    v67 = v4 + 4;
                    LastError = 0;
                    v54 = 0;
                    v24 = v76;
                  }
                }
                goto LABEL_5;
              }
              lpMaximumComponentLength = 9;
            }
          }
        }
LABEL_21:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v12, 11, lpMaximumComponentLength);
      }
      else
      {
        fnEfsLogTrace2(v13, (unsigned int)EFS_SECURITY_DATA_TOO_SMALL, 70, v56, 11, 110);
        LastError = 11;
      }
    }
    else
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 73728, 11, 89);
      LastError = 14;
    }
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_5:
  v5 = v48;
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
0x180065c90  mov     rax, rsp
0x180065c93  mov     [rax+10h], rdx
0x180065c97  mov     [rax+8], rcx
0x180065c9b  push    rbx
0x180065c9c  push    rsi
0x180065c9d  push    rdi
0x180065c9e  push    r12
0x180065ca0  push    r13
0x180065ca2  push    r14
0x180065ca4  push    r15
0x180065ca6  sub     rsp, 120h
0x180065cad  mov     r12, rdx
0x180065cb0  mov     rbx, rcx
0x180065cb3  xor     edi, edi
0x180065cb5  mov     [rsp+158h+var_E8], edi
0x180065cb9  mov     r14d, edi
0x180065cbc  xorps   xmm0, xmm0
0x180065cbf  movups  xmmword ptr [rax-88h], xmm0
0x180065cc6  mov     [rax-0D8h], rdi
0x180065ccd  xorps   xmm1, xmm1
0x180065cd0  movups  xmmword ptr [rax-98h], xmm1
0x180065cd7  movups  xmmword ptr [rax-70h], xmm0
0x180065cdb  movups  xmmword ptr [rax-60h], xmm0
0x180065cdf  movups  xmmword ptr [rax-50h], xmm0
0x180065ce3  mov     dl, dil
0x180065ce6  mov     [rsp+158h+var_F8], dl
0x180065cea  mov     [rsp+158h+var_F7], dil
0x180065cef  mov     [rax-0B8h], edi
0x180065cf5  lea     esi, [rdi+1]
0x180065cf8  cmp     [rcx], esi
0x180065cfa  jnz     loc_180066815
0x180065d00  mov     r15d, [rcx+4]
0x180065d04  mov     eax, r15d
0x180065d07  and     al, 3
0x180065d09  cmp     al, sil
0x180065d0c  jnz     loc_180066815
0x180065d12  lea     rax, [rcx+8]
0x180065d16  mov     [rsp+158h+var_A8], rax
0x180065d1e  mov     [rsp+158h+nFileSystemNameSize], edi; nFileSystemNameSize
0x180065d22  mov     [rsp+158h+lpFileSystemNameBuffer], rdi; lpFileSystemNameBuffer
0x180065d27  lea     rcx, [rsp+158h+FileSystemFlags]
0x180065d2f  mov     [rsp+158h+lpFileSystemFlags], rcx; lpFileSystemFlags
0x180065d34  mov     [rsp+158h+lpMaximumComponentLength], rdi; lpMaximumComponentLength
0x180065d39  xor     r9d, r9d; lpVolumeSerialNumber
0x180065d3c  xor     r8d, r8d; nVolumeNameSize
0x180065d3f  xor     edx, edx; lpVolumeNameBuffer
0x180065d41  mov     rcx, [rax]; hFile
0x180065d44  call    cs:__imp_GetVolumeInformationByHandleW
0x180065d4a  test    eax, eax
0x180065d4c  jnz     short loc_180065D9C
0x180065d4e  call    cs:__imp_GetLastError
0x180065d54  mov     ebx, eax
0x180065d56  mov     dl, [rsp+158h+var_F8]
0x180065d5a  mov     rcx, [rsp+158h+Handle]; Handle
0x180065d62  test    rcx, rcx
0x180065d65  jz      short loc_180065D71
0x180065d67  test    dl, dl
0x180065d69  jnz     short loc_180065D71
0x180065d6b  call    cs:__imp_NtClose
0x180065d71  test    r14, r14
0x180065d74  jz      short loc_180065D87
0x180065d76  xor     edx, edx; dwSize
0x180065d78  mov     r8d, 8000h; dwFreeType
0x180065d7e  mov     rcx, r14; lpAddress
0x180065d81  call    cs:__imp_VirtualFree
0x180065d87  mov     eax, ebx
0x180065d89  add     rsp, 120h
0x180065d90  pop     r15
0x180065d92  pop     r14
0x180065d94  pop     r13
0x180065d96  pop     r12
0x180065d98  pop     rdi
0x180065d99  pop     rsi
0x180065d9a  pop     rbx
0x180065d9b  retn
0x180065d9c  and     r15d, 8000h
0x180065da3  mov     [rsp+158h+var_C8], r15d
0x180065dab  mov     cl, dil
0x180065dae  mov     [rsp+158h+var_D0], ecx
0x180065db5  mov     [rsp+158h+var_F3], cl
0x180065db9  mov     eax, 4
0x180065dbe  test    [rsp+158h+FileSystemFlags], 40000h
0x180065dc9  jz      short loc_180065DD2
0x180065dcb  mov     [rsp+158h+var_F6], sil
0x180065dd0  jmp     short loc_180065DEB
0x180065dd2  mov     [rsp+158h+var_F6], dil
0x180065dd7  test    [rbx+4], al
0x180065dda  movzx   ecx, cl
0x180065ddd  cmovnz  ecx, esi
0x180065de0  mov     [rsp+158h+var_D0], ecx
0x180065de7  mov     [rsp+158h+var_F3], cl
0x180065deb  mov     ebx, 12000h
0x180065df0  mov     [rsp+158h+var_CC], ebx
0x180065df7  mov     r9d, eax; flProtect
0x180065dfa  mov     r8d, 1000h; flAllocationType
0x180065e00  mov     edx, ebx; dwSize
0x180065e02  xor     ecx, ecx; lpAddress
0x180065e04  call    cs:__imp_VirtualAlloc
0x180065e0a  mov     r14, rax
0x180065e0d  mov     [rsp+158h+var_C0], rax
0x180065e15  test    rax, rax
0x180065e18  jnz     short loc_180065E45
0x180065e1a  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 759h
0x180065e22  lea     r9d, [rax+0Bh]
0x180065e26  mov     r8d, ebx
0x180065e29  lea     rdx, EFS_ERROR_MEMORY
0x180065e30  mov     rcx, cs:g_hPublisher
0x180065e37  call    fnEfsLogTrace1
0x180065e3c  lea     ebx, [r14+0Eh]
0x180065e40  jmp     loc_180065D56
0x180065e45  lea     r9, [rsp+158h+var_E8]; unsigned int *
0x180065e4a  mov     r8, r12; void *
0x180065e4d  mov     r15d, 46h ; 'F'
0x180065e53  mov     edx, r15d; unsigned int
0x180065e56  mov     rcx, r14; char *
0x180065e59  call    ?EfspReceivePipeData@@YAKPEADKPEAXPEAK@Z; EfspReceivePipeData(char *,ulong,void *,ulong *)
0x180065e5e  mov     ebx, eax
0x180065e60  mov     r9d, [rsp+158h+var_E8]
0x180065e65  cmp     r9d, r15d
0x180065e68  jz      short loc_180065E90
0x180065e6a  mov     dword ptr [rsp+158h+lpFileSystemFlags], 76Eh
0x180065e72  lea     esi, [r15-3Bh]
0x180065e76  mov     dword ptr [rsp+158h+lpMaximumComponentLength], esi
0x180065e7a  mov     r8d, r15d
0x180065e7d  lea     rdx, EFS_SECURITY_DATA_TOO_SMALL
0x180065e84  call    fnEfsLogTrace2
0x180065e89  mov     ebx, esi
0x180065e8b  jmp     loc_180065D56
0x180065e90  test    eax, eax
0x180065e92  jz      short loc_180065EBD
0x180065e94  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 774h
0x180065e9c  mov     r9d, 0Bh
0x180065ea2  mov     r8d, eax
0x180065ea5  lea     rdx, EFS_API_ERROR
0x180065eac  mov     rcx, cs:g_hPublisher
0x180065eb3  call    fnEfsLogTrace1
0x180065eb8  jmp     loc_180065D56
0x180065ebd  lea     r13, [r14+4]
0x180065ec1  mov     rcx, r13; void *
0x180065ec4  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180065ec9  cmp     eax, esi
0x180065ecb  jnz     loc_18006680B
0x180065ed1  lea     rcx, [r14+18h]; void *
0x180065ed5  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180065eda  cmp     eax, 2
0x180065edd  jnz     loc_18006680B
0x180065ee3  lea     rcx, [r14+36h]; void *
0x180065ee7  call    ?EfspCheckSignature@@YAKPEAX@Z; EfspCheckSignature(void *)
0x180065eec  cmp     eax, 3
0x180065eef  jnz     loc_18006680B
0x180065ef5  mov     eax, 1910h
0x180065efa  cmp     ax, [r14+30h]
0x180065eff  jnz     loc_18006680B
0x180065f05  cmp     dword ptr [r14], 100h
0x180065f0c  jnz     loc_18006680B
0x180065f12  mov     r15d, [r14+42h]
0x180065f16  mov     [r14], r15d
0x180065f19  lea     r9d, [r15+r15]
0x180065f1d  mov     esi, 0Bh
0x180065f22  cmp     r9d, r15d
0x180065f25  jb      short loc_180065F5F
0x180065f27  lea     eax, [r9+1000h]
0x180065f2e  or      r12d, 0FFFFFFFFh
0x180065f32  cmp     eax, r9d
0x180065f35  cmovnb  r12d, eax
0x180065f39  sbb     ebx, ebx
0x180065f3b  and     ebx, 80070216h
0x180065f41  cmp     eax, r9d
0x180065f44  jnb     short loc_180065F8D
0x180065f46  mov     dword ptr [rsp+158h+lpFileSystemNameBuffer], 7B2h
0x180065f4e  mov     dword ptr [rsp+158h+lpFileSystemFlags], esi
0x180065f52  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 1000h
0x180065f5a  mov     r8d, ebx
0x180065f5d  jmp     short loc_180065F81
0x180065f5f  mov     r12d, edi
0x180065f62  mov     ebx, 80070216h
0x180065f67  mov     dword ptr [rsp+158h+lpFileSystemNameBuffer], 7A9h
0x180065f6f  mov     dword ptr [rsp+158h+lpFileSystemFlags], esi
0x180065f73  mov     dword ptr [rsp+158h+lpMaximumComponentLength], r15d
0x180065f78  mov     r9d, r15d
0x180065f7b  mov     r8d, 80070216h
0x180065f81  lea     rdx, EFS_API_ERROR_2
0x180065f88  call    fnEfsLogTrace3
0x180065f8d  test    ebx, ebx
0x180065f8f  js      loc_180066801
0x180065f95  mov     eax, 4
0x180065f9a  cmp     r15d, eax
0x180065f9d  jb      loc_180066801
0x180065fa3  cmp     r12d, 11FFCh
0x180065faa  jbe     short loc_18006600E
0x180065fac  lea     rcx, [rsp+158h+var_CC]
0x180065fb4  mov     [rsp+158h+lpMaximumComponentLength], rcx; unsigned int *
0x180065fb9  lea     r9, [rsp+158h+var_C0]; void **
0x180065fc1  mov     r8d, r12d; unsigned int
0x180065fc4  mov     edx, eax; Size
0x180065fc6  mov     rcx, r14; lpAddress
0x180065fc9  call    ?EfspResizeWorkBuffer@@YAKPEAXKKPEAPEAXPEAK@Z; EfspResizeWorkBuffer(void *,ulong,ulong,void * *,ulong *)
0x180065fce  mov     ebx, eax
0x180065fd0  test    eax, eax
0x180065fd2  jz      short loc_180066002
0x180065fd4  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7C6h
0x180065fdc  mov     r9d, esi
0x180065fdf  mov     r8d, eax
0x180065fe2  lea     rdx, EFS_API_ERROR
0x180065fe9  mov     rcx, cs:g_hPublisher
0x180065ff0  call    fnEfsLogTrace1
0x180065ff5  mov     r14, [rsp+158h+var_C0]
0x180065ffd  jmp     loc_180065D56
0x180066002  mov     r14, [rsp+158h+var_C0]
0x18006600a  lea     r13, [r14+4]
0x18006600e  lea     r9, [rsp+158h+var_E8]; unsigned int *
0x180066013  mov     r8, [rsp+158h+arg_8]; void *
0x18006601b  mov     edx, r15d; unsigned int
0x18006601e  mov     rcx, r13; char *
0x180066021  call    ?EfspReceivePipeData@@YAKPEADKPEAXPEAK@Z; EfspReceivePipeData(char *,ulong,void *,ulong *)
0x180066026  mov     ebx, eax
0x180066028  test    eax, eax
0x18006602a  jz      short loc_18006603C
0x18006602c  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7D2h
0x180066034  mov     r9d, esi
0x180066037  jmp     loc_180065EA2
0x18006603c  mov     ebx, [rsp+158h+var_E8]
0x180066040  cmp     r15d, ebx
0x180066043  jbe     short loc_180066056
0x180066045  mov     r12b, dil
0x180066048  mov     [rsp+158h+arg_10], dil
0x180066050  mov     [rsp+158h+var_E4], edi
0x180066054  jmp     short loc_180066074
0x180066056  mov     r12b, 1
0x180066059  mov     [rsp+158h+arg_10], r12b
0x180066061  jz      short loc_180066068
0x180066063  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "GetDataLength == cbBytesRead")
0x180066068  mov     r15, rbx
0x18006606b  mov     eax, [rbx+r13-4]
0x180066070  mov     [rsp+158h+var_E4], eax
0x180066074  lea     r8, [rsp+158h+var_F7]
0x180066079  mov     edx, r15d
0x18006607c  lea     rcx, [r13-4]
0x180066080  call    EfsValidateEfsStream
0x180066085  mov     ebx, eax
0x180066087  test    eax, eax
0x180066089  jnz     short loc_1800660AC
0x18006608b  cmp     [rsp+158h+var_F7], dil
0x180066090  jnz     short loc_1800660A8
0x180066092  lea     ebx, [rax+57h]
0x180066095  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7F6h
0x18006609d  mov     r9d, esi
0x1800660a0  mov     r8d, ebx
0x1800660a3  jmp     loc_180065EA5
0x1800660a8  test    eax, eax
0x1800660aa  jz      short loc_1800660B9
0x1800660ac  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 7FDh
0x1800660b4  jmp     loc_180066034
0x1800660b9  mov     rax, [rsp+158h+var_A8]
0x1800660c1  mov     [rsp+158h+var_78], rax
0x1800660c9  lea     rdx, [r13-4]; struct _EFS_DATA_STREAM_HEADER *
0x1800660cd  mov     rcx, [rax]; FileHandle
0x1800660d0  call    ?EfspOverwriteEfsAttr@@YAKPEAXPEAU_EFS_DATA_STREAM_HEADER@@@Z; EfspOverwriteEfsAttr(void *,_EFS_DATA_STREAM_HEADER *)
0x1800660d5  mov     ebx, eax
0x1800660d7  test    eax, eax
0x1800660d9  jz      short loc_1800660E8
0x1800660db  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 809h
0x1800660e3  jmp     loc_180066034
0x1800660e8  mov     r15d, edi
0x1800660eb  mov     [rsp+158h+var_E0], edi
0x1800660ef  mov     [rsp+158h+var_F5], dil
0x1800660f4  mov     al, 1
0x1800660f6  mov     [rsp+158h+arg_18], al
0x1800660fd  mov     [rsp+158h+var_F4], al
0x180066101  mov     ecx, edi
0x180066103  mov     [rsp+158h+ShareAccess], ecx
0x180066107  mov     [rsp+158h+var_B4], ecx
0x18006610e  mov     eax, [rsp+158h+var_C8]
0x180066115  mov     [rsp+158h+var_A0], eax
0x18006611c  lea     r13, [r14+4]
0x180066120  mov     [rsp+158h+var_B0], r13
0x180066128  test    r12b, r12b
0x18006612b  jz      loc_180065D56
0x180066131  mov     r12d, r13d
0x180066134  sub     r12d, r14d
0x180066137  mov     eax, [rsp+158h+var_CC]
0x18006613e  sub     eax, r12d
0x180066141  mov     ecx, [rsp+158h+var_E4]
0x180066145  cmp     ecx, eax
0x180066147  jbe     short loc_180066199
0x180066149  lea     rax, [rsp+158h+var_CC]
0x180066151  mov     [rsp+158h+lpMaximumComponentLength], rax; unsigned int *
0x180066156  lea     r9, [rsp+158h+var_C0]; void **
0x18006615e  mov     r8d, ecx; unsigned int
0x180066161  mov     edx, r12d; Size
0x180066164  mov     rcx, r14; lpAddress
0x180066167  call    ?EfspResizeWorkBuffer@@YAKPEAXKKPEAPEAXPEAK@Z; EfspResizeWorkBuffer(void *,ulong,ulong,void * *,ulong *)
0x18006616c  mov     ebx, eax
0x18006616e  test    eax, eax
0x180066170  jz      short loc_18006617F
0x180066172  mov     dword ptr [rsp+158h+lpMaximumComponentLength], 82Fh
0x18006617a  jmp     loc_180065FDC
0x18006617f  mov     r13d, r12d
0x180066182  mov     r14, [rsp+158h+var_C0]
0x18006618a  add     r13, r14
  ... truncated ...
```
