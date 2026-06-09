# PrivMoveFileIdentityW

- ea: `0x1800598f0`
- end: `0x180059d5d`
- name: `PrivMoveFileIdentityW`
- size: `1133`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x18000ccf0`
- `0x180049248`
- `0x1800598f0`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtClose` at `0x180059a51`
- `ntdll!NtClose` at `0x180059b2c`
- `ntdll!NtClose` at `0x180059cf2`
- `ntdll!NtClose` at `0x180059d09`
- `ntdll!NtClose` at `0x180059a51`
- `ntdll!NtClose` at `0x180059b2c`
- `ntdll!NtClose` at `0x180059cf2`
- `ntdll!NtClose` at `0x180059d09`
- `ntdll!NtQueryInformationFile` at `0x180059b8c`
- `ntdll!NtQueryInformationFile` at `0x180059b8c`
- `ntdll!NtSetInformationFile` at `0x180059bed`
- `ntdll!NtSetInformationFile` at `0x180059cd9`
- `ntdll!NtSetInformationFile` at `0x180059bed`
- `ntdll!NtSetInformationFile` at `0x180059cd9`
- `ntdll!RtlFreeHeap` at `0x180059a31`
- `ntdll!RtlFreeHeap` at `0x180059b0c`
- `ntdll!RtlFreeHeap` at `0x180059c7f`
- `ntdll!RtlFreeHeap` at `0x180059ca4`
- `ntdll!RtlFreeHeap` at `0x180083703`
- `ntdll!RtlFreeHeap` at `0x180083728`
- `ntdll!RtlFreeHeap` at `0x180059a31`
- `ntdll!RtlFreeHeap` at `0x180059b0c`
- `ntdll!RtlFreeHeap` at `0x180059c7f`
- `ntdll!RtlFreeHeap` at `0x180059ca4`
- `ntdll!RtlFreeHeap` at `0x180083703`
- `ntdll!RtlFreeHeap` at `0x180083728`
- `KERNELBASE!BasepNotifyTrackingService` at `0x180059c3c`
- `KERNELBASE!BasepNotifyTrackingService` at `0x180059c3c`

## pseudocode

