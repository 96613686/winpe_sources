# CComputeScribbleScheduler::CreateWakeupFence(CComputeScribbleScheduler::ScribbleFrame const &,ID3D12Fence * *)

- ea: `0x1801ea62c`
- end: `0x1801ea892`
- name: `?CreateWakeupFence@CComputeScribbleScheduler@@AEAAJAEBUScribbleFrame@1@PEAPEAUID3D12Fence@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(CComputeScribbleScheduler *__hidden this, const struct CComputeScribbleScheduler::ScribbleFrame *, struct ID3D12Fence **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18021b24c`

## callees

- `0x180026eac`
- `0x18004fce4`
- `0x18015a97c`
- `0x1801ea62c`
- `0x180254a0c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ea855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ea855`

## string_xrefs

- `0x1801ea69d`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801ea6da`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801ea734`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801ea77a`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801ea7c4`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`

## pseudocode

```c
__int64 __fastcall CComputeScribbleScheduler::CreateWakeupFence(
        CComputeScribbleScheduler *this,
        const struct CComputeScribbleScheduler::ScribbleFrame *a2,
        struct ID3D12Fence **a3)
{
  double v3; // xmm0_8
  __int64 v5; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct ID3D12Fence *v21; // rax
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-30h]
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  struct ID3D12Fence *v25; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v27; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+38h] BYREF
  __int64 v29; // [rsp+98h] [rbp+48h] BYREF

  v3 = *((double *)a2 + 2) * 10000000.0;
  v5 = *((_QWORD *)this + 3);
  v24 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(
         v5,
         *((_QWORD *)this + 4),
         (unsigned int)(int)v3,
         &v24);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 440;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)v10,
      v23);
LABEL_17:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v24);
    return v9;
  }
  if ( !v24 )
  {
    v9 = -2147024882;
    v11 = 443;
    v10 = 2147942414LL;
    goto LABEL_5;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 3);
  v27 = 0;
  v13 = (**v12)(v12, &GUID_64338358_366a_471b_bd56_dd8ef48e439b, &v27);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v13,
      v23);
LABEL_16:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v27);
    goto LABEL_17;
  }
  hObject = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v27 + 24LL))(v27, v24, 0, 0x10000000);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v14,
      0);
LABEL_15:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    goto LABEL_16;
  }
  v15 = *((_QWORD *)this + 2);
  v29 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 56LL))(
          v15,
          &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
          &v29);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v16,
      0);
LABEL_14:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
    goto LABEL_15;
  }
  v25 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, HANDLE, GUID *, struct ID3D12Fence **))(*(_QWORD *)v29 + 256LL))(
          v29,
          hObject,
          &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76,
          &v25);
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v17,
      0);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v25);
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x80000) != 0 )
    McTemplateU0xf_EventWriteTransfer(v19, v18, *(_QWORD *)a2);
  v21 = v25;
  v22 = v29;
  v25 = 0;
  *a3 = v21;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return 0;
}

