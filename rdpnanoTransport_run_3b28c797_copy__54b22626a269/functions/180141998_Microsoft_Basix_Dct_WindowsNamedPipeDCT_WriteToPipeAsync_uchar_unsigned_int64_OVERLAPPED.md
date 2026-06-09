# Microsoft::Basix::Dct::WindowsNamedPipeDCT::WriteToPipeAsync(uchar *,unsigned __int64,_OVERLAPPED *)

- ea: `0x180141998`
- end: `0x180141b9a`
- name: `?WriteToPipeAsync@WindowsNamedPipeDCT@Dct@Basix@Microsoft@@IEAAXPEAE_KPEAU_OVERLAPPED@@@Z`
- size: `514`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsNamedPipeDCT *__hidden this, unsigned __int8 *, unsigned __int64, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180141c40`

## callees

- `0x180024700`
- `0x180027b84`
- `0x180141998`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180141a1f`
- `KERNEL32!GetLastError` at `0x180141b35`
- `KERNEL32!GetLastError` at `0x180141a1f`
- `KERNEL32!GetLastError` at `0x180141b35`
- `KERNEL32!WriteFile` at `0x180141a15`
- `KERNEL32!WriteFile` at `0x180141a15`
- `KERNEL32!StartThreadpoolIo` at `0x1801419fa`
- `KERNEL32!StartThreadpoolIo` at `0x1801419fa`
- `KERNEL32!CancelThreadpoolIo` at `0x180141af2`
- `KERNEL32!CancelThreadpoolIo` at `0x180141af2`

## string_xrefs

