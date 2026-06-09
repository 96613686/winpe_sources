# SxGetProvisioningParameters(ushort const *,_DEVICE_LB_PROVISIONING_DESCRIPTOR *,ulong)

- ea: `0x18003f608`
- end: `0x18003f7e1`
- name: `?SxGetProvisioningParameters@@YAJPEBGPEAU_DEVICE_LB_PROVISIONING_DESCRIPTOR@@K@Z`
- size: `473`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _DEVICE_LB_PROVISIONING_DESCRIPTOR *lpOutBuffer, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002d220`
- `0x18002e1a4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x180013520`
- `0x18001913c`
- `0x18001a630`
- `0x18003f608`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f6f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f6f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003f763`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003f763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f76d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7b1`

## pseudocode

```c
__int64 __fastcall SxGetProvisioningParameters(
        const unsigned __int16 *a1,
        struct _DEVICE_LB_PROVISIONING_DESCRIPTOR *lpOutBuffer)
{
  __int64 FileW; // rbx
  __int16 v5; // ax
  int LastFailureAsHRESULT; // edi
  unsigned __int16 v7; // dx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-21h] BYREF
  int v16; // [rsp+58h] [rbp-11h] BYREF
  __int16 v17; // [rsp+5Ch] [rbp-Dh]
  __int16 v18; // [rsp+5Eh] [rbp-Bh]
  __int64 InBuffer; // [rsp+90h] [rbp+27h] BYREF
  int v20; // [rsp+98h] [rbp+2Fh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxGetProvisioningParameters", 2384, 1);
  lpFileName[1] = 0;
  InBuffer = 0;
  FileW = -1;
  v20 = 0;
  BytesReturned = 0;
  lpFileName[0] = &qword_18006F470;
  v5 = 2391;
  if ( !a1 || (v17 = 2391, v5 = 2392, !lpOutBuffer) )
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
LABEL_3:
    v18 = v5;
    goto LABEL_14;
  }
  v16 = 0;
  v17 = 2392;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a1);
  v16 = LastFailureAsHRESULT;
  v5 = 2394;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v17 = 2394;
  CBsString::UnTrailing((CBsString *)lpFileName, v7);
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9, v8, v10, v11);
    v16 = LastFailureAsHRESULT;
    v5 = 2406;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 2406;
  InBuffer = 11;
  if ( DeviceIoControl((HANDLE)FileW, 0x2D1400u, &InBuffer, 0xCu, lpOutBuffer, 0x28u, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = v16;
  }
  else
  {
    LastError = GetLastError();
    LastFailureAsHRESULT = LastError;
    if ( LastError > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
    v16 = LastFailureAsHRESULT;
    v5 = 2427;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v17 = 2427;
  }
LABEL_14:
  CBsString::_Release((LPVOID *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003f608  mov     [rsp-8+arg_10], rbx
0x18003f60d  push    rbp
0x18003f60e  push    rsi
0x18003f60f  push    rdi
0x18003f610  lea     rbp, [rsp-47h]
0x18003f615  sub     rsp, 0B0h
0x18003f61c  mov     rax, cs:__security_cookie
0x18003f623  xor     rax, rsp
0x18003f626  mov     [rbp+57h+var_20], rax
0x18003f62a  mov     rsi, rdx
0x18003f62d  mov     rdi, rcx
0x18003f630  lea     rdx, aSxgetprovision; "SxGetProvisioningParameters"
0x18003f637  mov     r9d, 1; unsigned __int16
0x18003f63d  lea     rcx, [rbp+57h+var_68]; this
0x18003f641  mov     r8d, 950h; unsigned __int16
0x18003f647  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003f64c  xor     eax, eax
0x18003f64e  mov     [rbp+57h+var_70], 0
0x18003f656  mov     [rbp+57h+InBuffer], rax
0x18003f65a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003f65e  mov     [rbp+57h+var_28], eax
0x18003f661  mov     [rbp+57h+BytesReturned], eax
0x18003f664  lea     rax, qword_18006F470
0x18003f66b  mov     [rbp+57h+lpFileName], rax
0x18003f66f  mov     eax, 957h
0x18003f674  test    rdi, rdi
0x18003f677  jnz     short loc_18003F68A
0x18003f679  mov     edi, 80070057h
0x18003f67e  mov     [rbp+57h+var_68], edi
0x18003f681  mov     [rbp+57h+var_62], ax
0x18003f685  jmp     loc_18003F79B
0x18003f68a  mov     [rbp+57h+var_64], ax
0x18003f68e  mov     eax, 958h
0x18003f693  test    rsi, rsi
0x18003f696  jz      short loc_18003F679
0x18003f698  mov     rdx, rdi; unsigned __int16 *
0x18003f69b  mov     [rbp+57h+var_68], 0
0x18003f6a2  lea     rcx, [rbp+57h+lpFileName]; this
0x18003f6a6  mov     [rbp+57h+var_64], ax
0x18003f6aa  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003f6af  mov     edi, eax
0x18003f6b1  mov     [rbp+57h+var_68], eax
0x18003f6b4  test    eax, eax
0x18003f6b6  mov     eax, 95Ah
0x18003f6bb  js      short loc_18003F681
0x18003f6bd  lea     rcx, [rbp+57h+lpFileName]; this
0x18003f6c1  mov     [rbp+57h+var_64], ax
0x18003f6c5  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x18003f6ca  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18003f6ce  mov     r8d, 3; dwShareMode
0x18003f6d4  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18003f6dd  xor     r9d, r9d; lpSecurityAttributes
0x18003f6e0  mov     [rsp+0C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003f6e8  mov     edx, 0C0000000h; dwDesiredAccess
0x18003f6ed  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003f6f2  call    cs:__imp_CreateFileW
0x18003f6f8  mov     rbx, rax
0x18003f6fb  inc     rax
0x18003f6fe  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003f704  jnz     short loc_18003F71A
0x18003f706  call    GetLastFailureAsHRESULT
0x18003f70b  mov     edi, eax
0x18003f70d  mov     [rbp+57h+var_68], eax
0x18003f710  mov     eax, 966h
0x18003f715  jmp     loc_18003F681
0x18003f71a  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x18003f723  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18003f727  mov     eax, 966h
0x18003f72c  mov     [rbp+57h+var_68], 0
0x18003f733  mov     [rbp+57h+var_64], ax
0x18003f737  mov     r9d, 0Ch; nInBufferSize
0x18003f73d  lea     rax, [rbp+57h+BytesReturned]
0x18003f741  mov     [rbp+57h+InBuffer], 0Bh
0x18003f749  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x18003f74e  mov     edx, 2D1400h; dwIoControlCode
0x18003f753  mov     [rsp+0C0h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x18003f75b  mov     rcx, rbx; hDevice
0x18003f75e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi; lpOutBuffer
0x18003f763  call    cs:__imp_DeviceIoControl
0x18003f769  test    eax, eax
0x18003f76b  jnz     short loc_18003F798
0x18003f76d  call    cs:__imp_GetLastError
0x18003f773  mov     edi, eax
0x18003f775  test    eax, eax
0x18003f777  jle     short loc_18003F782
0x18003f779  movzx   edi, ax
0x18003f77c  or      edi, 80070000h
0x18003f782  mov     [rbp+57h+var_68], edi
0x18003f785  mov     eax, 97Bh
0x18003f78a  test    edi, edi
0x18003f78c  js      loc_18003F681
0x18003f792  mov     [rbp+57h+var_64], ax
0x18003f796  jmp     short loc_18003F79B
0x18003f798  mov     edi, [rbp+57h+var_68]
0x18003f79b  lea     rcx, [rbp+57h+lpFileName]; this
0x18003f79f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003f7a4  lea     rcx, [rbx-1]
0x18003f7a8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003f7ac  ja      short loc_18003F7B7
0x18003f7ae  mov     rcx, rbx; hObject
0x18003f7b1  call    cs:__imp_CloseHandle
0x18003f7b7  lea     rcx, [rbp+57h+var_68]; this
0x18003f7bb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003f7c0  mov     eax, edi
0x18003f7c2  mov     rcx, [rbp+57h+var_20]
0x18003f7c6  xor     rcx, rsp; StackCookie
0x18003f7c9  call    __security_check_cookie
0x18003f7ce  mov     rbx, [rsp+0C0h+arg_10]
0x18003f7d6  add     rsp, 0B0h
0x18003f7dd  pop     rdi
0x18003f7de  pop     rsi
0x18003f7df  pop     rbp
0x18003f7e0  retn
```