```

## disassembly

```asm
0x1801ea62c  push    rbp
0x1801ea62e  push    rbx
0x1801ea62f  push    rsi
0x1801ea630  push    rdi
0x1801ea631  push    r14
0x1801ea633  mov     rbp, rsp
0x1801ea636  sub     rsp, 50h
0x1801ea63a  movsd   xmm0, qword ptr [rdx+10h]
0x1801ea63f  lea     r9, [rbp+var_10]
0x1801ea643  mulsd   xmm0, cs:__real@416312d000000000
0x1801ea64b  mov     rsi, rcx
0x1801ea64e  mov     rcx, [rcx+18h]
0x1801ea652  mov     r14, r8
0x1801ea655  mov     [rbp+var_10], 0
0x1801ea65d  mov     rdi, rdx
0x1801ea660  mov     rdx, [rsi+20h]
0x1801ea664  mov     rax, [rcx]
0x1801ea667  cvttsd2si r8, xmm0
0x1801ea66c  mov     rax, [rax+48h]
0x1801ea670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea675  mov     ebx, eax
0x1801ea677  test    eax, eax
0x1801ea679  jns     short loc_1801EA685
0x1801ea67b  mov     r9d, eax
0x1801ea67e  mov     edx, 1B8h
0x1801ea683  jmp     short loc_1801EA699
0x1801ea685  cmp     [rbp+var_10], 0
0x1801ea68a  jnz     short loc_1801EA6AE
0x1801ea68c  mov     ebx, 8007000Eh
0x1801ea691  mov     edx, 1BBh; void *
0x1801ea696  mov     r9d, ebx; char *
0x1801ea699  mov     rcx, [rbp+28h]; this
0x1801ea69d  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea6a9  jmp     loc_1801EA7FC
0x1801ea6ae  mov     rcx, [rsi+18h]
0x1801ea6b2  lea     r8, [rbp+arg_0]
0x1801ea6b6  mov     [rbp+arg_0], 0
0x1801ea6be  lea     rdx, _GUID_64338358_366a_471b_bd56_dd8ef48e439b
0x1801ea6c5  mov     rax, [rcx]
0x1801ea6c8  mov     rax, [rax]
0x1801ea6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea6d0  mov     ebx, eax
0x1801ea6d2  test    eax, eax
0x1801ea6d4  jns     short loc_1801EA6F3
0x1801ea6d6  mov     rcx, [rbp+28h]; this
0x1801ea6da  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea6e1  mov     r9d, eax; char *
0x1801ea6e4  mov     edx, 1BEh; void *
0x1801ea6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea6ee  jmp     loc_1801EA7F3
0x1801ea6f3  mov     rcx, [rbp+arg_0]
0x1801ea6f7  lea     rdx, [rbp+hObject]
0x1801ea6fb  mov     [rsp+50h+var_28], rdx
0x1801ea700  mov     r9d, 10000000h
0x1801ea706  mov     rdx, [rbp+var_10]
0x1801ea70a  xor     r8d, r8d
0x1801ea70d  mov     [rbp+hObject], 0
0x1801ea715  mov     rax, [rcx]
0x1801ea718  mov     qword ptr [rsp+50h+var_30], 0; int
0x1801ea721  mov     rax, [rax+18h]
0x1801ea725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea72a  mov     ebx, eax
0x1801ea72c  test    eax, eax
0x1801ea72e  jns     short loc_1801EA74D
0x1801ea730  mov     rcx, [rbp+28h]; this
0x1801ea734  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea73b  mov     r9d, eax; char *
0x1801ea73e  mov     edx, 1C6h; void *
0x1801ea743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea748  jmp     loc_1801EA7EA
0x1801ea74d  mov     rcx, [rsi+10h]
0x1801ea751  lea     r8, [rbp+arg_18]
0x1801ea755  mov     [rbp+arg_18], 0
0x1801ea75d  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1801ea764  mov     rax, [rcx]
0x1801ea767  mov     rax, [rax+38h]
0x1801ea76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea770  mov     ebx, eax
0x1801ea772  test    eax, eax
0x1801ea774  jns     short loc_1801EA790
0x1801ea776  mov     rcx, [rbp+28h]; this
0x1801ea77a  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea781  mov     r9d, eax; char *
0x1801ea784  mov     edx, 1C9h; void *
0x1801ea789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea78e  jmp     short loc_1801EA7E1
0x1801ea790  mov     rcx, [rbp+arg_18]
0x1801ea794  lea     r9, [rbp+var_8]
0x1801ea798  mov     rdx, [rbp+hObject]
0x1801ea79c  lea     r8, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1801ea7a3  mov     [rbp+var_8], 0
0x1801ea7ab  mov     rax, [rcx]
0x1801ea7ae  mov     rax, [rax+100h]
0x1801ea7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea7ba  mov     ebx, eax
0x1801ea7bc  test    eax, eax
0x1801ea7be  jns     short loc_1801EA809
0x1801ea7c0  mov     rcx, [rbp+28h]; this
0x1801ea7c4  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea7cb  mov     r9d, eax; char *
0x1801ea7ce  mov     edx, 1CDh; void *
0x1801ea7d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea7d8  lea     rcx, [rbp+var_8]
0x1801ea7dc  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ea7e1  lea     rcx, [rbp+arg_18]
0x1801ea7e5  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ea7ea  lea     rcx, [rbp+hObject]
0x1801ea7ee  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801ea7f3  lea     rcx, [rbp+arg_0]
0x1801ea7f7  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ea7fc  lea     rcx, [rbp+var_10]
0x1801ea800  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ea805  mov     eax, ebx
0x1801ea807  jmp     short loc_1801EA887
0x1801ea809  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+2, 8
0x1801ea810  jz      short loc_1801EA823
0x1801ea812  movsd   xmm3, qword ptr [rdi+10h]
0x1801ea817  mov     r8, [rdi]
0x1801ea81a  cvtpd2ps xmm3, xmm3
0x1801ea81e  call    McTemplateU0xf_EventWriteTransfer
0x1801ea823  mov     rax, [rbp+var_8]
0x1801ea827  mov     rcx, [rbp+arg_18]
0x1801ea82b  mov     [rbp+var_8], 0
0x1801ea833  mov     [r14], rax
0x1801ea836  test    rcx, rcx
0x1801ea839  jz      short loc_1801EA847
0x1801ea83b  mov     rax, [rcx]
0x1801ea83e  mov     rax, [rax+10h]
0x1801ea842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea847  mov     rcx, [rbp+hObject]; hObject
0x1801ea84b  lea     rax, [rcx-1]
0x1801ea84f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ea853  ja      short loc_1801EA85B
0x1801ea855  call    cs:__imp_CloseHandle
0x1801ea85b  mov     rcx, [rbp+arg_0]
0x1801ea85f  test    rcx, rcx
0x1801ea862  jz      short loc_1801EA870
0x1801ea864  mov     rax, [rcx]
0x1801ea867  mov     rax, [rax+10h]
0x1801ea86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea870  mov     rcx, [rbp+var_10]
0x1801ea874  test    rcx, rcx
0x1801ea877  jz      short loc_1801EA885
0x1801ea879  mov     rax, [rcx]
0x1801ea87c  mov     rax, [rax+10h]
0x1801ea880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea885  xor     eax, eax
0x1801ea887  add     rsp, 50h
0x1801ea88b  pop     r14
0x1801ea88d  pop     rdi
0x1801ea88e  pop     rsi
0x1801ea88f  pop     rbx
0x1801ea890  pop     rbp
0x1801ea891  retn
```
