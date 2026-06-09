# TlmInitialize

- ea: `0x180012754`
- end: `0x180012b01`
- name: `TlmInitialize`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180011f00`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x180012754`
- `0x18001c76c`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180012822`
- `ntdll!RtlInitializeSRWLock` at `0x180012835`
- `ntdll!RtlInitializeSRWLock` at `0x180012848`
- `ntdll!RtlInitializeSRWLock` at `0x18001285b`
- `ntdll!RtlInitializeSRWLock` at `0x180012822`
- `ntdll!RtlInitializeSRWLock` at `0x180012835`
- `ntdll!RtlInitializeSRWLock` at `0x180012848`
- `ntdll!RtlInitializeSRWLock` at `0x18001285b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800128b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800128b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012892`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012892`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18001286e`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18001286e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180012aa8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180012aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800129bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800129bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800129cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800129cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012951`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ad9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012902`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012902`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800128d1`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800128d1`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18001298e`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180012a0e`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x18001298e`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180012a0e`

## pseudocode

```c
int TlmInitialize()
{
  struct _PEB *v0; // rax
  __int64 FileW; // rdi
  char v2; // si
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  int v5; // edx
  DWORD pcbBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  int v12; // [rsp+88h] [rbp-78h]
  __int64 OutBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v14; // [rsp+98h] [rbp-68h]
  _MEMORYSTATUSEX Buffer; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR sz[8]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v17[264]; // [rsp+F0h] [rbp-10h] BYREF

  UnbiasedTime = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  memset_0(v17, 0, 0x208u);
  wcscpy(sz, L"\\\\.\\c:");
  memset_0(&Buffer, 0, sizeof(Buffer));
  InBuffer = 0;
  v12 = 0;
  OutBuffer = 0;
  v14 = 0;
  BytesReturned = 0;
  pcbBuffer = 0;
  v0 = NtCurrentPeb();
  if ( v0->Ldr->ShutdownInProgress )
    return (int)v0;
  FileW = -1;
  memset_0(&byte_18002A930, 0, 0x268u);
  RtlInitializeSRWLock(&qword_18002A940);
  RtlInitializeSRWLock(&qword_18002A970);
  RtlInitializeSRWLock(&qword_18002A9B8);
  RtlInitializeSRWLock(&qword_18002AA60);
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
    qword_18002AB70 = Buffer.ullTotalPhys >> 10;
  GetSystemInfo(&SystemInfo);
  dword_18002AB78 = SystemInfo.dwNumberOfProcessors;
  if ( GetWindowsDirectoryW(v17, 0x104u) )
  {
    sz[4] = v17[0];
    CharLowerW(sz);
    FileW = (__int64)CreateFileW(sz, 0, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
    {
      LODWORD(InBuffer) = 7;
      DeviceIoControl((HANDLE)FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0xCu, &BytesReturned, 0);
    }
  }
  if ( BytesReturned - 1 > 0xB )
    dword_18002AB7C = -1;
  else
    dword_18002AB7C = (_BYTE)v14 == 0;
  v2 = 1;
  if ( !GetUserNameW(String2.Buffer, &pcbBuffer) )
  {
    v3 = (unsigned __int16)(2 * (pcbBuffer + 1));
    String2.MaximumLength = 2 * (pcbBuffer + 1);
    ProcessHeap = GetProcessHeap();
    v0 = (struct _PEB *)HeapAlloc(ProcessHeap, 0, v3);
    String2.Buffer = (PWSTR)&v0->InheritedAddressSpace;
    v5 = v0 == 0 ? 8 : 0;
    if ( !v0 )
      v5 |= 0x80070000;
    if ( v5 < 0 )
      goto LABEL_21;
    GetUserNameW((LPWSTR)&v0->BeingDebugged, &pcbBuffer);
    *String2.Buffer = 92;
    String2.Buffer[((unsigned __int64)String2.MaximumLength >> 1) - 1] = 92;
    String2.Length = String2.MaximumLength;
  }
  LODWORD(v0) = TlgRegisterAggregateProviderEx();
  if ( (int)v0 >= 0 )
  {
    byte_18002AB80 = 1;
    if ( !dword_18002A1A0
      || (qword_18002A1B0 & 0x400000000000LL) == 0
      || (qword_18002A1B8 & 0x400000000000LL) != qword_18002A1B8 )
    {
      v2 = 0;
    }
    byte_18002A930 = v2;
    dword_18002AB60 = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    LODWORD(v0) = UnbiasedTime + 3600000;
    dword_18002AB40 = 0;
    qword_18002AB68 = UnbiasedTime + 3600000;
  }
LABEL_21:
  if ( FileW != -1 )
    LODWORD(v0) = CloseHandle((HANDLE)FileW);
  return (int)v0;
}

```

