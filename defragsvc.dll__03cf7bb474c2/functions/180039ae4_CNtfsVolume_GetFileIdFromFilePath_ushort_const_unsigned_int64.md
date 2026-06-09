# CNtfsVolume::_GetFileIdFromFilePath(ushort const *,unsigned __int64 *)

- ea: `0x180039ae4`
- end: `0x180039c2d`
- name: `?_GetFileIdFromFilePath@CNtfsVolume@@AEAAJPEBGPEA_K@Z`
- size: `329`
- prototype: `__int64 __fastcall(CNtfsVolume *this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003c0a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180039ae4`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039b9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039b9a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180039bbb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180039bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bf7`

## string_xrefs

- `0x180039b20`: `CNtfsVolume::_GetFileIdFromFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::_GetFileIdFromFilePath(
        CNtfsVolume *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  unsigned int v5; // edi
  __int64 v6; // rbx
  __int16 v7; // ax
  HANDLE FileW; // rax
  unsigned int v10; // [rsp+40h] [rbp-39h] BYREF
  __int16 v11; // [rsp+44h] [rbp-35h]
  __int16 v12; // [rsp+46h] [rbp-33h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-1h] BYREF

  v5 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CNtfsVolume::_GetFileIdFromFilePath", 2491, 1);
  v6 = -1;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !a3 )
  {
    v7 = 2497;
    goto LABEL_9;
  }
  *a3 = 0;
  v11 = 2497;
  v7 = 2498;
  if ( !a2 )
  {
LABEL_9:
    v5 = -2147024809;
    v12 = v7;
    goto LABEL_10;
  }
  v10 = 0;
  v11 = 2498;
  FileW = CreateFileW(a2, 0x100080u, 0, 0, 3u, 0x2200000u, 0);
  v6 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v11 = 2511;
  }
  else
  {
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
      *a3 = FileInformation.nFileIndexLow | ((unsigned __int64)FileInformation.nFileIndexHigh << 32);
    v5 = 0;
  }
LABEL_10:
  v10 = v5;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v5;
}

```

## disassembly

```asm
0x180039ae4  mov     [rsp-8+arg_0], rbx
0x180039ae9  mov     [rsp-8+arg_18], rsi
0x180039aee  push    rbp
0x180039aef  push    rdi
0x180039af0  push    r14
0x180039af2  lea     rbp, [rsp-47h]
0x180039af7  sub     rsp, 0C0h
0x180039afe  mov     rax, cs:__security_cookie
0x180039b05  xor     rax, rsp
0x180039b08  mov     [rbp+57h+var_18], rax
0x180039b0c  mov     rsi, r8
0x180039b0f  mov     r14, rdx
0x180039b12  mov     edi, 1
0x180039b17  mov     r9d, edi; unsigned __int16
0x180039b1a  mov     r8d, 9BBh; unsigned __int16
0x180039b20  lea     rdx, aCntfsvolumeGet_0; "CNtfsVolume::_GetFileIdFromFilePath"
0x180039b27  lea     rcx, [rbp+57h+var_90]; this
0x180039b2b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180039b30  nop
0x180039b31  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039b35  xorps   xmm0, xmm0
0x180039b38  xor     eax, eax
0x180039b3a  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180039b3e  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180039b42  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180039b46  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180039b49  test    rsi, rsi
0x180039b4c  jz      loc_180039BD9
0x180039b52  mov     [rsi], rax
0x180039b55  mov     eax, 9C1h
0x180039b5a  mov     [rbp+57h+var_8C], ax
0x180039b5e  mov     eax, 9C2h
0x180039b63  test    r14, r14
0x180039b66  jz      short loc_180039BDE
0x180039b68  mov     [rbp+57h+var_90], 0
0x180039b6f  mov     [rbp+57h+var_8C], ax
0x180039b73  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180039b7c  mov     [rsp+0D0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180039b84  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180039b8c  xor     r9d, r9d; lpSecurityAttributes
0x180039b8f  xor     r8d, r8d; dwShareMode
0x180039b92  mov     edx, 100080h; dwDesiredAccess
0x180039b97  mov     rcx, r14; lpFileName
0x180039b9a  call    cs:__imp_CreateFileW
0x180039ba0  mov     rbx, rax
0x180039ba3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039ba7  jnz     short loc_180039BB4
0x180039ba9  mov     eax, 9CFh
0x180039bae  mov     [rbp+57h+var_8C], ax
0x180039bb2  jmp     short loc_180039BE7
0x180039bb4  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180039bb8  mov     rcx, rax; hFile
0x180039bbb  call    cs:__imp_GetFileInformationByHandle
0x180039bc1  test    eax, eax
0x180039bc3  jz      short loc_180039BD5
0x180039bc5  mov     ecx, [rbp+57h+FileInformation.nFileIndexHigh]
0x180039bc8  shl     rcx, 20h
0x180039bcc  mov     eax, [rbp+57h+FileInformation.nFileIndexLow]
0x180039bcf  or      rcx, rax
0x180039bd2  mov     [rsi], rcx
0x180039bd5  xor     edi, edi
0x180039bd7  jmp     short loc_180039BE7
0x180039bd9  mov     eax, 9C1h
0x180039bde  mov     edi, 80070057h
0x180039be3  mov     [rbp+57h+var_8A], ax
0x180039be7  mov     [rbp+57h+var_90], edi
0x180039bea  lea     rcx, [rbx-1]
0x180039bee  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180039bf2  ja      short loc_180039BFE
0x180039bf4  mov     rcx, rbx; hObject
0x180039bf7  call    cs:__imp_CloseHandle
0x180039bfd  nop
0x180039bfe  lea     rcx, [rbp+57h+var_90]; this
0x180039c02  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180039c07  mov     eax, edi
0x180039c09  mov     rcx, [rbp+57h+var_18]
0x180039c0d  xor     rcx, rsp; StackCookie
0x180039c10  call    __security_check_cookie
0x180039c15  lea     r11, [rsp+0D0h+var_10]
0x180039c1d  mov     rbx, [r11+20h]
0x180039c21  mov     rsi, [r11+38h]
0x180039c25  mov     rsp, r11
0x180039c28  pop     r14
0x180039c2a  pop     rdi
0x180039c2b  pop     rbp
0x180039c2c  retn
```
