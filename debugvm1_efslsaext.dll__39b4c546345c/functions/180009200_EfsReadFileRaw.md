# EfsReadFileRaw

- ea: `0x180009200`
- end: `0x180009b26`
- name: `EfsReadFileRaw`
- size: `2342`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007bf0`

## callees

- `0x1800064f4`
- `0x180007e6c`
- `0x180008f40`
- `0x180009200`
- `0x18000a688`
- `0x18000a72c`
- `0x180012002`
- `0x18001200e`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009292`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009292`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b4`
- `ntdll!NtReadFile` at `0x18000993d`
- `ntdll!NtReadFile` at `0x18000993d`
- `ntdll!NtQueryInformationFile` at `0x18000967a`
- `ntdll!NtQueryInformationFile` at `0x18000967a`
- `ntdll!NtFsControlFile` at `0x180009408`
- `ntdll!NtFsControlFile` at `0x180009583`
- `ntdll!NtFsControlFile` at `0x180009784`
- `ntdll!NtFsControlFile` at `0x180009408`
- `ntdll!NtFsControlFile` at `0x180009583`
- `ntdll!NtFsControlFile` at `0x180009784`
- `ntdll!RtlNtStatusToDosError` at `0x1800095aa`
- `ntdll!RtlNtStatusToDosError` at `0x1800095aa`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800092bd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800094f2`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800092bd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800094f2`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000949b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009536`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000949b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009536`

## pseudocode

