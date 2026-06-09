# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800174b8`
- end: `0x1800175de`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011b00`

## callees

- `0x180011d6c`
- `0x180016ac8`
- `0x1800174b8`
- `0x18001ba64`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        char *a3)
{
  int v4; // ebx
  unsigned int v5; // r9d
  int v6; // eax
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v9; // [rsp+20h] [rbp-20h]
  unsigned int v10; // [rsp+28h] [rbp-18h]
  void *v11[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  void **v14; // [rsp+70h] [rbp+30h] BYREF
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // [rsp+78h] [rbp+38h] BYREF

  v14 = (void **)a3;
  v13 = a2;
  v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v14);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z((char **)&v14);
  v13 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), void **))(*a1)[6])(a1, v14);
    v13 = v4;
    if ( v4 >= 0 )
    {
      v11[0] = v14[7];
      v11[1] = 0;
      if ( SHProcessMessagesUntilEventsEx((HWND)v11[0], v11, 1u, v5, v9, v10) == -1 )
      {
        v6 = -2147467259;
        v13 = -2147467259;
      }
      else
      {
        v6 = v13;
      }
      v12 = 0;
      if ( v6 >= 0 && *((_DWORD *)v14 + 12) != 1 )
      {
        v7 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
        if ( v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12) >= 0 )
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v13);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      v4 = v13;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800174b8  mov     [rsp-18h+arg_10], r8
0x1800174bd  mov     [rsp-18h+arg_8], edx
0x1800174c1  push    rbp
0x1800174c2  push    rbx
0x1800174c3  push    rdi
0x1800174c4  mov     rbp, rsp
0x1800174c7  sub     rsp, 40h
0x1800174cb  mov     rdi, rcx
0x1800174ce  mov     [rbp+arg_18], rcx
0x1800174d2  test    rcx, rcx
0x1800174d5  jz      short loc_1800174E4
0x1800174d7  mov     rax, [rcx]
0x1800174da  mov     rax, [rax+8]
0x1800174de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174e3  nop
0x1800174e4  mov     [rbp+arg_10], 0
0x1800174ec  lea     rcx, [rbp+arg_10]
0x1800174f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800174f5  lea     rcx, [rbp+arg_10]
0x1800174f9  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x1800174fe  mov     ebx, eax
0x180017500  mov     [rbp+arg_8], eax
0x180017503  test    eax, eax
0x180017505  js      loc_1800175C0
0x18001750b  mov     rax, [rdi]
0x18001750e  mov     rdx, [rbp+arg_10]
0x180017512  mov     rcx, rdi
0x180017515  mov     rax, [rax+30h]
0x180017519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001751e  mov     ebx, eax
0x180017520  mov     [rbp+arg_8], eax
0x180017523  test    eax, eax
0x180017525  js      loc_1800175C0
0x18001752b  mov     rax, [rbp+arg_10]
0x18001752f  mov     rcx, [rax+38h]; HWND
0x180017533  mov     [rbp+var_10], rcx
0x180017537  mov     [rbp+var_8], 0
0x18001753f  mov     r8d, 1; unsigned int
0x180017545  lea     rdx, [rbp+var_10]; void **
0x180017549  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18001754e  cmp     eax, 0FFFFFFFFh
0x180017551  jnz     short loc_18001755D
0x180017553  mov     eax, 80004005h
0x180017558  mov     [rbp+arg_8], eax
0x18001755b  jmp     short loc_180017560
0x18001755d  mov     eax, [rbp+arg_8]
0x180017560  mov     [rbp+arg_0], 0
0x180017568  test    eax, eax
0x18001756a  js      short loc_1800175B4
0x18001756c  mov     rax, [rbp+arg_10]
0x180017570  cmp     dword ptr [rax+30h], 1
0x180017574  jz      short loc_1800175B4
0x180017576  mov     rax, [rdi]
0x180017579  mov     rbx, [rax]
0x18001757c  lea     rcx, [rbp+arg_0]
0x180017580  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017585  lea     r8, [rbp+arg_0]
0x180017589  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180017590  mov     rcx, rdi
0x180017593  mov     rax, rbx
0x180017596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001759b  test    eax, eax
0x18001759d  js      short loc_1800175B4
0x18001759f  mov     rcx, [rbp+arg_0]
0x1800175a3  mov     rax, [rcx]
0x1800175a6  lea     rdx, [rbp+arg_8]
0x1800175aa  mov     rax, [rax+40h]
0x1800175ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175b3  nop
0x1800175b4  lea     rcx, [rbp+arg_0]
0x1800175b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175bd  mov     ebx, [rbp+arg_8]
0x1800175c0  lea     rcx, [rbp+arg_10]
0x1800175c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175c9  nop
0x1800175ca  lea     rcx, [rbp+arg_18]
0x1800175ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175d3  mov     eax, ebx
0x1800175d5  add     rsp, 40h
0x1800175d9  pop     rdi
0x1800175da  pop     rbx
0x1800175db  pop     rbp
0x1800175dc  retn
```
