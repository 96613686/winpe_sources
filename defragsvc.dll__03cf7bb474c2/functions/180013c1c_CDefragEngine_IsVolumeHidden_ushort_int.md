# CDefragEngine::_IsVolumeHidden(ushort *,int *)

- ea: `0x180013c1c`
- end: `0x180013f78`
- name: `?_IsVolumeHidden@CDefragEngine@@AEAAJPEAGPEAH@Z`
- size: `860`
- prototype: `__int64 __fastcall(CDefragEngine *__hidden this, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180012cc8`
- `0x18001727c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180013c1c`
- `0x1800157fc`
- `0x180017e34`
- `0x1800192b4`
- `0x180067ae6`
- `0x180067af2`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013dad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013dad`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180013e1a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180013e70`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180013e1a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180013e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f35`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_IsVolumeHidden(CDefragEngine *this, unsigned __int16 *a2, int *a3)
{
  WCHAR *v5; // rdi
  __int64 v6; // r15
  __int64 FileW; // rbx
  unsigned __int16 v8; // dx
  __int16 v9; // ax
  int v10; // r12d
  int v11; // r14d
  WCHAR *v12; // rsi
  __int64 v13; // rcx
  __int16 v14; // ax
  int v15; // esi
  bool v16; // zf
  unsigned int v17; // esi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v23; // [rsp+5Ch] [rbp-A4h]
  __int16 v24; // [rsp+5Eh] [rbp-A2h]
  void *Src; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h] BYREF
  __int16 v27; // [rsp+9Ch] [rbp-64h]
  _DWORD v28[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Buf1[112]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 OutBuffer; // [rsp+160h] [rbp+60h] BYREF

  Src = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "CDefragEngine::_IsVolumeHidden", 2811, 1);
  v5 = (WCHAR *)&qword_18006F470;
  lpFileName = &qword_18006F470;
  v21 = 0;
  v6 = -1;
  FileW = -1;
  OutBuffer = 0;
  BytesReturned = 0;
  memset_0(v28, 0, 0x90u);
  v9 = 2821;
  if ( !a2 || (v23 = 2821, v9 = 2822, !a3) )
  {
    v22 = -2147024809;
LABEL_3:
    v24 = v9;
    goto LABEL_34;
  }
  v22 = 0;
  v23 = 2822;
  *a3 = 0;
  do
    ++v6;
  while ( a2[v6] );
  v10 = 0;
  if ( (_DWORD)v6 )
  {
    v10 = CBsString::ExtendBuffer((CBsString *)&lpFileName, (int)v6 + 1);
    if ( v10 >= 0 )
    {
      v11 = v21;
      v12 = (WCHAR *)&lpFileName[(unsigned int)v21];
      memcpy_0(v12, Src, 2LL * (unsigned int)v6);
      v12[(unsigned int)v6] = 0;
      LODWORD(v21) = v6 + v11;
      v22 = v10;
      goto LABEL_10;
    }
    v5 = (WCHAR *)lpFileName;
  }
  v22 = v10;
  if ( v10 < 0 )
  {
    v9 = 2837;
    goto LABEL_3;
  }
LABEL_10:
  v23 = 2837;
  v22 = CBsString::Trailing((CBsString *)&lpFileName, v8);
  v5 = (WCHAR *)lpFileName;
  v9 = 2838;
  if ( v22 < 0 )
    goto LABEL_3;
  v23 = 2838;
  v13 = (unsigned int)(v21 - 1);
  if ( (unsigned int)v13 < (unsigned int)v21 )
    lpFileName[v13] = 0;
  FileW = (__int64)CreateFileW(v5, 0x80u, 1u, 0, 3u, 0x2000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    GetLastError();
    goto LABEL_34;
  }
  if ( DeviceIoControl((HANDLE)FileW, 0x700F0u, 0, 0, &OutBuffer, 0x10u, &BytesReturned, 0)
    && (BYTE8(OutBuffer) & 4) != 0 )
  {
    v14 = 2883;
LABEL_21:
    v22 = 0;
    *a3 = 1;
    v23 = v14;
    goto LABEL_34;
  }
  if ( DeviceIoControl((HANDLE)FileW, 0x70048u, 0, 0, v28, 0x90u, &BytesReturned, 0) )
  {
    CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CDefragEngine::_IsPartitionTypeExcluded", 2619, 1);
    v26 = 0;
    v27 = 2621;
    v15 = 0;
    if ( v28[0] )
    {
      if ( v28[0] != 1 )
        goto LABEL_31;
      if ( memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
      {
        v16 = memcmp_0(Buf1, &PARTITION_SYSTEM_GUID, 0x10u) == 0;
        goto LABEL_29;
      }
    }
    else if ( Buf1[0] != 39 )
    {
      v16 = Buf1[0] == 0xEF;
LABEL_29:
      if ( !v16 )
        goto LABEL_31;
    }
    v15 = 1;
LABEL_31:
    CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
    v22 = 0;
    v23 = 2896;
    if ( v15 )
    {
      v14 = 2901;
      goto LABEL_21;
    }
  }
  CloseHandle((HANDLE)FileW);
  FileW = -1;
LABEL_34:
  v17 = v22;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_FreeData(v5);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return v17;
}

```

