# SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)

- ea: `0x1800197a8`
- end: `0x180019adc`
- name: `?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _VOLUME_DISK_EXTENTS **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800130c8`
- `0x1800391fc`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180017e34`
- `0x1800192b4`
- `0x1800197a8`
- `0x180019ae4`
- `0x18001a630`
- `0x180067af2`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001994f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001994f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800199a1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019a25`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800199a1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019848`

## pseudocode

```c
__int64 __fastcall SxGetDiskExts(unsigned __int16 *a1, struct _VOLUME_DISK_EXTENTS **a2)
{
  void *dwFlagsAndAttributes; // r9
  WCHAR *v5; // r12
  __int64 FileW; // rbx
  struct _VOLUME_DISK_EXTENTS *v7; // r13
  __int16 v8; // ax
  unsigned int v9; // edi
  __int64 v11; // rsi
  int v12; // r15d
  int v13; // eax
  int v14; // r14d
  WCHAR *v15; // rdi
  int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  DWORD v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  DWORD BytesReturned; // [rsp+40h] [rbp-69h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-61h] BYREF
  __int64 v33; // [rsp+50h] [rbp-59h]
  int LastFailureAsHRESULT; // [rsp+58h] [rbp-51h] BYREF
  __int16 v35; // [rsp+5Ch] [rbp-4Dh]
  __int16 v36; // [rsp+5Eh] [rbp-4Bh]
  void *Src; // [rsp+90h] [rbp-19h]
  struct _VOLUME_DISK_EXTENTS **v38; // [rsp+98h] [rbp-11h]
  _OWORD OutBuffer[2]; // [rsp+A0h] [rbp-9h] BYREF

  v38 = a2;
  Src = a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetDiskExts", 2441, 1);
  dwFlagsAndAttributes = 0;
  v5 = (WCHAR *)&qword_18006F470;
  BytesReturned = 0;
  lpFileName = &qword_18006F470;
  v33 = 0;
  FileW = -1;
  v7 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( a2 )
    *a2 = 0;
  v8 = 2451;
  if ( !a1 || (v35 = 2451, v8 = 2452, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_5:
    v36 = v8;
    goto LABEL_6;
  }
  LastFailureAsHRESULT = 0;
  v35 = 2452;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  v12 = 0;
  if ( (_DWORD)v11
    && (v13 = CBsString::ExtendBuffer((CBsString *)&lpFileName, (int)v11 + 1),
        v5 = (WCHAR *)lpFileName,
        dwFlagsAndAttributes = 0,
        v12 = v13,
        v13 >= 0) )
  {
    v14 = v33;
    v15 = (WCHAR *)&lpFileName[(unsigned int)v33];
    memcpy_0(v15, Src, 2LL * (unsigned int)v11);
    dwFlagsAndAttributes = 0;
    v16 = v11 + v14;
    v15[(unsigned int)v11] = 0;
    LODWORD(v33) = v16;
    LastFailureAsHRESULT = v12;
  }
  else
  {
    LastFailureAsHRESULT = v12;
    if ( v12 < 0 )
    {
      v8 = 2454;
      goto LABEL_5;
    }
    v16 = v33;
  }
  v35 = 2454;
  if ( v16 )
  {
    v26 = (unsigned int)(v16 - 1);
    if ( v5[v26] == 92 )
    {
      CBsString::SetLength((CBsString *)&lpFileName, v26);
      v5 = (WCHAR *)lpFileName;
    }
  }
  FileW = (__int64)CreateFileW(v5, 0, 3u, 0, 3u, (DWORD)dwFlagsAndAttributes, dwFlagsAndAttributes);
  if ( FileW == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18, v17, v19, v20);
    v8 = 2464;
    goto LABEL_5;
  }
  v35 = 2464;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) && GetLastError() != 234 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28, v27, v29, v30);
    v8 = 2475;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v35 = 2475;
  v21 = 24 * LODWORD(OutBuffer[0]) + 8;
  v7 = (struct _VOLUME_DISK_EXTENTS *)CoTaskMemAlloc(v21);
  v8 = 2480;
  if ( !v7 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_5;
  }
  v35 = 2480;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v7, v21, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v23, v22, v24, v25);
    v8 = 2489;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v35 = 2489;
  v8 = 2490;
  if ( !v7->NumberOfDiskExtents )
  {
    LastFailureAsHRESULT = -2147418113;
    goto LABEL_5;
  }
  v35 = 2490;
  *v38 = v7;
  v7 = 0;
