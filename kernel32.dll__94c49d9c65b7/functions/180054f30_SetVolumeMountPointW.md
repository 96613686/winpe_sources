# SetVolumeMountPointW

- ea: `0x180054f30`
- end: `0x180055431`
- name: `SetVolumeMountPointW`
- size: `1281`
- prototype: `BOOL __stdcall(LPCWSTR lpszVolumeMountPoint, LPCWSTR lpszVolumeName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180060080`
- `0x18006cba0`

## callees

- `0x18000f920`
- `0x180046ac0`
- `0x180054f30`
- `0x1800581b0`
- `0x18007a4c4`
- `0x18007a5ac`
- `0x18007a7d1`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180054fcb`
- `ntdll!RtlInitUnicodeStringEx` at `0x180054fe9`
- `ntdll!RtlInitUnicodeStringEx` at `0x180054fcb`
- `ntdll!RtlInitUnicodeStringEx` at `0x180054fe9`
- `ntdll!wcslen` at `0x180055253`
- `ntdll!wcslen` at `0x180055253`
- `ntdll!RtlSetLastWin32Error` at `0x1800552af`
- `ntdll!RtlSetLastWin32Error` at `0x180055302`
- `ntdll!RtlSetLastWin32Error` at `0x1800552af`
- `ntdll!RtlSetLastWin32Error` at `0x180055302`
- `ntdll!RtlFreeHeap` at `0x1800553f1`
- `ntdll!RtlFreeHeap` at `0x1800553f1`
- `ntdll!RtlAllocateHeap` at `0x1800552d8`
- `ntdll!RtlAllocateHeap` at `0x1800552d8`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180054fa2`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180055243`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180054fa2`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180055243`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800552bd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800552bd`
- `KERNELBASE!NotifyMountMgr` at `0x180055410`
- `KERNELBASE!NotifyMountMgr` at `0x180055410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800552e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800552f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800552e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800552f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800551cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055201`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800551cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055201`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180055225`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180055225`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800553d7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800553d7`

## string_xrefs