```c
_BOOL8 __fastcall PrivMoveFileIdentityW(const WCHAR *a1, const WCHAR *a2, unsigned __int8 a3)
{
  int v6; // edi
  int v7; // esi
  int v8; // r12d
  int v9; // ebx
  int v10; // esi
  int v11; // r14d
  int v12; // r15d
  int v13; // eax
  __int64 v14; // rcx
  char v16[4]; // [rsp+44h] [rbp-144h] BYREF
  int v17; // [rsp+48h] [rbp-140h]
  HANDLE Handle; // [rsp+50h] [rbp-138h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-130h] BYREF
  int v20; // [rsp+60h] [rbp-128h]
  int v21; // [rsp+64h] [rbp-124h]
  PVOID P; // [rsp+68h] [rbp-120h] BYREF
  PVOID v23; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v24[2]; // [rsp+78h] [rbp-110h] BYREF
  _QWORD v25[2]; // [rsp+88h] [rbp-100h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-F0h] BYREF
  struct _OBJECT_ATTRIBUTES v27; // [rsp+A8h] [rbp-E0h] BYREF
  struct _OBJECT_ATTRIBUTES v28; // [rsp+D8h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+108h] [rbp-80h] BYREF
  __int128 v30; // [rsp+118h] [rbp-70h]
  __int64 v31; // [rsp+128h] [rbp-60h]
  _QWORD FileInformation[5]; // [rsp+130h] [rbp-58h] BYREF

  v6 = 0;
  Handle = (HANDLE)-1LL;
  FileHandle = (HANDLE)-1LL;
  v25[0] = 0;
  v25[1] = 0;
  P = 0;
  v24[0] = 0;
  v24[1] = 0;
  v23 = 0;
  memset(&v27, 0, 44);
  memset(&v28, 0, 44);
  v16[0] = 1;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v7 = 130;
  v20 = 130;
  v8 = a3 & 1;
  if ( (a3 & 1) != 0 )
    v7 = 65666;
  v20 = v7;
  while ( 1 )
  {
    v9 = BasepOpenFileForMove(a1, (__int64)v25, &P, &Handle, &v27, v7);
    if ( v9 >= 0 || (a3 & (unsigned __int8)v7 & 2) == 0 )
      break;
    if ( P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      P = 0;
    }
    if ( Handle != (HANDLE)-1LL )
    {
      NtClose(Handle);
      Handle = (HANDLE)-1LL;
    }
    v7 &= ~2u;
    v20 = v7;
    if ( v6 >= 0 )
      v6 = v9;
    v17 = v6;
  }
  if ( v9 >= 0 )
  {
    v21 = 256;
    v10 = v7 & 2;
    v11 = 256;
    if ( v10 )
      v11 = 258;
    v21 = v11;
    while ( 1 )
    {
      v9 = BasepOpenFileForMove(a2, (__int64)v24, &v23, &FileHandle, &v28, v10 != 0 ? 258 : 256);
      if ( v9 >= 0 || (a3 & (unsigned __int8)v11 & 2) == 0 )
        break;
      if ( v23 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
        v23 = 0;
      }
      if ( FileHandle != (HANDLE)-1LL )
      {
        NtClose(FileHandle);
        FileHandle = (HANDLE)-1LL;
      }
      v11 &= ~2u;
      v21 = v11;
      if ( v6 >= 0 )
        v6 = v9;
      v17 = v6;
    }
    if ( v9 >= 0 )
    {
      v9 = NtQueryInformationFile(Handle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v9 >= 0 )
      {
        v30 = 0;
        v31 = 0;
        v29 = FileInformation[0];
        v9 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v29, 0x28u, FileBasicInformation);
      }
      v12 = a3 & 2;
      if ( v9 < 0 )
      {
        if ( !v12 )
          goto LABEL_41;
        if ( v6 >= 0 )
          v6 = v9;
        v17 = v6;
        v9 = 0;
      }
      if ( (v11 & 2) != 0 )
      {
        if ( v10 )
        {
          v13 = BasepNotifyTrackingService(&Handle, &v27, FileHandle, v24);
          v9 = v13;
          if ( v13 < 0 )
          {
            if ( v12 )
            {
              if ( v6 >= 0 )
                v6 = v13;
              v17 = v6;
              v9 = 0;
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v23 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
  if ( v9 >= 0 && v8 )
    v9 = NtSetInformationFile(Handle, &IoStatusBlock, v16, 1u, FileDispositionInformation);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
  if ( v9 < 0 )
  {
    v14 = (unsigned int)v9;
LABEL_56:
    BaseSetLastNTError(v14);
    return v9 >= 0;
  }
  if ( v6 < 0 )
  {
    v14 = (unsigned int)v6;
    goto LABEL_56;
  }
  return v9 >= 0;
}

```

## disassembly

