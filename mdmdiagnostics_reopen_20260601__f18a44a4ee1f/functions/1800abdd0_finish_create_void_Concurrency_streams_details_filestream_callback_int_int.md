# _finish_create(void *,Concurrency::streams::details::_filestream_callback *,int,int)

- ea: `0x1800abdd0`
- end: `0x1800ac03d`
- name: `?_finish_create@@YAXPEAXPEAV_filestream_callback@details@streams@Concurrency@@HH@Z`
- size: `621`
- prototype: `void __fastcall(HANDLE FileHandle, struct Concurrency::streams::details::_filestream_callback *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ab700`

## callees

- `0x180016c80`
- `0x180016d2f`
- `0x1800190a4`
- `0x180019ede`
- `0x18001add0`
- `0x18001b0a0`
- `0x1800a9eed`
- `0x1800abdd0`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abdfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800abe7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800abe7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800abf10`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800abf10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1800abf03`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1800abf03`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _finish_create(
        HANDLE FileHandle,
        struct Concurrency::streams::details::_filestream_callback *a2,
        int a3,
        int a4)
{
  DWORD LastError; // eax
  _QWORD *system_error; // rbx
  struct _TP_IO *ThreadpoolIo; // r15
  DWORD v11; // eax
  _QWORD *v12; // rbx
  bool v13; // zf
  __int64 v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  __int128 v17; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v18[48]; // [rsp+30h] [rbp-58h] BYREF

  if ( FileHandle == (HANDLE)-1LL || (ThreadpoolIo = CreateThreadpoolIo(FileHandle, IoCompletionCallback, 0, 0)) == 0 )
  {
    LastError = GetLastError();
    system_error = (_QWORD *)utility::details::create_system_error(v18, LastError);
    v17 = 0;
    __ExceptionPtrCreate(&v17);
    __ExceptionPtrCopyException(&v17, system_error, &TI4_AVsystem_error_std__);
    *system_error = &std::exception::`vftable';
    o___std_exception_destroy_0(system_error + 1);
    (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
      a2,
      &v17);
    __ExceptionPtrDestroy(&v17);
  }
  else if ( SetFileCompletionNotificationModes(FileHandle, 1u) )
  {
    if ( a3 != 1 || (v13 = a4 == 16, v14 = 512, !v13) )
      v14 = 0;
    v15 = operator new(0xA0u);
    v16 = v15;
    if ( v15 )
    {
      *v15 = 0;
      v15[1] = 0;
      *((_BYTE *)v15 + 16) = 0;
      v15[3] = v14;
      v15[4] = 0;
      v15[5] = 0;
      v15[6] = 0;
      v15[7] = 0;
      *((_DWORD *)v15 + 16) = a3;
      pplx::details::critical_section_impl::critical_section_impl((pplx::details::critical_section_impl *)(v15 + 9));
      *((_DWORD *)v16 + 34) = 0;
      *((_DWORD *)v16 + 35) = -1;
      v16[18] = FileHandle;
      v16[19] = ThreadpoolIo;
    }
    else
    {
      v16 = 0;
    }
    if ( (a3 & 0xC) != 0 )
      v16[1] = -1;
    (**(void (__fastcall ***)(struct Concurrency::streams::details::_filestream_callback *, _QWORD *))a2)(a2, v16);
  }
  else
  {
    CloseThreadpoolIo(ThreadpoolIo);
    v11 = GetLastError();
    v12 = (_QWORD *)utility::details::create_system_error(v18, v11);
    v17 = 0;
    __ExceptionPtrCreate(&v17);
    __ExceptionPtrCopyException(&v17, v12, &TI4_AVsystem_error_std__);
    *v12 = &std::exception::`vftable';
    o___std_exception_destroy_0(v12 + 1);
    (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
      a2,
      &v17);
    __ExceptionPtrDestroy(&v17);
  }
}

```

## disassembly

```asm
0x1800abdd0  mov     [rsp+arg_8], rbx
0x1800abdd5  mov     [rsp+arg_10], rbp
0x1800abdda  push    rsi
0x1800abddb  push    rdi
0x1800abddc  push    r12
0x1800abdde  push    r14
0x1800abde0  push    r15
0x1800abde2  sub     rsp, 60h
0x1800abde6  mov     ebx, r9d
0x1800abde9  mov     ebp, r8d
0x1800abdec  mov     r14, rdx
0x1800abdef  mov     rsi, rcx
0x1800abdf2  xor     r12d, r12d
0x1800abdf5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800abdf9  jnz     short loc_1800ABE6F
0x1800abdfb  call    cs:__imp_GetLastError
0x1800abe01  mov     edx, eax
0x1800abe03  lea     rcx, [rsp+88h+var_58]
0x1800abe08  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abe0d  mov     rbx, rax
0x1800abe10  xorps   xmm0, xmm0
0x1800abe13  movdqu  [rsp+88h+var_68], xmm0
0x1800abe19  lea     rcx, [rsp+88h+var_68]; void *
0x1800abe1e  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abe23  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abe2a  mov     rdx, rbx; void *
0x1800abe2d  lea     rcx, [rsp+88h+var_68]; void *
0x1800abe32  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abe37  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abe3e  mov     [rbx], rax
0x1800abe41  lea     rcx, [rbx+8]
0x1800abe45  call    _o___std_exception_destroy_0
0x1800abe4a  nop
0x1800abe4b  mov     rax, [r14]
0x1800abe4e  lea     rdx, [rsp+88h+var_68]
0x1800abe53  mov     rcx, r14
0x1800abe56  mov     rax, [rax+10h]
0x1800abe5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe5f  nop
0x1800abe60  lea     rcx, [rsp+88h+var_68]; void *
0x1800abe65  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abe6a  jmp     loc_1800AC024
0x1800abe6f  xor     r9d, r9d; pcbe
0x1800abe72  xor     r8d, r8d; pv
0x1800abe75  lea     rdx, ?IoCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800abe7c  call    cs:__imp_CreateThreadpoolIo
0x1800abe82  mov     r15, rax
0x1800abe85  test    rax, rax
0x1800abe88  jnz     short loc_1800ABEFE
0x1800abe8a  call    cs:__imp_GetLastError
0x1800abe90  mov     edx, eax
0x1800abe92  lea     rcx, [rsp+88h+var_58]
0x1800abe97  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abe9c  mov     rbx, rax
0x1800abe9f  xorps   xmm0, xmm0
0x1800abea2  movdqu  [rsp+88h+var_68], xmm0
0x1800abea8  lea     rcx, [rsp+88h+var_68]; void *
0x1800abead  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abeb2  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abeb9  mov     rdx, rbx; void *
0x1800abebc  lea     rcx, [rsp+88h+var_68]; void *
0x1800abec1  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abec6  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abecd  mov     [rbx], rax
0x1800abed0  lea     rcx, [rbx+8]
0x1800abed4  call    _o___std_exception_destroy_0
0x1800abed9  nop
0x1800abeda  mov     rax, [r14]
0x1800abedd  lea     rdx, [rsp+88h+var_68]
0x1800abee2  mov     rcx, r14
0x1800abee5  mov     rax, [rax+10h]
0x1800abee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abeee  nop
0x1800abeef  lea     rcx, [rsp+88h+var_68]; void *
0x1800abef4  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abef9  jmp     loc_1800AC024
0x1800abefe  mov     dl, 1; Flags
0x1800abf00  mov     rcx, rsi; FileHandle
0x1800abf03  call    cs:__imp_SetFileCompletionNotificationModes
0x1800abf09  test    eax, eax
0x1800abf0b  jnz     short loc_1800ABF8A
0x1800abf0d  mov     rcx, r15; pio
0x1800abf10  call    cs:__imp_CloseThreadpoolIo
0x1800abf16  call    cs:__imp_GetLastError
0x1800abf1c  mov     edx, eax
0x1800abf1e  lea     rcx, [rsp+88h+var_58]
0x1800abf23  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abf28  mov     rbx, rax
0x1800abf2b  xorps   xmm0, xmm0
0x1800abf2e  movdqu  [rsp+88h+var_68], xmm0
0x1800abf34  lea     rcx, [rsp+88h+var_68]; void *
0x1800abf39  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abf3e  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abf45  mov     rdx, rbx; void *
0x1800abf48  lea     rcx, [rsp+88h+var_68]; void *
0x1800abf4d  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abf52  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abf59  mov     [rbx], rax
0x1800abf5c  lea     rcx, [rbx+8]
0x1800abf60  call    _o___std_exception_destroy_0
0x1800abf65  nop
0x1800abf66  mov     rax, [r14]
0x1800abf69  lea     rdx, [rsp+88h+var_68]
0x1800abf6e  mov     rcx, r14
0x1800abf71  mov     rax, [rax+10h]
0x1800abf75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf7a  nop
0x1800abf7b  lea     rcx, [rsp+88h+var_68]; void *
0x1800abf80  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abf85  jmp     loc_1800AC024
0x1800abf8a  cmp     ebp, 1
0x1800abf8d  jnz     short loc_1800ABF99
0x1800abf8f  cmp     ebx, 10h
0x1800abf92  mov     ebx, 200h
0x1800abf97  jz      short loc_1800ABF9C
0x1800abf99  mov     rbx, r12
0x1800abf9c  mov     ecx, 0A0h; Size
0x1800abfa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800abfa6  mov     rdi, rax
0x1800abfa9  mov     [rsp+88h+arg_0], rax
0x1800abfb1  test    rax, rax
0x1800abfb4  jz      short loc_1800AC002
0x1800abfb6  mov     [rax], r12
0x1800abfb9  mov     [rax+8], r12
0x1800abfbd  mov     byte ptr [rax+10h], 0
0x1800abfc1  mov     [rax+18h], rbx
0x1800abfc5  mov     [rax+20h], r12
0x1800abfc9  mov     [rax+28h], r12
0x1800abfcd  mov     [rax+30h], r12
0x1800abfd1  mov     [rax+38h], r12
0x1800abfd5  mov     [rax+40h], ebp
0x1800abfd8  lea     rcx, [rax+48h]; this
0x1800abfdc  call    ??0critical_section_impl@details@pplx@@QEAA@XZ; pplx::details::critical_section_impl::critical_section_impl(void)
0x1800abfe1  mov     [rdi+88h], r12d
0x1800abfe8  mov     dword ptr [rdi+8Ch], 0FFFFFFFFh
0x1800abff2  mov     [rdi+90h], rsi
0x1800abff9  mov     [rdi+98h], r15
0x1800ac000  jmp     short loc_1800AC005
0x1800ac002  mov     rdi, r12
0x1800ac005  test    bpl, 0Ch
0x1800ac009  jz      short loc_1800AC013
0x1800ac00b  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800ac013  mov     rax, [r14]
0x1800ac016  mov     rdx, rdi
0x1800ac019  mov     rcx, r14
0x1800ac01c  mov     rax, [rax]
0x1800ac01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac024  lea     r11, [rsp+88h+var_28]
0x1800ac029  mov     rbx, [r11+38h]
0x1800ac02d  mov     rbp, [r11+40h]
0x1800ac031  mov     rsp, r11
0x1800ac034  pop     r15
0x1800ac036  pop     r14
0x1800ac038  pop     r12
0x1800ac03a  pop     rdi
0x1800ac03b  pop     rsi
0x1800ac03c  retn
```
