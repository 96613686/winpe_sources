# _read_file_async(Concurrency::streams::details::_file_info_impl *,Concurrency::streams::details::_filestream_callback *,void *,unsigned __int64,unsigned __int64)

- ea: `0x1800abeb0`
- end: `0x1800ac072`
- name: `?_read_file_async@@YA_KPEAU_file_info_impl@details@streams@Concurrency@@PEAV_filestream_callback@234@PEAX_K3@Z`
- size: `450`
- prototype: `unsigned __int64(struct Concurrency::streams::details::_file_info_impl *, struct Concurrency::streams::details::_filestream_callback *, void *, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ab7f0`
- `0x1800ac890`

## callees

- `0x180016c00`
- `0x180016caf`
- `0x180019024`
- `0x180019508`
- `0x180019e4e`
- `0x18001afc0`
- `0x1800a9d4d`
- `0x1800abeb0`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800abf41`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800abf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf49`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800abf26`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800abf26`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800abf6c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800abf6c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800abf9a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800abf9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _read_file_async(
        struct Concurrency::streams::details::_file_info_impl *a1,
        struct Concurrency::streams::details::_filestream_callback *a2,
        void *a3,
        DWORD a4,
        unsigned __int64 NumberOfBytesTransferred)
{
  struct _OVERLAPPED *v9; // rax
  struct _OVERLAPPED *lpOverlapped; // rbx
  DWORD v11; // rax^4
  BOOL File; // esi
  DWORD LastError; // eax
  DWORD v14; // ebp
  __int64 v15; // rsi
  BOOL OverlappedResult; // eax
  _QWORD *system_error; // rdi
  __int128 v19; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v20[48]; // [rsp+40h] [rbp-48h] BYREF

  v9 = (struct _OVERLAPPED *)operator new(0x30u);
  lpOverlapped = v9;
  if ( v9 )
  {
    v9[1].Internal = (ULONG_PTR)a2;
    v9[1].InternalHigh = (ULONG_PTR)_ReadFileCompletionRoutine<Concurrency::streams::details::_file_info_impl>;
    *(_OWORD *)&v9->Internal = 0;
    *(_OWORD *)&v9->Offset = 0;
  }
  else
  {
    lpOverlapped = 0;
  }
  v11 = HIDWORD(NumberOfBytesTransferred);
  lpOverlapped->Offset = NumberOfBytesTransferred;
  lpOverlapped->OffsetHigh = v11;
  StartThreadpoolIo(*((PTP_IO *)a1 + 19));
  File = ReadFile(*((HANDLE *)a1 + 18), a3, a4, 0, lpOverlapped);
  LastError = GetLastError();
  v14 = LastError;
  if ( !File && LastError == 997 )
  {
    lpOverlapped = 0;
    v15 = 0;
    goto LABEL_12;
  }
  CancelThreadpoolIo(*((PTP_IO *)a1 + 19));
  if ( File )
  {
    LODWORD(NumberOfBytesTransferred) = 0;
    OverlappedResult = GetOverlappedResult(*((HANDLE *)a1 + 18), lpOverlapped, (LPDWORD)&NumberOfBytesTransferred, 0);
    v15 = (unsigned int)NumberOfBytesTransferred;
    if ( !OverlappedResult )
      v15 = -1;
    if ( v15 == -1 )
      goto LABEL_11;
  }
  else
  {
    v15 = -1;
    if ( v14 != 38 )
    {
LABEL_11:
      system_error = (_QWORD *)utility::details::create_system_error(v20, v14);
      v19 = 0;
      __ExceptionPtrCreate(&v19);
      __ExceptionPtrCopyException(&v19, system_error, &TI4_AVsystem_error_std__);
      *system_error = &std::exception::`vftable';
      o___std_exception_destroy_0(system_error + 1);
      (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
        a2,
        &v19);
      __ExceptionPtrDestroy(&v19);
      goto LABEL_12;
    }
    (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, _QWORD))(*(_QWORD *)a2 + 24LL))(
      a2,
      0);
    v15 = 0;
  }
LABEL_12:
  if ( lpOverlapped )
    operator delete(lpOverlapped);
  return v15;
}

```

## disassembly

```asm
0x1800abeb0  mov     [rsp+arg_8], rbx
0x1800abeb5  mov     [rsp+arg_10], rbp
0x1800abeba  push    rsi
0x1800abebb  push    rdi
0x1800abebc  push    r14
0x1800abebe  sub     rsp, 70h
0x1800abec2  mov     rsi, r9
0x1800abec5  mov     rbp, r8
0x1800abec8  mov     r14, rdx
0x1800abecb  mov     rdi, rcx
0x1800abece  mov     ecx, 30h ; '0'; Size
0x1800abed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800abed8  mov     rbx, rax
0x1800abedb  mov     [rsp+88h+arg_0], rax
0x1800abee3  test    rax, rax
0x1800abee6  jz      short loc_1800ABF03
0x1800abee8  mov     [rax+20h], r14
0x1800abeec  lea     rax, ??$_ReadFileCompletionRoutine@U_file_info_impl@details@streams@Concurrency@@@@YAXKKPEAU_OVERLAPPED@@@Z; _ReadFileCompletionRoutine<Concurrency::streams::details::_file_info_impl>(ulong,ulong,_OVERLAPPED *)
0x1800abef3  mov     [rbx+28h], rax
0x1800abef7  xorps   xmm0, xmm0
0x1800abefa  movups  xmmword ptr [rbx], xmm0
0x1800abefd  movups  xmmword ptr [rbx+10h], xmm0
0x1800abf01  jmp     short loc_1800ABF05
0x1800abf03  xor     ebx, ebx
0x1800abf05  mov     [rsp+88h+arg_0], rbx
0x1800abf0d  mov     rax, qword ptr [rsp+88h+NumberOfBytesTransferred]
0x1800abf15  mov     [rbx+10h], eax
0x1800abf18  shr     rax, 20h
0x1800abf1c  mov     [rbx+14h], eax
0x1800abf1f  mov     rcx, [rdi+98h]; pio
0x1800abf26  call    cs:__imp_StartThreadpoolIo
0x1800abf2c  mov     r8d, esi; nNumberOfBytesToRead
0x1800abf2f  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x1800abf34  xor     r9d, r9d; lpNumberOfBytesRead
0x1800abf37  mov     rdx, rbp; lpBuffer
0x1800abf3a  mov     rcx, [rdi+90h]; hFile
0x1800abf41  call    cs:__imp_ReadFile
0x1800abf47  mov     esi, eax
0x1800abf49  call    cs:__imp_GetLastError
0x1800abf4f  mov     ebp, eax
0x1800abf51  test    esi, esi
0x1800abf53  jnz     short loc_1800ABF65
0x1800abf55  cmp     eax, 3E5h
0x1800abf5a  jnz     short loc_1800ABF65
0x1800abf5c  xor     ebx, ebx
0x1800abf5e  xor     esi, esi
0x1800abf60  jmp     loc_1800AC022
0x1800abf65  mov     rcx, [rdi+98h]; pio
0x1800abf6c  call    cs:__imp_CancelThreadpoolIo
0x1800abf72  test    esi, esi
0x1800abf74  jz      loc_1800AC04C
0x1800abf7a  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x1800abf85  xor     r9d, r9d; bWait
0x1800abf88  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800abf90  mov     rdx, rbx; lpOverlapped
0x1800abf93  mov     rcx, [rdi+90h]; hFile
0x1800abf9a  call    cs:__imp_GetOverlappedResult
0x1800abfa0  test    eax, eax
0x1800abfa2  mov     esi, [rsp+88h+NumberOfBytesTransferred]
0x1800abfa9  jnz     short loc_1800ABFB2
0x1800abfab  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800abfb2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800abfb6  jnz     short loc_1800AC022
0x1800abfb8  mov     edx, ebp
0x1800abfba  lea     rcx, [rsp+88h+var_48]
0x1800abfbf  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abfc4  mov     rdi, rax
0x1800abfc7  xorps   xmm0, xmm0
0x1800abfca  movdqu  [rsp+88h+var_58], xmm0
0x1800abfd0  lea     rcx, [rsp+88h+var_58]; void *
0x1800abfd5  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abfda  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abfe1  mov     rdx, rdi; void *
0x1800abfe4  lea     rcx, [rsp+88h+var_58]; void *
0x1800abfe9  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abfee  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abff5  mov     [rdi], rax
0x1800abff8  lea     rcx, [rdi+8]
0x1800abffc  call    _o___std_exception_destroy_0
0x1800ac001  nop
0x1800ac002  mov     rax, [r14]
0x1800ac005  lea     rdx, [rsp+88h+var_58]
0x1800ac00a  mov     rcx, r14
0x1800ac00d  mov     rax, [rax+10h]
0x1800ac011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac016  nop
0x1800ac017  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac01c  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ac021  nop
0x1800ac022  test    rbx, rbx
0x1800ac025  jz      short loc_1800AC034
0x1800ac027  mov     edx, 30h ; '0'
0x1800ac02c  mov     rcx, rbx; Block
0x1800ac02f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac034  mov     rax, rsi
0x1800ac037  lea     r11, [rsp+88h+var_18]
0x1800ac03c  mov     rbx, [r11+28h]
0x1800ac040  mov     rbp, [r11+30h]
0x1800ac044  mov     rsp, r11
0x1800ac047  pop     r14
0x1800ac049  pop     rdi
0x1800ac04a  pop     rsi
0x1800ac04b  retn
0x1800ac04c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800ac053  cmp     ebp, 26h ; '&'
0x1800ac056  jnz     loc_1800ABFB8
0x1800ac05c  mov     rax, [r14]
0x1800ac05f  xor     edx, edx
0x1800ac061  mov     rcx, r14
0x1800ac064  mov     rax, [rax+18h]
0x1800ac068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac06d  xor     esi, esi
0x1800ac06f  jmp     short loc_1800AC022
```
