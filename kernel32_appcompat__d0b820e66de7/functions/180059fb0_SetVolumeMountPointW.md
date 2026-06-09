# SetVolumeMountPointW

- ea: `0x180059fb0`
- end: `0x18005a524`
- name: `SetVolumeMountPointW`
- size: `1396`
- prototype: `BOOL __stdcall(LPCWSTR lpszVolumeMountPoint, LPCWSTR lpszVolumeName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180066710`
- `0x180074250`

## callees

- `0x18000ccf0`
- `0x18004a9fc`
- `0x180059fb0`
- `0x18005d758`
- `0x1800823f0`
- `0x1800824f4`
- `0x180082751`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18005a051`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005a075`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005a051`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005a075`
- `ntdll!wcslen` at `0x18005a303`
- `ntdll!wcslen` at `0x18005a303`
- `ntdll!RtlSetLastWin32Error` at `0x18005a365`
- `ntdll!RtlSetLastWin32Error` at `0x18005a3d6`
- `ntdll!RtlSetLastWin32Error` at `0x18005a365`
- `ntdll!RtlSetLastWin32Error` at `0x18005a3d6`
- `ntdll!RtlFreeHeap` at `0x18005a4d2`
- `ntdll!RtlFreeHeap` at `0x18005a4d2`
- `ntdll!RtlAllocateHeap` at `0x18005a39a`
- `ntdll!RtlAllocateHeap` at `0x18005a39a`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005a022`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005a2ed`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005a022`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005a2ed`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005a379`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005a379`
- `KERNELBASE!NotifyMountMgr` at `0x18005a4fd`
- `KERNELBASE!NotifyMountMgr` at `0x18005a4fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a4e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a25e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a29f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a25e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a29f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005a2c9`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005a2c9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005a4b2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005a4b2`

## string_xrefs

- `0x18005a234`: `\\.\MountPointManager`

## pseudocode

```c
BOOL __stdcall SetVolumeMountPointW(LPCWSTR lpszVolumeMountPoint, LPCWSTR lpszVolumeName)
{
  NTSTATUS inited; // eax
  __int64 v5; // rcx
  ULONG v6; // ecx
  struct _UNICODE_STRING v8; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+280h] [rbp+180h] BYREF

  BytesReturned = 0;
  DestinationString = 0;
  v8 = 0;
  if ( !lpszVolumeMountPoint || !lpszVolumeName )
    goto LABEL_36;
  if ( GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x104u)
    || NtCurrentTeb()->LastErrorValue == 206 )
  {
    v6 = 145;
    goto LABEL_37;
  }
  inited = RtlInitUnicodeStringEx(&DestinationString, lpszVolumeMountPoint);
  if ( inited < 0 || (inited = RtlInitUnicodeStringEx(&v8, lpszVolumeName), inited < 0) )
  {
    v5 = (unsigned int)inited;
LABEL_7:
    BaseSetLastNTError(v5);
    return 0;
  }
  if ( !DestinationString.Length || !v8.Length )
  {
LABEL_36:
    v6 = 87;
LABEL_37:
    RtlSetLastWin32Error(v6);
    return 0;
  }
  if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92
    || v8.Buffer[((unsigned __int64)v8.Length >> 1) - 1] != 92 )
  {
    v5 = 3221225523LL;
    goto LABEL_7;
  }
  if ( v8.Length != 96 && (v8.Length != 98 || v8.Buffer[48] != 92)
    || *v8.Buffer != 92
    || v8.Buffer[1] != 63 && v8.Buffer[1] != 92
    || v8.Buffer[2] != 63
    || v8.Buffer[3] != 92
    || v8.Buffer[4] != 86
    || v8.Buffer[5] != 111
    || v8.Buffer[6] != 108
    || v8.Buffer[7] != 117
    || v8.Buffer[8] != 109
    || v8.Buffer[9] != 101
    || v8.Buffer[10] != 123
    || v8.Buffer[19] != 45
    || v8.Buffer[24] != 45
    || v8.Buffer[29] != 45
    || v8.Buffer[34] != 45
    || v8.Buffer[47] != 125
    || v8.Length != 98
    || v8.Buffer[1] != 92
    || (unsigned int)IsThisAVolumeName(lpszVolumeName) )
  {
    goto LABEL_36;
  }
  return 0;
}

