# _write_file_async(Concurrency::streams::details::_file_info_impl *,Concurrency::streams::details::_filestream_callback *,void const *,unsigned __int64,unsigned __int64)

- ea: `0x1800ac080`
- end: `0x1800ac225`
- name: `?_write_file_async@@YA_KPEAU_file_info_impl@details@streams@Concurrency@@PEAV_filestream_callback@234@PEBX_K3@Z`
- size: `421`
- prototype: `unsigned __int64(struct Concurrency::streams::details::_file_info_impl *, struct Concurrency::streams::details::_filestream_callback *, const void *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800accc0`

## callees

- `0x180016c00`
- `0x180016caf`
- `0x180019024`
- `0x180019508`
- `0x180019e4e`
- `0x18001afc0`
- `0x1800a9d4d`
- `0x1800ac080`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ac123`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ac123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac12b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac12b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac108`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac108`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac14e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac14e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac178`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac178`

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
0x1800ac080  mov     [rsp+arg_8], rbx
0x1800ac085  mov     [rsp+arg_10], rbp
0x1800ac08a  push    rsi
0x1800ac08b  push    rdi
0x1800ac08c  push    r14
0x1800ac08e  sub     rsp, 70h
0x1800ac092  mov     rsi, r9
0x1800ac095  mov     rbp, r8
0x1800ac098  mov     r14, rdx
0x1800ac09b  mov     rdi, rcx
0x1800ac09e  mov     ecx, 30h ; '0'; Size
0x1800ac0a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac0a8  mov     rbx, rax
0x1800ac0ab  mov     [rsp+88h+arg_0], rax
0x1800ac0b3  test    rax, rax
0x1800ac0b6  jz      short loc_1800AC0D3
0x1800ac0b8  mov     [rax+20h], r14
0x1800ac0bc  lea     rax, ??$_ReadFileCompletionRoutine@U_file_info_impl@details@streams@Concurrency@@@@YAXKKPEAU_OVERLAPPED@@@Z; _ReadFileCompletionRoutine<Concurrency::streams::details::_file_info_impl>(ulong,ulong,_OVERLAPPED *)
0x1800ac0c3  mov     [rbx+28h], rax
0x1800ac0c7  xorps   xmm0, xmm0
0x1800ac0ca  movups  xmmword ptr [rbx], xmm0
0x1800ac0cd  movups  xmmword ptr [rbx+10h], xmm0
0x1800ac0d1  jmp     short loc_1800AC0D5
0x1800ac0d3  xor     ebx, ebx
0x1800ac0d5  mov     [rsp+88h+arg_0], rbx
0x1800ac0dd  mov     rcx, qword ptr [rsp+88h+NumberOfBytesTransferred]
0x1800ac0e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac0e9  jnz     short loc_1800AC0F4
0x1800ac0eb  mov     eax, 0FFFFFFFFh
0x1800ac0f0  mov     ecx, eax
0x1800ac0f2  jmp     short loc_1800AC0FB
0x1800ac0f4  mov     rax, rcx
0x1800ac0f7  shr     rax, 20h
0x1800ac0fb  mov     [rbx+10h], ecx
0x1800ac0fe  mov     [rbx+14h], eax
0x1800ac101  mov     rcx, [rdi+98h]; pio
0x1800ac108  call    cs:__imp_StartThreadpoolIo
0x1800ac10e  mov     r8d, esi; nNumberOfBytesToWrite
0x1800ac111  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x1800ac116  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800ac119  mov     rdx, rbp; lpBuffer
0x1800ac11c  mov     rcx, [rdi+90h]; hFile
0x1800ac123  call    cs:__imp_WriteFile
0x1800ac129  mov     esi, eax
0x1800ac12b  call    cs:__imp_GetLastError
0x1800ac131  mov     ebp, eax
0x1800ac133  test    esi, esi
0x1800ac135  jnz     short loc_1800AC147
0x1800ac137  cmp     eax, 3E5h
0x1800ac13c  jnz     short loc_1800AC147
0x1800ac13e  xor     ebx, ebx
0x1800ac140  xor     edi, edi
0x1800ac142  jmp     loc_1800AC1FB
0x1800ac147  mov     rcx, [rdi+98h]; pio
0x1800ac14e  call    cs:__imp_CancelThreadpoolIo
0x1800ac154  test    esi, esi
0x1800ac156  jz      short loc_1800AC18B
0x1800ac158  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x1800ac163  xor     r9d, r9d; bWait
0x1800ac166  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800ac16e  mov     rdx, rbx; lpOverlapped
0x1800ac171  mov     rcx, [rdi+90h]; hFile
0x1800ac178  call    cs:__imp_GetOverlappedResult
0x1800ac17e  test    eax, eax
0x1800ac180  jz      short loc_1800AC18B
0x1800ac182  mov     edi, [rsp+88h+NumberOfBytesTransferred]
0x1800ac189  jmp     short loc_1800AC1FB
0x1800ac18b  mov     edx, ebp
0x1800ac18d  lea     rcx, [rsp+88h+var_48]
0x1800ac192  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800ac197  mov     rdi, rax
0x1800ac19a  xorps   xmm0, xmm0
0x1800ac19d  movdqu  [rsp+88h+var_58], xmm0
0x1800ac1a3  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac1a8  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800ac1ad  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800ac1b4  mov     rdx, rdi; void *
0x1800ac1b7  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac1bc  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800ac1c1  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800ac1c8  mov     [rdi], rax
0x1800ac1cb  lea     rcx, [rdi+8]
0x1800ac1cf  call    _o___std_exception_destroy_0
0x1800ac1d4  nop
0x1800ac1d5  mov     rax, [r14]
0x1800ac1d8  lea     rdx, [rsp+88h+var_58]
0x1800ac1dd  mov     rcx, r14
0x1800ac1e0  mov     rax, [rax+10h]
0x1800ac1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac1e9  nop
0x1800ac1ea  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac1ef  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ac1f4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ac1fb  test    rbx, rbx
0x1800ac1fe  jz      short loc_1800AC20D
0x1800ac200  mov     edx, 30h ; '0'
0x1800ac205  mov     rcx, rbx; Block
0x1800ac208  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac20d  mov     rax, rdi
0x1800ac210  lea     r11, [rsp+88h+var_18]
0x1800ac215  mov     rbx, [r11+28h]
0x1800ac219  mov     rbp, [r11+30h]
0x1800ac21d  mov     rsp, r11
0x1800ac220  pop     r14
0x1800ac222  pop     rdi
0x1800ac223  pop     rsi
0x1800ac224  retn
```