```c
__int64 __fastcall EfsReadFileRaw(__int64 a1, void *a2)
{
  bool v3; // zf
  unsigned __int64 *v5; // rsi
  HANDLE ProcessHeap; // rax
  int v7; // ecx
  _QWORD *InputBuffer; // r12
  unsigned int v9; // r15d
  unsigned int v10; // eax
  signed int BufferSize; // ebx
  _DWORD *v12; // r13
  void *v13; // rcx
  NTSTATUS v14; // eax
  int v15; // ecx
  unsigned int *v16; // r12
  NTSTATUS v17; // ebx
  HANDLE v18; // rax
  unsigned int *v20; // rax
  int v21; // ecx
  void *v22; // rcx
  NTSTATUS v23; // eax
  int v24; // ecx
  NTSTATUS v25; // ecx
  unsigned int v26; // eax
  void *v27; // r8
  unsigned int v28; // eax
  __int64 v29; // r13
  ULONG v30; // edx
  char v31; // r8
  __int64 v32; // r12
  int v33; // ecx
  __int64 v34; // r12
  unsigned int v35; // ecx
  void *v36; // rcx
  __int64 v37; // rdx
  size_t v38; // r8
  unsigned int v39; // eax
  __int64 v40; // rcx
  unsigned __int64 *v41; // r12
  ULONG OutputBufferLength; // edx
  void *v43; // rcx
  NTSTATUS v44; // eax
  NTSTATUS v45; // r13d
  int v46; // r8d
  unsigned int v47; // edx
  __int64 v48; // r9
  int v49; // r8d
  unsigned int v50; // eax
  unsigned __int64 v51; // rdx
  NTSTATUS v52; // eax
  unsigned int v53; // eax
  int v54; // r8d
  char IoStatusBlock; // [rsp+20h] [rbp-A9h]
  char v56; // [rsp+50h] [rbp-79h]
  unsigned int Size[3]; // [rsp+54h] [rbp-75h] BYREF
  bool v58; // [rsp+60h] [rbp-69h]
  ULONG InputBufferLength[2]; // [rsp+68h] [rbp-61h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-59h] BYREF
  ULONG v61; // [rsp+78h] [rbp-51h]
  __int64 v62; // [rsp+80h] [rbp-49h]
  void *v63; // [rsp+88h] [rbp-41h]
  struct _IO_STATUS_BLOCK v64; // [rsp+90h] [rbp-39h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-19h]
  _OWORD FileInformation[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v68; // [rsp+D8h] [rbp+Fh]

  v62 = a1;
  v63 = a2;
  v68 = 0;
  InputBufferLength[0] = 0;
  Size[0] = 0;
  v3 = *(_DWORD *)a1 == 1;
  v5 = 0;
  ByteOffset.QuadPart = 0;
  v64 = 0;
  v66 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v65 = 0;
  if ( !v3 || (*(_BYTE *)(a1 + 4) & 3) != 0 )
  {
    InputBuffer = 0;
    BufferSize = 5;
    goto LABEL_21;
  }
  ProcessHeap = GetProcessHeap();
  InputBuffer = HeapAlloc(ProcessHeap, 8u, 0x80u);
  *(_QWORD *)&Size[1] = InputBuffer;
  v9 = 69632;
  do
  {
    if ( v9 < 0x5000 )
      break;
    v5 = (unsigned __int64 *)VirtualAlloc(0, v9, 0x1000u, 4u);
    v10 = v9 - 0x2000;
    if ( v5 )
      v10 = v9;
    v9 = v10;
  }
  while ( !v5 );
  if ( !v5 || !InputBuffer )
  {
    fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, 8, 11, 49);
    BufferSize = 14;
    goto LABEL_21;
  }
  memset_0(InputBuffer, 0, 0x80u);
  memset_0(v5, 0, v9);
  *(_DWORD *)v5 = 256;
  *(unsigned __int64 *)((char *)v5 + 4) = 0x530042004F0052LL;
  *((_DWORD *)v5 + 5) = 30;
  v5[3] = 0x5300460054004ELL;
  *((_WORD *)v5 + 24) = 6416;
  *((_DWORD *)v5 + 11) = 2;
  Size[0] = 50;
  BufferSize = EfspSendPipeData((char *)v5, 0x32u, a2);
  if ( !BufferSize )
  {
    memset_0(v5, 0, Size[0]);
    LODWORD(v65) = 1;
    *(unsigned __int64 *)((char *)v5 + 4) = 0x45005200550047LL;
    BufferSize = EfsFsctlGetBufferSize(&v65, InputBufferLength);
    if ( BufferSize >= 0 )
    {
      v12 = v5 + 2;
      if ( InputBufferLength[0] != 16 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      EfsFsctlPrepareData(
        3,
        0,
        (*(_DWORD *)(a1 + 4) & 0xFFFF8000) << 16,
        (unsigned int)&v65,
        (__int64)InputBuffer,
        (__int64)InputBufferLength);
      v13 = *(void **)(a1 + 8);
      v61 = InputBufferLength[0];
      v14 = NtFsControlFile(v13, 0, 0, 0, &v64, 0x900DBu, InputBuffer, InputBufferLength[0], v5 + 2, v9 - 16);
      v16 = (unsigned int *)v5;
      v17 = v14;
      if ( v14 < 0 )
      {
        fnEfsLogTrace1(v15, (unsigned int)EFS_API_ERROR, v14, 11, 172);
        if ( v17 != -1073741789 )
        {
LABEL_30:
          v25 = v17;
          goto LABEL_31;
        }
        if ( (unsigned int)(*v12 + 16) < *v12 )
          goto LABEL_19;
        if ( *v12 + 4112 < (unsigned int)(*v12 + 16) )
          goto LABEL_19;
        v9 = (*v12 + 4111) & 0xFFFFF000;
        if ( v9 < 0x5000 )
          goto LABEL_19;
        v20 = (unsigned int *)VirtualAlloc(0, v9, 0x1000u, 4u);
        v16 = v20;
        if ( !v20 )
        {
          fnEfsLogTrace1(v21, (unsigned int)EFS_ERROR_MEMORY, v9, 11, 219);
          BufferSize = 8;
          goto LABEL_20;
        }
        *(_OWORD *)v20 = *(_OWORD *)v5;
        VirtualFree(v5, 0, 0x8000u);
        v12 = v16 + 4;
        v22 = *(void **)(v62 + 8);
        *(_QWORD *)InputBufferLength = v16;
        v23 = NtFsControlFile(v22, 0, 0, 0, &v64, 0x900DBu, *(PVOID *)&Size[1], v61, v16 + 4, v9 - 16);
        v17 = v23;
        v5 = (unsigned __int64 *)v16;
        if ( v23 < 0 )
        {
          fnEfsLogTrace1(v24, (unsigned int)EFS_API_ERROR, v23, 11, 242);
          goto LABEL_30;
        }
      }
      v26 = *v12 + 16;
      if ( *v12 >= 0xFFFFFFF0 )
      {
        Size[0] = -1;
      }
      else
      {
        Size[0] = *v12 + 16;
        if ( v26 <= v9 )
        {
          v27 = v63;
          *v16 = v26;
          v58 = 1;
          v28 = EfspSendPipeData((char *)v5, Size[0], v27);
          v29 = v62;
          v30 = 0;
          InputBuffer = *(_QWORD **)&Size[1];
          BufferSize = v28;
          InputBufferLength[0] = 0;
          ByteOffset.QuadPart = 0;
          if ( *(_DWORD *)(v62 + 16) )
          {
            v61 = 16;
            *(_DWORD *)(*(_QWORD *)&Size[1] + 8LL) = v9 - 4096;
            v31 = 1;
          }
          else
          {
            v31 = 0;
          }
          v56 = v31;
          if ( v28 )
            goto LABEL_21;
          while ( 1 )
          {
            if ( !v31 )
              goto LABEL_21;
            if ( ByteOffset.QuadPart > 0x7FFFFFFFFFFFFFFFuLL )
            {
              BufferSize = 5;
              *InputBuffer = -1;
              fnEfsLogTrace1(-1, (unsigned int)EFS_API_ERROR, 5, 11, 70);
              goto LABEL_21;
            }
            *InputBuffer = ByteOffset.QuadPart;
            if ( !ByteOffset.QuadPart )
            {
              v32 = v30;
              v17 = NtQueryInformationFile(
                      *(HANDLE *)(*(_QWORD *)(v29 + 24) + 8LL * v30),
                      &v64,
                      FileInformation,
                      0x28u,
                      FileBasicInformation);
              if ( v17 < 0 )
              {
                fnEfsLogTrace1(v33, (unsigned int)EFS_API_ERROR, v17, 11, 102);
                goto LABEL_30;
              }
              v58 = (v68 & 0x4000) != 0;
              v34 = 2 * v32;
              *((_DWORD *)v5 + 3) = (v68 & 0x4000) == 0;
              v35 = *(unsigned __int16 *)(*(_QWORD *)(v29 + 32) + 8 * v34);
              *((_DWORD *)v5 + 6) = v35;
              v35 += 28;
              *(_DWORD *)v5 = v35;
              Size[0] = v35;
              v36 = (char *)v5 + 28;
              *(unsigned __int64 *)((char *)v5 + 4) = 0x5300460054004ELL;
              v5[2] = 0;
              if ( (unsigned __int64 *)((char *)v5 + 28) < v5
                || (v37 = *(_QWORD *)(v29 + 32), v38 = *(unsigned __int16 *)(v37 + 8 * v34), (int)v38 + 28 > v9) )
              {
                IoStatusBlock = -97;
                goto LABEL_83;
              }
              memcpy_0(v36, *(const void **)(v37 + 8 * v34 + 8), v38);
              v39 = EfspSendPipeData((char *)v5, Size[0], v63);
              BufferSize = v39;
              if ( v39 )
              {
                IoStatusBlock = -78;
                goto LABEL_80;
              }
            }
            v40 = InputBufferLength[0];
            v41 = v5 + 2;
            *((_DWORD *)v5 + 3) = 0;
            OutputBufferLength = v9 - 16;
            *(unsigned __int64 *)((char *)v5 + 4) = 0x45005200550047LL;
            v43 = *(void **)(*(_QWORD *)(v29 + 24) + 8 * v40);
            if ( v58 )
            {
              v44 = NtFsControlFile(v43, 0, 0, 0, &v64, 0x900E3u, *(PVOID *)&Size[1], v61, v5 + 2, OutputBufferLength);
              v45 = v44;
              LODWORD(v36) = v44 + 0x80000000;
              if ( (int)(v44 + 0x80000000) >= 0 && v44 != -1073741807 )
              {
                fnEfsLogTrace1((_DWORD)v36, (unsigned int)EFS_API_ERROR, v44, 11, 252);
LABEL_86:
                v25 = v45;
LABEL_31:
                BufferSize = RtlNtStatusToDosError(v25);
LABEL_20:
                InputBuffer = *(_QWORD **)&Size[1];
                goto LABEL_21;
              }
              if ( v44 != -1073741807 )
              {
                Size[0] = 16;
                if ( v41 < v5
                  || (LODWORD(v36) = *((_DWORD *)v5 + 6) + 16, *((_DWORD *)v5 + 6) >= 0xFFFFFFF0)
                  || (unsigned int)v36 > v9 )
                {
                  IoStatusBlock = 20;
                  goto LABEL_83;
                }
                Size[0] = *((_DWORD *)v5 + 6) + 16;
                v46 = *((unsigned __int16 *)v5 + 21);
                v47 = 4 * v46 + 32;
                if ( v47 < 4 * v46 )
                {
                  IoStatusBlock = 41;
LABEL_83:
                  BufferSize = 5;
                  v54 = 5;
                  goto LABEL_81;
                }
                if ( v47 > *((_DWORD *)v5 + 6) )
                {
                  IoStatusBlock = 47;
                  goto LABEL_83;
                }
                BufferSize = 0;
                v48 = 0;
                if ( (_WORD)v46 )
                {
                  while ( (unsigned __int64 *)((char *)v5 + (unsigned int)v36) >= v5 )
                  {
                    v49 = *((_DWORD *)v41 + v48 + 7);
                    if ( (int)v36 + v49 < (unsigned int)v36 || (int)v36 + v49 > v9 )
                      break;
                    LODWORD(v36) = v49 + (_DWORD)v36;
                    BufferSize = 0;
                    Size[0] = (unsigned int)v36;
                    v48 = (unsigned int)(v48 + 1);
                    if ( (unsigned int)v48 >= *((unsigned __int16 *)v5 + 21) )
                      goto LABEL_59;
                  }
                  IoStatusBlock = 67;
LABEL_88:
                  BufferSize = 5;
                  v54 = 5;
LABEL_81:
                  fnEfsLogTrace1((_DWORD)v36, (unsigned int)EFS_API_ERROR, v54, 11, IoStatusBlock);
                  goto LABEL_20;
                }
LABEL_59:
                *(_DWORD *)v5 = (_DWORD)v36;
                LOBYTE(v36) = *((_BYTE *)v5 + 38);
                v50 = *((unsigned __int16 *)v5 + 21) << (char)v36;
                if ( *((_DWORD *)v5 + 7) >= v50 )
                {
                  v51 = *v41 + v50;
                  if ( v51 < *v41 )
                  {
                    ByteOffset.QuadPart = -1;
                    IoStatusBlock = -127;
                    goto LABEL_83;
                  }
                  goto LABEL_61;
                }
              }
            }
            else
            {
              v52 = NtReadFile(v43, 0, 0, 0, &v64, v5 + 2, OutputBufferLength, &ByteOffset, 0);
              v45 = v52;
              if ( v52 < 0 )
              {
                fnEfsLogTrace1((_DWORD)v36, (unsigned int)EFS_API_ERROR, v52, 11, 152);
                if ( v45 != -1073741807 )
                  goto LABEL_86;
              }
              if ( v45 == 259 )
                __fastfail(7u);
              if ( v45 != -1073741807 )
              {
                Size[0] = 16;
                if ( v41 < v5
                  || (v53 = LODWORD(v64.Information) + 16, LODWORD(v64.Information) >= 0xFFFFFFF0)
                  || v53 > v9 )
                {
                  IoStatusBlock = -66;
                  goto LABEL_88;
                }
                Size[0] = LODWORD(v64.Information) + 16;
                BufferSize = 0;
                *(_DWORD *)v5 = v53;
                if ( v9 - 16 <= LODWORD(v64.Information) )
                {
                  v51 = ByteOffset.QuadPart + LODWORD(v64.Information);
                  if ( v51 < ByteOffset.QuadPart )
                  {
                    ByteOffset.QuadPart = -1;
                    IoStatusBlock = -13;
                    goto LABEL_83;
                  }
LABEL_61:
                  ByteOffset.QuadPart = v51;
                  goto LABEL_62;
                }
              }
            }
            LODWORD(v36) = v62;
            v30 = InputBufferLength[0] + 1;
            ByteOffset.QuadPart = 0;
            InputBufferLength[0] = v30;
            v31 = v30 < *(_DWORD *)(v62 + 16) ? v56 : 0;
            v56 = v31;
            BufferSize = v30 < *(_DWORD *)(v62 + 16) ? BufferSize : 0;
            if ( v45 == -1073741807 )
            {
              if ( BufferSize )
                goto LABEL_20;
              InputBuffer = *(_QWORD **)&Size[1];
              v29 = v62;
            }
            else
            {
LABEL_62:
              if ( Size[0] > v9 )
              {
                IoStatusBlock = 3;
                goto LABEL_83;
              }
              v39 = EfspSendPipeData((char *)v5, Size[0], v63);
              BufferSize = v39;
              if ( v39 )
              {
                IoStatusBlock = 11;
LABEL_80:
                v54 = v39;
                goto LABEL_81;
              }
              InputBuffer = *(_QWORD **)&Size[1];
              v29 = v62;
              v30 = InputBufferLength[0];
              v31 = v56;
            }
          }
        }
      }
LABEL_19:
      BufferSize = 5;
      goto LABEL_20;
    }
  }
LABEL_21:
  EfspSendPipeData((char *)Size, 0, v63);
  if ( v5 )
    VirtualFree(v5, 0, 0x8000u);
  if ( InputBuffer )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, InputBuffer);
  }
  return (unsigned int)BufferSize;
}

```

