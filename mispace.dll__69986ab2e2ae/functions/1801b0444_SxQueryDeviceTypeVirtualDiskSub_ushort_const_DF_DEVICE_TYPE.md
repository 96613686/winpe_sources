# SxQueryDeviceTypeVirtualDiskSub(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x1801b0444`
- end: `0x1801b066f`
- name: `?SxQueryDeviceTypeVirtualDiskSub@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801af550`
- `0x1801aff14`

## callees

- `0x1801af258`
- `0x1801b0444`
- `0x1801b0ec0`
- `0x1801b0fc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b051d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b060d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b051d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b060d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b052b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b052b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b04dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b04dd`
- `VirtDisk!GetStorageDependencyInformation` at `0x1801b0569`
- `VirtDisk!GetStorageDependencyInformation` at `0x1801b0569`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceTypeVirtualDiskSub(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *a2)
{
  __int16 v4; // ax
  HANDLE FileW; // r14
  struct _STORAGE_DEPENDENCY_INFO *v6; // rdi
  ULONG v7; // ebx
  DWORD StorageDependencyInformation; // eax
  unsigned int v9; // ebx
  int v10; // r9d
  int v11; // r8d
  ULONG v12; // edx
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-19h] BYREF
  __int16 v16; // [rsp+44h] [rbp-15h]
  __int16 v17; // [rsp+46h] [rbp-13h]
  ULONG SizeUsed; // [rsp+C0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "SxQueryDeviceTypeVirtualDiskSub",
    0xB0u,
    1u);
  SizeUsed = 0;
  v4 = 188;
  if ( lpFileName && (v16 = 188, v4 = 189, a2) )
  {
    v16 = 189;
    LastFailureAsHRESULT = 0;
    *(_DWORD *)a2 = 8;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v17 = 203;
      v9 = LastFailureAsHRESULT;
    }
    else
    {
      v6 = 0;
      LastFailureAsHRESULT = 0;
      v16 = 203;
      v7 = 100;
LABEL_5:
      StorageDependencyInformation = 122;
      while ( StorageDependencyInformation == 122 )
      {
        if ( v6 )
          CoTaskMemFree(v6);
        v6 = (struct _STORAGE_DEPENDENCY_INFO *)CoTaskMemAlloc(v7);
        if ( !v6 )
        {
          v9 = -2147024882;
          v17 = 222;
          LastFailureAsHRESULT = -2147024882;
          goto LABEL_29;
        }
        v16 = 222;
        LastFailureAsHRESULT = 0;
        *(_QWORD *)&v6->Version = 1;
        StorageDependencyInformation = GetStorageDependencyInformation(
                                         FileW,
                                         GET_STORAGE_DEPENDENCY_FLAG_DISK_HANDLE|GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                         v7,
                                         v6,
                                         &SizeUsed);
        if ( StorageDependencyInformation == 234 )
        {
          if ( SizeUsed > 0x48 )
          {
            v7 = 28 * v6->NumberEntries + 72;
            goto LABEL_5;
          }
        }
        else
        {
          if ( StorageDependencyInformation != 122 )
            break;
          v7 *= 2;
        }
      }
      if ( !StorageDependencyInformation )
      {
        v10 = 0;
        v11 = 0;
        v12 = 0;
        if ( v6->NumberEntries )
        {
          do
          {
            v13 = v12;
            if ( (v6->Version1Entries[v13].DependencyTypeFlags & 0x100) != 0 )
            {
              v10 = 1;
            }
            else if ( (v6->Version1Entries[v13].DependencyTypeFlags & 2) == 0 )
            {
              v11 = 1;
            }
            ++v12;
          }
          while ( v12 < v6->NumberEntries );
          if ( v10 )
          {
            *(_DWORD *)a2 = 9;
          }
          else if ( v11 )
          {
            *(_DWORD *)a2 = 10;
          }
        }
      }
      v9 = 0;
      LastFailureAsHRESULT = 0;
      v16 = 278;
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v9 = LastFailureAsHRESULT;
      }
