# PrivMoveFileIdentityW

- ea: `0x180054940`
- end: `0x180054d64`
- name: `PrivMoveFileIdentityW`
- size: `1060`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x18000f920`
- `0x180044c1c`
- `0x180054940`
- `0x18007a840`

## import_xrefs

- `ntdll!NtClose` at `0x180054a9b`
- `ntdll!NtClose` at `0x180054b6a`
- `ntdll!NtClose` at `0x180054d06`
- `ntdll!NtClose` at `0x180054d17`
- `ntdll!NtClose` at `0x180054a9b`
- `ntdll!NtClose` at `0x180054b6a`
- `ntdll!NtClose` at `0x180054d06`
- `ntdll!NtClose` at `0x180054d17`
- `ntdll!NtQueryInformationFile` at `0x180054bc4`
- `ntdll!NtQueryInformationFile` at `0x180054bc4`
- `ntdll!NtSetInformationFile` at `0x180054c1f`
- `ntdll!NtSetInformationFile` at `0x180054cf3`
- `ntdll!NtSetInformationFile` at `0x180054c1f`
- `ntdll!NtSetInformationFile` at `0x180054cf3`
- `ntdll!RtlFreeHeap` at `0x180054a81`
- `ntdll!RtlFreeHeap` at `0x180054b50`
- `ntdll!RtlFreeHeap` at `0x180054ca5`
- `ntdll!RtlFreeHeap` at `0x180054cc4`
- `ntdll!RtlFreeHeap` at `0x18007b608`
- `ntdll!RtlFreeHeap` at `0x18007b627`
- `ntdll!RtlFreeHeap` at `0x180054a81`
- `ntdll!RtlFreeHeap` at `0x180054b50`
- `ntdll!RtlFreeHeap` at `0x180054ca5`
- `ntdll!RtlFreeHeap` at `0x180054cc4`
- `ntdll!RtlFreeHeap` at `0x18007b608`
- `ntdll!RtlFreeHeap` at `0x18007b627`
- `KERNELBASE!BasepNotifyTrackingService` at `0x180054c68`
- `KERNELBASE!BasepNotifyTrackingService` at `0x180054c68`

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
0x180054940  mov     r11, rsp
0x180054943  mov     [r11+18h], rbx
0x180054947  mov     [r11+20h], rsi
0x18005494b  push    rdi
0x18005494c  push    r12
0x18005494e  push    r13
0x180054950  push    r14
0x180054952  push    r15
0x180054954  sub     rsp, 160h
0x18005495b  mov     rax, cs:__security_cookie
0x180054962  xor     rax, rsp
0x180054965  mov     [rsp+188h+var_30], rax
0x18005496d  mov     r15d, r8d
0x180054970  mov     r13, rdx
0x180054973  mov     r14, rcx
0x180054976  xor     ecx, ecx
0x180054978  mov     edi, ecx
0x18005497a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005497e  mov     [rsp+188h+Handle], rax
0x180054983  mov     [rsp+188h+FileHandle], rax
0x180054988  mov     [r11-100h], rcx
0x18005498f  mov     [r11-0F8h], rcx
0x180054996  mov     [rsp+188h+P], rcx
0x18005499b  mov     [rsp+188h+var_110], rcx
0x1800549a0  mov     [r11-108h], rcx
0x1800549a7  mov     [rsp+188h+var_118], rcx
0x1800549ac  xor     eax, eax
0x1800549ae  xorps   xmm0, xmm0
0x1800549b1  movups  [rsp+188h+var_E0], xmm0
0x1800549b9  movups  [rsp+188h+var_D0], xmm0
0x1800549c1  movups  [rsp+188h+var_D0+0Ch], xmm0
0x1800549c9  movups  [rsp+188h+var_B0], xmm0
0x1800549d1  movups  [rsp+188h+var_A0], xmm0
0x1800549d9  movups  [rsp+188h+var_A0+0Ch], xmm0
0x1800549e1  mov     [rsp+188h+var_144], 1
0x1800549e6  movups  xmmword ptr [rsp+188h+IoStatusBlock], xmm0
0x1800549ee  xorps   xmm1, xmm1
0x1800549f1  movups  xmmword ptr [r11-58h], xmm1
0x1800549f6  movups  xmmword ptr [r11-48h], xmm1
0x1800549fb  mov     [r11-38h], rax
0x1800549ff  movups  xmmword ptr [r11-80h], xmm0
0x180054a04  movups  xmmword ptr [r11-70h], xmm0
0x180054a09  mov     [r11-60h], rax
0x180054a0d  mov     esi, 82h
0x180054a12  mov     [rsp+188h+var_128], esi
0x180054a16  mov     r12d, r8d
0x180054a19  and     r12d, 1
0x180054a1d  mov     eax, 10082h
0x180054a22  cmovnz  esi, eax
0x180054a25  mov     [rsp+188h+var_128], esi
0x180054a29  mov     [rsp+188h+var_160], esi
0x180054a2d  lea     rax, [rsp+188h+var_E0]
0x180054a35  mov     qword ptr [rsp+188h+FileInformationClass], rax
0x180054a3a  lea     r9, [rsp+188h+Handle]
0x180054a3f  lea     r8, [rsp+188h+P]
0x180054a44  lea     rdx, [rsp+188h+var_100]
0x180054a4c  mov     rcx, r14
0x180054a4f  call    BasepOpenFileForMove
0x180054a54  mov     ebx, eax
0x180054a56  mov     [rsp+188h+var_148], eax
0x180054a5a  test    eax, eax
0x180054a5c  jns     short loc_180054AC7
0x180054a5e  mov     ecx, esi
0x180054a60  and     ecx, r15d
0x180054a63  test    cl, 2
0x180054a66  jz      short loc_180054AC7
0x180054a68  mov     r8, [rsp+188h+P]; P
0x180054a6d  test    r8, r8
0x180054a70  jz      short loc_180054A90
0x180054a72  mov     rcx, gs:60h
0x180054a7b  xor     edx, edx; Flags
0x180054a7d  mov     rcx, [rcx+30h]; HeapHandle
0x180054a81  call    cs:__imp_RtlFreeHeap
0x180054a87  mov     [rsp+188h+P], 0
0x180054a90  mov     rcx, [rsp+188h+Handle]; Handle
0x180054a95  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054a99  jz      short loc_180054AAA
0x180054a9b  call    cs:__imp_NtClose
0x180054aa1  mov     [rsp+188h+Handle], 0FFFFFFFFFFFFFFFFh
0x180054aaa  and     esi, 0FFFFFFFDh
0x180054aad  mov     [rsp+188h+var_128], esi
0x180054ab1  test    edi, edi
0x180054ab3  cmovns  edi, ebx
0x180054ab6  mov     [rsp+188h+var_140], edi
0x180054aba  mov     [rsp+188h+var_148], 0
0x180054ac2  jmp     loc_180054A29
0x180054ac7  test    ebx, ebx
0x180054ac9  js      loc_180054C8C
0x180054acf  mov     [rsp+188h+var_124], 100h
0x180054ad7  and     esi, 2
0x180054ada  mov     eax, 102h
0x180054adf  lea     r14d, [rax-2]
0x180054ae3  cmovnz  r14d, eax
0x180054ae7  mov     [rsp+188h+var_124], r14d
0x180054aec  mov     eax, esi
0x180054aee  neg     eax
0x180054af0  sbb     ecx, ecx
0x180054af2  and     ecx, 2
0x180054af5  add     ecx, 100h
0x180054afb  mov     [rsp+188h+var_160], ecx
0x180054aff  lea     rax, [rsp+188h+var_B0]
0x180054b07  mov     qword ptr [rsp+188h+FileInformationClass], rax
0x180054b0c  lea     r9, [rsp+188h+FileHandle]
0x180054b11  lea     r8, [rsp+188h+var_118]
0x180054b16  lea     rdx, [rsp+188h+var_110]
0x180054b1b  mov     rcx, r13
0x180054b1e  call    BasepOpenFileForMove
0x180054b23  mov     ebx, eax
0x180054b25  mov     [rsp+188h+var_148], eax
0x180054b29  test    eax, eax
0x180054b2b  jns     short loc_180054B98
0x180054b2d  mov     eax, r14d
0x180054b30  and     eax, r15d
0x180054b33  test    al, 2
0x180054b35  jz      short loc_180054B98
0x180054b37  mov     r8, [rsp+188h+var_118]; P
0x180054b3c  test    r8, r8
0x180054b3f  jz      short loc_180054B5F
0x180054b41  mov     rcx, gs:60h
0x180054b4a  xor     edx, edx; Flags
0x180054b4c  mov     rcx, [rcx+30h]; HeapHandle
0x180054b50  call    cs:__imp_RtlFreeHeap
0x180054b56  mov     [rsp+188h+var_118], 0
0x180054b5f  mov     rcx, [rsp+188h+FileHandle]; Handle
0x180054b64  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054b68  jz      short loc_180054B79
0x180054b6a  call    cs:__imp_NtClose
0x180054b70  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180054b79  and     r14d, 0FFFFFFFDh
0x180054b7d  mov     [rsp+188h+var_124], r14d
0x180054b82  test    edi, edi
0x180054b84  cmovns  edi, ebx
0x180054b87  mov     [rsp+188h+var_140], edi
0x180054b8b  mov     [rsp+188h+var_148], 0
0x180054b93  jmp     loc_180054AEC
0x180054b98  test    ebx, ebx
0x180054b9a  js      loc_180054C8C
0x180054ba0  mov     r13d, 4
0x180054ba6  mov     [rsp+188h+FileInformationClass], r13d; FileInformationClass
0x180054bab  lea     r9d, [r13+24h]; Length
0x180054baf  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x180054bb7  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180054bbf  mov     rcx, [rsp+188h+Handle]; FileHandle
0x180054bc4  call    cs:__imp_NtQueryInformationFile
0x180054bca  mov     ebx, eax
0x180054bcc  mov     [rsp+188h+var_148], eax
0x180054bd0  test    eax, eax
0x180054bd2  js      short loc_180054C2B
0x180054bd4  xorps   xmm0, xmm0
0x180054bd7  xor     eax, eax
0x180054bd9  movups  [rsp+188h+var_80], xmm0
0x180054be1  movups  [rsp+188h+var_70], xmm0
0x180054be9  mov     [rsp+188h+var_60], rax
0x180054bf1  mov     rax, [rsp+188h+FileInformation]
0x180054bf9  mov     qword ptr [rsp+188h+var_80], rax
0x180054c01  mov     [rsp+188h+FileInformationClass], r13d; FileInformationClass
0x180054c06  lea     r9d, [r13+24h]; Length
0x180054c0a  lea     r8, [rsp+188h+var_80]; FileInformation
0x180054c12  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180054c1a  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x180054c1f  call    cs:__imp_NtSetInformationFile
0x180054c25  mov     ebx, eax
0x180054c27  mov     [rsp+188h+var_148], eax
0x180054c2b  and     r15d, 2
0x180054c2f  test    ebx, ebx
0x180054c31  jns     short loc_180054C47
0x180054c33  test    r15d, r15d
0x180054c36  jz      short loc_180054C8C
0x180054c38  test    edi, edi
0x180054c3a  cmovns  edi, ebx
0x180054c3d  mov     [rsp+188h+var_140], edi
0x180054c41  xor     ebx, ebx
0x180054c43  mov     [rsp+188h+var_148], ebx
0x180054c47  test    r14b, 2
0x180054c4b  jz      short loc_180054C8C
0x180054c4d  test    esi, esi
0x180054c4f  jz      short loc_180054C8C
0x180054c51  lea     r9, [rsp+188h+var_110]
0x180054c56  mov     r8, [rsp+188h+FileHandle]
0x180054c5b  lea     rdx, [rsp+188h+var_E0]
0x180054c63  lea     rcx, [rsp+188h+Handle]
0x180054c68  call    cs:__imp_BasepNotifyTrackingService
0x180054c6e  mov     ebx, eax
0x180054c70  mov     [rsp+188h+var_148], eax
0x180054c74  test    eax, eax
0x180054c76  jns     short loc_180054C8C
0x180054c78  test    r15d, r15d
0x180054c7b  jz      short loc_180054C8C
0x180054c7d  test    edi, edi
0x180054c7f  cmovns  edi, eax
0x180054c82  mov     [rsp+188h+var_140], edi
0x180054c86  xor     ebx, ebx
0x180054c88  mov     [rsp+188h+var_148], ebx
0x180054c8c  mov     r8, [rsp+188h+P]; P
0x180054c91  test    r8, r8
0x180054c94  jz      short loc_180054CAB
0x180054c96  mov     rcx, gs:60h
0x180054c9f  xor     edx, edx; Flags
0x180054ca1  mov     rcx, [rcx+30h]; HeapHandle
0x180054ca5  call    cs:__imp_RtlFreeHeap
0x180054cab  mov     r8, [rsp+188h+var_118]; P
0x180054cb0  test    r8, r8
0x180054cb3  jz      short loc_180054CCA
0x180054cb5  mov     rcx, gs:60h
0x180054cbe  xor     edx, edx; Flags
0x180054cc0  mov     rcx, [rcx+30h]; HeapHandle
0x180054cc4  call    cs:__imp_RtlFreeHeap
0x180054cca  test    ebx, ebx
0x180054ccc  js      short loc_180054CFB
0x180054cce  test    r12d, r12d
0x180054cd1  jz      short loc_180054CFB
0x180054cd3  mov     [rsp+188h+FileInformationClass], 0Dh; FileInformationClass
0x180054cdb  mov     r9d, 1; Length
0x180054ce1  lea     r8, [rsp+188h+var_144]; FileInformation
0x180054ce6  lea     rdx, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x180054cee  mov     rcx, [rsp+188h+Handle]; FileHandle
0x180054cf3  call    cs:__imp_NtSetInformationFile
0x180054cf9  mov     ebx, eax
0x180054cfb  mov     rcx, [rsp+188h+FileHandle]; Handle
0x180054d00  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054d04  jz      short loc_180054D0C
0x180054d06  call    cs:__imp_NtClose
0x180054d0c  mov     rcx, [rsp+188h+Handle]; Handle
0x180054d11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054d15  jz      short loc_180054D1D
0x180054d17  call    cs:__imp_NtClose
0x180054d1d  test    ebx, ebx
0x180054d1f  jns     short loc_180054D25
0x180054d21  mov     ecx, ebx
0x180054d23  jmp     short loc_180054D2B
0x180054d25  test    edi, edi
0x180054d27  jns     short loc_180054D30
0x180054d29  mov     ecx, edi
0x180054d2b  call    BaseSetLastNTError
0x180054d30  xor     eax, eax
0x180054d32  test    ebx, ebx
0x180054d34  setns   al
0x180054d37  mov     rcx, [rsp+188h+var_30]
0x180054d3f  xor     rcx, rsp; StackCookie
0x180054d42  call    __security_check_cookie
0x180054d47  lea     r11, [rsp+188h+var_28]
0x180054d4f  mov     rbx, [r11+40h]
0x180054d53  mov     rsi, [r11+48h]
0x180054d57  mov     rsp, r11
0x180054d5a  pop     r15
0x180054d5c  pop     r14
0x180054d5e  pop     r13
0x180054d60  pop     r12
0x180054d62  pop     rdi
0x180054d63  retn
0x18007b5e7  push    rbp
0x18007b5e9  sub     rsp, 40h
0x18007b5ed  mov     rbp, rdx
0x18007b5f0  mov     r8, [rbp+68h]; P
0x18007b5f4  test    r8, r8
0x18007b5f7  jz      short loc_18007B60F
0x18007b5f9  mov     rcx, gs:60h
0x18007b602  xor     edx, edx; Flags
0x18007b604  mov     rcx, [rcx+30h]; HeapHandle
0x18007b608  call    cs:__imp_RtlFreeHeap
0x18007b60e  nop
0x18007b60f  mov     r8, [rbp+70h]; P
0x18007b613  test    r8, r8
0x18007b616  jz      short loc_18007B62E
0x18007b618  mov     rcx, gs:60h
0x18007b621  xor     edx, edx; Flags
0x18007b623  mov     rcx, [rcx+30h]; HeapHandle
0x18007b627  call    cs:__imp_RtlFreeHeap
0x18007b62d  nop
0x18007b62e  add     rsp, 40h
0x18007b632  pop     rbp
0x18007b633  retn
```
