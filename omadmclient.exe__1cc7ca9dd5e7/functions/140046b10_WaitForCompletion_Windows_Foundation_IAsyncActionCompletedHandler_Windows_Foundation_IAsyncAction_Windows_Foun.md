# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x140046b10`
- end: `0x140046ced`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047850`
- `0x140047f60`

## callees

- `0x1400057fc`
- `0x140046b10`
- `0x140046dc8`
- `0x140048b74`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140046b7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140046b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b94`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
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
  v5 = (void **)`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::FTMEventDelegate(v4);
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
0x140046b10  mov     [rsp-20h+arg_10], r8
0x140046b15  mov     [rsp-20h+arg_8], edx
0x140046b19  push    rbp
0x140046b1a  push    rbx
0x140046b1b  push    rsi
0x140046b1c  push    rdi
0x140046b1d  mov     rbp, rsp
0x140046b20  sub     rsp, 48h
0x140046b24  mov     rbx, rcx
0x140046b27  mov     [rbp+arg_18], rcx
0x140046b2b  test    rcx, rcx
0x140046b2e  jz      short loc_140046B3D
0x140046b30  mov     rax, [rcx]
0x140046b33  mov     rax, [rax+8]
0x140046b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046b3c  nop
0x140046b3d  mov     [rbp+arg_10], 0
0x140046b45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046b4c  mov     ecx, 40h ; '@'; unsigned __int64
0x140046b51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140046b56  test    rax, rax
0x140046b59  jnz     short loc_140046B67
0x140046b5b  mov     [rbp+arg_8], 8007000Eh
0x140046b62  jmp     loc_140046CAB
0x140046b67  mov     rcx, rax
0x140046b6a  call    ??0FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x140046b6f  mov     rsi, rax
0x140046b72  mov     r9d, 1F0003h; dwDesiredAccess
0x140046b78  xor     r8d, r8d; dwFlags
0x140046b7b  xor     edx, edx; lpName
0x140046b7d  xor     ecx, ecx; lpEventAttributes
0x140046b7f  call    cs:__imp_CreateEventExW
0x140046b86  nop     dword ptr [rax+rax+00h]
0x140046b8b  mov     [rsi+38h], rax
0x140046b8f  test    rax, rax
0x140046b92  jnz     short loc_140046BCB
0x140046b94  call    cs:__imp_GetLastError
0x140046b9b  nop     dword ptr [rax+rax+00h]
0x140046ba0  mov     edi, eax
0x140046ba2  test    eax, eax
0x140046ba4  jle     short loc_140046BAF
0x140046ba6  movzx   edi, ax
0x140046ba9  or      edi, 80070000h
0x140046baf  mov     rax, [rsi]
0x140046bb2  test    edi, edi
0x140046bb4  jns     short loc_140046BCE
0x140046bb6  mov     rcx, rsi
0x140046bb9  mov     rax, [rax+10h]
0x140046bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046bc2  nop
0x140046bc3  mov     [rbp+arg_8], edi
0x140046bc6  jmp     loc_140046CAB
0x140046bcb  mov     rax, [rsi]
0x140046bce  mov     rcx, rsi
0x140046bd1  mov     rax, [rax+8]
0x140046bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046bda  nop
0x140046bdb  mov     [rbp+arg_10], rsi
0x140046bdf  mov     rax, [rsi]
0x140046be2  mov     rcx, rsi
0x140046be5  mov     rax, [rax+10h]
0x140046be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046bee  nop
0x140046bef  mov     [rbp+arg_8], 0
0x140046bf6  mov     rax, [rbx]
0x140046bf9  mov     rdx, [rbp+arg_10]
0x140046bfd  mov     rcx, rbx
0x140046c00  mov     rax, [rax+30h]
0x140046c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c09  mov     [rbp+arg_8], eax
0x140046c0c  test    eax, eax
0x140046c0e  js      loc_140046CAB
0x140046c14  mov     rax, [rbp+arg_10]
0x140046c18  mov     rcx, [rax+38h]; HWND
0x140046c1c  mov     [rbp+var_18], rcx
0x140046c20  mov     [rbp+var_10], 0
0x140046c28  mov     r8d, 1; unsigned int
0x140046c2e  lea     rdx, [rbp+var_18]; void **
0x140046c32  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x140046c37  cmp     eax, 0FFFFFFFFh
0x140046c3a  jnz     short loc_140046C43
0x140046c3c  mov     [rbp+arg_8], 80004005h
0x140046c43  mov     [rbp+arg_0], 0
0x140046c4b  cmp     [rbp+arg_8], 0
0x140046c4f  jl      short loc_140046C8D
0x140046c51  mov     rax, [rbp+arg_10]
0x140046c55  cmp     dword ptr [rax+30h], 1
0x140046c59  jz      short loc_140046C8D
0x140046c5b  mov     rax, [rbx]
0x140046c5e  lea     r8, [rbp+arg_0]
0x140046c62  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140046c69  mov     rcx, rbx
0x140046c6c  mov     rax, [rax]
0x140046c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c74  test    eax, eax
0x140046c76  js      short loc_140046C8D
0x140046c78  mov     rcx, [rbp+arg_0]
0x140046c7c  mov     rax, [rcx]
0x140046c7f  lea     rdx, [rbp+arg_8]
0x140046c83  mov     rax, [rax+40h]
0x140046c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c8c  nop
0x140046c8d  mov     rcx, [rbp+arg_0]
0x140046c91  test    rcx, rcx
0x140046c94  jz      short loc_140046CAB
0x140046c96  mov     [rbp+arg_0], 0
0x140046c9e  mov     rax, [rcx]
0x140046ca1  mov     rax, [rax+10h]
0x140046ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046caa  nop
0x140046cab  mov     edi, [rbp+arg_8]
0x140046cae  mov     rcx, [rbp+arg_10]
0x140046cb2  test    rcx, rcx
0x140046cb5  jz      short loc_140046CCC
0x140046cb7  mov     [rbp+arg_10], 0
0x140046cbf  mov     rax, [rcx]
0x140046cc2  mov     rax, [rax+10h]
0x140046cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046ccb  nop
0x140046ccc  test    rbx, rbx
0x140046ccf  jz      short loc_140046CE1
0x140046cd1  mov     rcx, [rbx]
0x140046cd4  mov     rax, [rcx+10h]
0x140046cd8  mov     rcx, rbx
0x140046cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046ce0  nop
0x140046ce1  mov     eax, edi
0x140046ce3  add     rsp, 48h
0x140046ce7  pop     rdi
0x140046ce8  pop     rsi
0x140046ce9  pop     rbx
0x140046cea  pop     rbp
0x140046ceb  retn
```