- `0x1800551a2`: `\\.\MountPointManager`

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
0x180054f30  mov     [rsp-8+arg_10], rbx
0x180054f35  push    rbp
0x180054f36  push    rsi
0x180054f37  push    rdi
0x180054f38  push    r12
0x180054f3a  push    r13
0x180054f3c  push    r14
0x180054f3e  push    r15
0x180054f40  lea     rbp, [rsp-3A0h]
0x180054f48  sub     rsp, 4A0h
0x180054f4f  mov     rax, cs:__security_cookie
0x180054f56  xor     rax, rsp
0x180054f59  mov     [rbp+3D0h+var_40], rax
0x180054f60  xor     r12d, r12d
0x180054f63  xorps   xmm0, xmm0
0x180054f66  mov     [rsp+4D0h+BytesReturned], r12d
0x180054f6b  xorps   xmm1, xmm1
0x180054f6e  mov     [rsp+4D0h+var_490], r12b
0x180054f73  mov     r14, rdx
0x180054f76  mov     rsi, rcx
0x180054f79  movups  xmmword ptr [rsp+4D0h+DestinationString.Length], xmm0
0x180054f7e  movups  xmmword ptr [rsp+4D0h+var_488.Length], xmm1
0x180054f83  test    rcx, rcx
0x180054f86  jz      loc_1800552FD
0x180054f8c  test    rdx, rdx
0x180054f8f  jz      loc_1800552FD
0x180054f95  mov     r8d, 104h; cchBufferLength
0x180054f9b  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x180054fa2  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180054fa8  test    eax, eax
0x180054faa  jnz     loc_180055427
0x180054fb0  mov     eax, gs:68h
0x180054fb8  cmp     eax, 0CEh
0x180054fbd  jz      loc_180055427
0x180054fc3  mov     rdx, rsi; SourceString
0x180054fc6  lea     rcx, [rsp+4D0h+DestinationString]; DestinationString
0x180054fcb  call    cs:__imp_RtlInitUnicodeStringEx
0x180054fd1  test    eax, eax
0x180054fd3  jns     short loc_180054FE1
0x180054fd5  mov     ecx, eax
0x180054fd7  call    BaseSetLastNTError
0x180054fdc  jmp     loc_180055308
0x180054fe1  mov     rdx, r14; SourceString
0x180054fe4  lea     rcx, [rsp+4D0h+var_488]; DestinationString
0x180054fe9  call    cs:__imp_RtlInitUnicodeStringEx
0x180054fef  test    eax, eax
0x180054ff1  js      short loc_180054FD5
0x180054ff3  movzx   eax, [rsp+4D0h+DestinationString.Length]
0x180054ff8  test    ax, ax
0x180054ffb  jz      loc_1800552FD
0x180055001  movzx   edx, [rsp+4D0h+var_488.Length]
0x180055006  test    dx, dx
0x180055009  jz      loc_1800552FD
0x18005500f  mov     ecx, eax
0x180055011  mov     bx, 5Ch ; '\'
0x180055015  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x18005501a  shr     rcx, 1
0x18005501d  cmp     [rax+rcx*2-2], bx
0x180055022  jnz     loc_18005541D
0x180055028  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x18005502d  mov     eax, edx
0x18005502f  shr     rax, 1
0x180055032  cmp     [rcx+rax*2-2], bx
0x180055037  jnz     loc_18005541D
0x18005503d  cmp     edx, 60h ; '`'
0x180055040  jz      short loc_180055055
0x180055042  cmp     edx, 62h ; 'b'
0x180055045  jnz     loc_1800552FD
0x18005504b  cmp     [rcx+60h], bx
0x18005504f  jnz     loc_1800552FD
0x180055055  cmp     [rcx], bx
0x180055058  jnz     loc_1800552FD
0x18005505e  mov     r13d, 3Fh ; '?'
0x180055064  cmp     [rcx+2], r13w
0x180055069  jz      short loc_180055075
0x18005506b  cmp     [rcx+2], bx
0x18005506f  jnz     loc_1800552FD
0x180055075  cmp     [rcx+4], r13w
0x18005507a  jnz     loc_1800552FD
0x180055080  cmp     [rcx+6], bx
0x180055084  jnz     loc_1800552FD
0x18005508a  cmp     word ptr [rcx+8], 56h ; 'V'
0x18005508f  jnz     loc_1800552FD
0x180055095  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x18005509a  jnz     loc_1800552FD
0x1800550a0  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800550a5  jnz     loc_1800552FD
0x1800550ab  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800550b0  jnz     loc_1800552FD
0x1800550b6  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800550bb  jnz     loc_1800552FD
0x1800550c1  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1800550c6  jnz     loc_1800552FD
0x1800550cc  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1800550d1  jnz     loc_1800552FD
0x1800550d7  mov     ax, 2Dh ; '-'
0x1800550db  cmp     [rcx+26h], ax
0x1800550df  jnz     loc_1800552FD
0x1800550e5  cmp     [rcx+30h], ax
0x1800550e9  jnz     loc_1800552FD
0x1800550ef  cmp     [rcx+3Ah], ax
0x1800550f3  jnz     loc_1800552FD
0x1800550f9  cmp     [rcx+44h], ax
0x1800550fd  jnz     loc_1800552FD
0x180055103  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180055108  jnz     loc_1800552FD
0x18005510e  cmp     edx, 62h ; 'b'
0x180055111  jnz     loc_1800552FD
0x180055117  cmp     [rcx+2], bx
0x18005511b  jnz     loc_1800552FD
0x180055121  lea     rdx, [rsp+4D0h+var_490]
0x180055126  mov     rcx, r14; SourceString
0x180055129  call    IsThisAVolumeName
0x18005512e  test    eax, eax
0x180055130  jz      loc_180055308
0x180055136  cmp     [rsp+4D0h+var_490], r12b
0x18005513b  jz      loc_1800552FD
0x180055141  cmp     [rsp+4D0h+DestinationString.Length], 6
0x180055147  jnz     short loc_180055165
0x180055149  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x18005514e  cmp     word ptr [rax+2], 3Ah ; ':'
0x180055153  jnz     short loc_18005519E
0x180055155  mov     rcx, rsi
0x180055158  mov     rdx, r14
0x18005515b  call    SetVolumeNameForRoot
0x180055160  jmp     loc_18005530A
0x180055165  cmp     [rsp+4D0h+DestinationString.Length], 0Eh
0x18005516b  jnz     short loc_18005519E
0x18005516d  mov     rax, [rsp+4D0h+DestinationString.Buffer]
0x180055172  cmp     [rax], bx
0x180055175  jnz     short loc_18005519E
0x180055177  cmp     [rax+2], bx
0x18005517b  jnz     short loc_18005519E
0x18005517d  cmp     word ptr [rax+4], 2Eh ; '.'
0x180055182  jz      short loc_18005518B
0x180055184  cmp     [rax+4], r13w
0x180055189  jnz     short loc_18005519E
0x18005518b  cmp     [rax+6], bx
0x18005518f  jnz     short loc_18005519E
0x180055191  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x180055196  jnz     short loc_18005519E
0x180055198  lea     rcx, [rsi+8]
0x18005519c  jmp     short loc_180055158
0x18005519e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800551a2  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x1800551a9  mov     [rsp+4D0h+hTemplateFile], rbx; hTemplateFile
0x1800551ae  mov     r15d, 0C0000000h
0x1800551b4  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800551bc  xor     r9d, r9d; lpSecurityAttributes
0x1800551bf  mov     edx, r15d; dwDesiredAccess
0x1800551c2  lea     edi, [rbx+4]
0x1800551c5  mov     r8d, edi; dwShareMode
0x1800551c8  mov     [rsp+4D0h+dwCreationDisposition], edi; dwCreationDisposition
0x1800551cc  call    cs:__imp_CreateFileW
0x1800551d2  cmp     rax, rbx
0x1800551d5  jz      loc_180055308
0x1800551db  mov     rcx, rax; hObject
0x1800551de  call    cs:__imp_CloseHandle
0x1800551e4  mov     [rsp+4D0h+hTemplateFile], rbx; hTemplateFile
0x1800551e9  xor     r9d, r9d; lpSecurityAttributes
0x1800551ec  mov     [rsp+4D0h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x1800551f4  mov     r8d, edi; dwShareMode
0x1800551f7  mov     edx, r15d; dwDesiredAccess
0x1800551fa  mov     [rsp+4D0h+dwCreationDisposition], edi; dwCreationDisposition
0x1800551fe  mov     rcx, rsi; lpFileName
0x180055201  call    cs:__imp_CreateFileW
0x180055207  mov     r15, rax
0x18005520a  cmp     rax, rbx
0x18005520d  jz      loc_180055308
0x180055213  mov     ebx, 104h
0x180055218  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumePathName
0x18005521f  mov     r8d, ebx; cchBufferLength
0x180055222  mov     rcx, rsi; lpszFileName
0x180055225  call    cs:__imp_GetVolumePathNameW
0x18005522b  cmp     eax, 1
0x18005522e  jnz     loc_1800552BD
0x180055234  mov     r8d, ebx; cchBufferLength
0x180055237  lea     rdx, [rsp+4D0h+String]; lpszVolumeName
0x18005523c  lea     rcx, [rbp+3D0h+szVolumeName]; lpszVolumeMountPoint
0x180055243  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180055249  cmp     eax, 1
0x18005524c  jnz     short loc_1800552BD
0x18005524e  lea     rcx, [rsp+4D0h+String]; String
0x180055253  call    cs:__imp_wcslen
0x180055259  mov     rdx, rax
0x18005525c  lea     rcx, [rsp+4D0h+String]
0x180055261  mov     rbx, rax
0x180055264  call    IsVolumeOnCluster
0x180055269  mov     rdx, rbx
0x18005526c  lea     rcx, [rsp+4D0h+String]
0x180055271  mov     r12d, eax
0x180055274  call    IsVolumeOnCSV
0x180055279  movzx   ebx, [rsp+4D0h+var_488.Length]
0x18005527e  mov     edi, eax
0x180055280  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x180055285  shr     rbx, 1
0x180055288  mov     rdx, rbx
0x18005528b  call    IsVolumeOnCluster
0x180055290  mov     rcx, [rsp+4D0h+var_488.Buffer]
0x180055295  mov     rdx, rbx
0x180055298  mov     r13d, eax
0x18005529b  call    IsVolumeOnCSV
0x1800552a0  test    edi, edi
0x1800552a2  jnz     short loc_1800552F4
0x1800552a4  test    eax, eax
0x1800552a6  jnz     short loc_1800552AD
0x1800552a8  cmp     r12d, r13d
0x1800552ab  jnz     short loc_1800552F4
0x1800552ad  xor     ecx, ecx; LastError
0x1800552af  call    cs:__imp_RtlSetLastWin32Error
0x1800552b5  xor     r12d, r12d
0x1800552b8  lea     r13d, [r12+3Fh]
0x1800552bd  call    cs:__imp_KernelBaseGetGlobalData
0x1800552c3  mov     rcx, gs:60h
0x1800552cc  mov     r8d, 4000h; Size
0x1800552d2  mov     edx, [rax]; Flags
0x1800552d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800552d8  call    cs:__imp_RtlAllocateHeap
0x1800552de  mov     rdi, rax
0x1800552e1  test    rax, rax
0x1800552e4  jnz     short loc_180055334
0x1800552e6  mov     rcx, r15; hObject
0x1800552e9  call    cs:__imp_CloseHandle
0x1800552ef  lea     ecx, [rdi+8]
0x1800552f2  jmp     short loc_180055302
0x1800552f4  mov     rcx, r15; hObject
0x1800552f7  call    cs:__imp_CloseHandle
0x1800552fd  mov     ecx, 57h ; 'W'; LastError
0x180055302  call    cs:__imp_RtlSetLastWin32Error
0x180055308  xor     eax, eax
0x18005530a  mov     rcx, [rbp+3D0h+var_40]
0x180055311  xor     rcx, rsp; StackCookie
0x180055314  call    __security_check_cookie
0x180055319  mov     rbx, [rsp+4D0h+arg_10]
0x180055321  add     rsp, 4A0h
0x180055328  pop     r15
0x18005532a  pop     r14
0x18005532c  pop     r13
0x18005532e  pop     r12
0x180055330  pop     rdi
0x180055331  pop     rsi
0x180055332  pop     rbp
0x180055333  retn
0x180055334  lea     rcx, [rax+4]; void *
0x180055338  xor     edx, edx; Val
0x18005533a  mov     r8d, 3FFCh; Size
0x180055340  call    memset_0
0x180055345  mov     dword ptr [rdi], 0A0000003h
0x18005534b  lea     rbx, [rdi+10h]
0x18005534f  movzx   eax, [rsp+4D0h+var_488.Length]
0x180055354  mov     rcx, rbx; void *
0x180055357  add     ax, 6
0x18005535b  mov     dword ptr [rdi+6], 0
0x180055362  add     ax, ax
0x180055365  mov     [rdi+4], ax
0x180055369  movzx   eax, [rsp+4D0h+var_488.Length]
0x18005536e  mov     [rdi+0Ah], ax
0x180055372  mov     r8d, eax; Size
0x180055375  mov     rdx, [rsp+4D0h+var_488.Buffer]; Src
0x18005537a  call    memcpy_0
0x18005537f  movzx   ecx, word ptr [rdi+0Ah]
0x180055383  mov     rdx, rbx; Src
0x180055386  mov     [rdi+12h], r13w
0x18005538b  lea     eax, [rcx+2]
0x18005538e  add     rcx, 2
0x180055392  mov     [rdi+0Ch], ax
0x180055396  add     rcx, rbx; void *
0x180055399  movzx   eax, [rsp+4D0h+var_488.Length]
0x18005539e  mov     r8d, eax; Size
0x1800553a1  mov     [rdi+0Eh], ax
0x1800553a5  call    memcpy_0
0x1800553aa  movzx   r9d, word ptr [rdi+4]
0x1800553af  lea     rax, [rsp+4D0h+BytesReturned]
0x1800553b4  mov     [rsp+4D0h+lpOverlapped], r12; lpOverlapped
0x1800553b9  add     r9d, 8; nInBufferSize
0x1800553bd  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x1800553c2  mov     r8, rdi; lpInBuffer
0x1800553c5  mov     [rsp+4D0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x1800553ca  mov     edx, 900A4h; dwIoControlCode
0x1800553cf  mov     rcx, r15; hDevice
0x1800553d2  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r12; lpOutBuffer
0x1800553d7  call    cs:__imp_DeviceIoControl
0x1800553dd  mov     rcx, gs:60h
0x1800553e6  mov     r8, rdi; P
0x1800553e9  xor     edx, edx; Flags
0x1800553eb  mov     ebx, eax
0x1800553ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800553f1  call    cs:__imp_RtlFreeHeap
0x1800553f7  mov     rcx, r15; hObject
0x1800553fa  call    cs:__imp_CloseHandle
0x180055400  test    ebx, ebx
0x180055402  jz      short loc_180055416
0x180055404  mov     r8d, 1
0x18005540a  mov     rdx, r14
0x18005540d  mov     rcx, rsi
0x180055410  call    cs:__imp_NotifyMountMgr
0x180055416  mov     eax, ebx
0x180055418  jmp     loc_18005530A
0x18005541d  mov     ecx, 0C0000033h
0x180055422  jmp     loc_180054FD7
  ... truncated ...
```