## disassembly

```asm
0x180009200  mov     [rsp-8+arg_10], rbx
0x180009205  push    rbp
0x180009206  push    rsi
0x180009207  push    rdi
0x180009208  push    r12
0x18000920a  push    r13
0x18000920c  push    r14
0x18000920e  push    r15
0x180009210  lea     rbp, [rsp-27h]
0x180009215  sub     rsp, 0F0h
0x18000921c  mov     rax, cs:__security_cookie
0x180009223  xor     rax, rsp
0x180009226  mov     [rbp+57h+var_40], rax
0x18000922a  xor     eax, eax
0x18000922c  mov     [rbp+57h+var_A0], rcx
0x180009230  mov     rdi, rcx
0x180009233  mov     [rbp+57h+var_98], rdx
0x180009237  xor     ecx, ecx
0x180009239  mov     [rbp+57h+var_48], rax
0x18000923d  xorps   xmm0, xmm0
0x180009240  mov     [rbp+57h+var_B8], ecx
0x180009243  xorps   xmm1, xmm1
0x180009246  mov     dword ptr [rbp+57h+Size], ecx
0x180009249  cmp     dword ptr [rdi], 1
0x18000924c  mov     rbx, rdx
0x18000924f  mov     esi, ecx
0x180009251  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x180009255  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180009259  mov     [rbp+57h+var_70], rax
0x18000925d  movups  [rbp+57h+FileInformation], xmm1
0x180009261  movups  [rbp+57h+var_58], xmm1
0x180009265  movups  [rbp+57h+var_80], xmm0
0x180009269  jnz     loc_180009B19
0x18000926f  test    byte ptr [rdi+4], 3
0x180009273  jnz     loc_180009B19
0x180009279  call    cs:__imp_GetProcessHeap
0x18000927f  mov     r13d, 80h
0x180009285  lea     r14d, [rsi+8]
0x180009289  mov     rcx, rax; hHeap
0x18000928c  mov     r8d, r13d; dwBytes
0x18000928f  mov     edx, r14d; dwFlags
0x180009292  call    cs:__imp_HeapAlloc
0x180009298  mov     r12, rax
0x18000929b  mov     qword ptr [rbp+57h+Size+4], rax
0x18000929f  mov     r15d, 11000h
0x1800092a5  cmp     r15d, 5000h
0x1800092ac  jb      short loc_1800092D9
0x1800092ae  xor     ecx, ecx; lpAddress
0x1800092b0  mov     edx, r15d; dwSize
0x1800092b3  mov     r8d, 1000h; flAllocationType
0x1800092b9  lea     r9d, [rcx+4]; flProtect
0x1800092bd  call    cs:__imp_VirtualAlloc
0x1800092c3  mov     rsi, rax
0x1800092c6  lea     eax, [r15-2000h]
0x1800092cd  test    rsi, rsi
0x1800092d0  cmovnz  eax, r15d
0x1800092d4  mov     r15d, eax
0x1800092d7  jz      short loc_1800092A5
0x1800092d9  test    rsi, rsi
0x1800092dc  jz      loc_180009AF2
0x1800092e2  test    r12, r12
0x1800092e5  jz      loc_180009AF2
0x1800092eb  mov     r8, r13; Size
0x1800092ee  xor     edx, edx; Val
0x1800092f0  mov     rcx, r12; void *
0x1800092f3  call    memset_0
0x1800092f8  mov     r8d, r15d; Size
0x1800092fb  xor     edx, edx; Val
0x1800092fd  mov     rcx, rsi; void *
0x180009300  call    memset_0
0x180009305  mov     dword ptr [rsi], 100h
0x18000930b  lea     rdx, [rsi+30h]
0x18000930f  mov     rax, 530042004F0052h
0x180009319  mov     r8, rbx; void *
0x18000931c  mov     [rsi+4], rax
0x180009320  mov     rcx, rsi; char *
0x180009323  mov     dword ptr [rsi+14h], 1Eh
0x18000932a  mov     rax, 5300460054004Eh
0x180009334  mov     [rsi+18h], rax
0x180009338  mov     word ptr [rdx], 1910h
0x18000933d  sub     edx, esi
0x18000933f  add     edx, 2; unsigned int
0x180009342  mov     dword ptr [rsi+2Ch], 2
0x180009349  mov     dword ptr [rbp+57h+Size], edx
0x18000934c  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x180009351  mov     ebx, eax
0x180009353  test    eax, eax
0x180009355  jnz     loc_18000947C
0x18000935b  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000935f  xor     edx, edx; Val
0x180009361  mov     rcx, rsi; void *
0x180009364  call    memset_0
0x180009369  mov     rax, 45005200550047h
0x180009373  mov     dword ptr [rbp+57h+var_80], 1
0x18000937a  lea     rdx, [rbp+57h+var_B8]
0x18000937e  mov     [rsi+4], rax
0x180009382  lea     rcx, [rbp+57h+var_80]
0x180009386  call    EfsFsctlGetBufferSize
0x18000938b  mov     ebx, eax
0x18000938d  test    eax, eax
0x18000938f  js      loc_18000947C
0x180009395  cmp     [rbp+57h+var_B8], 10h
0x180009399  lea     r13, [rsi+10h]
0x18000939d  jz      short loc_1800093A4
0x18000939f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800093a4  mov     r8d, [rdi+4]
0x1800093a8  lea     rax, [rbp+57h+var_B8]
0x1800093ac  xor     edx, edx
0x1800093ae  mov     qword ptr [rsp+120h+FsControlCode], rax
0x1800093b3  and     r8d, 0FFFF8000h
0x1800093ba  mov     [rsp+120h+IoStatusBlock], r12
0x1800093bf  shl     r8d, 10h
0x1800093c3  lea     r9, [rbp+57h+var_80]
0x1800093c7  lea     ecx, [rdx+3]
0x1800093ca  call    EfsFsctlPrepareData
0x1800093cf  mov     rcx, [rdi+8]; FileHandle
0x1800093d3  lea     eax, [r15-10h]
0x1800093d7  mov     [rsp+120h+OutputBufferLength], eax; OutputBufferLength
0x1800093db  xor     r9d, r9d; ApcContext
0x1800093de  mov     eax, [rbp+57h+var_B8]
0x1800093e1  xor     r8d, r8d; ApcRoutine
0x1800093e4  mov     [rsp+120h+OutputBuffer], r13; OutputBuffer
0x1800093e9  xor     edx, edx; Event
0x1800093eb  mov     [rsp+120h+InputBufferLength], eax; InputBufferLength
0x1800093ef  mov     [rbp+57h+var_A8], eax
0x1800093f2  lea     rax, [rbp+57h+var_90]
0x1800093f6  mov     [rsp+120h+InputBuffer], r12; InputBuffer
0x1800093fb  mov     [rsp+120h+FsControlCode], 900DBh; FsControlCode
0x180009403  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x180009408  call    cs:__imp_NtFsControlFile
0x18000940e  mov     r12, rsi
0x180009411  lea     r14, EFS_API_ERROR
0x180009418  mov     ebx, eax
0x18000941a  mov     edi, 0Bh
0x18000941f  test    eax, eax
0x180009421  jns     loc_1800095B7
0x180009427  mov     r9d, edi
0x18000942a  mov     dword ptr [rsp+120h+IoStatusBlock], 3ACh
0x180009432  mov     r8d, eax
0x180009435  mov     rdx, r14
0x180009438  call    fnEfsLogTrace1
0x18000943d  cmp     ebx, 0C0000023h
0x180009443  jnz     loc_1800095A8
0x180009449  mov     eax, [r13+0]
0x18000944d  lea     ecx, [rax+10h]
0x180009450  cmp     ecx, eax
0x180009452  jb      short loc_180009473
0x180009454  lea     r15d, [rcx+1000h]
0x18000945b  cmp     r15d, ecx
0x18000945e  jb      short loc_180009473
0x180009460  dec     r15d
0x180009463  and     r15d, 0FFFFF000h
0x18000946a  cmp     r15d, 5000h
0x180009471  jnb     short loc_1800094E3
0x180009473  mov     ebx, 5
0x180009478  mov     r12, qword ptr [rbp+57h+Size+4]
0x18000947c  mov     r8, [rbp+57h+var_98]; void *
0x180009480  lea     rcx, [rbp+57h+Size]; char *
0x180009484  xor     edx, edx; unsigned int
0x180009486  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x18000948b  test    rsi, rsi
0x18000948e  jz      short loc_1800094A1
0x180009490  xor     edx, edx; dwSize
0x180009492  mov     r8d, 8000h; dwFreeType
0x180009498  mov     rcx, rsi; lpAddress
0x18000949b  call    cs:__imp_VirtualFree
0x1800094a1  test    r12, r12
0x1800094a4  jz      short loc_1800094BA
0x1800094a6  call    cs:__imp_GetProcessHeap
0x1800094ac  mov     r8, r12; lpMem
0x1800094af  xor     edx, edx; dwFlags
0x1800094b1  mov     rcx, rax; hHeap
0x1800094b4  call    cs:__imp_HeapFree
0x1800094ba  mov     eax, ebx
0x1800094bc  mov     rcx, [rbp+57h+var_40]
0x1800094c0  xor     rcx, rsp; StackCookie
0x1800094c3  call    __security_check_cookie
0x1800094c8  mov     rbx, [rsp+120h+arg_10]
0x1800094d0  add     rsp, 0F0h
0x1800094d7  pop     r15
0x1800094d9  pop     r14
0x1800094db  pop     r13
0x1800094dd  pop     r12
0x1800094df  pop     rdi
0x1800094e0  pop     rsi
0x1800094e1  pop     rbp
0x1800094e2  retn
0x1800094e3  xor     ecx, ecx; lpAddress
0x1800094e5  mov     edx, r15d; dwSize
0x1800094e8  mov     r8d, 1000h; flAllocationType
0x1800094ee  lea     r9d, [rcx+4]; flProtect
0x1800094f2  call    cs:__imp_VirtualAlloc
0x1800094f8  mov     r12, rax
0x1800094fb  test    rax, rax
0x1800094fe  jnz     short loc_180009524
0x180009500  mov     r9d, edi
0x180009503  mov     dword ptr [rsp+120h+IoStatusBlock], 3DBh
0x18000950b  mov     r8d, r15d
0x18000950e  lea     rdx, EFS_ERROR_MEMORY
0x180009515  call    fnEfsLogTrace1
0x18000951a  lea     ebx, [r12+8]
0x18000951f  jmp     loc_180009478
0x180009524  movups  xmm0, xmmword ptr [rsi]
0x180009527  xor     edx, edx; dwSize
0x180009529  mov     r8d, 8000h; dwFreeType
0x18000952f  mov     rcx, rsi; lpAddress
0x180009532  movdqu  xmmword ptr [rax], xmm0
0x180009536  call    cs:__imp_VirtualFree
0x18000953c  mov     rcx, [rbp+57h+var_A0]
0x180009540  lea     eax, [r15-10h]
0x180009544  mov     [rsp+120h+OutputBufferLength], eax; OutputBufferLength
0x180009548  lea     r13, [r12+10h]
0x18000954d  mov     eax, [rbp+57h+var_A8]
0x180009550  xor     r9d, r9d; ApcContext
0x180009553  mov     [rsp+120h+OutputBuffer], r13; OutputBuffer
0x180009558  xor     r8d, r8d; ApcRoutine
0x18000955b  mov     rcx, [rcx+8]; FileHandle
0x18000955f  xor     edx, edx; Event
0x180009561  mov     [rsp+120h+InputBufferLength], eax; InputBufferLength
0x180009565  mov     rax, qword ptr [rbp+57h+Size+4]
0x180009569  mov     [rsp+120h+InputBuffer], rax; InputBuffer
0x18000956e  lea     rax, [rbp+57h+var_90]
0x180009572  mov     [rsp+120h+FsControlCode], 900DBh; FsControlCode
0x18000957a  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x18000957f  mov     qword ptr [rbp+57h+var_B8], r12
0x180009583  call    cs:__imp_NtFsControlFile
0x180009589  mov     ebx, eax
0x18000958b  mov     rsi, r12
0x18000958e  test    eax, eax
0x180009590  jns     short loc_1800095B7
0x180009592  mov     dword ptr [rsp+120h+IoStatusBlock], 3F2h
0x18000959a  mov     r8d, eax
0x18000959d  mov     r9d, edi
0x1800095a0  mov     rdx, r14
0x1800095a3  call    fnEfsLogTrace1
0x1800095a8  mov     ecx, ebx; Status
0x1800095aa  call    cs:__imp_RtlNtStatusToDosError
0x1800095b0  mov     ebx, eax
0x1800095b2  jmp     loc_180009478
0x1800095b7  mov     eax, [r13+0]
0x1800095bb  add     eax, 10h
0x1800095be  cmp     eax, 10h
0x1800095c1  jb      loc_180009AE5
0x1800095c7  mov     dword ptr [rbp+57h+Size], eax
0x1800095ca  cmp     eax, r15d
0x1800095cd  ja      loc_180009473
0x1800095d3  mov     r8, [rbp+57h+var_98]; void *
0x1800095d7  mov     rcx, rsi; char *
0x1800095da  mov     [r12], eax
0x1800095de  mov     edx, dword ptr [rbp+57h+Size]; unsigned int
0x1800095e1  mov     [rbp+57h+var_C0], 1
0x1800095e5  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x1800095ea  mov     r13, [rbp+57h+var_A0]
0x1800095ee  xor     edx, edx
0x1800095f0  mov     r12, qword ptr [rbp+57h+Size+4]
0x1800095f4  mov     ebx, eax
0x1800095f6  mov     [rbp+57h+var_B8], edx
0x1800095f9  mov     qword ptr [rbp+57h+ByteOffset], rdx
0x1800095fd  cmp     [r13+10h], edx
0x180009601  jnz     short loc_180009608
0x180009603  xor     r8b, r8b
0x180009606  jmp     short loc_18000961E
0x180009608  lea     eax, [r15-1000h]
0x18000960f  mov     [rbp+57h+var_A8], 10h
0x180009616  mov     [r12+8], eax
0x18000961b  mov     r8b, 1
0x18000961e  mov     [rbp+57h+var_D0], r8b
0x180009622  test    ebx, ebx
0x180009624  jnz     loc_18000947C
0x18000962a  test    r8b, r8b
0x18000962d  jz      loc_18000947C
0x180009633  mov     rax, qword ptr [rbp+57h+ByteOffset]
0x180009637  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180009641  cmp     rax, rcx
0x180009644  ja      loc_180009ABD
0x18000964a  mov     [r12], rax
0x18000964e  cmp     qword ptr [rbp+57h+ByteOffset], 0
0x180009653  jnz     loc_180009720
0x180009659  mov     rcx, [r13+18h]
0x18000965d  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180009661  mov     r12d, edx
0x180009664  mov     r9d, 28h ; '('; Length
0x18000966a  lea     rdx, [rbp+57h+var_90]; IoStatusBlock
0x18000966e  mov     dword ptr [rsp+120h+IoStatusBlock], 4; FileInformationClass
0x180009676  mov     rcx, [rcx+r12*8]; FileHandle
0x18000967a  call    cs:__imp_NtQueryInformationFile
0x180009680  mov     ebx, eax
0x180009682  test    eax, eax
0x180009684  js      loc_180009A29
0x18000968a  test    dword ptr [rbp+57h+var_48], 4000h
0x180009691  setnz   [rbp+57h+var_C0]
0x180009695  xor     eax, eax
0x180009697  test    dword ptr [rbp+57h+var_48], 4000h
0x18000969e  setz    al
0x1800096a1  add     r12, r12
0x1800096a4  mov     [rsi+0Ch], eax
0x1800096a7  mov     rax, [r13+20h]
0x1800096ab  movzx   ecx, word ptr [rax+r12*8]
0x1800096b0  mov     rax, 5300460054004Eh
0x1800096ba  mov     [rsi+18h], ecx
  ... truncated ...
```
