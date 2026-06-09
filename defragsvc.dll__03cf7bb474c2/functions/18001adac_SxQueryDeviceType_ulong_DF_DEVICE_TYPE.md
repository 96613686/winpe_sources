# SxQueryDeviceType(ulong,DF_DEVICE_TYPE *)

- ea: `0x18001adac`
- end: `0x18001b2fa`
- name: `?SxQueryDeviceType@@YAJKPEAW4DF_DEVICE_TYPE@@@Z`
- size: `1358`
- prototype: `__int64 __fastcall(unsigned int, enum DF_DEVICE_TYPE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800130c8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001adac`
- `0x18001b300`
- `0x18001b38c`
- `0x18001b590`
- `0x1800391fc`
- `0x180046494`
- `0x180067b0a`
- `0x180067b30`
- `0x180067bf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001af1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001af1e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001af7b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001aff0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b063`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b236`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001af7b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001aff0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b063`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b09d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b09d`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceType(unsigned int a1, enum DF_DEVICE_TYPE *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  HANDLE FileW; // r14
  int v12; // esi
  int v13; // ebx
  __int16 v14; // ax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+54h] [rbp-ACh]
  __int16 v20; // [rsp+56h] [rbp-AAh]
  __int64 InBuffer; // [rsp+88h] [rbp-78h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h] BYREF
  int v24; // [rsp+A0h] [rbp-60h]
  __int128 OutBuffer; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v26; // [rsp+B8h] [rbp-48h]
  __int128 v27; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v28; // [rsp+D8h] [rbp-28h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  _DWORD v30[6]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v31; // [rsp+108h] [rbp+8h]
  char v32; // [rsp+11Eh] [rbp+1Eh]
  __int16 v33; // [rsp+2DAh] [rbp+1DAh]
  WCHAR FileName[264]; // [rsp+1130h] [rbp+1030h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SxQueryDeviceType", 444, 1);
  memset_0(FileName, 0, 0x20Au);
  InBuffer = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  OutBuffer = 0;
  LOWORD(v30[0]) = 0;
  v26 = 0;
  memset_0((char *)v30 + 2, 0, 0x1036u);
  BytesReturned = 0;
  v29 = 0;
  v16 = 0;
  v4 = 467;
  v17 = 0;
  v27 = 0;
  v28 = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v18 = -2147024809;
LABEL_3:
    v20 = v4;
    goto LABEL_4;
  }
  *(_DWORD *)a2 = 0;
  v18 = 0;
  v19 = 467;
  LastFailureAsHRESULT = StringCchPrintfW(FileName, 0x105u, L"\\\\?\\PhysicalDrive%ld", a1);
  v18 = LastFailureAsHRESULT;
  v4 = 474;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v19 = 474;
  FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7, v9, v10);
    v18 = LastFailureAsHRESULT;
    v4 = 483;
    goto LABEL_3;
  }
  v18 = 0;
  v19 = 483;
  InBuffer = 1;
  v12 = 0;
  if ( !DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0)
    || (_QWORD)OutBuffer != 0x2000000020LL )
  {
    OutBuffer = 0;
    v26 = 0;
  }
  if ( BYTE8(v26) == 15 )
  {
    if ( (int)SxQueryDeviceTypeVirtualDiskSub(FileName, a2) >= 0 )
    {
      v14 = 518;
LABEL_17:
      LastFailureAsHRESULT = 0;
      v19 = v14;
      v18 = 0;
      goto LABEL_18;
    }
  }
  else if ( BYTE8(v26) == 16 )
  {
    v12 = 1;
  }
  InBuffer = 11;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &v27, 0x28u, &BytesReturned, 0)
    && (_QWORD)v27 == 0x2800000028LL
    && (BYTE8(v27) & 1) != 0
    && (_QWORD)v28 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
    }
    *(_DWORD *)a2 = 2 * v12 + 5;
    v14 = 556;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = SxCheckTrimSupport(FileW, &v16);
  v18 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v13 = v16;
    v19 = 560;
    if ( v16
      && (InBuffer = 7, DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &v23, 0xCu, &BytesReturned, 0))
      && v23 == 0xC0000000CLL
      && !(_BYTE)v24 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
      }
      *(_DWORD *)a2 = v12 != 0 ? 12 : 3;
      v14 = 599;
    }
    else if ( v12 )
    {
      *(_DWORD *)a2 = 6;
      v14 = 606;
    }
    else if ( v13 )
    {
      if ( ((BYTE8(v26) - 3) & 0xF7) == 0
        && (v30[0] = 196656,
            v30[2] = 512,
            v30[3] = 10,
            v31 = 56,
            v32 = -20,
            DeviceIoControl(FileW, 0x4D02Cu, v30, 0x1038u, v30, 0x1038u, &BytesReturned, 0))
        && v33 == 1 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        *(_DWORD *)a2 = 3;
        v14 = 653;
      }
      else if ( (int)SxQueryDeviceRandomReadDiskScore(a1, &v17) < 0 || v17 < 0x20001 )
      {
        *(_DWORD *)a2 = 1;
        v14 = 675;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, a1);
        }
        *(_DWORD *)a2 = 3;
        v14 = 669;
      }
    }
    else
    {
      *(_DWORD *)a2 = 1;
      v14 = 619;
    }
    goto LABEL_17;
  }
  v20 = 560;
LABEL_18:
  if ( FileW )
    CloseHandle(FileW);
LABEL_4:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001adac  mov     [rsp-8+arg_10], rbx
0x18001adb1  push    rbp
0x18001adb2  push    rsi
0x18001adb3  push    rdi
0x18001adb4  push    r12
0x18001adb6  push    r13
0x18001adb8  push    r14
0x18001adba  push    r15
0x18001adbc  lea     rbp, [rsp-1250h]
0x18001adc4  mov     eax, 1350h
0x18001adc9  call    _alloca_probe
0x18001adce  sub     rsp, rax
0x18001add1  mov     rax, cs:__security_cookie
0x18001add8  xor     rax, rsp
0x18001addb  mov     [rbp+1280h+var_40], rax
0x18001ade2  mov     rdi, rdx
0x18001ade5  mov     r15d, ecx
0x18001ade8  lea     rdx, aSxquerydevicet; "SxQueryDeviceType"
0x18001adef  mov     r9d, 1; unsigned __int16
0x18001adf5  lea     rcx, [rsp+1380h+var_1330]; this
0x18001adfa  mov     r8d, 1BCh; unsigned __int16
0x18001ae00  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ae05  xor     edx, edx; Val
0x18001ae07  lea     rcx, [rbp+1280h+FileName]; void *
0x18001ae0e  mov     r8d, 20Ah; Size
0x18001ae14  call    memset_0
0x18001ae19  xor     eax, eax
0x18001ae1b  lea     rcx, [rbp+1280h+var_1290+2]; void *
0x18001ae1f  xorps   xmm0, xmm0
0x18001ae22  mov     [rbp+1280h+InBuffer], rax
0x18001ae26  xor     r12d, r12d
0x18001ae29  mov     [rbp+1280h+var_12F0], eax
0x18001ae2c  xor     edx, edx; Val
0x18001ae2e  mov     [rbp+1280h+var_12E8], rax
0x18001ae32  mov     r8d, 1036h; Size
0x18001ae38  mov     [rbp+1280h+var_12E0], eax
0x18001ae3b  movups  [rbp+1280h+OutBuffer], xmm0
0x18001ae3f  mov     word ptr [rbp+1280h+var_1290], r12w
0x18001ae44  movups  [rbp+1280h+var_12C8], xmm0
0x18001ae48  call    memset_0
0x18001ae4d  xor     eax, eax
0x18001ae4f  mov     [rsp+1380h+BytesReturned], r12d
0x18001ae54  mov     [rbp+1280h+var_1298], rax
0x18001ae58  xorps   xmm0, xmm0
0x18001ae5b  mov     [rsp+1380h+var_133C], r12d
0x18001ae60  mov     eax, 1D3h
0x18001ae65  mov     [rsp+1380h+var_1338], r12d
0x18001ae6a  movups  [rbp+1280h+var_12B8], xmm0
0x18001ae6e  movups  [rbp+1280h+var_12A8], xmm0
0x18001ae72  test    rdi, rdi
0x18001ae75  jnz     short loc_18001AEBB
0x18001ae77  mov     ebx, 80070057h
0x18001ae7c  mov     [rsp+1380h+var_1330], ebx
0x18001ae80  mov     [rsp+1380h+var_132A], ax
0x18001ae85  lea     rcx, [rsp+1380h+var_1330]; this
0x18001ae8a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ae8f  mov     eax, ebx
0x18001ae91  mov     rcx, [rbp+1280h+var_40]
0x18001ae98  xor     rcx, rsp; StackCookie
0x18001ae9b  call    __security_check_cookie
0x18001aea0  mov     rbx, [rsp+1380h+arg_10]
0x18001aea8  add     rsp, 1350h
0x18001aeaf  pop     r15
0x18001aeb1  pop     r14
0x18001aeb3  pop     r13
0x18001aeb5  pop     r12
0x18001aeb7  pop     rdi
0x18001aeb8  pop     rsi
0x18001aeb9  pop     rbp
0x18001aeba  retn
0x18001aebb  mov     r9d, r15d
0x18001aebe  mov     [rdi], r12d
0x18001aec1  lea     r8, aPhysicaldriveL; "\\\\?\\PhysicalDrive%ld"
0x18001aec8  mov     [rsp+1380h+var_1330], r12d
0x18001aecd  mov     edx, 105h; unsigned __int64
0x18001aed2  mov     [rsp+1380h+var_132C], ax
0x18001aed7  lea     rcx, [rbp+1280h+FileName]; unsigned __int16 *
0x18001aede  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001aee3  mov     ebx, eax
0x18001aee5  mov     [rsp+1380h+var_1330], eax
0x18001aee9  test    eax, eax
0x18001aeeb  mov     eax, 1DAh
0x18001aef0  js      short loc_18001AE80
0x18001aef2  mov     r13d, 3
0x18001aef8  mov     [rsp+1380h+hTemplateFile], r12; hTemplateFile
0x18001aefd  mov     r8d, r13d; dwShareMode
0x18001af00  mov     [rsp+1380h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001af05  xor     r9d, r9d; lpSecurityAttributes
0x18001af08  mov     [rsp+1380h+var_132C], ax
0x18001af0d  mov     edx, 0C0000000h; dwDesiredAccess
0x18001af12  mov     [rsp+1380h+dwCreationDisposition], r13d; dwCreationDisposition
0x18001af17  lea     rcx, [rbp+1280h+FileName]; lpFileName
0x18001af1e  call    cs:__imp_CreateFileW
0x18001af24  mov     r14, rax
0x18001af27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001af2b  jz      loc_18001B0A8
0x18001af31  mov     [rsp+1380h+lpOverlapped], r12; lpOverlapped
0x18001af36  lea     ebx, [r13-2]
0x18001af3a  mov     eax, 1E3h
0x18001af3f  mov     [rsp+1380h+var_1330], r12d
0x18001af44  mov     [rsp+1380h+var_132C], ax
0x18001af49  lea     r9d, [r13+9]; nInBufferSize
0x18001af4d  lea     rax, [rsp+1380h+BytesReturned]
0x18001af52  mov     [rbp+1280h+InBuffer], rbx
0x18001af56  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18001af5b  lea     r8, [rbp+1280h+InBuffer]; lpInBuffer
0x18001af5f  lea     rax, [rbp+1280h+OutBuffer]
0x18001af63  mov     [rsp+1380h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18001af6b  mov     edx, 2D1400h; dwIoControlCode
0x18001af70  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18001af75  mov     rcx, r14; hDevice
0x18001af78  mov     esi, r12d
0x18001af7b  call    cs:__imp_DeviceIoControl
0x18001af81  test    eax, eax
0x18001af83  jnz     loc_18001B0C4
0x18001af89  xorps   xmm0, xmm0
0x18001af8c  movups  [rbp+1280h+OutBuffer], xmm0
0x18001af90  movups  [rbp+1280h+var_12C8], xmm0
0x18001af94  mov     al, byte ptr [rbp+1280h+var_12C8+8]
0x18001af97  cmp     al, 0Fh
0x18001af99  jnz     loc_18001B0E4
0x18001af9f  mov     rdx, rdi; enum DF_DEVICE_TYPE *
0x18001afa2  lea     rcx, [rbp+1280h+FileName]; lpFileName
0x18001afa9  call    ?SxQueryDeviceTypeVirtualDiskSub@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z; SxQueryDeviceTypeVirtualDiskSub(ushort const *,DF_DEVICE_TYPE *)
0x18001afae  test    eax, eax
0x18001afb0  jns     loc_18001B0DD
0x18001afb6  mov     [rsp+1380h+lpOverlapped], r12; lpOverlapped
0x18001afbb  lea     rax, [rsp+1380h+BytesReturned]
0x18001afc0  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18001afc5  lea     r8, [rbp+1280h+InBuffer]; lpInBuffer
0x18001afc9  lea     rax, [rbp+1280h+var_12B8]
0x18001afcd  mov     [rsp+1380h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x18001afd5  mov     r9d, 0Ch; nInBufferSize
0x18001afdb  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18001afe0  mov     edx, 2D1400h; dwIoControlCode
0x18001afe5  mov     [rbp+1280h+InBuffer], 0Bh
0x18001afed  mov     rcx, r14; hDevice
0x18001aff0  call    cs:__imp_DeviceIoControl
0x18001aff6  test    eax, eax
0x18001aff8  jnz     loc_18001B0EE
0x18001affe  lea     rdx, [rsp+1380h+var_133C]; int *
0x18001b003  mov     rcx, r14; hDevice
0x18001b006  call    ?SxCheckTrimSupport@@YAJPEAXPEAH@Z; SxCheckTrimSupport(void *,int *)
0x18001b00b  mov     ebx, eax
0x18001b00d  mov     [rsp+1380h+var_1330], eax
0x18001b011  test    eax, eax
0x18001b013  mov     eax, 230h
0x18001b018  js      loc_18001B0BD
0x18001b01e  mov     ebx, [rsp+1380h+var_133C]
0x18001b022  mov     [rsp+1380h+var_132C], ax
0x18001b027  test    ebx, ebx
0x18001b029  jz      short loc_18001B071
0x18001b02b  mov     [rsp+1380h+lpOverlapped], r12; lpOverlapped
0x18001b030  lea     rax, [rsp+1380h+BytesReturned]
0x18001b035  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18001b03a  lea     r8, [rbp+1280h+InBuffer]; lpInBuffer
0x18001b03e  mov     ecx, 0Ch
0x18001b043  mov     [rbp+1280h+InBuffer], 7
0x18001b04b  mov     [rsp+1380h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18001b04f  lea     rax, [rbp+1280h+var_12E8]
0x18001b053  mov     r9d, ecx; nInBufferSize
0x18001b056  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18001b05b  mov     rcx, r14; hDevice
0x18001b05e  mov     edx, 2D1400h; dwIoControlCode
0x18001b063  call    cs:__imp_DeviceIoControl
0x18001b069  test    eax, eax
0x18001b06b  jnz     loc_18001B15C
0x18001b071  test    esi, esi
0x18001b073  jz      loc_18001B1C4
0x18001b079  mov     dword ptr [rdi], 6
0x18001b07f  mov     eax, 25Eh
0x18001b084  mov     ebx, r12d
0x18001b087  mov     [rsp+1380h+var_132C], ax
0x18001b08c  mov     [rsp+1380h+var_1330], r12d
0x18001b091  test    r14, r14
0x18001b094  jz      loc_18001AE85
0x18001b09a  mov     rcx, r14; hObject
0x18001b09d  call    cs:__imp_CloseHandle
0x18001b0a3  jmp     loc_18001AE85
0x18001b0a8  call    GetLastFailureAsHRESULT
0x18001b0ad  mov     ebx, eax
0x18001b0af  mov     [rsp+1380h+var_1330], eax
0x18001b0b3  mov     eax, 1E3h
0x18001b0b8  jmp     loc_18001AE80
0x18001b0bd  mov     [rsp+1380h+var_132A], ax
0x18001b0c2  jmp     short loc_18001B091
0x18001b0c4  cmp     dword ptr [rbp+1280h+OutBuffer], 20h ; ' '
0x18001b0c8  jnz     loc_18001AF89
0x18001b0ce  cmp     dword ptr [rbp+1280h+OutBuffer+4], 20h ; ' '
0x18001b0d2  jz      loc_18001AF94
0x18001b0d8  jmp     loc_18001AF89
0x18001b0dd  mov     eax, 206h
0x18001b0e2  jmp     short loc_18001B084
0x18001b0e4  cmp     al, 10h
0x18001b0e6  cmovz   esi, ebx
0x18001b0e9  jmp     loc_18001AFB6
0x18001b0ee  cmp     dword ptr [rbp+1280h+var_12B8], 28h ; '('
0x18001b0f2  jnz     loc_18001AFFE
0x18001b0f8  cmp     dword ptr [rbp+1280h+var_12B8+4], 28h ; '('
0x18001b0fc  jnz     loc_18001AFFE
0x18001b102  test    byte ptr [rbp+1280h+var_12B8+8], bl
0x18001b105  jz      loc_18001AFFE
0x18001b10b  cmp     qword ptr [rbp+1280h+var_12A8], r12
0x18001b10f  jbe     loc_18001AFFE
0x18001b115  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b11c  lea     rax, WPP_GLOBAL_Control
0x18001b123  cmp     rcx, rax
0x18001b126  jz      short loc_18001B149
0x18001b128  test    dword ptr [rcx+1Ch], 10000000h
0x18001b12f  jz      short loc_18001B149
0x18001b131  mov     rcx, [rcx+10h]
0x18001b135  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18001b13c  mov     edx, 0Bh
0x18001b141  mov     r9d, r15d
0x18001b144  call    WPP_SF_d
0x18001b149  lea     eax, ds:5[rsi*2]
0x18001b150  mov     [rdi], eax
0x18001b152  mov     eax, 22Ch
0x18001b157  jmp     loc_18001B084
0x18001b15c  cmp     dword ptr [rbp+1280h+var_12E8], 0Ch
0x18001b160  jnz     loc_18001B071
0x18001b166  cmp     dword ptr [rbp+1280h+var_12E8+4], 0Ch
0x18001b16a  jnz     loc_18001B071
0x18001b170  cmp     byte ptr [rbp+1280h+var_12E0], r12b
0x18001b174  jnz     loc_18001B071
0x18001b17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b181  lea     rax, WPP_GLOBAL_Control
0x18001b188  cmp     rcx, rax
0x18001b18b  jz      short loc_18001B1AE
0x18001b18d  test    dword ptr [rcx+1Ch], 10000000h
0x18001b194  jz      short loc_18001B1AE
0x18001b196  mov     rcx, [rcx+10h]
0x18001b19a  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18001b1a1  mov     edx, 0Ch
0x18001b1a6  mov     r9d, r15d
0x18001b1a9  call    WPP_SF_d
0x18001b1ae  neg     esi
0x18001b1b0  sbb     eax, eax
0x18001b1b2  and     eax, 9
0x18001b1b5  add     eax, r13d
0x18001b1b8  mov     [rdi], eax
0x18001b1ba  mov     eax, 257h
0x18001b1bf  jmp     loc_18001B084
0x18001b1c4  test    ebx, ebx
0x18001b1c6  jnz     short loc_18001B1D8
0x18001b1c8  mov     dword ptr [rdi], 1
0x18001b1ce  mov     eax, 26Bh
0x18001b1d3  jmp     loc_18001B084
0x18001b1d8  mov     al, byte ptr [rbp+1280h+var_12C8+8]
0x18001b1db  sub     al, r13b
0x18001b1de  test    al, 0F7h
0x18001b1e0  jnz     loc_18001B28D
0x18001b1e6  mov     [rsp+1380h+lpOverlapped], r12; lpOverlapped
0x18001b1eb  lea     rax, [rsp+1380h+BytesReturned]
0x18001b1f0  mov     [rsp+1380h+hTemplateFile], rax; lpBytesReturned
0x18001b1f5  lea     r8, [rbp+1280h+var_1290]; lpInBuffer
0x18001b1f9  mov     r9d, 1038h; nInBufferSize
0x18001b1ff  mov     [rbp+1280h+var_1290], 30030h
0x18001b206  lea     rax, [rbp+1280h+var_1290]
0x18001b20a  mov     [rsp+1380h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x18001b20f  mov     edx, 4D02Ch; dwIoControlCode
0x18001b214  mov     qword ptr [rsp+1380h+dwCreationDisposition], rax; lpOutBuffer
0x18001b219  mov     rcx, r14; hDevice
0x18001b21c  mov     [rbp+1280h+var_1288], 200h
0x18001b223  mov     [rbp+1280h+var_1284], 0Ah
0x18001b22a  mov     [rbp+1280h+var_1278], 38h ; '8'
0x18001b232  mov     [rbp+1280h+var_1262], 0ECh
0x18001b236  call    cs:__imp_DeviceIoControl
0x18001b23c  mov     ebx, 1
0x18001b241  test    eax, eax
0x18001b243  jz      short loc_18001B292
0x18001b245  cmp     [rbp+1280h+var_10A6], bx
0x18001b24c  jnz     short loc_18001B292
0x18001b24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b255  lea     rax, WPP_GLOBAL_Control
0x18001b25c  cmp     rcx, rax
0x18001b25f  jz      short loc_18001B280
0x18001b261  test    dword ptr [rcx+1Ch], 10000000h
0x18001b268  jz      short loc_18001B280
0x18001b26a  mov     rcx, [rcx+10h]
0x18001b26e  lea     edx, [rbx+0Ch]
0x18001b271  mov     r9d, r15d
0x18001b274  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18001b27b  call    WPP_SF_d
0x18001b280  mov     [rdi], r13d
0x18001b283  mov     eax, 28Dh
0x18001b288  jmp     loc_18001B084
0x18001b28d  mov     ebx, 1
0x18001b292  lea     rdx, [rsp+1380h+var_1338]; unsigned int *
0x18001b297  mov     ecx, r15d; unsigned int
0x18001b29a  call    ?SxQueryDeviceRandomReadDiskScore@@YAJKPEAK@Z; SxQueryDeviceRandomReadDiskScore(ulong,ulong *)
0x18001b29f  test    eax, eax
0x18001b2a1  js      short loc_18001B2EE
0x18001b2a3  cmp     [rsp+1380h+var_1338], 20001h
0x18001b2ab  jb      short loc_18001B2EE
0x18001b2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2b4  lea     rax, WPP_GLOBAL_Control
0x18001b2bb  cmp     rcx, rax
0x18001b2be  jz      short loc_18001B2E1
0x18001b2c0  test    dword ptr [rcx+1Ch], 10000000h
  ... truncated ...
```
