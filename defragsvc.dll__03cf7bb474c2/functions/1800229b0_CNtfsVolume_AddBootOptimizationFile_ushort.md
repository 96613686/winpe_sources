# CNtfsVolume::AddBootOptimizationFile(ushort *)

- ea: `0x1800229b0`
- end: `0x180022c51`
- name: `?AddBootOptimizationFile@CNtfsVolume@@UEAAJPEAG@Z`
- size: `673`
- prototype: `__int64 __fastcall(CNtfsVolume *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800229b0`
- `0x18004bbb0`
- `0x180062164`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a4c`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180022a66`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180022a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022abe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022abe`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::AddBootOptimizationFile(CNtfsVolume *this, unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax
  void *v6; // rbx
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r10
  _WORD *v11; // rcx
  __int16 v13; // ax
  char LastError; // al
  int v15; // edx
  int v16; // r8d
  int v17; // [rsp+40h] [rbp-39h] BYREF
  __int16 v18; // [rsp+44h] [rbp-35h]
  __int16 v19; // [rsp+46h] [rbp-33h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-1h] BYREF

  v4 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CNtfsVolume::AddBootOptimizationFile", 759, 1);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !a2 )
  {
    v4 = -2147024809;
    v17 = -2147024809;
    v19 = 765;
    goto LABEL_13;
  }
  v17 = 0;
  v18 = 765;
  FileW = CreateFileW(a2, 0x100080u, 0, 0, 3u, 0x2200000u, 0);
  v6 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      v7 = *((_QWORD *)this + 16);
      v8 = FileInformation.nFileSizeHigh | (unsigned __int64)FileInformation.nFileSizeLow;
      if ( v7 && v8 > v7 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_SII(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            v8,
            (_DWORD)a2,
            LOBYTE(FileInformation.nFileSizeHigh) | LOBYTE(FileInformation.nFileSizeLow),
            *((_QWORD *)this + 16));
        }
        v13 = 831;
      }
      else
      {
        v9 = *((_QWORD *)this + 17);
        if ( !v9 || (v10 = v8 + *((_QWORD *)this + 18), v10 <= v9) )
        {
          *((_QWORD *)this + 18) += v8;
          v11 = CoTaskMemAlloc(0x10u);
          if ( !v11 )
          {
            v4 = -2147024882;
            v19 = 803;
            goto LABEL_10;
          }
          v18 = 803;
          v17 = 0;
          v11[2] = FileInformation.nFileIndexHigh;
          *(_DWORD *)v11 = FileInformation.nFileIndexLow;
          v11[3] = FileInformation.nFileIndexHigh >> 20;
          *((_QWORD *)v11 + 1) = *((_QWORD *)this + 72);
          *((_QWORD *)this + 72) = v11;
          goto LABEL_15;
        }
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_SII(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v8, (_DWORD)a2, v10, *((_QWORD *)this + 17));
        }
        v13 = 820;
      }
      v18 = v13;
LABEL_10:
      v17 = v4;
      if ( v6 )
        CloseHandle(v6);
      goto LABEL_13;
    }
LABEL_15:
    if ( v6 )
      CloseHandle(v6);
    v4 = v17;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (_DWORD)a2, LastError);
  }
  v17 = 1;
  v18 = 783;
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v4;
}

```

## disassembly

