# SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)

- ea: `0x1801adb3c`
- end: `0x1801adde0`
- name: `?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _VOLUME_DISK_EXTENTS **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801ae820`
- `0x1801afd08`

## callees

- `0x180006350`
- `0x1801adb3c`
- `0x1801af258`
- `0x1801b0b88`
- `0x1801b0c38`
- `0x1801b0e90`
- `0x1801b0ec0`
- `0x1801b0fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801adc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801adc98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801adda5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801adda5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801add80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801add80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801adcdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801adcdb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801adc88`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801add2e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801adc88`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801add2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801adc27`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801adc27`

## pseudocode

```c
__int64 __fastcall SxGetDiskExts(const unsigned __int16 *a1, struct _VOLUME_DISK_EXTENTS **a2)
{
  __int64 FileW; // rbx
  struct _VOLUME_DISK_EXTENTS *v5; // rdi
  __int16 v6; // ax
  unsigned __int16 v7; // dx
  DWORD v8; // r14d
  unsigned int v9; // edi
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-41h] BYREF
  __int16 v13; // [rsp+4Ch] [rbp-3Dh]
  __int16 v14; // [rsp+4Eh] [rbp-3Bh]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-9h] BYREF
  _OWORD OutBuffer[2]; // [rsp+90h] [rbp+7h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetDiskExts", 0x989u, 1u);
  lpFileName[0] = (LPCWSTR)qword_1802E5D80;
  FileW = -1;
  BytesReturned = 0;
  lpFileName[1] = 0;
  v5 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( a2 )
    *a2 = 0;
  v6 = 2451;
  if ( !a1 || (v13 = 2451, v6 = 2452, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_5:
    v14 = v6;
    goto LABEL_20;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2452;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a1);
  v6 = 2454;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_5;
  v13 = 2454;
  CBsString::UnTrailing((CBsString *)lpFileName, v7);
  FileW = (__int64)CreateFileW(lpFileName[0], 0, 3u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2464;
    goto LABEL_5;
  }
  v13 = 2464;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) && GetLastError() != 234 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2475;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2475;
  v8 = 24 * LODWORD(OutBuffer[0]) + 8;
  v5 = (struct _VOLUME_DISK_EXTENTS *)CoTaskMemAlloc(v8);
  v6 = 2480;
  if ( !v5 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_5;
  }
  v13 = 2480;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v5, v8, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2489;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2489;
  v6 = 2490;
  if ( !v5->NumberOfDiskExtents )
  {
    LastFailureAsHRESULT = -2147418113;
    goto LABEL_5;
  }
  *a2 = v5;
  v5 = 0;
  v13 = 2490;
LABEL_20:
  CoTaskMemFree(v5);
  v9 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1801adb3c  mov     [rsp-8+arg_10], rbx