- `0x180141b1c`: `Posting write to a named pipe failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Basix::Dct::WindowsNamedPipeDCT::WriteToPipeAsync(
        Microsoft::Basix::Dct::WindowsNamedPipeDCT *this,
        unsigned __int8 *a2,
        DWORD a3,
        struct _OVERLAPPED *a4)
{
  __int64 v8; // rax
  Microsoft::Basix *v9; // rcx
  const struct std::error_category *v10; // rax
  Microsoft::Basix *v11; // rcx
  const struct std::error_category *v12; // rbx
  signed int LastError; // eax
  unsigned int v14; // edx
  _QWORD v15[3]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF

  if ( !*((_QWORD *)this + 149) || (v8 = *((_QWORD *)this + 138)) == 0 || v8 == -1 )
  {
    std::string::string(v19, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp");
    std::string::string(v17, "The pipe is closed.");
    v10 = Microsoft::Basix::WindowsCategory(v9);
    *(_OWORD *)&v15[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v16, -2147418113, v10);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v15[1],
      (unsigned int)v17,
      (unsigned int)v18,
      162,
      (__int64)v19);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  ++*((_DWORD *)this + 301);
  StartThreadpoolIo(*((PTP_IO *)this + 149));
  if ( !WriteFile(*((HANDLE *)this + 138), a2, a3, 0, a4) && GetLastError() != 997 )
  {
    --*((_DWORD *)this + 301);
    CancelThreadpoolIo(*((PTP_IO *)this + 149));
    std::string::string(v17, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp");
    std::string::string(v19, "Posting write to a named pipe failed.");
    v12 = Microsoft::Basix::WindowsCategory(v11);
    LastError = GetLastError();
    v14 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v14 = LastError;
    *(_OWORD *)&v15[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v16, v14, v12);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v15[1],
      (unsigned int)v19,
      (unsigned int)v18,
      181,
      (__int64)v17);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180141998  mov     rax, rsp
0x18014199b  mov     [rax+8], rbx
0x18014199f  mov     [rax+10h], rsi
0x1801419a3  mov     [rax+18h], rdi
0x1801419a7  mov     [rax+20h], r14
0x1801419ab  push    rbp
0x1801419ac  lea     rbp, [rax-48h]
0x1801419b0  mov     eax, 140h
0x1801419b5  call    _alloca_probe
0x1801419ba  sub     rsp, rax
0x1801419bd  mov     rdi, r9
0x1801419c0  mov     rsi, r8
0x1801419c3  mov     r14, rdx
0x1801419c6  mov     rbx, rcx
0x1801419c9  cmp     qword ptr [rcx+4A8h], 0
0x1801419d1  jz      short loc_180141A4D
0x1801419d3  mov     rax, [rcx+450h]
0x1801419da  test    rax, rax
0x1801419dd  jz      short loc_180141A4D
0x1801419df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801419e3  jz      short loc_180141A4D
0x1801419e5  mov     eax, [rcx+4B4h]
0x1801419eb  inc     eax
0x1801419ed  mov     [rcx+4B4h], eax
0x1801419f3  mov     rcx, [rcx+4A8h]; pio
0x1801419fa  call    cs:__imp_StartThreadpoolIo
0x180141a00  mov     [rsp+140h+lpOverlapped], rdi; lpOverlapped
0x180141a05  xor     r9d, r9d; lpNumberOfBytesWritten
0x180141a08  mov     r8d, esi; nNumberOfBytesToWrite
0x180141a0b  mov     rdx, r14; lpBuffer
0x180141a0e  mov     rcx, [rbx+450h]; hFile
0x180141a15  call    cs:__imp_WriteFile
0x180141a1b  test    eax, eax
0x180141a1d  jnz     short loc_180141A30
0x180141a1f  call    cs:__imp_GetLastError
0x180141a25  cmp     eax, 3E5h
0x180141a2a  jnz     loc_180141ADD
0x180141a30  lea     r11, [rsp+140h+var_s0]
0x180141a38  mov     rbx, [r11+10h]
0x180141a3c  mov     rsi, [r11+18h]
0x180141a40  mov     rdi, [r11+20h]
0x180141a44  mov     r14, [r11+28h]
0x180141a48  mov     rsp, r11
0x180141a4b  pop     rbp
0x180141a4c  retn
0x180141a4d  lea     rdx, Str1
0x180141a54  lea     rcx, [rbp+40h+var_B0]
0x180141a58  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141a5d  nop
0x180141a5e  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180141a65  lea     rcx, [rsp+140h+var_D0]
0x180141a6a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141a6f  nop
0x180141a70  lea     rdx, aThePipeIsClose; "The pipe is closed."
0x180141a77  lea     rcx, [rsp+140h+var_F0]
0x180141a7c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141a81  nop
0x180141a82  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180141a87  mov     r8, rax; struct std::error_category *
0x180141a8a  mov     edx, 8000FFFFh; int
0x180141a8f  lea     rcx, [rsp+140h+var_100]; this
0x180141a94  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180141a99  movups  xmm0, xmmword ptr [rax]
0x180141a9c  movdqu  xmmword ptr [rsp+140h+var_118+8], xmm0
0x180141aa2  lea     rax, [rbp+40h+var_B0]
0x180141aa6  mov     qword ptr [rsp+140h+var_118], rax
0x180141aab  mov     [rsp+140h+lpOverlapped], 0A2h
0x180141ab4  lea     r9, [rsp+140h+var_D0]
0x180141ab9  lea     r8, [rsp+140h+var_F0]
0x180141abe  lea     rdx, [rsp+140h+var_118+8]
0x180141ac3  lea     rcx, [rbp+40h+pExceptionObject]
0x180141ac7  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180141acc  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180141ad3  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180141ad7  call    _CxxThrowException
0x180141add  mov     eax, [rbx+4B4h]
0x180141ae3  dec     eax
0x180141ae5  mov     [rbx+4B4h], eax
0x180141aeb  mov     rcx, [rbx+4A8h]; pio
0x180141af2  call    cs:__imp_CancelThreadpoolIo
0x180141af8  lea     rdx, Str1
0x180141aff  lea     rcx, [rsp+140h+var_F0]
0x180141b04  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141b09  nop
0x180141b0a  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180141b11  lea     rcx, [rsp+140h+var_D0]
0x180141b16  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141b1b  nop
0x180141b1c  lea     rdx, aPostingWriteTo; "Posting write to a named pipe failed."
0x180141b23  lea     rcx, [rbp+40h+var_B0]
0x180141b27  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180141b2c  nop
0x180141b2d  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180141b32  mov     rbx, rax
0x180141b35  call    cs:__imp_GetLastError
0x180141b3b  movzx   edx, ax
0x180141b3e  or      edx, 80070000h
0x180141b44  test    eax, eax
0x180141b46  cmovle  edx, eax; int
0x180141b49  mov     r8, rbx; struct std::error_category *
0x180141b4c  lea     rcx, [rsp+140h+var_100]; this
0x180141b51  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180141b56  movups  xmm0, xmmword ptr [rax]
0x180141b59  movdqu  xmmword ptr [rsp+140h+var_118+8], xmm0
0x180141b5f  lea     rax, [rsp+140h+var_F0]
0x180141b64  mov     qword ptr [rsp+140h+var_118], rax
0x180141b69  mov     [rsp+140h+lpOverlapped], 0B5h
0x180141b72  lea     r9, [rsp+140h+var_D0]
0x180141b77  lea     r8, [rbp+40h+var_B0]
0x180141b7b  lea     rdx, [rsp+140h+var_118+8]
0x180141b80  lea     rcx, [rbp+40h+pExceptionObject]
0x180141b84  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180141b89  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180141b90  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180141b94  call    _CxxThrowException
```
