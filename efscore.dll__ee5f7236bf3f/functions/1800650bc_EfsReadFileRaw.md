# EfsReadFileRaw

- ea: `0x1800650bc`
- end: `0x1800659f5`
- name: `EfsReadFileRaw`
- size: `2361`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800109f0`

## callees

- `0x180004f86`
- `0x180005045`
- `0x1800102f0`
- `0x180010bf0`
- `0x1800124d8`
- `0x180063698`
- `0x180063e48`
- `0x180064724`
- `0x1800650bc`
- `0x180068438`
- `0x1800684dc`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006516b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065349`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006516b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065349`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065392`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800659b9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065392`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800659b9`
- `ntdll!NtReadFile` at `0x180065721`
- `ntdll!NtReadFile` at `0x180065721`
- `ntdll!NtFsControlFile` at `0x1800652ba`
- `ntdll!NtFsControlFile` at `0x1800653de`
- `ntdll!NtFsControlFile` at `0x1800655e6`
- `ntdll!NtFsControlFile` at `0x1800652ba`
- `ntdll!NtFsControlFile` at `0x1800653de`
- `ntdll!NtFsControlFile` at `0x1800655e6`
- `ntdll!NtQueryInformationFile` at `0x1800654d7`
- `ntdll!NtQueryInformationFile` at `0x1800654d7`
- `ntdll!RtlNtStatusToDosError` at `0x18006540c`
- `ntdll!RtlNtStatusToDosError` at `0x1800658b2`
- `ntdll!RtlNtStatusToDosError` at `0x18006540c`
- `ntdll!RtlNtStatusToDosError` at `0x1800658b2`

## pseudocode

