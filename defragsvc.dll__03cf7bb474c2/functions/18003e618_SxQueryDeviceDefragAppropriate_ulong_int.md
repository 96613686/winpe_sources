# SxQueryDeviceDefragAppropriate(ulong,int *)

- ea: `0x18003e618`
- end: `0x18003eaf4`
- name: `?SxQueryDeviceDefragAppropriate@@YAJKPEAH@Z`
- size: `1244`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800130c8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001b300`
- `0x18001b38c`
- `0x18001b590`
- `0x1800391fc`
- `0x18003e618`
- `0x180046494`
- `0x180067b0a`
- `0x180067b30`
- `0x180067bf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e73e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e73e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e7a7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e8f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e9ac`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e7a7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e8f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003e9ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa7`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceDefragAppropriate(unsigned int a1, int *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HANDLE FileW; // rsi
  __int64 v9; // r8
  __int64 v10; // r9
  BOOL v11; // ebx
  __int16 v12; // ax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+54h] [rbp-ACh]
  __int16 v20; // [rsp+56h] [rbp-AAh]
  int v21; // [rsp+88h] [rbp-78h] BYREF
  __int16 v22; // [rsp+8Ch] [rbp-74h]
  __int64 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  int v24; // [rsp+C8h] [rbp-38h]
  __int64 v25; // [rsp+D0h] [rbp-30h] BYREF
  int v26; // [rsp+D8h] [rbp-28h]
  __int128 OutBuffer; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v28; // [rsp+F0h] [rbp-10h]
  _DWORD v29[6]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v30; // [rsp+118h] [rbp+18h]
  char v31; // [rsp+12Eh] [rbp+2Eh]
  __int16 v32; // [rsp+2EAh] [rbp+1EAh]
  WCHAR FileName[264]; // [rsp+1140h] [rbp+1040h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SxQueryDeviceDefragAppropriate", 689, 1);
  memset_0(FileName, 0, 0x20Au);
  InBuffer = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  OutBuffer = 0;
  LOWORD(v29[0]) = 0;
  v28 = 0;
  memset_0((char *)v29 + 2, 0, 0x1036u);
  BytesReturned = 0;
  v4 = 711;
  v16 = 0;
  v17 = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v18 = -2147024809;
    goto LABEL_48;
  }
  *a2 = 1;
  v18 = 0;
  v19 = 711;
  LastFailureAsHRESULT = StringCchPrintfW(FileName, 0x105u, L"\\\\?\\PhysicalDrive%ld", a1);
  v18 = LastFailureAsHRESULT;
  v4 = 718;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_48:
    v20 = v4;
    goto LABEL_49;
  }
  v19 = 718;
  FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7, v6, v9, v10);
    v18 = LastFailureAsHRESULT;
    v4 = 727;
    goto LABEL_48;
  }
  v18 = 0;
  v19 = 727;
  InBuffer = 1;
  if ( !DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0)
    || (_QWORD)OutBuffer != 0x2000000020LL )
  {
    OutBuffer = 0;
    v28 = 0;
  }
  if ( BYTE8(v28) != 15 )
    goto LABEL_16;
  v11 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "SxQueryDeviceForDynamicVirtualDisk", 295, 1);
  v15 = 0;
  v22 = 301;
  v21 = 0;
  if ( (int)SxQueryDeviceTypeVirtualDiskSub(FileName, (enum DF_DEVICE_TYPE *)&v15) >= 0 )
    v11 = (unsigned int)(v15 - 9) > 1;
  v21 = 0;
  v22 = 320;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  if ( v11 )
  {
LABEL_16:
    LastFailureAsHRESULT = SxCheckTrimSupport(FileW, &v16);
    v18 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v20 = 775;
      goto LABEL_45;
    }
    v19 = 775;
    if ( v16 )
    {
      InBuffer = 7;
      if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &v25, 0xCu, &BytesReturned, 0)
        && v25 == 0xC0000000CLL
        && !(_BYTE)v26 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        *a2 = 0;
        v12 = 802;
      }
      else if ( ((BYTE8(v28) - 3) & 0xF7) == 0
             && (v29[0] = 196656,
                 v29[2] = 512,
                 v29[3] = 10,
                 v30 = 56,
                 v31 = -20,
                 DeviceIoControl(FileW, 0x4D02Cu, v29, 0x1038u, v29, 0x1038u, &BytesReturned, 0))
             && v32 == 1 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        *a2 = 0;
        v12 = 836;
      }
      else if ( (int)SxQueryDeviceRandomReadDiskScore(a1, &v17) < 0 || v17 < 0x20001 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        v12 = 857;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        *a2 = 0;
        v12 = 852;
      }
    }
    else
    {
      v12 = 779;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
    }
    *a2 = 0;
    v12 = 764;
  }
  LastFailureAsHRESULT = 0;
  v19 = v12;
  v18 = 0;
