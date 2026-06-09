# SecMessage

- ea: `0x140021ca0`
- end: `0x1400222d0`
- name: `SecMessage`
- size: `1584`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x1400067a4`
- `0x140006b6c`
- `0x140009b50`
- `0x140009b80`
- `0x14000add8`
- `0x14001038f`
- `0x140011590`
- `0x140011650`
- `0x140011700`
- `0x1400119c0`
- `0x140021a64`
- `0x140021ca0`
- `0x1400223a4`
- `0x140022468`
- `0x140022574`
- `0x140022aa4`
- `0x140022c2c`
- `0x140022d2c`
- `0x140022d5c`
- `0x140022dc0`
- `0x140022e20`
- `0x140022e88`
- `0x140022f00`
- `0x140022fe4`
- `0x14002314c`
- `0x140023224`
- `0x14002c6b0`
- `0x140039c1c`
- `0x140039e84`
- `0x14003bcb4`
- `0x14003c40c`
- `0x140044140`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140021f6d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140021f6d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140021f22`
- `ntoskrnl!IoGetCurrentProcess` at `0x140021f5e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140021f22`
- `ntoskrnl!IoGetCurrentProcess` at `0x140021f5e`
- `ntoskrnl!ProbeForWrite` at `0x140021e31`
- `ntoskrnl!ProbeForWrite` at `0x140021e74`
- `ntoskrnl!ProbeForWrite` at `0x140021e31`
- `ntoskrnl!ProbeForWrite` at `0x140021e74`
- `ntoskrnl!ProbeForRead` at `0x140021e17`
- `ntoskrnl!ProbeForRead` at `0x140021e17`

## pseudocode

