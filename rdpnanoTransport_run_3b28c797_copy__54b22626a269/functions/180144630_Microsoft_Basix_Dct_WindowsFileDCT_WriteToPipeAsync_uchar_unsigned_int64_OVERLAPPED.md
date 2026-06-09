# Microsoft::Basix::Dct::WindowsFileDCT::WriteToPipeAsync(uchar *,unsigned __int64,_OVERLAPPED *)

- ea: `0x180144630`
- end: `0x180144832`
- name: `?WriteToPipeAsync@WindowsFileDCT@Dct@Basix@Microsoft@@IEAAXPEAE_KPEAU_OVERLAPPED@@@Z`
- size: `514`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsFileDCT *__hidden this, unsigned __int8 *, unsigned __int64, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801448a0`

## callees

- `0x180024700`
- `0x180027b84`
- `0x180144630`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801446b7`
- `KERNEL32!GetLastError` at `0x1801447cd`
- `KERNEL32!GetLastError` at `0x1801446b7`
- `KERNEL32!GetLastError` at `0x1801447cd`
- `KERNEL32!WriteFile` at `0x1801446ad`
- `KERNEL32!WriteFile` at `0x1801446ad`
- `KERNEL32!StartThreadpoolIo` at `0x180144692`
- `KERNEL32!StartThreadpoolIo` at `0x180144692`
- `KERNEL32!CancelThreadpoolIo` at `0x18014478a`
- `KERNEL32!CancelThreadpoolIo` at `0x18014478a`

## string_xrefs