0x1801adb41  push    rbp
0x1801adb42  push    rsi
0x1801adb43  push    rdi
0x1801adb44  push    r14
0x1801adb46  push    r15
0x1801adb48  lea     rbp, [rsp-37h]
0x1801adb4d  sub     rsp, 0C0h
0x1801adb54  mov     rax, cs:__security_cookie
0x1801adb5b  xor     rax, rsp
0x1801adb5e  mov     [rbp+57h+var_30], rax
0x1801adb62  mov     rsi, rdx
0x1801adb65  mov     r14, rcx
0x1801adb68  lea     rdx, aSxgetdiskexts; "SxGetDiskExts"
0x1801adb6f  mov     r9d, 1; unsigned __int16
0x1801adb75  lea     rcx, [rbp+57h+var_98]; this
0x1801adb79  mov     r8d, 989h; unsigned __int16
0x1801adb7f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801adb84  xor     r15d, r15d
0x1801adb87  lea     rax, qword_1802E5D80
0x1801adb8e  xorps   xmm0, xmm0
0x1801adb91  mov     [rbp+57h+lpFileName], rax
0x1801adb95  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801adb99  mov     [rbp+57h+BytesReturned], r15d
0x1801adb9d  mov     [rbp+57h+var_58], r15
0x1801adba1  mov     edi, r15d
0x1801adba4  movups  [rbp+57h+OutBuffer], xmm0
0x1801adba8  movups  [rbp+57h+var_40], xmm0
0x1801adbac  test    rsi, rsi
0x1801adbaf  jz      short loc_1801ADBB4
0x1801adbb1  mov     [rsi], r15
0x1801adbb4  mov     eax, 993h
0x1801adbb9  test    r14, r14
0x1801adbbc  jnz     short loc_1801ADBCE
0x1801adbbe  mov     [rbp+57h+var_98], 80070057h
0x1801adbc5  mov     [rbp+57h+var_92], ax
0x1801adbc9  jmp     loc_1801ADD7D
0x1801adbce  mov     [rbp+57h+var_94], ax
0x1801adbd2  mov     eax, 994h
0x1801adbd7  test    rsi, rsi
0x1801adbda  jz      short loc_1801ADBBE
0x1801adbdc  mov     rdx, r14; unsigned __int16 *
0x1801adbdf  mov     [rbp+57h+var_98], r15d
0x1801adbe3  lea     rcx, [rbp+57h+lpFileName]; this
0x1801adbe7  mov     [rbp+57h+var_94], ax
0x1801adbeb  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801adbf0  mov     [rbp+57h+var_98], eax
0x1801adbf3  test    eax, eax
0x1801adbf5  mov     eax, 996h
0x1801adbfa  js      short loc_1801ADBC5
0x1801adbfc  lea     rcx, [rbp+57h+lpFileName]; this
0x1801adc00  mov     [rbp+57h+var_94], ax
0x1801adc04  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801adc09  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1801adc0d  mov     r8d, 3; dwShareMode
0x1801adc13  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x1801adc18  xor     r9d, r9d; lpSecurityAttributes
0x1801adc1b  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801adc20  xor     edx, edx; dwDesiredAccess
0x1801adc22  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801adc27  call    cs:__imp_CreateFileW
0x1801adc2e  nop     dword ptr [rax+rax+00h]
0x1801adc33  mov     rbx, rax
0x1801adc36  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801adc3a  jnz     short loc_1801ADC4E
0x1801adc3c  call    GetLastFailureAsHRESULT
0x1801adc41  mov     [rbp+57h+var_98], eax
0x1801adc44  mov     eax, 9A0h
0x1801adc49  jmp     loc_1801ADBC5
0x1801adc4e  mov     [rsp+0E0h+lpOverlapped], r15; lpOverlapped
0x1801adc53  mov     eax, 9A0h
0x1801adc58  mov     [rbp+57h+var_94], ax
0x1801adc5c  xor     r9d, r9d; nInBufferSize
0x1801adc5f  lea     rax, [rbp+57h+BytesReturned]
0x1801adc63  mov     [rbp+57h+var_98], r15d
0x1801adc67  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1801adc6c  xor     r8d, r8d; lpInBuffer
0x1801adc6f  lea     rax, [rbp+57h+OutBuffer]
0x1801adc73  mov     [rsp+0E0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x1801adc7b  mov     edx, 560000h; dwIoControlCode
0x1801adc80  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x1801adc85  mov     rcx, rbx; hDevice
0x1801adc88  call    cs:__imp_DeviceIoControl
0x1801adc8f  nop     dword ptr [rax+rax+00h]
0x1801adc94  test    eax, eax
0x1801adc96  jnz     short loc_1801ADCBD
0x1801adc98  call    cs:__imp_GetLastError
0x1801adc9f  nop     dword ptr [rax+rax+00h]
0x1801adca4  cmp     eax, 0EAh
0x1801adca9  jz      short loc_1801ADCBD
0x1801adcab  call    GetLastFailureAsHRESULT
0x1801adcb0  mov     [rbp+57h+var_98], eax
0x1801adcb3  mov     eax, 9ABh
0x1801adcb8  jmp     loc_1801ADBC5
0x1801adcbd  mov     eax, 9ABh
0x1801adcc2  mov     [rbp+57h+var_98], r15d
0x1801adcc6  mov     [rbp+57h+var_94], ax
0x1801adcca  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x1801adccd  lea     ecx, [rax+rax*2]
0x1801adcd0  lea     r14d, ds:8[rcx*8]
0x1801adcd8  mov     ecx, r14d; cb
0x1801adcdb  call    cs:__imp_CoTaskMemAlloc
0x1801adce2  nop     dword ptr [rax+rax+00h]
0x1801adce7  mov     rdi, rax
0x1801adcea  test    rax, rax
0x1801adced  mov     eax, 9B0h
0x1801adcf2  jnz     short loc_1801ADD00
0x1801adcf4  mov     [rbp+57h+var_98], 8007000Eh
0x1801adcfb  jmp     loc_1801ADBC5
0x1801add00  mov     [rsp+0E0h+lpOverlapped], r15; lpOverlapped
0x1801add05  xor     r9d, r9d; nInBufferSize
0x1801add08  mov     [rbp+57h+var_94], ax
0x1801add0c  xor     r8d, r8d; lpInBuffer
0x1801add0f  lea     rax, [rbp+57h+BytesReturned]
0x1801add13  mov     [rbp+57h+var_98], r15d
0x1801add17  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1801add1c  mov     edx, 560000h; dwIoControlCode
0x1801add21  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1801add26  mov     rcx, rbx; hDevice
0x1801add29  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rdi; lpOutBuffer
0x1801add2e  call    cs:__imp_DeviceIoControl
0x1801add35  nop     dword ptr [rax+rax+00h]
0x1801add3a  test    eax, eax
0x1801add3c  jnz     short loc_1801ADD50
0x1801add3e  call    GetLastFailureAsHRESULT
0x1801add43  mov     [rbp+57h+var_98], eax
0x1801add46  mov     eax, 9B9h
0x1801add4b  jmp     loc_1801ADBC5
0x1801add50  mov     eax, 9B9h
0x1801add55  mov     [rbp+57h+var_98], r15d
0x1801add59  mov     [rbp+57h+var_94], ax
0x1801add5d  mov     eax, 9BAh
0x1801add62  cmp     [rdi], r15d
0x1801add65  jnz     short loc_1801ADD73
0x1801add67  mov     [rbp+57h+var_98], 8000FFFFh
0x1801add6e  jmp     loc_1801ADBC5
0x1801add73  mov     [rsi], rdi
0x1801add76  mov     rdi, r15
0x1801add79  mov     [rbp+57h+var_94], ax
0x1801add7d  mov     rcx, rdi; pv
0x1801add80  call    cs:__imp_CoTaskMemFree
0x1801add87  nop     dword ptr [rax+rax+00h]
0x1801add8c  mov     edi, [rbp+57h+var_98]
0x1801add8f  lea     rcx, [rbp+57h+lpFileName]; this
0x1801add93  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1801add98  lea     rdx, [rbx-1]
0x1801add9c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801adda0  ja      short loc_1801ADDB1
0x1801adda2  mov     rcx, rbx; hObject
0x1801adda5  call    cs:__imp_CloseHandle
0x1801addac  nop     dword ptr [rax+rax+00h]
0x1801addb1  lea     rcx, [rbp+57h+var_98]; this
0x1801addb5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801addba  mov     eax, edi
0x1801addbc  mov     rcx, [rbp+57h+var_30]
0x1801addc0  xor     rcx, rsp; StackCookie
0x1801addc3  call    __security_check_cookie
0x1801addc8  mov     rbx, [rsp+0E0h+arg_10]
0x1801addd0  add     rsp, 0C0h
0x1801addd7  pop     r15
0x1801addd9  pop     r14
0x1801adddb  pop     rdi
0x1801adddc  pop     rsi
0x1801adddd  pop     rbp
0x1801addde  retn
```