```c
__int64 __fastcall SecMessage(
        PVOID PortCookie,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  SIZE_T v7; // r14
  _DWORD *PagedPoolQuata; // rdi
  unsigned int *v10; // rsi
  int ProcessStartKey; // ebx
  char v12; // al
  PVOID v13; // r13
  int v14; // eax
  struct _KPROCESS *CurrentProcess; // rax
  PEPROCESS v16; // rbx
  HANDLE CurrentProcessId; // rax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int CiInformationForFile; // eax
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  char v39; // al
  PSLIST_ENTRY ListEntry; // [rsp+70h] [rbp-3A8h] BYREF
  __int64 v44; // [rsp+78h] [rbp-3A0h]
  _BYTE v45[176]; // [rsp+80h] [rbp-398h] BYREF
  _BYTE v46[672]; // [rsp+130h] [rbp-2E8h] BYREF

  v7 = InputBufferLength;
  PagedPoolQuata = 0;
  v10 = 0;
  memset(v46, 0, 0x298u);
  memset(v45, 0, 0xA8u);
  ListEntry = 0;
  v44 = 0;
  if ( FltIs32bitProcess_0(0) )
  {
    ProcessStartKey = -1073741637;
    goto LABEL_95;
  }
  *ReturnOutputBufferLength = 0;
  if ( (unsigned int)v7 < 0x10 || OutputBufferLength < 0x10 )
    goto LABEL_94;
  if ( !InputBuffer || !OutputBuffer )
  {
    ProcessStartKey = -1073741811;
    goto LABEL_95;
  }
  if ( (unsigned int)v7 <= 0x298 )
  {
    PagedPoolQuata = v46;
  }
  else
  {
    _mm_lfence();
    PagedPoolQuata = (_DWORD *)SecAllocatePagedPoolQuata(v7, 1919312723);
    if ( !PagedPoolQuata )
    {
LABEL_9:
      ProcessStartKey = -1073741670;
      goto LABEL_95;
    }
  }
  if ( OutputBufferLength <= 0xA8 )
  {
    v10 = (unsigned int *)v45;
  }
  else
  {
    _mm_lfence();
    v10 = (unsigned int *)SecAllocatePagedPoolQuata(OutputBufferLength, 1919312723);
    if ( !v10 )
      goto LABEL_9;
  }
  v12 = BYTE8(xmmword_14001B740);
  _mm_lfence();
  if ( (v12 & 0x20) != 0 )
  {
    ProbeForRead(InputBuffer, v7, 1u);
    v13 = OutputBuffer;
    ProbeForWrite(OutputBuffer, OutputBufferLength, 1u);
    memmove(PagedPoolQuata, InputBuffer, v7);
  }
  else
  {
    _mm_lfence();
    RtlCopyFromUser(PagedPoolQuata, InputBuffer, v7);
    v13 = OutputBuffer;
    ProbeForWrite(OutputBuffer, OutputBufferLength, 1u);
  }
  v14 = PagedPoolQuata[3];
  if ( v14 != 1 && *PagedPoolQuata != 66 )
  {
    ProcessStartKey = -1073741735;
    goto LABEL_95;
  }
  if ( (unsigned int)(v14 - 1) > 0x1D )
  {
    ProcessStartKey = -1073741808;
    goto LABEL_95;
  }
  if ( PagedPoolQuata[2] != (_DWORD)v7
    || (_mm_lfence(), (unsigned int)v7 < (unsigned __int16)FunctionInputBufferLength[PagedPoolQuata[3]]) )
  {
LABEL_94:
    ProcessStartKey = -1073741306;
    goto LABEL_95;
  }
  _mm_lfence();
  if ( OutputBufferLength < (unsigned __int16)FunctionMinimumOutputBufferLength[PagedPoolQuata[3]] )
  {
    ProcessStartKey = -1073741789;
    goto LABEL_95;
  }
  *v10 = 66;
  v10[1] = 1;
  v10[2] = OutputBufferLength;
  CurrentProcess = IoGetCurrentProcess();
  ProcessStartKey = SecGetProcessStartKey(CurrentProcess);
  if ( ProcessStartKey >= 0 )
  {
    ProcessStartKey = SecGetProcessContextByStartkey(v44, &ListEntry);
    if ( ProcessStartKey < 0 )
    {
      v16 = IoGetCurrentProcess();
      CurrentProcessId = PsGetCurrentProcessId();
      ProcessStartKey = SecCreateProcessContext(CurrentProcessId, v16, 0, &ListEntry);
    }
    if ( ProcessStartKey >= 0 )
    {
      if ( PagedPoolQuata[3] != 9 && (HIDWORD(ListEntry[38].Next) & 0x10) == 0 )
      {
        ProcessStartKey = -1073741790;
        goto LABEL_95;
      }
      v18 = PagedPoolQuata[3];
      if ( v18 > 15 )
      {
        if ( v18 > 25 )
        {
          v35 = v18 - 26;
          if ( !v35 )
          {
            _mm_lfence();
            CiInformationForFile = SecOpenFileAndRequestOplockRequest(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v36 = v35 - 1;
          if ( !v36 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetDriverLmfNetworkShareConfiguration(PagedPoolQuata);
            goto LABEL_84;
          }
          v37 = v36 - 1;
          if ( !v37 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetDriverLmfSysvolAccessConfiguration(PagedPoolQuata);
            goto LABEL_84;
          }
          v38 = v37 - 1;
          if ( !v38 )
          {
            _mm_lfence();
            CiInformationForFile = SecWriteExtendedFileHashEA(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          if ( v38 == 1 )
          {
            _mm_lfence();
            CiInformationForFile = SecWriteFileMarkOfTheWebEA(PagedPoolQuata, v10);
            goto LABEL_84;
          }
        }
        else
        {
          if ( v18 == 25 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetDriverLmfConfiguration(PagedPoolQuata);
            goto LABEL_84;
          }
          v30 = v18 - 16;
          if ( !v30 )
          {
            _mm_lfence();
            CiInformationForFile = SecGetCiInformationForFile(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v31 = v30 - 1;
          if ( !v31 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetDriverDlpConfiguration(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v32 = v31 - 4;
          if ( !v32 || (v33 = v32 - 1) == 0 || (v34 = v33 - 1) == 0 )
          {
            ProcessStartKey = -1073741808;
            goto LABEL_86;
          }
          if ( v34 == 1 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetCiInformationForFile(PagedPoolQuata);
            goto LABEL_84;
          }
        }
      }
      else
      {
        if ( v18 == 15 )
        {
          _mm_lfence();
          CiInformationForFile = SecRequestOplockOnFileRequest(PagedPoolQuata, v10);
          goto LABEL_84;
        }
        if ( v18 > 7 )
        {
          v25 = v18 - 9;
          if ( !v25 )
          {
            _mm_lfence();
            CiInformationForFile = SecRegisterConsumer(ListEntry, PagedPoolQuata);
            goto LABEL_84;
          }
          v26 = v25 - 1;
          if ( !v26 )
          {
            _mm_lfence();
            CiInformationForFile = SecUnregisterConsumer(ListEntry, PagedPoolQuata);
            goto LABEL_84;
          }
          v27 = v26 - 1;
          if ( !v27 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetDriverConfiguration(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v28 = v27 - 1;
          if ( !v28 )
          {
            _mm_lfence();
            CiInformationForFile = SecWriteFileHashEA(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v29 = v28 - 1;
          if ( !v29 )
          {
            _mm_lfence();
            CiInformationForFile = SecWriteFileDlpEA(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          if ( v29 == 1 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetFileMonitorData(ListEntry, PagedPoolQuata);
            goto LABEL_84;
          }
        }
        else
        {
          if ( v18 == 7 )
          {
            _mm_lfence();
            CiInformationForFile = SecQueryProcessData(PagedPoolQuata, v10);
            goto LABEL_84;
          }
          v19 = v18 - 1;
          if ( !v19 )
          {
            v10[4] = 66;
            v10[5] = 1;
            goto LABEL_85;
          }
          v20 = v19 - 1;
          if ( !v20 || (v21 = v20 - 1) == 0 )
          {
LABEL_85:
            if ( ProcessStartKey >= 0 )
            {
LABEL_88:
              v39 = BYTE8(xmmword_14001B740);
              _mm_lfence();
              if ( (v39 & 0x20) != 0 )
                memmove(v13, v10, v10[2]);
              else
                RtlCopyToUser(v13, v10, OutputBufferLength);
              *ReturnOutputBufferLength = v10[2];
              goto LABEL_95;
            }
LABEL_86:
            if ( PagedPoolQuata[3] != 7 || ProcessStartKey != -1073741801 )
              goto LABEL_95;
            goto LABEL_88;
          }
          v22 = v21 - 1;
          if ( !v22 )
          {
            _mm_lfence();
            CiInformationForFile = SecSetRegistryData(ListEntry, PagedPoolQuata);
            goto LABEL_84;
          }
          v23 = v22 - 1;
          if ( !v23 )
            goto LABEL_85;
          if ( v23 == 1 )
          {
            _mm_lfence();
            CiInformationForFile = SecQueryFileHash(PagedPoolQuata, v10);
LABEL_84:
            ProcessStartKey = CiInformationForFile;
            goto LABEL_85;
          }
        }
      }
      ProcessStartKey = -1073741808;
      goto LABEL_85;
    }
  }
LABEL_95:
  if ( PagedPoolQuata && PagedPoolQuata != (_DWORD *)v46 )
    SecFreePool(PagedPoolQuata, 0x72666353u);
  if ( v10 && v10 != (unsigned int *)v45 )
    SecFreePool(v10, 0x72666353u);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  return (unsigned int)ProcessStartKey;
}

```