## disassembly

```asm
0x180013c1c  mov     [rsp-8+arg_0], rbx
0x180013c21  push    rbp
0x180013c22  push    rsi
0x180013c23  push    rdi
0x180013c24  push    r12
0x180013c26  push    r13
0x180013c28  push    r14
0x180013c2a  push    r15
0x180013c2c  lea     rbp, [rsp-80h]
0x180013c31  sub     rsp, 180h
0x180013c38  mov     rax, cs:__security_cookie
0x180013c3f  xor     rax, rsp
0x180013c42  mov     [rbp+0B0h+var_38], rax
0x180013c46  mov     r13, r8
0x180013c49  mov     rsi, rdx
0x180013c4c  mov     [rbp+0B0h+Src], rdx
0x180013c50  mov     r9d, 1; unsigned __int16
0x180013c56  mov     r8d, 0AFBh; unsigned __int16
0x180013c5c  lea     rdx, aCdefragengineI; "CDefragEngine::_IsVolumeHidden"
0x180013c63  lea     rcx, [rsp+1B0h+var_158]; this
0x180013c68  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013c6d  nop
0x180013c6e  lea     rdi, qword_18006F470
0x180013c75  mov     [rsp+1B0h+lpFileName], rdi
0x180013c7a  xor     r14d, r14d
0x180013c7d  mov     [rsp+1B0h+var_160], r14
0x180013c82  or      r15, 0FFFFFFFFFFFFFFFFh
0x180013c86  mov     rbx, r15
0x180013c89  xorps   xmm0, xmm0
0x180013c8c  movups  [rbp+0B0h+OutBuffer], xmm0
0x180013c90  mov     [rsp+1B0h+BytesReturned], r14d
0x180013c95  xor     edx, edx; Val
0x180013c97  mov     r8d, 90h; Size
0x180013c9d  lea     rcx, [rbp+0B0h+var_E0]; void *
0x180013ca1  call    memset_0
0x180013ca6  mov     eax, 0B05h
0x180013cab  test    rsi, rsi
0x180013cae  jnz     short loc_180013CC2
0x180013cb0  mov     [rsp+1B0h+var_158], 80070057h
0x180013cb8  mov     [rsp+1B0h+var_152], ax
0x180013cbd  jmp     loc_180013F24
0x180013cc2  mov     [rsp+1B0h+var_154], ax
0x180013cc7  mov     eax, 0B06h
0x180013ccc  test    r13, r13
0x180013ccf  jz      short loc_180013CB0
0x180013cd1  mov     [rsp+1B0h+var_158], r14d
0x180013cd6  mov     [rsp+1B0h+var_154], ax
0x180013cdb  mov     [r13+0], r14d
0x180013cdf  inc     r15
0x180013ce2  cmp     [rsi+r15*2], r14w
0x180013ce7  jnz     short loc_180013CDF
0x180013ce9  mov     r12d, r14d
0x180013cec  test    r15d, r15d
0x180013cef  jz      loc_180013DD1
0x180013cf5  lea     edx, [r15+1]; unsigned int
0x180013cf9  lea     rcx, [rsp+1B0h+lpFileName]; this
0x180013cfe  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180013d03  mov     r12d, eax
0x180013d06  test    eax, eax
0x180013d08  js      loc_180013DCC
0x180013d0e  mov     r14d, dword ptr [rsp+1B0h+var_160]
0x180013d13  mov     rcx, [rsp+1B0h+lpFileName]
0x180013d18  lea     rsi, [rcx+r14*2]
0x180013d1c  mov     ecx, r15d
0x180013d1f  lea     rdi, [rcx+rcx]
0x180013d23  mov     r8, rdi; Size
0x180013d26  mov     rdx, [rbp+0B0h+Src]; Src
0x180013d2a  mov     rcx, rsi; void *
0x180013d2d  call    memcpy_0
0x180013d32  xor     ecx, ecx
0x180013d34  mov     [rdi+rsi], cx
0x180013d38  add     r14d, r15d
0x180013d3b  mov     dword ptr [rsp+1B0h+var_160], r14d
0x180013d40  mov     [rsp+1B0h+var_158], r12d
0x180013d45  xor     r14d, r14d
0x180013d48  mov     eax, 0B15h
0x180013d4d  mov     [rsp+1B0h+var_154], ax
0x180013d52  lea     rcx, [rsp+1B0h+lpFileName]; this
0x180013d57  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180013d5c  mov     [rsp+1B0h+var_158], eax
0x180013d60  mov     rdi, [rsp+1B0h+lpFileName]
0x180013d65  test    eax, eax
0x180013d67  mov     eax, 0B16h
0x180013d6c  js      loc_180013CB8
0x180013d72  mov     [rsp+1B0h+var_154], ax
0x180013d77  mov     eax, dword ptr [rsp+1B0h+var_160]
0x180013d7b  lea     ecx, [rax-1]
0x180013d7e  cmp     ecx, eax
0x180013d80  jnb     short loc_180013D87
0x180013d82  mov     [rdi+rcx*2], r14w
0x180013d87  mov     [rsp+1B0h+hTemplateFile], r14; hTemplateFile
0x180013d8c  mov     [rsp+1B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180013d94  mov     [rsp+1B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180013d9c  xor     r9d, r9d; lpSecurityAttributes
0x180013d9f  lea     r15d, [r9+1]
0x180013da3  mov     r8d, r15d; dwShareMode
0x180013da6  lea     edx, [r15+7Fh]; dwDesiredAccess
0x180013daa  mov     rcx, rdi; lpFileName
0x180013dad  call    cs:__imp_CreateFileW
0x180013db3  mov     rbx, rax
0x180013db6  inc     rax
0x180013db9  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013dbf  jnz     short loc_180013DE9
0x180013dc1  call    cs:__imp_GetLastError
0x180013dc7  jmp     loc_180013F24
0x180013dcc  mov     rdi, [rsp+1B0h+lpFileName]
0x180013dd1  mov     [rsp+1B0h+var_158], r12d
0x180013dd6  test    r12d, r12d
0x180013dd9  jns     loc_180013D48
0x180013ddf  mov     eax, 0B15h
0x180013de4  jmp     loc_180013CB8
0x180013de9  mov     [rsp+1B0h+lpOverlapped], r14; lpOverlapped
0x180013dee  lea     rax, [rsp+1B0h+BytesReturned]
0x180013df3  mov     [rsp+1B0h+hTemplateFile], rax; lpBytesReturned
0x180013df8  mov     r12d, 10h
0x180013dfe  mov     [rsp+1B0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180013e03  lea     rax, [rbp+0B0h+OutBuffer]
0x180013e07  mov     qword ptr [rsp+1B0h+dwCreationDisposition], rax; lpOutBuffer
0x180013e0c  xor     r9d, r9d; nInBufferSize
0x180013e0f  xor     r8d, r8d; lpInBuffer
0x180013e12  mov     edx, 700F0h; dwIoControlCode
0x180013e17  mov     rcx, rbx; hDevice
0x180013e1a  call    cs:__imp_DeviceIoControl
0x180013e20  test    eax, eax
0x180013e22  jz      short loc_180013E42
0x180013e24  test    byte ptr [rbp+0B0h+OutBuffer+8], 4
0x180013e28  jz      short loc_180013E42
0x180013e2a  mov     eax, 0B43h
0x180013e2f  mov     [rsp+1B0h+var_158], r14d
0x180013e34  mov     [r13+0], r15d
0x180013e38  mov     [rsp+1B0h+var_154], ax
0x180013e3d  jmp     loc_180013F24
0x180013e42  mov     [rsp+1B0h+lpOverlapped], r14; lpOverlapped
0x180013e47  lea     rax, [rsp+1B0h+BytesReturned]
0x180013e4c  mov     [rsp+1B0h+hTemplateFile], rax; lpBytesReturned
0x180013e51  mov     [rsp+1B0h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x180013e59  lea     rax, [rbp+0B0h+var_E0]
0x180013e5d  mov     qword ptr [rsp+1B0h+dwCreationDisposition], rax; lpOutBuffer
0x180013e62  xor     r9d, r9d; nInBufferSize
0x180013e65  xor     r8d, r8d; lpInBuffer
0x180013e68  mov     edx, 70048h; dwIoControlCode
0x180013e6d  mov     rcx, rbx; hDevice
0x180013e70  call    cs:__imp_DeviceIoControl
0x180013e76  test    eax, eax
0x180013e78  jz      loc_180013F17
0x180013e7e  mov     r9d, r15d; unsigned __int16
0x180013e81  mov     r8d, 0A3Bh; unsigned __int16
0x180013e87  lea     rdx, aCdefragengineI_0; "CDefragEngine::_IsPartitionTypeExcluded"
0x180013e8e  lea     rcx, [rbp+0B0h+var_118]; this
0x180013e92  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013e97  nop
0x180013e98  mov     [rbp+0B0h+var_118], r14d
0x180013e9c  mov     eax, 0A3Dh
0x180013ea1  mov     [rbp+0B0h+var_114], ax
0x180013ea5  mov     esi, r14d
0x180013ea8  mov     ecx, [rbp+0B0h+var_E0]
0x180013eab  test    ecx, ecx
0x180013ead  jz      short loc_180013EE2
0x180013eaf  cmp     ecx, 1
0x180013eb2  jnz     short loc_180013EF1
0x180013eb4  mov     r8, r12; Size
0x180013eb7  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x180013ebe  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x180013ec2  call    memcmp_0
0x180013ec7  test    eax, eax
0x180013ec9  jz      short loc_180013EEE
0x180013ecb  mov     r8, r12; Size
0x180013ece  lea     rdx, PARTITION_SYSTEM_GUID; Buf2
0x180013ed5  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x180013ed9  call    memcmp_0
0x180013ede  test    eax, eax
0x180013ee0  jmp     short loc_180013EEC
0x180013ee2  cmp     [rbp+0B0h+Buf1], 27h ; '''
0x180013ee6  jz      short loc_180013EEE
0x180013ee8  cmp     [rbp+0B0h+Buf1], 0EFh
0x180013eec  jnz     short loc_180013EF1
0x180013eee  mov     esi, r15d
0x180013ef1  lea     rcx, [rbp+0B0h+var_118]; this
0x180013ef5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013efa  mov     [rsp+1B0h+var_158], r14d
0x180013eff  mov     eax, 0B50h
0x180013f04  mov     [rsp+1B0h+var_154], ax
0x180013f09  test    esi, esi
0x180013f0b  jz      short loc_180013F17
0x180013f0d  mov     eax, 0B55h
0x180013f12  jmp     loc_180013E2F
0x180013f17  mov     rcx, rbx; hObject
0x180013f1a  call    cs:__imp_CloseHandle
0x180013f20  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013f24  mov     esi, [rsp+1B0h+var_158]
0x180013f28  lea     rdx, [rbx-1]
0x180013f2c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180013f30  ja      short loc_180013F3C
0x180013f32  mov     rcx, rbx; hObject
0x180013f35  call    cs:__imp_CloseHandle
0x180013f3b  nop
0x180013f3c  mov     rcx, rdi; unsigned __int16 *
0x180013f3f  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180013f44  nop
0x180013f45  lea     rcx, [rsp+1B0h+var_158]; this
0x180013f4a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013f4f  mov     eax, esi
0x180013f51  mov     rcx, [rbp+0B0h+var_38]
0x180013f55  xor     rcx, rsp; StackCookie
0x180013f58  call    __security_check_cookie
0x180013f5d  mov     rbx, [rsp+1B0h+arg_0]
0x180013f65  add     rsp, 180h
0x180013f6c  pop     r15
0x180013f6e  pop     r14
0x180013f70  pop     r13
0x180013f72  pop     r12
0x180013f74  pop     rdi
0x180013f75  pop     rsi
0x180013f76  pop     rbp
0x180013f77  retn
```