- `0x1801447b4`: `Posting write to a named pipe failed.`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::WindowsFileDCT::WriteToPipeAsync(
        Microsoft::Basix::Dct::WindowsFileDCT *this,
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

  if ( !*((_QWORD *)this + 147) || (v8 = *((_QWORD *)this + 136)) == 0 || v8 == -1 )
  {
    std::string::string(v19, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
    std::string::string(v17, "The file is closed.");
    v10 = Microsoft::Basix::WindowsCategory(v9);
    *(_OWORD *)&v15[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v16, -2147418113, v10);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v15[1],
      (unsigned int)v17,
      (unsigned int)v18,
      224,
      (__int64)v19);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  ++*((_DWORD *)this + 297);
  StartThreadpoolIo(*((PTP_IO *)this + 147));
  if ( !WriteFile(*((HANDLE *)this + 136), a2, a3, 0, a4) && GetLastError() != 997 )
  {
    --*((_DWORD *)this + 297);
    CancelThreadpoolIo(*((PTP_IO *)this + 147));
    std::string::string(v17, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
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
      238,
      (__int64)v17);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180144630  mov     rax, rsp
0x180144633  mov     [rax+8], rbx
0x180144637  mov     [rax+10h], rsi
0x18014463b  mov     [rax+18h], rdi
0x18014463f  mov     [rax+20h], r14
0x180144643  push    rbp
0x180144644  lea     rbp, [rax-48h]
0x180144648  mov     eax, 140h
0x18014464d  call    _alloca_probe
0x180144652  sub     rsp, rax
0x180144655  mov     rdi, r9
0x180144658  mov     rsi, r8
0x18014465b  mov     r14, rdx
0x18014465e  mov     rbx, rcx
0x180144661  cmp     qword ptr [rcx+498h], 0
0x180144669  jz      short loc_1801446E5
0x18014466b  mov     rax, [rcx+440h]
0x180144672  test    rax, rax
0x180144675  jz      short loc_1801446E5
0x180144677  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014467b  jz      short loc_1801446E5
0x18014467d  mov     eax, [rcx+4A4h]
0x180144683  inc     eax
0x180144685  mov     [rcx+4A4h], eax
0x18014468b  mov     rcx, [rcx+498h]; pio
0x180144692  call    cs:__imp_StartThreadpoolIo
0x180144698  mov     [rsp+140h+lpOverlapped], rdi; lpOverlapped
0x18014469d  xor     r9d, r9d; lpNumberOfBytesWritten
0x1801446a0  mov     r8d, esi; nNumberOfBytesToWrite
0x1801446a3  mov     rdx, r14; lpBuffer
0x1801446a6  mov     rcx, [rbx+440h]; hFile
0x1801446ad  call    cs:__imp_WriteFile
0x1801446b3  test    eax, eax
0x1801446b5  jnz     short loc_1801446C8
0x1801446b7  call    cs:__imp_GetLastError
0x1801446bd  cmp     eax, 3E5h
0x1801446c2  jnz     loc_180144775
0x1801446c8  lea     r11, [rsp+140h+var_s0]
0x1801446d0  mov     rbx, [r11+10h]
0x1801446d4  mov     rsi, [r11+18h]
0x1801446d8  mov     rdi, [r11+20h]
0x1801446dc  mov     r14, [r11+28h]
0x1801446e0  mov     rsp, r11
0x1801446e3  pop     rbp
0x1801446e4  retn
0x1801446e5  lea     rdx, Str1
0x1801446ec  lea     rcx, [rbp+40h+var_B0]
0x1801446f0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801446f5  nop
0x1801446f6  lea     rdx, aCW1SSrcLibbasi_69; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1801446fd  lea     rcx, [rsp+140h+var_D0]
0x180144702  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180144707  nop
0x180144708  lea     rdx, aTheFileIsClose; "The file is closed."
0x18014470f  lea     rcx, [rsp+140h+var_F0]
0x180144714  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180144719  nop
0x18014471a  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18014471f  mov     r8, rax; struct std::error_category *
0x180144722  mov     edx, 8000FFFFh; int
0x180144727  lea     rcx, [rsp+140h+var_100]; this
0x18014472c  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180144731  movups  xmm0, xmmword ptr [rax]
0x180144734  movdqu  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18014473a  lea     rax, [rbp+40h+var_B0]
0x18014473e  mov     qword ptr [rsp+140h+var_118], rax
0x180144743  mov     [rsp+140h+lpOverlapped], 0E0h
0x18014474c  lea     r9, [rsp+140h+var_D0]
0x180144751  lea     r8, [rsp+140h+var_F0]
0x180144756  lea     rdx, [rsp+140h+var_118+8]
0x18014475b  lea     rcx, [rbp+40h+pExceptionObject]
0x18014475f  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180144764  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18014476b  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18014476f  call    _CxxThrowException
0x180144775  mov     eax, [rbx+4A4h]
0x18014477b  dec     eax
0x18014477d  mov     [rbx+4A4h], eax
0x180144783  mov     rcx, [rbx+498h]; pio
0x18014478a  call    cs:__imp_CancelThreadpoolIo
0x180144790  lea     rdx, Str1
0x180144797  lea     rcx, [rsp+140h+var_F0]
0x18014479c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801447a1  nop
0x1801447a2  lea     rdx, aCW1SSrcLibbasi_69; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1801447a9  lea     rcx, [rsp+140h+var_D0]
0x1801447ae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801447b3  nop
0x1801447b4  lea     rdx, aPostingWriteTo; "Posting write to a named pipe failed."
0x1801447bb  lea     rcx, [rbp+40h+var_B0]
0x1801447bf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801447c4  nop
0x1801447c5  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1801447ca  mov     rbx, rax
0x1801447cd  call    cs:__imp_GetLastError
0x1801447d3  movzx   edx, ax
0x1801447d6  or      edx, 80070000h
0x1801447dc  test    eax, eax
0x1801447de  cmovle  edx, eax; int
0x1801447e1  mov     r8, rbx; struct std::error_category *
0x1801447e4  lea     rcx, [rsp+140h+var_100]; this
0x1801447e9  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1801447ee  movups  xmm0, xmmword ptr [rax]
0x1801447f1  movdqu  xmmword ptr [rsp+140h+var_118+8], xmm0
0x1801447f7  lea     rax, [rsp+140h+var_F0]
0x1801447fc  mov     qword ptr [rsp+140h+var_118], rax
0x180144801  mov     [rsp+140h+lpOverlapped], 0EEh
0x18014480a  lea     r9, [rsp+140h+var_D0]
0x18014480f  lea     r8, [rbp+40h+var_B0]
0x180144813  lea     rdx, [rsp+140h+var_118+8]
0x180144818  lea     rcx, [rbp+40h+pExceptionObject]
0x18014481c  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180144821  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180144828  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18014482c  call    _CxxThrowException
```
