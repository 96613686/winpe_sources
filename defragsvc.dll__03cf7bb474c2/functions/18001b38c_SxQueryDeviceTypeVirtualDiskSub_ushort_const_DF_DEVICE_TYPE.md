# SxQueryDeviceTypeVirtualDiskSub(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x18001b38c`
- end: `0x18001b588`
- name: `?SxQueryDeviceTypeVirtualDiskSub@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001adac`
- `0x18003e618`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001b38c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b425`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b544`
- `VirtDisk!GetStorageDependencyInformation` at `0x18001b49b`
- `VirtDisk!GetStorageDependencyInformation` at `0x18001b49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b45b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b45b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b533`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceTypeVirtualDiskSub(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *a2)
{
  __int16 v4; // ax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  HANDLE FileW; // r14
  struct _STORAGE_DEPENDENCY_INFO *v10; // rdi
  ULONG v11; // ebx
  DWORD StorageDependencyInformation; // eax
  unsigned int v13; // ebx
  int v14; // r9d
  int v15; // r8d
  ULONG v16; // edx
  __int64 v17; // rcx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-19h] BYREF
  __int16 v20; // [rsp+44h] [rbp-15h]
  __int16 v21; // [rsp+46h] [rbp-13h]
  ULONG SizeUsed; // [rsp+C0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "SxQueryDeviceTypeVirtualDiskSub",
    176,
    1);
  SizeUsed = 0;
  v4 = 188;
  if ( lpFileName && (v20 = 188, v4 = 189, a2) )
  {
    v20 = 189;
    LastFailureAsHRESULT = 0;
    *(_DWORD *)a2 = 8;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5, v7, v8);
      v21 = 203;
      v13 = LastFailureAsHRESULT;
    }
    else
    {
      v10 = 0;
      LastFailureAsHRESULT = 0;
      v20 = 203;
      v11 = 100;
LABEL_5:
      StorageDependencyInformation = 122;
      while ( StorageDependencyInformation == 122 )
      {
        if ( v10 )
          CoTaskMemFree(v10);
        v10 = (struct _STORAGE_DEPENDENCY_INFO *)CoTaskMemAlloc(v11);
        if ( !v10 )
        {
          v13 = -2147024882;
          v21 = 222;
          LastFailureAsHRESULT = -2147024882;
          goto LABEL_29;
        }
        v20 = 222;
        LastFailureAsHRESULT = 0;
        *(_QWORD *)&v10->Version = 1;
        StorageDependencyInformation = GetStorageDependencyInformation(
                                         FileW,
                                         GET_STORAGE_DEPENDENCY_FLAG_DISK_HANDLE|GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                         v11,
                                         v10,
                                         &SizeUsed);
        if ( StorageDependencyInformation == 234 )
        {
          if ( SizeUsed > 0x48 )
          {
            v11 = 28 * v10->NumberEntries + 72;
            goto LABEL_5;
          }
        }
        else
        {
          if ( StorageDependencyInformation != 122 )
            break;
          v11 *= 2;
        }
      }
      if ( !StorageDependencyInformation )
      {
        v14 = 0;
        v15 = 0;
        v16 = 0;
        if ( v10->NumberEntries )
        {
          do
          {
            v17 = v16;
            if ( (v10->Version1Entries[v17].DependencyTypeFlags & 0x100) != 0 )
            {
              v14 = 1;
            }
            else if ( (v10->Version1Entries[v17].DependencyTypeFlags & 2) == 0 )
            {
              v15 = 1;
            }
            ++v16;
          }
          while ( v16 < v10->NumberEntries );
          if ( v14 )
          {
            *(_DWORD *)a2 = 9;
          }
          else if ( v15 )
          {
            *(_DWORD *)a2 = 10;
          }
        }
      }
      v13 = 0;
      LastFailureAsHRESULT = 0;
      v20 = 278;
      if ( v10 )
      {
        CoTaskMemFree(v10);
        v13 = LastFailureAsHRESULT;
      }
LABEL_29:
      if ( FileW )
        CloseHandle(FileW);
    }
  }
  else
  {
    v13 = -2147024809;
    v21 = v4;
    LastFailureAsHRESULT = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v13;
}