```c
__int64 __fastcall EfsReadFileRaw(__int64 a1, void *a2)
{
  bool v3; // zf
  char *v5; // rdi
  _DWORD *InputBuffer; // r12
  unsigned int v7; // r15d
  unsigned int v8; // eax
  signed int BufferSize; // ebx
  __int64 v10; // rcx
  void *v11; // rcx
  NTSTATUS v12; // eax
  unsigned int *v13; // r13
  int v14; // ebx
  unsigned int *v15; // rax
  NTSTATUS v16; // eax
  unsigned int v17; // eax
  void *v18; // r8
  unsigned int v19; // eax
  __int64 v20; // r13
  __int64 v21; // rcx
  char v22; // dl
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r10
  int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // r9d
  __int64 v29; // r10
  unsigned __int64 *v30; // r12
  ULONG OutputBufferLength; // edx
  void *v32; // rcx
  NTSTATUS v33; // eax
  NTSTATUS v34; // r13d
  unsigned int v35; // eax
  int v36; // r9d
  int v37; // r10d
  unsigned int v38; // ecx
  __int64 i; // r11
  int v40; // r9d
  int v41; // r10d
  int v42; // r11d
  unsigned int v43; // eax
  unsigned __int64 v44; // rdx
  int v45; // r8d
  NTSTATUS v46; // eax
  int v47; // r10d
  bool v48; // cf
  char *v49; // rcx
  unsigned int v50; // r9d
  unsigned int v51; // eax
  int v52; // r8d
  char IoStatusBlock; // [rsp+20h] [rbp-A9h]
  char IoStatusBlocka; // [rsp+20h] [rbp-A9h]
  char v56; // [rsp+50h] [rbp-79h]
  size_t Size; // [rsp+54h] [rbp-75h] BYREF
  bool v58; // [rsp+5Ch] [rbp-6Dh]
  PVOID v59; // [rsp+60h] [rbp-69h]
  union _LARGE_INTEGER ByteOffset; // [rsp+68h] [rbp-61h] BYREF
  __int64 v61; // [rsp+70h] [rbp-59h]
  ULONG InputBufferLength; // [rsp+78h] [rbp-51h]
  unsigned int v63; // [rsp+7Ch] [rbp-4Dh] BYREF
  unsigned __int64 v64; // [rsp+80h] [rbp-49h]
  void *v65; // [rsp+88h] [rbp-41h]
  struct _IO_STATUS_BLOCK v66; // [rsp+90h] [rbp-39h] BYREF
  __int128 v67; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-19h]
  _OWORD FileInformation[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v70; // [rsp+D8h] [rbp+Fh]

  v61 = a1;
  v65 = a2;
  v70 = 0;
  Size = 0;
  v3 = *(_DWORD *)a1 == 1;
  v5 = 0;
  ByteOffset.QuadPart = 0;
  v66 = 0;
  v63 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v68 = 0;
  v67 = 0;
  if ( !v3 || (*(_BYTE *)(a1 + 4) & 3) != 0 )
  {
    InputBuffer = 0;
    goto LABEL_90;
  }
  InputBuffer = wil::details::heap_allocator::allocate(0x80u);
  v59 = InputBuffer;
  v7 = 69632;
  do
  {
    if ( v7 < 0x5000 )
      break;
    v5 = (char *)VirtualAlloc(0, v7, 0x1000u, 4u);
    v8 = v7 - 0x2000;
    if ( v5 )
      v8 = v7;
    v7 = v8;
  }
  while ( !v5 );
  if ( !v5 || !InputBuffer )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 11, 49);
    BufferSize = 14;
    goto LABEL_91;
  }
  memset_0(InputBuffer, 0, 0x80u);
  memset_0(v5, 0, v7);
  *(_DWORD *)v5 = 256;
  *(_QWORD *)(v5 + 4) = 0x530042004F0052LL;
  *((_DWORD *)v5 + 5) = 30;
  *((_QWORD *)v5 + 3) = 0x5300460054004ELL;
  *((_WORD *)v5 + 24) = 6416;
  *((_DWORD *)v5 + 11) = 2;
  LODWORD(Size) = 50;
  BufferSize = EfspSendPipeData(v5, 0x32u, a2);
  if ( !BufferSize )
  {
    memset_0(v5, 0, (unsigned int)Size);
    LODWORD(v67) = 1;
    *(_QWORD *)(v5 + 4) = 0x45005200550047LL;
    BufferSize = EfsFsctlGetBufferSize(&v67, (char *)&Size + 4);
    if ( BufferSize >= 0 )
    {
      v64 = (unsigned __int64)(v5 + 16);
      if ( HIDWORD(Size) != 16 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
      EfsFsctlPrepareData(
        3,
        0,
        (*(_DWORD *)(a1 + 4) & 0xFFFF8000) << 16,
        (unsigned int)&v67,
        (__int64)InputBuffer,
        (__int64)&Size + 4);
      v11 = *(void **)(a1 + 8);
      InputBufferLength = HIDWORD(Size);
      v12 = NtFsControlFile(v11, 0, 0, 0, &v66, 0x900DBu, InputBuffer, HIDWORD(Size), v5 + 16, v7 - 16);
      v13 = (unsigned int *)v5;
      v14 = v12;
      if ( v12 < 0 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v12, 11, 172);
        if ( v14 != -1073741789 )
        {
LABEL_23:
          BufferSize = RtlNtStatusToDosError(v14);
          goto LABEL_91;
        }
        if ( (unsigned int)(*(_DWORD *)v64 + 16) < *(_DWORD *)v64 )
          goto LABEL_90;
        if ( *(_DWORD *)v64 + 4112 < (unsigned int)(*(_DWORD *)v64 + 16) )
          goto LABEL_90;
        v7 = (*(_DWORD *)v64 + 4111) & 0xFFFFF000;
        if ( v7 < 0x5000 )
          goto LABEL_90;
        v15 = (unsigned int *)VirtualAlloc(0, v7, 0x1000u, 4u);
        v13 = v15;
        if ( !v15 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v7, 11, 219);
          BufferSize = 8;
          goto LABEL_91;
        }
        *(_OWORD *)v15 = *(_OWORD *)v5;
        VirtualFree(v5, 0, 0x8000u);
        v64 = (unsigned __int64)(v13 + 4);
        v16 = NtFsControlFile(
                *(HANDLE *)(v61 + 8),
                0,
                0,
                0,
                &v66,
                0x900DBu,
                InputBuffer,
                InputBufferLength,
                v13 + 4,
                v7 - 16);
        v14 = v16;
        v5 = (char *)v13;
        if ( v16 < 0 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v16, 11, 242);
          goto LABEL_23;
        }
      }
      v17 = *(_DWORD *)v64 + 16;
      if ( *(_DWORD *)v64 >= 0xFFFFFFF0 )
      {
        LODWORD(Size) = -1;
      }
      else
      {
        LODWORD(Size) = *(_DWORD *)v64 + 16;
        if ( v17 <= v7 )
        {
          v18 = v65;
          *v13 = v17;
          v58 = 1;
          v19 = EfspSendPipeData(v5, Size, v18);
          v20 = v61;
          v21 = 0;
          BufferSize = v19;
          HIDWORD(Size) = 0;
          ByteOffset.QuadPart = 0;
          if ( *(_DWORD *)(v61 + 16) )
          {
            InputBufferLength = 16;
            InputBuffer[2] = v7 - 4096;
            v22 = 1;
          }
          else
          {
            v22 = 0;
          }
          v56 = v22;
          while ( 1 )
          {
            if ( BufferSize || !v22 )
              goto LABEL_91;
            if ( ByteOffset.QuadPart > 0x7FFFFFFFFFFFFFFFuLL )
            {
              BufferSize = 5;
              *(_QWORD *)InputBuffer = -1;
              v52 = 5;
              IoStatusBlocka = 70;
              goto LABEL_86;
            }
            *(union _LARGE_INTEGER *)InputBuffer = ByteOffset;
            if ( !ByteOffset.QuadPart )
            {
              v23 = (unsigned int)v21;
              v24 = *(_QWORD *)(v20 + 24);
              v64 = v23;
              v14 = NtQueryInformationFile(
                      *(HANDLE *)(v24 + 8 * v23),
                      &v66,
                      FileInformation,
                      0x28u,
                      FileBasicInformation);
              if ( v14 < 0 )
              {
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v14, 11, 102);
                goto LABEL_23;
              }
              v58 = (v70 & 0x4000) != 0;
              v25 = 2 * v64;
              *((_DWORD *)v5 + 3) = (v70 & 0x4000) == 0;
              v26 = *(unsigned __int16 *)(*(_QWORD *)(v20 + 32) + 8 * v25);
              *((_DWORD *)v5 + 6) = v26;
              v26 += 28;
              *(_DWORD *)v5 = v26;
              LODWORD(Size) = v26;
              *(_QWORD *)(v5 + 4) = 0x5300460054004ELL;
              *((_QWORD *)v5 + 2) = 0;
              v27 = EfspEnsureSpaceInBuffer(v5, v7, v5 + 28, *(unsigned __int16 *)(*(_QWORD *)(v20 + 32) + 8 * v25));
              BufferSize = v27;
              if ( v27 )
              {
                IoStatusBlocka = -97;
LABEL_69:
                v52 = v27;
LABEL_86:
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v52, 11, IoStatusBlocka);
                goto LABEL_91;
              }
              memcpy_0(v5 + 28, *(const void **)(*(_QWORD *)(v20 + 32) + 8 * v29 + 8), v28);
              v27 = EfspSendPipeData(v5, Size, v65);
              BufferSize = v27;
              if ( v27 )
              {
                IoStatusBlocka = -78;
                goto LABEL_69;
              }
              v21 = HIDWORD(Size);
            }
            *((_DWORD *)v5 + 3) = 0;
            v30 = (unsigned __int64 *)(v5 + 16);
            OutputBufferLength = v7 - 16;
            *(_QWORD *)(v5 + 4) = 0x45005200550047LL;
            v32 = *(void **)(*(_QWORD *)(v20 + 24) + 8 * v21);
            if ( v58 )
            {
              v33 = NtFsControlFile(v32, 0, 0, 0, &v66, 0x900E3u, v59, InputBufferLength, v5 + 16, OutputBufferLength);
              v34 = v33;
              if ( (int)(v33 + 0x80000000) >= 0 && v33 != -1073741807 )
              {
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v33, 11, 252);
LABEL_73:
                BufferSize = RtlNtStatusToDosError(v34);
LABEL_84:
                InputBuffer = v59;
                goto LABEL_91;
              }
              if ( v33 != -1073741807 )
              {
                LODWORD(Size) = 16;
                v35 = EfspEnsureSpaceInBuffer(v5, v7, v5 + 16, *((_DWORD *)v5 + 6));
                BufferSize = v35;
                if ( v35 )
                {
                  IoStatusBlock = 20;
                  goto LABEL_82;
                }
                LODWORD(Size) = v36 + 16;
                if ( (int)ULongLongToULong(4LL * *((unsigned __int16 *)v5 + 21), &v63) < 0 )
                {
                  IoStatusBlock = 35;
                  goto LABEL_54;
                }
                v38 = v63 + 32;
                if ( v63 + 32 < v63 )
                {
                  IoStatusBlock = 41;
                  goto LABEL_54;
                }
                v63 += 32;
                if ( v38 > *((_DWORD *)v5 + 6) )
                {
                  IoStatusBlock = 47;
                  goto LABEL_54;
                }
                for ( i = 0; (unsigned int)i < *((unsigned __int16 *)v5 + 21); i = (unsigned int)(v42 + 1) )
                {
                  v35 = EfspEnsureSpaceInBuffer(v5, v7, &v5[v37], *((_DWORD *)v30 + i + 7));
                  BufferSize = v35;
                  if ( v35 )
                  {
                    IoStatusBlock = 67;
                    goto LABEL_82;
                  }
                  v37 = v40 + v41;
                  LODWORD(Size) = v37;
                }
                *(_DWORD *)v5 = v37;
                v43 = *((unsigned __int16 *)v5 + 21) << v5[38];
                if ( *((_DWORD *)v5 + 7) < v43 )
                  goto LABEL_64;
                v44 = *v30 + v43;
                if ( v44 < *v30 )
                {
                  IoStatusBlock = -127;
                  goto LABEL_53;
                }
LABEL_63:
                ByteOffset.QuadPart = v44;
                goto LABEL_65;
              }
            }
            else
            {
              v46 = NtReadFile(v32, 0, 0, 0, &v66, v5 + 16, OutputBufferLength, &ByteOffset, 0);
              v34 = v46;
              if ( v46 < 0 )
              {
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v46, 11, 152);
                if ( v34 != -1073741807 )
                  goto LABEL_73;
              }
              if ( v34 == 259 )
                __fastfail(7u);
              if ( v34 != -1073741807 )
              {
                LODWORD(Size) = 16;
                v35 = EfspEnsureSpaceInBuffer(v5, v7, v5 + 16, v66.Information);
                BufferSize = v35;
                if ( v35 )
                {
                  IoStatusBlock = -66;
                  goto LABEL_82;
                }
                LODWORD(Size) = v47 + 16;
                *(_DWORD *)v5 = v47 + 16;
                if ( v7 - 16 <= LODWORD(v66.Information) )
                {
                  v44 = ByteOffset.QuadPart + LODWORD(v66.Information);
                  if ( v44 < ByteOffset.QuadPart )
                  {
                    IoStatusBlock = -13;
LABEL_53:
                    ByteOffset.QuadPart = -1;
LABEL_54:
                    BufferSize = 5;
                    v45 = 5;
                    goto LABEL_83;
                  }
                  goto LABEL_63;
                }
              }
            }
LABEL_64:
            InputBuffer = v59;
            v21 = (unsigned int)(HIDWORD(Size) + 1);
            HIDWORD(Size) = v21;
            v48 = (unsigned int)v21 < *(_DWORD *)(v61 + 16);
            ByteOffset.QuadPart = 0;
            v22 = v48 ? v56 : 0;
            v56 = v22;
            BufferSize = 0;
            v3 = v34 == -1073741807;
            v20 = v61;
            if ( !v3 )
            {
LABEL_65:
              v35 = EfspEnsureSpaceInBuffer(v5, v7, v5, Size);
              BufferSize = v35;
              if ( v35 )
              {
                IoStatusBlock = 3;
LABEL_82:
                v45 = v35;
LABEL_83:
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v45, 11, IoStatusBlock);
                goto LABEL_84;
              }
              v51 = EfspSendPipeData(v49, v50, v65);
              InputBuffer = v59;
              BufferSize = v51;
              v21 = HIDWORD(Size);
              v20 = v61;
              v22 = v56;
              if ( v51 )
              {
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v51, 11, 11);
                v21 = HIDWORD(Size);
                v22 = v56;
              }
            }
          }
        }
      }
LABEL_90:
      BufferSize = 5;
    }
  }
LABEL_91:
  EfspSendPipeData((char *)&Size, 0, v65);
  if ( v5 )
    VirtualFree(v5, 0, 0x8000u);
  if ( InputBuffer )
    EfsFreeHeap(InputBuffer);
  return (unsigned int)BufferSize;
}

```

