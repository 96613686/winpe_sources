# SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)

- ea: `0x180052e20`
- end: `0x1800530b0`
- name: `?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800130c8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001b300`
- `0x180046494`
- `0x180052e20`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180052f29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180052f29`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052f90`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052ff3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052f90`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053073`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceForThinProvisionedDisk(unsigned int a1, int a2, _DWORD *a3)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  HANDLE FileW; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ebx
  __int16 v14; // ax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v18; // [rsp+4Ch] [rbp-B4h]
  __int16 v19; // [rsp+4Eh] [rbp-B2h]
  __int64 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+88h] [rbp-78h]
  __int128 OutBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+D0h] [rbp-30h]
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "SxQueryDeviceForThinProvisionedDisk", 67, 1);
  memset_0(FileName, 0, 0x20Au);
  InBuffer = 0;
  v21 = 0;
  v26 = 0;
  v6 = 78;
  BytesReturned = 0;
  OutBuffer = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( !a3 )
  {
    LastFailureAsHRESULT = -2147024809;
    v17 = -2147024809;
LABEL_3:
    v19 = v6;
    goto LABEL_23;
  }
  v17 = 0;
  v18 = 78;
  *a3 = a2;
  LastFailureAsHRESULT = StringCchPrintfW(FileName, 0x105u, L"\\\\?\\PhysicalDrive%ld", a1);
  v17 = LastFailureAsHRESULT;
  v6 = 87;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v18 = 87;
  FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9, v8, v11, v12);
    v17 = LastFailureAsHRESULT;
    v6 = 96;
    goto LABEL_3;
  }
  v17 = 0;
  v18 = 96;
  InBuffer = 1;
  v13 = 0;
  if ( !DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0)
    || (_QWORD)OutBuffer != 0x2000000020LL )
  {
    OutBuffer = 0;
    v23 = 0;
  }
  InBuffer = 11;
  if ( BYTE8(v23) == 16 )
    v13 = 1;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &v24, 0x28u, &BytesReturned, 0)
    && (_QWORD)v24 == 0x2800000028LL
    && (BYTE8(v24) & 1) != 0
    && (_QWORD)v25 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
    }
    *a3 = 2 * v13 + 5;
    v14 = 158;
  }
  else
  {
    v14 = 162;
  }
  v18 = v14;
  LastFailureAsHRESULT = 0;
  v17 = 0;
  if ( FileW )
    CloseHandle(FileW);
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180052e20  mov     [rsp-8+arg_8], rbx
0x180052e25  mov     [rsp-8+arg_18], rsi
0x180052e2a  push    rbp
0x180052e2b  push    rdi
0x180052e2c  push    r12
0x180052e2e  push    r14
0x180052e30  push    r15
0x180052e32  lea     rbp, [rsp-200h]
0x180052e3a  sub     rsp, 300h
0x180052e41  mov     rax, cs:__security_cookie
0x180052e48  xor     rax, rsp
0x180052e4b  mov     [rbp+220h+var_30], rax
0x180052e52  mov     r12d, 1
0x180052e58  mov     rsi, r8
0x180052e5b  mov     ebx, edx
0x180052e5d  mov     r14d, ecx
0x180052e60  mov     r9d, r12d; unsigned __int16
0x180052e63  lea     rdx, aSxquerydevicef_0; "SxQueryDeviceForThinProvisionedDisk"
0x180052e6a  lea     rcx, [rsp+320h+var_2D8]; this
0x180052e6f  lea     r8d, [r12+42h]; unsigned __int16
0x180052e74  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180052e79  xor     edx, edx; Val
0x180052e7b  lea     rcx, [rbp+220h+FileName]; void *
0x180052e7f  mov     r8d, 20Ah; Size
0x180052e85  call    memset_0
0x180052e8a  xor     eax, eax
0x180052e8c  xor     r15d, r15d
0x180052e8f  mov     [rbp+220h+InBuffer], rax
0x180052e93  xorps   xmm0, xmm0
0x180052e96  mov     [rbp+220h+var_298], eax
0x180052e99  xorps   xmm1, xmm1
0x180052e9c  mov     [rbp+220h+var_250], rax
0x180052ea0  lea     eax, [r12+4Dh]
0x180052ea5  mov     [rsp+320h+BytesReturned], r15d
0x180052eaa  movups  [rbp+220h+OutBuffer], xmm0
0x180052eae  movups  [rbp+220h+var_280], xmm0
0x180052eb2  movups  [rbp+220h+var_270], xmm1
0x180052eb6  movups  [rbp+220h+var_260], xmm1
0x180052eba  test    rsi, rsi
0x180052ebd  jnz     short loc_180052ED2
0x180052ebf  mov     ebx, 80070057h
0x180052ec4  mov     [rsp+320h+var_2D8], ebx
0x180052ec8  mov     [rsp+320h+var_2D2], ax
0x180052ecd  jmp     loc_180053079
0x180052ed2  mov     r9d, r14d
0x180052ed5  mov     [rsp+320h+var_2D8], r15d
0x180052eda  lea     r8, aPhysicaldriveL; "\\\\?\\PhysicalDrive%ld"
0x180052ee1  mov     [rsp+320h+var_2D4], ax
0x180052ee6  mov     edx, 105h; unsigned __int64
0x180052eeb  mov     [rsi], ebx
0x180052eed  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x180052ef1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052ef6  mov     ebx, eax
0x180052ef8  mov     [rsp+320h+var_2D8], eax
0x180052efc  test    eax, eax
0x180052efe  mov     eax, 57h ; 'W'
0x180052f03  js      short loc_180052EC8
0x180052f05  mov     [rsp+320h+hTemplateFile], r15; hTemplateFile
0x180052f0a  lea     r8d, [rax-54h]; dwShareMode
0x180052f0e  mov     [rsp+320h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180052f13  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180052f17  xor     r9d, r9d; lpSecurityAttributes
0x180052f1a  mov     [rsp+320h+dwCreationDisposition], r8d; dwCreationDisposition
0x180052f1f  mov     edx, 0C0000000h; dwDesiredAccess
0x180052f24  mov     [rsp+320h+var_2D4], ax
0x180052f29  call    cs:__imp_CreateFileW
0x180052f2f  mov     rdi, rax
0x180052f32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052f36  jnz     short loc_180052F48
0x180052f38  call    GetLastFailureAsHRESULT
0x180052f3d  mov     ebx, eax
0x180052f3f  mov     [rsp+320h+var_2D8], eax
0x180052f43  lea     eax, [rdi+61h]
0x180052f46  jmp     short loc_180052EC8
0x180052f48  mov     [rsp+320h+lpOverlapped], r15; lpOverlapped
0x180052f4d  lea     r8, [rbp+220h+InBuffer]; lpInBuffer
0x180052f51  mov     eax, 60h ; '`'
0x180052f56  mov     [rsp+320h+var_2D8], r15d
0x180052f5b  mov     [rsp+320h+var_2D4], ax
0x180052f60  mov     r9d, 0Ch; nInBufferSize
0x180052f66  lea     rax, [rsp+320h+BytesReturned]
0x180052f6b  mov     [rbp+220h+InBuffer], r12
0x180052f6f  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x180052f74  mov     edx, 2D1400h; dwIoControlCode
0x180052f79  lea     rax, [rbp+220h+OutBuffer]
0x180052f7d  mov     [rsp+320h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180052f85  mov     rcx, rdi; hDevice
0x180052f88  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x180052f8d  mov     ebx, r15d
0x180052f90  call    cs:__imp_DeviceIoControl
0x180052f96  test    eax, eax
0x180052f98  jz      short loc_180052FA6
0x180052f9a  cmp     dword ptr [rbp+220h+OutBuffer], 20h ; ' '
0x180052f9e  jnz     short loc_180052FA6
0x180052fa0  cmp     dword ptr [rbp+220h+OutBuffer+4], 20h ; ' '
0x180052fa4  jz      short loc_180052FB1
0x180052fa6  xorps   xmm0, xmm0
0x180052fa9  movups  [rbp+220h+OutBuffer], xmm0
0x180052fad  movups  [rbp+220h+var_280], xmm0
0x180052fb1  cmp     byte ptr [rbp+220h+var_280+8], 10h
0x180052fb5  lea     rax, [rsp+320h+BytesReturned]
0x180052fba  mov     [rsp+320h+lpOverlapped], r15; lpOverlapped
0x180052fbf  lea     r8, [rbp+220h+InBuffer]; lpInBuffer
0x180052fc3  mov     [rsp+320h+hTemplateFile], rax; lpBytesReturned
0x180052fc8  mov     r9d, 0Ch; nInBufferSize
0x180052fce  lea     rax, [rbp+220h+var_270]
0x180052fd2  mov     [rsp+320h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x180052fda  mov     edx, 2D1400h; dwIoControlCode
0x180052fdf  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; lpOutBuffer
0x180052fe4  mov     rcx, rdi; hDevice
0x180052fe7  mov     [rbp+220h+InBuffer], 0Bh
0x180052fef  cmovz   ebx, r12d
0x180052ff3  call    cs:__imp_DeviceIoControl
0x180052ff9  test    eax, eax
0x180052ffb  jz      short loc_180053059
0x180052ffd  cmp     dword ptr [rbp+220h+var_270], 28h ; '('
0x180053001  jnz     short loc_180053059
0x180053003  cmp     dword ptr [rbp+220h+var_270+4], 28h ; '('
0x180053007  jnz     short loc_180053059
0x180053009  test    byte ptr [rbp+220h+var_270+8], r12b
0x18005300d  jz      short loc_180053059
0x18005300f  cmp     qword ptr [rbp+220h+var_260], r15
0x180053013  jbe     short loc_180053059
0x180053015  mov     rcx, cs:WPP_GLOBAL_Control
0x18005301c  lea     rax, WPP_GLOBAL_Control
0x180053023  cmp     rcx, rax
0x180053026  jz      short loc_180053049
0x180053028  test    dword ptr [rcx+1Ch], 10000000h
0x18005302f  jz      short loc_180053049
0x180053031  mov     rcx, [rcx+10h]
0x180053035  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18005303c  mov     edx, 0Ah
0x180053041  mov     r9d, r14d
0x180053044  call    WPP_SF_d
0x180053049  lea     eax, ds:5[rbx*2]
0x180053050  mov     [rsi], eax
0x180053052  mov     eax, 9Eh
0x180053057  jmp     short loc_18005305E
0x180053059  mov     eax, 0A2h
0x18005305e  mov     [rsp+320h+var_2D4], ax
0x180053063  mov     ebx, r15d
0x180053066  mov     [rsp+320h+var_2D8], r15d
0x18005306b  test    rdi, rdi
0x18005306e  jz      short loc_180053079
0x180053070  mov     rcx, rdi; hObject
0x180053073  call    cs:__imp_CloseHandle
0x180053079  lea     rcx, [rsp+320h+var_2D8]; this
0x18005307e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180053083  mov     eax, ebx
0x180053085  mov     rcx, [rbp+220h+var_30]
0x18005308c  xor     rcx, rsp; StackCookie
0x18005308f  call    __security_check_cookie
0x180053094  lea     r11, [rsp+320h+var_20]
0x18005309c  mov     rbx, [r11+38h]
0x1800530a0  mov     rsi, [r11+48h]
0x1800530a4  mov     rsp, r11
0x1800530a7  pop     r15
0x1800530a9  pop     r14
0x1800530ab  pop     r12
0x1800530ad  pop     rdi
0x1800530ae  pop     rbp
0x1800530af  retn
```