LABEL_45:
  if ( FileW )
    CloseHandle(FileW);
LABEL_49:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003e618  mov     [rsp-8+arg_10], rbx
0x18003e61d  mov     [rsp-8+arg_18], rsi
0x18003e622  push    rbp
0x18003e623  push    rdi
0x18003e624  push    r13
0x18003e626  push    r14
0x18003e628  push    r15
0x18003e62a  lea     rbp, [rsp-1260h]
0x18003e632  mov     eax, 1360h
0x18003e637  call    _alloca_probe
0x18003e63c  sub     rsp, rax
0x18003e63f  mov     rax, cs:__security_cookie
0x18003e646  xor     rax, rsp
0x18003e649  mov     [rbp+1280h+var_30], rax
0x18003e650  mov     r14, rdx
0x18003e653  mov     edi, ecx
0x18003e655  mov     r13d, 1
0x18003e65b  lea     rdx, aSxquerydeviced; "SxQueryDeviceDefragAppropriate"
0x18003e662  mov     r9d, r13d; unsigned __int16
0x18003e665  lea     rcx, [rsp+1380h+var_1330]; this
0x18003e66a  mov     r8d, 2B1h; unsigned __int16
0x18003e670  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003e675  xor     edx, edx; Val
0x18003e677  lea     rcx, [rbp+1280h+FileName]; void *
0x18003e67e  mov     r8d, 20Ah; Size
0x18003e684  call    memset_0
0x18003e689  xor     eax, eax
0x18003e68b  lea     rcx, [rbp+1280h+var_1280+2]; void *
0x18003e68f  xorps   xmm0, xmm0
0x18003e692  mov     [rbp+1280h+InBuffer], rax
0x18003e696  xor     r15d, r15d
0x18003e699  mov     [rbp+1280h+var_12B8], eax
0x18003e69c  xor     edx, edx; Val
0x18003e69e  mov     [rbp+1280h+var_12B0], rax
0x18003e6a2  mov     r8d, 1036h; Size
0x18003e6a8  mov     [rbp+1280h+var_12A8], eax
0x18003e6ab  movups  [rbp+1280h+OutBuffer], xmm0
0x18003e6af  mov     word ptr [rbp+1280h+var_1280], r15w
0x18003e6b4  movups  [rbp+1280h+var_1290], xmm0
0x18003e6b8  call    memset_0
0x18003e6bd  mov     [rsp+1380h+BytesReturned], r15d
0x18003e6c2  mov     eax, 2C7h
0x18003e6c7  mov     [rsp+1380h+var_1338], r15d
0x18003e6cc  mov     [rsp+1380h+var_1334], r15d
0x18003e6d1  test    r14, r14
0x18003e6d4  jz      loc_18003EAAF
0x18003e6da  mov     r9d, edi
0x18003e6dd  mov     [r14], r13d
0x18003e6e0  lea     r8, aPhysicaldriveL; "\\\\?\\PhysicalDrive%ld"
0x18003e6e7  mov     [rsp+1380h+var_1330], r15d
0x18003e6ec  mov     edx, 105h; unsigned __int64
0x18003e6f1  mov     [rsp+1380h+var_132C], ax
0x18003e6f6  lea     rcx, [rbp+1280h+FileName]; unsigned __int16 *
0x18003e6fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e702  mov     ebx, eax
0x18003e704  mov     [rsp+1380h+var_1330], eax
0x18003e708  test    eax, eax
0x18003e70a  mov     eax, 2CEh
0x18003e70f  js      loc_18003EAB8
0x18003e715  mov     [rsp+1380h+var_132C], ax
0x18003e71a  lea     rcx, [rbp+1280h+FileName]; lpFileName
0x18003e721  lea     eax, [r13+2]
0x18003e725  mov     [rsp+1380h+hTemplateFile], r15; hTemplateFile
0x18003e72a  mov     r8d, eax; dwShareMode
0x18003e72d  mov     [rsp+1380h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18003e732  xor     r9d, r9d; lpSecurityAttributes
0x18003e735  mov     [rsp+1380h+dwCreationDisposition], eax; dwCreationDisposition
0x18003e739  mov     edx, 0C0000000h; dwDesiredAccess
0x18003e73e  call    cs:__imp_CreateFileW
0x18003e744  mov     rsi, rax
0x18003e747  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e74b  jnz     short loc_18003E762
0x18003e74d  call    GetLastFailureAsHRESULT
0x18003e752  mov     ebx, eax
0x18003e754  mov     [rsp+1380h+var_1330], eax
0x18003e758  mov     eax, 2D7h
0x18003e75d  jmp     loc_18003EAB8
0x18003e762  mov     [rsp+1380h+lpOverlapped], r15; lpOverlapped
0x18003e767  lea     r8, [rbp+1280h+InBuffer]; lpInBuffer
0x18003e76b  mov     eax, 2D7h
0x18003e770  mov     [rsp+1380h+var_1330], r15d
0x18003e775  mov     [rsp+1380h+var_132C], ax
0x18003e77a  mov     r9d, 0Ch; nInBufferSize
0x18003e780  lea     rax, [rsp+1380h+BytesReturned]
0x18003e785  mov     [rbp+1280h+InBuffer], r13
0x18003e789  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18003e78e  mov     edx, 2D1400h; dwIoControlCode
0x18003e793  lea     rax, [rbp+1280h+OutBuffer]
0x18003e797  mov     [rsp+1380h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18003e79f  mov     rcx, rsi; hDevice
0x18003e7a2  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18003e7a7  call    cs:__imp_DeviceIoControl
0x18003e7ad  test    eax, eax
0x18003e7af  jz      short loc_18003E7BD
0x18003e7b1  cmp     dword ptr [rbp+1280h+OutBuffer], 20h ; ' '
0x18003e7b5  jnz     short loc_18003E7BD
0x18003e7b7  cmp     dword ptr [rbp+1280h+OutBuffer+4], 20h ; ' '
0x18003e7bb  jz      short loc_18003E7C8
0x18003e7bd  xorps   xmm0, xmm0
0x18003e7c0  movups  [rbp+1280h+OutBuffer], xmm0
0x18003e7c4  movups  [rbp+1280h+var_1290], xmm0
0x18003e7c8  cmp     byte ptr [rbp+1280h+var_1290+8], 0Fh
0x18003e7cc  jnz     loc_18003E87C
0x18003e7d2  mov     r9d, r13d; unsigned __int16
0x18003e7d5  lea     rdx, aSxquerydevicef; "SxQueryDeviceForDynamicVirtualDisk"
0x18003e7dc  mov     r8d, 127h; unsigned __int16
0x18003e7e2  lea     rcx, [rbp+1280h+var_12F8]; this
0x18003e7e6  mov     ebx, r13d
0x18003e7e9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003e7ee  mov     eax, 12Dh
0x18003e7f3  mov     [rsp+1380h+var_133C], r15d
0x18003e7f8  lea     rdx, [rsp+1380h+var_133C]; enum DF_DEVICE_TYPE *
0x18003e7fd  mov     [rbp+1280h+var_12F4], ax
0x18003e801  lea     rcx, [rbp+1280h+FileName]; lpFileName
0x18003e808  mov     [rbp+1280h+var_12F8], r15d
0x18003e80c  call    ?SxQueryDeviceTypeVirtualDiskSub@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z; SxQueryDeviceTypeVirtualDiskSub(ushort const *,DF_DEVICE_TYPE *)
0x18003e811  test    eax, eax
0x18003e813  js      short loc_18003E823
0x18003e815  mov     ecx, [rsp+1380h+var_133C]
0x18003e819  add     ecx, 0FFFFFFF7h
0x18003e81c  cmp     ecx, r13d
0x18003e81f  cmovbe  ebx, r15d
0x18003e823  mov     eax, 140h
0x18003e828  mov     [rbp+1280h+var_12F8], r15d
0x18003e82c  mov     [rbp+1280h+var_12F4], ax
0x18003e830  lea     rcx, [rbp+1280h+var_12F8]; this
0x18003e834  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003e839  test    ebx, ebx
0x18003e83b  jnz     short loc_18003E87C
0x18003e83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e844  lea     rax, WPP_GLOBAL_Control
0x18003e84b  cmp     rcx, rax
0x18003e84e  jz      short loc_18003E86F
0x18003e850  test    dword ptr [rcx+1Ch], 10000000h
0x18003e857  jz      short loc_18003E86F
0x18003e859  mov     rcx, [rcx+10h]
0x18003e85d  lea     edx, [rbx+0Fh]
0x18003e860  mov     r9d, edi
0x18003e863  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18003e86a  call    WPP_SF_d
0x18003e86f  mov     [r14], r15d
0x18003e872  mov     eax, 2FCh
0x18003e877  jmp     loc_18003EA92
0x18003e87c  lea     rdx, [rsp+1380h+var_1338]; int *
0x18003e881  mov     rcx, rsi; hDevice
0x18003e884  call    ?SxCheckTrimSupport@@YAJPEAXPEAH@Z; SxCheckTrimSupport(void *,int *)
0x18003e889  mov     ebx, eax
0x18003e88b  mov     [rsp+1380h+var_1330], eax
0x18003e88f  test    eax, eax
0x18003e891  mov     eax, 307h
0x18003e896  jns     short loc_18003E8A2
0x18003e898  mov     [rsp+1380h+var_132A], ax
0x18003e89d  jmp     loc_18003EA9F
0x18003e8a2  mov     [rsp+1380h+var_132C], ax
0x18003e8a7  cmp     [rsp+1380h+var_1338], r15d
0x18003e8ac  jnz     short loc_18003E8B8
0x18003e8ae  mov     eax, 30Bh
0x18003e8b3  jmp     loc_18003EA92
0x18003e8b8  mov     [rsp+1380h+lpOverlapped], r15; lpOverlapped
0x18003e8bd  lea     rax, [rsp+1380h+BytesReturned]
0x18003e8c2  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18003e8c7  lea     r8, [rbp+1280h+InBuffer]; lpInBuffer
0x18003e8cb  lea     rax, [rbp+1280h+var_12B0]
0x18003e8cf  mov     [rsp+1380h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18003e8d7  mov     r9d, 0Ch; nInBufferSize
0x18003e8dd  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18003e8e2  mov     edx, 2D1400h; dwIoControlCode
0x18003e8e7  mov     [rbp+1280h+InBuffer], 7
0x18003e8ef  mov     rcx, rsi; hDevice
0x18003e8f2  call    cs:__imp_DeviceIoControl
0x18003e8f8  test    eax, eax
0x18003e8fa  jz      short loc_18003E94F
0x18003e8fc  cmp     dword ptr [rbp+1280h+var_12B0], 0Ch
0x18003e900  jnz     short loc_18003E94F
0x18003e902  cmp     dword ptr [rbp+1280h+var_12B0+4], 0Ch
0x18003e906  jnz     short loc_18003E94F
0x18003e908  cmp     byte ptr [rbp+1280h+var_12A8], r15b
0x18003e90c  jnz     short loc_18003E94F
0x18003e90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e915  lea     rax, WPP_GLOBAL_Control
0x18003e91c  cmp     rcx, rax
0x18003e91f  jz      short loc_18003E942
0x18003e921  test    dword ptr [rcx+1Ch], 10000000h
0x18003e928  jz      short loc_18003E942
0x18003e92a  mov     rcx, [rcx+10h]
0x18003e92e  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18003e935  mov     edx, 10h
0x18003e93a  mov     r9d, edi
0x18003e93d  call    WPP_SF_d
0x18003e942  mov     [r14], r15d
0x18003e945  mov     eax, 322h
0x18003e94a  jmp     loc_18003EA92
0x18003e94f  mov     al, byte ptr [rbp+1280h+var_1290+8]
0x18003e952  sub     al, 3
0x18003e954  test    al, 0F7h
0x18003e956  jnz     loc_18003EA01
0x18003e95c  mov     [rsp+1380h+lpOverlapped], r15; lpOverlapped
0x18003e961  lea     rax, [rsp+1380h+BytesReturned]
0x18003e966  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18003e96b  lea     r8, [rbp+1280h+var_1280]; lpInBuffer
0x18003e96f  mov     r9d, 1038h; nInBufferSize
0x18003e975  mov     [rbp+1280h+var_1280], 30030h
0x18003e97c  lea     rax, [rbp+1280h+var_1280]
0x18003e980  mov     [rsp+1380h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x18003e985  mov     edx, 4D02Ch; dwIoControlCode
0x18003e98a  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18003e98f  mov     rcx, rsi; hDevice
0x18003e992  mov     [rbp+1280h+var_1278], 200h
0x18003e999  mov     [rbp+1280h+var_1274], 0Ah
0x18003e9a0  mov     [rbp+1280h+var_1268], 38h ; '8'
0x18003e9a8  mov     [rbp+1280h+var_1252], 0ECh
0x18003e9ac  call    cs:__imp_DeviceIoControl
0x18003e9b2  test    eax, eax
0x18003e9b4  jz      short loc_18003EA01
0x18003e9b6  cmp     [rbp+1280h+var_1096], r13w
0x18003e9be  jnz     short loc_18003EA01
0x18003e9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e9c7  lea     rax, WPP_GLOBAL_Control
0x18003e9ce  cmp     rcx, rax
0x18003e9d1  jz      short loc_18003E9F4
0x18003e9d3  test    dword ptr [rcx+1Ch], 10000000h
0x18003e9da  jz      short loc_18003E9F4
0x18003e9dc  mov     rcx, [rcx+10h]
0x18003e9e0  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18003e9e7  mov     edx, 11h
0x18003e9ec  mov     r9d, edi
0x18003e9ef  call    WPP_SF_d
0x18003e9f4  mov     [r14], r15d
0x18003e9f7  mov     eax, 344h
0x18003e9fc  jmp     loc_18003EA92
0x18003ea01  lea     rdx, [rsp+1380h+var_1334]; unsigned int *
0x18003ea06  mov     ecx, edi; unsigned int
0x18003ea08  call    ?SxQueryDeviceRandomReadDiskScore@@YAJKPEAK@Z; SxQueryDeviceRandomReadDiskScore(ulong,ulong *)
0x18003ea0d  test    eax, eax
0x18003ea0f  js      short loc_18003EA59
0x18003ea11  cmp     [rsp+1380h+var_1334], 20001h
0x18003ea19  jb      short loc_18003EA59
0x18003ea1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea22  lea     rax, WPP_GLOBAL_Control
0x18003ea29  cmp     rcx, rax
0x18003ea2c  jz      short loc_18003EA4F
0x18003ea2e  test    dword ptr [rcx+1Ch], 10000000h
0x18003ea35  jz      short loc_18003EA4F
0x18003ea37  mov     rcx, [rcx+10h]
0x18003ea3b  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18003ea42  mov     edx, 12h
0x18003ea47  mov     r9d, edi
0x18003ea4a  call    WPP_SF_d
0x18003ea4f  mov     [r14], r15d
0x18003ea52  mov     eax, 354h
0x18003ea57  jmp     short loc_18003EA92
0x18003ea59  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea60  lea     rax, WPP_GLOBAL_Control
0x18003ea67  cmp     rcx, rax
0x18003ea6a  jz      short loc_18003EA8D
0x18003ea6c  test    dword ptr [rcx+1Ch], 10000000h
0x18003ea73  jz      short loc_18003EA8D
0x18003ea75  mov     rcx, [rcx+10h]
0x18003ea79  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18003ea80  mov     edx, 13h
0x18003ea85  mov     r9d, edi
0x18003ea88  call    WPP_SF_d
0x18003ea8d  mov     eax, 359h
0x18003ea92  mov     ebx, r15d
0x18003ea95  mov     [rsp+1380h+var_132C], ax
0x18003ea9a  mov     [rsp+1380h+var_1330], r15d
0x18003ea9f  test    rsi, rsi
0x18003eaa2  jz      short loc_18003EABD
0x18003eaa4  mov     rcx, rsi; hObject
0x18003eaa7  call    cs:__imp_CloseHandle
0x18003eaad  jmp     short loc_18003EABD
0x18003eaaf  mov     ebx, 80070057h
0x18003eab4  mov     [rsp+1380h+var_1330], ebx
0x18003eab8  mov     [rsp+1380h+var_132A], ax
0x18003eabd  lea     rcx, [rsp+1380h+var_1330]; this
0x18003eac2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003eac7  mov     eax, ebx
0x18003eac9  mov     rcx, [rbp+1280h+var_30]
0x18003ead0  xor     rcx, rsp; StackCookie
0x18003ead3  call    __security_check_cookie
0x18003ead8  lea     r11, [rsp+1380h+var_20]
0x18003eae0  mov     rbx, [r11+40h]
0x18003eae4  mov     rsi, [r11+48h]
0x18003eae8  mov     rsp, r11
0x18003eaeb  pop     r15
0x18003eaed  pop     r14
0x18003eaef  pop     r13
0x18003eaf1  pop     rdi
0x18003eaf2  pop     rbp
0x18003eaf3  retn
```
