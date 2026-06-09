# CUploadJob::GetReplyData(uchar * *,unsigned __int64 *)

- ea: `0x18008b230`
- end: `0x18008b6a6`
- name: `?GetReplyData@CUploadJob@@UEBAJPEAPEAEPEA_K@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CUploadJob *this, unsigned __int8 **, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008b70`
- `0x18000dcb0`
- `0x180019040`
- `0x18006b0c0`
- `0x18008b230`
- `0x18008c444`
- `0x18009befc`
- `0x18009d2b0`
- `0x1800a3420`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b510`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008b43c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008b43c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008b590`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008b590`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CUploadJob::GetReplyData(CUploadJob *this, unsigned __int8 **a2, union _LARGE_INTEGER *a3)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int LastError; // ecx
  unsigned int v10; // ecx
  DWORD LowPart; // ebx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // r14
  unsigned int v14; // ecx
  void *v15; // [rsp+30h] [rbp-3A8h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-398h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-390h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-388h] BYREF
  unsigned __int8 *v19; // [rsp+58h] [rbp-380h]
  void **v20[8]; // [rsp+60h] [rbp-378h] BYREF
  void **pExceptionObject; // [rsp+A0h] [rbp-338h] BYREF
  __int128 v22; // [rsp+A8h] [rbp-330h]
  int v23; // [rsp+B8h] [rbp-320h]
  int v24; // [rsp+BCh] [rbp-31Ch]
  int v25; // [rsp+C0h] [rbp-318h]
  void **v26; // [rsp+100h] [rbp-2D8h] BYREF
  __int128 v27; // [rsp+108h] [rbp-2D0h]
  unsigned int v28; // [rsp+118h] [rbp-2C0h]
  int v29; // [rsp+11Ch] [rbp-2BCh]
  int v30; // [rsp+120h] [rbp-2B8h]
  void **v31; // [rsp+160h] [rbp-278h] BYREF
  __int128 v32; // [rsp+168h] [rbp-270h]
  unsigned int v33; // [rsp+178h] [rbp-260h]
  int v34; // [rsp+17Ch] [rbp-25Ch]
  int v35; // [rsp+180h] [rbp-258h]
  void **v36; // [rsp+1C0h] [rbp-218h] BYREF
  __int128 v37; // [rsp+1C8h] [rbp-210h]
  int v38; // [rsp+1D8h] [rbp-200h]
  int v39; // [rsp+1DCh] [rbp-1FCh]
  int v40; // [rsp+1E0h] [rbp-1F8h]
  void **v41; // [rsp+220h] [rbp-1B8h] BYREF
  __int128 v42; // [rsp+228h] [rbp-1B0h]
  int v43; // [rsp+238h] [rbp-1A0h]
  int v44; // [rsp+23Ch] [rbp-19Ch]
  int v45; // [rsp+240h] [rbp-198h]
  void **v46; // [rsp+280h] [rbp-158h] BYREF
  __int128 v47; // [rsp+288h] [rbp-150h]
  unsigned int v48; // [rsp+298h] [rbp-140h]
  int v49; // [rsp+29Ch] [rbp-13Ch]
  int v50; // [rsp+2A0h] [rbp-138h]
  void **v51; // [rsp+2E0h] [rbp-F8h] BYREF
  __int128 v52; // [rsp+2E8h] [rbp-F0h]
  int v53; // [rsp+2F8h] [rbp-E0h]
  int v54; // [rsp+2FCh] [rbp-DCh]
  int v55; // [rsp+300h] [rbp-D8h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  a3->QuadPart = 0;
  *a2 = 0;
  if ( *((_DWORD *)this + 166) != 2 )
    return 2147500033LL;
  if ( (unsigned int)(*((_DWORD *)this + 165) - 6) > 1 )
    return 2149580802LL;
  v19 = 0;
  CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v20);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 191) + 8LL), 1u);
  hFile = (HANDLE)*((_QWORD *)this + 191);
  CNestedImpersonation::SwitchToLogonToken((__int64)v20, &hFile);
  if ( (*((_BYTE *)this + 1232) & 1) != 0 )
  {
    if ( !**((_QWORD **)this + 155) )
    {
      v22 = 0;
      pExceptionObject = &ComError::`vftable';
      v23 = -2145386410;
      v24 = 10252;
      v25 = 1;
      throw (ComError *)&pExceptionObject;
    }
    CNestedImpersonation::Impersonate((CNestedImpersonation *)v20, (CUploadJob *)((char *)this + 1240));
  }
  hFile = (HANDLE)-1LL;
  v7 = 16;
  if ( *((_DWORD *)this + 165) != 7 )
    v7 = 24;
  v8 = BITSCreateFile2(
         (const unsigned __int16 *)(*(_QWORD *)(v7 + *((_QWORD *)this + 203)) + 12LL),
         0x80000000,
         0,
         0,
         3u,
         0,
         v15);
  auto_HANDLE<-1>::operator=(&hFile, v8);
  if ( hFile == (HANDLE)-1LL )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v27 = 0;
    v26 = &ComError::`vftable';
    v28 = LastError;
    v29 = 10276;
    v30 = 1;
    throw (ComError *)&v26;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    if ( (int)GetLastError() > 0 )
      v10 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v10 = GetLastError();
    v32 = 0;
    v31 = &ComError::`vftable';
    v33 = v10;
    v34 = 10285;
    v35 = 1;
    throw (ComError *)&v31;
  }
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0x100000 )
  {
    *a3 = FileSize;
    v37 = 0;
    v36 = &ComError::`vftable';
    v38 = -2145386464;
    v39 = 10291;
    v40 = 1;
    throw (ComError *)&v36;
  }
  v12 = (unsigned __int8 *)CoTaskMemAlloc(FileSize.LowPart);
  v13 = v12;
  v19 = v12;
  if ( !v12 )
  {
    v42 = 0;
    v41 = &ComError::`vftable';
    v43 = -2147024882;
    v44 = 10301;
    v45 = 1;
    throw (ComError *)&v41;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, v12, LowPart, &NumberOfBytesRead, 0) )
  {
    if ( (int)GetLastError() > 0 )
      v14 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v14 = GetLastError();
    v47 = 0;
    v46 = &ComError::`vftable';
    v48 = v14;
    v49 = 10315;
    v50 = 1;
    throw (ComError *)&v46;
  }
  if ( NumberOfBytesRead != LowPart )
  {
    v52 = 0;
    v51 = &ComError::`vftable';
    v53 = -2147467259;
    v54 = 0;
    v55 = 1;
    throw (ComError *)&v51;
  }
  a3->QuadPart = NumberOfBytesRead;
  *a2 = v13;
  auto_HANDLE<-1>::~auto_HANDLE<-1>(&hFile);
  CNestedImpersonation::~CNestedImpersonation(v20);
  return 0;
}