## disassembly

```asm
0x180012754  push    rbp
0x180012756  push    rbx
0x180012757  push    rsi
0x180012758  push    rdi
0x180012759  lea     rbp, [rsp-218h]
0x180012761  sub     rsp, 318h
0x180012768  mov     rax, cs:__security_cookie
0x18001276f  xor     rax, rsp
0x180012772  mov     [rbp+230h+var_30], rax
0x180012779  xorps   xmm0, xmm0
0x18001277c  mov     [rsp+330h+UnbiasedTime], 0
0x180012785  xor     edx, edx; Val
0x180012787  lea     rcx, [rbp+230h+var_240]; void *
0x18001278b  mov     r8d, 208h; Size
0x180012791  movups  xmmword ptr [rsp+330h+SystemInfo], xmm0
0x180012796  movups  xmmword ptr [rsp+330h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001279b  movups  xmmword ptr [rsp+330h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800127a0  call    memset_0
0x1800127a5  mov     rax, 5C002E005C005Ch
0x1800127af  mov     [rbp+230h+var_246], 3Ah ; ':'
0x1800127b6  mov     qword ptr [rbp+230h+sz], rax
0x1800127ba  lea     rcx, [rbp+230h+Buffer]; void *
0x1800127be  mov     eax, 63h ; 'c'
0x1800127c3  xor     edx, edx; Val
0x1800127c5  mov     [rbp+230h+var_248], ax
0x1800127c9  lea     ebx, [rax-23h]
0x1800127cc  mov     r8d, ebx; Size
0x1800127cf  call    memset_0
0x1800127d4  xor     eax, eax
0x1800127d6  mov     [rbp+230h+InBuffer], rax
0x1800127da  mov     [rbp+230h+var_2A8], eax
0x1800127dd  mov     [rbp+230h+OutBuffer], rax
0x1800127e1  mov     [rbp+230h+var_298], eax
0x1800127e4  mov     [rsp+330h+BytesReturned], eax
0x1800127e8  mov     [rsp+330h+pcbBuffer], eax
0x1800127ec  mov     rax, gs:60h
0x1800127f5  mov     rcx, [rax+18h]
0x1800127f9  cmp     byte ptr [rcx+48h], 0
0x1800127fd  jnz     loc_180012AE5
0x180012803  xor     edx, edx; Val
0x180012805  lea     rcx, byte_18002A930; void *
0x18001280c  mov     r8d, 268h; Size
0x180012812  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012816  call    memset_0
0x18001281b  lea     rcx, qword_18002A940
0x180012822  call    cs:__imp_RtlInitializeSRWLock
0x180012829  nop     dword ptr [rax+rax+00h]
0x18001282e  lea     rcx, qword_18002A970
0x180012835  call    cs:__imp_RtlInitializeSRWLock
0x18001283c  nop     dword ptr [rax+rax+00h]
0x180012841  lea     rcx, qword_18002A9B8
0x180012848  call    cs:__imp_RtlInitializeSRWLock
0x18001284f  nop     dword ptr [rax+rax+00h]
0x180012854  lea     rcx, qword_18002AA60
0x18001285b  call    cs:__imp_RtlInitializeSRWLock
0x180012862  nop     dword ptr [rax+rax+00h]
0x180012867  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x18001286b  mov     [rbp+230h+Buffer.dwLength], ebx
0x18001286e  call    cs:__imp_GlobalMemoryStatusEx
0x180012875  nop     dword ptr [rax+rax+00h]
0x18001287a  test    eax, eax
0x18001287c  jz      short loc_18001288D
0x18001287e  mov     rax, [rbp+230h+Buffer.ullTotalPhys]
0x180012882  shr     rax, 0Ah
0x180012886  mov     cs:qword_18002AB70, rax
0x18001288d  lea     rcx, [rsp+330h+SystemInfo]; lpSystemInfo
0x180012892  call    cs:__imp_GetSystemInfo
0x180012899  nop     dword ptr [rax+rax+00h]
0x18001289e  mov     eax, [rsp+330h+SystemInfo.dwNumberOfProcessors]
0x1800128a2  lea     rcx, [rbp+230h+var_240]; lpBuffer
0x1800128a6  mov     edx, 104h; uSize
0x1800128ab  mov     cs:dword_18002AB78, eax
0x1800128b1  call    cs:__imp_GetWindowsDirectoryW
0x1800128b8  nop     dword ptr [rax+rax+00h]
0x1800128bd  test    eax, eax
0x1800128bf  jz      loc_18001295D
0x1800128c5  movzx   eax, [rbp+230h+var_240]
0x1800128c9  lea     rcx, [rbp+230h+sz]; lpsz
0x1800128cd  mov     [rbp+230h+var_248], ax
0x1800128d1  call    cs:__imp_CharLowerW
0x1800128d8  nop     dword ptr [rax+rax+00h]
0x1800128dd  mov     r8d, 3; dwShareMode
0x1800128e3  mov     [rsp+330h+hTemplateFile], 0; hTemplateFile
0x1800128ec  mov     [rsp+330h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800128f4  lea     rcx, [rbp+230h+sz]; lpFileName
0x1800128f8  xor     r9d, r9d; lpSecurityAttributes
0x1800128fb  mov     [rsp+330h+dwCreationDisposition], r8d; dwCreationDisposition
0x180012900  xor     edx, edx; dwDesiredAccess
0x180012902  call    cs:__imp_CreateFileW
0x180012909  nop     dword ptr [rax+rax+00h]
0x18001290e  mov     rdi, rax
0x180012911  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012915  jz      short loc_18001295D
0x180012917  mov     [rsp+330h+lpOverlapped], 0; lpOverlapped
0x180012920  lea     rax, [rsp+330h+BytesReturned]
0x180012925  mov     [rsp+330h+hTemplateFile], rax; lpBytesReturned
0x18001292a  lea     r8, [rbp+230h+InBuffer]; lpInBuffer
0x18001292e  mov     r9d, 0Ch; nInBufferSize
0x180012934  mov     dword ptr [rbp+230h+InBuffer], 7
0x18001293b  lea     rax, [rbp+230h+OutBuffer]
0x18001293f  mov     [rsp+330h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x180012944  mov     edx, 2D1400h; dwIoControlCode
0x180012949  mov     qword ptr [rsp+330h+dwCreationDisposition], rax; lpOutBuffer
0x18001294e  mov     rcx, rdi; hDevice
0x180012951  call    cs:__imp_DeviceIoControl
0x180012958  nop     dword ptr [rax+rax+00h]
0x18001295d  mov     eax, [rsp+330h+BytesReturned]
0x180012961  dec     eax
0x180012963  cmp     eax, 0Bh
0x180012966  ja      short loc_180012978
0x180012968  xor     eax, eax
0x18001296a  cmp     byte ptr [rbp+230h+var_298], al
0x18001296d  setz    al
0x180012970  mov     cs:dword_18002AB7C, eax
0x180012976  jmp     short loc_180012982
0x180012978  mov     cs:dword_18002AB7C, 0FFFFFFFFh
0x180012982  mov     rcx, cs:String2.Buffer; lpBuffer
0x180012989  lea     rdx, [rsp+330h+pcbBuffer]; pcbBuffer
0x18001298e  call    cs:__imp_GetUserNameW
0x180012995  nop     dword ptr [rax+rax+00h]
0x18001299a  mov     si, 1
0x18001299e  test    eax, eax
0x1800129a0  jnz     loc_180012A4D
0x1800129a6  movzx   eax, word ptr [rsp+330h+pcbBuffer]
0x1800129ab  add     ax, si
0x1800129ae  add     ax, ax
0x1800129b1  movzx   ebx, ax
0x1800129b4  mov     cs:String2.MaximumLength, bx
0x1800129bb  call    cs:__imp_GetProcessHeap
0x1800129c2  nop     dword ptr [rax+rax+00h]
0x1800129c7  mov     r8d, ebx; dwBytes
0x1800129ca  xor     edx, edx; dwFlags
0x1800129cc  mov     rcx, rax; hHeap
0x1800129cf  call    cs:__imp_HeapAlloc
0x1800129d6  nop     dword ptr [rax+rax+00h]
0x1800129db  mov     rcx, rax
0x1800129de  mov     cs:String2.Buffer, rax
0x1800129e5  neg     rcx
0x1800129e8  sbb     edx, edx
0x1800129ea  not     edx
0x1800129ec  and     edx, 8
0x1800129ef  mov     ecx, edx
0x1800129f1  or      ecx, 80070000h
0x1800129f7  test    rax, rax
0x1800129fa  cmovz   edx, ecx
0x1800129fd  test    edx, edx
0x1800129ff  js      loc_180012AD0
0x180012a05  lea     rcx, [rax+2]; lpBuffer
0x180012a09  lea     rdx, [rsp+330h+pcbBuffer]; pcbBuffer
0x180012a0e  call    cs:__imp_GetUserNameW
0x180012a15  nop     dword ptr [rax+rax+00h]
0x180012a1a  mov     rax, cs:String2.Buffer
0x180012a21  mov     edx, 5Ch ; '\'
0x180012a26  mov     [rax], dx
0x180012a29  movzx   ecx, cs:String2.MaximumLength
0x180012a30  mov     rax, cs:String2.Buffer
0x180012a37  shr     rcx, 1
0x180012a3a  mov     [rax+rcx*2-2], dx
0x180012a3f  movzx   eax, cs:String2.MaximumLength
0x180012a46  mov     cs:String2.Length, ax
0x180012a4d  call    TlgRegisterAggregateProviderEx
0x180012a52  test    eax, eax
0x180012a54  js      short loc_180012AD0
0x180012a56  mov     eax, cs:dword_18002A1A0
0x180012a5c  mov     cs:byte_18002AB80, sil
0x180012a63  test    eax, eax
0x180012a65  jz      short loc_180012A8F
0x180012a67  mov     rcx, cs:qword_18002A1B8
0x180012a6e  mov     rdx, 400000000000h
0x180012a78  mov     rax, cs:qword_18002A1B0
0x180012a7f  test    rdx, rax
0x180012a82  jz      short loc_180012A8F
0x180012a84  mov     rax, rcx
0x180012a87  and     rax, rdx
0x180012a8a  cmp     rax, rcx
0x180012a8d  jz      short loc_180012A92
0x180012a8f  xor     sil, sil
0x180012a92  lea     rcx, [rsp+330h+UnbiasedTime]; UnbiasedTime
0x180012a97  mov     cs:byte_18002A930, sil
0x180012a9e  mov     cs:dword_18002AB60, 0
0x180012aa8  call    cs:__imp_QueryUnbiasedInterruptTime
0x180012aaf  nop     dword ptr [rax+rax+00h]
0x180012ab4  mov     rax, [rsp+330h+UnbiasedTime]
0x180012ab9  add     rax, 36EE80h
0x180012abf  mov     cs:dword_18002AB40, 0
0x180012ac9  mov     cs:qword_18002AB68, rax
0x180012ad0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180012ad4  jz      short loc_180012AE5
0x180012ad6  mov     rcx, rdi; hObject
0x180012ad9  call    cs:__imp_CloseHandle
0x180012ae0  nop     dword ptr [rax+rax+00h]
0x180012ae5  mov     rcx, [rbp+230h+var_30]
0x180012aec  xor     rcx, rsp; StackCookie
0x180012aef  call    __security_check_cookie
0x180012af4  add     rsp, 318h
0x180012afb  pop     rdi
0x180012afc  pop     rsi
0x180012afd  pop     rbx
0x180012afe  pop     rbp
0x180012aff  retn
```
