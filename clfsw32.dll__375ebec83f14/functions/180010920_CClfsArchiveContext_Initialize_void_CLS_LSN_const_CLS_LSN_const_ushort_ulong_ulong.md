# CClfsArchiveContext::Initialize(void *,_CLS_LSN const &,_CLS_LSN const &,ushort *,ulong,ulong &)

- ea: `0x180010920`
- end: `0x180010bd5`
- name: `?Initialize@CClfsArchiveContext@@QEAAKPEAXAEBT_CLS_LSN@@1PEAGKAEAK@Z`
- size: `693`
- prototype: `unsigned int(CClfsArchiveContext *__hidden this, void *, const union _CLS_LSN *, const union _CLS_LSN *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be70`

## callees

- `0x180010920`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ba3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010a37`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010a37`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010a9d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010a9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a06`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800109dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800109dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aec`

## pseudocode

```c
unsigned int __fastcall CClfsArchiveContext::Initialize(
        CClfsArchiveContext *this,
        char *a2,
        const union _CLS_LSN *a3,
        const union _CLS_LSN *a4,
        unsigned __int16 *lpOutBuffer,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int64 EventA; // rax
  HANDLE CurrentProcess; // rax
  void *v13; // rcx
  DWORD v14; // edx
  BOOL v15; // eax
  DWORD v16; // ecx
  unsigned int result; // eax
  DWORD v18; // r8d
  __int64 v19; // rax
  unsigned __int16 *v20; // r9
  __int64 v21; // rcx
  const wchar_t *v22; // r10
  __int64 v23; // r9
  unsigned __int16 *v24; // rax
  __int64 i; // rdx
  unsigned __int16 *v26; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-68h] BYREF
  ULONGLONG InBuffer; // [rsp+48h] [rbp-60h] BYREF
  ULONGLONG ullOffset; // [rsp+50h] [rbp-58h]

  InBuffer = CLFS_LSN_NULL.ullOffset;
  ullOffset = CLFS_LSN_NULL.ullOffset;
  BytesReturned = 0;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || a3 && CLFS_LSN_INVALID.ullOffset == a3->ullOffset
    || a4 && CLFS_LSN_INVALID.ullOffset == a4->ullOffset
    || a3 && a4 && a3->ullOffset > a4->ullOffset )
  {
    return 87;
  }
  *a7 = 0;
  EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
  *((_QWORD *)this + 11) = EventA;
  if ( EventA - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return GetLastError();
  *((_QWORD *)this + 11) = EventA | 1;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, a2, CurrentProcess, (LPHANDLE)this + 1, 0, 1, 2u) )
    return GetLastError();
  v13 = (void *)*((_QWORD *)this + 1);
  InBuffer = a3->ullOffset;
  v14 = 2 * a6 - 10;
  if ( a6 <= 5 )
    v14 = 0;
  ullOffset = a4->ullOffset;
  v15 = DeviceIoControl(v13, 0x8007283E, &InBuffer, 0x10u, lpOutBuffer, v14, &BytesReturned, (LPOVERLAPPED)this + 2);
  v16 = (BytesReturned >> 1) + 5;
  *a7 = v16;
  if ( v15 )
  {
    v18 = 0;
  }
  else
  {
    result = GetLastError();
    if ( result != 997 )
    {
      if ( result == 234 && a6 < *a7 )
        return 111;
      return result;
    }
    v18 = WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
    if ( v18 )
      return 1359;
    v16 = *a7;
    if ( a6 < *a7 )
      v18 = 111;
  }
  lpOutBuffer[v16 - 5] = 0;
  if ( (unsigned __int64)a6 - 1 <= 0x7FFFFFFE )
  {
    v19 = a6;
    v20 = lpOutBuffer;
    while ( *v20 )
    {
      ++v20;
      if ( !--v19 )
      {
        v21 = 0;
        goto LABEL_30;
      }
    }
    v21 = a6 - v19;
LABEL_30:
    if ( v19 )
    {
      v22 = L".blf";
      v23 = 4;
      v24 = &lpOutBuffer[v21];
      for ( i = a6 - v21; i; --i )
      {
        if ( !v23 )
          break;
        if ( !*v22 )
          break;
        *v24++ = *v22++;
        --v23;
      }
      v26 = v24 - 1;
      if ( i )
        v26 = v24;
      *v26 = 0;
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180010920  push    rbx
0x180010922  push    rbp
0x180010923  push    rsi
0x180010924  push    rdi
0x180010925  push    r12
0x180010927  push    r13
0x180010929  push    r14
0x18001092b  push    r15
0x18001092d  sub     rsp, 68h
0x180010931  mov     rax, cs:__security_cookie
0x180010938  xor     rax, rsp
0x18001093b  mov     [rsp+0A8h+var_50], rax
0x180010940  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180010947  mov     rdi, r9
0x18001094a  mov     r14, [rsp+0A8h+lpOutBuffer]
0x180010952  mov     rbx, r8
0x180010955  mov     rsi, [rsp+0A8h+arg_30]
0x18001095d  mov     r13, rdx
0x180010960  mov     [rsp+0A8h+InBuffer], rax
0x180010965  mov     rbp, rcx
0x180010968  mov     [rsp+0A8h+var_58], rax
0x18001096d  lea     rax, [rdx-1]
0x180010971  mov     [rsp+0A8h+BytesReturned], 0
0x180010979  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001097d  ja      loc_180010BB1
0x180010983  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001098a  test    rbx, rbx
0x18001098d  jz      short loc_180010998
0x18001098f  cmp     rax, [r8]
0x180010992  jz      loc_180010BB1
0x180010998  test    rdi, rdi
0x18001099b  jz      short loc_1800109A6
0x18001099d  cmp     rax, [r9]
0x1800109a0  jz      loc_180010BB1
0x1800109a6  test    rbx, rbx
0x1800109a9  jz      short loc_1800109CC
0x1800109ab  test    rdi, rdi
0x1800109ae  jz      short loc_1800109CC
0x1800109b0  mov     eax, [r8+4]
0x1800109b4  cmp     eax, [r9+4]
0x1800109b8  jb      short loc_1800109CC
0x1800109ba  jnz     loc_180010BB1
0x1800109c0  mov     eax, [r9]
0x1800109c3  cmp     [r8], eax
0x1800109c6  ja      loc_180010BB1
0x1800109cc  xor     r9d, r9d; lpName
0x1800109cf  mov     dword ptr [rsi], 0
0x1800109d5  xor     r8d, r8d; bInitialState
0x1800109d8  xor     edx, edx; bManualReset
0x1800109da  xor     ecx, ecx; lpEventAttributes
0x1800109dc  call    cs:__imp_CreateEventA
0x1800109e3  nop     dword ptr [rax+rax+00h]
0x1800109e8  lea     r15, [rbp+40h]
0x1800109ec  mov     [r15+18h], rax
0x1800109f0  lea     rcx, [rax-1]
0x1800109f4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800109f8  ja      loc_180010BA3
0x1800109fe  or      rax, 1
0x180010a02  mov     [rbp+58h], rax
0x180010a06  call    cs:__imp_GetCurrentProcess
0x180010a0d  nop     dword ptr [rax+rax+00h]
0x180010a12  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x180010a1a  lea     r9, [rbp+8]; lpTargetHandle
0x180010a1e  mov     r8, rax; hTargetProcessHandle
0x180010a21  mov     [rsp+0A8h+bInheritHandle], 1; bInheritHandle
0x180010a29  mov     rcx, rax; hSourceProcessHandle
0x180010a2c  mov     [rsp+0A8h+dwDesiredAccess], 0; dwDesiredAccess
0x180010a34  mov     rdx, r13; hSourceHandle
0x180010a37  call    cs:__imp_DuplicateHandle
0x180010a3e  nop     dword ptr [rax+rax+00h]
0x180010a43  xor     r13d, r13d
0x180010a46  test    eax, eax
0x180010a48  jz      loc_180010BA3
0x180010a4e  mov     rax, [rbx]
0x180010a51  lea     r9d, [r13+10h]; nInBufferSize
0x180010a55  mov     ebx, [rsp+0A8h+arg_28]
0x180010a5c  lea     r8, [rsp+0A8h+InBuffer]; lpInBuffer
0x180010a61  mov     rcx, [rbp+8]; hDevice
0x180010a65  cmp     ebx, 5
0x180010a68  mov     [rsp+0A8h+InBuffer], rax
0x180010a6d  mov     rax, [rdi]
0x180010a70  mov     [rsp+0A8h+lpOverlapped], r15; lpOverlapped
0x180010a75  lea     edx, ds:0FFFFFFFFFFFFFFF6h[rbx*2]
0x180010a7c  cmovbe  edx, r13d
0x180010a80  mov     [rsp+0A8h+var_58], rax
0x180010a85  lea     rax, [rsp+0A8h+BytesReturned]
0x180010a8a  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpBytesReturned
0x180010a8f  mov     [rsp+0A8h+bInheritHandle], edx; nOutBufferSize
0x180010a93  mov     edx, 8007283Eh; dwIoControlCode
0x180010a98  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r14; lpOutBuffer
0x180010a9d  call    cs:__imp_DeviceIoControl
0x180010aa4  nop     dword ptr [rax+rax+00h]
0x180010aa9  mov     ecx, [rsp+0A8h+BytesReturned]
0x180010aad  shr     ecx, 1
0x180010aaf  add     ecx, 5
0x180010ab2  mov     [rsi], ecx
0x180010ab4  test    eax, eax
0x180010ab6  jnz     short loc_180010B17
0x180010ab8  call    cs:__imp_GetLastError
0x180010abf  nop     dword ptr [rax+rax+00h]
0x180010ac4  cmp     eax, 3E5h
0x180010ac9  jz      short loc_180010AE5
0x180010acb  cmp     eax, 0EAh
0x180010ad0  jnz     loc_180010BB6
0x180010ad6  cmp     ebx, [rsi]
0x180010ad8  lea     r8d, [r13+6Fh]
0x180010adc  cmovb   eax, r8d
0x180010ae0  jmp     loc_180010BB6
0x180010ae5  mov     rcx, [rbp+58h]; hHandle
0x180010ae9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010aec  call    cs:__imp_WaitForSingleObject
0x180010af3  nop     dword ptr [rax+rax+00h]
0x180010af8  mov     r8d, eax
0x180010afb  test    eax, eax
0x180010afd  jz      short loc_180010B09
0x180010aff  mov     eax, 54Fh
0x180010b04  jmp     loc_180010BB6
0x180010b09  mov     ecx, [rsi]
0x180010b0b  cmp     ebx, ecx
0x180010b0d  jnb     short loc_180010B1A
0x180010b0f  mov     r8d, 6Fh ; 'o'
0x180010b15  jmp     short loc_180010B1A
0x180010b17  mov     r8d, r13d
0x180010b1a  lea     eax, [rcx-5]
0x180010b1d  mov     rdx, rbx
0x180010b20  mov     [r14+rax*2], r13w
0x180010b25  lea     rax, [rbx-1]
0x180010b29  cmp     rax, 7FFFFFFEh
0x180010b2f  ja      short loc_180010B9E
0x180010b31  mov     rax, rbx
0x180010b34  mov     r9, r14
0x180010b37  mov     rcx, rbx
0x180010b3a  cmp     [r9], r13w
0x180010b3e  jz      short loc_180010B4F
0x180010b40  add     r9, 2
0x180010b44  sub     rax, 1
0x180010b48  jnz     short loc_180010B3A
0x180010b4a  mov     rcx, r13
0x180010b4d  jmp     short loc_180010B52
0x180010b4f  sub     rcx, rax
0x180010b52  test    rax, rax
0x180010b55  jz      short loc_180010B9E
0x180010b57  lea     r10, aBlf_1; ".blf"
0x180010b5e  mov     r9d, 4
0x180010b64  lea     rax, [r14+rcx*2]
0x180010b68  sub     rdx, rcx
0x180010b6b  jz      short loc_180010B8F
0x180010b6d  test    r9, r9
0x180010b70  jz      short loc_180010B8F
0x180010b72  movzx   ecx, word ptr [r10]
0x180010b76  test    cx, cx
0x180010b79  jz      short loc_180010B8F
0x180010b7b  mov     [rax], cx
0x180010b7e  add     r10, 2
0x180010b82  add     rax, 2
0x180010b86  dec     r9
0x180010b89  sub     rdx, 1
0x180010b8d  jnz     short loc_180010B6D
0x180010b8f  test    rdx, rdx
0x180010b92  lea     rcx, [rax-2]
0x180010b96  cmovnz  rcx, rax
0x180010b9a  mov     [rcx], r13w
0x180010b9e  mov     eax, r8d
0x180010ba1  jmp     short loc_180010BB6
0x180010ba3  call    cs:__imp_GetLastError
0x180010baa  nop     dword ptr [rax+rax+00h]
0x180010baf  jmp     short loc_180010BB6
0x180010bb1  mov     eax, 57h ; 'W'
0x180010bb6  mov     rcx, [rsp+0A8h+var_50]
0x180010bbb  xor     rcx, rsp; StackCookie
0x180010bbe  call    __security_check_cookie
0x180010bc3  add     rsp, 68h
0x180010bc7  pop     r15
0x180010bc9  pop     r14
0x180010bcb  pop     r13
0x180010bcd  pop     r12
0x180010bcf  pop     rdi
0x180010bd0  pop     rsi
0x180010bd1  pop     rbp
0x180010bd2  pop     rbx
0x180010bd3  retn
```
