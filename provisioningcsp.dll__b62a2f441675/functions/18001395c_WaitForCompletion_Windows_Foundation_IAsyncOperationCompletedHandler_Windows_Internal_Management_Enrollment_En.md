# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18001395c`
- end: `0x180013b39`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014f14`

## callees

- `0x1800030e8`
- `0x18001395c`
- `0x180013b40`
- `0x180021de4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800139cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800139cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(
        __int64 a1,
        int a2,
        void **a3)
{
  void *v4; // rax
  void **v5; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v8; // edi
  void (__fastcall **v9)(void **); // rax
  unsigned int v10; // r9d
  __int64 v11; // rcx
  unsigned int v12; // edi
  void **v13; // rcx
  unsigned int v15; // [rsp+20h] [rbp-28h]
  unsigned int v16; // [rsp+28h] [rbp-20h]
  void *v17[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v18; // [rsp+70h] [rbp+28h] BYREF
  int v19; // [rsp+78h] [rbp+30h] BYREF
  void **v20; // [rsp+80h] [rbp+38h]
  __int64 v21; // [rsp+88h] [rbp+40h]

  v20 = a3;
  v19 = a2;
  v21 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v20 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v19 = -2147024882;
    goto LABEL_20;
  }
  v5 = (void **)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v4);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v5[7] = Event;
  if ( Event )
  {
    v9 = (void (__fastcall **)(void **))*v5;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = (void (__fastcall **)(void **))*v5;
    if ( v8 < 0 )
    {
      v9[2](v5);
      v19 = v8;
      goto LABEL_20;
    }
  }
  v9[1](v5);
  v20 = v5;
  (*((void (__fastcall **)(void **))*v5 + 2))(v5);
  v19 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a1 + 48LL))(a1, v20);
  if ( v19 >= 0 )
  {
    v17[0] = v20[7];
    v17[1] = 0;
    if ( SHProcessMessagesUntilEventsEx((HWND)v17[0], v17, 1u, v10, v15, v16) == -1 )
      v19 = -2147467259;
    v18 = 0;
    if ( v19 >= 0
      && *((_DWORD *)v20 + 12) != 1
      && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, &v18) >= 0 )
    {
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 64LL))(v18, &v19);
    }
    v11 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
LABEL_20:
  v12 = v19;
  v13 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*((void (__fastcall **)(void **))*v13 + 2))(v13);
  }
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v12;
}

