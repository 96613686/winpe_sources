# SSI_FILE::SSIReadFile(void)

- ea: `0x180002a38`
- end: `0x180002b73`
- name: `?SSIReadFile@SSI_FILE@@AEAAJXZ`
- size: `315`
- prototype: `signed int __fastcall(SSI_FILE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002978`

## callees

- `0x180002a38`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b3f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002aef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002aef`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002b35`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002b35`

## pseudocode

```c
signed int __fastcall SSI_FILE::SSIReadFile(SSI_FILE *this)
{
  __int64 v2; // rcx
  signed int result; // eax
  HLOCAL v4; // rax
  void *v5; // rbx
  void *v6; // rax
  void *v7; // rax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+10h] BYREF
  SIZE_T uBytes; // [rsp+68h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  uBytes = 0;
  v2 = *((_QWORD *)this + 2);
  memset(&Overlapped, 0, sizeof(Overlapped));
  (*(void (__fastcall **)(__int64, SIZE_T *))(*(_QWORD *)v2 + 64LL))(v2, &uBytes);
  if ( HIDWORD(uBytes) )
    return -2147024809;
  if ( !(_DWORD)uBytes )
    return 0;
  v4 = LocalAlloc(0, (unsigned int)uBytes);
  *((_QWORD *)this + 3) = v4;
  v5 = v4;
  if ( !v4 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 80LL))(*((_QWORD *)this + 2));
  if ( ReadFile(v6, v5, uBytes, &NumberOfBytesRead, &Overlapped) )
    return (_DWORD)uBytes != NumberOfBytesRead ? 0x8007000D : 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023899 )
  {
    v7 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 80LL))(*((_QWORD *)this + 2));
    if ( !GetOverlappedResult(v7, &Overlapped, &NumberOfBytesRead, 1) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    return (_DWORD)uBytes != NumberOfBytesRead ? 0x8007000D : 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002a38  mov     [rsp-8+arg_10], rbx
0x180002a3d  mov     [rsp-8+arg_18], rdi
0x180002a42  push    rbp
0x180002a43  mov     rbp, rsp
0x180002a46  sub     rsp, 50h
0x180002a4a  xorps   xmm0, xmm0
0x180002a4d  mov     [rbp+NumberOfBytesRead], 0
0x180002a54  mov     rdi, rcx
0x180002a57  mov     [rbp+uBytes], 0
0x180002a5f  mov     rcx, [rcx+10h]
0x180002a63  lea     rdx, [rbp+uBytes]
0x180002a67  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180002a6b  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180002a6f  mov     rax, [rcx]
0x180002a72  mov     rax, [rax+40h]
0x180002a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a7b  cmp     dword ptr [rbp+uBytes+4], 0
0x180002a7f  jz      short loc_180002A8B
0x180002a81  mov     eax, 80070057h
0x180002a86  jmp     loc_180002B63
0x180002a8b  mov     rax, [rbp+uBytes]
0x180002a8f  test    eax, eax
0x180002a91  jz      loc_180002B61
0x180002a97  mov     edx, eax; uBytes
0x180002a99  xor     ecx, ecx; uFlags
0x180002a9b  call    cs:__imp_LocalAlloc
0x180002aa1  mov     [rdi+18h], rax
0x180002aa5  mov     rbx, rax
0x180002aa8  test    rax, rax
0x180002aab  jnz     short loc_180002AC8
0x180002aad  call    cs:__imp_GetLastError
0x180002ab3  test    eax, eax
0x180002ab5  jle     loc_180002B63
0x180002abb  movzx   eax, ax
0x180002abe  or      eax, 80070000h
0x180002ac3  jmp     loc_180002B63
0x180002ac8  mov     rcx, [rdi+10h]
0x180002acc  mov     rax, [rcx]
0x180002acf  mov     rax, [rax+50h]
0x180002ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad8  mov     r8d, dword ptr [rbp+uBytes]; nNumberOfBytesToRead
0x180002adc  lea     rcx, [rbp+Overlapped]
0x180002ae0  mov     [rsp+50h+lpOverlapped], rcx; lpOverlapped
0x180002ae5  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002ae9  mov     rcx, rax; hFile
0x180002aec  mov     rdx, rbx; lpBuffer
0x180002aef  call    cs:__imp_ReadFile
0x180002af5  test    eax, eax
0x180002af7  jnz     short loc_180002B50
0x180002af9  call    cs:__imp_GetLastError
0x180002aff  mov     ebx, 80070000h
0x180002b04  test    eax, eax
0x180002b06  jle     short loc_180002B0D
0x180002b08  movzx   eax, ax
0x180002b0b  or      eax, ebx
0x180002b0d  cmp     eax, 800703E5h
0x180002b12  jnz     short loc_180002B63
0x180002b14  mov     rcx, [rdi+10h]
0x180002b18  mov     rax, [rcx]
0x180002b1b  mov     rax, [rax+50h]
0x180002b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b24  mov     rcx, rax; hFile
0x180002b27  lea     r8, [rbp+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180002b2b  mov     r9d, 1; bWait
0x180002b31  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180002b35  call    cs:__imp_GetOverlappedResult
0x180002b3b  test    eax, eax
0x180002b3d  jnz     short loc_180002B50
0x180002b3f  call    cs:__imp_GetLastError
0x180002b45  test    eax, eax
0x180002b47  jle     short loc_180002B63
0x180002b49  movzx   eax, ax
0x180002b4c  or      eax, ebx
0x180002b4e  jmp     short loc_180002B63
0x180002b50  mov     eax, [rbp+NumberOfBytesRead]
0x180002b53  sub     eax, dword ptr [rbp+uBytes]
0x180002b56  neg     eax
0x180002b58  sbb     eax, eax
0x180002b5a  and     eax, 8007000Dh
0x180002b5f  jmp     short loc_180002B63
0x180002b61  xor     eax, eax
0x180002b63  mov     rbx, [rsp+50h+arg_10]
0x180002b68  mov     rdi, [rsp+50h+arg_18]
0x180002b6d  add     rsp, 50h
0x180002b71  pop     rbp
0x180002b72  retn
```