```asm
0x1800229b0  mov     [rsp-8+arg_10], rbx
0x1800229b5  mov     [rsp-8+arg_18], rsi
0x1800229ba  push    rbp
0x1800229bb  push    rdi
0x1800229bc  push    r14
0x1800229be  lea     rbp, [rsp-47h]
0x1800229c3  sub     rsp, 0C0h
0x1800229ca  mov     rax, cs:__security_cookie
0x1800229d1  xor     rax, rsp
0x1800229d4  mov     [rbp+57h+var_20], rax
0x1800229d8  mov     r14, rdx
0x1800229db  mov     rsi, rcx
0x1800229de  mov     edi, 1
0x1800229e3  lea     rdx, aCntfsvolumeAdd_0; "CNtfsVolume::AddBootOptimizationFile"
0x1800229ea  mov     r9d, edi; unsigned __int16
0x1800229ed  lea     rcx, [rbp+57h+var_90]; this
0x1800229f1  mov     r8d, 2F7h; unsigned __int16
0x1800229f7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800229fc  xorps   xmm0, xmm0
0x1800229ff  xor     eax, eax
0x180022a01  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180022a04  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180022a08  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180022a0c  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180022a10  test    r14, r14
0x180022a13  jz      loc_180022AED
0x180022a19  mov     [rbp+57h+var_90], eax
0x180022a1c  xor     r9d, r9d; lpSecurityAttributes
0x180022a1f  mov     eax, 2FDh
0x180022a24  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180022a2d  mov     [rsp+0D0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180022a35  xor     r8d, r8d; dwShareMode
0x180022a38  mov     edx, 100080h; dwDesiredAccess
0x180022a3d  mov     [rbp+57h+var_8C], ax
0x180022a41  mov     rcx, r14; lpFileName
0x180022a44  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180022a4c  call    cs:__imp_CreateFileW
0x180022a52  mov     rbx, rax
0x180022a55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022a59  jz      loc_180022B99
0x180022a5f  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180022a63  mov     rcx, rax; hFile
0x180022a66  call    cs:__imp_GetFileInformationByHandle
0x180022a6c  test    eax, eax
0x180022a6e  jz      loc_180022B61
0x180022a74  mov     r8d, [rbp+57h+FileInformation.nFileSizeLow]
0x180022a78  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x180022a7b  mov     r9, [rsi+80h]
0x180022a82  or      r8, rax
0x180022a85  test    r9, r9
0x180022a88  jz      short loc_180022A93
0x180022a8a  cmp     r8, r9
0x180022a8d  ja      loc_180022BE3
0x180022a93  mov     r9, [rsi+88h]
0x180022a9a  test    r9, r9
0x180022a9d  jz      short loc_180022AB2
0x180022a9f  mov     r10, [rsi+90h]
0x180022aa6  add     r10, r8
0x180022aa9  cmp     r10, r9
0x180022aac  ja      loc_180022B74
0x180022ab2  add     [rsi+90h], r8
0x180022ab9  mov     ecx, 10h; cb
0x180022abe  call    cs:__imp_CoTaskMemAlloc
0x180022ac4  mov     rcx, rax
0x180022ac7  test    rax, rax
0x180022aca  mov     eax, 323h
0x180022acf  jnz     short loc_180022B2D
0x180022ad1  mov     edi, 8007000Eh
0x180022ad6  mov     [rbp+57h+var_8A], ax
0x180022ada  mov     [rbp+57h+var_90], edi
0x180022add  test    rbx, rbx
0x180022ae0  jz      short loc_180022AFE
0x180022ae2  mov     rcx, rbx; hObject
0x180022ae5  call    cs:__imp_CloseHandle
0x180022aeb  jmp     short loc_180022AFE
0x180022aed  mov     edi, 80070057h
0x180022af2  mov     eax, 2FDh
0x180022af7  mov     [rbp+57h+var_90], edi
0x180022afa  mov     [rbp+57h+var_8A], ax
0x180022afe  lea     rcx, [rbp+57h+var_90]; this
0x180022b02  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180022b07  mov     eax, edi
0x180022b09  mov     rcx, [rbp+57h+var_20]
0x180022b0d  xor     rcx, rsp; StackCookie
0x180022b10  call    __security_check_cookie
0x180022b15  lea     r11, [rsp+0D0h+var_10]
0x180022b1d  mov     rbx, [r11+30h]
0x180022b21  mov     rsi, [r11+38h]
0x180022b25  mov     rsp, r11
0x180022b28  pop     r14
0x180022b2a  pop     rdi
0x180022b2b  pop     rbp
0x180022b2c  retn
0x180022b2d  mov     [rbp+57h+var_8C], ax
0x180022b31  movzx   eax, word ptr [rbp+57h+FileInformation.nFileIndexHigh]
0x180022b35  mov     [rbp+57h+var_90], 0
0x180022b3c  mov     [rcx+4], ax
0x180022b40  mov     eax, [rbp+57h+FileInformation.nFileIndexLow]
0x180022b43  mov     [rcx], eax
0x180022b45  mov     eax, [rbp+57h+FileInformation.nFileIndexHigh]
0x180022b48  shr     eax, 14h
0x180022b4b  mov     [rcx+6], ax
0x180022b4f  mov     rax, [rsi+240h]
0x180022b56  mov     [rcx+8], rax
0x180022b5a  mov     [rsi+240h], rcx
0x180022b61  test    rbx, rbx
0x180022b64  jz      short loc_180022B6F
0x180022b66  mov     rcx, rbx; hObject
0x180022b69  call    cs:__imp_CloseHandle
0x180022b6f  mov     edi, [rbp+57h+var_90]
0x180022b72  jmp     short loc_180022AFE
0x180022b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b7b  lea     rax, WPP_GLOBAL_Control
0x180022b82  cmp     rcx, rax
0x180022b85  jnz     loc_180022C24
0x180022b8b  mov     eax, 334h
0x180022b90  mov     [rbp+57h+var_8C], ax
0x180022b94  jmp     loc_180022ADA
0x180022b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ba0  lea     rax, WPP_GLOBAL_Control
0x180022ba7  cmp     rcx, rax
0x180022baa  jz      short loc_180022BD2
0x180022bac  test    dword ptr [rcx+1Ch], 40000h
0x180022bb3  jz      short loc_180022BD2
0x180022bb5  call    cs:__imp_GetLastError
0x180022bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bc2  mov     r9, r14
0x180022bc5  mov     [rsp+0D0h+dwCreationDisposition], eax
0x180022bc9  mov     rcx, [rcx+10h]
0x180022bcd  call    WPP_SF_SD
0x180022bd2  mov     eax, 30Fh
0x180022bd7  mov     [rbp+57h+var_90], edi
0x180022bda  mov     [rbp+57h+var_8C], ax
0x180022bde  jmp     loc_180022AFE
0x180022be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bea  lea     rax, WPP_GLOBAL_Control
0x180022bf1  cmp     rcx, rax
0x180022bf4  jz      short loc_180022C1A
0x180022bf6  test    dword ptr [rcx+1Ch], 40000h
0x180022bfd  jz      short loc_180022C1A
0x180022bff  mov     rcx, [rcx+10h]
0x180022c03  mov     edx, 0Eh
0x180022c08  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r9
0x180022c0d  mov     r9, r14
0x180022c10  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r8
0x180022c15  call    WPP_SF_SII
0x180022c1a  mov     eax, 33Fh
0x180022c1f  jmp     loc_180022B90
0x180022c24  test    dword ptr [rcx+1Ch], 40000h
0x180022c2b  jz      loc_180022B8B
0x180022c31  mov     rcx, [rcx+10h]
0x180022c35  mov     edx, 0Dh
0x180022c3a  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r9
0x180022c3f  mov     r9, r14
0x180022c42  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r10
0x180022c47  call    WPP_SF_SII
0x180022c4c  jmp     loc_180022B8B
```