LABEL_29:
      if ( FileW )
        CloseHandle(FileW);
    }
  }
  else
  {
    v9 = -2147024809;
    v17 = v4;
    LastFailureAsHRESULT = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1801b0444  push    rbp
0x1801b0446  push    rbx
0x1801b0447  push    rsi
0x1801b0448  push    rdi
0x1801b0449  push    r13
0x1801b044b  push    r14
0x1801b044d  lea     rbp, [rsp-2Fh]
0x1801b0452  sub     rsp, 88h
0x1801b0459  mov     rsi, rdx
0x1801b045c  mov     rbx, rcx
0x1801b045f  mov     r13d, 1
0x1801b0465  lea     rdx, aSxquerydevicet_0; "SxQueryDeviceTypeVirtualDiskSub"
0x1801b046c  mov     r9d, r13d; unsigned __int16
0x1801b046f  lea     rcx, [rbp+57h+var_70]; this
0x1801b0473  mov     r8d, 0B0h; unsigned __int16
0x1801b0479  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801b047e  mov     [rbp+57h+SizeUsed], 0
0x1801b0485  mov     eax, 0BCh
0x1801b048a  test    rbx, rbx
0x1801b048d  jz      loc_1801B0647
0x1801b0493  mov     [rbp+57h+var_6C], ax
0x1801b0497  mov     eax, 0BDh
0x1801b049c  test    rsi, rsi
0x1801b049f  jz      loc_1801B0647
0x1801b04a5  mov     [rbp+57h+var_6C], ax
0x1801b04a9  xor     r9d, r9d; lpSecurityAttributes
0x1801b04ac  lea     eax, [r13+2]
0x1801b04b0  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1801b04b9  mov     r8d, eax; dwShareMode
0x1801b04bc  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801b04c4  mov     edx, 0C0000000h; dwDesiredAccess
0x1801b04c9  mov     [rbp+57h+var_70], 0
0x1801b04d0  mov     rcx, rbx; lpFileName
0x1801b04d3  mov     dword ptr [rsi], 8
0x1801b04d9  mov     [rsp+0B0h+dwCreationDisposition], eax; dwCreationDisposition
0x1801b04dd  call    cs:__imp_CreateFileW
0x1801b04e4  nop     dword ptr [rax+rax+00h]
0x1801b04e9  mov     r14, rax
0x1801b04ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b04f0  jz      loc_1801B0632
0x1801b04f6  xor     edi, edi
0x1801b04f8  mov     ecx, 0CBh
0x1801b04fd  mov     [rbp+57h+var_70], edi
0x1801b0500  mov     [rbp+57h+var_6C], cx
0x1801b0504  lea     ebx, [rdi+64h]
0x1801b0507  mov     eax, 7Ah ; 'z'
0x1801b050c  cmp     eax, 7Ah ; 'z'
0x1801b050f  jnz     loc_1801B05A8
0x1801b0515  test    rdi, rdi
0x1801b0518  jz      short loc_1801B0529
0x1801b051a  mov     rcx, rdi; pv
0x1801b051d  call    cs:__imp_CoTaskMemFree
0x1801b0524  nop     dword ptr [rax+rax+00h]
0x1801b0529  mov     ecx, ebx; cb
0x1801b052b  call    cs:__imp_CoTaskMemAlloc
0x1801b0532  nop     dword ptr [rax+rax+00h]
0x1801b0537  mov     rdi, rax
0x1801b053a  test    rax, rax
0x1801b053d  mov     eax, 0DEh
0x1801b0542  jz      short loc_1801B059A
0x1801b0544  mov     [rbp+57h+var_6C], ax
0x1801b0548  mov     r9, rdi; StorageDependencyInfo
0x1801b054b  lea     rax, [rbp+57h+SizeUsed]
0x1801b054f  mov     [rbp+57h+var_70], 0
0x1801b0556  mov     r8d, ebx; StorageDependencyInfoSize
0x1801b0559  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; SizeUsed
0x1801b055e  mov     edx, 3; Flags
0x1801b0563  mov     [rdi], r13
0x1801b0566  mov     rcx, r14; ObjectHandle
0x1801b0569  call    cs:__imp_GetStorageDependencyInformation
0x1801b0570  nop     dword ptr [rax+rax+00h]
0x1801b0575  cmp     eax, 0EAh
0x1801b057a  jnz     short loc_1801B058E
0x1801b057c  cmp     [rbp+57h+SizeUsed], 48h ; 'H'
0x1801b0580  jbe     short loc_1801B050C
0x1801b0582  imul    ebx, [rdi+4], 1Ch
0x1801b0586  add     ebx, 48h ; 'H'
0x1801b0589  jmp     loc_1801B0507
0x1801b058e  cmp     eax, 7Ah ; 'z'
0x1801b0591  jnz     short loc_1801B05A8
0x1801b0593  add     ebx, ebx
0x1801b0595  jmp     loc_1801B050C
0x1801b059a  mov     ebx, 8007000Eh
0x1801b059f  mov     [rbp+57h+var_6A], ax
0x1801b05a3  mov     [rbp+57h+var_70], ebx
0x1801b05a6  jmp     short loc_1801B061C
0x1801b05a8  test    eax, eax
0x1801b05aa  jnz     short loc_1801B05F7
0x1801b05ac  xor     r9d, r9d
0x1801b05af  xor     r8d, r8d
0x1801b05b2  xor     edx, edx
0x1801b05b4  cmp     [rdi+4], edx
0x1801b05b7  jbe     short loc_1801B05F7
0x1801b05b9  mov     eax, edx
0x1801b05bb  imul    rcx, rax, 1Ch
0x1801b05bf  test    dword ptr [rcx+rdi+8], 100h
0x1801b05c7  jz      short loc_1801B05CE
0x1801b05c9  mov     r9d, r13d
0x1801b05cc  jmp     short loc_1801B05D7
0x1801b05ce  test    byte ptr [rcx+rdi+8], 2
0x1801b05d3  cmovz   r8d, r13d
0x1801b05d7  add     edx, r13d
0x1801b05da  cmp     edx, [rdi+4]
0x1801b05dd  jb      short loc_1801B05B9
0x1801b05df  test    r9d, r9d
0x1801b05e2  jz      short loc_1801B05EC
0x1801b05e4  mov     dword ptr [rsi], 9
0x1801b05ea  jmp     short loc_1801B05F7
0x1801b05ec  test    r8d, r8d
0x1801b05ef  jz      short loc_1801B05F7
0x1801b05f1  mov     dword ptr [rsi], 0Ah
0x1801b05f7  xor     ebx, ebx
0x1801b05f9  mov     eax, 116h
0x1801b05fe  mov     [rbp+57h+var_70], ebx
0x1801b0601  mov     [rbp+57h+var_6C], ax
0x1801b0605  test    rdi, rdi
0x1801b0608  jz      short loc_1801B061C
0x1801b060a  mov     rcx, rdi; pv
0x1801b060d  call    cs:__imp_CoTaskMemFree
0x1801b0614  nop     dword ptr [rax+rax+00h]
0x1801b0619  mov     ebx, [rbp+57h+var_70]
0x1801b061c  test    r14, r14
0x1801b061f  jz      short loc_1801B0653
0x1801b0621  mov     rcx, r14; hObject
0x1801b0624  call    cs:__imp_CloseHandle
0x1801b062b  nop     dword ptr [rax+rax+00h]
0x1801b0630  jmp     short loc_1801B0653
0x1801b0632  call    GetLastFailureAsHRESULT
0x1801b0637  mov     ecx, 0CBh
0x1801b063c  mov     [rbp+57h+var_70], eax
0x1801b063f  mov     [rbp+57h+var_6A], cx
0x1801b0643  mov     ebx, eax
0x1801b0645  jmp     short loc_1801B0653
0x1801b0647  mov     ebx, 80070057h
0x1801b064c  mov     [rbp+57h+var_6A], ax
0x1801b0650  mov     [rbp+57h+var_70], ebx
0x1801b0653  lea     rcx, [rbp+57h+var_70]; this
0x1801b0657  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801b065c  mov     eax, ebx
0x1801b065e  add     rsp, 88h
0x1801b0665  pop     r14
0x1801b0667  pop     r13
0x1801b0669  pop     rdi
0x1801b066a  pop     rsi
0x1801b066b  pop     rbx
0x1801b066c  pop     rbp
0x1801b066d  retn
```
