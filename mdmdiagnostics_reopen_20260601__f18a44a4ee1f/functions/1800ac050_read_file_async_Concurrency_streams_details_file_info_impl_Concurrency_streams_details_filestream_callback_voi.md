# _read_file_async(Concurrency::streams::details::_file_info_impl *,Concurrency::streams::details::_filestream_callback *,void *,unsigned __int64,unsigned __int64)

- ea: `0x1800ac050`
- end: `0x1800ac212`
- name: `?_read_file_async@@YA_KPEAU_file_info_impl@details@streams@Concurrency@@PEAV_filestream_callback@234@PEAX_K3@Z`
- size: `450`
- prototype: `unsigned __int64(struct Concurrency::streams::details::_file_info_impl *, struct Concurrency::streams::details::_filestream_callback *, void *, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ab990`
- `0x1800aca30`

## callees

- `0x180016c80`
- `0x180016d2f`
- `0x1800190a4`
- `0x180019588`
- `0x180019ede`
- `0x18001b0a0`
- `0x1800a9eed`
- `0x1800ac050`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ac0e1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ac0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0e9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac0c6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800ac0c6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac10c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800ac10c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac13a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ac13a`

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
0x1800ac050  mov     [rsp+arg_8], rbx
0x1800ac055  mov     [rsp+arg_10], rbp
0x1800ac05a  push    rsi
0x1800ac05b  push    rdi
0x1800ac05c  push    r14
0x1800ac05e  sub     rsp, 70h
0x1800ac062  mov     rsi, r9
0x1800ac065  mov     rbp, r8
0x1800ac068  mov     r14, rdx
0x1800ac06b  mov     rdi, rcx
0x1800ac06e  mov     ecx, 30h ; '0'; Size
0x1800ac073  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac078  mov     rbx, rax
0x1800ac07b  mov     [rsp+88h+arg_0], rax
0x1800ac083  test    rax, rax
0x1800ac086  jz      short loc_1800AC0A3
0x1800ac088  mov     [rax+20h], r14
0x1800ac08c  lea     rax, ??$_ReadFileCompletionRoutine@U_file_info_impl@details@streams@Concurrency@@@@YAXKKPEAU_OVERLAPPED@@@Z; _ReadFileCompletionRoutine<Concurrency::streams::details::_file_info_impl>(ulong,ulong,_OVERLAPPED *)
0x1800ac093  mov     [rbx+28h], rax
0x1800ac097  xorps   xmm0, xmm0
0x1800ac09a  movups  xmmword ptr [rbx], xmm0
0x1800ac09d  movups  xmmword ptr [rbx+10h], xmm0
0x1800ac0a1  jmp     short loc_1800AC0A5
0x1800ac0a3  xor     ebx, ebx
0x1800ac0a5  mov     [rsp+88h+arg_0], rbx
0x1800ac0ad  mov     rax, qword ptr [rsp+88h+NumberOfBytesTransferred]
0x1800ac0b5  mov     [rbx+10h], eax
0x1800ac0b8  shr     rax, 20h
0x1800ac0bc  mov     [rbx+14h], eax
0x1800ac0bf  mov     rcx, [rdi+98h]; pio
0x1800ac0c6  call    cs:__imp_StartThreadpoolIo
0x1800ac0cc  mov     r8d, esi; nNumberOfBytesToRead
0x1800ac0cf  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x1800ac0d4  xor     r9d, r9d; lpNumberOfBytesRead
0x1800ac0d7  mov     rdx, rbp; lpBuffer
0x1800ac0da  mov     rcx, [rdi+90h]; hFile
0x1800ac0e1  call    cs:__imp_ReadFile
0x1800ac0e7  mov     esi, eax
0x1800ac0e9  call    cs:__imp_GetLastError
0x1800ac0ef  mov     ebp, eax
0x1800ac0f1  test    esi, esi
0x1800ac0f3  jnz     short loc_1800AC105
0x1800ac0f5  cmp     eax, 3E5h
0x1800ac0fa  jnz     short loc_1800AC105
0x1800ac0fc  xor     ebx, ebx
0x1800ac0fe  xor     esi, esi
0x1800ac100  jmp     loc_1800AC1C2
0x1800ac105  mov     rcx, [rdi+98h]; pio
0x1800ac10c  call    cs:__imp_CancelThreadpoolIo
0x1800ac112  test    esi, esi
0x1800ac114  jz      loc_1800AC1EC
0x1800ac11a  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x1800ac125  xor     r9d, r9d; bWait
0x1800ac128  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800ac130  mov     rdx, rbx; lpOverlapped
0x1800ac133  mov     rcx, [rdi+90h]; hFile
0x1800ac13a  call    cs:__imp_GetOverlappedResult
0x1800ac140  test    eax, eax
0x1800ac142  mov     esi, [rsp+88h+NumberOfBytesTransferred]
0x1800ac149  jnz     short loc_1800AC152
0x1800ac14b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800ac152  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800ac156  jnz     short loc_1800AC1C2
0x1800ac158  mov     edx, ebp
0x1800ac15a  lea     rcx, [rsp+88h+var_48]
0x1800ac15f  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800ac164  mov     rdi, rax
0x1800ac167  xorps   xmm0, xmm0
0x1800ac16a  movdqu  [rsp+88h+var_58], xmm0
0x1800ac170  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac175  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800ac17a  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800ac181  mov     rdx, rdi; void *
0x1800ac184  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac189  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800ac18e  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800ac195  mov     [rdi], rax
0x1800ac198  lea     rcx, [rdi+8]
0x1800ac19c  call    _o___std_exception_destroy_0
0x1800ac1a1  nop
0x1800ac1a2  mov     rax, [r14]
0x1800ac1a5  lea     rdx, [rsp+88h+var_58]
0x1800ac1aa  mov     rcx, r14
0x1800ac1ad  mov     rax, [rax+10h]
0x1800ac1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac1b6  nop
0x1800ac1b7  lea     rcx, [rsp+88h+var_58]; void *
0x1800ac1bc  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ac1c1  nop
0x1800ac1c2  test    rbx, rbx
0x1800ac1c5  jz      short loc_1800AC1D4
0x1800ac1c7  mov     edx, 30h ; '0'
0x1800ac1cc  mov     rcx, rbx; Block
0x1800ac1cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac1d4  mov     rax, rsi
0x1800ac1d7  lea     r11, [rsp+88h+var_18]
0x1800ac1dc  mov     rbx, [r11+28h]
0x1800ac1e0  mov     rbp, [r11+30h]
0x1800ac1e4  mov     rsp, r11
0x1800ac1e7  pop     r14
0x1800ac1e9  pop     rdi
0x1800ac1ea  pop     rsi
0x1800ac1eb  retn
0x1800ac1ec  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800ac1f3  cmp     ebp, 26h ; '&'
0x1800ac1f6  jnz     loc_1800AC158
0x1800ac1fc  mov     rax, [r14]
0x1800ac1ff  xor     edx, edx
0x1800ac201  mov     rcx, r14
0x1800ac204  mov     rax, [rax+18h]
0x1800ac208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac20d  xor     esi, esi
0x1800ac20f  jmp     short loc_1800AC1C2
```