```asm
0x1800598f0  mov     r11, rsp
0x1800598f3  mov     [r11+18h], rbx
0x1800598f7  mov     [r11+20h], rsi
0x1800598fb  push    rdi
0x1800598fc  push    r12
0x1800598fe  push    r13
0x180059900  push    r14
0x180059902  push    r15
0x180059904  sub     rsp, 160h
0x18005990b  mov     rax, cs:__security_cookie
0x180059912  xor     rax, rsp
0x180059915  mov     [rsp+188h+var_30], rax
0x18005991d  mov     r15d, r8d
0x180059920  mov     r13, rdx
0x180059923  mov     r14, rcx
0x180059926  xor     ecx, ecx
0x180059928  mov     edi, ecx
0x18005992a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005992e  mov     [rsp+188h+Handle], rax
0x180059933  mov     [rsp+188h+FileHandle], rax
0x180059938  mov     [r11-100h], rcx
0x18005993f  mov     [r11-0F8h], rcx
0x180059946  mov     [rsp+188h+P], rcx
0x18005994b  mov     [rsp+188h+var_110], rcx
0x180059950  mov     [r11-108h], rcx
0x180059957  mov     [rsp+188h+var_118], rcx
0x18005995c  xor     eax, eax
0x18005995e  xorps   xmm0, xmm0
0x180059961  movups  [rsp+188h+var_E0], xmm0
0x180059969  movups  [rsp+188h+var_D0], xmm0
0x180059971  movups  [rsp+188h+var_D0+0Ch], xmm0
0x180059979  movups  [rsp+188h+var_B0], xmm0
0x180059981  movups  [rsp+188h+var_A0], xmm0
0x180059989  movups  [rsp+188h+var_A0+0Ch], xmm0
0x180059991  mov     [rsp+188h+var_144], 1
0x180059996  movups  xmmword ptr [rsp+188h+IoStatusBlock], xmm0
0x18005999e  xorps   xmm1, xmm1
0x1800599a1  movups  xmmword ptr [r11-58h], xmm1
0x1800599a6  movups  xmmword ptr [r11-48h], xmm1
0x1800599ab  mov     [r11-38h], rax
0x1800599af  movups  xmmword ptr [r11-80h], xmm0
0x1800599b4  movups  xmmword ptr [r11-70h], xmm0
0x1800599b9  mov     [r11-60h], rax
0x1800599bd  mov     esi, 82h
0x1800599c2  mov     [rsp+188h+var_128], esi
0x1800599c6  mov     r12d, r8d
0x1800599c9  and     r12d, 1
0x1800599cd  mov     eax, 10082h
0x1800599d2  cmovnz  esi, eax
0x1800599d5  mov     [rsp+188h+var_128], esi
0x1800599d9  mov     [rsp+188h+var_160], esi
0x1800599dd  lea     rax, [rsp+188h+var_E0]
0x1800599e5  mov     qword ptr [rsp+188h+FileInformationClass], rax
0x1800599ea  lea     r9, [rsp+188h+Handle]
0x1800599ef  lea     r8, [rsp+188h+P]
0x1800599f4  lea     rdx, [rsp+188h+var_100]
0x1800599fc  mov     rcx, r14
0x1800599ff  call    BasepOpenFileForMove
0x180059a04  mov     ebx, eax
0x180059a06  mov     [rsp+188h+var_148], eax
0x180059a0a  test    eax, eax
0x180059a0c  jns     short loc_180059A83
0x180059a0e  mov     ecx, esi
0x180059a10  and     ecx, r15d
0x180059a13  test    cl, 2
0x180059a16  jz      short loc_180059A83
0x180059a18  mov     r8, [rsp+188h+P]; P
0x180059a1d  test    r8, r8
0x180059a20  jz      short loc_180059A46
0x180059a22  mov     rcx, gs:60h
0x180059a2b  xor     edx, edx; Flags
0x180059a2d  mov     rcx, [rcx+30h]; HeapHandle
0x180059a31  call    cs:__imp_RtlFreeHeap
0x180059a38  nop     dword ptr [rax+rax+00h]
0x180059a3d  mov     [rsp+188h+P], 0
0x180059a46  mov     rcx, [rsp+188h+Handle]; Handle
0x180059a4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180059a4f  jz      short loc_180059A66
0x180059a51  call    cs:__imp_NtClose
0x180059a58  nop     dword ptr [rax+rax+00h]
0x180059a5d  mov     [rsp+188h+Handle], 0FFFFFFFFFFFFFFFFh
0x180059a66  and     esi, 0FFFFFFFDh
0x180059a69  mov     [rsp+188h+var_128], esi
0x180059a6d  test    edi, edi
0x180059a6f  cmovns  edi, ebx
0x180059a72  mov     [rsp+188h+var_140], edi
0x180059a76  mov     [rsp+188h+var_148], 0
0x180059a7e  jmp     loc_1800599D9
0x180059a83  test    ebx, ebx
0x180059a85  js      loc_180059C66
0x180059a8b  mov     [rsp+188h+var_124], 100h
0x180059a93  and     esi, 2
0x180059a96  mov     eax, 102h
0x180059a9b  lea     r14d, [rax-2]
0x180059a9f  cmovnz  r14d, eax
0x180059aa3  mov     [rsp+188h+var_124], r14d
0x180059aa8  mov     eax, esi
0x180059aaa  neg     eax
0x180059aac  sbb     ecx, ecx
0x180059aae  and     ecx, 2
0x180059ab1  add     ecx, 100h
0x180059ab7  mov     [rsp+188h+var_160], ecx
0x180059abb  lea     rax, [rsp+188h+var_B0]
0x180059ac3  mov     qword ptr [rsp+188h+FileInformationClass], rax
0x180059ac8  lea     r9, [rsp+188h+FileHandle]
0x180059acd  lea     r8, [rsp+188h+var_118]
0x180059ad2  lea     rdx, [rsp+188h+var_110]
0x180059ad7  mov     rcx, r13
0x180059ada  call    BasepOpenFileForMove
0x180059adf  mov     ebx, eax
0x180059ae1  mov     [rsp+188h+var_148], eax
0x180059ae5  test    eax, eax
0x180059ae7  jns     short loc_180059B60
0x180059ae9  mov     eax, r14d
0x180059aec  and     eax, r15d
0x180059aef  test    al, 2
0x180059af1  jz      short loc_180059B60
0x180059af3  mov     r8, [rsp+188h+var_118]; P
0x180059af8  test    r8, r8
0x180059afb  jz      short loc_180059B21
0x180059afd  mov     rcx, gs:60h
0x180059b06  xor     edx, edx; Flags
0x180059b08  mov     rcx, [rcx+30h]; HeapHandle
0x180059b0c  call    cs:__imp_RtlFreeHeap
0x180059b13  nop     dword ptr [rax+rax+00h]
0x180059b18  mov     [rsp+188h+var_118], 0
0x180059b21  mov     rcx, [rsp+188h+FileHandle]; Handle
0x180059b26  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180059b2a  jz      short loc_180059B41
0x180059b2c  call    cs:__imp_NtClose
0x180059b33  nop     dword ptr [rax+rax+00h]
0x180059b38  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180059b41  and     r14d, 0FFFFFFFDh
0x180059b45  mov     [rsp+188h+var_124], r14d
0x180059b4a  test    edi, edi
0x180059b4c  cmovns  edi, ebx
0x180059b4f  mov     [rsp+188h+var_140], edi
0x180059b53  mov     [rsp+188h+var_148], 0
0x180059b5b  jmp     loc_180059AA8
0x180059b60  test    ebx, ebx
0x180059b62  js      loc_180059C66
0x180059b68  mov     r13d, 4
0x180059b6e  mov     [rsp+188h+FileInformationClass], r13d; FileInformationClass
0x180059b73  lea     r9d, [r13+24h]; Length
0x180059b77  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x180059b7f  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180059b87  mov     rcx, [rsp+188h+Handle]; FileHandle
0x180059b8c  call    cs:__imp_NtQueryInformationFile
0x180059b93  nop     dword ptr [rax+rax+00h]
0x180059b98  mov     ebx, eax
0x180059b9a  mov     [rsp+188h+var_148], eax
0x180059b9e  test    eax, eax
0x180059ba0  js      short loc_180059BFF
0x180059ba2  xorps   xmm0, xmm0
0x180059ba5  xor     eax, eax
0x180059ba7  movups  [rsp+188h+var_80], xmm0
0x180059baf  movups  [rsp+188h+var_70], xmm0
0x180059bb7  mov     [rsp+188h+var_60], rax
0x180059bbf  mov     rax, [rsp+188h+FileInformation]
0x180059bc7  mov     qword ptr [rsp+188h+var_80], rax
0x180059bcf  mov     [rsp+188h+FileInformationClass], r13d; FileInformationClass
0x180059bd4  lea     r9d, [r13+24h]; Length
0x180059bd8  lea     r8, [rsp+188h+var_80]; FileInformation
0x180059be0  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180059be8  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x180059bed  call    cs:__imp_NtSetInformationFile
0x180059bf4  nop     dword ptr [rax+rax+00h]
0x180059bf9  mov     ebx, eax
0x180059bfb  mov     [rsp+188h+var_148], eax
0x180059bff  and     r15d, 2
0x180059c03  test    ebx, ebx
0x180059c05  jns     short loc_180059C1B
0x180059c07  test    r15d, r15d
0x180059c0a  jz      short loc_180059C66
0x180059c0c  test    edi, edi
0x180059c0e  cmovns  edi, ebx
0x180059c11  mov     [rsp+188h+var_140], edi
0x180059c15  xor     ebx, ebx
0x180059c17  mov     [rsp+188h+var_148], ebx
0x180059c1b  test    r14b, 2
0x180059c1f  jz      short loc_180059C66
0x180059c21  test    esi, esi
0x180059c23  jz      short loc_180059C66
0x180059c25  lea     r9, [rsp+188h+var_110]
0x180059c2a  mov     r8, [rsp+188h+FileHandle]
0x180059c2f  lea     rdx, [rsp+188h+var_E0]
0x180059c37  lea     rcx, [rsp+188h+Handle]
0x180059c3c  call    cs:__imp_BasepNotifyTrackingService
0x180059c43  nop     dword ptr [rax+rax+00h]
0x180059c48  mov     ebx, eax
0x180059c4a  mov     [rsp+188h+var_148], eax
0x180059c4e  test    eax, eax
0x180059c50  jns     short loc_180059C66
0x180059c52  test    r15d, r15d
0x180059c55  jz      short loc_180059C66
0x180059c57  test    edi, edi
0x180059c59  cmovns  edi, eax
0x180059c5c  mov     [rsp+188h+var_140], edi
0x180059c60  xor     ebx, ebx
0x180059c62  mov     [rsp+188h+var_148], ebx
0x180059c66  mov     r8, [rsp+188h+P]; P
0x180059c6b  test    r8, r8
0x180059c6e  jz      short loc_180059C8B
0x180059c70  mov     rcx, gs:60h
0x180059c79  xor     edx, edx; Flags
0x180059c7b  mov     rcx, [rcx+30h]; HeapHandle
0x180059c7f  call    cs:__imp_RtlFreeHeap
0x180059c86  nop     dword ptr [rax+rax+00h]
0x180059c8b  mov     r8, [rsp+188h+var_118]; P
0x180059c90  test    r8, r8
0x180059c93  jz      short loc_180059CB0
0x180059c95  mov     rcx, gs:60h
0x180059c9e  xor     edx, edx; Flags
0x180059ca0  mov     rcx, [rcx+30h]; HeapHandle
0x180059ca4  call    cs:__imp_RtlFreeHeap
0x180059cab  nop     dword ptr [rax+rax+00h]
0x180059cb0  test    ebx, ebx
0x180059cb2  js      short loc_180059CE7
0x180059cb4  test    r12d, r12d
0x180059cb7  jz      short loc_180059CE7
0x180059cb9  mov     [rsp+188h+FileInformationClass], 0Dh; FileInformationClass
0x180059cc1  mov     r9d, 1; Length
0x180059cc7  lea     r8, [rsp+188h+var_144]; FileInformation
0x180059ccc  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180059cd4  mov     rcx, [rsp+188h+Handle]; FileHandle
0x180059cd9  call    cs:__imp_NtSetInformationFile
0x180059ce0  nop     dword ptr [rax+rax+00h]
0x180059ce5  mov     ebx, eax
0x180059ce7  mov     rcx, [rsp+188h+FileHandle]; Handle
0x180059cec  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180059cf0  jz      short loc_180059CFE
0x180059cf2  call    cs:__imp_NtClose
0x180059cf9  nop     dword ptr [rax+rax+00h]
0x180059cfe  mov     rcx, [rsp+188h+Handle]; Handle
0x180059d03  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180059d07  jz      short loc_180059D15
0x180059d09  call    cs:__imp_NtClose
0x180059d10  nop     dword ptr [rax+rax+00h]
0x180059d15  test    ebx, ebx
0x180059d17  jns     short loc_180059D1D
0x180059d19  mov     ecx, ebx
0x180059d1b  jmp     short loc_180059D23
0x180059d1d  test    edi, edi
0x180059d1f  jns     short loc_180059D28
0x180059d21  mov     ecx, edi
0x180059d23  call    BaseSetLastNTError
0x180059d28  xor     eax, eax
0x180059d2a  test    ebx, ebx
0x180059d2c  setns   al
0x180059d2f  mov     rcx, [rsp+188h+var_30]
0x180059d37  xor     rcx, rsp; StackCookie
0x180059d3a  call    __security_check_cookie
0x180059d3f  lea     r11, [rsp+188h+var_28]
0x180059d47  mov     rbx, [r11+40h]
0x180059d4b  mov     rsi, [r11+48h]
0x180059d4f  mov     rsp, r11
0x180059d52  pop     r15
0x180059d54  pop     r14
0x180059d56  pop     r13
0x180059d58  pop     r12
0x180059d5a  pop     rdi
0x180059d5b  retn
0x1800836e2  push    rbp
0x1800836e4  sub     rsp, 40h
0x1800836e8  mov     rbp, rdx
0x1800836eb  mov     r8, [rbp+68h]; P
0x1800836ef  test    r8, r8
0x1800836f2  jz      short loc_180083710
0x1800836f4  mov     rcx, gs:60h
0x1800836fd  xor     edx, edx; Flags
0x1800836ff  mov     rcx, [rcx+30h]; HeapHandle
0x180083703  call    cs:__imp_RtlFreeHeap
0x18008370a  nop     dword ptr [rax+rax+00h]
0x18008370f  nop
0x180083710  mov     r8, [rbp+70h]; P
0x180083714  test    r8, r8
0x180083717  jz      short loc_180083735
0x180083719  mov     rcx, gs:60h
0x180083722  xor     edx, edx; Flags
0x180083724  mov     rcx, [rcx+30h]; HeapHandle
0x180083728  call    cs:__imp_RtlFreeHeap
0x18008372f  nop     dword ptr [rax+rax+00h]
0x180083734  nop
0x180083735  add     rsp, 40h
0x180083739  pop     rbp
0x18008373a  retn
```