## disassembly

```asm
0x140021ca0  push    rbx
0x140021ca2  push    rsi
0x140021ca3  push    rdi
0x140021ca4  push    r12
0x140021ca6  push    r13
0x140021ca8  push    r14
0x140021caa  push    r15
0x140021cac  sub     rsp, 3E0h
0x140021cb3  mov     rax, cs:__security_cookie
0x140021cba  xor     rax, rsp
0x140021cbd  mov     [rsp+418h+var_48], rax
0x140021cc5  mov     r13, r9
0x140021cc8  mov     [rsp+418h+var_3B8], r9
0x140021ccd  mov     r14d, r8d
0x140021cd0  mov     r15, rdx
0x140021cd3  mov     [rsp+418h+Address], rdx
0x140021cd8  mov     [rsp+418h+var_3F8], r14d
0x140021cdd  mov     [rsp+418h+var_3B0], r9
0x140021ce2  mov     r12d, dword ptr [rsp+418h+Length]
0x140021cea  mov     [rsp+418h+var_3E0], r12d
0x140021cef  mov     dword ptr [rsp+418h+Size], r12d
0x140021cf4  mov     rax, [rsp+418h+ReturnOutputBufferLength]
0x140021cfc  mov     [rsp+418h+var_3E8], rax
0x140021d01  xor     ebx, ebx
0x140021d03  xor     eax, eax
0x140021d05  mov     [rsp+418h+var_3F0], eax
0x140021d09  xor     edi, edi
0x140021d0b  xor     esi, esi
0x140021d0d  xor     edx, edx; Val
0x140021d0f  mov     r8d, 298h; Size
0x140021d15  lea     rcx, [rsp+418h+var_2E8]; void *
0x140021d1d  call    memset
0x140021d22  xor     edx, edx; Val
0x140021d24  mov     r8d, 0A8h; Size
0x140021d2a  lea     rcx, [rsp+418h+var_398]; void *
0x140021d32  call    memset
0x140021d37  mov     [rsp+418h+ListEntry], rbx
0x140021d3c  mov     [rsp+418h+var_3A0], rbx
0x140021d41  xor     ecx, ecx; CallbackData
0x140021d43  call    FltIs32bitProcess_0
0x140021d48  test    al, al
0x140021d4a  jz      short loc_140021D56
0x140021d4c  mov     ebx, 0C00000BBh
0x140021d51  jmp     loc_14002225D
0x140021d56  mov     rax, [rsp+418h+var_3E8]
0x140021d5b  mov     [rax], ebx
0x140021d5d  cmp     r14d, 10h
0x140021d61  jb      loc_140022258
0x140021d67  cmp     r12d, 10h
0x140021d6b  jb      loc_140022258
0x140021d71  test    r15, r15
0x140021d74  jz      loc_140022251
0x140021d7a  test    r13, r13
0x140021d7d  jz      loc_140022251
0x140021d83  cmp     r14d, 298h
0x140021d8a  jbe     short loc_140021DB3
0x140021d8c  lfence
0x140021d8f  mov     rcx, r14
0x140021d92  mov     edx, 72666353h
0x140021d97  call    SecAllocatePagedPoolQuata
0x140021d9c  mov     rdi, rax
0x140021d9f  mov     [rsp+418h+var_3D0], rax
0x140021da4  test    rax, rax
0x140021da7  jnz     short loc_140021DC0
0x140021da9  mov     ebx, 0C000009Ah
0x140021dae  jmp     loc_14002225D
0x140021db3  lea     rdi, [rsp+418h+var_2E8]
0x140021dbb  mov     [rsp+418h+var_3D0], rdi
0x140021dc0  cmp     r12d, 0A8h
0x140021dc7  jbe     short loc_140021DE8
0x140021dc9  lfence
0x140021dcc  mov     edx, 72666353h
0x140021dd1  mov     rcx, r12
0x140021dd4  call    SecAllocatePagedPoolQuata
0x140021dd9  mov     rsi, rax
0x140021ddc  mov     [rsp+418h+var_3C8], rax
0x140021de1  test    rax, rax
0x140021de4  jnz     short loc_140021DF5
0x140021de6  jmp     short loc_140021DA9
0x140021de8  lea     rsi, [rsp+418h+var_398]
0x140021df0  mov     [rsp+418h+var_3C8], rsi
0x140021df5  mov     rcx, r14
0x140021df8  mov     rax, qword ptr cs:xmmword_14001B740+8
0x140021dff  lfence
0x140021e02  test    al, 20h
0x140021e04  jz      short loc_140021E4F
0x140021e06  mov     r15d, 1
0x140021e0c  mov     r8d, r15d; Alignment
0x140021e0f  mov     rdx, rcx; Length
0x140021e12  mov     rcx, [rsp+418h+Address]; Address
0x140021e17  call    cs:__imp_ProbeForRead
0x140021e1e  nop     dword ptr [rax+rax+00h]
0x140021e23  mov     r8d, r15d; Alignment
0x140021e26  mov     rdx, r12; Length
0x140021e29  mov     r13, [rsp+418h+var_3B8]
0x140021e2e  mov     rcx, r13; Address
0x140021e31  call    cs:__imp_ProbeForWrite
0x140021e38  nop     dword ptr [rax+rax+00h]
0x140021e3d  mov     r8, r14; Size
0x140021e40  mov     rdx, [rsp+418h+Address]; Src
0x140021e45  mov     rcx, rdi; void *
0x140021e48  call    memmove
0x140021e4d  jmp     short loc_140021E80
0x140021e4f  lfence
0x140021e52  mov     r8, rcx; Size
0x140021e55  mov     rdx, r15; Src
0x140021e58  mov     rcx, rdi; void *
0x140021e5b  call    RtlCopyFromUser
0x140021e60  mov     r15d, 1
0x140021e66  mov     r8d, r15d; Alignment
0x140021e69  mov     rdx, r12; Length
0x140021e6c  mov     r13, [rsp+418h+var_3B8]
0x140021e71  mov     rcx, r13; Address
0x140021e74  call    cs:__imp_ProbeForWrite
0x140021e7b  nop     dword ptr [rax+rax+00h]
0x140021e80  jmp     short loc_140021EA3
0x140021e82  mov     ebx, eax
0x140021e84  mov     r15d, 1
0x140021e8a  mov     rdi, [rsp+418h+var_3D0]
0x140021e8f  mov     rsi, [rsp+418h+var_3C8]
0x140021e94  mov     r14d, [rsp+418h+var_3F8]
0x140021e99  mov     r13, [rsp+418h+var_3B0]
0x140021e9e  mov     r12d, [rsp+418h+var_3E0]
0x140021ea3  test    ebx, ebx
0x140021ea5  js      loc_14002225D
0x140021eab  mov     eax, [rdi+0Ch]
0x140021eae  cmp     eax, r15d
0x140021eb1  jz      short loc_140021EC2
0x140021eb3  cmp     dword ptr [rdi], 42h ; 'B'
0x140021eb6  jz      short loc_140021EC2
0x140021eb8  mov     ebx, 0C0000059h
0x140021ebd  jmp     loc_14002225D
0x140021ec2  dec     eax
0x140021ec4  cmp     eax, 1Dh
0x140021ec7  ja      loc_14002224A
0x140021ecd  cmp     [rdi+8], r14d
0x140021ed1  jnz     loc_140022258
0x140021ed7  lfence
0x140021eda  movsxd  rax, dword ptr [rdi+0Ch]
0x140021ede  lea     rcx, cs:140000000h
0x140021ee5  movzx   eax, rva FunctionInputBufferLength[rcx+rax*2]
0x140021eed  cmp     r14d, eax
0x140021ef0  jb      loc_140022258
0x140021ef6  lfence
0x140021ef9  movsxd  rax, dword ptr [rdi+0Ch]
0x140021efd  movzx   eax, rva FunctionMinimumOutputBufferLength[rcx+rax*2]
0x140021f05  cmp     r12d, eax
0x140021f08  jnb     short loc_140021F14
0x140021f0a  mov     ebx, 0C0000023h
0x140021f0f  jmp     loc_14002225D
0x140021f14  mov     dword ptr [rsi], 42h ; 'B'
0x140021f1a  mov     [rsi+4], r15d
0x140021f1e  mov     [rsi+8], r12d
0x140021f22  call    cs:__imp_IoGetCurrentProcess
0x140021f29  nop     dword ptr [rax+rax+00h]
0x140021f2e  mov     rcx, rax; Process
0x140021f31  lea     rdx, [rsp+418h+var_3A0]
0x140021f36  call    SecGetProcessStartKey
0x140021f3b  mov     ebx, eax
0x140021f3d  test    eax, eax
0x140021f3f  js      loc_14002225D
0x140021f45  lea     rdx, [rsp+418h+ListEntry]
0x140021f4a  mov     rcx, [rsp+418h+var_3A0]
0x140021f4f  call    SecGetProcessContextByStartkey
0x140021f54  mov     ebx, eax
0x140021f56  mov     [rsp+418h+var_3F8], eax
0x140021f5a  test    eax, eax
0x140021f5c  jns     short loc_140021F92
0x140021f5e  call    cs:__imp_IoGetCurrentProcess
0x140021f65  nop     dword ptr [rax+rax+00h]
0x140021f6a  mov     rbx, rax
0x140021f6d  call    cs:__imp_PsGetCurrentProcessId
0x140021f74  nop     dword ptr [rax+rax+00h]
0x140021f79  mov     rcx, rax
0x140021f7c  lea     r9, [rsp+418h+ListEntry]
0x140021f81  xor     r8d, r8d
0x140021f84  mov     rdx, rbx
0x140021f87  call    SecCreateProcessContext
0x140021f8c  mov     ebx, eax
0x140021f8e  mov     [rsp+418h+var_3F8], eax
0x140021f92  test    ebx, ebx
0x140021f94  js      loc_14002225D
0x140021f9a  cmp     dword ptr [rdi+0Ch], 9
0x140021f9e  jz      short loc_140021FBA
0x140021fa0  mov     rax, [rsp+418h+ListEntry]
0x140021fa5  mov     ecx, [rax+264h]
0x140021fab  test    cl, 10h
0x140021fae  jnz     short loc_140021FBA
0x140021fb0  mov     ebx, 0C0000022h
0x140021fb5  jmp     loc_14002225D
0x140021fba  mov     ecx, [rdi+0Ch]
0x140021fbd  cmp     ecx, 0Fh
0x140021fc0  jg      loc_1400220FD
0x140021fc6  jz      loc_1400220EA
0x140021fcc  cmp     ecx, 7
0x140021fcf  jg      short loc_14002204C
0x140021fd1  jz      short loc_140022039
0x140021fd3  sub     ecx, 1
0x140021fd6  jz      short loc_140022029
0x140021fd8  sub     ecx, 1
0x140021fdb  jz      loc_1400221E2
0x140021fe1  sub     ecx, 1
0x140021fe4  jz      loc_1400221E2
0x140021fea  sub     ecx, 1
0x140021fed  jz      short loc_140022014
0x140021fef  sub     ecx, 1
0x140021ff2  jz      loc_1400221E2
0x140021ff8  cmp     ecx, 1
0x140021ffb  jnz     loc_140022189
0x140022001  lfence
0x140022004  mov     rdx, rsi
0x140022007  mov     rcx, rdi
0x14002200a  call    SecQueryFileHash
0x14002200f  jmp     loc_1400221DC
0x140022014  lfence
0x140022017  mov     rdx, rdi
0x14002201a  mov     rcx, [rsp+418h+ListEntry]
0x14002201f  call    SecSetRegistryData
0x140022024  jmp     loc_1400221DC
0x140022029  mov     dword ptr [rsi+10h], 42h ; 'B'
0x140022030  mov     [rsi+14h], r15d
0x140022034  jmp     loc_1400221E2
0x140022039  lfence
0x14002203c  mov     rdx, rsi
0x14002203f  mov     rcx, rdi
0x140022042  call    SecQueryProcessData
0x140022047  jmp     loc_1400221DC
0x14002204c  sub     ecx, 9
0x14002204f  jz      loc_1400220D5
0x140022055  sub     ecx, 1
0x140022058  jz      short loc_1400220C0
0x14002205a  sub     ecx, 1
0x14002205d  jz      short loc_1400220AD
0x14002205f  sub     ecx, 1
0x140022062  jz      short loc_14002209A
0x140022064  sub     ecx, 1
0x140022067  jz      short loc_140022087
0x140022069  cmp     ecx, 1
0x14002206c  jnz     loc_140022189
0x140022072  lfence
0x140022075  mov     rdx, rdi
0x140022078  mov     rcx, [rsp+418h+ListEntry]
0x14002207d  call    SecSetFileMonitorData
0x140022082  jmp     loc_1400221DC
0x140022087  lfence
0x14002208a  mov     rdx, rsi
0x14002208d  mov     rcx, rdi
0x140022090  call    SecWriteFileDlpEA
0x140022095  jmp     loc_1400221DC
0x14002209a  lfence
0x14002209d  mov     rdx, rsi
0x1400220a0  mov     rcx, rdi
0x1400220a3  call    SecWriteFileHashEA
0x1400220a8  jmp     loc_1400221DC
0x1400220ad  lfence
0x1400220b0  mov     rdx, rsi
0x1400220b3  mov     rcx, rdi
0x1400220b6  call    SecSetDriverConfiguration
0x1400220bb  jmp     loc_1400221DC
0x1400220c0  lfence
0x1400220c3  mov     rdx, rdi
0x1400220c6  mov     rcx, [rsp+418h+ListEntry]
0x1400220cb  call    SecUnregisterConsumer
0x1400220d0  jmp     loc_1400221DC
0x1400220d5  lfence
0x1400220d8  mov     rdx, rdi
0x1400220db  mov     rcx, [rsp+418h+ListEntry]
0x1400220e0  call    SecRegisterConsumer
0x1400220e5  jmp     loc_1400221DC
0x1400220ea  lfence
0x1400220ed  mov     rdx, rsi
0x1400220f0  mov     rcx, rdi
0x1400220f3  call    SecRequestOplockOnFileRequest
0x1400220f8  jmp     loc_1400221DC
0x1400220fd  cmp     ecx, 19h
0x140022100  jg      short loc_140022170
0x140022102  jz      short loc_140022163
0x140022104  sub     ecx, 10h
0x140022107  jz      short loc_140022153
0x140022109  sub     ecx, 1
0x14002210c  jz      short loc_140022140
0x14002210e  sub     ecx, 4
0x140022111  jz      short loc_140022132
0x140022113  sub     ecx, 1
0x140022116  jz      short loc_140022132
0x140022118  sub     ecx, 1
0x14002211b  jz      short loc_140022132
0x14002211d  cmp     ecx, 1
0x140022120  jnz     short loc_140022189
0x140022122  lfence
0x140022125  mov     rcx, rdi
0x140022128  call    SecSetCiInformationForFile
0x14002212d  jmp     loc_1400221DC
0x140022132  mov     ebx, 0C0000010h
0x140022137  mov     [rsp+418h+var_3F8], ebx
0x14002213b  jmp     loc_1400221E6
0x140022140  lfence
0x140022143  mov     rdx, rsi
0x140022146  mov     rcx, rdi
0x140022149  call    SecSetDriverDlpConfiguration
  ... truncated ...
```