LABEL_6:
  CoTaskMemFree(v7);
  v9 = LastFailureAsHRESULT;
  CBsString::_FreeData(v5);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1800197a8  mov     [rsp-8+arg_10], rbx
0x1800197ad  push    rbp
0x1800197ae  push    rsi
0x1800197af  push    rdi
0x1800197b0  push    r12
0x1800197b2  push    r13
0x1800197b4  push    r14
0x1800197b6  push    r15
0x1800197b8  lea     rbp, [rsp-27h]
0x1800197bd  sub     rsp, 0D0h
0x1800197c4  mov     rax, cs:__security_cookie
0x1800197cb  xor     rax, rsp
0x1800197ce  mov     [rbp+57h+var_40], rax
0x1800197d2  mov     rsi, rdx
0x1800197d5  mov     [rbp+57h+var_68], rdx
0x1800197d9  mov     rdi, rcx
0x1800197dc  mov     [rbp+57h+Src], rcx
0x1800197e0  lea     rdx, aSxgetdiskexts; "SxGetDiskExts"
0x1800197e7  mov     r9d, 1; unsigned __int16
0x1800197ed  lea     rcx, [rbp+57h+var_A8]; this
0x1800197f1  mov     r8d, 989h; unsigned __int16
0x1800197f7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800197fc  xor     r9d, r9d
0x1800197ff  lea     r12, qword_18006F470
0x180019806  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001980a  mov     [rbp+57h+BytesReturned], r9d
0x18001980e  mov     [rbp+57h+lpFileName], r12
0x180019812  xorps   xmm0, xmm0
0x180019815  mov     [rbp+57h+var_B0], r9
0x180019819  mov     rbx, rcx
0x18001981c  mov     r13d, r9d
0x18001981f  movups  [rbp+57h+OutBuffer], xmm0
0x180019823  movups  [rbp+57h+var_50], xmm0
0x180019827  test    rsi, rsi
0x18001982a  jnz     loc_180019A85
0x180019830  mov     eax, 993h
0x180019835  test    rdi, rdi
0x180019838  jnz     short loc_180019899
0x18001983a  mov     [rbp+57h+var_A8], 80070057h
0x180019841  mov     [rbp+57h+var_A2], ax
0x180019845  mov     rcx, r13; pv
0x180019848  call    cs:__imp_CoTaskMemFree
0x18001984e  mov     edi, [rbp+57h+var_A8]
0x180019851  mov     rcx, r12; unsigned __int16 *
0x180019854  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180019859  lea     rdx, [rbx-1]
0x18001985d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019861  jbe     loc_180019A59
0x180019867  lea     rcx, [rbp+57h+var_A8]; this
0x18001986b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019870  mov     eax, edi
0x180019872  mov     rcx, [rbp+57h+var_40]
0x180019876  xor     rcx, rsp; StackCookie
0x180019879  call    __security_check_cookie
0x18001987e  mov     rbx, [rsp+100h+arg_10]
0x180019886  add     rsp, 0D0h
0x18001988d  pop     r15
0x18001988f  pop     r14
0x180019891  pop     r13
0x180019893  pop     r12
0x180019895  pop     rdi
0x180019896  pop     rsi
0x180019897  pop     rbp
0x180019898  retn
0x180019899  mov     [rbp+57h+var_A4], ax
0x18001989d  mov     eax, 994h
0x1800198a2  test    rsi, rsi
0x1800198a5  jz      short loc_18001983A
0x1800198a7  mov     [rbp+57h+var_A8], r9d
0x1800198ab  mov     [rbp+57h+var_A4], ax
0x1800198af  mov     rsi, rcx
0x1800198b2  inc     rsi
0x1800198b5  cmp     [rdi+rsi*2], r9w
0x1800198ba  jnz     short loc_1800198B2
0x1800198bc  mov     r15d, r9d
0x1800198bf  test    esi, esi
0x1800198c1  jz      short loc_18001990F
0x1800198c3  lea     edx, [rsi+1]; unsigned int
0x1800198c6  lea     rcx, [rbp+57h+lpFileName]; this
0x1800198ca  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800198cf  mov     r12, [rbp+57h+lpFileName]
0x1800198d3  xor     r9d, r9d
0x1800198d6  mov     r15d, eax
0x1800198d9  test    eax, eax
0x1800198db  js      short loc_18001990F
0x1800198dd  mov     r14d, dword ptr [rbp+57h+var_B0]
0x1800198e1  mov     rdx, [rbp+57h+Src]; Src
0x1800198e5  mov     ecx, esi
0x1800198e7  lea     rdi, [r12+r14*2]
0x1800198eb  lea     rbx, [rcx+rcx]
0x1800198ef  mov     rcx, rdi; void *
0x1800198f2  mov     r8, rbx; Size
0x1800198f5  call    memcpy_0
0x1800198fa  xor     r9d, r9d
0x1800198fd  add     r14d, esi
0x180019900  mov     [rbx+rdi], r9w
0x180019905  mov     dword ptr [rbp+57h+var_B0], r14d
0x180019909  mov     [rbp+57h+var_A8], r15d
0x18001990d  jmp     short loc_180019920
0x18001990f  mov     [rbp+57h+var_A8], r15d
0x180019913  test    r15d, r15d
0x180019916  js      loc_180019A8D
0x18001991c  mov     r14d, dword ptr [rbp+57h+var_B0]
0x180019920  mov     eax, 996h
0x180019925  mov     [rbp+57h+var_A4], ax
0x180019929  test    r14d, r14d
0x18001992c  jnz     loc_180019A97
0x180019932  mov     [rsp+100h+hTemplateFile], r9; hTemplateFile
0x180019937  mov     r8d, 3; dwShareMode
0x18001993d  mov     [rsp+100h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x180019942  xor     edx, edx; dwDesiredAccess
0x180019944  xor     r9d, r9d; lpSecurityAttributes
0x180019947  mov     [rsp+100h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001994c  mov     rcx, r12; lpFileName
0x18001994f  call    cs:__imp_CreateFileW
0x180019955  mov     rbx, rax
0x180019958  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001995c  jz      loc_1800199E9
0x180019962  mov     eax, 9A0h
0x180019967  xor     esi, esi
0x180019969  mov     [rbp+57h+var_A4], ax
0x18001996d  mov     r14d, 560000h
0x180019973  mov     [rsp+100h+lpOverlapped], rsi; lpOverlapped
0x180019978  lea     rax, [rbp+57h+BytesReturned]
0x18001997c  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x180019981  xor     r9d, r9d; nInBufferSize
0x180019984  lea     rax, [rbp+57h+OutBuffer]
0x180019988  mov     [rsp+100h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180019990  xor     r8d, r8d; lpInBuffer
0x180019993  mov     qword ptr [rsp+100h+dwCreationDisposition], rax; lpOutBuffer
0x180019998  mov     edx, r14d; dwIoControlCode
0x18001999b  mov     [rbp+57h+var_A8], esi
0x18001999e  mov     rcx, rbx; hDevice
0x1800199a1  call    cs:__imp_DeviceIoControl
0x1800199a7  test    eax, eax
0x1800199a9  jz      loc_180019AB9
0x1800199af  mov     eax, 9ABh
0x1800199b4  mov     [rbp+57h+var_A8], esi
0x1800199b7  mov     [rbp+57h+var_A4], ax
0x1800199bb  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x1800199be  lea     ecx, [rax+rax*2]
0x1800199c1  lea     edi, ds:8[rcx*8]
0x1800199c8  mov     ecx, edi; cb
0x1800199ca  call    cs:__imp_CoTaskMemAlloc
0x1800199d0  mov     r13, rax
0x1800199d3  test    rax, rax
0x1800199d6  mov     eax, 9B0h
0x1800199db  jnz     short loc_1800199FB
0x1800199dd  mov     [rbp+57h+var_A8], 8007000Eh
0x1800199e4  jmp     loc_180019841
0x1800199e9  call    GetLastFailureAsHRESULT
0x1800199ee  mov     [rbp+57h+var_A8], eax
0x1800199f1  mov     eax, 9A0h
0x1800199f6  jmp     loc_180019841
0x1800199fb  mov     [rsp+100h+lpOverlapped], rsi; lpOverlapped
0x180019a00  xor     r9d, r9d; nInBufferSize
0x180019a03  mov     [rbp+57h+var_A4], ax
0x180019a07  xor     r8d, r8d; lpInBuffer
0x180019a0a  lea     rax, [rbp+57h+BytesReturned]
0x180019a0e  mov     [rbp+57h+var_A8], esi
0x180019a11  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x180019a16  mov     edx, r14d; dwIoControlCode
0x180019a19  mov     [rsp+100h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180019a1d  mov     rcx, rbx; hDevice
0x180019a20  mov     qword ptr [rsp+100h+dwCreationDisposition], r13; lpOutBuffer
0x180019a25  call    cs:__imp_DeviceIoControl
0x180019a2b  test    eax, eax
0x180019a2d  jz      short loc_180019A73
0x180019a2f  mov     eax, 9B9h
0x180019a34  mov     [rbp+57h+var_A8], esi
0x180019a37  mov     [rbp+57h+var_A4], ax
0x180019a3b  mov     eax, 9BAh
0x180019a40  cmp     [r13+0], esi
0x180019a44  jz      short loc_180019A67
0x180019a46  mov     [rbp+57h+var_A4], ax
0x180019a4a  mov     rax, [rbp+57h+var_68]
0x180019a4e  mov     [rax], r13
0x180019a51  mov     r13, rsi
0x180019a54  jmp     loc_180019845
0x180019a59  mov     rcx, rbx; hObject
0x180019a5c  call    cs:__imp_CloseHandle
0x180019a62  jmp     loc_180019867
0x180019a67  mov     [rbp+57h+var_A8], 8000FFFFh
0x180019a6e  jmp     loc_180019841
0x180019a73  call    GetLastFailureAsHRESULT
0x180019a78  mov     [rbp+57h+var_A8], eax
0x180019a7b  mov     eax, 9B9h
0x180019a80  jmp     loc_180019841
0x180019a85  mov     [rsi], r9
0x180019a88  jmp     loc_180019830
0x180019a8d  mov     eax, 996h
0x180019a92  jmp     loc_180019841
0x180019a97  lea     edx, [r14-1]; unsigned int
0x180019a9b  cmp     word ptr [r12+rdx*2], 5Ch ; '\'
0x180019aa1  jnz     loc_180019932
0x180019aa7  lea     rcx, [rbp+57h+lpFileName]; this
0x180019aab  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x180019ab0  mov     r12, [rbp+57h+lpFileName]
0x180019ab4  jmp     loc_180019932
0x180019ab9  call    cs:__imp_GetLastError
0x180019abf  cmp     eax, 0EAh
0x180019ac4  jz      loc_1800199AF
0x180019aca  call    GetLastFailureAsHRESULT
0x180019acf  mov     [rbp+57h+var_A8], eax
0x180019ad2  mov     eax, 9ABh
0x180019ad7  jmp     loc_180019841
```
