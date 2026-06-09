# _write_file_async(Concurrency::streams::details::_file_info_impl *,Concurrency::streams::details::_filestream_callback *,void const *,unsigned __int64,unsigned __int64)

- ea: `0x1800ac220`
- end: `0x1800ac3c5`
- name: `?_write_file_async@@YA_KPEAU_file_info_impl@details@streams@Concurrency@@PEAV_filestream_callback@234@PEBX_K3@Z`
- size: `421`
- prototype: `unsigned __int64(struct Concurrency::streams::details::_file_info_impl *, struct Concurrency::streams::details::_filestream_callback *, const void *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ace60`

## callees

- `0x180016c80`
- `0x180016d2f`
- `0x1800190a4`
- `0x180019588`
- `0x180019ede`
- `0x18001b0a0`
- `0x1800a9eed`
- `0x1800ac220`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ac2c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ac2c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2cb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac2a8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac2a8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac2ee`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac2ee`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac318`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac318`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _write_file_async(
        struct Concurrency::streams::details::_file_info_impl *a1,
        struct Concurrency::streams::details::_filestream_callback *a2,
        const void *a3,
        DWORD a4,
        unsigned __int64 NumberOfBytesTransferred)
{
  struct _OVERLAPPED *v9; // rax
  struct _OVERLAPPED *lpOverlapped; // rbx
  int v11; // ecx
  unsigned __int64 v12; // rax
  BOOL v13; // esi
  DWORD LastError; // eax
  DWORD v15; // ebp
  __int64 v16; // rdi
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
  v11 = NumberOfBytesTransferred;
  if ( NumberOfBytesTransferred == -1 )
  {
    LODWORD(v12) = -1;
    v11 = -1;
  }
  else
  {
    v12 = HIDWORD(NumberOfBytesTransferred);
  }
  lpOverlapped->Offset = v11;
  lpOverlapped->OffsetHigh = v12;
  StartThreadpoolIo(*((PTP_IO *)a1 + 19));
  v13 = WriteFile(*((HANDLE *)a1 + 18), a3, a4, 0, lpOverlapped);
  LastError = GetLastError();
  v15 = LastError;
  if ( v13 || LastError != 997 )
  {
    CancelThreadpoolIo(*((PTP_IO *)a1 + 19));
    if ( v13
      && (LODWORD(NumberOfBytesTransferred) = 0,
          GetOverlappedResult(*((HANDLE *)a1 + 18), lpOverlapped, (LPDWORD)&NumberOfBytesTransferred, 0)) )
    {
      v16 = (unsigned int)NumberOfBytesTransferred;
    }
    else
    {
      system_error = (_QWORD *)utility::details::create_system_error(v20, v15);
      v19 = 0;
      __ExceptionPtrCreate(&v19);
      __ExceptionPtrCopyException(&v19, system_error, &TI4_AVsystem_error_std__);
      *system_error = &std::exception::`vftable';
      o___std_exception_destroy_0(system_error + 1);
      (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
        a2,
        &v19);
      __ExceptionPtrDestroy(&v19);
      v16 = -1;
    }
  }
  else
  {
    lpOverlapped = 0;
    v16 = 0;
  }
  if ( lpOverlapped )
    operator delete(lpOverlapped);
  return v16;
}

```

## disassembly

```asm
0x1800ac220  mov     [rsp+arg_8], rbx
0x1800ac225  mov     [rsp+arg_10], rbp
0x1800ac22a  push    rsi
0x1800ac22b  push    rdi
0x1800ac22c  push    r14
0x1800ac22e  sub     rsp, 70h
0x1800ac232  mov     rsi, r9
0x1800ac235  mov     rbp, r8
0x1800ac238  mov     r14, rdx
0x1800ac23b  mov     rdi, rcx
0x1800ac23e  mov     ecx, 30h ; '0'; Size
0x1800ac243  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac248  mov     rbx, rax
0x1800ac24b  mov     [rsp+88h+arg_0], rax
0x1800ac253  test    rax, rax
0x1800ac256  jz      short loc_1800AC273
0x1800ac258  mov     [rax+20h], r14
0x1800ac25c  lea     rax, ??$_ReadFileCompletionRoutine@U_file_info_impl@details@streams@Concurrency@@@@YAXKKPEAU_OVERLAPPED@@@Z; _ReadFileCompletionRoutine<Concurrency::streams::details::_file_info_impl>(ulong,ulong,_OVERLAPPED *)
0x1800ac263  mov     [rbx+28h], rax
0x1800ac267  xorps   xmm0, xmm0
0x1800ac26a  movups  xmmword ptr [rbx], xmm0
0x1800ac26d  movups  xmmword ptr [rbx+10h], xmm0
0x1800ac271  jmp     short loc_1800AC275
0x1800ac273  xor     ebx, ebx
0x1800ac275  mov     [rsp+88h+arg_0], rbx
0x1800ac27d  mov     rcx, qword ptr [rsp+88h+NumberOfBytesTransferred]
0x1800ac285  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac289  jnz     short loc_1800AC294
0x1800ac28b  mov     eax, 0FFFFFFFFh
0x1800ac290  mov     ecx, eax
0x1800ac292  jmp     short loc_1800AC29B
0x1800ac294  mov     rax, rcx
0x1800ac297  shr     rax, 20h
0x1800ac29b  mov     [rbx+10h], ecx
0x1800ac29e  mov     [rbx+14h], eax
0x1800ac2a1  mov     rcx, [rdi+98h]; pio
0x1800ac2a8  call    cs:__imp_StartThreadpoolIo
0x1800ac2ae  mov     r8d, esi; nNumberOfBytesToWrite
0x1800ac2b1  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x1800ac2b6  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800ac2b9  mov     rdx, rbp; lpBuffer
0x1800ac2bc  mov     rcx, [rdi+90h]; hFile
0x1800ac2c3  call    cs:__imp_WriteFile
0x1800ac2c9  mov     esi, eax
0x1800ac2cb  call    cs:__imp_GetLastError
0x1800ac2d1  mov     ebp, eax
0x1800ac2d3  test    esi, esi
0x1800ac2d5  jnz     short loc_1800AC2E7
0x1800ac2d7  cmp     eax, 3E5h
0x1800ac2dc  jnz     short loc_1800AC2E7
0x1800ac2de  xor     ebx, ebx
0x1800ac2e0  xor     edi, edi
0x1800ac2e2  jmp     loc_1800AC39B
0x1800ac2e7  mov     rcx, [rdi+98h]; pio
0x1800ac2ee  call    cs:__imp_CancelThreadpoolIo
0x1800ac2f4  test    esi, esi
0x1800ac2f6  jz      short loc_1800AC32B
0x1800ac2f8  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x1800ac303  xor     r9d, r9d; bWait
0x1800ac306  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800ac30e  mov     rdx, rbx; lpOverlapped
0x1800ac311  mov     rcx, [rdi+90h]; hFile
0x1800ac318  call    cs:__imp_GetOverlappedResult
0x1800ac31e  test    eax, eax
0x1800ac320  jz      short loc_1800AC32B
0x1800ac322  mov     edi, [rsp+88h+NumberOfBytesTransferred]
0x1800ac329  jmp     short loc_1800AC39B
0x1800ac32b  mov     edx, ebp
0x1800ac32d  lea     rcx, [rsp+88h+var_48]
0x1800ac332  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800ac337  mov     rdi, rax
0x1800ac33a  xorps   xmm0, xmm0
0x1800ac33d  movdqu  [rsp+88h+var_58], xmm0
0x1800ac343  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac348  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800ac34d  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800ac354  mov     rdx, rdi; void *
0x1800ac357  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac35c  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800ac361  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800ac368  mov     [rdi], rax
0x1800ac36b  lea     rcx, [rdi+8]
0x1800ac36f  call    _o___std_exception_destroy_0
0x1800ac374  nop
0x1800ac375  mov     rax, [r14]
0x1800ac378  lea     rdx, [rsp+88h+var_58]
0x1800ac37d  mov     rcx, r14
0x1800ac380  mov     rax, [rax+10h]
0x1800ac384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac389  nop
0x1800ac38a  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac38f  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ac394  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ac39b  test    rbx, rbx
0x1800ac39e  jz      short loc_1800AC3AD
0x1800ac3a0  mov     edx, 30h ; '0'
0x1800ac3a5  mov     rcx, rbx; Block
0x1800ac3a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac3ad  mov     rax, rdi
0x1800ac3b0  lea     r11, [rsp+88h+var_18]
0x1800ac3b5  mov     rbx, [r11+28h]
0x1800ac3b9  mov     rbp, [r11+30h]
0x1800ac3bd  mov     rsp, r11
0x1800ac3c0  pop     r14
0x1800ac3c2  pop     rdi
0x1800ac3c3  pop     rsi
0x1800ac3c4  retn
```
