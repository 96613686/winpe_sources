# CreateLogContainerScanContext

- ea: `0x180009d40`
- end: `0x180009fd4`
- name: `CreateLogContainerScanContext`
- size: `660`
- prototype: `BOOL __stdcall(HANDLE hLog, ULONG cFromContainer, ULONG cContainers, CLFS_SCAN_MODE eScanMode, PCLFS_SCAN_CONTEXT pcxScan, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800018a4`
- `0x180009d40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009f57`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800152f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009f57`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800152f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001534d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001534d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f26`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009f16`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009f16`

## pseudocode

```c
BOOL __stdcall CreateLogContainerScanContext(
        HANDLE hLog,
        ULONG cFromContainer,
        ULONG cContainers,
        CLFS_SCAN_MODE eScanMode,
        PCLFS_SCAN_CONTEXT pcxScan,
        LPOVERLAPPED pOverlapped)
{
  ULONG v7; // r9d
  char v8; // al
  WCHAR *lpOutBuffer; // rsi
  CLFS_SCAN_CONTEXT *v10; // rdi
  DWORD LastError; // ebx
  BOOL v12; // r13d
  char v13; // al
  PCLS_CONTAINER_INFORMATION pinfoContainer; // rax
  ULONG v15; // eax
  DWORD nOutBufferSize; // r12d
  CLFS_SCAN_CONTEXT *v17; // rax
  DWORD BytesReturned; // [rsp+48h] [rbp-50h] BYREF
  CLFS_SCAN_CONTEXT *v20; // [rsp+50h] [rbp-48h]
  CLFS_SCAN_CONTEXT *v21; // [rsp+58h] [rbp-40h]

  v7 = cContainers;
  BytesReturned = 0;
  if ( !pcxScan
    || !cContainers
    || (v8 = eScanMode & 4, (eScanMode & 2) != 0) && v8
    || (eScanMode & 2) == 0 && !v8
    || (eScanMode & 8) != 0
    || (eScanMode & 0x10) != 0
    || (lpOutBuffer = 0, v20 = 0, v10 = 0, v21 = 0, LastError = 0, (eScanMode & 0x20) != 0) )
  {
    SetLastError(0x57u);
    return 0;
  }
  v12 = 1;
  v13 = eScanMode & 1;
  if ( (eScanMode & 1) != 0 )
  {
    if ( pcxScan->cidNode.cType != -1040322546 || pcxScan->cidNode.cbNode != 56 )
    {
      LastError = 87;
      goto LABEL_25;
    }
    pinfoContainer = pcxScan->pinfoContainer;
    if ( pinfoContainer )
    {
      lpOutBuffer = &pinfoContainer[-1].FileName[236];
      v20 = (CLFS_SCAN_CONTEXT *)&pinfoContainer[-1].FileName[236];
      v10 = (CLFS_SCAN_CONTEXT *)&pinfoContainer[-1].FileName[236];
      v21 = (CLFS_SCAN_CONTEXT *)&pinfoContainer[-1].FileName[236];
      if ( *(HANDLE *)&pinfoContainer[-1].FileName[240] == hLog )
      {
        v15 = *((_DWORD *)lpOutBuffer + 6);
        if ( v15 >= cContainers )
        {
          nOutBufferSize = 576 * v15 + 56;
          goto LABEL_22;
        }
      }
    }
    LastError = 87;
  }
  else
  {
    *(_OWORD *)&pcxScan->cidNode.cType = 0;
    *(_OWORD *)&pcxScan->cIndex = 0;
    *(_OWORD *)&pcxScan->cContainersReturned = 0;
    pcxScan->pinfoContainer = 0;
    nOutBufferSize = 576 * cContainers + 56;
    v17 = (CLFS_SCAN_CONTEXT *)operator new[](nOutBufferSize, (const struct std::nothrow_t *)&std::nothrow);
    lpOutBuffer = (WCHAR *)v17;
    v20 = v17;
    if ( v17 )
    {
      v10 = v17;
      v21 = v17;
      v17->cidNode.cType = -1040322546;
      v17->cidNode.cbNode = 56;
      v17->hLog = hLog;
      v17->pinfoContainer = (PCLS_CONTAINER_INFORMATION)&v17[1];
      v7 = cContainers;
LABEL_22:
      v10->cIndex = cFromContainer;
      v10->cContainers = v7;
      v10->cContainersReturned = 0;
      v10->eScanMode = eScanMode | 1;
      if ( !DeviceIoControl(v10->hLog, 0x80076816, 0, 0, lpOutBuffer, nOutBufferSize, &BytesReturned, pOverlapped) )
        LastError = GetLastError();
      goto LABEL_24;
    }
    LastError = 8;
  }
LABEL_24:
  v13 = eScanMode & 1;
LABEL_25:
  if ( !LastError || (v12 = 0, v13) )
  {
    if ( v10 )
    {
      if ( v10->cContainersReturned )
        v10->eScanMode |= 0x30u;
      *pcxScan = *v10;
    }
  }
  else
  {
    pcxScan->hLog = (HANDLE)-1LL;
    if ( lpOutBuffer )
      operator delete[](lpOutBuffer);
    pcxScan->eScanMode &= ~0x10u;
  }
  SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x180009d40  mov     rax, rsp
0x180009d43  mov     [rax+20h], r9b
0x180009d47  mov     [rax+18h], r8d
0x180009d4b  mov     [rax+10h], edx
0x180009d4e  mov     [rax+8], rcx
0x180009d52  push    rbx
0x180009d53  push    rsi
0x180009d54  push    rdi
0x180009d55  push    r12
0x180009d57  push    r13
0x180009d59  push    r14
0x180009d5b  push    r15
0x180009d5d  sub     rsp, 60h
0x180009d61  mov     r15b, r9b
0x180009d64  mov     r9d, r8d
0x180009d67  mov     dword ptr [rax-50h], 0
0x180009d6e  mov     r14, [rsp+98h+pcxScan]
0x180009d76  test    r14, r14
0x180009d79  jz      loc_180009FB0
0x180009d7f  test    r8d, r8d
0x180009d82  jz      loc_180009FB0
0x180009d88  mov     r8b, r15b
0x180009d8b  mov     al, r15b
0x180009d8e  and     al, 4
0x180009d90  and     r8b, 2
0x180009d94  jz      short loc_180009D9E
0x180009d96  test    al, al
0x180009d98  jnz     loc_180009FB0
0x180009d9e  test    r8b, r8b
0x180009da1  jnz     short loc_180009DAB
0x180009da3  test    al, al
0x180009da5  jz      loc_180009FB0
0x180009dab  test    r15b, 8
0x180009daf  jnz     loc_180009FB0
0x180009db5  test    r15b, 10h
0x180009db9  jnz     loc_180009FB0
0x180009dbf  xor     esi, esi
0x180009dc1  mov     [rsp+98h+var_48], rsi
0x180009dc6  xor     edi, edi
0x180009dc8  mov     [rsp+98h+var_40], rdi
0x180009dcd  xor     ebx, ebx
0x180009dcf  mov     [rsp+98h+var_54], ebx
0x180009dd3  test    r15b, 20h
0x180009dd7  jnz     loc_180009FB0
0x180009ddd  mov     al, r15b
0x180009de0  lea     r13d, [rsi+1]
0x180009de4  and     al, r13b
0x180009de7  mov     [rsp+98h+var_58], al
0x180009deb  jz      short loc_180009E52
0x180009ded  cmp     dword ptr [r14], 0C1FDF00Eh
0x180009df4  jnz     short loc_180009E44
0x180009df6  cmp     dword ptr [r14+4], 38h ; '8'
0x180009dfb  jnz     short loc_180009E44
0x180009dfd  mov     rax, [r14+30h]
0x180009e01  test    rax, rax
0x180009e04  jnz     short loc_180009E14
0x180009e06  mov     ebx, 57h ; 'W'
0x180009e0b  mov     [rsp+98h+var_54], ebx
0x180009e0f  jmp     loc_180009F38
0x180009e14  lea     rsi, [rax-38h]
0x180009e18  mov     [rsp+98h+var_48], rsi
0x180009e1d  mov     rdi, rsi
0x180009e20  mov     [rsp+98h+var_40], rsi
0x180009e25  cmp     [rsi+8], rcx
0x180009e29  jnz     short loc_180009E06
0x180009e2b  mov     eax, [rsi+18h]
0x180009e2e  cmp     eax, r9d
0x180009e31  jb      short loc_180009E06
0x180009e33  lea     r12d, [rax+rax*8]
0x180009e37  shl     r12d, 6
0x180009e3b  add     r12d, 38h ; '8'
0x180009e3f  jmp     loc_180009ECA
0x180009e44  mov     ebx, 57h ; 'W'
0x180009e49  mov     [rsp+98h+var_54], ebx
0x180009e4d  jmp     loc_180009F3C
0x180009e52  xorps   xmm0, xmm0
0x180009e55  xor     eax, eax
0x180009e57  movups  xmmword ptr [r14], xmm0
0x180009e5b  movups  xmmword ptr [r14+10h], xmm0
0x180009e60  movups  xmmword ptr [r14+20h], xmm0
0x180009e65  mov     [r14+30h], rax
0x180009e69  lea     r12d, [r9+r9*8]
0x180009e6d  shl     r12d, 6
0x180009e71  add     r12d, 38h ; '8'
0x180009e75  mov     ecx, r12d; unsigned __int64
0x180009e78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e7f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e84  mov     rsi, rax
0x180009e87  mov     [rsp+98h+var_48], rax
0x180009e8c  test    rax, rax
0x180009e8f  jnz     short loc_180009E99
0x180009e91  lea     ebx, [rax+8]
0x180009e94  jmp     loc_180009E0B
0x180009e99  mov     rdi, rsi
0x180009e9c  mov     [rsp+98h+var_40], rsi
0x180009ea1  mov     dword ptr [rax], 0C1FDF00Eh
0x180009ea7  mov     dword ptr [rax+4], 38h ; '8'
0x180009eae  mov     rax, [rsp+98h+arg_0]
0x180009eb6  mov     [rsi+8], rax
0x180009eba  lea     rax, [rsi+38h]
0x180009ebe  mov     [rsi+30h], rax
0x180009ec2  mov     r9d, [rsp+98h+arg_10]
0x180009eca  mov     eax, [rsp+98h+arg_8]
0x180009ed1  mov     [rdi+10h], eax
0x180009ed4  mov     [rdi+18h], r9d
0x180009ed8  mov     dword ptr [rdi+20h], 0
0x180009edf  or      r15b, r13b
0x180009ee2  mov     [rdi+28h], r15b
0x180009ee6  mov     rax, [rsp+98h+pOverlapped]
0x180009eee  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x180009ef3  lea     rax, [rsp+98h+BytesReturned]
0x180009ef8  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x180009efd  mov     [rsp+98h+nOutBufferSize], r12d; nOutBufferSize
0x180009f02  mov     [rsp+98h+lpOutBuffer], rsi; lpOutBuffer
0x180009f07  xor     r9d, r9d; nInBufferSize
0x180009f0a  xor     r8d, r8d; lpInBuffer
0x180009f0d  mov     edx, 80076816h; dwIoControlCode
0x180009f12  mov     rcx, [rdi+8]; hDevice
0x180009f16  call    cs:__imp_DeviceIoControl
0x180009f1d  nop     dword ptr [rax+rax+00h]
0x180009f22  test    eax, eax
0x180009f24  jnz     short loc_180009F38
0x180009f26  call    cs:__imp_GetLastError
0x180009f2d  nop     dword ptr [rax+rax+00h]
0x180009f32  mov     ebx, eax
0x180009f34  mov     [rsp+98h+var_54], eax
0x180009f38  mov     al, [rsp+98h+var_58]
0x180009f3c  test    ebx, ebx
0x180009f3e  jz      short loc_180009F6A
0x180009f40  xor     r13d, r13d
0x180009f43  test    al, al
0x180009f45  jnz     short loc_180009F6A
0x180009f47  mov     qword ptr [r14+8], 0FFFFFFFFFFFFFFFFh
0x180009f4f  test    rsi, rsi
0x180009f52  jz      short loc_180009F63
0x180009f54  mov     rcx, rsi
0x180009f57  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009f5e  nop     dword ptr [rax+rax+00h]
0x180009f63  and     byte ptr [r14+28h], 0EFh
0x180009f68  jmp     short loc_180009F9D
0x180009f6a  test    rdi, rdi
0x180009f6d  jz      short loc_180009F9D
0x180009f6f  cmp     dword ptr [rdi+20h], 0
0x180009f73  jbe     short loc_180009F79
0x180009f75  or      byte ptr [rdi+28h], 30h
0x180009f79  movups  xmm0, xmmword ptr [rdi]
0x180009f7c  movups  xmmword ptr [r14], xmm0
0x180009f80  movups  xmm1, xmmword ptr [rdi+10h]
0x180009f84  movups  xmmword ptr [r14+10h], xmm1
0x180009f89  movups  xmm0, xmmword ptr [rdi+20h]
0x180009f8d  movups  xmmword ptr [r14+20h], xmm0
0x180009f92  movsd   xmm1, qword ptr [rdi+30h]
0x180009f97  movsd   qword ptr [r14+30h], xmm1
0x180009f9d  mov     ecx, ebx; dwErrCode
0x180009f9f  call    cs:__imp_SetLastError
0x180009fa6  nop     dword ptr [rax+rax+00h]
0x180009fab  mov     eax, r13d
0x180009fae  jmp     short loc_180009FC3
0x180009fb0  mov     ecx, 57h ; 'W'; dwErrCode
0x180009fb5  call    cs:__imp_SetLastError
0x180009fbc  nop     dword ptr [rax+rax+00h]
0x180009fc1  xor     eax, eax
0x180009fc3  add     rsp, 60h
0x180009fc7  pop     r15
0x180009fc9  pop     r14
0x180009fcb  pop     r13
0x180009fcd  pop     r12
0x180009fcf  pop     rdi
0x180009fd0  pop     rsi
0x180009fd1  pop     rbx
0x180009fd2  retn
0x1800152b1  push    rbx
0x1800152b3  push    rbp
0x1800152b4  push    rdi
0x1800152b5  sub     rsp, 40h
0x1800152b9  mov     rbp, rdx
0x1800152bc  mov     edi, [rbp+44h]
0x1800152bf  test    edi, edi
0x1800152c1  jz      short loc_180015311
0x1800152c3  xor     al, al
0x1800152c5  test    byte ptr [rbp+0B8h], 1
0x1800152cc  movzx   eax, al
0x1800152cf  mov     ecx, 1
0x1800152d4  cmovnz  eax, ecx
0x1800152d7  test    al, al
0x1800152d9  jnz     short loc_180015311
0x1800152db  mov     rbx, [rbp+0C0h]
0x1800152e2  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800152ea  mov     rcx, [rbp+50h]
0x1800152ee  test    rcx, rcx
0x1800152f1  jz      short loc_180015307
0x1800152f3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800152fa  nop     dword ptr [rax+rax+00h]
0x1800152ff  mov     qword ptr [rbp+50h], 0
0x180015307  mov     al, [rbx+28h]
0x18001530a  and     al, 0EFh
0x18001530c  mov     [rbx+28h], al
0x18001530f  jmp     short loc_18001534B
0x180015311  mov     rdx, [rbp+58h]
0x180015315  test    rdx, rdx
0x180015318  jz      short loc_18001534B
0x18001531a  cmp     dword ptr [rdx+20h], 0
0x18001531e  jbe     short loc_180015324
0x180015320  or      byte ptr [rdx+28h], 30h
0x180015324  mov     rax, [rbp+0C0h]
0x18001532b  movups  xmm0, xmmword ptr [rdx]
0x18001532e  movups  xmmword ptr [rax], xmm0
0x180015331  movups  xmm1, xmmword ptr [rdx+10h]
0x180015335  movups  xmmword ptr [rax+10h], xmm1
0x180015339  movups  xmm0, xmmword ptr [rdx+20h]
0x18001533d  movups  xmmword ptr [rax+20h], xmm0
0x180015341  movsd   xmm1, qword ptr [rdx+30h]
0x180015346  movsd   qword ptr [rax+30h], xmm1
0x18001534b  mov     ecx, edi; dwErrCode
0x18001534d  call    cs:__imp_SetLastError
0x180015354  nop     dword ptr [rax+rax+00h]
0x180015359  nop
0x18001535a  add     rsp, 40h
0x18001535e  pop     rdi
0x18001535f  pop     rbp
0x180015360  pop     rbx
0x180015361  retn
```