```

## disassembly

```asm
0x18001395c  mov     [rsp-20h+arg_10], r8
0x180013961  mov     [rsp-20h+arg_8], edx
0x180013965  push    rbp
0x180013966  push    rbx
0x180013967  push    rsi
0x180013968  push    rdi
0x180013969  mov     rbp, rsp
0x18001396c  sub     rsp, 48h
0x180013970  mov     rbx, rcx
0x180013973  mov     [rbp+arg_18], rcx
0x180013977  test    rcx, rcx
0x18001397a  jz      short loc_180013989
0x18001397c  mov     rax, [rcx]
0x18001397f  mov     rax, [rax+8]
0x180013983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013988  nop
0x180013989  mov     [rbp+arg_10], 0
0x180013991  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013998  mov     ecx, 40h ; '@'; unsigned __int64
0x18001399d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800139a2  test    rax, rax
0x1800139a5  jnz     short loc_1800139B3
0x1800139a7  mov     [rbp+arg_8], 8007000Eh
0x1800139ae  jmp     loc_180013AF7
0x1800139b3  mov     rcx, rax
0x1800139b6  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x1800139bb  mov     rsi, rax
0x1800139be  mov     r9d, 1F0003h; dwDesiredAccess
0x1800139c4  xor     r8d, r8d; dwFlags
0x1800139c7  xor     edx, edx; lpName
0x1800139c9  xor     ecx, ecx; lpEventAttributes
0x1800139cb  call    cs:__imp_CreateEventExW
0x1800139d2  nop     dword ptr [rax+rax+00h]
0x1800139d7  mov     [rsi+38h], rax
0x1800139db  test    rax, rax
0x1800139de  jnz     short loc_180013A17
0x1800139e0  call    cs:__imp_GetLastError
0x1800139e7  nop     dword ptr [rax+rax+00h]
0x1800139ec  mov     edi, eax
0x1800139ee  test    eax, eax
0x1800139f0  jle     short loc_1800139FB
0x1800139f2  movzx   edi, ax
0x1800139f5  or      edi, 80070000h
0x1800139fb  mov     rax, [rsi]
0x1800139fe  test    edi, edi
0x180013a00  jns     short loc_180013A1A
0x180013a02  mov     rcx, rsi
0x180013a05  mov     rax, [rax+10h]
0x180013a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a0e  nop
0x180013a0f  mov     [rbp+arg_8], edi
0x180013a12  jmp     loc_180013AF7
0x180013a17  mov     rax, [rsi]
0x180013a1a  mov     rcx, rsi
0x180013a1d  mov     rax, [rax+8]
0x180013a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a26  nop
0x180013a27  mov     [rbp+arg_10], rsi
0x180013a2b  mov     rax, [rsi]
0x180013a2e  mov     rcx, rsi
0x180013a31  mov     rax, [rax+10h]
0x180013a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a3a  nop
0x180013a3b  mov     [rbp+arg_8], 0
0x180013a42  mov     rax, [rbx]
0x180013a45  mov     rdx, [rbp+arg_10]
0x180013a49  mov     rcx, rbx
0x180013a4c  mov     rax, [rax+30h]
0x180013a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a55  mov     [rbp+arg_8], eax
0x180013a58  test    eax, eax
0x180013a5a  js      loc_180013AF7
0x180013a60  mov     rax, [rbp+arg_10]
0x180013a64  mov     rcx, [rax+38h]; HWND
0x180013a68  mov     [rbp+var_18], rcx
0x180013a6c  mov     [rbp+var_10], 0
0x180013a74  mov     r8d, 1; unsigned int
0x180013a7a  lea     rdx, [rbp+var_18]; void **
0x180013a7e  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180013a83  cmp     eax, 0FFFFFFFFh
0x180013a86  jnz     short loc_180013A8F
0x180013a88  mov     [rbp+arg_8], 80004005h
0x180013a8f  mov     [rbp+arg_0], 0
0x180013a97  cmp     [rbp+arg_8], 0
0x180013a9b  jl      short loc_180013AD9
0x180013a9d  mov     rax, [rbp+arg_10]
0x180013aa1  cmp     dword ptr [rax+30h], 1
0x180013aa5  jz      short loc_180013AD9
0x180013aa7  mov     rax, [rbx]
0x180013aaa  lea     r8, [rbp+arg_0]
0x180013aae  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180013ab5  mov     rcx, rbx
0x180013ab8  mov     rax, [rax]
0x180013abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac0  test    eax, eax
0x180013ac2  js      short loc_180013AD9
0x180013ac4  mov     rcx, [rbp+arg_0]
0x180013ac8  mov     rax, [rcx]
0x180013acb  lea     rdx, [rbp+arg_8]
0x180013acf  mov     rax, [rax+40h]
0x180013ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ad8  nop
0x180013ad9  mov     rcx, [rbp+arg_0]
0x180013add  test    rcx, rcx
0x180013ae0  jz      short loc_180013AF7
0x180013ae2  mov     [rbp+arg_0], 0
0x180013aea  mov     rax, [rcx]
0x180013aed  mov     rax, [rax+10h]
0x180013af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af6  nop
0x180013af7  mov     edi, [rbp+arg_8]
0x180013afa  mov     rcx, [rbp+arg_10]
0x180013afe  test    rcx, rcx
0x180013b01  jz      short loc_180013B18
0x180013b03  mov     [rbp+arg_10], 0
0x180013b0b  mov     rax, [rcx]
0x180013b0e  mov     rax, [rax+10h]
0x180013b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b17  nop
0x180013b18  test    rbx, rbx
0x180013b1b  jz      short loc_180013B2D
0x180013b1d  mov     rcx, [rbx]
0x180013b20  mov     rax, [rcx+10h]
0x180013b24  mov     rcx, rbx
0x180013b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b2c  nop
0x180013b2d  mov     eax, edi
0x180013b2f  add     rsp, 48h
0x180013b33  pop     rdi
0x180013b34  pop     rsi
0x180013b35  pop     rbx
0x180013b36  pop     rbp
0x180013b37  retn
```