## disassembly

```asm
0x1800650bc  mov     [rsp-8+arg_10], rbx
0x1800650c1  push    rbp
0x1800650c2  push    rsi
0x1800650c3  push    rdi
0x1800650c4  push    r12
0x1800650c6  push    r13
0x1800650c8  push    r14
0x1800650ca  push    r15
0x1800650cc  lea     rbp, [rsp-27h]
0x1800650d1  sub     rsp, 0F0h
0x1800650d8  mov     rax, cs:__security_cookie
0x1800650df  xor     rax, rsp
0x1800650e2  mov     [rbp+57h+var_40], rax
0x1800650e6  xor     eax, eax
0x1800650e8  mov     [rbp+57h+var_B0], rcx
0x1800650ec  mov     rsi, rcx
0x1800650ef  mov     [rbp+57h+var_98], rdx
0x1800650f3  xor     ecx, ecx
0x1800650f5  mov     [rbp+57h+var_48], rax
0x1800650f9  xorps   xmm0, xmm0
0x1800650fc  mov     dword ptr [rbp+57h+Size+4], ecx
0x1800650ff  xorps   xmm1, xmm1
0x180065102  mov     dword ptr [rbp+57h+Size], ecx
0x180065105  cmp     dword ptr [rsi], 1
0x180065108  mov     rbx, rdx
0x18006510b  mov     edi, ecx
0x18006510d  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x180065111  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180065115  mov     [rbp+57h+var_A4], ecx
0x180065118  movups  [rbp+57h+FileInformation], xmm1
0x18006511c  mov     [rbp+57h+var_70], rax
0x180065120  movups  [rbp+57h+var_58], xmm1
0x180065124  movups  [rbp+57h+var_80], xmm0
0x180065128  jnz     loc_180065992
0x18006512e  test    byte ptr [rsi+4], 3
0x180065132  jnz     loc_180065992
0x180065138  mov     r14d, 80h
0x18006513e  mov     ecx, r14d; unsigned __int64
0x180065141  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180065146  mov     r12, rax
0x180065149  mov     [rbp+57h+var_C0], rax
0x18006514d  mov     r15d, 11000h
0x180065153  cmp     r15d, 5000h
0x18006515a  jb      short loc_180065187
0x18006515c  xor     ecx, ecx; lpAddress
0x18006515e  mov     edx, r15d; dwSize
0x180065161  mov     r8d, 1000h; flAllocationType
0x180065167  lea     r9d, [rcx+4]; flProtect
0x18006516b  call    cs:__imp_VirtualAlloc
0x180065171  mov     rdi, rax
0x180065174  lea     eax, [r15-2000h]
0x18006517b  test    rdi, rdi
0x18006517e  cmovnz  eax, r15d
0x180065182  mov     r15d, eax
0x180065185  jz      short loc_180065153
0x180065187  test    rdi, rdi
0x18006518a  jz      loc_180065966
0x180065190  test    r12, r12
0x180065193  jz      loc_180065966
0x180065199  mov     r8, r14; Size
0x18006519c  xor     edx, edx; Val
0x18006519e  mov     rcx, r12; void *
0x1800651a1  call    memset_0
0x1800651a6  mov     r8d, r15d; Size
0x1800651a9  xor     edx, edx; Val
0x1800651ab  mov     rcx, rdi; void *
0x1800651ae  call    memset_0
0x1800651b3  mov     dword ptr [rdi], 100h
0x1800651b9  lea     rdx, [rdi+30h]
0x1800651bd  mov     rax, 530042004F0052h
0x1800651c7  mov     r8, rbx; void *
0x1800651ca  mov     [rdi+4], rax
0x1800651ce  mov     rcx, rdi; char *
0x1800651d1  mov     dword ptr [rdi+14h], 1Eh
0x1800651d8  mov     rax, 5300460054004Eh
0x1800651e2  mov     [rdi+18h], rax
0x1800651e6  mov     word ptr [rdx], 1910h
0x1800651eb  sub     edx, edi
0x1800651ed  add     edx, 2; unsigned int
0x1800651f0  mov     dword ptr [rdi+2Ch], 2
0x1800651f7  mov     dword ptr [rbp+57h+Size], edx
0x1800651fa  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x1800651ff  mov     ebx, eax
0x180065201  test    eax, eax
0x180065203  jnz     loc_18006599A
0x180065209  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18006520d  xor     edx, edx; Val
0x18006520f  mov     rcx, rdi; void *
0x180065212  call    memset_0
0x180065217  mov     rax, 45005200550047h
0x180065221  mov     dword ptr [rbp+57h+var_80], 1
0x180065228  lea     rdx, [rbp+57h+Size+4]
0x18006522c  mov     [rdi+4], rax
0x180065230  lea     rcx, [rbp+57h+var_80]
0x180065234  call    EfsFsctlGetBufferSize
0x180065239  mov     ebx, eax
0x18006523b  test    eax, eax
0x18006523d  js      loc_18006599A
0x180065243  cmp     dword ptr [rbp+57h+Size+4], 10h
0x180065247  lea     rbx, [rdi+10h]
0x18006524b  mov     [rbp+57h+var_A0], rbx
0x18006524f  jz      short loc_180065256
0x180065251  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FsctlInputLength == CB_EFS_FSCTL_PREFIX")
0x180065256  mov     r8d, [rsi+4]
0x18006525a  lea     rax, [rbp+57h+Size+4]
0x18006525e  xor     edx, edx
0x180065260  mov     qword ptr [rsp+120h+FsControlCode], rax
0x180065265  and     r8d, 0FFFF8000h
0x18006526c  mov     [rsp+120h+IoStatusBlock], r12
0x180065271  shl     r8d, 10h
0x180065275  lea     r9, [rbp+57h+var_80]
0x180065279  lea     ecx, [rdx+3]
0x18006527c  call    EfsFsctlPrepareData
0x180065281  mov     rcx, [rsi+8]; FileHandle
0x180065285  lea     eax, [r15-10h]
0x180065289  mov     [rsp+120h+OutputBufferLength], eax; OutputBufferLength
0x18006528d  xor     r9d, r9d; ApcContext
0x180065290  mov     eax, dword ptr [rbp+57h+Size+4]
0x180065293  xor     r8d, r8d; ApcRoutine
0x180065296  mov     [rsp+120h+OutputBuffer], rbx; OutputBuffer
0x18006529b  xor     edx, edx; Event
0x18006529d  mov     [rsp+120h+InputBufferLength], eax; InputBufferLength
0x1800652a1  mov     [rbp+57h+var_A8], eax
0x1800652a4  lea     rax, [rbp+57h+var_90]
0x1800652a8  mov     [rsp+120h+InputBuffer], r12; InputBuffer
0x1800652ad  mov     [rsp+120h+FsControlCode], 900DBh; FsControlCode
0x1800652b5  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x1800652ba  call    cs:__imp_NtFsControlFile
0x1800652c0  mov     r13, rdi
0x1800652c3  lea     r14, EFS_API_ERROR
0x1800652ca  mov     ebx, eax
0x1800652cc  mov     esi, 0Bh
0x1800652d1  test    eax, eax
0x1800652d3  jns     loc_180065419
0x1800652d9  mov     rcx, cs:g_hPublisher
0x1800652e0  mov     r9d, esi
0x1800652e3  mov     r8d, eax
0x1800652e6  mov     dword ptr [rsp+120h+IoStatusBlock], 3ACh
0x1800652ee  mov     rdx, r14
0x1800652f1  call    fnEfsLogTrace1
0x1800652f6  cmp     ebx, 0C0000023h
0x1800652fc  jnz     loc_18006540A
0x180065302  mov     rax, [rbp+57h+var_A0]
0x180065306  mov     eax, [rax]
0x180065308  lea     ecx, [rax+10h]
0x18006530b  cmp     ecx, eax
0x18006530d  jb      loc_180065995
0x180065313  lea     r15d, [rcx+1000h]
0x18006531a  cmp     r15d, ecx
0x18006531d  jb      loc_180065995
0x180065323  dec     r15d
0x180065326  and     r15d, 0FFFFF000h
0x18006532d  cmp     r15d, 5000h
0x180065334  jb      loc_180065995
0x18006533a  mov     edx, r15d; dwSize
0x18006533d  lea     r9d, [rsi-7]; flProtect
0x180065341  xor     ecx, ecx; lpAddress
0x180065343  mov     r8d, 1000h; flAllocationType
0x180065349  call    cs:__imp_VirtualAlloc
0x18006534f  mov     r13, rax
0x180065352  test    rax, rax
0x180065355  jnz     short loc_180065380
0x180065357  mov     rcx, cs:g_hPublisher
0x18006535e  lea     rdx, EFS_ERROR_MEMORY
0x180065365  mov     r9d, esi
0x180065368  mov     dword ptr [rsp+120h+IoStatusBlock], 3DBh
0x180065370  mov     r8d, r15d
0x180065373  call    fnEfsLogTrace1
0x180065378  lea     ebx, [rsi-3]
0x18006537b  jmp     loc_18006599A
0x180065380  movups  xmm0, xmmword ptr [rdi]
0x180065383  xor     edx, edx; dwSize
0x180065385  mov     r8d, 8000h; dwFreeType
0x18006538b  mov     rcx, rdi; lpAddress
0x18006538e  movdqu  xmmword ptr [rax], xmm0
0x180065392  call    cs:__imp_VirtualFree
0x180065398  mov     r10, [rbp+57h+var_B0]
0x18006539c  lea     eax, [r15-10h]
0x1800653a0  mov     [rsp+120h+OutputBufferLength], eax; OutputBufferLength
0x1800653a4  lea     rcx, [r13+10h]
0x1800653a8  mov     eax, [rbp+57h+var_A8]
0x1800653ab  xor     r9d, r9d; ApcContext
0x1800653ae  mov     [rsp+120h+OutputBuffer], rcx; OutputBuffer
0x1800653b3  xor     r8d, r8d; ApcRoutine
0x1800653b6  mov     [rsp+120h+InputBufferLength], eax; InputBufferLength
0x1800653ba  xor     edx, edx; Event
0x1800653bc  mov     [rsp+120h+InputBuffer], r12; InputBuffer
0x1800653c1  lea     rax, [rbp+57h+var_90]
0x1800653c5  mov     [rbp+57h+var_A0], r13
0x1800653c9  mov     [rbp+57h+var_A0], rcx
0x1800653cd  mov     rcx, [r10+8]; FileHandle
0x1800653d1  mov     [rsp+120h+FsControlCode], 900DBh; FsControlCode
0x1800653d9  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x1800653de  call    cs:__imp_NtFsControlFile
0x1800653e4  mov     ebx, eax
0x1800653e6  mov     rdi, r13
0x1800653e9  test    eax, eax
0x1800653eb  jns     short loc_180065419
0x1800653ed  mov     dword ptr [rsp+120h+IoStatusBlock], 3F2h
0x1800653f5  mov     r8d, eax
0x1800653f8  mov     rcx, cs:g_hPublisher
0x1800653ff  mov     r9d, esi
0x180065402  mov     rdx, r14
0x180065405  call    fnEfsLogTrace1
0x18006540a  mov     ecx, ebx; Status
0x18006540c  call    cs:__imp_RtlNtStatusToDosError
0x180065412  mov     ebx, eax
0x180065414  jmp     loc_18006599A
0x180065419  mov     rax, [rbp+57h+var_A0]
0x18006541d  mov     eax, [rax]
0x18006541f  add     eax, 10h
0x180065422  cmp     eax, 10h
0x180065425  jb      loc_18006595D
0x18006542b  mov     dword ptr [rbp+57h+Size], eax
0x18006542e  cmp     eax, r15d
0x180065431  ja      loc_180065995
0x180065437  mov     r8, [rbp+57h+var_98]; void *
0x18006543b  mov     rcx, rdi; char *
0x18006543e  mov     [r13+0], eax
0x180065442  mov     edx, dword ptr [rbp+57h+Size]; unsigned int
0x180065445  mov     [rbp+57h+var_C4], 1
0x180065449  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x18006544e  mov     r13, [rbp+57h+var_B0]
0x180065452  xor     ecx, ecx
0x180065454  mov     ebx, eax
0x180065456  mov     dword ptr [rbp+57h+Size+4], ecx
0x180065459  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x18006545d  cmp     [r13+10h], ecx
0x180065461  jnz     short loc_180065467
0x180065463  xor     dl, dl
0x180065465  jmp     short loc_18006547C
0x180065467  lea     eax, [r15-1000h]
0x18006546e  mov     [rbp+57h+var_A8], 10h
0x180065475  mov     [r12+8], eax
0x18006547a  mov     dl, 1
0x18006547c  mov     [rbp+57h+var_D0], dl
0x18006547f  test    ebx, ebx
0x180065481  jnz     loc_18006599A
0x180065487  test    dl, dl
0x180065489  jz      loc_18006599A
0x18006548f  mov     rax, qword ptr [rbp+57h+ByteOffset]
0x180065493  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18006549d  cmp     rax, rdx
0x1800654a0  ja      loc_180065931
0x1800654a6  mov     [r12], rax
0x1800654aa  cmp     qword ptr [rbp+57h+ByteOffset], 0
0x1800654af  jnz     loc_180065585
0x1800654b5  mov     eax, ecx
0x1800654b7  lea     r9d, [rbx+28h]; Length
0x1800654bb  mov     rcx, [r13+18h]
0x1800654bf  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800654c3  lea     rdx, [rbp+57h+var_90]; IoStatusBlock
0x1800654c7  mov     [rbp+57h+var_A0], rax
0x1800654cb  mov     dword ptr [rsp+120h+IoStatusBlock], 4; FileInformationClass
0x1800654d3  mov     rcx, [rcx+rax*8]; FileHandle
0x1800654d7  call    cs:__imp_NtQueryInformationFile
0x1800654dd  mov     ebx, eax
0x1800654df  test    eax, eax
0x1800654e1  js      loc_180065882
0x1800654e7  test    dword ptr [rbp+57h+var_48], 4000h
0x1800654ee  lea     r8, [rdi+1Ch]; void *
0x1800654f2  mov     r10, [rbp+57h+var_A0]
0x1800654f6  mov     edx, r15d; unsigned int
0x1800654f9  setnz   [rbp+57h+var_C4]
0x1800654fd  xor     eax, eax
0x1800654ff  test    dword ptr [rbp+57h+var_48], 4000h
0x180065506  setz    al
0x180065509  add     r10, r10
0x18006550c  mov     [rdi+0Ch], eax
0x18006550f  mov     rax, [r13+20h]
0x180065513  movzx   ecx, word ptr [rax+r10*8]
0x180065518  mov     rax, 5300460054004Eh
0x180065522  mov     [rdi+18h], ecx
0x180065525  add     ecx, 1Ch
0x180065528  mov     [rdi], ecx
0x18006552a  mov     dword ptr [rbp+57h+Size], ecx
0x18006552d  mov     rcx, rdi; void *
0x180065530  mov     [rdi+4], rax
0x180065534  mov     qword ptr [rdi+10h], 0
0x18006553c  mov     rax, [r13+20h]
0x180065540  movzx   r9d, word ptr [rax+r10*8]; unsigned int
0x180065545  call    ?EfspEnsureSpaceInBuffer@@YAKPEBXKPEAXK@Z; EfspEnsureSpaceInBuffer(void const *,ulong,void *,ulong)
0x18006554a  mov     ebx, eax
0x18006554c  test    eax, eax
0x18006554e  jnz     loc_180065878
0x180065554  mov     rdx, [r13+20h]
0x180065558  lea     rcx, [rdi+1Ch]; void *
0x18006555c  mov     r8d, r9d; Size
0x18006555f  mov     rdx, [rdx+r10*8+8]; Src
0x180065564  call    memcpy_0
0x180065569  mov     r8, [rbp+57h+var_98]; void *
0x18006556d  mov     rcx, rdi; char *
0x180065570  mov     edx, dword ptr [rbp+57h+Size]; unsigned int
0x180065573  call    ?EfspSendPipeData@@YAKPEADKPEAX@Z; EfspSendPipeData(char *,ulong,void *)
0x180065578  mov     ebx, eax
0x18006557a  test    eax, eax
0x18006557c  jnz     loc_180065868
0x180065582  mov     ecx, dword ptr [rbp+57h+Size+4]
0x180065585  mov     dword ptr [rdi+0Ch], 0
0x18006558c  lea     r12, [rdi+10h]
  ... truncated ...
```