```

## disassembly

```asm
0x18008b230  push    rbx
0x18008b232  push    rsi
0x18008b233  push    r13
0x18008b235  push    r14
0x18008b237  push    r15
0x18008b239  sub     rsp, 3B0h
0x18008b240  mov     rax, cs:__security_cookie
0x18008b247  xor     rax, rsp
0x18008b24a  mov     [rsp+3D8h+var_38], rax
0x18008b252  mov     rsi, r8
0x18008b255  mov     r15, rdx
0x18008b258  mov     rbx, rcx
0x18008b25b  test    rdx, rdx
0x18008b25e  jz      loc_18008B680
0x18008b264  test    r8, r8
0x18008b267  jz      loc_18008B680
0x18008b26d  mov     qword ptr [r8], 0
0x18008b274  mov     qword ptr [rdx], 0
0x18008b27b  cmp     dword ptr [rcx+298h], 2
0x18008b282  jz      short loc_18008B28E
0x18008b284  mov     eax, 80004001h
0x18008b289  jmp     loc_18008B685
0x18008b28e  mov     eax, [rcx+294h]
0x18008b294  sub     eax, 6
0x18008b297  mov     r13d, 1
0x18008b29d  cmp     eax, r13d
0x18008b2a0  jbe     short loc_18008B2AC
0x18008b2a2  mov     eax, 80200002h
0x18008b2a7  jmp     loc_18008B685
0x18008b2ac  mov     [rsp+3D8h+var_380], 0
0x18008b2b5  lea     rcx, [rsp+3D8h+var_378]; this
0x18008b2ba  call    ??0CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::CNestedImpersonation(void)
0x18008b2bf  nop
0x18008b2c0  mov     rax, [rbx+5F8h]
0x18008b2c7  lock add [rax+8], r13d
0x18008b2cc  mov     rax, [rbx+5F8h]
0x18008b2d3  mov     [rsp+3D8h+hFile], rax
0x18008b2d8  lea     rdx, [rsp+3D8h+hFile]
0x18008b2dd  lea     rcx, [rsp+3D8h+var_378]
0x18008b2e2  call    ?SwitchToLogonToken@CNestedImpersonation@@QEAAXV?$GenericStringHandle@G@@@Z; CNestedImpersonation::SwitchToLogonToken(GenericStringHandle<ushort>)
0x18008b2e7  test    [rbx+4D0h], r13b
0x18008b2ee  jz      short loc_18008B30E
0x18008b2f0  lea     rdx, [rbx+4D8h]; struct TokenHandle *
0x18008b2f7  mov     rax, [rdx]
0x18008b2fa  cmp     qword ptr [rax], 0
0x18008b2fe  jz      loc_18008B385
0x18008b304  lea     rcx, [rsp+3D8h+var_378]; this
0x18008b309  call    ?Impersonate@CNestedImpersonation@@QEAAXAEBVTokenHandle@@@Z; CNestedImpersonation::Impersonate(TokenHandle const &)
0x18008b30e  mov     [rsp+3D8h+hFile], 0FFFFFFFFFFFFFFFFh
0x18008b317  mov     ecx, 10h
0x18008b31c  lea     eax, [rcx+8]
0x18008b31f  cmp     dword ptr [rbx+294h], 7
0x18008b326  cmovnz  ecx, eax
0x18008b329  mov     rax, [rbx+658h]
0x18008b330  mov     rcx, [rcx+rax]
0x18008b334  add     rcx, 0Ch; unsigned __int16 *
0x18008b338  mov     [rsp+3D8h+var_3B0], 0; unsigned int
0x18008b340  mov     dword ptr [rsp+3D8h+lpOverlapped], 3; unsigned int
0x18008b348  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x18008b34b  xor     r8d, r8d; unsigned int
0x18008b34e  mov     edx, 80000000h; unsigned int
0x18008b353  call    ?BITSCreateFile2@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; BITSCreateFile2(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18008b358  mov     rdx, rax
0x18008b35b  lea     rcx, [rsp+3D8h+hFile]
0x18008b360  call    ??4?$auto_HANDLE@$0?0@@QEAAAEAV0@PEAX@Z; auto_HANDLE<-1>::operator=(void *)
0x18008b365  cmp     [rsp+3D8h+hFile], 0FFFFFFFFFFFFFFFFh
0x18008b36b  jnz     loc_18008B429
0x18008b371  call    cs:__imp_GetLastError
0x18008b377  test    eax, eax
0x18008b379  jg      short loc_18008B3D2
0x18008b37b  call    cs:__imp_GetLastError
0x18008b381  mov     ecx, eax
0x18008b383  jmp     short loc_18008B3E1
0x18008b385  xorps   xmm0, xmm0
0x18008b388  movups  [rsp+3D8h+var_330], xmm0
0x18008b390  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b397  mov     [rsp+3D8h+pExceptionObject], rax
0x18008b39f  mov     [rsp+3D8h+var_320], 80200056h
0x18008b3aa  mov     [rsp+3D8h+var_31C], 280Ch
0x18008b3b5  mov     [rsp+3D8h+var_318], r13d
0x18008b3bd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b3c4  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x18008b3cc  call    _CxxThrowException_0
0x18008b3d2  call    cs:__imp_GetLastError
0x18008b3d8  movzx   ecx, ax
0x18008b3db  or      ecx, 80070000h
0x18008b3e1  xorps   xmm0, xmm0
0x18008b3e4  movups  [rsp+3D8h+var_2D0], xmm0
0x18008b3ec  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b3f3  mov     [rsp+3D8h+var_2D8], rax
0x18008b3fb  mov     [rsp+3D8h+var_2C0], ecx
0x18008b402  mov     [rsp+3D8h+var_2BC], 2824h
0x18008b40d  mov     [rsp+3D8h+var_2B8], r13d
0x18008b415  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b41c  lea     rcx, [rsp+3D8h+var_2D8]; pExceptionObject
0x18008b424  call    _CxxThrowException_0
0x18008b429  mov     qword ptr [rsp+3D8h+FileSize], 0
0x18008b432  lea     rdx, [rsp+3D8h+FileSize]; lpFileSize
0x18008b437  mov     rcx, [rsp+3D8h+hFile]; hFile
0x18008b43c  call    cs:__imp_GetFileSizeEx
0x18008b442  test    eax, eax
0x18008b444  jnz     short loc_18008B4B1
0x18008b446  call    cs:__imp_GetLastError
0x18008b44c  test    eax, eax
0x18008b44e  jg      short loc_18008B45A
0x18008b450  call    cs:__imp_GetLastError
0x18008b456  mov     ecx, eax
0x18008b458  jmp     short loc_18008B469
0x18008b45a  call    cs:__imp_GetLastError
0x18008b460  movzx   ecx, ax
0x18008b463  or      ecx, 80070000h
0x18008b469  xorps   xmm0, xmm0
0x18008b46c  movups  [rsp+3D8h+var_270], xmm0
0x18008b474  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b47b  mov     [rsp+3D8h+var_278], rax
0x18008b483  mov     [rsp+3D8h+var_260], ecx
0x18008b48a  mov     [rsp+3D8h+var_25C], 282Dh
0x18008b495  mov     [rsp+3D8h+var_258], r13d
0x18008b49d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b4a4  lea     rcx, [rsp+3D8h+var_278]; pExceptionObject
0x18008b4ac  call    _CxxThrowException_0
0x18008b4b1  mov     rbx, qword ptr [rsp+3D8h+FileSize]
0x18008b4b6  cmp     rbx, 100000h
0x18008b4bd  jle     short loc_18008B50E
0x18008b4bf  mov     [rsi], rbx
0x18008b4c2  xorps   xmm0, xmm0
0x18008b4c5  movups  [rsp+3D8h+var_210], xmm0
0x18008b4cd  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b4d4  mov     [rsp+3D8h+var_218], rax
0x18008b4dc  mov     [rsp+3D8h+var_200], 80200020h
0x18008b4e7  mov     [rsp+3D8h+var_1FC], 2833h
0x18008b4f2  mov     [rsp+3D8h+var_1F8], r13d
0x18008b4fa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b501  lea     rcx, [rsp+3D8h+var_218]; pExceptionObject
0x18008b509  call    _CxxThrowException_0
0x18008b50e  mov     ecx, ebx; cb
0x18008b510  call    cs:__imp_CoTaskMemAlloc
0x18008b516  mov     r14, rax
0x18008b519  mov     [rsp+3D8h+var_380], rax
0x18008b51e  test    rax, rax
0x18008b521  jnz     short loc_18008B56F
0x18008b523  xorps   xmm0, xmm0
0x18008b526  movups  [rsp+3D8h+var_1B0], xmm0
0x18008b52e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b535  mov     [rsp+3D8h+var_1B8], rax
0x18008b53d  mov     [rsp+3D8h+var_1A0], 8007000Eh
0x18008b548  mov     [rsp+3D8h+var_19C], 283Dh
0x18008b553  mov     [rsp+3D8h+var_198], r13d
0x18008b55b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b562  lea     rcx, [rsp+3D8h+var_1B8]; pExceptionObject
0x18008b56a  call    _CxxThrowException_0
0x18008b56f  mov     [rsp+3D8h+NumberOfBytesRead], 0
0x18008b577  mov     [rsp+3D8h+lpOverlapped], 0; lpOverlapped
0x18008b580  lea     r9, [rsp+3D8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008b585  mov     r8d, ebx; nNumberOfBytesToRead
0x18008b588  mov     rdx, r14; lpBuffer
0x18008b58b  mov     rcx, [rsp+3D8h+hFile]; hFile
0x18008b590  call    cs:__imp_ReadFile
0x18008b596  test    eax, eax
0x18008b598  jnz     short loc_18008B605
0x18008b59a  call    cs:__imp_GetLastError
0x18008b5a0  test    eax, eax
0x18008b5a2  jg      short loc_18008B5AE
0x18008b5a4  call    cs:__imp_GetLastError
0x18008b5aa  mov     ecx, eax
0x18008b5ac  jmp     short loc_18008B5BD
0x18008b5ae  call    cs:__imp_GetLastError
0x18008b5b4  movzx   ecx, ax
0x18008b5b7  or      ecx, 80070000h
0x18008b5bd  xorps   xmm0, xmm0
0x18008b5c0  movups  [rsp+3D8h+var_150], xmm0
0x18008b5c8  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b5cf  mov     [rsp+3D8h+var_158], rax
0x18008b5d7  mov     [rsp+3D8h+var_140], ecx
0x18008b5de  mov     [rsp+3D8h+var_13C], 284Bh
0x18008b5e9  mov     [rsp+3D8h+var_138], r13d
0x18008b5f1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b5f8  lea     rcx, [rsp+3D8h+var_158]; pExceptionObject
0x18008b600  call    _CxxThrowException_0
0x18008b605  cmp     [rsp+3D8h+NumberOfBytesRead], ebx
0x18008b609  jz      short loc_18008B657
0x18008b60b  xorps   xmm0, xmm0
0x18008b60e  movups  [rsp+3D8h+var_F0], xmm0
0x18008b616  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18008b61d  mov     [rsp+3D8h+var_F8], rax
0x18008b625  mov     [rsp+3D8h+var_E0], 80004005h
0x18008b630  mov     [rsp+3D8h+var_DC], 0
0x18008b63b  mov     [rsp+3D8h+var_D8], r13d
0x18008b643  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008b64a  lea     rcx, [rsp+3D8h+var_F8]; pExceptionObject
0x18008b652  call    _CxxThrowException_0
0x18008b657  mov     eax, [rsp+3D8h+NumberOfBytesRead]
0x18008b65b  mov     [rsi], rax
0x18008b65e  mov     [r15], r14
0x18008b661  lea     rcx, [rsp+3D8h+hFile]; void *
0x18008b666  call    ??1?$auto_HANDLE@$0?0@@QEAA@XZ; auto_HANDLE<-1>::~auto_HANDLE<-1>(void)
0x18008b66b  nop
0x18008b66c  lea     rcx, [rsp+3D8h+var_378]; this
0x18008b671  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18008b676  xor     eax, eax
0x18008b678  jmp     short loc_18008B685
0x18008b67a  mov     eax, [rsp+3D8h+NumberOfBytesRead]
0x18008b67e  jmp     short loc_18008B685
0x18008b680  mov     eax, 80070057h
0x18008b685  mov     rcx, [rsp+3D8h+var_38]
0x18008b68d  xor     rcx, rsp; StackCookie
0x18008b690  call    __security_check_cookie
0x18008b695  add     rsp, 3B0h
0x18008b69c  pop     r15
0x18008b69e  pop     r14
0x18008b6a0  pop     r13
0x18008b6a2  pop     rsi
0x18008b6a3  pop     rbx
0x18008b6a4  retn
```