```

## disassembly

```asm
0x180059fb0  mov     [rsp-8+arg_10], rbx
0x180059fb5  push    rbp
0x180059fb6  push    rsi
0x180059fb7  push    rdi
0x180059fb8  push    r12
0x180059fba  push    r13
0x180059fbc  push    r14
0x180059fbe  push    r15
0x180059fc0  lea     rbp, [rsp-3A0h]
0x180059fc8  sub     rsp, 4A0h
0x180059fcf  mov     rax, cs:__security_cookie
0x180059fd6  xor     rax, rsp
0x180059fd9  mov     [rbp+3D0h+var_40], rax
0x180059fe0  xor     r12d, r12d
0x180059fe3  xorps   xmm0, xmm0
0x180059fe6  mov     [rsp+4D0h+BytesReturned], r12d
0x180059feb  xorps   xmm1, xmm1
0x180059fee  mov     [rsp+4D0h+var_490], r12b
0x180059ff3  mov     r14, rdx
0x180059ff6  mov     rsi, rcx
0x180059ff9  movups  xmmword ptr [rsp+4D0h+DestinationString.Length], xmm0
0x180059ffe  movups  xmmword ptr [rsp+4D0h+var_488.Length], xmm1
0x18005a003  test    rcx, rcx
0x18005a006  jz      loc_18005A3D1
0x18005a00c  test    rdx, rdx
0x18005a00f  jz      loc_18005A3D1
0x18005a015  mov     r8d, 104h; cchBufferLength
0x18005a01b  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x18005a022  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005a029  nop     dword ptr [rax+rax+00h]
0x18005a02e  test    eax, eax
0x18005a030  jnz     loc_18005A51A
0x18005a036  mov     eax, gs:68h
0x18005a03e  cmp     eax, 0CEh
0x18005a043  jz      loc_18005A51A
0x18005a049  mov     rdx, rsi; SourceString
0x18005a04c  lea     rcx, [rsp+4D0h+DestinationString]; DestinationString
0x18005a051  call    cs:__imp_RtlInitUnicodeStringEx
0x18005a058  nop     dword ptr [rax+rax+00h]
0x18005a05d  test    eax, eax
0x18005a05f  jns     short loc_18005A06D
0x18005a061  mov     ecx, eax
0x18005a063  call    BaseSetLastNTError
0x18005a068  jmp     loc_18005A3E2
0x18005a06d  mov     rdx, r14; SourceString
0x18005a070  lea     rcx, [rsp+4D0h+var_488]; DestinationString
0x18005a075  call    cs:__imp_RtlInitUnicodeStringEx
0x18005a07c  nop     dword ptr [rax+rax+00h]
0x18005a081  test    eax, eax
0x18005a083  js      short loc_18005A061
0x18005a085  movzx   eax, [rsp+4D0h+DestinationString.Length]
0x18005a08a  test    ax, ax
0x18005a08d  jz      loc_18005A3D1
0x18005a093  movzx   edx, [rsp+4D0h+var_488.Length]
0x18005a098  test    dx, dx
0x18005a09b  jz      loc_18005A3D1
0x18005a0a1  mov     ecx, eax
0x18005a0a3  mov     bx, 5Ch ; '\'
0x18005a0a7  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x18005a0ac  shr     rcx, 1
0x18005a0af  cmp     [rax+rcx*2-2], bx
0x18005a0b4  jnz     loc_18005A510
0x18005a0ba  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x18005a0bf  mov     eax, edx
0x18005a0c1  shr     rax, 1
0x18005a0c4  cmp     [rcx+rax*2-2], bx
0x18005a0c9  jnz     loc_18005A510
0x18005a0cf  cmp     edx, 60h ; '`'
0x18005a0d2  jz      short loc_18005A0E7
0x18005a0d4  cmp     edx, 62h ; 'b'
0x18005a0d7  jnz     loc_18005A3D1
0x18005a0dd  cmp     [rcx+60h], bx
0x18005a0e1  jnz     loc_18005A3D1
0x18005a0e7  cmp     [rcx], bx
0x18005a0ea  jnz     loc_18005A3D1
0x18005a0f0  mov     r13d, 3Fh ; '?'
0x18005a0f6  cmp     [rcx+2], r13w
0x18005a0fb  jz      short loc_18005A107
0x18005a0fd  cmp     [rcx+2], bx
0x18005a101  jnz     loc_18005A3D1
0x18005a107  cmp     [rcx+4], r13w
0x18005a10c  jnz     loc_18005A3D1
0x18005a112  cmp     [rcx+6], bx
0x18005a116  jnz     loc_18005A3D1
0x18005a11c  cmp     word ptr [rcx+8], 56h ; 'V'
0x18005a121  jnz     loc_18005A3D1
0x18005a127  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x18005a12c  jnz     loc_18005A3D1
0x18005a132  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x18005a137  jnz     loc_18005A3D1
0x18005a13d  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x18005a142  jnz     loc_18005A3D1
0x18005a148  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x18005a14d  jnz     loc_18005A3D1
0x18005a153  cmp     word ptr [rcx+12h], 65h ; 'e'
0x18005a158  jnz     loc_18005A3D1
0x18005a15e  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x18005a163  jnz     loc_18005A3D1
0x18005a169  mov     ax, 2Dh ; '-'
0x18005a16d  cmp     [rcx+26h], ax
0x18005a171  jnz     loc_18005A3D1
0x18005a177  cmp     [rcx+30h], ax
0x18005a17b  jnz     loc_18005A3D1
0x18005a181  cmp     [rcx+3Ah], ax
0x18005a185  jnz     loc_18005A3D1
0x18005a18b  cmp     [rcx+44h], ax
0x18005a18f  jnz     loc_18005A3D1
0x18005a195  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x18005a19a  jnz     loc_18005A3D1
0x18005a1a0  cmp     edx, 62h ; 'b'
0x18005a1a3  jnz     loc_18005A3D1
0x18005a1a9  cmp     [rcx+2], bx
0x18005a1ad  jnz     loc_18005A3D1
0x18005a1b3  lea     rdx, [rsp+4D0h+var_490]
0x18005a1b8  mov     rcx, r14; SourceString
0x18005a1bb  call    IsThisAVolumeName
0x18005a1c0  test    eax, eax
0x18005a1c2  jz      loc_18005A3E2
0x18005a1c8  cmp     [rsp+4D0h+var_490], r12b
0x18005a1cd  jz      loc_18005A3D1
0x18005a1d3  cmp     [rsp+4D0h+DestinationString.Length], 6
0x18005a1d9  jnz     short loc_18005A1F7
0x18005a1db  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x18005a1e0  cmp     word ptr [rax+2], 3Ah ; ':'
0x18005a1e5  jnz     short loc_18005A230
0x18005a1e7  mov     rcx, rsi
0x18005a1ea  mov     rdx, r14
0x18005a1ed  call    SetVolumeNameForRoot
0x18005a1f2  jmp     loc_18005A3E4
0x18005a1f7  cmp     [rsp+4D0h+DestinationString.Length], 0Eh
0x18005a1fd  jnz     short loc_18005A230
0x18005a1ff  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x18005a204  cmp     [rax], bx
0x18005a207  jnz     short loc_18005A230
0x18005a209  cmp     [rax+2], bx
0x18005a20d  jnz     short loc_18005A230
0x18005a20f  cmp     word ptr [rax+4], 2Eh ; '.'
0x18005a214  jz      short loc_18005A21D
0x18005a216  cmp     [rax+4], r13w
0x18005a21b  jnz     short loc_18005A230
0x18005a21d  cmp     [rax+6], bx
0x18005a221  jnz     short loc_18005A230
0x18005a223  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x18005a228  jnz     short loc_18005A230
0x18005a22a  lea     rcx, [rsi+8]
0x18005a22e  jmp     short loc_18005A1EA
0x18005a230  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005a234  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x18005a23b  mov     [rsp+4D0h+hTemplateFile], rbx; hTemplateFile
0x18005a240  mov     r15d, 0C0000000h
0x18005a246  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005a24e  xor     r9d, r9d; lpSecurityAttributes
0x18005a251  mov     edx, r15d; dwDesiredAccess
0x18005a254  lea     edi, [rbx+4]
0x18005a257  mov     r8d, edi; dwShareMode
0x18005a25a  mov     [rsp+4D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18005a25e  call    cs:__imp_CreateFileW
0x18005a265  nop     dword ptr [rax+rax+00h]
0x18005a26a  cmp     rax, rbx
0x18005a26d  jz      loc_18005A3E2
0x18005a273  mov     rcx, rax; hObject
0x18005a276  call    cs:__imp_CloseHandle
0x18005a27d  nop     dword ptr [rax+rax+00h]
0x18005a282  mov     [rsp+4D0h+hTemplateFile], rbx; hTemplateFile
0x18005a287  xor     r9d, r9d; lpSecurityAttributes
0x18005a28a  mov     [rsp+4D0h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x18005a292  mov     r8d, edi; dwShareMode
0x18005a295  mov     edx, r15d; dwDesiredAccess
0x18005a298  mov     [rsp+4D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18005a29c  mov     rcx, rsi; lpFileName
0x18005a29f  call    cs:__imp_CreateFileW
0x18005a2a6  nop     dword ptr [rax+rax+00h]
0x18005a2ab  mov     r15, rax
0x18005a2ae  cmp     rax, rbx
0x18005a2b1  jz      loc_18005A3E2
0x18005a2b7  mov     ebx, 104h
0x18005a2bc  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumePathName
0x18005a2c3  mov     r8d, ebx; cchBufferLength
0x18005a2c6  mov     rcx, rsi; lpszFileName
0x18005a2c9  call    cs:__imp_GetVolumePathNameW
0x18005a2d0  nop     dword ptr [rax+rax+00h]
0x18005a2d5  cmp     eax, 1
0x18005a2d8  jnz     loc_18005A379
0x18005a2de  mov     r8d, ebx; cchBufferLength
0x18005a2e1  lea     rdx, [rsp+4D0h+String]; lpszVolumeName
0x18005a2e6  lea     rcx, [rbp+3D0h+szVolumeName]; lpszVolumeMountPoint
0x18005a2ed  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005a2f4  nop     dword ptr [rax+rax+00h]
0x18005a2f9  cmp     eax, 1
0x18005a2fc  jnz     short loc_18005A379
0x18005a2fe  lea     rcx, [rsp+4D0h+String]; String
0x18005a303  call    cs:__imp_wcslen
0x18005a30a  nop     dword ptr [rax+rax+00h]
0x18005a30f  mov     rdx, rax
0x18005a312  lea     rcx, [rsp+4D0h+String]
0x18005a317  mov     rbx, rax
0x18005a31a  call    IsVolumeOnCluster
0x18005a31f  mov     rdx, rbx
0x18005a322  lea     rcx, [rsp+4D0h+String]
0x18005a327  mov     r12d, eax
0x18005a32a  call    IsVolumeOnCSV
0x18005a32f  movzx   ebx, [rsp+4D0h+var_488.Length]
0x18005a334  mov     edi, eax
0x18005a336  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x18005a33b  shr     rbx, 1
0x18005a33e  mov     rdx, rbx
0x18005a341  call    IsVolumeOnCluster
0x18005a346  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x18005a34b  mov     rdx, rbx
0x18005a34e  mov     r13d, eax
0x18005a351  call    IsVolumeOnCSV
0x18005a356  test    edi, edi
0x18005a358  jnz     short loc_18005A3C2
0x18005a35a  test    eax, eax
0x18005a35c  jnz     short loc_18005A363
0x18005a35e  cmp     r12d, r13d
0x18005a361  jnz     short loc_18005A3C2
0x18005a363  xor     ecx, ecx; LastError
0x18005a365  call    cs:__imp_RtlSetLastWin32Error
0x18005a36c  nop     dword ptr [rax+rax+00h]
0x18005a371  xor     r12d, r12d
0x18005a374  lea     r13d, [r12+3Fh]
0x18005a379  call    cs:__imp_KernelBaseGetGlobalData
0x18005a380  nop     dword ptr [rax+rax+00h]
0x18005a385  mov     rcx, gs:60h
0x18005a38e  mov     r8d, 4000h; Size
0x18005a394  mov     edx, [rax]; Flags
0x18005a396  mov     rcx, [rcx+30h]; HeapHandle
0x18005a39a  call    cs:__imp_RtlAllocateHeap
0x18005a3a1  nop     dword ptr [rax+rax+00h]
0x18005a3a6  mov     rdi, rax
0x18005a3a9  test    rax, rax
0x18005a3ac  jnz     short loc_18005A40F
0x18005a3ae  mov     rcx, r15; hObject
0x18005a3b1  call    cs:__imp_CloseHandle
0x18005a3b8  nop     dword ptr [rax+rax+00h]
0x18005a3bd  lea     ecx, [rdi+8]
0x18005a3c0  jmp     short loc_18005A3D6
0x18005a3c2  mov     rcx, r15; hObject
0x18005a3c5  call    cs:__imp_CloseHandle
0x18005a3cc  nop     dword ptr [rax+rax+00h]
0x18005a3d1  mov     ecx, 57h ; 'W'; LastError
0x18005a3d6  call    cs:__imp_RtlSetLastWin32Error
0x18005a3dd  nop     dword ptr [rax+rax+00h]
0x18005a3e2  xor     eax, eax
0x18005a3e4  mov     rcx, [rbp+3D0h+var_40]
0x18005a3eb  xor     rcx, rsp; StackCookie
0x18005a3ee  call    __security_check_cookie
0x18005a3f3  mov     rbx, [rsp+4D0h+arg_10]
0x18005a3fb  add     rsp, 4A0h
0x18005a402  pop     r15
0x18005a404  pop     r14
0x18005a406  pop     r13
0x18005a408  pop     r12
0x18005a40a  pop     rdi
0x18005a40b  pop     rsi
0x18005a40c  pop     rbp
0x18005a40d  retn
0x18005a40f  lea     rcx, [rax+4]; void *
0x18005a413  xor     edx, edx; Val
0x18005a415  mov     r8d, 3FFCh; Size
0x18005a41b  call    memset_0
0x18005a420  mov     dword ptr [rdi], 0A0000003h
0x18005a426  lea     rbx, [rdi+10h]
0x18005a42a  movzx   eax, [rsp+4D0h+var_488.Length]
0x18005a42f  mov     rcx, rbx; void *
0x18005a432  add     ax, 6
0x18005a436  mov     dword ptr [rdi+6], 0
0x18005a43d  add     ax, ax
0x18005a440  mov     [rdi+4], ax
0x18005a444  movzx   eax, [rsp+4D0h+var_488.Length]
0x18005a449  mov     [rdi+0Ah], ax
0x18005a44d  mov     r8d, eax; Size
0x18005a450  mov     rdx, [rsp+4D0h+var_488.Buffer]; Src
0x18005a455  call    memcpy_0
0x18005a45a  movzx   ecx, word ptr [rdi+0Ah]
0x18005a45e  mov     rdx, rbx; Src
0x18005a461  mov     [rdi+12h], r13w
0x18005a466  lea     eax, [rcx+2]
0x18005a469  add     rcx, 2
0x18005a46d  mov     [rdi+0Ch], ax
0x18005a471  add     rcx, rbx; void *
0x18005a474  movzx   eax, [rsp+4D0h+var_488.Length]
0x18005a479  mov     r8d, eax; Size
0x18005a47c  mov     [rdi+0Eh], ax
0x18005a480  call    memcpy_0
0x18005a485  movzx   r9d, word ptr [rdi+4]
0x18005a48a  lea     rax, [rsp+4D0h+BytesReturned]
0x18005a48f  mov     [rsp+4D0h+lpOverlapped], r12; lpOverlapped
0x18005a494  add     r9d, 8; nInBufferSize
0x18005a498  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x18005a49d  mov     r8, rdi; lpInBuffer
0x18005a4a0  mov     [rsp+4D0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x18005a4a5  mov     edx, 900A4h; dwIoControlCode
0x18005a4aa  mov     rcx, r15; hDevice
0x18005a4ad  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r12; lpOutBuffer
0x18005a4b2  call    cs:__imp_DeviceIoControl
0x18005a4b9  nop     dword ptr [rax+rax+00h]
0x18005a4be  mov     rcx, gs:60h
0x18005a4c7  mov     r8, rdi; P
  ... truncated ...
```