```

## disassembly

```asm
0x18001b38c  push    rbp
0x18001b38e  push    rbx
0x18001b38f  push    rsi
0x18001b390  push    rdi
0x18001b391  push    r13
0x18001b393  push    r14
0x18001b395  lea     rbp, [rsp-2Fh]
0x18001b39a  sub     rsp, 88h
0x18001b3a1  mov     rsi, rdx
0x18001b3a4  mov     rbx, rcx
0x18001b3a7  mov     r13d, 1
0x18001b3ad  lea     rdx, aSxquerydevicet_0; "SxQueryDeviceTypeVirtualDiskSub"
0x18001b3b4  mov     r9d, r13d; unsigned __int16
0x18001b3b7  lea     rcx, [rbp+57h+var_70]; this
0x18001b3bb  mov     r8d, 0B0h; unsigned __int16
0x18001b3c1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b3c6  mov     [rbp+57h+SizeUsed], 0
0x18001b3cd  mov     eax, 0BCh
0x18001b3d2  test    rbx, rbx
0x18001b3d5  jz      loc_18001B561
0x18001b3db  mov     [rbp+57h+var_6C], ax
0x18001b3df  mov     eax, 0BDh
0x18001b3e4  test    rsi, rsi
0x18001b3e7  jz      loc_18001B561
0x18001b3ed  mov     [rbp+57h+var_6C], ax
0x18001b3f1  xor     r9d, r9d; lpSecurityAttributes
0x18001b3f4  lea     eax, [r13+2]
0x18001b3f8  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18001b401  mov     r8d, eax; dwShareMode
0x18001b404  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001b40c  mov     edx, 0C0000000h; dwDesiredAccess
0x18001b411  mov     [rbp+57h+var_70], 0
0x18001b418  mov     rcx, rbx; lpFileName
0x18001b41b  mov     dword ptr [rsi], 8
0x18001b421  mov     [rsp+0B0h+dwCreationDisposition], eax; dwCreationDisposition
0x18001b425  call    cs:__imp_CreateFileW
0x18001b42b  mov     r14, rax
0x18001b42e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b432  jz      loc_18001B54C
0x18001b438  xor     edi, edi
0x18001b43a  mov     ecx, 0CBh
0x18001b43f  mov     [rbp+57h+var_70], edi
0x18001b442  mov     [rbp+57h+var_6C], cx
0x18001b446  lea     ebx, [rdi+64h]
0x18001b449  mov     eax, 7Ah ; 'z'
0x18001b44e  cmp     eax, 7Ah ; 'z'
0x18001b451  jnz     short loc_18001B4CE
0x18001b453  test    rdi, rdi
0x18001b456  jz      short loc_18001B461
0x18001b458  mov     rcx, rdi; pv
0x18001b45b  call    cs:__imp_CoTaskMemFree
0x18001b461  mov     ecx, ebx; cb
0x18001b463  call    cs:__imp_CoTaskMemAlloc
0x18001b469  mov     rdi, rax
0x18001b46c  test    rax, rax
0x18001b46f  mov     eax, 0DEh
0x18001b474  jz      short loc_18001B4C0
0x18001b476  mov     [rbp+57h+var_6C], ax
0x18001b47a  mov     r9, rdi; StorageDependencyInfo
0x18001b47d  lea     rax, [rbp+57h+SizeUsed]
0x18001b481  mov     [rbp+57h+var_70], 0
0x18001b488  mov     r8d, ebx; StorageDependencyInfoSize
0x18001b48b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; SizeUsed
0x18001b490  mov     edx, 3; Flags
0x18001b495  mov     [rdi], r13
0x18001b498  mov     rcx, r14; ObjectHandle
0x18001b49b  call    cs:__imp_GetStorageDependencyInformation
0x18001b4a1  cmp     eax, 0EAh
0x18001b4a6  jnz     short loc_18001B4B7
0x18001b4a8  cmp     [rbp+57h+SizeUsed], 48h ; 'H'
0x18001b4ac  jbe     short loc_18001B44E
0x18001b4ae  imul    ebx, [rdi+4], 1Ch
0x18001b4b2  add     ebx, 48h ; 'H'
0x18001b4b5  jmp     short loc_18001B449
0x18001b4b7  cmp     eax, 7Ah ; 'z'
0x18001b4ba  jnz     short loc_18001B4CE
0x18001b4bc  add     ebx, ebx
0x18001b4be  jmp     short loc_18001B44E
0x18001b4c0  mov     ebx, 8007000Eh
0x18001b4c5  mov     [rbp+57h+var_6A], ax
0x18001b4c9  mov     [rbp+57h+var_70], ebx
0x18001b4cc  jmp     short loc_18001B53C
0x18001b4ce  test    eax, eax
0x18001b4d0  jnz     short loc_18001B51D
0x18001b4d2  xor     r9d, r9d
0x18001b4d5  xor     r8d, r8d
0x18001b4d8  xor     edx, edx
0x18001b4da  cmp     [rdi+4], edx
0x18001b4dd  jbe     short loc_18001B51D
0x18001b4df  mov     eax, edx
0x18001b4e1  imul    rcx, rax, 1Ch
0x18001b4e5  test    dword ptr [rcx+rdi+8], 100h
0x18001b4ed  jz      short loc_18001B4F4
0x18001b4ef  mov     r9d, r13d
0x18001b4f2  jmp     short loc_18001B4FD
0x18001b4f4  test    byte ptr [rcx+rdi+8], 2
0x18001b4f9  cmovz   r8d, r13d
0x18001b4fd  add     edx, r13d
0x18001b500  cmp     edx, [rdi+4]
0x18001b503  jb      short loc_18001B4DF
0x18001b505  test    r9d, r9d
0x18001b508  jz      short loc_18001B512
0x18001b50a  mov     dword ptr [rsi], 9
0x18001b510  jmp     short loc_18001B51D
0x18001b512  test    r8d, r8d
0x18001b515  jz      short loc_18001B51D
0x18001b517  mov     dword ptr [rsi], 0Ah
0x18001b51d  xor     ebx, ebx
0x18001b51f  mov     eax, 116h
0x18001b524  mov     [rbp+57h+var_70], ebx
0x18001b527  mov     [rbp+57h+var_6C], ax
0x18001b52b  test    rdi, rdi
0x18001b52e  jz      short loc_18001B53C
0x18001b530  mov     rcx, rdi; pv
0x18001b533  call    cs:__imp_CoTaskMemFree
0x18001b539  mov     ebx, [rbp+57h+var_70]
0x18001b53c  test    r14, r14
0x18001b53f  jz      short loc_18001B56D
0x18001b541  mov     rcx, r14; hObject
0x18001b544  call    cs:__imp_CloseHandle
0x18001b54a  jmp     short loc_18001B56D
0x18001b54c  call    GetLastFailureAsHRESULT
0x18001b551  mov     ecx, 0CBh
0x18001b556  mov     [rbp+57h+var_70], eax
0x18001b559  mov     [rbp+57h+var_6A], cx
0x18001b55d  mov     ebx, eax
0x18001b55f  jmp     short loc_18001B56D
0x18001b561  mov     ebx, 80070057h
0x18001b566  mov     [rbp+57h+var_6A], ax
0x18001b56a  mov     [rbp+57h+var_70], ebx
0x18001b56d  lea     rcx, [rbp+57h+var_70]; this
0x18001b571  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b576  mov     eax, ebx
0x18001b578  add     rsp, 88h
0x18001b57f  pop     r14
0x18001b581  pop     r13
0x18001b583  pop     rdi
0x18001b584  pop     rsi
0x18001b585  pop     rbx
0x18001b586  pop     rbp
0x18001b587  retn
```
